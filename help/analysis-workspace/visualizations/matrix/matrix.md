---
title: Panoramica della visualizzazione a matrice in Analysis Workspace
description: Scopri la visualizzazione a matrice in Customer Journey Analytics Analysis Workspace, compresi cosa mostra, quando utilizzarla e come si confronta con altre visualizzazioni.
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 2%
---

# Panoramica sulla matrice {#matrix-overview}

La visualizzazione della matrice in Analysis Workspace consente di visualizzare in che modo gli elementi dimensionali di due dimensioni si sovrappongono o si correlano tra loro.

Gli elementi Dimension per una dimensione vengono visualizzati come righe (lungo l’asse Y), mentre gli elementi dimensione per l’altra dimensione vengono visualizzati come colonne (lungo l’asse X). Ogni cella che si interseca mostra i dati di sovrapposizione o di correlazione, basati sulla metrica scelta.

Ad esempio, la seguente visualizzazione della matrice mostra il conteggio di sovrapposizione degli eventi per i nomi dei dispositivi in base al codice del paese.

* Dimension 1 (dimensione riga): nome dispositivo

* Dimension 2 (dimensione colonna): codice paese

* Metrica: Eventi

![Panoramica matrice](assets/matrix-overview.png)

## Funzioni chiave

* **Confronta due dimensioni diverse**: verifica la correlazione tra gli elementi di una dimensione e gli elementi di un&#39;altra dimensione.

* **Confronta una dimensione con se stessa**: verifica la correlazione tra gli elementi nella stessa dimensione.

* **Sovrapposizione**: visualizza la sovrapposizione di elementi dimensionali.

* **Correlazione**: verifica la correlazione tra gli elementi dimensionali su una scala da -1 (spostarsi sempre in direzioni opposte) a +1 (spostarsi sempre insieme).

* **Colori mappa di calore**: il colore della cella indica se la sovrapposizione è alta o bassa oppure se la correlazione è positiva o negativa e quanto è forte. Sovrapposizione e correlazione hanno palette di colori separate.

## Insight potenziali

* Trovate le serie e gli spazi vuoti tra due dimensioni. Ad esempio, puoi rispondere a domande come:

  * Quali campagne ottengono buoni risultati in alcune aree geografiche ma non in altre?

  * Quali tipi di contenuto hanno prestazioni migliori su ciascun tipo di dispositivo?

* Scopri la tendenza degli elementi dimensionali in relazione tra loro. Ad esempio, puoi rispondere a domande come:

  * Quali canali di marketing tendono insieme nel tempo, quali si muovono in modo indipendente e quali in direzioni opposte?

  * Quali pagine presentano un traffico che aumenta e diminuisce?

* Confrontare una dimensione con se stessa. Ad esempio, puoi rispondere a domande come:

  * Quali prodotti vengono spesso acquistati dalle stesse persone?

  * Quali dispositivi utilizzano insieme le stesse persone, ad esempio telefoni cellulari e tablet?

## Scegli tra visualizzazioni a matrice, tabella a forma libera, Venn o a dispersione

La visualizzazione della matrice ha analogie con [l&#39;utilizzo di più colonne di dimensione in una tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md), la [visualizzazione Venn](/help/analysis-workspace/visualizations/venn.md) e la [visualizzazione a dispersione](/help/analysis-workspace/visualizations/scatterplot.md). Ogni visualizzazione mostra la correlazione tra i componenti, ma le differenze riguardano i componenti utilizzati e il modo in cui visualizzano i risultati.

### Quando utilizzare ciascuna visualizzazione

Scegli la visualizzazione più adatta alla tua analisi:

* **Matrice:** Per una determinata metrica, vedi in che modo ogni elemento dimensione in una dimensione si relaziona a ogni elemento dimensione in un&#39;altra, inclusi gli spazi vuoti e gli elementi dimensione con tendenze congiunte.

* **Tabella a forma libera con più colonne di dimensione:** È possibile aggiungere fino a 5 dimensioni come colonne separate in una tabella a forma libera. Gli elementi Dimension visualizzati nella stessa riga della tabella vengono concatenati. Aggiungi alla tabella un numero qualsiasi di metriche per visualizzare i dati delle metriche per ciascun elemento della dimensione concatenato. Filtra, ordina e aggiungi suddivisioni agli elementi dimensionali concatenati.

* **Venn:** Per una singola metrica, visualizzare la sovrapposizione di un massimo di 3 segmenti.

* **A dispersione:** confrontare elementi dimensionali in due o tre metriche per trovare pattern e outlier.

### Comprendere le differenze

<!-- SME CHECK: Confirm the Matrix cells: segments can't be used as rows or columns. Container row: confirm what each Matrix container means for overlap, and that freeform combinations are based on the dimension items that apply to each event. -->

| Funzione | Matrice | Più colonne di dimensione in una tabella a forma libera | Venn | A dispersione |
| --- | --- | --- | --- | --- |
| **Componenti utilizzati** | 2 dimensioni; 1 metrica<p>Confronta elementi dimensionali da 2 dimensioni o da 1 dimensione con se stessa.</p> | Fino a 5 dimensioni; qualsiasi numero di metriche<p>Gli elementi Dimension visualizzati nella stessa riga sono concatenati e si comportano come un singolo elemento dimensionale. Le righe concatenate vengono confrontate in base ai loro valori di metrica.</p> | Fino a 3 segmenti; 1 metrica<p>Confronta la sovrapposizione tra segmenti.</p> | 1 dimensione; fino a 3 metriche<p>Confronta gli elementi dimensionali tra le metriche.</p> |
| **Contenitore** | Impostato nella visualizzazione: Persona (impostazione predefinita), Sessione o Evento<p>Determina se la sovrapposizione conta gli elementi dimensionali che si verificano per la stessa persona, nella stessa sessione o nello stesso evento.</p> | Nessuna impostazione contenitore<p>Ogni riga combina gli elementi dimensionali applicabili allo stesso evento. La metrica scelta, ad esempio Persone o Sessioni, determina ciò che viene conteggiato.</p> | Imposta in ciascun segmento<p>Ogni segmento utilizza il proprio [contenitore](/help/components/segments/seg-overview.md#containers) (persona, sessione o evento). La metrica determina cosa viene conteggiato in ogni sovrapposizione.</p> | Nessuna impostazione contenitore<p>Le metriche scelte determinano il conteggio.</p> |
| **Layout** | Griglia, simile a una tabella pivot<p>Gli elementi Dimension di una dimensione sono righe, mentre gli elementi dimensione dell’altra dimensione sono colonne.</p> | Elenco<p>Ogni riga combina un elemento dimensione da ogni colonna dimensione.</p> | Cerchi sovrapposti | Punti sull&#39;asse X e sull&#39;asse Y |
| **Mostra sovrapposizione** | Sì<p>Mostra la sovrapposizione tra ogni elemento dimensione nelle righe e ogni elemento dimensione nelle colonne.</p><p>Utilizza la visualizzazione **[!UICONTROL Conteggio sovrapposizioni]**.</p> | Sì<p>Mostra la metrica per ogni combinazione di elementi dimensionali, una combinazione per riga.</p> | Sì<p>Mostra la sovrapposizione tra segmenti.</p> | No |
| **Mostra correlazione** | Sì, tra elementi dimensionali<p>Mostra la tendenza degli elementi dimensionali nel tempo, su una scala da -1 (direzioni opposte) a +1 (insieme).</p><p>Utilizza la visualizzazione **[!UICONTROL Forza di correlazione]**.</p> | No | No | Sì, tra metriche<p>Mostra la correlazione tra le metriche. Ogni punto è un elemento dimensionale tracciato da un massimo di 3 metriche.</p> |

{style="table-layout:auto"}

