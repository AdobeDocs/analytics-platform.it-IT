---
title: Creare uno schema personalizzato per Customer Journey Analytics
description: Scopri come creare uno schema personalizzato per Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 902e5890-f970-4f1a-b091-9c3e51a987db
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 53%

---

# Creare uno schema personalizzato da utilizzare con Customer Journey Analytics {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create"
>title="Creare lo schema personalizzato desiderato in Adobe Experience Platform"
>abstract="Utilizza l’interfaccia utente di Adobe Experience Platform per creare uno schema in modo che Adobe conosca il formato corretto per archiviare i tuoi dati.<br><br>Questo passaggio comporta l’effettiva creazione dello schema concordato dalla tua organizzazione. Il tempo stimato per la creazione dello schema nell’interfaccia di Adobe Experience Platform è di circa una settimana, a seconda del numero di dimensioni e metriche da creare."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create-default-aa"
>title="Creare uno schema utilizzando il gruppo di campi ExperienceEvent di Adobe Analytics"
>abstract="Utilizza il gruppo di campi “ExperienceEvent di Adobe Analytics” per creare uno schema in Adobe Experience Platform che contiene tutti i campi utilizzati da Adobe Analytics.<br><br>La creazione di uno schema basato sul gruppo di campi ExperienceEvent di Adobe Analytics è semplice e richiede solo pochi minuti per essere completata."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-profile"
>title="Abilitare lo schema per il profilo"
>abstract="Abilita il profilo nello schema per l’utilizzo in Adobe Real-time CDP. Questo passaggio viene visualizzato perché è stato selezionato che desideri integrazione con Adobe Real-time CDP.<br><br>Poiché questo passaggio comporta la selezione di una singola casella, l’operazione richiede solo alcuni minuti."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

>[!IMPORTANT]
>
>Prima di iniziare a creare lo schema personalizzato, rivolgiti al team di dati e ad altre parti interessate all’interno dell’organizzazione per identificare la progettazione dello schema ideale per Customer Journey Analytics e le altre applicazioni Adobe Experience Platform utilizzate. Per ulteriori informazioni, consulta [Architettura dello schema da utilizzare con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

Nelle sezioni seguenti viene descritto come creare uno schema che può essere utilizzato con Customer Journey Analytics. Sono disponibili le seguenti opzioni di schema:

* **Schema XDM personalizzato:** (consigliato) Consente uno schema semplificato personalizzato in base alle esigenze della tua organizzazione e alle specifiche applicazioni Platform utilizzate. Qualsiasi modifica futura necessaria è semplice.

* **Lo schema Adobe Analytics che utilizza il gruppo di campi Adobe Analytics ExperienceEvent:** richiede l&#39;aggiunta di migliaia di campi non necessari. Qualsiasi cambiamento futuro richiesto è più difficile.

Per ulteriori informazioni su queste opzioni di schema, vedere [Scegliere lo schema per Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

## Creare lo schema

Lo schema personalizzato definito per l’implementazione di Web SDK rappresenta il modello dei dati raccolti in Adobe Experience Platform.

Per creare uno schema personalizzato:

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. In Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Schemas]** entro [!UICONTROL DATA MANAGEMENT].

1. Seleziona **[!UICONTROL Create schema]**.

1. Nel passaggio **[!UICONTROL Select a class]** della procedura guidata Crea schema:

   1. Seleziona **[!UICONTROL Experience Event]**.

      ![Crea uno schema che evidenzia l&#39;evento esperienza](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Lo schema Experience Event viene utilizzato per modellare il _comportamento_ di un profilo (come nome di scena, pulsante da aggiungere al carrello). Per modellare gli _attributi_ del profilo (come nome, e-mail, genere) viene utilizzato uno schema Individual Profile.

   1. Seleziona **[!UICONTROL Next]**.


1. In [!UICONTROL Name and review step] della procedura guidata [!UICONTROL Create schema]:

   1. Immetti **[!UICONTROL Schema display name]** per lo schema e (facoltativo) **[!UICONTROL Description]**.

      ![Finestra Crea schema con il nome dei campi dello schema](assets/create-ee-schema-wizard-step-2.png)

   1. Seleziona **[!UICONTROL Finish]**.

1. Aggiungi tutti i gruppi di campi contenenti i campi da includere nello schema.

   I gruppi di campi sono raccolte riutilizzabili di oggetti e attributi che consentono di estendere facilmente lo schema.

   1. Nella sezione **[!UICONTROL Field groups]**, selezionare **[!UICONTROL + Add]**.

      ![Aggiungere un gruppo di campi](assets/add-field-group-button.png)

   1. Nella finestra di dialogo [!UICONTROL Add fields groups] (Aggiungi gruppi di campi) seleziona il gruppo di campi **[!UICONTROL AEP Web SDK ExperienceEvent]** dall’elenco.

      ![AEP Web SDK ExperienceEvent fieldgroup](assets/select-aepwebsdk-experienceevent.png)

      Puoi selezionare il pulsante di anteprima per visualizzare un’anteprima dei campi che fanno parte del gruppo di campi, ad esempio `web > webPageDetails > name`.

      ![Anteprima AEP Web SDK ExperienceEvent fieldgroup](assets/aepwebsdk-experiencevent-preview.png)

      Seleziona **[!UICONTROL Back]** (Indietro) per chiudere l’anteprima.

   1. (Facoltativo) Seleziona eventuali gruppi di campi aggiuntivi da includere.

      Se hai scelto di utilizzare lo schema Adobe Analytics predefinito invece di creare uno schema XDM personalizzato, ora puoi aggiungere il gruppo di campi Adobe Analytics ExperienceEvent. Tuttavia, Adobe consiglia di creare uno schema XDM personalizzato anziché aggiungere questo gruppo di campi.

      Per ulteriori informazioni su queste opzioni di schema, vedere [Scegliere lo schema per Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

   1. Seleziona **[!UICONTROL Add field groups]**.

1. (Facoltativo) Se disponi di campi personalizzati da includere nello schema, crea un gruppo di campi personalizzato e aggiungi i campi personalizzati al gruppo di campi.

   1. Nella sezione **[!UICONTROL Field groups]**, selezionare **[!UICONTROL + Add]**.

      ![Aggiungere un gruppo di campi](assets/add-field-group-button.png)

   1. Nella finestra di dialogo [!UICONTROL Add fields groups], seleziona **[!UICONTROL Create new field group]**.

   1. Specificare un nome visualizzato e una descrizione facoltativa, quindi selezionare **[!UICONTROL Add field groups]**.

1. Seleziona **[!UICONTROL +]** accanto al nome dello schema nel pannello [!UICONTROL Structure] (Struttura).

   ![Pulsante per l’aggiunta di campi nello schema di esempio](assets/example-schema-plus.png)

1. Nel pannello [!UICONTROL Field Properties] (Proprietà campo), inserisci `Identification` come nome, **[!UICONTROL Identification]** (Identificazione) come [!UICONTROL Display name] (Nome di visualizzazione), seleziona **[!UICONTROL Object]** (Oggetto) come [!UICONTROL Type] (Tipo) e seleziona **[!UICONTROL ExperienceEvent Core v2.1]** come [!UICONTROL Field Group] (Gruppo di campo).

   >[!NOTE]
   >
   >Se tale gruppo di campi non è disponibile, cercare un altro gruppo di campi contenente campi di identità. Oppure [crea un nuovo gruppo di campi](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) e [aggiungi nuovi campi di identità](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) (come `ecid`, `crmId` e altri necessari) al gruppo di campi e seleziona il nuovo gruppo di campi.

   ![Oggetto di identificazione](assets/identification-field.png)

   L’oggetto di identificazione aggiunge funzionalità di identificazione allo schema. Nel tuo caso, vuoi identificare i profili che visitano il tuo sito utilizzando l’Experience Cloud ID e l’indirizzo e-mail. Sono disponibili molti altri attributi per tenere traccia dell’identificazione della persona (ad esempio ID cliente, ID fedeltà).

   Seleziona **[!UICONTROL Apply]** (Applica) per aggiungere questo oggetto allo schema.

1. Seleziona il campo **[!UICONTROL ecid]** nell’oggetto di identificazione appena aggiunto e seleziona **[!UICONTROL Identity]** (Identità) e **[!UICONTROL Primary Identity]** (Identità principale) e **[!UICONTROL ECID]** dall’elenco [!UICONTROL Identity namespace] (Spazio dei nomi dell’identità) nel pannello di destra.

   ![Specificare ECID come identità](./assets/specify-identity.png)

   Stai specificando l’Experience Cloud Identity come identità principale che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili con lo stesso ECID.

   Seleziona **[!UICONTROL Apply]** (Applica). Nell’attributo ecid viene visualizzata l’icona di un’impronta digitale.

1. Seleziona il campo **[!UICONTROL email]** nell’oggetto di identificazione appena aggiunto e seleziona **[!UICONTROL Identity]** (identità) e **[!UICONTROL Email]** dall’elenco [!UICONTROL Identity namespace] (Spazio dei nomi dell’identità) nel pannello [!UICONTROL Field Properties] (Proprietà campo).

   ![Specificare l’e-mail come identità](./assets/specify-email-identity.png)

   Stai specificando l’indirizzo e-mail come un’altra identità che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili.

   Seleziona **[!UICONTROL Apply]** (Applica). Nell’attributo e-mail viene visualizzata l’icona di un’impronta digitale.

   Seleziona **[!UICONTROL Save]** (Salva).

1. (Facoltativo) Se desideri integrare Customer Journey Analytics con RTCDP, seleziona l&#39;elemento principale dello schema che mostra il nome dello schema, quindi seleziona l&#39;opzione **[!UICONTROL Profile]**.

   Viene richiesto di abilitare lo schema per il profilo. Una volta abilitato, quando i dati vengono inseriti in set di dati basati su questo schema, tali dati vengono uniti su Real-Time Customer Profile.

   Per ulteriori informazioni, consulta la sezione [Abilitare lo schema per l’utilizzo in Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile).

   >[!IMPORTANT]
   >
   >Dopo aver abilitato uno schema per il profilo, non può essere disabilitato per il profilo.

   ![Abilitare lo schema per il profilo](./assets/enable-for-profile.png)

1. Seleziona **[!UICONTROL Save]** (Salva) per salvare lo schema.

   Hai creato uno schema minimo che modella i dati che puoi acquisire dal tuo sito Web. Lo schema consente di identificare i profili utilizzando Experience Cloud Identity e l’indirizzo e-mail. Attivando lo schema per il profilo, garantisci che i dati acquisiti dal tuo sito Web vengano aggiunti a Real-Time Customer Profile.

   Accanto ai dati sul comportamento, puoi anche acquisire i dati degli attributi del profilo dal sito (ad esempio i dettagli dei profili che si abbonano a una newsletter).

   Per acquisire questi dati del profilo:

   * Crea uno schema basato sulla classe di profilo individuale XDM.

   * Aggiungi il gruppo di campi Profile Core v2 allo schema.

   * Aggiungi un oggetto di identificazione basato sul gruppo di campi Profile Core v2.

   * Definisci Experience Cloud ID come identificatore primario e e-mail come identificatore.

   * Abilitare lo schema per il profilo

   Per ulteriori informazioni sull’aggiunta e la rimozione di gruppi di campi e singoli campi a uno schema, consulta la sezione [Creare e modificare schemi nell’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=it).

{{upgrade-final-step}}
