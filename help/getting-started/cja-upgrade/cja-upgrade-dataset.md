---
title: Creare uno schema per Customer Journey Analytics
description: Scopri il percorso consigliato durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 100%

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

1. In Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Datasets]** all’interno di [!UICONTROL DATA MANAGEMENT].

1. Seleziona **[!UICONTROL Create dataset]**.

   ![Creare un set di dati](assets/create-dataset.png)

1. Seleziona **[!UICONTROL Create dataset from schema]** (Crea set di dati da schema).

   ![Creare un set di dati da uno schema](assets/create-dataset-from-schema.png)

1. Seleziona lo schema creato in precedenza e seleziona **[!UICONTROL Next]** (Avanti).

1. Assegna un nome al set di dati e (facoltativamente) fornisci una descrizione.

   ![Assegnare un nome al set di dati](assets/name-your-datatest.png)

1. Seleziona **[!UICONTROL Finish]** (Fine).

1. Seleziona il pulsante **[!UICONTROL Profile]** (Profilo).

   Viene richiesto di abilitare il set di dati per il profilo. Una volta abilitato, il set di dati arricchisce i profili dei clienti in tempo reale con i relativi dati inseriti.

   >[!IMPORTANT]
   >
   >    Puoi abilitare un set di dati per il profilo solo quando lo schema a cui aderisce il set di dati è abilitato anche per il profilo.

   ![Abilitare lo schema per il profilo](assets/aepwebsdk-dataset-profile.png)

   Per ulteriori informazioni su come visualizzare, visualizzare in anteprima, creare o eliminare un set di dati, consulta la sezione [Guida all’interfaccia utente dei set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it). Puoi anche scoprire come abilitare un set di dati per il profilo cliente in tempo reale.

{{upgrade-final-step}}
