---
title: Creare uno schema per Customer Journey Analytics
description: Scopri il percorso consigliato durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
TQID: https://experienceleague.adobe.com/s-wqiMU0z0Q5h6qdsqtMPfjdelvqoaAg4rNkvhUEN-4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 89%

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

1. Seleziona **[!UICONTROL Nuovo flusso di dati]**.

1. Assegna un nome e una descrizione al tuo flusso di dati. Seleziona lo schema dall&#39;elenco [!UICONTROL Schema evento].

   ![Nuovo flusso di dati](assets/new-datastream.png)

1. Seleziona **[!UICONTROL Salva]**.

{{upgrade-final-step}}
