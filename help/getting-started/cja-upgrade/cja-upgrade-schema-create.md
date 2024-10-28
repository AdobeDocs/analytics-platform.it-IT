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
source-wordcount: '923'
ht-degree: 55%

---

# Creare uno schema XDM da utilizzare con il Customer Journey Analytics

>[!NOTE]
>
>Utilizzare questa documentazione dopo aver completato il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi precedenti generati in modo dinamico per la tua organizzazione.
>
>Dopo aver completato i passaggi in questa pagina, continua seguendo i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione dal [questionario Adobe Analytics all&#39;aggiornamento di Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

>[!IMPORTANT]
>
>Prima di iniziare la creazione dello schema XDM, collabora con il team di dati e altre parti interessate in tutta l’organizzazione per identificare la progettazione dello schema ideale per il Customer Journey Analytics e le altre applicazioni Adobe Experience Platform utilizzate. Per ulteriori informazioni, consulta [Architettura dello schema da utilizzare con il Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

Adobe consiglia di creare uno schema Experience Data Model (XDM) durante l’aggiornamento al Customer Journey Analytics. Uno schema XDM consente uno schema semplificato personalizzato in base alle esigenze della tua organizzazione e alle specifiche applicazioni Platform utilizzate. Quando sono necessarie delle modifiche allo schema, non è necessario esaminare minuziosamente migliaia di campi inutilizzati per trovare il campo che richiede l’aggiornamento.

## Creare lo schema

Lo schema XDM definito rappresenta il modello dei dati raccolti in Adobe Experience Platform.

Per creare uno schema:

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. In Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Schemas]** entro [!UICONTROL DATA MANAGEMENT].

1. Seleziona **[!UICONTROL Create schema]**.

1. Nel passaggio Selezionare una classe della procedura guidata Crea schema:

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

1. Nella scheda Struttura dello schema di esempio:

   1. Seleziona **[!UICONTROL + Add]** (Aggiungi) in [!UICONTROL Field groups] (Gruppi di campi).

      ![Aggiungere un gruppo di campi](assets/add-field-group-button.png)

      I gruppi di campi sono raccolte riutilizzabili di oggetti e attributi che consentono di estendere facilmente lo schema.

   1. Nella finestra di dialogo [!UICONTROL Add fields groups] (Aggiungi gruppi di campi) seleziona il gruppo di campi **[!UICONTROL AEP Web SDK ExperienceEvent]** dall’elenco.

      ![AEP Web SDK ExperienceEvent fieldgroup](assets/select-aepwebsdk-experienceevent.png)

      Puoi selezionare il pulsante di anteprima per visualizzare un’anteprima dei campi che fanno parte del gruppo di campi, ad esempio `web > webPageDetails > name`.

      ![Anteprima AEP Web SDK ExperienceEvent fieldgroup](assets/aepwebsdk-experiencevent-preview.png)

      Seleziona **[!UICONTROL Back]** (Indietro) per chiudere l’anteprima.

   1. Seleziona **[!UICONTROL Add field groups]** (Aggiungi gruppi di campi).

1. Seleziona **[!UICONTROL +]** accanto al nome dello schema nel pannello [!UICONTROL Structure] (Struttura).

   ![Pulsante per l’aggiunta di campi nello schema di esempio](assets/example-schema-plus.png)

1. Nel pannello [!UICONTROL Field Properties] (Proprietà campo), inserisci `Identification` come nome, **[!UICONTROL Identification]** (Identificazione) come [!UICONTROL Display name] (Nome di visualizzazione), seleziona **[!UICONTROL Object]** (Oggetto) come [!UICONTROL Type] (Tipo) e seleziona **[!UICONTROL ExperienceEvent Core v2.1]** come [!UICONTROL Field Group] (Gruppo di campo).

   >[!NOTE]
   >
   >Se tale gruppo di campi non è disponibile, cercare un altro gruppo di campi contenente campi di identità. Oppure [crea un nuovo gruppo di campi](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) e [aggiungi nuovi campi di identità](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) (come `ecid`, `crmId` e altri necessari) al gruppo di campi e seleziona il nuovo gruppo di campi.

   ![Oggetto di identificazione](assets/identification-field.png)

   L’oggetto di identificazione aggiunge funzionalità di identificazione allo schema. Nel tuo caso, vuoi identificare i profili che visitano il tuo sito utilizzando l’ID Experience Cloud e l’indirizzo e-mail. Sono disponibili molti altri attributi per tenere traccia dell’identificazione della persona (ad esempio ID cliente, ID fedeltà).

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

1. Seleziona l’elemento principale dello schema che visualizza il nome dello schema, quindi seleziona il pulsante **[!UICONTROL Profile]** (Profilo).

   Viene richiesto di abilitare lo schema per il profilo. Una volta abilitato, quando i dati vengono inseriti in set di dati basati su questo schema, tali dati vengono uniti su Real-Time Customer Profile.

   Per ulteriori informazioni, consulta la sezione [Abilitare lo schema per l’utilizzo in Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile).

   >[!IMPORTANT]
   >
   >    Una volta salvato uno schema abilitato per il profilo, non è più possibile disattivarlo per il profilo.

   ![Abilitare lo schema per il profilo](./assets/enable-for-profile.png)

1. Seleziona **[!UICONTROL Save]** (Salva) per salvare lo schema.

   Hai creato uno schema minimo che modella i dati che puoi acquisire dal tuo sito Web. Lo schema consente di identificare i profili utilizzando Experience Cloud Identity e l’indirizzo e-mail. Attivando lo schema per il profilo, garantisci che i dati acquisiti dal tuo sito Web vengano aggiunti a Real-Time Customer Profile.

   Accanto ai dati sul comportamento, puoi anche acquisire i dati degli attributi del profilo dal sito (ad esempio i dettagli dei profili che si abbonano a una newsletter).

   Per acquisire questi dati del profilo:

   * Crea uno schema basato sulla classe di profilo individuale XDM.

   * Aggiungi il gruppo di campi Profile Core v2 allo schema.

   * Aggiungi un oggetto di identificazione basato sul gruppo di campi Profile Core v2.

   * Definisci l’ID Experience Cloud come identificatore principale e invia un’e-mail come identificatore.

   * Abilitare lo schema per il profilo

   Per ulteriori informazioni sull’aggiunta e la rimozione di gruppi di campi e singoli campi a uno schema, consulta la sezione [Creare e modificare schemi nell’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=it).

1. Continua seguendo i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione dal [questionario di aggiornamento di Adobe Analytics al Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

