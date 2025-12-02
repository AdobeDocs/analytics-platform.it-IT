---
description: Scopri i metodi disponibili per l’esportazione da Analysis Workspace.
keywords: Analysis Workspace
title: Come esportare i dati del progetto
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 100%

---

# Panoramica sull’esportazione

Puoi esportare i progetti di Customer Journey Analytics (o una parte di essi) da Analysis Workspace. Puoi avere necessità di esportare i rapporti di Customer Journey Analytics per diversi motivi, ad esempio per utilizzarli in strumenti di terze parti o combinarli con dati esterni.

Nelle sezioni seguenti vengono descritti i tipi di file supportati, i vari metodi disponibili per l’esportazione e i vantaggi di ciascun metodo.

## Tipi di file supportati

Puoi esportare i rapporti di Customer Journey Analytics come file PDF, CSV o JSON.

* **PDF:** offre un modo semplice per condividere dati visivi con gli stakeholder. Il PDF tutte le tabelle e visualizzazioni mostrate (visibili) nel progetto.

* **CSV:** consente di visualizzare dati non elaborati in un’applicazione per fogli di calcolo, ad esempio Excel. I file CSV contengono dati in formato testo normale.

* **JSON:** fornisce un formato di file di standard aperto per la condivisione dei dati.

## Metodi di esportazione

Sono disponibili diversi metodi per l’esportazione da Analysis Workspace. Quando scegli un metodo di esportazione, valuta cosa desideri esportare e chi dovrà accedervi.

| Metodo di esportazione | Utilizza questo metodo per: |
|---------|----------|
| [Download sulla tua workstation](/help/analysis-workspace/export/download-send.md) | <li>Scaricare i progetti sulla tua workstation personale.</li><li>Scaricare solo dati ad hoc (senza pianificazione).</li> <li>Scaricare un massimo di 50.000 righe.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Invio ad altri utenti](/help/analysis-workspace/export/t-schedule-report.md) | <li>Inviare via e-mail ad altri utenti dell’organizzazione i dati Customer Journey Analytics esportati.</li><li>Inviare l’e-mail ad hoc o con pianificazione.</li> <li>Includere un massimo di 50.000 righe nell’e-mail.</li> <!--true?--> |
| [Esportare in una posizione cloud](/help/analysis-workspace/export/export-cloud.md) | <li>Esportare in una posizione cloud, ad esempio <ul><li>Adobe Experience Platform Data Landing Zone</li><li>Google Cloud Platform</li><li>Microsoft Azure</li><li>Amazon S3</li><li>Snowflake</li></ul></li><li>Esportare dati ad hoc o con pianificazione.</li><li>Memorizzare quantità maggiori di dati Customer Journey Analytics.</li><li>Esportare tabelle complete contenenti migliaia o milioni di righe.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
