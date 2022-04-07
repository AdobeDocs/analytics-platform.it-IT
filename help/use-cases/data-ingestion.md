---
title: Opzioni di inserimento dati per il Customer Journey Analytics
description: Comprendere i diversi modi in cui è possibile inserire i dati nel Customer Journey Analytics
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 570fb36de0ed81f001ed6115e73d1d4347f368ec
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 10%

---

# Opzioni di inserimento dati per il Customer Journey Analytics

Quando si tratta di acquisire dati in un Customer Journey Analytics, sono disponibili diverse opzioni. Alcuni di essi presuppongono che si desideri trasferire i dati tradizionali di Adobe Analytics, altri presuppongono che i dati vengano acquisiti direttamente da Adobe Experience Platform. Questo riferimento fornisce passaggi di alto livello da seguire, con collegamenti a informazioni più dettagliate.

## Acquisire dati da Adobe Analytics tradizionale

Questo flusso di lavoro utilizza Adobe Analytics Data Connector e varia a seconda che utilizzi DTM o Launch come Tag Manager.

### Tramite tag in Adobe Experience Platform (precedentemente denominato [!UICONTROL Launch])

1. [Creare un livello dati](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html), se non lo hai già fatto. Un livello dati è un framework di oggetti JavaScript sul sito che contiene tutti i valori variabili utilizzati nell&#39;implementazione. Consente un maggiore controllo e una manutenzione più semplice nell’implementazione.
1. Utilizzo [Tag Adobe Experience Platform](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html) per implementare il codice sul sito per la raccolta dati, se non lo hai già fatto. Questa soluzione di gestione dei tag consente di distribuire il codice Analytics insieme ad altri requisiti di assegnazione tag. I tag offrono integrazioni con altre soluzioni e prodotti e consentono di distribuire codice personalizzato. Tutte queste attività possono essere eseguite senza affidarsi ad alcun team di sviluppo dell’organizzazione per aggiornare il codice sul sito.
1. Crea un [Connettore sorgente Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) in Adobe Experience Platform. Questo connettore di origine acquisirà i dati di Analytics in Experience Platform in un framework standardizzato denominato [Sistema Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it).
1. Utilizzo [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=it) per creare una o più connessioni e visualizzazioni dati che informino il reporting tra canali.

## Inserire dati tramite Adobe Experience Platform Web SDK e Edge Network

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it) è una libreria JavaScript lato client che consente ai clienti di Adobe Experience Cloud di interagire con i vari servizi dell’Experience Cloud tramite Adobe Experience Platform Edge Network.

1. [Configurare l’estensione AEP Web SDK nei tag](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=en) per inviare dati a Adobe Experience Cloud dalle proprietà web tramite Adobe Experience Platform Edge Network.
1. Utilizzo [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) per crearne uno o più [connessioni](/help/connections/create-connection.md) e [visualizzazioni dati](/help/data-views/data-views.md) in modo da informare il reporting cross-channel.

## Acquisire dati con acquisizione batch e acquisizione in streaming

Adobe Experience Platform riunisce dati provenienti da più sorgenti per aiutare gli esperti di marketing a comprendere meglio il comportamento dei loro clienti. L’acquisizione dei dati di Adobe Experience Platform rappresenta i diversi metodi in base ai quali Platform acquisisce i dati da queste sorgenti, nonché il modo in cui tali dati vengono memorizzati all’interno del Data Lake e possono essere utilizzati dai servizi della piattaforma a valle.

### Acquisizione batch

1. Configurazione [Acquisizione batch](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en#batch) per consentire l’acquisizione di dati in Adobe Experience Platform come file batch. I dati da acquisire possono essere i dati di profilo di un file flat in un sistema CRM (ad esempio un file di parquet) o dati conformi a uno schema noto nel registro Experience Data Model (XDM).
1. Utilizzo [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) per crearne uno o più [connessioni](/help/connections/create-connection.md) e [visualizzazioni dati](/help/data-views/data-views.md) in modo da informare il reporting cross-channel.

### Acquisizione in streaming

1. Configurazione [Acquisizione in streaming](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en#streaming) inviare in tempo reale dati da dispositivi lato client e lato server ad Experience Platform.
1. Utilizzo [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) per crearne uno o più [connessioni](/help/connections/create-connection.md) e [visualizzazioni dati](/help/data-views/data-views.md) in modo da informare il reporting cross-channel.

## Dati Google Analytics da analizzare in Customer Journey Analytics

Rivedi questa esercitazione su come [Analizzare i dati delle Google Analytics utilizzando il Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=en#objectives) per i passaggi dettagliati.

## Utilizza l’API di inserimento dati in blocco per ottenere i dati in Analytics, quindi effettua l’acquisizione tramite connettore origine Adobe in Experience Platform

1. [Utilizza API di inserimento dati in blocco](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) per inviare dati di raccolta lato server ad Adobe Analytics. Ti consente di inviare file in formato CSV contenenti i dati dell’evento.
1. [Creare un connettore sorgente Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) per inserire questi dati dei consumatori in Adobe Experience Platform.
1. Utilizzo [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) per crearne uno o più [connessioni](/help/connections/create-connection.md) e [visualizzazioni dati](/help/data-views/data-views.md) in modo da informare il reporting cross-channel.
