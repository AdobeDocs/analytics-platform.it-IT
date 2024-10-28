---
title: Creazione di uno schema per il Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 34%

---

# Creare un flusso di dati da utilizzare con il Customer Journey Analytics

>[!NOTE]
>
>Utilizzare questa documentazione dopo aver completato il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi precedenti generati in modo dinamico per la tua organizzazione.
>
>Dopo aver completato i passaggi in questa pagina, continua seguendo i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione dal [questionario Adobe Analytics all&#39;aggiornamento di Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un flusso di dati rappresenta la configurazione lato server quando si implementano gli SDK per Web e dispositivi mobili di Adobe Experience Platform. Durante la raccolta di dati con gli SDK di Adobe Experience Platform, i dati vengono inviati alla rete Edge di Adobe Experience Platform. È lo stream di dati che determina a quali servizi vengono inoltrati i dati.

Nella configurazione, desideri che i dati raccolti dal sito Web vengano inviati al set di dati in Adobe Experience Platform.

Per impostare il flusso di dati:

1. In Adobe Experience Platform, seleziona **[!UICONTROL Datastreams]** da [!UICONTROL DATA COLLECTION] nella barra a sinistra.

1. Seleziona **[!UICONTROL New Datastream]** (Nuovo flusso di dati).

1. Assegna un nome e una descrizione al tuo flusso di dati. Seleziona lo schema dall’elenco [!UICONTROL Event Schema] (Schema eventi).

   ![Nuovo flusso di dati](assets/new-datastream.png)

1. Seleziona **[!UICONTROL Save]** (Salva).

1. Continua seguendo i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione dal [questionario di aggiornamento di Adobe Analytics al Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

