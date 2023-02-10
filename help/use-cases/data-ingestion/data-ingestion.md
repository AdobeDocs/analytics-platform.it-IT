---
title: Opzioni di acquisizione dati per Customer Journey Analytics
description: Scopri i diversi modi in cui è possibile acquisire i dati in Customer Journey Analytics
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 69356510596d047d80af63338fccca71e8af53cd
workflow-type: ht
source-wordcount: '783'
ht-degree: 100%

---

# Opzioni di acquisizione dati per Customer Journey Analytics

Esistono diverse opzioni per acquisire dati in Customer Journey Analytics. Alcune sono adatte per trasferire i dati della versione tradizionale di Adobe Analytics; altre per acquisire i dati direttamente da Adobe Experience Platform. Questo articolo descrive i passaggi di alto livello da seguire, con collegamenti verso informazioni più dettagliate.

## Acquisire dati dalla versione tradizionale di Adobe Analytics

Questo flusso di lavoro utilizza il connettore di origine di Adobe Analytics e varia a seconda che si utilizzi DTM o Launch per la gestione dei tag.

### Tramite tag in Adobe Experience Platform (precedentemente denominato [!UICONTROL Launch])

1. [Crea un livello dati](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=it), se non lo hai già fatto. Un livello dati è un framework di oggetti JavaScript sul sito che contiene tutti i valori delle variabili utilizzati nell’implementazione. Offre maggiore controllo ed è più facile da mantenere nell’implementazione.
1. Utilizza i [tag di Adobe Experience Platform](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=it) per implementare nel sito il codice per la raccolta dati, se non lo hai già fatto. Questa soluzione per la gestione dei tag consente di implementare il codice Analytics e altri requisiti di assegnazione tag. I tag permettono integrazioni con altre soluzioni e prodotti e consentono di implementare codice personalizzato. Tutte queste attività possono essere eseguite senza dover ricorrere a un team di sviluppatori nell’organizzazione per aggiornare il codice sul sito.
1. Crea un [connettore di origine Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) in Adobe Experience Platform. Il connettore di origine inserirà i dati di Analytics in Experience Platform in un framework standardizzato denominato [sistema Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it). Consulta la sezione [Utilizzo dei dati della suite di rapporti di Adobe Analytics in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
1. Utilizza [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=it) per creare una o più connessioni e visualizzazioni dati necessarie per il reporting tra canali diversi.

## Inserire dati tramite SDK per Web di Adobe Experience Platform e la rete Edge

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it) è una libreria JavaScript lato client che consente ai clienti di Adobe Experience Cloud di interagire con i vari servizi Experience Cloud tramite la rete Edge di Adobe Experience Platform.

1. [Configura l’estensione AEP Web SDK nei tag](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=it) per inviare i dati ad Adobe Experience Cloud dalle proprietà web tramite la rete Edge di Adobe Experience Platform.
1. Utilizza [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=it) per creare una o più [connessioni](/help/connections/create-connection.md) e [visualizzazioni dati](/help/data-views/data-views.md) necessarie per il reporting tra canali diversi.

## Acquisire dati in modalità batch e in streaming

Adobe Experience Platform riunisce dati provenienti da più origini per aiutare gli esperti di marketing a comprendere meglio il comportamento dei loro clienti. L’acquisizione dei dati di Adobe Experience Platform comprende sia i diversi metodi utilizzati da Platform per acquisire i dati da tali sorgenti, sia il modo in cui i dati vengono memorizzati nel data lake per poter essere utilizzati dai servizi Platform a valle.

### Acquisizione batch

1. Configura l’[acquisizione batch](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=it#batch) per acquisire i dati in Adobe Experience Platform come file di batch. È possibile acquisire dati di profilo di un semplice file in un sistema CRM (ad esempio un file parquet) oppure dati conformi a uno schema noto nel registro Experience Data Model (XDM).
1. Utilizza [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=it) per creare una o più [connessioni](/help/connections/create-connection.md) e [visualizzazioni dati](/help/data-views/data-views.md) necessarie per il reporting tra canali diversi.

### Acquisizione in streaming

1. Imposta l’[acquisizione in streaming](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=it#streaming) per inviare in tempo reale i dati da dispositivi lato client e lato server a Experience Platform.
1. Utilizza [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=it) per creare una o più [connessioni](/help/connections/create-connection.md) e [visualizzazioni dati](/help/data-views/data-views.md) necessarie per il reporting tra canali diversi.

## Acquisire dati Google Analytics da analizzare in Customer Journey Analytics

Segui i passaggi dettagliati descritti in questo tutorial su come [analizzare i dati Google Analytics utilizzando Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial-v22/module12/ex5.html?lang=it).

## Utilizza Bulk Data Insertion API per inserire i dati in Analytics, quindi effettua l’acquisizione tramite Adobe Source Connector in Experience Platform.

1. [Utilizza Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) per inviare dati di raccolta lato server ad Adobe Analytics. È possibile inviare file in formato CSV contenenti dati di eventi.
1. [Crea un connettore di origine Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) per inserire i dati dei consumatori in Adobe Experience Platform.
1. Utilizza [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=it) per creare una o più [connessioni](/help/connections/create-connection.md) e [visualizzazioni dati](/help/data-views/data-views.md) necessarie per il reporting tra canali diversi.
