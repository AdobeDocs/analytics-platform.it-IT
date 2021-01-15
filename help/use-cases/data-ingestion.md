---
title: Opzioni di assimilazione dei dati per il Customer Journey Analytics
description: Comprendere i diversi modi in cui è possibile inserire i dati nel Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 8a3a868ff4e2fbbcdf83ff7769382c6a92f78ec2
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 6%

---


# Opzioni di assimilazione dei dati per il Customer Journey Analytics

Sono disponibili diverse opzioni per l’assimilazione dei dati nel Customer Journey Analytics. Alcuni di essi presuppongono che si desideri spostare  dati Adobe Analytics tradizionali, alcuni dei quali presuppongono l&#39;acquisizione di dati direttamente da Adobe Experience Platform. Questo riferimento fornisce passaggi di alto livello da seguire, con collegamenti a informazioni più dettagliate.

## Acquisire dati da Adobe Analytics  tradizionale

Questo flusso di lavoro utilizza il Connettore dati Adobe Analytics  e varia a seconda che tu utilizzi DTM o Launch come Gestione tag.

### Tramite Dynamic Tag Management (DTM)

1. [Crea un livello](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html) dati, se non lo hai già fatto. Un livello dati è un framework di oggetti JavaScript presenti sul sito che contiene tutti i valori variabili utilizzati nell&#39;implementazione. Consente un maggiore controllo e una manutenzione più semplice nell&#39;implementazione.
1. Utilizza [DTM](https://docs.adobe.com/content/help/en/analytics/implementation/other/dtm/dtm-implementation-overview.html) per implementare il codice sul tuo sito per la raccolta dei dati, se non lo hai già fatto. Gestione tag dinamica fornisce un singolo livello di dati che invia i dati da più origini.
1. Creare un [ connettore sorgente Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) in Adobe Experience Platform. Questo connettore di origine trasferirà i dati di Analytics  Experience Platform in un framework standard denominato [Experience Data Model (XDM) System](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Utilizzate [Customer Journey Analytics](https://docs.adobe.com/content/help/it-IT/analytics-platform/using/cja-overview/cja-getting-started.html) per creare una o più connessioni e viste dati che informino il reporting tra canali.

### Tramite Launch

1. [Crea un livello](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html) dati, se non lo hai già fatto. Un livello dati è un framework di oggetti JavaScript presenti sul sito che contiene tutti i valori variabili utilizzati nell&#39;implementazione. Consente un maggiore controllo e una manutenzione più semplice nell&#39;implementazione.
1. Utilizzate [ Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/analytics/implementation/launch/overview.html) per implementare il codice sul sito per la raccolta dei dati, se non lo avete già fatto. Launch è una soluzione di gestione tag che consente di distribuire il codice Analytics insieme ad altri requisiti di tag. Launch offre integrazioni con altre soluzioni e prodotti e consente di distribuire codice personalizzato. Tutte queste attività possono essere eseguite senza affidarsi ad alcun team di sviluppo dell&#39;organizzazione per aggiornare il codice sul sito.
1. Creare un [ connettore sorgente Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) in Adobe Experience Platform. Questo connettore di origine trasferirà i dati di Analytics  Experience Platform in un framework standard denominato [Experience Data Model (XDM) System](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Utilizzate [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) per creare una o più connessioni e viste dati che informino il reporting tra canali.

## Inviare i dati tramite Adobe Experience Platform Web SDK e Edge Network

[Adobe Experience Platform Web ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) SDKè una libreria JavaScript lato client che consente ai clienti di Adobe Experience Cloud di interagire con i vari servizi nel Experience Cloud di  attraverso Adobe Experience Platform Edge Network.

1. [Configura l’estensione AEP Web SDK in ](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension) Launchal per inviare dati all’Adobe Experience Cloud dalle proprietà Web, tramite Adobe Experience Platform Edge Network.
1. Utilizzate [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) per creare una o più connessioni e viste dati che informino il reporting tra canali.

## Caricamento dei dati con caricamento batch e caricamento in streaming

Adobe Experience Platform riunisce i dati provenienti da più origini per aiutare gli addetti al marketing a comprendere meglio il comportamento dei loro clienti. Adobe Experience Platform Data Ingestion rappresenta i diversi metodi mediante i quali la piattaforma acquisisce i dati da queste origini, nonché il modo in cui tali dati vengono memorizzati all&#39;interno del Data Lake per essere utilizzati dai servizi della piattaforma a valle.

### Caricamento batch

1. Configurate [Batch Ingestion](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en#batch) per poter trasferire i dati in Adobe Experience Platform come file batch. I dati che si desidera acquisire possono essere i dati di profilo provenienti da un file semplice in un sistema CRM (ad esempio un file parquet), o i dati conformi a uno schema noto nel Registro di sistema di Experience Data Model (XDM).
1. Utilizzate [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) per creare una o più connessioni e viste dati che informino il reporting tra canali.

### Caricamento in streaming

1. Configurate [Streaming assimilation](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en#streaming) per inviare i dati dai dispositivi client e server al Experience Platform  in tempo reale.
1. Utilizzate [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) per creare una o più connessioni e viste dati che informino il reporting tra canali.

## Inserimento di dati di Google Analytics da analizzare nel Customer Journey Analytics

Per informazioni dettagliate, consulta questa esercitazione su come [Analizzare i dati delle Google Analytics utilizzando l&#39;Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=en#objectives).

## Utilizzate l&#39;API di inserimento dati di massa per inserire dati in Analytics, quindi caricate tramite  connettore origine Adobe in  Experience Platform

1. [Utilizzate ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) API di inserimento dati di massa per inviare dati di raccolta lato server a  Adobe Analytics. Consente di inviare file in formato CSV contenenti i dati dell’evento.
1. [Create un ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) connettore di origine Adobe Analytics  per inserire i dati di consumo in Adobe Experience Platform.
1. Utilizzate [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) per creare una o più connessioni e viste dati che informino il reporting tra canali.