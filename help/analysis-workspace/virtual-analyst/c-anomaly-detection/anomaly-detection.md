---
description: In Analysis Workspace è possibile visualizzare e analizzare le anomalie nei dati in modo contestuale.
title: Panoramica di Rilevamento delle anomalie
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 96%

---


# Panoramica di Rilevamento delle anomalie

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

In Analysis Workspace è possibile visualizzare e analizzare le anomalie nei dati in modo contestuale.

[Rilevamento anomalie su YouTube](https://www.youtube.com/watch?v=krXyQCjXoeU&amp;index=63&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:53)

Il rilevamento anomalie fornisce un metodo statistico per determinare il cambiamento di una data metrica in relazione ai dati precedenti.

Consente di separare i “segnali effettivi” da quelli di “disturbo” e quindi di individuare i potenziali fattori che hanno contribuito al verificarsi di tali segnali o anomalie. In altre parole, permette di individuare le fluttuazioni statistiche rilevanti da quelle che non lo sono, e quindi di arrivare alla causa di fondo di una anomalia effettiva. Inoltre, è possibile ottenere previsioni di metriche affidabili (KPI).

Ecco alcuni esempi di anomalie da esaminare:

* Drastico calo nel valore medio degli ordini
* Picchi negli ordini con fatturato basso
* Picchi o calo nelle registrazioni di prova
* Calo nelle visualizzazioni della pagina di destinazione
* Picchi negli eventi di buffering video
* Picchi nei valori più bassi di bitrate video

[Rilevamento delle anomalie](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) e Analisi contributi sono flussi di lavoro principali in Analysis Workspace. Puoi eseguire Analisi contributi rispetto a qualsiasi anomalia giornaliera e incorporare il risultato nel progetto Analysis Workspace.

>[!IMPORTANT]
>
>Analisi contributi non ancora disponibile nel Customer Journey Analytics.

L’algoritmo di rilevazione delle anomalie di Analysis Workspace include:

* Supporto per la granularità oraria, settimanale e mensile, oltre a quella giornaliera già supportata
* Supporto per la stagionalità (ad esempio “Black Friday”) e le festività

## Disattivare il rilevamento delle anomalie

Per disattivare il rilevamento delle anomalie a livello di colonna, deseleziona **[!UICONTROL Anomalies]** (Anomalie) nelle impostazioni della colonna.

![](assets/turnoff_anomalies.png)
