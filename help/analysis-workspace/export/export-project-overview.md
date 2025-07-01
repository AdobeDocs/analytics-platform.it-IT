---
description: Scopri i metodi disponibili per l’esportazione da Analysis Workspace.
keywords: Analysis Workspace
title: Come esportare i dati del progetto
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: 70daf2251576bc3b473e63b3bb7c48f2d16dbffe
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 55%

---

# Panoramica sull’esportazione

Puoi esportare (parte di) progetti Customer Journey Analytics da Analysis Workspace. Potrebbe essere utile esportare i rapporti di Customer Journey Analytics per una serie di motivi, ad esempio per utilizzarli in strumenti di terze parti o combinarli con dati esterni.

Nelle sezioni seguenti vengono descritti i tipi di file supportati, i vari metodi disponibili per l’esportazione e i vantaggi di ciascun metodo.

## Tipi di file supportati

Puoi esportare i rapporti di Customer Journey Analytics come file PDF, CSV o JSON.

* **PDF:** offre un modo semplice per condividere dati visivi con gli stakeholder. Il PDF tutte le tabelle e visualizzazioni mostrate (visibili) nel progetto.

* **CSV:** consente di visualizzare dati non elaborati in un’applicazione per fogli di calcolo, ad esempio Excel. I file CSV contengono dati in formato testo normale.

* **JSON:** fornisce un formato di file di standard aperto per la condivisione dei dati.

## Metodi di esportazione

Esistono diversi metodi per esportare da Analysis Workspace. Quando scegli un metodo di esportazione, considera cosa desideri esportare e chi deve accedervi.

| Metodo di esportazione | Utilizza questo metodo se desideri... |
|---------|----------|
| [Download sulla tua workstation](/help/analysis-workspace/export/download-send.md) | <li>Scaricare i progetti sulla tua workstation personale.</li><li>Scarica solo dati ad hoc (non pianificato).</li> <li>Scarica un massimo di 50.000 righe.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Invio ad altri utenti](/help/analysis-workspace/curate-share/t-schedule-report.md) | <li>Inviare via e-mail ad altri utenti dell’organizzazione i dati Customer Journey Analytics esportati.</li><li>Invia l’e-mail ad hoc o secondo una pianificazione.</li> <li>Includi un massimo di 50.000 righe nell’e-mail.</li> <!--true?--> |
| [Esporta in un&#39;applicazione cloud](/help/analysis-workspace/export/export-cloud.md) | <li>Esporta in una posizione cloud, ad esempio <ul><li>Zona di destinazione dei dati di Adobe Experience Platform</li><li>Google Cloud Platform</li><li>Microsoft Azure</li><li>Amazon S3</li><li>Snowflake</li></ul></li><li>Esporta dati ad hoc o secondo una pianificazione.</li><li>Memorizzare quantità maggiori di dati Customer Journey Analytics.</li><li>Esportare tabelle complete contenenti migliaia o milioni di righe.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
