---
title: Configurare Streaming Media Collection per Customer Journey Analytics
description: Scopri come impostare Streaming Media Collection per Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 68ce73ddf805ec377fdb2c539683507f191c9249
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# Configurare Streaming Media Collection per Customer Journey Analytics {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Configurare e implementare Media Edge"
>abstract="Puoi configurare Adobe Streaming Media Collection in modo da utilizzare Experience Platform Edge per rendere i dati disponibili in Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

I passaggi per implementare Streaming Media Collection in Customer Journey Analytics variano a seconda dell’implementazione corrente di Streaming Media Collection in Adobe Analytics.

Streaming Media Collection può essere implementato in Adobe Analytics in uno dei seguenti modi:

* [Implementazioni di Edge Network per Streaming Media Collection](#edge-network-implementations)

+++ Visualizza infografica

  ![Implementazione di Streaming Media su Edge](assets/streaming-media-edge.png)

+++

* [Implementazioni solo per Adobe Analytics per Streaming Media Collection](#adobe-analytics-only-implementations)

+++ Visualizza infografica

  ![Implementazione solo Analytics](assets/analytics-implementation.png)

+++

Per ulteriori informazioni sulle differenze tra questi metodi di implementazione, vedere [Implementare Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) nella Guida alla raccolta di contenuti multimediali in streaming.

## Implementazioni di Edge Network per Streaming Media Collection

Se la raccolta di file multimediali in streaming è [implementata utilizzando Edge Network nell&#39;implementazione di Adobe Analytics](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods), significa che alcuni passaggi necessari per aggiornare la raccolta di file multimediali in streaming a Customer Journey Analytics sono già stati completati come parte dell&#39;implementazione di Adobe Analytics. Di seguito sono riportati i passaggi completati:

* [Configura lo schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Crea un set di dati in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Configurare uno stream di dati in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

I seguenti passaggi aggiuntivi devono essere completati come parte dell’aggiornamento a Customer Journey Analytics:

>[!NOTE]
>
>Quando completi i passaggi di aggiornamento di Customer Journey Analytics, assicurati di utilizzare lo schema, il set di dati e lo stream di dati dall’implementazione di Streaming Media Collection in Adobe Analytics.

* [Creare una connessione in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Creare una visualizzazione dati in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Implementazioni solo per Adobe Analytics per Streaming Media Collection

Se la raccolta multimediale in streaming è [implementata utilizzando un&#39;implementazione solo Adobe Analytics nell&#39;ambiente Adobe Analytics](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), significa che i dati di Streaming Media non verranno ancora inviati ad Edge Network.

Quando crei lo schema, il set di dati, lo stream di dati, la connessione e la visualizzazione dati come parte dell’aggiornamento da Adobe Analytics a Customer Journey Analytics, effettua le seguenti selezioni per tenere conto dei dati di Streaming Media Collection:

* Durante la creazione dello schema per Customer Journey Analytics, includere il gruppo di campi `MediaAnalytics Interaction Details`.

  Per ulteriori informazioni sull&#39;aggiunta di questo gruppo di campi, vedere [Configurare lo schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) nella Guida alla raccolta di contenuti multimediali in streaming.

  Per informazioni sulla creazione dello schema, vedere [Creare uno schema personalizzato da utilizzare con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* Durante la configurazione dello stream di dati per Customer Journey Analytics, abilita Media Analytics.

  Per ulteriori informazioni sull&#39;abilitazione di questa opzione, vedere [Configurare uno stream di dati in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) nella Guida alla raccolta di contenuti multimediali in streaming.

  Per informazioni sulla creazione dello stream di dati, vedere [Creare uno stream di dati da utilizzare con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* Durante la creazione di una visualizzazione dati per Customer Journey Analytics, includi i campi di schema richiesti per Streaming Media Collection.

  Assicurati di mappare questi campi schema ai valori corretti nell’oggetto XDM.

  Per ulteriori informazioni sui campi obbligatori, vedere [Creare una visualizzazione dati in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) nella Guida di Streaming Media Collection.

  Per informazioni sulla creazione della visualizzazione dati, vedere [Creare una visualizzazione dati in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).


