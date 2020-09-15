---
title: Opzioni di assimilazione dei dati per il Customer Journey Analytics
description: Comprendere i diversi modi in cui è possibile inserire i dati nel Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 4ea06ca1f13255c570ccc9f69cb328d57bf975b2
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 3%

---


# Opzioni di assimilazione dei dati per il Customer Journey Analytics

Sono disponibili diverse opzioni per l’assimilazione dei dati nel Customer Journey Analytics. Alcuni di essi presuppongono che si desideri spostare  dati Adobe Analytics tradizionali, alcuni dei quali presuppongono l&#39;acquisizione di dati direttamente da Adobe Experience Platform. Questo riferimento fornisce passaggi di alto livello da seguire, con collegamenti a informazioni più dettagliate.

## Acquisire dati da Adobe Analytics  tradizionale

Questo flusso di lavoro utilizza il Connettore dati Adobe Analytics  e varia a seconda che tu utilizzi DTM o Launch come Gestione tag.

### Tramite Dynamic Tag Management (DTM)

1. [Creare un livello dati](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), se non lo avete già fatto. Un livello dati è un framework di oggetti JavaScript presenti sul sito che contiene tutti i valori variabili utilizzati nell&#39;implementazione. Consente un maggiore controllo e una manutenzione più semplice nell&#39;implementazione.
1. Use [DTM](https://docs.adobe.com/content/help/en/analytics/implementation/other/dtm/dtm-implementation-overview.html) per implementare il codice sul sito per la raccolta dei dati, se non lo avete già fatto. Gestione tag dinamica fornisce un singolo livello di dati che invia i dati da più origini.
1. Creare un [ connettore sorgente Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) in Adobe Experience Platform. Questo connettore di origine trasferirà i dati di Analytics  Experience Platform in un framework standard denominato [Sistema XDM (Experience Data Model)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Use [Customer Journey Analytics](https://docs.adobe.com/content/help/it-IT/analytics-platform/using/cja-overview/cja-getting-started.html) per creare una o più connessioni e viste dati che informino i rapporti tra canali.

### Tramite Launch

1. [Creare un livello dati](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), se non lo avete già fatto. Un livello dati è un framework di oggetti JavaScript presenti sul sito che contiene tutti i valori variabili utilizzati nell&#39;implementazione. Consente un maggiore controllo e una manutenzione più semplice nell&#39;implementazione.
1. Use [ Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/analytics/implementation/launch/overview.html) per implementare il codice sul sito per la raccolta dei dati, se non lo avete già fatto. Launch è una soluzione di gestione tag che consente di distribuire il codice Analytics insieme ad altri requisiti di tag. Launch offre integrazioni con altre soluzioni e prodotti e consente di distribuire codice personalizzato. Tutte queste attività possono essere eseguite senza affidarsi ad alcun team di sviluppo dell&#39;organizzazione per aggiornare il codice sul sito.
1. Creare un [ connettore sorgente Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) in Adobe Experience Platform. Questo connettore di origine trasferirà i dati di Analytics  Experience Platform in un framework standard denominato [Sistema XDM (Experience Data Model)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Use [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) per creare una o più connessioni e viste dati che informino i rapporti tra canali.
