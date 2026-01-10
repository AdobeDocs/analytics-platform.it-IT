---
title: Creare uno schema personalizzato per Customer Journey Analytics
description: Scopri come creare uno schema personalizzato per Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 902e5890-f970-4f1a-b091-9c3e51a987db
source-git-commit: 3dc53d6955eab3048ebf8a7c9d232b4b5739c6bd
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 79%

---

# Creare uno schema personalizzato da utilizzare con Customer Journey Analytics {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create"
>title="Creare lo schema personalizzato desiderato in Adobe Experience Platform"
>abstract="Utilizza l’interfaccia utente di Adobe Experience Platform per creare uno schema in modo che Adobe conosca il formato corretto per archiviare i tuoi dati.<br><br>Questo passaggio comporta l’effettiva creazione dello schema concordato dalla tua organizzazione. Il tempo stimato per la creazione dello schema nell’interfaccia di Adobe Experience Platform è di circa una settimana, a seconda del numero di dimensioni e metriche da creare."

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create-default-aa"
>title="Creare uno schema utilizzando il gruppo di campi ExperienceEvent di Adobe Analytics"
>abstract="Utilizza il gruppo di campi “ExperienceEvent di Adobe Analytics” per creare uno schema in Adobe Experience Platform che contiene tutti i campi utilizzati da Adobe Analytics.<br><br>La creazione di uno schema basato sul gruppo di campi ExperienceEvent di Adobe Analytics è semplice e richiede solo pochi minuti per essere completata."

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-profile"
>title="Abilitare lo schema per il profilo"
>abstract="Abilita il profilo nello schema per l’utilizzo in Adobe Real-time CDP. Questo passaggio viene visualizzato perché è stato selezionato che desideri integrazione con Adobe Real-time CDP.<br><br>Poiché questo passaggio comporta la selezione di una singola casella, l’operazione richiede solo alcuni minuti."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

>[!IMPORTANT]
>
>Prima di iniziare a creare lo schema personalizzato, lavora con il team di dati e con gli altri stakeholder all’interno dell’organizzazione per identificare la progettazione dello schema ideale della tua organizzazione per Customer Journey Analytics e per le altre applicazioni Adobe Experience Platform utilizzate. Per ulteriori informazioni, consulta [Progettare lo schema da utilizzare con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

Nelle sezioni seguenti viene descritto come creare uno schema che può essere utilizzato con Customer Journey Analytics. Sono disponibili le seguenti opzioni per lo schema:

* **Schema XDM personalizzato:** (Consigliato) Consente uno schema semplificato che viene personalizzato in base alle esigenze dell’organizzazione e alle specifiche applicazioni di Platform che utilizzi. Qualsiasi modifica futura necessaria è semplice.

* **Schema Adobe Analytics che utilizza il gruppo di campi di Adobe Analytics ExperienceEvent:** richiede l’aggiunta di migliaia di campi non necessari. Qualsiasi modifica futura necessaria è più difficile.

Per ulteriori informazioni su queste opzioni di schema, consulta [Scegliere lo schema per Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

## Creare lo schema

Lo schema personalizzato definito per l’implementazione di Web SDK rappresenta il modello dei dati raccolti in Adobe Experience Platform.

Per creare uno schema personalizzato:

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. In Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Schemi]** in [!UICONTROL GESTIONE DATI].

1. Seleziona **[!UICONTROL Crea schema]**.

1. Nel passaggio **[!UICONTROL Seleziona una classe]** della procedura guidata Crea schema:

   1. Seleziona **[!UICONTROL Evento esperienza]**.

      ![Creare uno schema che evidenzia l’evento esperienza](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Per modellare il _comportamento_ di un profilo (come nome di scena, premere il pulsante per aggiungere al carrello) viene utilizzato uno schema evento esperienza. Per modellare gli _attributi_ del profilo (come nome, e-mail, genere) viene utilizzato uno schema Individual Profile.

   1. Seleziona **[!UICONTROL Avanti]**.


1. Nel [!UICONTROL passaggio Nome e revisione] della procedura guidata [!UICONTROL Crea schema]:

   1. Immetti un **[!UICONTROL nome visualizzato dello schema]** per lo schema e (facoltativo) una **[!UICONTROL Descrizione]**.

      ![Finestra Crea schema che mostra i campi Denomina lo schema](assets/create-ee-schema-wizard-step-2.png)

   1. Seleziona **[!UICONTROL Fine]**.

1. Aggiungi tutti i gruppi di campi contenenti i campi da includere nello schema.

   I gruppi di campi sono raccolte riutilizzabili di oggetti e attributi che consentono di estendere facilmente lo schema.

   1. Nella sezione **[!UICONTROL Gruppi di campi]**, selezionare **[!UICONTROL + Aggiungi]**.

      ![Aggiungere un gruppo di campi](assets/add-field-group-button.png)

   1. Nella finestra di dialogo [!UICONTROL Aggiungi gruppi di campi], seleziona il gruppo di campi **[!UICONTROL AEP Web SDK ExperienceEvent]** dall&#39;elenco.

      ![AEP Web SDK ExperienceEvent fieldgroup](assets/select-aepwebsdk-experienceevent.png)

      Puoi selezionare il pulsante di anteprima per visualizzare un’anteprima dei campi che fanno parte del gruppo di campi, ad esempio `web > webPageDetails > name`.

      ![Anteprima AEP Web SDK ExperienceEvent fieldgroup](assets/aepwebsdk-experiencevent-preview.png)

      Seleziona **[!UICONTROL Indietro]** per chiudere l&#39;anteprima.

   1. (Facoltativo) Seleziona eventuali gruppi di campi aggiuntivi da includere.

      Se hai scelto di utilizzare lo schema Adobe Analytics predefinito invece di creare uno schema XDM personalizzato, a questo punto puoi aggiungere il gruppo di campi Adobe Analytics ExperienceEvent. Tuttavia, Adobe consiglia di creare uno schema XDM personalizzato anziché aggiungere questo gruppo di campi.

      Per ulteriori informazioni su queste opzioni di schema, consulta [Scegliere lo schema per Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

   1. Seleziona **[!UICONTROL Aggiungi gruppi di campi]**.

1. (Facoltativo) Se disponi di campi personalizzati da includere nello schema, crea un gruppo di campi personalizzato e aggiungi i campi personalizzati a questo gruppo.

   1. Nella sezione **[!UICONTROL Gruppi di campi]**, selezionare **[!UICONTROL + Aggiungi]**.

      ![Aggiungere un gruppo di campi](assets/add-field-group-button.png)

   1. Nella finestra di dialogo [!UICONTROL Aggiungi gruppi di campi], seleziona **[!UICONTROL Crea nuovo gruppo di campi]**.

   1. Specifica un nome visualizzato e una descrizione facoltativa, quindi seleziona **[!UICONTROL Aggiungi gruppi di campi]**.

1. Seleziona **[!UICONTROL +]** accanto al nome dello schema nel pannello [!UICONTROL Struttura].

   ![Pulsante per l’aggiunta di campi nello schema di esempio](assets/example-schema-plus.png)

1. Nel pannello [!UICONTROL Proprietà campo], immetti `Identification` come nome, **[!UICONTROL Identificazione]** come [!UICONTROL Nome visualizzato], seleziona **[!UICONTROL Oggetto]** come [!UICONTROL Tipo] e seleziona **[!UICONTROL Core ExperienceEvent v2.1]** come [!UICONTROL Gruppo campi].

   >[!NOTE]
   >
   >Se tale gruppo di campi non è disponibile, cercane un altro contenente campi di identità. Oppure [crea un nuovo gruppo di campi](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=it) e [aggiungi nuovi campi di identità](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html?lang=it#define-a-identity-field) (come `ecid`, `crmId` e altri di cui hai bisogno) al gruppo di campi e seleziona il nuovo gruppo di campi.

   ![Oggetto di identificazione](assets/identification-field.png)

   L’oggetto di identificazione aggiunge funzionalità di individuazione dello schema. Nel tuo caso, immagina di voler identificare i profili che visitano il tuo sito utilizzando l’ID Experience Cloud e l’indirizzo e-mail. Sono disponibili molti altri attributi per monitorare l’identificazione del visitatore (ad esempio, ID cliente, ID di fidelizzazione).

   Seleziona **[!UICONTROL Applica]** per aggiungere questo oggetto allo schema.

1. Seleziona il campo **[!UICONTROL ecid]** nell&#39;oggetto di identificazione appena aggiunto, quindi seleziona **[!UICONTROL Identità]** e **[!UICONTROL Identità primaria]** e **[!UICONTROL ECID]** dall&#39;elenco [!UICONTROL Spazio dei nomi identità] nel pannello di destra.

   ![Specificare ECID come identità](./assets/specify-identity.png)

   Stai specificando l’Experience Cloud Identity come identità principale che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili con lo stesso ECID.

   Selezionare **[!UICONTROL Applica]**. Nell’attributo ecid viene visualizzata l’icona di un’impronta digitale.

1. Seleziona il campo **[!UICONTROL email]** nell&#39;oggetto di identificazione appena aggiunto, quindi seleziona **[!UICONTROL Identity]** e **[!UICONTROL Email]** dall&#39;elenco [!UICONTROL Identity namespace] nel pannello [!UICONTROL Field Properties].

   ![Specificare l’e-mail come identità](./assets/specify-email-identity.png)

   Stai specificando l’indirizzo e-mail come un’altra identità che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili.

   Selezionare **[!UICONTROL Applica]**. Nell’attributo e-mail viene visualizzata l’icona di un’impronta digitale.

   Seleziona **[!UICONTROL Salva]**.

1. (Facoltativo) Se desideri integrare Customer Journey Analytics con RTCDP, seleziona l&#39;elemento principale dello schema con il nome dello schema, quindi seleziona l&#39;opzione **[!UICONTROL Profilo]**.

   Viene richiesto di abilitare lo schema per il profilo. Una volta abilitato, quando i dati vengono inseriti in set di dati basati su questo schema, tali dati vengono uniti su Real-Time Customer Profile.

   Per ulteriori informazioni, consulta la sezione [Abilitare lo schema per l’utilizzo in Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it#profile).

   >[!IMPORTANT]
   >
   >Una volta che lo schema è stato abilitato per il profilo, non può essere disabilitato.

   ![Abilitare lo schema per il profilo](./assets/enable-for-profile.png)

1. Seleziona **[!UICONTROL Salva]** per salvare lo schema.

   Hai creato uno schema minimo che modella i dati che puoi acquisire dal tuo sito Web. Lo schema consente di identificare i profili utilizzando Experience Cloud Identity e l’indirizzo e-mail. Abilitando lo schema per il profilo, garantisci che i dati acquisiti dal tuo sito web vengano aggiunti a Real-Time Customer Profile.

   Accanto ai dati sul comportamento, puoi anche acquisire i dati degli attributi del profilo dal sito (ad esempio i dettagli dei profili che si abbonano a una newsletter).

   Per acquisire questi dati del profilo:

   * Crea uno schema basato sulla classe di profilo individuale XDM.

   * Aggiungi il gruppo di campi Profile Core v2 allo schema.

   * Aggiungi un oggetto di identificazione basato sul gruppo di campi Profile Core v2.

   * Definisci l’ID Experience Cloud come identificatore principale e l’e-mail come identificatore.

   * Abilitare lo schema per il profilo

   Per ulteriori informazioni sull’aggiunta e la rimozione di gruppi di campi e singoli campi a uno schema, consulta la sezione [Creare e modificare schemi nell’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=it).

{{upgrade-final-step}}
