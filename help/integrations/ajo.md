---
title: Integrare Adobe Journey Optimizer con Customer Journey Analytics
description: Inserire i dati generati da Adobe Journey Optimizer e analizzarli utilizzando Analysis Workspace all’interno di Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: eda523204ec40a5660621cfd9e96ba77b61aa22c
workflow-type: tm+mt
source-wordcount: '2876'
ht-degree: 43%

---

# Integrare AJO con Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/get-started/get-started) ti consente di fornire esperienze connesse, contestuali e personalizzate. Aiuta i tuoi clienti a prendere familiarità con il passaggio successivo nel loro percorso.

Puoi configurare i dati generati da AJO per eseguire analisi avanzate in Customer Journey Analytics. Puoi configurare automaticamente questa integrazione. Se necessario, puoi effettuare personalizzazioni manuali aggiuntive ai set di dati, alle dimensioni o alle metriche disponibili nella connessione o nelle visualizzazioni dati.

## Configurare automaticamente l’integrazione di AJO

{{release-limited-testing-section}}

AJO supporta l’utilizzo di Customer Journey Analytics come motore di reporting. Consulta [Introduzione alla nuova interfaccia di reporting](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channel-report/report-gs-cja) nella documentazione di AJO.

Dopo aver abilitato il reporting di Customer Journey Analytics per AJO, vengono create automaticamente una [connessione](/help/connections/overview.md) e una [visualizzazione dati](/help/data-views/data-views.md) per la sandbox specifica.

### Connessione

La connessione porta il nome **[!UICONTROL AJO Enabled Connection (*nome sandbox *)]**e ha i seguenti valori predefiniti per la configurazione e i set di dati:

| **Impostazioni della connessione** | Valore |
|---|---| 
| [!UICONTROL Connection name] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL Connection description] | [!UICONTROL *Descrivi qui la tua connessione*] |
| [!UICONTROL Tags] | [!UICONTROL *Seleziona tag*] |


| **Impostazioni dei dati** | Valore |
|---|---| 
| [!UICONTROL Enable rolling data window] | Abilitata. [!UICONTROL Selected number of months] `13`. |
| [!UICONTROL Sandbox] | [!UICONTROL *nome della sandbox*] (disattivato; non è possibile modificare questa impostazione). |
| [!UICONTROL Average number of daily events] | meno di 1 milione (disabilitato; non è possibile modificare questa impostazione). |


| Nome del set di dati | Schema | Tipo di set di dati | Tipo di origine dati | ID persona | Chiave | Chiave corrispondente | Importare nuovi dati | Retrocompilazione dei dati |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL AJO Entity Dataset] | [!UICONTROL AJO Entity Record Schema] | [!UICONTROL Lookup] | [!UICONTROL Other] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![Stato verde](assets/../../connections/assets/status-green.svg) Attiva | ![Stato grigio](assets/../../connections/assets/status-gray.svg) Disattiva |
| [!UICONTROL Journey Step Events] | [!UICONTROL Journey Step Event schema for Journey Orchestration] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL  IdentityMap(\<primary\>)] | - | - | ![Stato verde](assets/../../connections/assets/status-green.svg) Attiva | ![Stato grigio](assets/../../connections/assets/status-gray.svg) Disattiva |
| [!UICONTROL AJO Email Tracking Experience Event Dataset] | [!UICONTROL AJO Email Tracking Experience Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Stato verde](assets/../../connections/assets/status-green.svg) Attiva | ![Stato grigio](assets/../../connections/assets/status-gray.svg) Disattiva |
| [!UICONTROL AJO Message Feedback Event Dataset] | [!UICONTROL AJO Message Feedback Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Stato verde](assets/../../connections/assets/status-green.svg) Attiva | ![Stato grigio](assets/../../connections/assets/status-gray.svg) Disattiva |
| [!UICONTROL AJO Push Tracking Experience Event Dataset] | [!UICONTROL AJO Push Tracking Experience Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Stato verde](assets/../../connections/assets/status-green.svg) Attiva | ![Stato grigio](assets/../../connections/assets/status-gray.svg) Disattiva |


### Visualizzazione dati

La visualizzazione dati porta il nome **Abilita visualizzazione dati di AJO (*nome sandbox*)**.

- Nella scheda **[!UICONTROL Configure]**, i seguenti valori sono configurati come predefiniti.

  | Impostazioni | Valore |
  |---|---|
  | [!UICONTROL Connection] | Connessione abilitata per AJO (*nome sandbox*) |
  | [!UICONTROL Name] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL External ID] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` (derivato dal nome) |
  | [!UICONTROL Description] | `undefined` |

  {style="table-layout:fixed"}

  | Compatibilità | Valore |
  |---|---|
  | [!UICONTROL Set as the default data view in Adobe Journey Optimizer] | Abilitato (impostazione predefinita).<br/><br/>Questa opzione di configurazione consente di designare una visualizzazione dati da utilizzare con AJO, senza la necessità di eseguire la configurazione manuale. Per informazioni su come abilitare questa opzione di configurazione (se non è già abilitata per impostazione predefinita), consultare la sezione [Compatibilità](/help/data-views/create-dataview.md#compatibility) in [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md). <br/><br/>Quando si disattiva l’opzione, viene visualizzata una finestra di dialogo in cui viene richiesto se si desidera continuare a modificare la visualizzazione dati predefinita. Quando selezioni **[!UICONTROL Continue]**, è necessario selezionare un’altra visualizzazione dati come predefinita. Seleziona **[!UICONTROL Confirm]** per confermare la selezione. Seleziona **[!UICONTROL Cancel]** per annullare la modifica alla visualizzazione dati predefinita. |

  | Contenitori | Valore |
  |---|---|
  | [!UICONTROL Person container name] | `Person` |
  | [!UICONTROL Session container name] | `Session` |
  | [!UICONTROL Event container name] | `Event` |

  | Calendario | Valore |
  |---|---|
  | [!UICONTROL Time zone] | Fuso orario conforme alla località |
  | [!UICONTROL Calendar type] | Gregoriano |
  | [!UICONTROL First month of the year] | Gennaio |
  | [!UICONTROL First day of the week] | Domenica |


- Nella scheda **Componenti**:
   - Tutte le metriche e le dimensioni che hanno [!UICONTROL (AJO)] aggiunto al nome vengono aggiunti automaticamente come parte di questa configurazione automatica.
   - Alcune delle metriche o dimensioni che sono state aggiunte automaticamente sono basate su campi derivati. Questi campi derivati sono creati in modo specifico per questa integrazione. Ad esempio, la metrica [!UICONTROL Landing Page Clicks (AJO)] è basata sul campo derivato [!UICONTROL Landing Page Clicks].
   - Alcune delle metriche o dimensioni hanno una configurazione aggiuntiva. Ad esempio, [!UICONTROL Spam Complaint (AJO)] ha applicate le impostazioni [!UICONTROL Format] e [!UICONTROL Include Exclude Values].
   - Tutte le metriche e le dimensioni aggiunte automaticamente hanno un’etichetta di contesto denominata `:`*`name_of_metric_or_dimension`*. Ad esempio, la metrica [!UICONTROL Landing Page Clicks (AJO)] ha l’etichetta di contesto `:Landing page clicks (AJO)`.

- Nella scheda **[!UICONTROL Settings]**, non vengono applicati valori di configurazione specifici

>[!IMPORTANT]
>
>La modifica di uno qualsiasi dei valori configurati automaticamente per la connessione e la visualizzazione dati comporta conseguenze per il reporting di AJO, che si basa sull’integrazione di Customer Journey Analytics configurata automaticamente e la utilizza.


## Configurare manualmente una visualizzazione dati da utilizzare con AJO

Le sezioni seguenti descrivono come utilizzare manualmente i dati generati da AJO per eseguire analisi avanzate di Customer Journey Analytics. Questa configurazione manuale è necessaria solo se l&#39;opzione di configurazione [automatica](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) non è sufficiente per le proprie esigenze.

### Inviare dati da AJO a Adobe Experience Platform

Adobe Experience Platform funge da origine dati centrale e da collegamento tra Journey Optimizer e Customer Journey Analytics. Consulta [Introduzione ai set di dati](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) nella guida utente di AJO per visualizzare i passaggi su come inviare dati AJO a Experience Platform come set di dati.

### Creare una connessione in Customer Journey Analytics

Una volta che i dati di Journey Optimizer sono in Adobe Experience Platform, puoi [Creare una connessione](/help/connections/create-connection.md) in base ai set di dati di Journey Optimizer. Oppure puoi aggiungere set di dati di Journey Optimizer a una connessione esistente.

Seleziona e configura i seguenti set di dati:

| Set di dati | Tipo di set di dati | Impostazioni della connessione | Descrizione |
| --- | --- | --- | --- |
| Set di dati evento feedback messaggio AJO | Evento | ID persona: `IdentityMap` | Contiene eventi di consegna dei messaggi, ad esempio “[!UICONTROL Sends]” e “[!UICONTROL Bounces]”. |
| Set di dati evento esperienza di tracciamento e-mail AJO | Evento | ID persona: `IdentityMap` | Contiene eventi di tracciamento e-mail, come “[!UICONTROL Opens]”, “[!UICONTROL Clicks]”, e “[!UICONTROL Unsubscribes]”. |
| Set di dati evento di tracciamento push AJO | Evento | ID persona: `IdentityMap` | Contiene eventi di tracciamento push, come “[!UICONTROL App Launches]”. |
| Eventi passaggio percorso | Evento | ID persona: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Contiene eventi che mostrano quali profili hanno partecipato a ciascun nodo del percorso. |
| Set di dati di entità AJO | Ricerca | Chiave: `_id`<br>Chiave corrispondente: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contiene classificazioni che associano i metadati di percorso e campagna a tutti i dati evento AJO. |

{style="table-layout:auto"}


### Configurare la visualizzazione dati

Dopo aver creato una connessione, puoi creare una o più [Viste dati](/help/data-views/create-dataview.md) per configurare le dimensioni e le metriche desiderate disponibili in Customer Journey Analytics.

>[!NOTE]
>
>Le discrepanze di dati tra AJO e Customer Journey Analytics sono in genere inferiori all’1-2%. È possibile che si verifichino discrepanze maggiori per i dati raccolti nelle ultime due ore. Per attenuare le discrepanze dovute ai tempi di elaborazione, utilizza intervalli di date escludendo “oggi”.


#### Configurare le dimensioni

Per ottenere una parità approssimativa con dimensioni simili in Journey Optimizer, puoi creare le dimensioni seguenti in una visualizzazione dati. Consulta [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati, per informazioni dettagliate sulle opzioni di personalizzazione della dimensione.

| Dimensione | Descrizione | Set di dati | Elemento dello schema | Impostazioni del componente |
| --- | --- | --- | --- | --- |
| Errore di esecuzione azione (AJO) | Condizione di errore che impediva l’esecuzione dell’azione in Percorsi Runtime. | Eventi passaggio percorso | `_experience.journeyOrchestration.`<br/>`stepEvents.actionExecutionError ` | Tipo di componente: dimensione |
| Etichetta azione (AJO) | Il nome visualizzato generato dal cliente dell’elemento con cui l’utente finale ha interagito. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `_experience.decisioning.`<br/>`propositionAction.label` | Tipo di componente: dimensione |
| ID batch (AJO) | GUID creato alla chiamata di ogni nuova istanza batch per un Percorso pianificato o un&#39;azione campagna. Se, ad esempio, un Percorso pianificato o un&#39;azione di campagna viene eseguita alle 08.00 e alle 00.00, esistono due batchInstanceID diversi. | Set di dati evento di tracciamento push di AJO, Set di dati evento feedback messaggi di AJO, Set di dati evento tracciamento e-mail di AJO | ` _experience.customerJourneyManagement.`<br/>`messageExecution.batchInstanceID` | Tipo di componente: dimensione |
| Timestamp istanza batch (AJO) | Il timestamp dell’istanza batch. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | Campi derivati | Tipo di componente: Dimension (campo derivato) |
| ID campagna (AJO) | ID della campagna. | Set di dati di entità AJO | `_experience.customerJourneyManagement.entities.`<br/>`campaign.campaignID` | Tipo di componente: dimensione |
| Nome campagna (AJO) | Nome della campagna. | Set di dati di entità AJO | `_experience.customerJourneyManagement.entities.`<br/>`campaign.name` | Tipo di componente: dimensione |
| ID versione campagna (AJO) | ID versione della campagna. | Set di dati di entità AJO | `_experience.customerJourneyManagement.`<br/>`entities.campaign.campaignVersionID` | Tipo di componente: dimensione |
| Canale (AJO) | Canale a cui devono essere correlati i dati. | Set di dati di entità AJO | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.channel._id` | Tipo di componente: dimensione |
| ID correlazione (AJO) | L’Id Di Correlazione. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `_experience.decisioning.propositions.`<br/>`scopeDetails.correlationID` | Tipo di componente: dimensione |
| Id Criterio Decisione (AJO) | ID del criterio di decisione utilizzato per decidere quali elementi includere nella proposta. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | Campi derivati | Tipo di componente: Dimension (campo derivato) |
| Dominio destinatario e-mail (AJO) | Dominio dell’indirizzo e-mail | Set di dati evento di tracciamento push di AJO, Set di dati evento feedback messaggi di AJO, Set di dati evento tracciamento e-mail di AJO | `_experience.customerJourneyManagement.`<br/>`emailChannelContext.address` | Tipo di componente: dimensione |
| Oggetto e-mail (AJO) | Oggetto e-mail, non personalizzato | Set di dati di entità AJO | `_experience.customerJourneyManagement.entities.`<br/>`channelDetails.email.subject` | Tipo di componente: dimensione |
| ID evento (AJO) | Un identificatore univoco dell’evento della serie temporale. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `_id` | Tipo di componente: Dimension (campo derivato) |
| ID criterio di uscita (AJO) | ID dei criteri di uscita utilizzati per determinare se il percorso deve uscire. | Eventi passaggio percorso | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaID` | Tipo di componente: dimensione |
| Nome criterio di uscita (AJO) | Nome dei criteri di uscita. | Eventi passaggio percorso | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaName` | Tipo di componente: dimensione |
| ID esperimento (AJO) | ID dell’esperimento. | Set di dati di entità AJO | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | Tipo di componente: dimensione |
| Nome esperimento (AJO) | Nome dell’esperimento. | Set di dati di entità AJO | `_experience.customerJourneyManagement.entities.`<br/>`experiment.experimentName` | Tipo di componente: Etichette contesto Dimension: esperimento |
| Errore di recupero (AJO) | Condizione di errore che impediva l’esecuzione del recupero da parte di Percorsi Runtime. | Eventi passaggio percorso | `_experience.journeyOrchestration.`<br/>`stepEvents.fetchError` | Tipo di componente: dimensione |
| Ottimizzato per l’ora di invio (AJO) | È l’esecuzione di un messaggio SendTimeOptimized | Set di dati evento di tracciamento push di AJO, Set di dati evento feedback messaggi di AJO, Set di dati evento tracciamento e-mail di AJO | `_experience.customerJourneyManagement.`<br/>`messageProfile.isSendTimeOptimized` | Tipo di componente: dimensione |
| È un Percorso di test (AJO) | L’evento fa parte di un’esecuzione del percorso di test | Eventi passaggio percorso | `_experience.journeyOrchestration.`<br/>`stepEvents.inTest` | Tipo di componente: dimensione |
| È un messaggio di prova (AJO) | Messaggio inviato come esecuzione del test | Set di dati evento di tracciamento push di AJO, Set di dati evento feedback messaggi di AJO, Set di dati evento tracciamento e-mail di AJO | `_experience.customerJourneyManagement.`<br/>`messageProfile.isTestExecution` | Tipo di componente: dimensione |
| ID elemento (AJO) | ID dell&#39;elemento. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `_experience.decisioning.`<br/>`propositions.items.id` | Tipo di componente: dimensione |
| Nome elemento (AJO) | Nome dell&#39;elemento | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `_experience.decisioning.`<br/>`propositions.items.name` | Tipo di componente: dimensione |
| ID azione percorso | ID azione di percorso, per il quale viene attivato MessageExecution. | Set di dati evento di tracciamento push di AJO, Set di dati evento feedback messaggi di AJO, Set di dati evento tracciamento e-mail di AJO | `_experience.customerJourneyManagement.`<br/>`messageExecution.journeyActionID` | Tipo di componente: dimensione |
| Nome nodo azione percorso (AJO) | Nome del nodo di azione del percorso. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO, set di dati entità di AJO | Campi derivati | Tipo di componente: Dimension (campo derivato) |
| Nome nodo evento percorso (AJO) | Questo valore viene impostato ogni volta che si verifica un segmento o un evento esterno in un percorso. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO, set di dati entità di AJO | Campi derivati | Tipo di componente: Dimension (campo derivato) |
| ID percorso (AJO) | ID del percorso. | Set di dati di entità AJO | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyID` | Tipo di componente: dimensione |
| Nome percorso (AJO) | Nome del percorso. | Set di dati di entità AJO | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyName` | Tipo di componente: dimensione |
| Nome e versione percorso (AJO) | Nome e versione del percorso. | Set di dati di entità AJO | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNameAndVersion` | Tipo di componente: dimensione |
| ID versione percorso (AJO) | ID versione del percorso. | Set di dati di entità AJO | `_experience.customerJourneyManagement.entities.`<br/>`journey.journeyVersionID` | Tipo di componente: dimensione |
| ID pagina di destinazione (AJO) | Identificatore univoco per la pagina di destinazione. | Set di dati evento esperienza di tracciamento e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.landingpage.landingPageID` | Tipo di componente: dimensione |
| Pagina di destinazione Source (AJO) | Origine della pagina di destinazione. | Set di dati evento esperienza di tracciamento e-mail AJO | Campi derivati | Tipo di componente: Dimension (campo derivato) |
| URL collegamento (AJO) | URL su cui l’utente ha fatto clic. | Set di dati evento esperienza di tracciamento e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.urlID` | Tipo di componente: dimensione |

{style="table-layout:auto"}

#### Configurare le metriche nella visualizzazione dati

Per ottenere una parità approssimativa con metriche simili in Journey Optimizer, in una visualizzazione dati puoi creare le metriche seguenti. Vedi [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati per informazioni sulle opzioni di personalizzazione delle metriche.

| Metrica | Descrizione | Set di dati | Elemento dello schema | Impostazioni del componente |
| --- | --- | --- | --- | --- |
| Installazioni app (AJO) | Numero di installazioni dell’app | Set di dati evento di tracciamento push AJO | `application.installs.value` | Tipo di componente: metrica |
| Avvii di app (AJO) | Numero di volte in cui l’app mobile viene avviata | Set di dati evento di tracciamento push AJO | `application.launches.value` | Tipo di componente: metrica |
| Mancati Recapiti Per Canali In Uscita (AJO) | Numero totale di messaggi non recapitati tra i canali in uscita | Set di dati evento feedback messaggio AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Tipo di componente: metrica |
| Clic (AJO) | Numero totale di clic su tutti i canali | Set di dati evento di esperienza di tracciamento push di AJO, eventi dei passaggi del Percorso, set di dati evento di tracciamento e-mail di AJO, set di dati evento di feedback dei messaggi di AJO | Campi derivati | Tipo di componente: metrica (campo derivato) |
| Numero di offerte di fallback (AJO) | Numero di offerte di fallback. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `_experience.decisioning.propositions.items.`<br/>`itemSelection.selectionDetail.selectionType` | Tipo di componente: metrica |
| Numero di offerte (AJO) | Numero di offerte. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | ` _experience.decisioning.`<br/>`propositions.items.id` | Tipo di componente: metrica |
| Metrica di deduplicazione (AJO) | Dedup metric | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `_id` | Tipo di componente: metrica |
| Consegnato (AJO) | Numero totale di messaggi consegnati. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | Campi derivati | Tipo di componente: metrica (campo derivato) |
| Ignorato (AJO) | Conta ogni volta che il messaggio inApp viene chiuso dall’SDK di Adobe, indipendentemente dall’azione scelta dall’utente finale per chiuderlo. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Tipo di componente: metrica |
| Display (AJO) | Questo conteggio visualizza i messaggi di AJO. Ciò include le aperture e-mail, le visualizzazioni web e le visualizzazioni in-app. Le piattaforme mobili non segnalano la visualizzazione di SMS e messaggi push, pertanto non sono conteggiate. | Set di dati evento di esperienza di tracciamento push di AJO, eventi dei passaggi del Percorso, set di dati evento di tracciamento e-mail di AJO, set di dati evento di feedback dei messaggi di AJO | Campi derivati | Tipo di componente: metrica (campo derivato) |
| Aperture e-mail (AJO) | Numero totale di aperture e-mail | Set di dati evento esperienza di tracciamento e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo di componente: metrica |
| Clic in entrata (AJO) | Numero totale di clic tra i canali in entrata | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `_experience.decisioning.`<br/>`propositionEventType.interact` | Tipo di componente: metrica |
| Notifiche in entrata ignorate (AJO) | Numero totale di ignoramenti tra i canali in entrata | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Tipo di componente: metrica |
| Impression in entrata (AJO) | Numero totale di impression tra i canali in entrata | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo di componente: metrica |
| Fine percorso (AJO) | True se il passaggio corrente ha portato alla fine di un&#39;istanza del percorso. L’ultimo passaggio in un percorso per un determinato profilo è stato eseguito correttamente. | Eventi passaggio percorso | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | Tipo di componente: metrica |
| Immissioni percorso (AJO) | True se l&#39;evento del passaggio è stato un evento di ingresso percorso per un profilo. | Eventi passaggio percorso | Campi derivati | Tipo di componente: metrica (campo derivato) |
| Uscite dal percorso (AJO) | True se il passaggio corrente ha portato alla fine di un&#39;istanza del percorso. Questo è l’ultimo passaggio di un percorso per un determinato profilo eseguito correttamente. | Eventi passaggio percorso | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | Tipo di componente: metrica |
| Errori di percorso (AJO) | Fornisce lo stato corrente del passaggio che ha completato l’esecuzione. Valori possibili: `Transitions` (il passaggio successivo si verificherà in una transizione di evento), `EndStep` (l&#39;ultimo passaggio in questa istanza di percorso è stato eseguito), `Error` (questo passaggio ha rilevato una condizione di errore, terminando l&#39;istanza di percorso corrente), `TimedOut` (il passaggio corrente è terminato a causa di un timeout in un recupero o in un&#39;azione). | Eventi passaggio percorso | `_experience.journeyOrchestration.`<br/>`stepEvents.stepStatus` | Tipo di componente: metrica |
| Clic sulla pagina di destinazione (AJO) | Numero totale di clic sulla pagina di destinazione. | Set di dati evento esperienza di tracciamento e-mail AJO | Campi derivati | Tipo di componente: metrica (campo derivato) |
| Conversioni delle pagine di destinazione (AJO) | Numero totale di conversioni nella pagina di destinazione. | Set di dati evento esperienza di tracciamento e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo di componente: metrica |
| Visualizzazioni pagina di destinazione (AJO) | Numero totale di visualizzazioni nella pagina di destinazione. | Set di dati evento esperienza di tracciamento e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo di componente: metrica |
| Entrate nodo (AJO) | True se l&#39;evento del passaggio è stato un evento di ingresso al nodo per un profilo. | Eventi passaggio percorso | Campi derivati | Tipo di componente: metrica (campo derivato) |
| Clic in uscita (AJO) | Numero totale di clic tra i canali in uscita | Set di dati evento esperienza di tracciamento e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo di componente: metrica |
| Errori in uscita (AJO) | Numero totale di messaggi con errori tra i canali in uscita | Set di dati evento feedback messaggio AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Tipo di componente: metrica |
| Esclusioni in uscita (AJO) | Numero totale di eventi di esclusione tra i canali in uscita | Set di dati evento feedback messaggio AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Tipo di componente: metrica |
| Invii in uscita (AJO) | Numero totale di messaggi inviati tra canali in uscita | Set di dati evento feedback messaggio AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Tipo di componente: metrica |
| Azioni personalizzate push (AJO) | Numero totale di azioni personalizzate nell’interazione push. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `eventType` | Tipo di componente: metrica |
| Interazioni push (AJO) | Numero di volte in cui l’app mobile viene avviata a causa di un’interazione con un messaggio push diretto | Set di dati evento di tracciamento push AJO | `application.launches.value` | Tipo di componente: metrica |
| Invii (AJO) | Numero totale di messaggi inviati su tutti i canali | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | Campi derivati | Tipo di componente: metrica (campo derivato) |
| Messaggi SMS in entrata (AJO) | Risposta SMS in entrata. Ad esempio, stop, start, subscribe, ecc. | Set di dati evento di tracciamento push di AJO, Set di dati evento feedback messaggi di AJO, Set di dati evento tracciamento e-mail di AJO | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.inboundMessage` | Tipo di componente: metrica |
| Reclamo spam (AJO) | Numero totale di segnalazioni di posta indesiderata | Set di dati evento esperienza di tracciamento e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo di componente: metrica |
| Aggiunte a elenco iscrizioni (AJO) | Numero totale di aggiunte all’elenco di iscrizioni. | Set di dati evento esperienza di tracciamento e-mail AJO | Campi derivati | Tipo di componente: metrica (campo derivato) |
| Rimozioni elenco iscrizioni (AJO) | Numero totale di rimozioni dall’elenco iscrizioni. | Set di dati evento esperienza di tracciamento e-mail AJO | Campi derivati | Tipo di componente: metrica (campo derivato) |
| Target (AJO) | Questo conteggio del numero di volte in cui una proposta è stata indirizzata a una persona. Numero di volte in cui una proposta è stata considerata per la visualizzazione a una persona. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | Campi derivati | Tipo di componente: metrica (campo derivato) |
| Attivato (AJO) | La proposta è stata scelta per essere visualizzata dall’SDK di Adobe. Altri fattori possono impedirne l’effettiva visualizzazione. | Set di dati evento di tracciamento push di AJO, eventi passaggio Percorso, set di dati evento di feedback dei messaggi di AJO, set di dati evento di tracciamento e-mail di AJO | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo di componente: metrica |
| Visitatori univoci in esperimento (AJO) | I visitatori univoci nell’esperimento | Set di dati di entità AJO | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | Tipo di componente: metrica |
| Annullamenti iscrizione (AJO) | Numero totale di annullamenti di abbonamenti | Set di dati evento esperienza di tracciamento e-mail AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo di componente: metrica |

{style="table-layout:auto"}
