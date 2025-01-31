---
description: In Analysis Workspace, le metriche possono essere utilizzate in due modi.
title: Metriche
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 5%

---

# Metriche

Le metriche consentono di quantificare i punti dati in Analysis Workspace. Sono più comunemente utilizzate come colonne in una visualizzazione e legate alle dimensioni.

## Utilizzare le metriche in Analysis Workspace

Le metriche sono flessibili per quanto riguarda il loro utilizzo in Analysis Workspace. Trascina una metrica in una tabella a forma libera vuota per visualizzare la tendenza della metrica nel periodo della data del progetto. Puoi anche trascinare una metrica quando è presente una dimensione per visualizzarla rispetto a ciascun elemento dimensione. Trascinare una metrica sopra un’intestazione di metrica esistente la sostituisce e trascinare una metrica accanto a un’intestazione consente di vedere entrambe le metriche una accanto all’altra.

Per informazioni su come aggiungere metriche e altri tipi di componenti ad Analysis Workspace, vedi [Utilizzare componenti in Analysis Workspace](/help/components/use-components-in-workspace.md).


## Tipi di metriche

Adobe offre diversi tipi di metriche da utilizzare in Analysis Workspace:


* **Metriche standard**: esempio di metriche standard: persone, sessioni, eventi.

  A differenza di Adobe Analytics, Customer Journey Analytics consente di definire le metriche standard in modo flessibile all’interno dell’ambito di una connessione e di una visualizzazione dati.

   * **Persone**: la metrica Persone nel Customer Journey Analytics è il conteggio distinto degli ID persona. A seconda di quello che scegli come ID persona quando configuri i set di dati nella connessione, la metrica Persone può significare cose diverse.
   * **Sessioni**: la metrica Sessioni nel Customer Journey Analytics è ciò che si definisce come parte della configurazione delle Impostazioni sessioni nella visualizzazione dati. Vedere [Impostazioni sessione](/help/data-views/session-settings.md).
   * **Eventi**: la metrica Eventi nel Customer Journey Analytics è composta dagli eventi che fanno parte di qualsiasi set di dati evento configurato come parte della connessione.

* **Metriche calcolate** ![Calcolatore](/help/assets/icons/Calculator.svg): metriche definite dall&#39;utente basate su metriche standard, numeri statici o funzioni algoritmiche.

* **Modelli di metriche calcolate** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg): metriche definite dall&#39;Adobe che si comportano in modo simile alle metriche calcolate. Puoi utilizzarli così come sono nei progetti Workspace o salvarne una copia per personalizzare la logica. Vedi [Metriche calcolate predefinite](calc-metrics/cm-workflow/../default-calcmetrics.md).

Puoi vedere se una metrica è approvata ![Icona Approvata](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) o meno. Per ulteriori dettagli su una metrica, passa il cursore del mouse sulla metrica e seleziona ![Icona informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Per ulteriori informazioni, vedere [Informazioni sul componente](use-components-in-workspace.md#component-info).



## Metriche calcolate

Le metriche calcolate consentono di configurare facilmente il modo in cui le metriche si relazionano tra loro utilizzando semplici operatori o funzioni statistiche. Per ulteriori informazioni, vedere [Panoramica delle metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md).

<!--

There are several ways to create calculated metrics. See [Create calculated metrics]()

### Create calculated metrics for all projects

You can use the calculated metric builder to create calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. 

For information about how to access the calculated metrics builder, see [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Create calculated metrics for a single project

You can create quick calculated metrics that are available only for the project where they were created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, select **[!UICONTROL Create metric from selection]** from the context menu in a column header.

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the following options:

   * [!UICONTROL **Divide**]
   
   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Add**]

   * [!UICONTROL **Multiply**]

   Or, to open the calculated metric builder and create the calculated metric for all projects, select [!UICONTROL **Open in Calculated Metric Builder**], then continue with [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).


<!-- This video really shows an AA example using hits, etc.  Not suitable for CJA... >
+++ See the following video on how to create an implementation-less calculated metric from within Analysis Workspace.

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)


>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12&learn=on)

+++

-->

## Confrontare metriche con diversi modelli di attribuzione

Per confrontare in modo rapido e semplice un modello di attribuzione con un altro per una metrica, selezionare **[!UICONTROL Compare attribution models]** dal menu di scelta rapida per una metrica.

![Evidenziazione del pannello Workspace Confronta modelli di attribuzione](assets/compare-attribution.png)

Questa scelta rapida consente di confrontare in modo rapido e semplice i modelli di attribuzione.
