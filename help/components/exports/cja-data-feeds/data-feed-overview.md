---
description: Scopri come utilizzare i feed di dati per estrarre dati non elaborati da Customer Journey Analytics. Scopri i prerequisiti per l’utilizzo dei feed di dati e cosa fare dopo.
keywords: clickstream;feed dati;datafeed;feed dati
title: Panoramica sui feed dati di Analytics
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
source-git-commit: 5e77857ca846767e3b9e7479baa4a4b18c6e3c8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 14%

---

# Panoramica sui feed dati

I feed di dati sono un modo potente per estrarre dati non elaborati da Customer Journey Analytics. Puoi utilizzare questi dati non elaborati in altre piattaforme al di fuori di Adobe, a discrezione della tua organizzazione. I dati vengono consegnati in batch orari alla conclusione di ogni ora oppure in batch giornalieri alla conclusione di ogni giorno.

## Prerequisiti

Prima di utilizzare i feed di dati, è necessario soddisfare tutti i seguenti requisiti:

* Un&#39;implementazione funzionante con i dati acquisiti in Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->
* Il tuo account è un amministratore di prodotto Analytics oppure appartiene a un profilo di prodotto con accesso ai feed di dati <!--???-->
* Un bucket configurato su {DNL Amazon S3}, {DNL Google Cloud Platform}, {DNL Azure RBAC} o {DNL Azure SAS}

## Introduzione

Per iniziare a utilizzare i feed di dati in Customer Journey Analytics, è necessario innanzitutto comprendere le differenze tra i feed di dati in Customer Journey Analytics e i feed di dati in Adobe Analytics. Dopo aver compreso le differenze, puoi mappare i feed di dati di Adobe Analytics su Customer Journey Analytics, quindi iniziare a creare un feed di dati.

1. [Comprendere le differenze tra i feed di dati in Customer Journey Analytics e Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

1. [Mappatura delle colonne del feed dati di Adobe Analytics su Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

1. [Creare un feed di dati](/help/components/exports/cja-data-feeds/create-feed.md).
