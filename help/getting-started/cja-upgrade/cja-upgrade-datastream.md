---
title: Creare uno schema per Customer Journey Analytics
description: Scopri il percorso consigliato durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '213'
ht-degree: 100%

---

# Creare uno stream di dati da utilizzare con Customer Journey Analytics {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Creare uno stream di dati in Adobe Experience Platform"
>abstract="Uno stream di dati è una posizione intermedia che trasmette i dati a tutti i servizi configurati. Crea questa posizione in Adobe Experience Platform.<br><br>La creazione iniziale di uno stream di dati nell’interfaccia di Platform richiede solo alcuni minuti."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un flusso di dati rappresenta la configurazione lato server quando si implementano gli SDK per Web e dispositivi mobili di Adobe Experience Platform. Durante la raccolta di dati con gli SDK di Adobe Experience Platform, i dati vengono inviati alla rete Edge di Adobe Experience Platform. È il flusso di dati che determina a quali servizi vengono inoltrati i dati.

Nella configurazione, vuoi impostare lo stream di dati per inviare i dati raccolti al set di dati in Adobe Experience Platform.

>[!NOTE]
>
>I passaggi seguenti sono necessari solo per le implementazioni di Adobe Analytics che utilizzano AppMeasurement o l’estensione Analytics (tag).
>
>Se l’implementazione di Adobe Analytics utilizza Web SDK o l’estensione Web SDK, lo stream di dati esiste già nell’ambiente Adobe Analytics.

Per impostare il flusso di dati:

1. In Adobe Experience Platform, seleziona **[!UICONTROL Datastreams]** da [!UICONTROL DATA COLLECTION] nella barra a sinistra.

1. Seleziona **[!UICONTROL New Datastream]** (Nuovo flusso di dati).

1. Assegna un nome e una descrizione al tuo flusso di dati. Seleziona lo schema dall’elenco [!UICONTROL Event Schema] (Schema eventi).

   ![Nuovo flusso di dati](assets/new-datastream.png)

1. Seleziona **[!UICONTROL Save]** (Salva).

{{upgrade-final-step}}
