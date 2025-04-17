---
title: Dati di riepilogo
description: Dettagli e informazioni su come utilizzare e configurare i dati di riepilogo in una visualizzazione dati.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: e2e04432682f94b18bf9ed25d15f906c05bfd59d
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 99%

---

# Dati di riepilogo

I dati di riepilogo sono cati di serie temporali che non sono legati a un singolo ID persona. I dati di riepilogo rappresentano i dati aggregati a un diverso livello di aggregazione, ad esempio le campagne. Puoi utilizzare questi dati in Customer Journey Analytics per supportare vari casi d’uso. Ad esempio, dati contenenti una data e un singolo valore di metrica oppure dati contenenti più dimensioni e metriche.

Questi dati di riepilogo possono quindi essere utilizzati per presentare indicatori di prestazioni di alto livello o eseguire analisi. Esempi di dati di riepilogo possono essere impression pubblicitarie, aperture di e-mail, spese pubblicitarie, costo del bene venduto, indici S&amp;P e altro ancora. Puoi anche utilizzare i dati di riepilogo per caricare target o obiettivi su base oraria o giornaliera.

>[!NOTE]
>
>I dati di riepilogo sono dati di serie temporali provenienti da un set di dati di riepilogo. Tale set di dati di riepilogo è basato su uno schema che utilizza la classe Metriche di riepilogo XDM come classe base.
>Sono supportati solo i dati di serie temporali basate su ore o su giorni.

>[!TIP]
>
>Puoi configurare una connessione, una visualizzazione dati e successivamente generare un rapporto sui **soli** dati di riepilogo. Non è necessario disporre di dati evento, profilo o ricerca aggiuntivi come parte della configurazione.


## Esempio

Un esempio di utilizzo dei dati di riepilogo è la combinazione dei dati riepilogati delle campagne pubblicitarie con i dati click-stream nel sito per la generazione di rapporti.

### Dati di riepilogo

I dati di riepilogo contengono i seguenti dati della campagna pubblicitaria.

| Codice campagna | Impression | Costo |
|---|---:|---:|
| abc123 | 1.250 | $ 1.500 |
| def456 | 775 | $ 650 |
| ghi789 | 500 | $ 500 |


### Dati evento

I dati click-stream nel sito contengono i seguenti eventi.

| Codice di tracciamento | Click-through | Ricavi |
|---|---:|---:|
| abc123 | 1.250 | $ 7.200 |
| def456 | 775 | $ 1.250 |
| ghi789 | 500 | $ 750 |

### Dati combinati

Come spiegato in [Set di dati evento combinati](/help/connections/combined-dataset.md), quando si definisce una connessione, Customer Journey Analytics crea un set di dati evento combinati complessivo. Quando configuri la visualizzazione dati per le dimensioni provenienti da un set di dati di riepilogo, sono disponibili opzioni per raggruppare e nascondere le dimensioni in preparazione al reporting in Workspace. In particolare per i dati di riepilogo, questi vengono combinati con i dati evento, in base alla configurazione del [componente gruppo di dati di riepilogo](component-settings/summary-data-group.md).

| Codice di tracciamento | Codice campagna | Impression | Costo | Click-through | Ricavi |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1.250 | $ 1.500 | 1.250 | $ 7.200 |
| def456 | def123 | 775 | $ 650 | 775 | $ 1.250 |
| ghi789 | ghi789 | 500 | $ 500 | 500 | $ 750 |



### Reporting

La combinazione dei dati evento riepilogati e dei dati click-stream nel sito ti consente di generare rapporti in Workspace sul ritorno sulla spesa pubblicitaria (ROAS).

| Codice di tracciamento | Impression | Costo | Click-through | Ricavi | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1.250 | $ 1.500 | 1.250 | $ 7.200 | 4,80 |
| def456 | 775 | $ 650 | 775 | $ 1.250 | 1,92 |
| ghi789 | 500 | $ 500 | 500 | $ 750 | 1,50 |


### Dati di ricerca

Se desideri creare un rapporto utilizzando una dimensione definita in un set di dati di ricerca aggiuntivo (ad esempio, nome della campagna), devi seguire questi passaggi aggiuntivi:

1. Crea un nuovo campo derivato che utilizza la funzione [Ricerca](/help/data-views/derived-fields/derived-fields.md#lookup) per cercare il nome della campagna nel set di dati di ricerca. Nella definizione della funzione [Ricerca](/help/data-views/derived-fields/derived-fields.md#lookup) utilizzi la corrispondenza tra il codice della campagna e il codice di tracciamento per cercare il nome della campagna.
1. Aggiungi il campo derivato appena creato come componente dimensione alla visualizzazione dati.
1. Configura il componente dimensione nome campagna (dal set di dati di ricerca) in modo che abbia un raggruppamento di dati di riepilogo con il campo derivato appena creato.

Il caso d’uso [Acquisire e generare rapporti sui dati di riepilogo](/help/use-cases/data-views/summary-data.md) offre un articolo dettagliato su come utilizzare, creare rapporti e analizzare i dati di riepilogo in Customer Journey Analytics.


## Prerequisiti

Per utilizzare correttamente i dati di riepilogo nei rapporti e nelle analisi, è necessario soddisfare una serie di prerequisiti. Nelle sezioni seguenti vengono descritti in dettaglio questi prerequisiti.

### Granularità e fuso orario

Quando configuri il set di dati contenente i dati di riepilogo in Customer Journey Analytics, noti che la granularità viene derivata automaticamente dai dati. Le selezioni **[!UICONTROL Timestamp]** e **[!UICONTROL Timezone]** dell’elenco a discesa sono disabilitate in quanto derivano entrambe dalla definizione dello schema.

#### Granularità

Non è possibile combinare e abbinare la granularità oraria e giornaliera dei dati di riepilogo in un unico set di dati (o con set di dati diversi), utilizzando uno schema di dati di riepilogo. Ad esempio, se disponi di dati di riepilogo granulari giornalieri e orari per i dati della campagna pubblicitaria, sono necessari due schemi: uno per i dati di riepilogo giornalieri e uno per quelli orari. Quindi carica i dati granulari rilevanti nei set di dati associati allo schema appropriato (ad esempio, carica dati orari in un set di dati associato allo schema di dati di riepilogo orari).

#### Fuso orario

Il fuso orario dei dati di riepilogo è definito a livello di schema di riepilogo in Experience Platform. Il fuso orario si applica solo ai dati granulari orari.

- Per la granularità giornaliera, Experience Platform attribuisce valori UTC, a meno che la marca temporale non includa uno scostamento di fuso orario. Quando si aggiunge il set di dati di riepilogo contenente i dati di riepilogo giornalieri, Customer Journey Analytics ignora la definizione del fuso orario impostata nello schema e rispetta il giorno associato alla marca temporale dai dati nel set di dati.
- Per la granularità oraria, Customer Journey Analytics rispetta il fuso orario configurato nello schema dei dati di riepilogo in Experience Platform durante l’interpretazione della marca temporale. La tabella seguente fornisce alcuni esempi di tale interpretazione.

  | Marca temporale <br/>dati di origine | Schema<br/>fuso orario  | Marca temporale<br/>Experience<br/>Platform | Visualizzazione<br/> dati<br/>fuso orario | Marca temporale<br/>Customer<br/>Journey<br>Analytics |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *GMT predefinito* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *GMT predefinito* | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT predefinito* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT predefinito* | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 2024-08-02 | *GMT predefinito* | 2024-08-02T00:00:00 | IST | 2024-08-02T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles` | 2024-07-28T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  Per i fusi orari con uno scostamento di 30 minuti (ad esempio IST, Ora standard dell’India), lo scostamento di 30 minuti viene eliminato durante la generazione di rapporti sui dati di riepilogo. Ad esempio: 12:30 è indicato come 12:00.


Per garantire che venga utilizzato il fuso orario corretto per i dati di riepilogo granulari orari,devi assicurarti che nello schema utilizzato per i dati di riepilogo sia configurato il fuso orario corretto.

Per configurare la granularità e il fuso orario per lo schema dei dati di riepilogo, devi utilizzare la seguente chiamata API in quanto non è disponibile un’interfaccia utente equivalente.

```shell
curl -X POST \
https://platform.adobe.io/data/foundation/schemaregistry/tenant/descriptors \
 -H "Authorization: Bearer {$ACCESS_TOKEN}" \
 -H 'Content-Type: application/json' \
 -H 'x-api-key: {$API_KEY}' \
 -H 'x-gw-ims-org-id: {$ORG_ID}' \
 -H 'x-sandbox-name: {$SANDBOX_NAME}' \
 -d '{  
    "@type": "xdm:descriptorTimeSeriesGranularity",
    "xdm:sourceSchema": "{$SCHEMA_ID}",
    "xdm:sourceVersion": 1,
    "xdm:granularity": "{$GRANULARITY}",
    "xdm:ianaTimezone": "{$TIMEZONE}" 
 }'
```

| Variabile | Valore |
|---|---|
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | Per ulteriori informazioni su come specificare i valori per queste variabili, consulta [Autenticazione e accesso alle API di Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/landing/platform-apis/api-authentication). |
| `$SCHEMA_ID` | Puoi trovare l’ID dello schema nell’interfaccia utente di Experience Platform. Seleziona lo schema di riepilogo dall’elenco e individua **[!UICONTROL API Usage]** > **[!UICONTROL Schema ID]** nel pannello a destra. Utilizza tale ID come valore. |
| `$GRANULARITY` | Specifica `hour` o `day` come valore. |
| `$TIMEZONE` | Specifica il valore dell’identificatore del fuso orario corretto dalla colonna dell’identificatore TZ nell’[elenco dei fusi orari del database TZ](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). Ad esempio: `America/Los_Angeles`. |

## Impostazioni dei componenti

Assicurati che le impostazioni dei componenti per un gruppo di dati di riepilogo siano le stesse. Per ulteriori dettagli, consulta [Impostazioni del componente del gruppo di dati di riepilogo](component-settings/summary-data-group.md#same-component-settings).

>[!MORELIKETHIS]
>
>- Consulta l’articolo [Utilizzare i dati di riepilogo](/help/use-cases/data-views/summary-data.md) per un esempio dettagliato di caso d’uso su come utilizzare i dati di riepilogo e generare rapporti su di essi.
>- Blog: [Come i dati di riepilogo migliorano i set di dati di Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-summary-data-enhances-adobe-customer-journey-analytics/ba-p/704635)

