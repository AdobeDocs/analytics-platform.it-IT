---
description: Scopri come utilizzare un istogramma, simile a un grafico a barre, ma che raggruppa i numeri in intervalli.
title: Istogramma
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 90%

---

# Istogramma {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Istogramma"
>abstract="Crea una visualizzazione a istogramma per rappresentare la distribuzione dei dati numerici in gruppi di intervalli."


>[!BEGINSHADEBOX]

_Questo articolo descrive la visualizzazione a istogramma in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Consulta [Istogramma](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/visualizations/histogram) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]


Una visualizzazione a **[!UICONTROL Histogram]** ![istogramma](/help/assets/icons/Histogram.svg) è simile a una visualizzazione [!UICONTROL Bar], ma con i numeri raggruppati in intervalli (bucket). Analytics automatizza la creazione di intervalli di numeri, ma puoi comunque cambiare le impostazioni in [Impostazioni avanzate](#advanced-settings).

## Utilizzo

Per creare un istogramma:

1. Aggiungi una visualizzazione a **[!UICONTROL Histogram]** ![istogramma](/help/assets/icons/Histogram.svg). Consulta [Aggiungere una visualizzazione a un pannello](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Trascinare una metrica dall&#39;elenco dei componenti **[!UICONTROL Metrics]** oppure selezionare una metrica dal menu a discesa [!UICONTROL *Aggiungi una metrica*].
1. (facoltativo) Seleziona **[!UICONTROL Show advanced settings]**. Consulta [Impostazioni avanzate](#advanced-settings).
1. Seleziona **[!UICONTROL Build]**.

>[!NOTE]
>
>Gli istogrammi supportano solo metriche standard; le metriche calcolate non sono supportate.

Nell’esempio seguente, viene utilizzato un istogramma per le sessioni di bucket relative al numero di persone. L’istogramma mostra che la maggior parte delle persone ha tra 16 e 21 sessioni per l’intervallo di date selezionato.

![Istogramma](assets/histogram.png)

## Impostazioni avanzate

Come parte della visualizzazione, sono disponibili impostazioni specifiche dell’istogramma.

| Impostazioni istogramma | Descrizione |
|---|---|
| **[!UICONTROL Starting bucket]** | Determina con quale intervallo inizia l’istogramma. L’impostazione predefinita è 1. Puoi impostare il numero iniziale da 0 all’infinito (non sono consentiti numeri negativi). |
| **[!UICONTROL Metric buckets]** | Consente di aumentare/diminuire il numero di intervalli di dati (bucket). Il numero massimo di bucket è 50. |
| **[!UICONTROL Metric bucket size]** | Puoi impostare la dimensione di ogni intervallo. Ad esempio, puoi cambiare la dimensione dell’intervallo da 1 a 2 visualizzazioni di pagina. |
| **[!UICONTROL Counting method]** | Seleziona da **[!UICONTROL Global Account]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Account]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Buying Group]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Opportunity]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Person]**, **[!UICONTROL Session]** o **[!UICONTROL Event]**. Ad esempio, visualizzazioni di pagina per account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, per sessione, per persona o per evento. |

<!--Russ or Meike - Check Hit Type link above. -->

**Esempi**:

| Bucket iniziale | Bucket metrica | Dimensione bucket di metrica | Risultato |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Istogramma, bucket iniziale 1, bucket metrica 5, dimensione bucket metrica 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Istogramma, bucket iniziale 0, bucket metrica 3, dimensione bucket metrica 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Aggiungere una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Impostazioni di visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Menu di scelta rapida visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>&#x200B;>[Utilizzo di istogrammi per identificare valori di dati imprevisti](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

