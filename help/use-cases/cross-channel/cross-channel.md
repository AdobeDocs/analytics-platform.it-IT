---
title: Analisi del percorso cross-channel
description: Analizza ed estrai informazioni dalle interazioni dei clienti lungo l’intero percorso del cliente.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases, Cross-Channel Analysis
role: User
source-git-commit: 5e80e68c6b5d3dca19dae21c6719b040b28afaf9
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 68%

---

# Analisi cross-channel {#cross-channel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-additional-datasets"
>title="Aggiungere altri set di dati alla connessione"
>abstract="Dopo aver aggiunto dati a un set di dati in Adobe Experience Platform, puoi aggiungere il set di dati alla tua connessione in Customer Journey Analytics. Se aggiungi dati da altri canali, assicurati che siano conformi allo schema utilizzato dalla tua organizzazione.<br><br>Ogni set di dati aggiunto richiede un’ingente mole di lavoro, in particolare per verificare che per ogni evento esista un identificatore univoco e per assicurarsi che la struttura generale dei dati sia conforme allo schema personalizzato dell’organizzazione. La definizione di questo flusso di lavoro può richiedere il coordinamento di più team all’interno dell’organizzazione per un periodo di alcuni mesi."

<!-- markdownlint-enable MD034 -->

Cross-channel analysis enables a single consolidated view of customer behavior across various channels by unifying data from various web, mobile, and offline properties. Ad esempio, puoi utilizzare questa vista consolidata per analizzare le interazioni dei clienti su computer desktop e dispositivi mobili per comprendere il comportamento dei clienti ed estrarre informazioni per ottimizzare le esperienze dei clienti digitali. Puoi anche analizzare le interazioni dei clienti tra i diversi canali, compresi i canali digitali e offline, come le interazioni di supporto e gli acquisti in-store per comprendere e ottimizzare meglio il percorso del cliente.

## Passaggi di implementazione

![Flow of implementation steps as described in this section.](../assets/cca-architecture.png)

1. [Creare schemi](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it) per i dati da inserire.
1. [Creare set di dati](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=it) per i dati da inserire.
1. [Ingest data into Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=it):
   1. Event-based data ![event](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg) from website or mobile app through the Edge Network or Analytics source connector.
   2. Profile data ![profile](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg) (for example from a CRM system, call center application, loyalty application).
   3. Lookup data ![lookup](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) (for example product name, category from a product information system).

1. Use a common namespace ID across datasets. Use [Stitching](../../stitching/overview.md) to elevate any event-based dataset ![data refresh](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg) in respect to providing the common ID on each row. Al momento, Customer Journey Analytics non utilizza i servizi Profile o Identity di Experience Platform per l’unione.
1. Esegui qualsiasi preparazione dei dati personalizzati per garantire una chiave comune tra i set di dati delle serie temporali da inserire in Customer Journey Analytics.
1. Attribuisci ai dati di ricerca un ID primario che possa unirsi a un campo nei dati dell’evento. Conta come righe nella licenza.
1. Imposta lo stesso ID primario per i dati di profilo come ID primario dei dati dell’evento.
1. [Create a connection](../../connections/overview.md) to ingest the relevant datasets from Experience Platform to Customer Journey Analytics.
1. [Crea una visualizzazione dati](/help/data-views/create-dataview.md) sulla connessione per selezionare le dimensioni e le metriche specifiche da includere nella visualizzazione. Le impostazioni di attribuzione e allocazione sono configurate anche nella visualizzazione dati. Queste impostazioni vengono calcolate al momento del rapporto.
1. [Create a project](/help/analysis-workspace/home.md) to configure dashboards and reports within Analysis Workspace.

## Considerazioni

Quando stabilisci questo flusso di lavoro, assicurati di prendere in considerazione i seguenti punti.

* L’analisi dei dati tra canali diversi richiede lo stesso ID dello spazio dei nomi su ogni record.
* Il processo di unione di diversi set di dati richiede una chiave primaria comune per la persona/entità nei set di dati.
* Le unioni basate su chiavi secondarie non sono supportate al momento.
* The stitching process allows for rekeying identities in rows based on transient ID (such as an authentication ID) info from records sharing same persistent ID.This allows for resolving disparate records to a single stitched ID for analysis at the person level, rather than at the device or cookie level.
* Gli oggetti e gli attributi dello stesso campo XDM si uniscono in una dimensione in Customer Journey Analytics. Per unire più attributi da diversi set di dati nella stessa dimensione di Customer Journey Analytics, i set di dati devono fare riferimento allo stesso campo o schema XDM.

