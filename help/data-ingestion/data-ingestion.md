---
title: Panoramica sull’inserimento di dati
description: Scopri i diversi modi in cui è possibile inserire i dati in Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 96%

---

# Panoramica sull’inserimento di dati

Esistono diverse opzioni per inserire dati in Customer Journey Analytics. Alcune presuppongono che si vogliano trasferire i dati tradizionali di Adobe Analytics, altre che si utilizzino i dati inseriti in Adobe Experience Platform.

>[!IMPORTANT]
>
>In tutti gli scenari, i dati che desideri _usare_ in Customer Journey Analytics vengono effettivamente _inseriti_ in Adobe Experience Platform.


Esamina l’architettura di Customer Journey Analytics di alto livello mostrata in precedenza nella sezione [Panoramica](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it):

![Customer Journey Analytics](./assets/cja-architecture.png)

Il set di dati nell’architettura di cui sopra può provenire da varie origini:

- dati batch,

- dati in streaming,

- dati provenienti da una distribuzione di Adobe Analytics corrente,

- dati provenienti dal tracciamento del sito Web/dell’app per dispositivi mobili tramite l’SDK per Web/dispositivi mobili di Adobe Experience Platform, oppure

- dati provenienti da un provider di dati di terze parti per il quale Adobe fornisce un connettore di origine.

È possibile avere molti set di dati come questi.

Questa sezione della documentazione offre guide introduttive per vari scenari.

## Inserire e usare i dati dalla versione tradizionale di Adobe Analytics

Immagina di aver già distribuito Adobe Analytics e di voler inserire questi dati in Adobe Experience Platform e utilizzarli, combinarli e analizzarli con dati di altri canali e origini dati in Customer Journey Analytics.

Per ulteriori informazioni, consulta la sezione [Inserire e usare i dati dalla versione tradizionale di Adobe Analytics](./analytics.md).

## Inserire e usare i dati tramite SDK per Web di Adobe Experience Platform e la rete Edge

Desideri analizzare il tuo sito web con tecnologia Adobe, migrare potenzialmente da un’altra soluzione o iniziare a monitorare il comportamento della persona. Segui le best practice di Adobe per l’implementazione, che prevedono di utilizzare gli SDK di Adobe Experience Platform e la rete Edge, per inserire i dati. Puoi quindi utilizzare, combinare e analizzare i dati inseriti con i dati provenienti da altri canali e origini dati in Customer Journey Analytics.

Per ulteriori informazioni, consulta la sezione [Inserire e usare i dati tramite SDK per Web di Adobe Experience Platform e la rete Edge](./aepwebsdk.md).

## Inserire e utilizzare dati batch

Sono disponibili dati batch rilevanti che forniscono dettagli utili per comprendere meglio il comportamento dei clienti e analizzare le interazioni dei clienti. Esempi di tali dati batch sono file flat in formato CSV, JSON o Parquet provenienti da un sistema di gestione delle relazioni con i clienti, un’applicazione di fidelizzazione o un’altra soluzione per la quale attualmente Adobe non fornisce un connettore di origine. Questi dati batch inseriti in Adobe Experience Platform possono essere utilizzati, combinati e analizzati con dati provenienti da altri canali e origini dati in Customer Journey Analytics.

Per ulteriori informazioni, consulta la sezione [Inserire e utilizzare dati batch](./batch.md).

## Inserire e utilizzare i dati in streaming

Immagina di avere un’origine dati rilevante come un sistema di gestione delle relazioni con i clienti, un sistema ERP o qualsiasi altra origine che fornisce dettagli che possono aiutarti a comprendere meglio il comportamento dei clienti e ad analizzare le interazioni dei clienti. Tale origine dati è in grado di comunicare tramite l’infrastruttura di streaming cloud HTTP o pubblica, ma per la quale attualmente Adobe non fornisce un connettore sorgente. Questi dati in streaming inseriti in Adobe Experience Platform in tempo reale possono essere utilizzati, combinati e analizzati con dati provenienti da altri canali e origini dati in Customer Journey Analytics.

Per ulteriori informazioni, consulta la sezione [Inserire e utilizzare dati in streaming](./streaming.md).

## Inserire e utilizzare i dati utilizzando i connettori di origine

Immagina di avere a disposizione dei dati da un’origine supportata da un connettore di origine. I connettori di origine sono configurazioni configurabili che consentono di inserire dati da applicazioni di Adobe, prime e terze parti in Adobe Experience Platform. Per una panoramica dei connettori di origine disponibili, consulta la sezione [Panoramica dei connettori di origine](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=it). Utilizzando il connettore di origine è possibile inserire facilmente i dati provenienti dall’origine in Adobe Experience Platform e quindi utilizzarli, combinarli e analizzarli con i dati di altri canali e origini dati in Customer Journey Analytics.

Per ulteriori informazioni, consulta la sezione [Inserire e utilizzare i dati tramite i connettori di origine](./sources.md).
