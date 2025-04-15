---
title: Configurare Streaming Media Collection per Customer Journey Analytics
description: Scopri come impostare Streaming Media Collection per Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b807099d-a61d-48f9-9fec-94ecc6b76213
source-git-commit: 380ed5c9ee0c21ea9855a41728afec040637ce65
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 6%

---

# Configurare Streaming Media Collection per Customer Journey Analytics {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Configurare e implementare i file multimediali Edge"
>abstract="Se prevedi di utilizzare Streaming Media Collection con Customer Journey Analytics, devi effettuare selezioni specifiche in determinati passaggi del processo di aggiornamento. Ad esempio, devi aggiungere il gruppo di campi Dettagli interazioni di Media Analytics allo schema, abilitare Media Analytics nello stream di dati e altro ancora."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Come in Adobe Analytics, Streaming Media Collection può essere utilizzato per raccogliere dati multimediali in streaming da utilizzare in Customer Journey Analytics. Se utilizzi Streaming Media Collection con Adobe Analytics, devi includerlo nei piani di aggiornamento a Customer Journey Analytics.

Durante i passaggi per l’aggiornamento da Adobe Analytics a Customer Journey Analytics, effettua le seguenti selezioni per tenere conto dei dati di Streaming Media Collection:

* Durante la creazione dello schema per Customer Journey Analytics, includere il gruppo di campi `MediaAnalytics Interaction Details`.

  Per ulteriori informazioni sull&#39;aggiunta di questo gruppo di campi, vedere [Configurare lo schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) nella Guida alla raccolta di contenuti multimediali in streaming.

  Per informazioni sulla creazione dello schema, vedere [Creare uno schema personalizzato da utilizzare con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* Durante la configurazione dello stream di dati per Customer Journey Analytics, abilita Media Analytics.

  Per ulteriori informazioni sull&#39;abilitazione di questa opzione, vedere [Configurare uno stream di dati in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) nella Guida alla raccolta di contenuti multimediali in streaming.

  Per informazioni sulla creazione dello stream di dati, vedere [Creare uno stream di dati da utilizzare con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

  >[!NOTE]
  >
  >Se la tua implementazione di Adobe Analytics utilizza già Experience Platform Web SDK, questo passaggio non è necessario.

* Durante la creazione di una visualizzazione dati per Customer Journey Analytics, includi i campi di schema richiesti per Streaming Media Collection.

  Accertati di mappare questi campi schema ai valori corretti nell’oggetto XDM.

  Per ulteriori informazioni sui campi obbligatori, vedere [Creare una visualizzazione dati in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) nella Guida di Streaming Media Collection.

  Per informazioni sulla creazione della visualizzazione dati, vedere [Creare una visualizzazione dati in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

<!--

------------------

The steps for implementing the Streaming Media Collection in Customer Journey Analytics differ depending on your current Streaming Media Collection implementation in Adobe Analytics. 

Streaming Media Collection can be implemented in Adobe Analytics in either of the following ways:

* [Edge Network implementations for the Streaming Media Collection](#edge-network-implementations)

* [Adobe Analytics-only implementations for the Streaming Media Collection](#adobe-analytics-only-implementations)

For more information about the differences between these implementation methods, see [Implement the Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) in the Streaming Media Collection Guide.

## Edge Network implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using the Edge Network in your Adobe Analytics implementation](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods), this means that some steps that are required to upgrade the Streaming Media Collection to Customer Journey Analytics have already been completed as part of your Adobe Analytics implementation. Following are the completed steps:

* [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Create a dataset in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

The following additional steps need to be completed as part of the upgrade to Customer Journey Analytics:

>[!NOTE]
>
>As you complete the Customer Journey Analytics upgrade steps, make sure you use the schema, dataset, and datastream from your Streaming Media Collection implementation in Adobe Analytics.

* [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Adobe Analytics-only implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using an Adobe Analytics-only implementation in your Adobe Analytics environment](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), this means that Streaming Media data is not yet going to Edge Network. 

As you create the schema, dataset, datastream, connection, and data view as part of your upgrade from Adobe Analytics to Customer Journey Analytics, make the following selections to account for Streaming Media Collection data:

* When creating the schema for Customer Journey Analytics, include the `MediaAnalytics Interaction Details` field group.

  For more information about adding this field group, see [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the schema, see [Create a custom schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* When configuring the datastream for Customer Journey Analytics, enable Media Analytics. 

  For more information about enabling this option, see [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the datastream, see [Create a datastream to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* When creating a data view for Customer Journey Analytics, include the required schema fields for the Streaming Media Collection.

  Make sure you map these schema fieldds to the correct values in the XDM object.

  For more information about the required fields, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) in the Streaming Media Collection Guide.

  For information about creating the data view, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

  -->
