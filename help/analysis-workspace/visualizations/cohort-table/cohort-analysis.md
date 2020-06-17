---
title: Cos’è un’analisi per coorte?
description: Scopri l’analisi per coorte in  Analysis Workspace
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 46%

---


# Che cosa è [!UICONTROL Cohort Analysis]?

>[!NOTE] Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Un *`cohort`* è un gruppo di persone che condividono le stesse caratteristiche per un determinato periodo di tempo. [!UICONTROL Cohort Analysis] è utile, ad esempio, quando si desidera imparare come una coorte si relaziona con un marchio. Permette di individuare facilmente cambiamenti nelle tendenze e reagire di conseguenza. (Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

Dopo aver generato un rapporto sulla coorte, puoi curarne i componenti (dimensioni, metriche e segmenti specifici) e condividerlo con chiunque. Vedi [Cura e condivisione](/help/analysis-workspace/curate-share/curate.md).

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* Lanciare campagne sviluppate per promuovere un’azione desiderata.
* Spostare il budget marketing nel momento giusto del ciclo di vita di un cliente.
* Riconoscere quando terminare una versione di prova o un&#39;offerta, al fine di massimizzare il valore.
* Sviluppare idee per il test A/B in aree come prezzo, percorso di upgrade ecc.
* View a [!UICONTROL Cohort Analysis] report within a Guided Analysis report.

[!UICONTROL Cohort Analysis] è disponibile per tutti i clienti Adobe  Analytics con diritti di accesso a [!UICONTROL Analysis Workspace].

[Analisi per coorte su YouTube](https://www.youtube.com/watch?v=kqOIYrvV-co&amp;index=45&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:36)

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] non supporta le metriche non filtrabili (comprese le metriche calcolate), le metriche non complete (come Entrate) o le occorrenze. Solo le metriche utilizzabili nei segmenti possono essere utilizzate in
>[!UICONTROL Cohort Analysis]e possono essere incrementati solo di 1 alla volta.

## Capacità dell’analisi per coorte

Le seguenti funzionalità consentono un controllo accurato delle coorti che si stanno creando:

### [!UICONTROL Retention] Tabella

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. Può contenere fino a 3 metriche e 10 segmenti.

![](assets/retention-report.png)

### [!UICONTROL Churn] Tabella

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. Può contenere fino a 3 metriche e 10 segmenti.

![](assets/churn-report.png)

### [!UICONTROL Rolling Calculation]

Consente di calcolare il livello di fidelizzazione o abbandono dei visitatori in base alla colonna precedente, non alla colonna Included (Incluso).

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Tabella

Misura il tempo trascorso prima e dopo il verificarsi dell’evento di inclusione. È un ottimo strumento di analisi pre/post. The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension] Coorte

Puoi creare le coorti in base a una dimensione selezionata, anziché in base al tempo come avviene per impostazione predefinita. Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

Per informazioni su come impostare ed eseguire un rapporto per coorte, consulta [Configurare un rapporto di analisi per coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).

