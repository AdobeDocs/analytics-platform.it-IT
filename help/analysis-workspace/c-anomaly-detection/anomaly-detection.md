---
description: Scopri il rilevamento delle anomalie nei dati in Analysis Workspace.
title: Panoramica di Rilevamento delle anomalie
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
source-git-commit: e07b901f66a59aba1a7a517443eec73387d23c57
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 96%

---

# Panoramica sul rilevamento delle anomalie

In Analysis Workspace è possibile visualizzare e analizzare le anomalie nei dati in modo contestuale.

[Tutorial video sul rilevamento delle anomalie](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=it) (4:53)

Il rilevamento anomalie fornisce un metodo statistico per determinare il cambiamento di una data metrica in relazione ai dati precedenti.

Consente di separare i “segnali effettivi” da quelli di “disturbo” e quindi di individuare i potenziali fattori che hanno contribuito al verificarsi di tali segnali o anomalie. In altre parole, permette di individuare le fluttuazioni statistiche rilevanti da quelle che non lo sono, e quindi di arrivare alla causa di fondo di una anomalia effettiva. Inoltre, è possibile ottenere previsioni di metriche affidabili (KPI).

Ecco alcuni esempi di anomalie da esaminare:

* Drastico calo nel valore medio degli ordini
* Picchi negli ordini con fatturato basso
* Picchi o calo nelle registrazioni di prova
* Calo nelle visualizzazioni della pagina di destinazione
* Picchi negli eventi di buffering video
* Picchi nei valori più bassi di bitrate video

L’algoritmo di rilevazione delle anomalie di Analysis Workspace include:

* Supporto per la granularità oraria, settimanale e mensile, oltre a quella giornaliera già supportata
* Supporto per la stagionalità (ad esempio “Black Friday”) e le festività
