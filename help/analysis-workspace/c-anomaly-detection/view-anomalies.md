---
description: Scopri come visualizzare e analizzare le anomalie nei dati in modo contestuale, in Analysis Workspace.
title: Panoramica di Rilevamento delle anomalie
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
role: User
source-git-commit: 808b09d79d3c686747f7b19b6646001e3345b9aa
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 51%

---


# Visualizzare le anomalie

In Analysis Workspace puoi visualizzare le anomalie in una tabella o in un grafico a linee.

## Visualizzazione delle anomalie in una tabella {#section_869A87B92B574A38B017A980ED8A29C5}

È possibile visualizzare le anomalie in una tabella a forma libera della serie temporale.

1. Seleziona ![Impostazione](/help/assets/icons/Setting.svg) nell&#39;intestazione della colonna, quindi accertati che l&#39;opzione **[!UICONTROL Show anomalies]** sia selezionata nell&#39;elenco delle opzioni. Per ulteriori informazioni, consulta la sezione [Impostazioni delle colonne](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Le anomalie sono mostrate nella tabella come segue:

   ![Anomalie rilevate](assets/anomaly-detected.png)

   ◥ viene visualizzato nell&#39;angolo superiore destro di ogni riga in cui viene rilevata un&#39;anomalia di dati.

   La **linea verticale colorata** in ogni riga ➋ indica il valore previsto. L&#39;**area ombreggiata colorata** in ogni riga ➊ indica il valore effettivo. Il modo in cui la linea (valore previsto) viene confrontata con l’area ombreggiata (valore effettivo) determina se vi è un’anomalia. Un&#39;osservazione è considerata anomala in base alle tecniche statistiche avanzate descritte in [Tecniche statistiche utilizzate nel rilevamento delle anomalie](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

1. Selezionare ◥ nell&#39;angolo superiore destro di una riga per visualizzare i dettagli sull&#39;anomalia. Mostra la misura (in percentuale) in cui il valore effettivo si discosta al di sopra o al di sotto del valore previsto.

## Visualizzare le anomalie in un grafico a linee

I grafici a linee sono l’unica visualizzazione che consente di visualizzare le anomalie.

Per visualizzare le anomalie in un grafico a linee:

1. Seleziona ![Impostazione](/help/assets/icons/Setting.svg) nell&#39;intestazione della visualizzazione, quindi accertati che l&#39;opzione [!UICONTROL **Mostra anomalie**] sia selezionata nell&#39;elenco delle opzioni. Per ulteriori informazioni, consulta la sezione [Linea](/help/analysis-workspace/visualizations/line.md).

1. (Facoltativo) Per consentire all&#39;intervallo di attendibilità di ridimensionare il grafico, seleziona ![Impostazione](/help/assets/icons/Setting.svg) nell&#39;intestazione della visualizzazione, quindi seleziona l&#39;opzione, **[!UICONTROL Allow anomalies to Scale Y-axis]**.

   Questa opzione non è selezionata per impostazione predefinita perché a volte può rendere il grafico meno leggibile.

   Le anomalie vengono mostrate nel grafico a linee come segue:

   ![Visualizzazione riga rilevata anomalia](assets/anomaly-detected-line.png)

   Sulla riga compare un **punto bianco** ogni volta che viene rilevata un’anomalia nei dati. Un&#39;osservazione è considerata anomala in base alle tecniche statistiche avanzate descritte in [Tecniche statistiche utilizzate nel rilevamento delle anomalie](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

   L’**area ombreggiata chiara** è la banda di confidenza, o l’intervallo previsto, in cui devono trovarsi i valori. Qualsiasi valore che non rientra nell’intervallo previsto è un’anomalia.

   Nei grafici a linee per più metriche, sono mostrate solo le anomalie; quando si passa il puntatore su un valore anomalo viene visualizzata la relativa banda di valori affidabili.

   La **linea tratteggiata** è il valore previsto esatto.

1. Seleziona un’anomalia (punto bianco) per visualizzare le seguenti informazioni:

   * La data in cui si è verificata l’anomalia.

   * Il valore non elaborato dell’anomalia.

   * la percentuale superiore o inferiore al valore previsto rappresentata dalla linea verde continua.








<!--
# View anomalies in Analysis Workspace

You can view anomalies in a table or in a line chart.

## View anomalies in a table {#table}

You can view anomalies in a time-series Freeform Table.

1. Select the column settings icon in the column header, then ensure that the [!UICONTROL **Anomalies**] option is selected in the list of options. For more information, see [Column settings](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Click away from the settings menu to view the updated table.

   ![An anomaly detection notification indicating 15% below expected.](assets/anomaly_detected.png)

1. Anomalies are shown in the table as follows:

   A **dark gray triangle** appears in the upper-right corner of each row where a data anomaly is detected.

   The colored **vertical line** in each row indicates the expected value. The colored **shaded area** in each row indicates the actual value. How the line (expected value) compares with the shaded area (actual value) determines whether there is an anomaly. (An observation is considered anomolous based on the advanced statistical techniques described in [Statistical techniques used in anomaly detection](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

1. Select the gray triangle in the upper-right corner of a row to view details about the anomaly. This shows the extent (as a percentage) to which the actual value diverges either above or below the expected value.

## View anomalies in a line chart {#line-chart}

A Line chart is the only visualization that allows you to view anomalies.

To view anomalies in a line chart:

1. Select the settings icon in the visualization header, then ensure that the [!UICONTROL **Show anomalies**] option is selected in the list of options. For more information, see [Line](/help/analysis-workspace/visualizations/line.md).

1. (Optional) To allow the confidence interval to scale the chart, select the settings icon in the visualization header, then select the option, **[!UICONTROL Allow anomalies to Scale Y-axis]**. 

   This option is not selected by default because it can sometimes make the chart less legible.
   
1. Click away from the settings menu to view the updated line chart.

      ![A line chart with an anomaly detected message indicating 15% above expected.](assets/anomaly_linechart.png)

   Anomalies are shown in the line chart as follows:
   
   A **white dot** appears on the line wherever a data anomaly is detected. (An observation is considered anomolous based on the advanced statistical techniques described in [Statistical techniques used in anomaly detection](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

   The **light shaded area** is the confidence band, or expected range, where values should occur. Any value that falls outside of this expected range is an anomaly. 

   If you have multiple metrics in the line chart, only the anomalies are shown and you have to hover over each anomaly to see the confidence band for that metric. 

   The **dotted line** is the exact expected value.

1. Click an anomaly (white dot) to view the following information:

   * The date the anomaly occurred 
   
   * The raw value of the anomaly 
   
   * The percentage value above or below the expected value, which is represented by the solid green line.
   
-->
