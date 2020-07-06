---
description: È possibile visualizzare le anomalie sotto forma di tabella o grafico a linee.
title: Visualizzare le anomalie in Analysis Workspace
uuid: 270a7ea9-6485-4c83-8220-5a2200bd7200
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 91%

---


# Visualizzare le anomalie in Analysis Workspace

>[!NOTE]
>
>Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

È possibile visualizzare le anomalie sotto forma di tabella o grafico a linee.

## Visualizzazione delle anomalie in una tabella {#section_869A87B92B574A38B017A980ED8A29C5}

In una tabella a forma libera su serie temporale, ogni riga viene ora segnalata con un punto esclamativo grigio scuro se viene rilevata un’anomalia nei dati.

![](assets/anomaly_detected.png)

La linea grigia verticale in ogni riga indica il valore previsto. Quando si passa il cursore sul punto esclamativo, viene indicato di quanto l’anomalia si scosta dal valore previsto (sotto forma di +/- %).

## Visualizzazione delle anomalie in un grafico a linee {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

Il grafico a linee mostra la banda di valori affidabili in verde chiaro e i valori anomali come punti bianchi.

Se fai clic su un punto bianco, questo diventerà verde e mostrerà:

* la data in cui si è verificata l’anomalia
* il valore non elaborato dell’anomalia
* La percentuale superiore o inferiore al valore previsto rappresentata dalla linea verde continua.
<!--* The Analyze link to start [Contribution Analysis](/help/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md).-->

![](assets/anomaly_linechart.png)

Nei grafici a linee per più metriche, sono rappresentate solo le anomalie; quando si passa il mouse su un valore anomalo viene visualizzata la relativa banda di valori affidabili.

L’intervallo di attendibilità per il rilevamento delle anomalie non ridimensiona automaticamente l’asse Y di una visualizzazione per rendere potenzialmente più leggibile il grafico.

Un’opzione consente all’intervallo di attendibilità di ridimensionare il grafico. Fai clic sull’icona Impostazioni (ingranaggio) e seleziona **[!UICONTROL Allow Anomaly Detection to Scale Y Axis]** (Consenti al rilevamento anomalie di ridimensionare l’asse Y).

![](assets/scale-y-axis.png)

