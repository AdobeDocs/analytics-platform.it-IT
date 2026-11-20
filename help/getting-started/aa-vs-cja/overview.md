---
title: Confronto con Adobe Analytics
description: Panoramica del confronto tra Customer Journey Analytics e Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
autotag-review: '2026-05-19T09:13:47.721Z'
TQID: 'https://experienceleague.adobe.com/MU9ywSyInHtsdzqvxO3yxTSY5bcDvdhnTUkhAgDHmZ4'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1f480cda20e0b2d54dd42b909bfa8bf8a2bc0c95
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 52%
---
# Confronto con Adobe Analytics

Questa sezione della documentazione spiega come confrontare e comprendere le differenze tra Adobe Customer Journey Analytics e Adobe Analytics.

La differenza fondamentale tra le due soluzioni è l’ampiezza dei dati che puoi considerare durante la creazione dei rapporti e analisi.

In Customer Journey Analytics, *qualsiasi* origine dati può far parte dei dati utilizzati per il reporting e le analisi. Adobe Analytics si rivolge principalmente ai dati online raccolti da siti web e app mobili. Adobe Analytics offre funzionalità per importare dati da altre origini, ma lo scopo principale di questa funzionalità è quello di fornire più contesto per i dati online precedentemente menzionati.

## Raccolta dati

Customer Journey Analytics si basa sui dati memorizzati nei set di dati di Adobe Experience Platform. In Experience Platform sono disponibili diverse opzioni per raccogliere e acquisire dati da questi set di dati. Queste opzioni sono descritte in dettaglio nella [Panoramica sull&#39;acquisizione dei dati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/data-ingestion).

Adobe Analytics raccoglie infine i dati all’interno della soluzione stessa. Anche in questo caso, sono disponibili diverse opzioni per raccogliere tali dati, descritte in dettaglio nella [Guida all&#39;implementazione di Adobe Analytics](https://experienceleague.adobe.com/it/docs/analytics/implementation/home).

Puoi utilizzare i dati della suite di rapporti di Adobe Analytics in Customer Journey Analytics utilizzando il [connettore di origine di Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). Questo connettore acquisisce in Experience Platform i dati raccolti in Adobe Analytics. Puoi quindi creare una connessione a questo set di dati in Customer Journey Analytics. Per ulteriori informazioni, consulta [Utilizzo dei dati della suite di rapporti di Adobe Analytics in Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja).

I dati nella suite di rapporti di Adobe Analytics sono indipendenti da quelli memorizzati nei set di dati di Adobe Experience Platform che costituiscono la connessione Customer Journey Analytics. Di conseguenza, Adobe consiglia di valutare i dati in ogni piattaforma separatamente, anziché aspettarsi che entrambe le piattaforme riflettano gli stessi valori.

## Elaborazione dei dati

Prima di poter generare rapporti sui dati, questi vanno spesso elaborati per garantire che possano essere utilizzati correttamente per il reporting. L’elaborazione dei dati può avvenire al momento della raccolta dei dati e del reporting.

In generale, Customer Journey Analytics è progettato per funzionare con i dati raccolti e memorizzati nei set di dati di Experience Platform al momento del reporting. Customer Journey Analytics offre potenti funzionalità di elaborazione al momento del rapporto per garantire che i dati siano pronti per il reporting e l’analisi. [I campi derivati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/derived-fields) e le [impostazioni dei componenti](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/component-settings/overview) possono essere modificati e applicati retroattivamente ai dati storici. Se devi mappare, trasformare e convalidare i dati prima che vengano acquisiti in Experience Platform, puoi utilizzare la funzionalità [Preparazione dati](https://experienceleague.adobe.com/it/docs/experience-platform/data-prep/home) di Experience Platform.

In Adobe Analytics, la maggior parte dell’elaborazione dei dati avviene immediatamente dopo la raccolta dei dati. Le regole del canale di marketing, le regole di elaborazione, la persistenza di eVar e altre logiche di post-elaborazione vengono applicate in questo momento e sono permanenti nella suite di rapporti. Le modifiche apportate a una di queste configurazioni influiscono solo sui nuovi dati in arrivo da quel momento in poi.

Per ulteriori informazioni consulta [Confrontare l’elaborazione dei dati tra Adobe Analytics e Customer Journey Analytics](data-processing-comparisons.md) e [Regole di elaborazione, VISTA e classificazioni rispetto alla preparazione dati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep).


## Terminologia

Customer Journey Analytics offre flessibilità su come definire dimensioni e metriche, grazie alla versatilità fornita dagli schemi basati su Experience Data Model (XDM) sottostanti. Ad esempio, se Adobe Analytics utilizza visitatori, visite e hit, Customer Journey Analytics utilizza persone, sessioni ed eventi (puoi modificare la denominazione nel modo che ritieni più appropriato).

Per ulteriori informazioni sulle differenze terminologiche consulta [Confrontare la terminologia per i dati di Analytics trasmessi tramite il connettore di origine di Analytics](https://experienceleague.adobe.com/it/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology).


## Ambienti virtuali di reporting e sandbox

Adobe Analytics ha il concetto di suite di rapporti virtuali, che consente di segmentare i dati raccolti e di controllare l’accesso a tali dati segmentati.

Customer Journey Analytics ha un concetto simile, chiamato visualizzazioni dati. Le visualizzazioni dati sono contenitori che consentono di determinare come interpretare i dati da una connessione. Offrono la massima flessibilità per specificare e configurare dimensioni e metriche in preparazione per il reporting e l’analisi.

Experience Platform offre sandbox che funzionano come contenitore contenente dati e applicazioni per un dato ambiente. La funzionalità di una sandbox non è correlata a una suite di rapporti virtuali di Adobe Analytics o a una visualizzazione dati di Customer Journey Analytics. Adobe Analytics stessa non ha alcuna dipendenza o relazione con le sandbox di Experience Platform. Customer Journey Analytics supporta le sandbox di Experience Platform, ma vi sono alcune considerazioni importanti.

Per ulteriori informazioni, consulta [Suite di rapporti virtuali, visualizzazioni dati, sandbox di Adobe Experience Platform e connettore di origine di Analytics](https://experienceleague.adobe.com/it/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc).


## Identità

Customer Journey Analytics supporta le identità definite come parte degli schemi ai quali si conformano i set di dati contenenti i dati. Di conseguenza, le identità sono un concetto fondamentale di Experience Platform, che Customer Journey Analytics utilizza durante la configurazione di una [connessione](../../connections/overview.md) (definendo l’ID persona per ciascun set di dati) e durante l’applicazione dell’[unione](../../stitching/overview.md) per l’analisi cross-channel. Un’identità importante utilizzata dagli SDK e dall’API di Experience Platform è l’ECID.

Adobe Analytics utilizza un set di campi di identità più definitivo, come Adobe Analytics ID (AAID). Quando si utilizza il connettore di origine di Analytics, a questi campi di identità di Adobe Analytics viene riservato un trattamento speciale. Per ulteriori informazioni consulta [AAID, ECID, AACUSTOMID e il connettore di origine di Analytics](https://experienceleague.adobe.com/it/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc).


## Dimensioni a cardinalità elevata

Customer Journey Analytics memorizza valori di dimensione interi e non esiste alcun limite al numero di valori univoci che una dimensione può includere. Al contrario, Adobe Analytics utilizza hash a 32 bit per mappare i valori delle dimensioni al fine di ottimizzare il reporting e l’archiviazione. Questo comportamento può causare [conflitti di hash](https://experienceleague.adobe.com/it/docs/analytics/implementation/validate/hash-collisions) nel reporting. Adobe Analytics inserisce anche i valori nella riga [Low-Traffic](https://experienceleague.adobe.com/it/docs/analytics/technotes/low-traffic) una volta raggiunta la soglia di limite univoco. I segmenti che utilizzano queste dimensioni possono mostrare discrepanze tra i rapporti di Adobe Analytics e di Customer Journey Analytics.

## Funzioni supportate

Puoi trovare una panoramica delle funzionalità di Adobe Analytics e del modo in cui Customer Journey Analytics le supporta all&#39;indirizzo [Customer Journey Analytics feature support](https://experienceleague.adobe.com/it/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa).
