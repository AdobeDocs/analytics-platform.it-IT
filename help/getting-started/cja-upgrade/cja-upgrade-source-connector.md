---
title: Creare il connettore di origine di Analytics e mappare i campi
description: Scopri come creare il connettore di origine di Analytics e mappare i campi
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8e51e97b0616a5406c5c3a29431fde87a551ab9f
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 2%

---

# Creare il connettore di origine di Analytics e mappare i campi

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), oppure puoi seguire i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

Puoi usare il connettore di origine di Analytics per inserire in Adobe Experience Platform i dati della suite di rapporti di Adobe Analytics. Questi dati possono quindi essere utilizzati come dati storici nel Customer Journey Analytics.

Nei passaggi seguenti si presuppone che si desideri [creare uno schema XDM durante l&#39;aggiornamento al Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), perché si desidera uno schema semplificato personalizzato in base alle esigenze della propria organizzazione e alle specifiche applicazioni Platform utilizzate.

Una volta creato lo schema XDM, devi creare il connettore di origine di Adobe Analytics da utilizzare per i dati storici.

Per linee guida generali e più complete sulla creazione di un connettore di origine, vedi [Creare una connessione di origine Adobe Analytics nell&#39;interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it).

Per creare un connettore di origine di Adobe Analytics da utilizzare per i dati storici:

1. Nell&#39;interfaccia utente di Platform, nella sezione **[!UICONTROL Connections]** della barra a sinistra, seleziona **[!UICONTROL Sources]**.

1. Seleziona **[!UICONTROL Adobe applications]** (Applicazioni Adobe) dall’elenco [!UICONTROL CATEGORIES] (CATEGORIE).

1. Seleziona **[!UICONTROL Add data]** nel riquadro Adobe Analytics.

   ![Finestra di Adobe Experience Platform con Origini selezionate insieme alle applicazioni Adobe ed Aggiungi dati evidenziati.](./assets/sources-overview.png)

1. Seleziona **[!UICONTROL Report suite]**, quindi dall&#39;elenco delle suite di rapporti, seleziona la suite di rapporti che contiene i dati storici che desideri utilizzare nel Customer Journey Analytics.

   ![Finestra di Adobe Experience Platform con l&#39;elenco delle suite di rapporti](./assets/report-suites.png)

1. Selezionare **[!UICONTROL Next]** nell&#39;angolo superiore destro dello schermo.

1. Seleziona **[!UICONTROL Custom schema]**, quindi seleziona lo schema creato in [Creare uno schema XDM che includa il gruppo di campi di Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md). <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. Mappa ogni dimensione di Adobe Analytics a una dimensione dello schema XDM personalizzata.

   1. Nella sezione **[!UICONTROL Map standard fields]** selezionare la scheda **[!UICONTROL Custom]**.

   1. Seleziona **[!UICONTROL Add new mapping]**.

   ![mappa campi schema](assets/schema-mapping.png)

   1. In **[!UICONTROL Source field]**, selezionare un campo Adobe Analytics dal gruppo di campi Modello Adobe Analytics ExperienceEvent. Quindi, in **[!UICONTROL Target field]**, seleziona il campo XDM a cui vuoi mappare.

   1. Ripeti questa procedura per ogni campo del gruppo di campi Modello Adobe Analytics ExperienceEvent che utilizzi per raccogliere dati in Adobe Analytics.

1. Selezionare **[!UICONTROL Next]** nell&#39;angolo superiore destro dello schermo.

1. Assegna un nome al flusso di dati e (facoltativamente) fornisci una descrizione.

   ![Finestra di Adobe Experience Platform che evidenzia la sezione dei dettagli del flusso di dati](./assets/dataflow-detail.png)

1. Selezionare **[!UICONTROL Next]** nell&#39;angolo superiore destro dello schermo.

1. Rivedere la connessione, quindi selezionare **[!UICONTROL Finish]**.

   ![Finestra di Adobe Experience Platform che evidenzia le sezioni Connect e Data type per la revisione](./assets/review.png)

   Dopo la creazione della connessione, il flusso di dati viene creato automaticamente per popolare un set di dati con i dati di Adobe Analytics dalla suite di rapporti. Il flusso di dati acquisisce fino a 13 mesi di dati storici per le sandbox di produzione. La retrocompilazione nelle sandbox non di produzione è limitata a tre mesi.

   Se utilizzi il connettore di origine di Analytics per inserire dati storici nell’implementazione dell’SDK web di Customer Journey Analytics, devi aggiungere questo set di dati creato automaticamente alla connessione creata per l’implementazione dell’SDK web.

1. Continua seguendo i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i [passaggi di aggiornamento generati dinamicamente](https://gigazelle.github.io/cja-ttv/).




