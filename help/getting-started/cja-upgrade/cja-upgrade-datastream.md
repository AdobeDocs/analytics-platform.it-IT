---
title: Creazione di uno schema per il Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 41965bcd5ae8252fbf2ceda0d2b633ec6dc0e9a3
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 22%

---

# Creare un flusso di dati da utilizzare con il Customer Journey Analytics

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), oppure puoi seguire i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un flusso di dati rappresenta la configurazione lato server quando si implementano gli SDK per Web e dispositivi mobili di Adobe Experience Platform. Durante la raccolta di dati con gli SDK di Adobe Experience Platform, i dati vengono inviati alla rete Edge di Adobe Experience Platform. È lo stream di dati che determina a quali servizi vengono inoltrati i dati.

Nella configurazione, vuoi configurare lo stream di dati per inviare i dati raccolti al set di dati in Adobe Experience Platform.

>[!NOTE]
>
>I passaggi seguenti sono necessari solo per le implementazioni di Adobe Analytics che utilizzano AppMeasurement o l’estensione Analytics (tag).
>
>Se l’implementazione di Adobe Analytics utilizza il Web SDK o l’estensione Web SDK, lo stream di dati esiste già nell’ambiente Adobe Analytics.

Per impostare il flusso di dati:

1. In Adobe Experience Platform, seleziona **[!UICONTROL Datastreams]** da [!UICONTROL DATA COLLECTION] nella barra a sinistra.

1. Seleziona **[!UICONTROL New Datastream]** (Nuovo flusso di dati).

1. Assegna un nome e una descrizione al tuo flusso di dati. Seleziona lo schema dall’elenco [!UICONTROL Event Schema] (Schema eventi).

   ![Nuovo flusso di dati](assets/new-datastream.png)

1. Seleziona **[!UICONTROL Save]** (Salva).

1. Continua seguendo i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i [passaggi di aggiornamento generati dinamicamente](https://gigazelle.github.io/cja-ttv/).
