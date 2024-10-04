---
description: Un istogramma è simile a un grafico a barre, ma con i numeri raggruppati in intervalli.
title: Istogramma
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 40%

---

# Istogramma {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_histogram_button"
>title="Istogramma"
>abstract="Crea una visualizzazione istogramma per rappresentare la distribuzione dei dati numerici in gruppi di intervalli."

<!-- markdownlint-enable MD034 -->


La visualizzazione ![Istogramma](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogram]** è simile a una visualizzazione [!UICONTROL Bar], ma raggruppa i numeri in intervalli (bucket). Analytics automatizza la creazione di intervalli di numeri, ma puoi comunque cambiare le impostazioni in [Impostazioni avanzate](#advanced-settings).

## Seleziona

Per creare un istogramma:

1. Aggiungi una visualizzazione ![Istogramma](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogram]**. Vedi [Aggiungere una visualizzazione a un pannello](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Trascinare una metrica dall&#39;elenco dei componenti **[!UICONTROL Metrics]** oppure selezionare una metrica dal menu a discesa [!UICONTROL *Aggiungi una metrica*].
1. (facoltativo) Selezionare **[!UICONTROL Show advanced settings]**. Vedi [Impostazioni avanzate](#advanced-settings).
1. Seleziona **[!UICONTROL Build]**.

>[!NOTE]
>
>Gli istogrammi supportano solo metriche standard; le metriche calcolate non sono supportate.

Nell’esempio seguente, viene utilizzato un istogramma per le sessioni di bucket relative al numero di persone. L’istogramma mostra che la maggior parte delle persone ha tra 16 e 21 sessioni per l’intervallo di dati selezionato.

![](assets/histogram.png)

## Impostazioni avanzate

Come parte della visualizzazione, sono disponibili impostazioni specifiche dell’istogramma.

| Impostazioni degli istogrammi | Descrizione |
|---|---|
| **[!UICONTROL Starting bucket]** | Determina con quale intervallo inizia l’istogramma. L’impostazione predefinita è 1. Puoi impostare il numero iniziale da 0 all’infinito (non sono consentiti numeri negativi). |
| **[!UICONTROL Metric buckets]** | Puoi aumentare o ridurre il numero di intervalli di dati. Il numero massimo consentito è 50. |
| **[!UICONTROL Metric bucket size]** | Puoi impostare la dimensione di ogni intervallo. Ad esempio, puoi cambiare la dimensione dell’intervallo da 1 a 2 visualizzazioni di pagina. |
| **[!UICONTROL Counting method]** | Seleziona tra **[!UICONTROL Person]**, **[!UICONTROL Session]** o **[!UICONTROL Event]**. Ad esempio, visualizzazioni pagina per sessione, visualizzazioni pagina per persona o visualizzazioni pagina per evento. |

<!--Russ or Meike - Check Hit Type link above. -->

**Esempi**:

| Bucket iniziale | Periodi fissi di metrica | Dimensione del bucket della metrica | Risultato |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Istogramma, bucket iniziale 1, bucket metrica 5, dimensione bucket metrica 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Istogramma, bucket iniziale 0, bucket metrica 3, dimensione bucket metrica 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Aggiungi una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Impostazioni visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu di scelta rapida visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>


## Post di blog

Consulta questo post di blog sulle informazioni sull&#39;utilizzo di [istogrammi per identificare valori di dati imprevisti](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168).
