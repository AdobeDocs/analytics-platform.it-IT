---
description: Scopri i metodi disponibili per l’esportazione da Analysis Workspace.
keywords: Analysis Workspace
title: Come esportare i dati del progetto
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '304'
ht-degree: 100%

---

# Panoramica sull’esportazione

Puoi esportare i rapporti di Customer Journey Analytics da Analysis Workspace. Potrebbe essere utile esportare i rapporti di Customer Journey Analytics per diversi motivi, ad esempio per utilizzarli in strumenti di terze parti o combinarli con dati esterni.

Nelle sezioni seguenti vengono descritti i tipi di file supportati, i vari metodi disponibili per l’esportazione e i vantaggi di ciascun metodo.

## Tipi di file supportati

Puoi esportare i rapporti di Customer Journey Analytics come file PDF, CSV o JSON.

* **PDF:** offre un modo semplice per condividere dati visivi con gli stakeholder. Il PDF tutte le tabelle e visualizzazioni mostrate (visibili) nel progetto.

* **CSV:** consente di visualizzare dati non elaborati in un’applicazione per fogli di calcolo, ad esempio Excel. I file CSV contengono dati in formato testo normale.

* **JSON:** fornisce un formato di file di standard aperto per la condivisione dei dati.

## Metodi di esportazione

Sono disponibili diversi metodi per l’esportazione da Analysis Workspace. Quando scegli un metodo di esportazione, considera cosa desideri esportare e chi deve accedervi.

| Metodo di esportazione | Vantaggi |
|---------|----------|
| [Download sulla tua workstation](/help/analysis-workspace/export/download-send.md) | Utilizza questo metodo se desideri: <ul><li>Scaricare i progetti sulla tua workstation personale.</li><li>I download sono solo ad hoc (non possono essere pianificati).</li> <li>Viene scaricato un totale di 50.000 righe.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Invio ad altri utenti](/help/analysis-workspace/export/t-schedule-report.md) | Utilizza questo metodo se desideri: <ul><li>Inviare via e-mail ad altri utenti dell’organizzazione i dati Customer Journey Analytics esportati.</li><li>Può essere ad hoc o con pianificazione.</li> <li>Viene incluso un totale di 50.000 righe.</li> <!--true?--> |
| [Invio a un’applicazione cloud](/help/analysis-workspace/export/export-cloud.md) | Utilizza questo metodo se desideri: <ul><li>Esportare in una posizione condivisa, ad esempio Data Landing Zone di Adobe Experience Platform, Google Cloud Platform, Microsoft Azure, Amazon S3 o Snowflake.</li><li>Può essere ad hoc o con pianificazione.</li><li>Memorizzare quantità maggiori di dati Customer Journey Analytics.</li><li>Esportare tabelle complete contenenti migliaia o milioni di righe.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
