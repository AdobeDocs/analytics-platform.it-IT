---
description: Scopri come utilizzare i feed di dati per estrarre dati non elaborati da Customer Journey Analytics. Scopri i prerequisiti per l’utilizzo dei feed di dati e cosa fare dopo.
keywords: clickstream;feed dati;datafeed;feed dati
title: Panoramica sui feed dati di Analytics
feature: Components
hide: true
hidefromtoc: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
source-git-commit: 50b82943d4c59f612240ffc8d83a8a08f09b8331
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 29%

---

# Panoramica sui feed dati

I feed di dati sono un modo potente per estrarre dati non elaborati da Customer Journey Analytics. Puoi utilizzare i dati non elaborati in altre piattaforme al di fuori di Adobe, in base alle esigenze della tua organizzazione. I dati vengono consegnati in batch orari alla conclusione di ogni ora oppure in batch giornalieri alla conclusione di ogni giorno.

## Prerequisiti

Prima di utilizzare i feed di dati, è necessario soddisfare tutti i seguenti requisiti.

* Un’implementazione funzionante con i dati acquisiti in Adobe Customer Journey Analytics. <!-- For more information, see Data ingestion overview - add link -->
* Il tuo account è un amministratore di prodotto Analytics oppure appartiene a un profilo di prodotto con accesso ai feed di dati. <!--???-->
* Un bucket configurato su Amazon S3, Google Cloud Platform, Azure RBAC o Azure SAS.<!--Which cloud providers do we support??-->
* (Legacy: Obbligatorio solo per i tipi di destinazione FTP e SFTP legacy) Disponi di un sito FTP e di credenziali a portata di mano (credenziali FTP fornite dalla tua organizzazione.)<!--Delete???-->

## Confrontare i feed di dati in Customer Journey Analytics e Adobe Analytics

La funzionalità del feed dati in Customer Journey Analytics è diversa da quella di Adobe Analytics. Per ulteriori informazioni, vedere [Confrontare feed di dati in Customer Journey Analytics e Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).


## Passaggi successivi

Le risorse seguenti sono utili per comprendere il flusso di lavoro di base per ottenere dei feed di dati. Una volta compreso il flusso di lavoro di base, puoi lavorare con i team della tua organizzazione per archiviare o acquisire dati non elaborati in un database.

* Best practice per i feed dati<!--add link-->: best practice per la creazione e la gestione dei feed dati.
* Creare un feed di dati<!--add link-->: dettagli tecnici per la creazione di un feed di dati, con informazioni più dettagliate sui singoli campi
* Gestisci feed dati<!--add link-->: ulteriori informazioni sulla navigazione nell&#39;interfaccia del feed dati
* Contenuto feed dati <!--add link-->: informazioni sul contenuto del file compresso
* Definizioni delle colonne dati <!--add link-->: elenco completo di tutte le colonne disponibili.

<!-- Is this still the output users can download from the destination? I aske Jun. -->

>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Naviga nell&#39;interfaccia feed dati](https://video.tv.adobe.com/v/25452?quality=12&learn=on){target="_blank"} per vedere un video dimostrativo.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Trova il tuo ID feed dati](https://video.tv.adobe.com/v/335747?quality=12&learn=on){target="_blank"} per vedere un video dimostrativo.

>[!ENDSHADEBOX]
