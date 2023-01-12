---
description: È possibile visualizzare le anomalie sotto forma di tabella o grafico a linee.
title: Visualizzare le anomalie in Analysis Workspace
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
source-git-commit: e62261d1d440c0a85e4cab95611c6e6272de6724
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 14%

---

# Visualizzare le anomalie in Analysis Workspace

È possibile visualizzare le anomalie sotto forma di tabella o grafico a linee.

## Visualizzazione delle anomalie in una tabella {#section_869A87B92B574A38B017A980ED8A29C5}

È possibile visualizzare le anomalie in una tabella a forma libera serie temporale.

1. Seleziona l’icona delle impostazioni della colonna nell’intestazione della colonna, quindi assicurati che la [!UICONTROL **Anomalie**] l’opzione è selezionata nell’elenco delle opzioni. Per ulteriori informazioni, consulta [Impostazioni colonna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Fai clic lontano dal menu impostazioni per visualizzare la tabella aggiornata.

   ![](assets/anomaly_detected.png)

1. Le anomalie sono mostrate nella tabella come segue:

   A **triangolo grigio scuro** nell’angolo in alto a destra di ogni riga in cui viene rilevata un’anomalia nei dati.

   Colorato **linea verticale** in ogni riga indica il valore previsto. Colorato **zona ombreggiata** in ogni riga indica il valore effettivo. Il modo in cui la linea (valore previsto) viene confrontata con l’area ombreggiata (valore effettivo) determina se vi è un’anomalia. (Un’osservazione è considerata anomala in base alle tecniche statistiche avanzate descritte in [Tecniche di statistica utilizzate nel rilevamento delle anomalie](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).)

1. Seleziona il triangolo grigio nell’angolo superiore destro di una riga per visualizzare i dettagli dell’anomalia. Mostra l’estensione (in percentuale) a cui il valore effettivo si discosta al di sopra o al di sotto del valore previsto.

## Visualizzazione delle anomalie in un grafico a linee {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

I grafici a linee sono l’unica visualizzazione che consente di visualizzare le anomalie.

Per visualizzare le anomalie in un grafico a linee:

1. Seleziona l’icona delle impostazioni nell’intestazione della visualizzazione, quindi assicurati che la [!UICONTROL **Mostra anomalie**] l’opzione è selezionata nell’elenco delle opzioni. Per ulteriori informazioni, consulta [Linea](/help/analysis-workspace/visualizations/line.md).

1. (Facoltativo) Per consentire all’intervallo di attendibilità di ridimensionare il grafico, seleziona l’icona delle impostazioni nell’intestazione della visualizzazione, quindi seleziona l’opzione , **[!UICONTROL Allow anomalies to Scale Y-axis]**.

   Questa opzione non è selezionata per impostazione predefinita perché a volte può rendere il grafico meno leggibile.

1. Fare clic lontano dal menu impostazioni per visualizzare il grafico a linee aggiornato.

   ![](assets/anomaly_linechart.png)

   Le anomalie vengono mostrate nel grafico a linee come segue:

   A **punto bianco** viene visualizzata sulla riga ogni volta che viene rilevata un’anomalia nei dati. (Un’osservazione è considerata anomala in base alle tecniche statistiche avanzate descritte in [Tecniche di statistica utilizzate nel rilevamento delle anomalie](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).)

   La **area ombreggiata luminosa** è la banda di valori affidabili, o l’intervallo previsto, in cui devono verificarsi i valori. Qualsiasi valore che non rientra nell’intervallo previsto è un’anomalia.

   Se nel grafico a linee sono presenti più metriche, vengono visualizzate solo le anomalie e devi passare il cursore del mouse su ciascuna anomalia per visualizzare la banda di affidabilità per tale metrica.

   La **linea tratteggiata** è il valore esatto previsto.

1. Fai clic su un’anomalia (punto bianco) per visualizzare le seguenti informazioni:

   * Data in cui si è verificata l’anomalia

   * il valore non elaborato dell’anomalia

   * La percentuale superiore o inferiore al valore previsto rappresentata dalla linea verde continua.

