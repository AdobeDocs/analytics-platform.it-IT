---
title: Analisi Percorso cross-channel
description: Analizza ed estrai informazioni dalle interazioni dei clienti lungo l’intero percorso del cliente.
source-git-commit: a6c6620a4f4118755509e534d7d6a12bf08b4b67
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 5%

---


# Analisi Percorso cross-channel

Avere un’unica vista consolidata del comportamento dei clienti tra vari canali unificando i dati provenienti da varie proprietà web, mobili e offline. Ad esempio, puoi utilizzare questa vista consolidata per analizzare le interazioni dei clienti su computer desktop e dispositivi mobili per comprendere il comportamento dei clienti ed estrarre informazioni per ottimizzare le esperienze dei clienti digitali. Puoi anche analizzare le interazioni dei clienti tra i diversi canali, compresi i canali digitali e offline, come le interazioni di supporto e gli acquisti in-store per comprendere e ottimizzare meglio il percorso dei clienti.

## Architettura

![Architettura cross channel](assets/cross-channel-architecture.svg)

## Passaggi di implementazione

1. [Creare ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it) schemi per l’acquisizione dei dati.
1. [Crea ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html) set di dati per i dati da acquisire.
1. [Inserire dati in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html).
1. Utilizza un ID comune dello spazio dei nomi nei set di dati o utilizza [Cross-Channel Analytics](/help/connections/cca/overview.md) per collegare le persone. Al momento, Customer Journey Analytics non utilizza i servizi Profilo o Identità di Experience Platform per l’unione.
1. Esegui qualsiasi preparazione di dati personalizzati per garantire una chiave comune tra i set di dati delle serie temporali da acquisire nel Customer Journey Analytics.
1. Attribuisci ai dati di ricerca un ID primario che possa unirsi a un campo nei dati dell’evento. Conta come righe nella licenza.
1. Imposta lo stesso ID principale per i dati di profilo come ID principale dei dati dell’evento.
1. Configura una connessione dati per l’acquisizione di dati da Experience Platform a Customer Journey Analytics.
1. [Crea una ](/help/data-views/create-dataview.md) visualizzazione dati sulla connessione per selezionare le dimensioni e le metriche specifiche da includere nella visualizzazione. Le impostazioni di attribuzione e allocazione sono configurate anche nella visualizzazione dati. Queste impostazioni vengono calcolate al momento del rapporto.
1. Crea un progetto per configurare dashboard e rapporti in Analysis Workspace.

## Considerazioni

Quando stabilisci questo flusso di lavoro, assicurati di prendere in considerazione i seguenti punti.

* L&#39;analisi dei dati tra canali richiede lo stesso namespace ID su ogni record.
* Il processo di unione di diversi set di dati richiede una chiave primaria comune per la persona/entità nei set di dati.
* Le unioni basate su chiave secondarie non sono attualmente supportate.
* Il processo di unione delle identità basato sui campi consente di reinserire le identità nelle righe in base ai record ID transitori successivi, ad esempio un ID di autenticazione. Ciò consente di risolvere record diversi a un singolo ID per l&#39;analisi a livello di persona anziché a livello di dispositivo o cookie.
* Gli oggetti e gli attributi dello stesso campo XDM si uniscono in una dimensione del Customer Journey Analytics. Per unire più attributi da diversi set di dati alla stessa dimensione di Customer Journey Analytics, i set di dati devono fare riferimento allo stesso campo o schema XDM.
