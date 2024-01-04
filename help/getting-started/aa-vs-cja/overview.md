---
title: Confronto con Adobe Analytics
description: Panoramica del confronto tra Customer Journey Analytics e Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 1%

---

# Confronto con Adobe Analytics

Questa sezione della documentazione spiega come confrontare e comprendere le differenze tra Adobe Customer Journey Analytics e Adobe Analytics.

La differenza fondamentale tra le due soluzioni è l’ampiezza dei dati che puoi (puoi) considerare durante la creazione dei rapporti e dell’analisi.

In Customer Journey Analytics, *qualsiasi* l’origine dati può far parte dei dati utilizzati per la generazione di rapporti e analisi. Adobe Analytics si rivolge principalmente ai dati online raccolti da siti web e app mobili. Adobe Analytics offre funzionalità per importare dati da altre origini, ma lo scopo principale è quello di fornire più contesto per i dati online precedentemente menzionati.

## Raccolta dati

Il Customer Journey Analytics si basa sui dati memorizzati nei set di dati di Adobe Experience Platform. In Experienci Platform sono disponibili diverse opzioni per raccogliere e acquisire dati da questi set di dati. Queste opzioni sono descritte più dettagliatamente nella [Panoramica sull’acquisizione dei dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=en).

Adobe Analytics raccoglie infine i dati all’interno della soluzione stessa. Anche in questo caso, sono disponibili diverse opzioni per la raccolta di tali dati, descritte più dettagliatamente nella [Guida all’implementazione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=it).

Puoi utilizzare i dati della suite di rapporti di Adobe Analytics nel Customer Journey Analytics utilizzando [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it). Questo connettore acquisisce in Experienci Platform i dati raccolti in Adobe Analytics. Puoi quindi creare una connessione a questo set di dati in Customer Journey Analytics. Consulta [Utilizzare i dati della suite di rapporti di Adobe Analytics nel Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=it) per ulteriori informazioni.


## Elaborazione dati

Prima di poter creare rapporti sui dati, spesso devi elaborarli per garantire che possano essere utilizzati correttamente per il reporting. L’elaborazione dei dati può avvenire al momento della raccolta dei dati e al momento della generazione del rapporto.

In generale, Customer Journey Analytics è progettato per funzionare con i dati raccolti e memorizzati nel set di dati Experienci Platform al momento del reporting. Customer Journey Analytics offre potenti funzionalità di elaborazione al momento del reporting per garantire che i dati siano pronti per il reporting e l’analisi. Se devi mappare, trasformare e convalidare i dati prima che vengano acquisiti in Experienci Platform, puoi utilizzare [Preparazione dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) funzionalità di Experienci Platform.

In Adobe Analytics, la maggior parte dell’elaborazione dei dati avviene immediatamente dopo la raccolta dei dati.

Consulta [Confrontare l’elaborazione dei dati in Adobe Analytics e Customer Journey Analytics](data-processing-comparisons.md) e [Regole di elaborazione, VISTA e classificazioni rispetto alla preparazione dati](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=it) per ulteriori informazioni.


## Terminologia

Customer Journey Analytics offre flessibilità su come definire dimensioni e metriche, grazie alla flessibilità offerta dagli schemi basati su Experience Data Model (XDM) sottostanti. Ad esempio, se Adobe Analytics utilizza visitatori, visite e hit, il Customer Journey Analytics utilizza persone, sessioni ed eventi come concetti equivalenti (puoi modificare la denominazione nel modo che ritieni più appropriato).

Consulta [Confrontare la terminologia per i dati di Analytics trasmessi tramite il connettore di origine di Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=en) per ulteriori informazioni sulle differenze terminologiche.


## Ambienti di reporting e sandbox virtuali

Adobe Analytics ha il concetto di suite di rapporti virtuali, che ti consente di segmentare i dati raccolti e di controllare l’accesso a tali dati segmentati.

Il Customer Journey Analytics ha un concetto simile, chiamato visualizzazioni dati. Le visualizzazioni dati sono contenitori che consentono di determinare come interpretare i dati di una connessione. Offrono la massima flessibilità per specificare e configurare dimensioni e metriche in preparazione alle attività di reporting e analisi.

Experienci Platform offre sandbox che possono essere considerate come un contenitore in cui sono memorizzati dati e applicazioni per un dato ambiente. La funzionalità di una sandbox non è correlata a una suite di rapporti virtuali di Adobe Analytics o a una visualizzazione dati del Customer Journey Analytics. Adobe Analytics stessa non ha alcuna dipendenza o relazione con le sandbox Experienci Platform. Il Customer Journey Analytics supporta le sandbox di Experience Platform, ma vi sono alcune considerazioni importanti.

Consulta [Suite di rapporti virtuali, visualizzazioni dati, sandbox Adobe Experience Platform e il connettore di origine Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=it) per ulteriori informazioni.


## Identità

Il Customer Journey Analytics supporta le identità definite come parte degli schemi ai quali si conformano i set di dati contenenti i dati. Di conseguenza, le identità sono un concetto fondamentale di Experience Platform, che il Customer Journey Analytics utilizza durante la configurazione di un [connessione](../../connections/overview.md) (definendo l’ID persona per ciascun set di dati) e quando si applica [unione](../../stitching/overview.md) per l&#39;analisi cross-channel. Un’identità importante utilizzata dagli SDK e dall’API Experienci Platform è l’ID Experience Cloud (ECID).

Adobe Analytics utilizza un set di campi di identità più definitivo, come l’Adobe Analytics ID (AAID). Quando si utilizza il connettore di origine di Analytics, a questi campi di identificazione di Adobe Analytics viene riservato un trattamento speciale. Consulta [AAID, ECID, AACUSTOMID e il connettore di origine di Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) per ulteriori informazioni.


## Funzioni supportate

Una panoramica delle funzioni di Adobe Analytics e del modo in cui sono supportate dal Customer Journey Analytics è disponibile sul sito [Supporto delle funzioni del Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=en).
