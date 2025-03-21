---
title: Creare set di dati di ricerca per classificare i dati in Customer Journey Analytics
description: Scopri come creare set di dati di ricerca per classificare i dati in Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f5443ddd-81d0-43cc-99cb-215e7ddf5acf
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 11%

---

# Creare set di dati di ricerca per classificare i dati in Customer Journey Analytics {#upgrade-lookup-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-lookup-dataset-create"
>title="Creare un set di dati di ricerca per ogni dimensione contenente dati di classificazione"
>abstract="Simili ai dati delle classificazioni in Adobe Analytics, i set di dati di ricerca costituiscono il metodo con cui vengono classificati i dati in Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Simili ai dati delle classificazioni in Adobe Analytics, i set di dati di ricerca costituiscono il metodo con cui vengono classificati i dati in Customer Journey Analytics.

Quando si utilizza il connettore di origine di Analytics, alcuni set di dati di ricerca standard vengono applicati automaticamente al momento del rapporto. Per ulteriori informazioni, consulta [Aggiungere ricerche standard ai set di dati](/help/connections/standard-lookups.md).

Per classificare i dati in Customer Journey Analytics quando si utilizza Experience Platform Web SDK, è necessario creare uno schema personalizzato e un set di dati di ricerca per ogni dimensione che contiene i dati da classificare.

## Creare uno schema personalizzato da utilizzare con il set di dati di ricerca

Crea un nuovo schema personalizzato per ogni dimensione che contiene i dati da classificare in Customer Journey Analytics. Quando crei il set di dati di ricerca in un passaggio successivo, farà riferimento a questo schema.

Ripeti questo processo per ogni dimensione che contiene i dati da classificare.

Per creare uno schema da utilizzare con un set di dati di ricerca in Customer Journey Analytics:

1. In Adobe Experience Platform, seleziona **[!UICONTROL Schemas]** nella sezione **[!UICONTROL Data Management]** nella barra a sinistra.

1. Seleziona **[!UICONTROL Create schema]**.

   ![Pulsante Crea schema](assets/schema-create.png)

1. Seleziona **[!UICONTROL Manual]**. Questo consente di aggiungere manualmente campi e gruppi di campi allo schema. Scegliere **[!UICONTROL Select]** per passare alla pagina successiva della procedura guidata di creazione.

1. Nella pagina **[!UICONTROL Schema details]**, seleziona **[!UICONTROL Other]**, quindi **[!UICONTROL Custom]**.

   ![Crea personalizzato](assets/schema-custom.png)

1. Seleziona **[!UICONTROL Create class]**.

   <!-- add screenshot -->

1. Nella finestra di dialogo **[!UICONTROL Create class]** specificare un nome e una descrizione per lo schema, selezionare **[!UICONTROL Record]**, quindi selezionare **[!UICONTROL Create]**.

1. Continua con [Crea un set di dati di ricerca](#create-a-lookup-dataset).

## Creare un set di dati di ricerca

Dopo aver [creato uno schema personalizzato](#create-a-custom-schema-to-use-with-the-lookup-dataset) da utilizzare per un set di dati di ricerca, è necessario creare il set di dati di ricerca e mapparlo allo schema.

Ripeti questo processo per ogni dimensione che contiene i dati da classificare.

Per creare un set di dati di ricerca da utilizzare con uno schema in Customer Journey Analytics:

>[!NOTE]
>
>Il processo seguente utilizza un file CSV per creare il set di dati. Puoi anche utilizzare qualsiasi altro metodo disponibile per importare dati in Experience Platform, ad esempio la configurazione di un flusso di dati.

1. In Adobe Experience Platform, seleziona **[!UICONTROL Workflows]** nella barra a sinistra.

   ![Crea personalizzato](assets/lookup-dataset-workflows.png)

1. Seleziona **[!UICONTROL Map CSV to XDM schema]**, quindi seleziona **[!UICONTROL Launch]**.

1. Nella sezione **[!UICONTROL Dataset details]**, selezionare **[!UICONTROL New dataset]**.

1. Specifica nome e descrizione per il set di dati.

1. Nel campo **[!UICONTROL Schema]** selezionare lo schema creato per i set di dati di ricerca, come descritto in [Creare uno schema per i set di dati di ricerca](#create-a-schema-for-lookup-datasets).

1. Seleziona **[!UICONTROL Next]**.

1. Nella sezione **[!UICONTROL Upload files]** di **[!UICONTROL Map CSV to XDM schema page]** selezionare **[!UICONTROL Choose files]**, quindi cercare nel file system il file contenente le informazioni di classificazione per la dimensione per la quale si desidera applicare i dati di classificazione. Ad esempio, potrebbe trattarsi di un foglio di calcolo che elenca gli ID dei campi e i nomi dei campi corrispondenti. <!-- correct? How can I better explain what this file is?-->

   ![Mappa file CSV](assets/lookup-map-csv.png)

1. Seleziona **[!UICONTROL Next]**

1. Dopo il caricamento del file, controlla le mappature per assicurarti che siano accurate. Le colonne del file CSV sono elencate in **[!UICONTROL Source Data]** e i campi dello schema XDM corrispondenti sono elencati in **[!UICONTROL Target Field]**.

   Platform fornisce automaticamente consigli intelligenti per campi mappati automaticamente in base allo schema o al set di dati di destinazione selezionato. Puoi regolare manualmente le regole di mappatura in base ai tuoi casi d’uso.

   Per ulteriori informazioni sul processo di mappatura, consulta [Mappare un file CSV su uno schema XDM esistente](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema) nella documentazione di Experience Platform.

1. Seleziona **[!UICONTROL Finish]**.

1. Continua con [Aggiungi il set di dati di ricerca alla tua connessione in Customer Journey Analytics](#add-the-lookup-dataset-to-your-connection-in-customer-journey-analytics).

## Aggiungere il set di dati di ricerca alla connessione in Customer Journey Analytics

Dopo aver [creato uno schema personalizzato](#create-a-custom-schema-to-use-with-the-lookup-dataset) e [creato un set di dati di ricerca](#create-a-lookup-dataset), è necessario aggiungere il set di dati di ricerca alla connessione in Customer Journey Analytics.

Ripeti questo processo per ogni dimensione che contiene i dati da classificare.

Per aggiungere il set di dati di ricerca alla connessione in Customer Journey Analytics:

1. In Customer Journey Analytics, seleziona la scheda **[!UICONTROL Connections]**.

1. Seleziona l&#39;icona ![Altro](assets/More.svg) accanto alla connessione in cui desideri aggiungere il set di dati di ricerca, quindi seleziona **[!UICONTROL Edit]**.

   <!-- add screenshot -->

1. Seleziona **[!UICONTROL Add datasets]**.

1. Nella finestra di dialogo **[!UICONTROL Add datasets]** selezionare il set di dati di ricerca creato, quindi selezionare **[!UICONTROL Next]**.

1. Nel campo **[!UICONTROL Person ID]**, seleziona un ID persona tra le identità disponibili definite nello schema del set di dati configurato in Experience Platform. <!-- fill out other fields? -->

1. Seleziona **[!UICONTROL Add datasets]**, quindi seleziona **[!UICONTROL Save]**.

   <!-- is there a step right in between here where you select the dataset -->

1. Utilizzando il campo **[!UICONTROL Key]** e il campo **[!UICONTROL Matching key]**, crea una correlazione tra il campo nel set di dati di ricerca e quello nel set di dati evento o di riepilogo.

1. Ripeti questo processo fino a quando tutti i set di dati di ricerca non vengono aggiunti alla connessione in Customer Journey Analytics.

{{upgrade-final-step}}

