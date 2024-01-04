---
title: Analisi del percorso cross-channel
description: Analizza ed estrai informazioni dalle interazioni dei clienti lungo l’intero percorso del cliente.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases, Cross-Channel Analysis
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 61%

---

# Analisi cross-channel

L’analisi cross-channel consente un’unica visualizzazione consolidata del comportamento dei clienti su vari canali, unificando i dati da varie proprietà web, mobili e offline. Ad esempio, puoi utilizzare questa vista consolidata per analizzare le interazioni dei clienti su computer desktop e dispositivi mobili per comprendere il comportamento dei clienti ed estrarre informazioni per ottimizzare le esperienze dei clienti digitali. Puoi anche analizzare le interazioni dei clienti tra i diversi canali, compresi i canali digitali e offline, come le interazioni di supporto e gli acquisti in-store per comprendere e ottimizzare meglio il percorso del cliente.

## Passaggi di implementazione

![Flusso dei passaggi di implementazione come descritto in questa sezione.](../assets/cca-architecture.png)

1. [Creare schemi](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it) per i dati da inserire.
1. [Creare set di dati](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=it) per i dati da inserire.
1. [Acquisire dati in Experienci Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=it):
   1. Dati basati su eventi ![evento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg) dal sito web o dall’app mobile tramite il connettore di origine Edge Network o Analytics.
   2. Dati profilo ![profilo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg) (ad esempio da un sistema di gestione delle relazioni con i clienti, un’applicazione del call center o un’applicazione fedeltà).
   3. Ricercare dati ![ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) (ad esempio nome del prodotto, categoria da un sistema di informazioni sul prodotto).

1. Utilizza un ID con uno spazio dei nomi comune nei diversi set di dati. Utilizzare [Stitching](../../stitching/overview.md) per elevare qualsiasi set di dati basato su eventi ![aggiornamento dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg) per fornire l’ID comune su ogni riga. Al momento, Customer Journey Analytics non utilizza i servizi Profile o Identity di Experience Platform per l’unione.
1. Esegui qualsiasi preparazione dei dati personalizzati per garantire una chiave comune tra i set di dati delle serie temporali da inserire in Customer Journey Analytics.
1. Attribuisci ai dati di ricerca un ID primario che possa unirsi a un campo nei dati dell’evento. Conta come righe nella licenza.
1. Imposta lo stesso ID primario per i dati di profilo come ID primario dei dati dell’evento.
1. [Creare una connessione](../../connections/overview.md) acquisire i set di dati rilevanti da Experienci Platform a Customer Journey Analytics.
1. [Crea una visualizzazione dati](/help/data-views/create-dataview.md) sulla connessione per selezionare le dimensioni e le metriche specifiche da includere nella visualizzazione. Le impostazioni di attribuzione e allocazione sono configurate anche nella visualizzazione dati. Queste impostazioni vengono calcolate al momento del rapporto.
1. [Creare un progetto](/help/analysis-workspace/home.md) per configurare dashboard e rapporti in Analysis Workspace.

## Considerazioni

Quando stabilisci questo flusso di lavoro, assicurati di prendere in considerazione i seguenti punti.

* L’analisi dei dati tra canali diversi richiede lo stesso ID dello spazio dei nomi su ogni record.
* Il processo di unione di diversi set di dati richiede una chiave primaria comune per la persona/entità nei set di dati.
* Le unioni basate su chiavi secondarie non sono supportate al momento.
* Il processo di unione consente di reimpostare le identità nelle righe in base a informazioni di ID transitorie (come un ID di autenticazione) da record che condividono lo stesso ID persistente. Questo consente di risolvere diversi record in un singolo ID unito per l’analisi a livello di persona, anziché a livello di dispositivo o cookie.
* Gli oggetti e gli attributi dello stesso campo XDM si uniscono in una dimensione in Customer Journey Analytics. Per unire più attributi da diversi set di dati nella stessa dimensione di Customer Journey Analytics, i set di dati devono fare riferimento allo stesso campo o schema XDM.

