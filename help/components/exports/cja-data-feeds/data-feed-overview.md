---
description: Scopri come utilizzare i feed di dati per esportare dati non elaborati a livello di evento da Customer Journey Analytics, esaminare i prerequisiti e trovare gli articoli necessari per iniziare.
keywords: clickstream;feed dati;datafeed;feed dati
title: Panoramica dei feed dati di Customer Journey Analytics
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 34959e37a7040bcd861a506968895ad6f051b686
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 1%
---
# Panoramica sui feed dati

{{release-limited-testing}}

I feed di dati esportano dati grezzi a livello di evento da Customer Journey Analytics a una destinazione cloud. Puoi utilizzare questi dati in altre piattaforme al di fuori di Adobe, ad esempio in un data warehouse.

I feed di dati sono creati dai componenti di una visualizzazione dati. Ogni dimensione e metrica inclusa diventa una colonna nel feed dati e le impostazioni di visualizzazione dati, come persistenza, campi derivati e segmenti, vengono applicate ai dati. I file vengono consegnati in formato Parquet.

Puoi creare i seguenti tipi di feed dati:

* **Feed live**: esporta dati correnti e futuri su base oraria o giornaliera. Ogni consegna viene inviata dopo la fine dell’ora o del giorno e il ritardo di elaborazione è stato superato.

* **Feed di backfill**: esporta dati storici per un intervallo di date passato.

Per un confronto tra i feed di dati e altri metodi di esportazione di Customer Journey Analytics, ad esempio Esportazione tabella completa, vedere [Confronto tra i prodotti Analytics](/help/getting-started/analytics-product-comparison.md).

## Prerequisiti

Prima di utilizzare i feed di dati, è necessario soddisfare tutti i seguenti requisiti:

* I dati vengono acquisiti in Customer Journey Analytics e sono configurate una connessione e [visualizzazione dati](/help/data-views/create-dataview.md). <!-- For more information, see Data ingestion overview - add link -->

* Il tuo account è un amministratore di prodotto Customer Journey Analytics o appartiene a un profilo di prodotto con l&#39;autorizzazione [!UICONTROL **Feed dati**] (nella categoria [!UICONTROL **Strumenti visualizzazione dati**]) per la visualizzazione dati che desideri utilizzare. Per ulteriori informazioni, vedere [Controllo degli accessi](/help/technotes/access-control.md). <!--Add a Data Feeds row to the Data View Tools permissions table in access-control.md.-->

* Account e percorso di esportazione cloud configurati per [!DNL Amazon S3], [!DNL Google Cloud Platform], [!DNL Azure RBAC] o [!DNL Azure SAS]. Per ulteriori informazioni, vedere [Configurare gli account di esportazione cloud](/help/components/exports/cloud-export-accounts.md) e [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

>[!TIP]
>
>Poiché le modifiche ai componenti di una visualizzazione dati influiscono su ogni feed di dati che la utilizza, è consigliabile creare una visualizzazione dati utilizzata solo per i feed di dati.
>
>* **Vantaggio**: riduce il rischio che le modifiche apportate ai rapporti di Analysis Workspace cambino in modo imprevisto l&#39;output del feed dati.
>
>* **Svantaggio**: devi mantenere la visualizzazione dati aggiuntiva insieme alle altre visualizzazioni dati.

## Introduzione

Utilizza i seguenti articoli per pianificare, eseguire la migrazione e creare feed di dati.

### Pianificare i feed dati

* [Confrontare feed dati in Customer Journey Analytics e Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md): comprendere le differenze nelle funzioni e nei concetti se in precedenza si utilizzavano feed dati di Adobe Analytics.

* [Comprendere le discrepanze di dati tra i feed di dati e Analysis Workspace](/help/components/exports/cja-data-feeds/df-comparison-workspace.md): scopri perché l&#39;output del feed di dati potrebbe non corrispondere ai rapporti in Analysis Workspace.

* [Disponibilità dei componenti nei feed di dati](/help/components/exports/cja-data-feeds/df-components.md): scopri quali dimensioni e metriche sono necessarie, non supportate o soggette a restrizioni nei feed di dati.

### Migrazione dai feed dati di Adobe Analytics

1. [Preparare il mapping delle colonne del feed dati](/help/components/exports/cja-data-feeds/df-column-mapping-prep.md): comprendere i fattori che influiscono sul mapping delle colonne di Adobe Analytics a Customer Journey Analytics.

1. [Mappatura delle colonne del feed dati di Adobe Analytics su Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md): trova l&#39;equivalente Customer Journey Analytics di ogni colonna di Adobe Analytics che desideri mantenere.

### Creare e configurare feed di dati

* [Creare un feed di dati](/help/components/exports/cja-data-feeds/create-feed.md): scegliere i componenti, configurare la pianificazione e configurare la consegna.

* [Segmentazione nei feed dati](/help/components/exports/cja-data-feeds/df-segmentation.md): applica segmenti per filtrare i dati in un feed dati.

* [Applica trasformazioni dati](/help/components/exports/cja-data-feeds/df-data-transformations.md): trasforma i dati utilizzando le impostazioni del componente, i campi derivati o SQL.

* [Componenti evento secondario nei feed di dati](/help/components/exports/cja-data-feeds/df-sub-event.md): scopri come vengono esportati i componenti da array e mappe e come eseguirne le query.

