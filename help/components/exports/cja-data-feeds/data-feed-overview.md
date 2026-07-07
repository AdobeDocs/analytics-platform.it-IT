---
description: Scopri come utilizzare i feed di dati per estrarre dati non elaborati da Customer Journey Analytics. Scopri i prerequisiti per l’utilizzo dei feed di dati e cosa fare dopo.
keywords: clickstream;feed dati;datafeed;feed dati
title: Panoramica sui feed dati di Analytics
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 66a8a96da6710d20b01b9315fe87ba38c54c2511
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 14%

---

# Panoramica sui feed dati

{{release-limited-testing}}

I feed di dati sono un modo potente per estrarre dati non elaborati da Customer Journey Analytics. Puoi utilizzare questi dati non elaborati in altre piattaforme al di fuori di Adobe, a discrezione della tua organizzazione. I dati vengono consegnati in batch orari alla conclusione di ogni ora oppure in batch giornalieri alla conclusione di ogni giorno.

## Prerequisiti

Prima di utilizzare i feed di dati, è necessario soddisfare tutti i seguenti requisiti:

* Un&#39;implementazione funzionante con i dati acquisiti in Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->
* Il tuo account è un amministratore di prodotto Analytics oppure appartiene a un profilo di prodotto con accesso ai feed di dati <!--???-->
* Un bucket configurato su [!DNL Amazon S3], [!DNL Google Cloud Platform], [!DNL Azure RBAC] o [!DNL Azure SAS]

## Introduzione

Per iniziare a utilizzare i feed di dati in Customer Journey Analytics, è necessario innanzitutto comprendere le differenze tra i feed di dati in Customer Journey Analytics e i feed di dati in Adobe Analytics. Dopo aver compreso le differenze, puoi mappare i feed di dati di Adobe Analytics su Customer Journey Analytics, quindi iniziare a creare un feed di dati.

1. [Comprendere le differenze tra i feed di dati in Customer Journey Analytics e Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

1. [Mappatura delle colonne del feed dati di Adobe Analytics su Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

1. [Creare un feed di dati](/help/components/exports/cja-data-feeds/create-feed.md).

