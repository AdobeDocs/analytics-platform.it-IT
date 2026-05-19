---
title: Creare uno schema per Customer Journey Analytics
description: Scopri il percorso consigliato durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
autotag-review: '2026-05-19T08:12:18.647Z'
TQID: 'https://experienceleague.adobe.com/ti9UiQzAa9wBCCH-44dmUxTzojuh5ZHu9YJ9HNC8OHI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 84%

---

# Creare un set di dati da utilizzare con Customer Journey Analytics {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Creare un set di dati in Adobe Experience Platform"
>abstract="Per set di dati si intende la posizione in cui si trovano i dati raccolti. Crea questa posizione in Adobe Experience Platform.<br><br>La creazione di un set di dati con uno schema richiede solo alcuni minuti."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un set di dati è il costrutto che memorizza e gestisce i dati raccolti in Adobe Experience Platform.

Per creare un set di dati:

1. In Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Set di dati]** in [!UICONTROL GESTIONE DATI].

1. Seleziona **[!UICONTROL Crea set di dati]**.

   ![Creare un set di dati](assets/create-dataset.png)

1. Seleziona **[!UICONTROL Crea set di dati dallo schema]**.

   ![Creare un set di dati da uno schema](assets/create-dataset-from-schema.png)

1. Seleziona lo schema creato in precedenza e seleziona **[!UICONTROL Successivo]**.

1. Assegna un nome al set di dati e (facoltativamente) fornisci una descrizione.

   ![Assegnare un nome al set di dati](assets/name-your-datatest.png)

1. Seleziona **[!UICONTROL Fine]**.

1. Selezionare l&#39;opzione **[!UICONTROL Profilo]**.

   Viene richiesto di abilitare il set di dati per il profilo. Una volta abilitato, il set di dati arricchisce i profili dei clienti in tempo reale con i relativi dati inseriti.

   >[!IMPORTANT]
   >
   >    Puoi abilitare un set di dati per il profilo solo quando lo schema a cui aderisce il set di dati è abilitato anche per il profilo.

   ![Abilitare lo schema per il profilo](assets/aepwebsdk-dataset-profile.png)

   Per ulteriori informazioni su come visualizzare, visualizzare in anteprima, creare o eliminare un set di dati, consulta la sezione [Guida all’interfaccia utente dei set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it). Puoi anche scoprire come abilitare un set di dati per il profilo cliente in tempo reale.

{{upgrade-final-step}}
