---
title: Panoramica sull’acquisizione di dati
description: Scopri i diversi modi in cui è possibile inserire i dati in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: ec56bc657961b2e4e8318ab14cd676288398462f
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 100%

---

# Panoramica sull’acquisizione di dati

Esistono diverse opzioni per acquisire dati in Customer Journey Analytics. Alcune presuppongono che si vogliano trasferire i dati tradizionali di Adobe Analytics, altre che si utilizzino i dati inseriti in Adobe Experience Platform.

>[!IMPORTANT]
>
>In tutti gli scenari, i dati che desideri _usare_ in Customer Journey Analytics vengono effettivamente _inseriti_ in Adobe Experience Platform.


L’architettura di alto livello di Customer Journey Analytics è mostrata qui:

![Architettura di Customer Journey Analytics](/help/getting-started/assets/cja-overview.svg)

Questa architettura illustra come Customer Journey Analytics consente di:

* Combinare più set di dati ![Dati](/help/assets/icons/Data.svg) in una [connessione](/help/connections/overview.md).
* Definire e configurare le dimensioni ![Dimensioni](/help/assets/icons/Dimensions.svg) e le metriche ![Evento](/help/assets/icons/Event.svg) in una [visualizzazione dati](/help/data-views/data-views.md), in base ai campi disponibili nei set di dati definiti nella connessione.
* Creare rapporti ![VisualizzaTabella](/help/assets/icons/ViewTable.svg) e visualizzazioni (come riga ![Riga](/help/assets/icons/GraphTrend.svg) e area ![Area](/help/assets/icons/GraphAreaStacked.svg)) nei [progetti](/help/analysis-workspace/home.md), in base alle dimensioni e alle metriche delle visualizzazioni dati.

I set di dati nell’architettura precedenti possono provenire da varie origini:

* dati batch,

* dati in streaming,

* dati provenienti da una distribuzione di Adobe Analytics corrente,

* dati provenienti dal tracciamento del sito web o dell’app per dispositivi mobili tramite Adobe Experience Platform Web/Mobile SDK,

* dati provenienti dal tracciamento di un’applicazione desktop, un gioco da console, un set top box o un dispositivo IoT utilizzando Adobe Experience Platform Edge Network Server API, oppure

* dati provenienti da un provider di dati di terze parti per il quale Adobe fornisce un connettore di origine.

È possibile avere molti set di dati come questi.

Questa sezione della documentazione offre guide introduttive per vari scenari.

## Priorità di acquisizione e latenza

Puoi acquisire i dati degli eventi in Customer Journey Analytics entro 90 minuti (SLT), indipendentemente dal fatto che i dati abbiano 24 o 48 ore, oppure 7 giorni.

Tieni presente che questa funzionalità varia in base al pacchetto SKU acquistato dalla tua azienda:

* Priorità di acquisizione di base: elaborazione SLT di dati di 24 ore entro 90 minuti (disponibile per **CJA Foundation** e **CJA Select**)

* Priorità di acquisizione intermedia: elaborazione SLT di dati di 72 ore entro 90 minuti (disponibile per **CJA Prime**)

* Priorità di acquisizione avanzata: elaborazione SLT di dati di 1 settimana entro 90 minuti (disponibile per **CJA Ultimate**)

## Inserire e usare i dati dalla versione tradizionale di Adobe Analytics

Immagina di aver già distribuito Adobe Analytics e di voler inserire questi dati in Adobe Experience Platform e utilizzarli, combinarli e analizzarli con dati di altri canali e origini dati in Customer Journey Analytics.

Per ulteriori informazioni, consulta la sezione [Inserire e usare i dati dalla versione tradizionale di Adobe Analytics](./analytics.md).


## Acquisire e utilizzare i dati tramite la rete Edge

### Utilizzo di Adobe Experience Platform Web SDK

In questo scenario, vuoi analizzare il tuo sito web con tecnologia Adobe, potenzialmente eseguendo la migrazione da un’altra soluzione o iniziando a monitorare il comportamento delle persone. Segui le best practice di Adobe per l’implementazione, che prevedono di utilizzare gli SDK di Adobe Experience Platform e la rete Edge, per inserire i dati. Puoi quindi utilizzare, combinare e analizzare i dati inseriti con i dati provenienti da altri canali e origini dati in Customer Journey Analytics.

Per ulteriori informazioni, consulta [Acquisire e utilizzare i dati tramite Adobe Experience Platform Web SDK](./aepwebsdk.md).

### Utilizzo di Adobe Experience Platform Mobile SDK

In questo scenario, vuoi analizzare la tua app mobile con tecnologia Adobe, potenzialmente eseguendo la migrazione da un’altra soluzione o iniziando a monitorare da zero il comportamento di una persona nell’app. Segui le best practice di Adobe per l’implementazione, che prevedono di utilizzare gli SDK di Adobe Experience Platform e la rete Edge, per inserire i dati. Puoi quindi utilizzare, combinare e analizzare i dati inseriti con i dati provenienti da altri canali e origini dati in Customer Journey Analytics.

Per ulteriori informazioni, consulta [Acquisire e utilizzare i dati tramite Adobe Experience Platform Mobile SDK](./aepmobilesdk.md).

### Utilizzo di Adobe Experience Platform Edge Network Server API

In questo scenario, vuoi analizzare un’applicazione desktop, un gioco su una console di giochi, l’utilizzo di un’applicazione di streaming video su un set top box o un dispositivo IoT con tecnologia Adobe. Potenzialmente vuoi migrare da un’altra soluzione o iniziare a monitorare da zero il comportamento di una persona su questi dispositivi. Segui le best practice di Adobe per l’implementazione, che prevedono di utilizzare le API server di Adobe Experience Platform Edge Network e la rete Edge, per acquisire i dati. Puoi quindi utilizzare, combinare e analizzare i dati inseriti con i dati provenienti da altri canali e origini dati in Customer Journey Analytics.

Per ulteriori informazioni, consulta [Acquisire e utilizzare i dati tramite Adobe Experience Platform Edge Network Server API](./serverapi.md).

## Inserire e utilizzare dati batch

Sono disponibili dati batch rilevanti che forniscono dettagli utili per comprendere meglio il comportamento dei clienti e analizzare le interazioni dei clienti. Esempi di tali dati batch sono file flat in formato CSV, JSON o Parquet provenienti da un sistema di gestione delle relazioni con i clienti, un’applicazione di fidelizzazione o un’altra soluzione per la quale attualmente Adobe non fornisce un connettore di origine. Questi dati batch inseriti in Adobe Experience Platform possono essere utilizzati, combinati e analizzati con dati provenienti da altri canali e origini dati in Customer Journey Analytics.

Per ulteriori informazioni, consulta la sezione [Inserire e utilizzare dati batch](./batch.md).

## Inserire e utilizzare i dati in streaming

Immagina di avere un’origine dati rilevante come un sistema di gestione delle relazioni con i clienti, un sistema ERP o qualsiasi altra origine che fornisce dettagli che possono aiutarti a comprendere meglio il comportamento dei clienti e ad analizzare le interazioni dei clienti. Tale origine dati è in grado di comunicare tramite l’infrastruttura di streaming cloud HTTP o pubblica, ma per la quale attualmente Adobe non fornisce un connettore sorgente. Questi dati in streaming inseriti in Adobe Experience Platform in tempo reale possono essere utilizzati, combinati e analizzati con dati provenienti da altri canali e origini dati in Customer Journey Analytics.

Per ulteriori informazioni, consulta la sezione [Inserire e utilizzare dati in streaming](./streaming.md).

## Inserire e utilizzare i dati utilizzando i connettori di origine

Immagina di avere a disposizione dei dati da un’origine supportata da un connettore di origine. I connettori di origine sono configurazioni configurabili che consentono di inserire dati da applicazioni di Adobe, prime e terze parti in Adobe Experience Platform. Per una panoramica dei connettori di origine disponibili, consulta la sezione [Panoramica dei connettori di origine](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=it). Utilizzando il connettore di origine è possibile inserire facilmente i dati provenienti dall’origine in Adobe Experience Platform e quindi utilizzarli, combinarli e analizzarli con i dati di altri canali e origini dati in Customer Journey Analytics.

Per ulteriori informazioni, consulta la sezione [Inserire e utilizzare i dati tramite i connettori di origine](./sources.md).

## Acquisire e utilizzare i dati ad hoc

Sono disponibili dati ad hoc che richiedono un solo set di dati in Experience Platform e non necessitano della configurazione di uno schema Experience Data Model (XDM). Questo scenario è denominato schema ad hoc. Gli schemi ad hoc vengono utilizzati in vari flussi di lavoro di acquisizione dati per Experience Platform, inclusa l’acquisizione di file CSV e la creazione di alcuni tipi di connessioni di origine.

Consulta [Acquisire e utilizzare dati ad hoc](./adhoc.md)

>[!MORELIKETHIS]
>
>Blog: [Informazioni più approfondite sull’elaborazione e l’acquisizione dei dati in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-closer-look-at-data-processing-amp-ingestion-in-adobe-customer/ba-p/665091)

