---
title: Informazioni su eventi secondari e array di oggetti nei feed di dati
description: Scopri in che modo i feed di dati di Customer Journey Analytics esportano gli eventi secondari dagli array di schema, preservando la gerarchia invece di "appiattirli" come fa Workspace.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%
---
# Eventi secondari nei feed dati

{{release-limited-testing}}

Nello schema XDM, tutto ciò che è un array (stringa o oggetto) è un sottoevento. I sottoeventi in Customer Journey Analytics sono rappresentati nelle esportazioni di feed di dati con la relativa gerarchia.

In Adobe Analytics, i sottoeventi sono rappresentati come una singola colonna.

Utilizza le seguenti informazioni per comprendere come utilizzare i sottoeventi nei feed dati di Customer Journey Analytics.

## Eventi secondari nello schema XDM, in Workspace e nei feed di dati

Nello schema XDM, puoi definire i sottoeventi come array di stringhe o array di oggetti.

Questi eventi secondari vengono rappresentati in modo diverso, a seconda che vengano visualizzati in Analysis Workspace o nei feed di dati.

| Posizione | Modalità di rappresentazione dei sottoeventi |
| --- | --- |
| **Analysis Workspace** | I singoli oggetti in un array di oggetti possono essere selezionati come singoli componenti, separati da qualsiasi gerarchia visibile. |
| **Feed dati** | Gli oggetti in un array di oggetti sono rappresentati come un gruppo, con la gerarchia intatta. |

## Aggiungere dati di eventi secondari a un feed di dati

Quando tenti di aggiungere una colonna che è un evento secondario durante la creazione di un feed di dati, viene visualizzata una finestra di dialogo che ti consente di aggiungere tutti gli eventi secondari peer. Tutti questi eventi verranno visualizzati in una singola colonna dell’output del feed dati.

## Visualizzare i dati di eventi secondari nell’output del feed dati

I dati dei sottoeventi (come più prodotti in un singolo evento) vengono visualizzati in modo diverso nei feed di dati di Customer Journey Analytics rispetto ai feed di dati di Adobe Analytics. La tabella seguente confronta il modo in cui ogni prodotto rappresenta i dati dei sottoeventi.

| Prodotto | Visualizzazione dei dati di eventi secondari nei feed di dati | Esempio: elenco prodotti |
| --- | --- | --- |
| **Adobe Analytics** | Viene ridotta a una stringa delimitata in una singola colonna. | Un elenco di prodotti contiene più prodotti raggruppati in una singola stringa:<p>`;LG Washing Machine 2000;1;1600,;LG Dryer 2000;1;500` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | I sottoeventi mantengono la gerarchia definita nello schema XDM. Rimangono raggruppati nella stessa colonna, insieme all’evento principale e ai sottoeventi di pari livello. | Un elenco di prodotti mantiene la gerarchia definita nello schema XDM come array:<p>`[{"name":"LG Washing Machine 2000","units":1,"revenue":1600},{"name":"LG Dryer 2000","units":1,"revenue":500}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Eseguire query sui dati degli eventi secondari nell’output del feed dati

Poiché i dati dell&#39;evento secondario [&#x200B; vengono visualizzati in modo diverso nei feed dati di Customer Journey Analytics](#customer-journey-analytics-vs-adobe-analytics), le query utilizzate per tale evento sono diverse da quelle utilizzate per i feed dati di Adobe Analytics.

Gli esempi seguenti mostrano come trovare gli eventi che includono un prodotto specifico. Negli esempi viene utilizzata la sintassi BigQuery di Google. Altri data warehouse, come Snowflake e Databricks, supportano lo stesso approccio con differenze di sintassi minori.

+++ Eseguire query sui dati dei prodotti nei feed di dati di Adobe Analytics

Nei feed dati di Adobe Analytics, un evento con due prodotti acquistati insieme viene visualizzato come una singola stringa delimitata nella colonna `product_list`:

```text
Power Tools;Cordless Drill;1;129.99;event1=1;eVar10=DrillBundle,Power Tools;Drill Battery Pack;2;39.98;event1=1;eVar10=DrillBundle
```

Per trovare gli eventi che includono un trapano senza fili, analizzare questa stringa con un&#39;espressione regolare:

```sql
SELECT hitid_high, hitid_low, post_evar10
FROM aa_hit_data
WHERE REGEXP_CONTAINS(product_list, r'(^|,)[^;]*;Cordless Drill;')
```

+++

+++ Eseguire query sui dati dei prodotti nei feed di dati di Customer Journey Analytics

Nei feed di dati di Customer Journey Analytics, gli stessi due prodotti vengono visualizzati come un array di oggetti nella colonna `product_list_items`. Non è richiesta alcuna analisi del delimitatore:

```json
{
  "row_id": "01K3F2M9-...-4821",
  "timestamp_utc": "2026-09-16T14:32:07.512000Z",
  "product_list_items": [
    { "category": "Power Tools", "product": "Cordless Drill", "quantity": 1, "revenue": 129.99,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} },
    { "category": "Power Tools", "product": "Drill Battery Pack", "quantity": 2, "revenue": 39.98,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} }
  ]
}
```

La modalità di scrittura della query dipende dal fatto che si desideri una riga per evento o una riga per prodotto corrispondente.

**Restituire una riga per evento**

Per filtrare gli eventi senza modificare il numero di righe, utilizzare `UNNEST` all&#39;interno di una sottoquery `EXISTS`:

```sql
SELECT row_id, timestamp_utc, product_list_items
FROM `project.dataset.cja_data_feed` AS f
WHERE EXISTS (
  SELECT 1
  FROM UNNEST(f.product_list_items) AS item
  WHERE item.product = 'Cordless Drill'
);
```

Questa query restituisce una riga per ogni evento corrispondente, con l&#39;array `product_list_items` completo intatto, indipendentemente dal numero di prodotti nell&#39;array corrispondenti.

**Restituire una riga per prodotto corrispondente**

Per restituire una riga per ogni prodotto corrispondente, spostare `UNNEST` nella clausola `FROM` esterna:

```sql
SELECT f.row_id, f.timestamp_utc, item.product, item.quantity, item.revenue
FROM `project.dataset.cja_data_feed` AS f,
     UNNEST(f.product_list_items) AS item
WHERE item.product = 'Cordless Drill';
```

Un evento con più di un prodotto corrispondente viene visualizzato come più righe e le colonne dell&#39;evento, ad esempio `row_id`, vengono ripetute su ogni riga. Utilizzare questo approccio solo quando sono necessari dettagli a livello di prodotto. Per contare gli eventi nei risultati, utilizzare `COUNT(DISTINCT row_id)` invece di contare le righe.

Questo approccio si applica a qualsiasi campo array nello schema XDM, non solo ai prodotti.

+++






