---
title: Creare il connettore di origine di Analytics e mappare i campi
description: Scopri come creare il connettore di origine di Analytics e mappare i campi
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '719'
ht-degree: 100%

---

# Creare il connettore di origine di Analytics e mappare i campi {#create-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create"
>title="Creare il connettore di origine di Analytics"
>abstract="Utilizza il connettore di origine di Analytics per acquisire i dati della suite di rapporti da utilizzare in Customer Journey Analytics.<br><br>La creazione del connettore di origine di Analytics richiede solo alcuni minuti con le impostazioni predefinite."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-map-fields"
>title="Creare il connettore di origine di Analytics e mappare i campi schema"
>abstract="Il connettore di origine deve sapere come mappare i campi di Adobe Analytics per lo schema della tua organizzazione. Utilizza questa interfaccia per fornire al connettore di origine tale mappatura. Questo passaggio fa parte dell’aggiunta di dati storici a Customer Journey Analytics.<br><br>Il tempo necessario per questo passaggio dipende maggiormente dal numero di dimensioni e metriche da mappare. Questo passaggio non è difficile, quanto noioso e ripetitivo. Il completamento della mappatura dello stream di dati richiede circa una settimana di lavoro."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Informazioni sul modo in cui il connettore di origine di Analytics può inserire dati storici in Customer Journey Analytics

Puoi utilizzare il connettore di origine di Analytics per inserire in Adobe Experience Platform i dati della suite di rapporti di Adobe Analytics. Questi dati possono quindi essere utilizzati come dati storici in Customer Journey Analytics.

Questo processo presuppone che desideri [creare uno schema personalizzato da utilizzare con l’implementazione di Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), perché desideri uno schema semplificato che viene personalizzato in base alle esigenze della tua organizzazione e alle specifiche applicazioni Platform utilizzate.

Per utilizzare il connettore di origine di Analytics per inserire dati storici in Customer Journey Analytics, devi:

1. [Creare uno schema personalizzato per il connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Se non disponi già di un connettore di origine di Analytics, crea il connettore di origine di Analytics e mappa i campi sullo schema personalizzato Web SDK, come descritto di seguito.

   Oppure

   Se disponi già di un connettore di origine di Analytics, [mappa i campi dal connettore di origine allo schema personalizzato Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Aggiungere il set di dati del connettore di origine di Analytics alla connessione](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Creare il connettore di origine di Analytics e mappare i campi

Una volta creato lo schema personalizzato, devi creare il connettore di origine di Adobe Analytics da utilizzare per i dati storici. Per le linee guida generali e più esaurienti sulla creazione di un connettore di origine, consulta [Creare una connessione di origine di Adobe Analytics nell’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it).

Per creare un connettore di origine di Adobe Analytics da utilizzare per i dati storici:

1. Nell’interfaccia utente di Platform, nella sezione **[!UICONTROL Connections]** della barra a sinistra, seleziona **[!UICONTROL Sources]**.

1. Seleziona **[!UICONTROL Adobe applications]** (Applicazioni Adobe) dall’elenco [!UICONTROL CATEGORIES] (CATEGORIE).

1. Seleziona **[!UICONTROL Add data]** nella sezione Adobe Analytics.

   ![Finestra di Adobe Experience Platform con Origini selezionate insieme alle applicazioni Adobe e Aggiungi dati evidenziati.](./assets/sources-overview.png)

1. Seleziona **[!UICONTROL Report suite]**, quindi dall’elenco delle suite di rapporti, seleziona la suite di rapporti che contiene i dati storici che desideri utilizzare in Customer Journey Analytics.

   ![Finestra di Adobe Experience Platform con l’elenco delle suite di rapporti](./assets/report-suites.png)

1. Seleziona **[!UICONTROL Next]** nell’angolo in alto a destra dello schermo.

1. Seleziona **[!UICONTROL Custom schema]**, quindi seleziona lo schema creato in [Creare uno schema personalizzato che includa il gruppo di campi di Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md). <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. Mappa ogni dimensione di Adobe Analytics a una dimensione dello schema personalizzata.

   1. Nella sezione **[!UICONTROL Map standard fields]** seleziona la scheda **[!UICONTROL Custom]**.

   1. Seleziona **[!UICONTROL Add new mapping]**.

   ![mappa campi schema](assets/schema-mapping.png)

   1. In **[!UICONTROL Source field]**, seleziona un campo di Adobe Analytics dal gruppo di campi Modello di Adobe Analytics ExperienceEvent. Quindi, in **[!UICONTROL Target field]**, seleziona il campo personalizzato nello schema XDM a cui desideri mapparlo.

      Non tutti i campi di Adobe Analytics hanno un campo corrispondente in XDM a causa delle differenze di architettura intrinseche tra AppMeasurement e XDM.

   1. Ripeti questa procedura per ogni campo del gruppo di campi Modello di Adobe Analytics ExperienceEvent che utilizzi per raccogliere dati in Adobe Analytics.

1. Seleziona **[!UICONTROL Next]** nell’angolo in alto a destra dello schermo.

1. Assegna un nome al flusso di dati e (facoltativamente) fornisci una descrizione.

   ![Finestra di Adobe Experience Platform che evidenzia la sezione dei dettagli del flusso di dati](./assets/dataflow-detail.png)

1. Seleziona **[!UICONTROL Next]** nell’angolo in alto a destra dello schermo.

1. Rivedi la connessione, quindi seleziona **[!UICONTROL Finish]**.

   ![Finestra di Adobe Experience Platform che evidenzia le sezioni Connetti e Tipo di dati per la revisione](./assets/review.png)

   Dopo la creazione della connessione, il flusso di dati viene creato automaticamente per popolare un set di dati con i dati di Adobe Analytics dalla suite di rapporti. Il flusso di dati acquisisce fino a 13 mesi di dati storici per le sandbox di produzione. La retrocompilazione nelle sandbox non di produzione è limitata a 3 mesi.

   Se stai utilizzando il connettore di origine di Analytics per inserire dati storici nell’implementazione di Customer Journey Analytics Web SDK, devi aggiungere questo set di dati creato automaticamente alla connessione creata per l’implementazione di Web SDK.

{{upgrade-final-step}}
