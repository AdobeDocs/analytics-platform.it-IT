---
title: Importazione di canali di marketing in CJA tramite il connettore dati di Analytics
description: Utilizzate le impostazioni corrette del Connettore dati di Analytics per inserire le regole di elaborazione del canale di marketing in Adobe Experience Platform.
translation-type: tm+mt
source-git-commit: 26486c79f6d94db1aa795bf024f581cad74c25f6
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 5%

---


# Importazione di canali di marketing in CJA tramite il connettore dati di Analytics

Se l&#39;azienda utilizza il [Connettore dati di Analytics](https://docs.adobe.com/content/help/it-IT/experience-platform/sources/connectors/adobe-applications/analytics.html) per inserire i dati della suite di rapporti in CJA, puoi configurare una connessione in CJA per creare rapporti sulle dimensioni del canale di marketing.

## Prerequisiti

* I dati della suite di rapporti devono già essere importati in Adobe Experience Platform utilizzando il [Connettore dati di Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html).
* Le regole di elaborazione del canale di marketing devono già essere configurate. Consultate [Regole di elaborazione per canali di marketing](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-rules.html) nella guida tradizionale ai componenti di Analytics.

## Elementi dello schema del canale di marketing

Dopo aver utilizzato il Connettore dati di Analytics in una suite di rapporti desiderata, viene creato uno schema XDM. Questo schema contiene tutte le dimensioni e le metriche di Analytics come dati non elaborati. Questi dati non elaborati non contengono attribuzione o persistenza. Al contrario, ogni hit passa attraverso le regole di elaborazione dei canali di marketing e registra la prima regola che corrisponde. Quando si crea una visualizzazione dati in CJA è possibile specificare attribuzione e persistenza.

1. [Crea una ](/help/connections/create-connection.md) connessione che include un dataset basato sul Connettore dati di Analytics.
2. [Crea una ](/help/data-views/create-dataview.md) visualizzazione dati che include le dimensioni seguenti:
   * **`channel.typeAtSource`**: Equivalente alla dimensione  [del ](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) canale Marketing.
   * **`channel._id`**: Equivalente al dettaglio del canale  [Marketing](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. Dare a ogni dimensione il modello di attribuzione e la persistenza desiderati. Se vuoi avere sia la prima che l’ultima dimensione touch, trascina più volte nell’area dei componenti ogni dimensione del canale di marketing. Dare a ogni dimensione il modello di attribuzione e la persistenza desiderati.  Adobe consiglia inoltre di assegnare a ciascuna dimensione un nome visualizzato per facilitarne l’utilizzo in Workspace.
4. Creare la visualizzazione dati.

Le dimensioni del canale di marketing sono ora disponibili per  Analysis Workspace.

## Differenze di elaborazione e architettura

>[!IMPORTANT]
>
>Esistono diverse differenze fondamentali tra i dati della suite di rapporti e quelli della piattaforma.  Adobe consiglia vivamente di modificare le regole di elaborazione dei canali di marketing della suite di rapporti per facilitare la corretta raccolta dei dati in Piattaforma.


Poiché le dimensioni del primo e dell&#39;ultimo canale di tocco sono sostanzialmente le stesse con diversi modelli di attribuzione, è possibile ricreare dimensioni simili durante la [creazione di una visualizzazione dati](/help/data-views/create-dataview.md). Potete creare più dimensioni basate sullo stesso elemento dello schema, dando loro diversi modelli di attribuzione e persistenza.

## Differenze tra

