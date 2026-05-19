---
description: Scopri i metodi disponibili per l’esportazione da Analysis Workspace.
keywords: Analysis Workspace
title: Come esportare i dati del progetto
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
autotag-review: '2026-05-19T08:26:15.356Z'
TQID: 'https://experienceleague.adobe.com/9pyrzsluOss-Dz4yrDJAmVqxjjeiEYTNILIz4llAMPA'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 96%

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
| [Download sulla tua workstation](/help/analysis-workspace/export/download-send.md) | <li>Scaricare i progetti sulla tua workstation personale.</li><li>Scaricare solo dati ad hoc (senza pianificazione).</li> <li>Scaricare un massimo di 50.000 righe.</li> <!--true? Are there 2 different options to download to your workstation? is this emailing it? --> |
| [Invio ad altri utenti](/help/analysis-workspace/export/t-schedule-report.md) | <li>Inviare via e-mail ad altri utenti dell’organizzazione i dati Customer Journey Analytics esportati.</li><li>Inviare l’e-mail ad hoc o con pianificazione.</li> <li>Includi un massimo di 400 righe nell’e-mail.</li> <!--true?--> |
| [Esportare in una posizione cloud](/help/analysis-workspace/export/export-cloud.md) | <li>Esportare in una posizione cloud, ad esempio <ul><li>Zona di destinazione dei dati di Adobe Experience Platform</li><li>Google Cloud Platform</li><li>Microsoft Azure</li><li>Amazon S3</li><li>Snowflake</li></ul></li><li>Esportare dati ad hoc o con pianificazione.</li><li>Memorizzare quantità maggiori di dati Customer Journey Analytics.</li><li>Esportare tabelle complete contenenti migliaia o milioni di righe.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
