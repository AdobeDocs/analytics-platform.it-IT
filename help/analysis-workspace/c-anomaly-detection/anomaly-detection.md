---
description: Scopri il rilevamento delle anomalie nei dati in Analysis Workspace.
title: Panoramica sul rilevamento di anomalie
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
source-git-commit: e07b901f66a59aba1a7a517443eec73387d23c57
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 29%

---

# Panoramica sul rilevamento di anomalie

In Analysis Workspace è possibile visualizzare e analizzare le anomalie nei dati in modo contestuale.

[Esercitazione video sul rilevamento delle anomalie](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=it) (4:53)

Il rilevamento anomalie fornisce un metodo statistico per determinare il cambiamento di una data metrica in relazione ai dati precedenti.

Il rilevamento delle anomalie consente di separare i &quot;segnali effettivi&quot; dal &quot;rumore&quot; e quindi di identificare i fattori potenziali che hanno contribuito a tali segnali o anomalie. In altre parole, consente di identificare quali fluttuazioni statistiche hanno un impatto significativo e quali no. Puoi quindi identificare la causa principale di una vera anomalia. Inoltre, è possibile ottenere previsioni di metriche affidabili (KPI).

Di seguito sono riportati alcuni esempi di anomalie che è possibile analizzare:

* Cali drastici nel valore medio dell’ordine
* Picchi negli ordini con ricavi bassi
* Picchi o cadute nelle registrazioni di prova
* Cadute nelle visualizzazioni della pagina di destinazione
* Picchi negli eventi del buffer video
* Picchi di bit rate video ridotti

L’algoritmo di rilevazione delle anomalie di Analysis Workspace include:

* Supporto per granularità oraria, settimanale e mensile, oltre alla granularità giornaliera esistente.
* Consapevolezza della stagionalità (come il &quot;Black Friday&quot;) e delle festività.
