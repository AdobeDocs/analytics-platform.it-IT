---
description: Scopri come visualizzare le anomalie in una tabella o in un grafico a linee.
title: Come visualizzare le anomalie in Analysis Workspace
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 88%

---

# Visualizzare le anomalie in Analysis Workspace

È possibile visualizzare le anomalie sotto forma di tabella o grafico a linee.

## Visualizzazione delle anomalie in una tabella {#table}

È possibile visualizzare le anomalie in una tabella a forma libera della serie temporale.

1. Seleziona l’icona delle impostazioni della colonna nell’intestazione della colonna, quindi assicurati che l’opzione [!UICONTROL **Anomalies**] (Anomalie) sia selezionata nell’elenco delle opzioni. Per ulteriori informazioni, consulta la sezione [Impostazioni delle colonne](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Fai clic lontano dal menu impostazioni per visualizzare la tabella aggiornata.

   ![È prevista una notifica di rilevamento delle anomalie che indica un valore inferiore del 15% rispetto a quello previsto.](assets/anomaly_detected.png)

1. Le anomalie sono mostrate nella tabella come segue:

   Compare un **triangolo grigio scuro** nell’angolo in alto a destra di ogni riga in cui viene rilevata un’anomalia nei dati.

   La **linea verticale** colorata in ogni riga indica il valore previsto. L’**area ombreggiata** in ogni riga indica il valore effettivo. Il modo in cui la linea (valore previsto) viene confrontata con l’area ombreggiata (valore effettivo) determina se vi è un’anomalia. (Un’osservazione è considerata anomala in base alle tecniche statistiche avanzate descritte in [Tecniche di statistica utilizzate nel rilevamento delle anomalie](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)).

1. Seleziona il triangolo grigio nell’angolo in alto a destra di una riga per visualizzare i dettagli dell’anomalia. Mostra la misura (in percentuale) in cui il valore effettivo si discosta al di sopra o al di sotto del valore previsto.

## Visualizzare le anomalie in un grafico a linee {#line-chart}

Un grafico a linee è l’unica visualizzazione che consente di visualizzare le anomalie.

Per visualizzare le anomalie in un grafico a linee:

1. Seleziona l’icona delle impostazioni nell’intestazione della visualizzazione, quindi assicurati che l’opzione [!UICONTROL **Show anomalies**] (Mostra anomalie) sia selezionata nell’elenco delle opzioni. Per ulteriori informazioni, consulta la sezione [Linea](/help/analysis-workspace/visualizations/line.md).

1. (Facoltativo) Per consentire all’intervallo di confidenza di dimensionare il grafico, seleziona l’icona delle impostazioni nell’intestazione della visualizzazione, quindi seleziona l’opzione **[!UICONTROL Allow anomalies to Scale Y-axis]**.

   Questa opzione non è selezionata per impostazione predefinita perché a volte può rendere il grafico meno leggibile.

1. Fai clic lontano dal menu impostazioni per visualizzare il grafico a linee aggiornato.

   ![Un grafico a linee con un’anomalia ha rilevato un messaggio che indica un aumento del 15% rispetto al previsto.](assets/anomaly_linechart.png)

   Le anomalie vengono mostrate nel grafico a linee come segue:

   Sulla riga compare un **punto bianco** ogni volta che viene rilevata un’anomalia nei dati. (Un’osservazione è considerata anomala in base alle tecniche statistiche avanzate descritte in [Tecniche di statistica utilizzate nel rilevamento delle anomalie](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)).

   L’**area ombreggiata chiara** è la banda di confidenza, o l’intervallo previsto, in cui devono trovarsi i valori. Qualsiasi valore che non rientra nell’intervallo previsto è un’anomalia.

   Nei grafici a linee per più metriche, sono mostrate solo le anomalie; quando si passa il mouse su un valore anomalo viene visualizzata la relativa banda di valori affidabili.

   La **linea tratteggiata** è il valore previsto esatto.

1. Fai clic su un’anomalia (punto bianco) per visualizzare le seguenti informazioni:

   * la data in cui si è verificata l’anomalia

   * il valore non elaborato dell’anomalia

   * la percentuale superiore o inferiore al valore previsto rappresentata dalla linea verde continua.

