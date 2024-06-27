---
title: Integrare Adobe Journey Optimizer con Customer Journey Analytics
description: Inserire i dati generati da Adobe Journey Optimizer e analizzarli utilizzando Analysis Workspace all’interno di Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 5185c28c7a2cf1a0690e783633bbfbf851a1dcd1
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 55%

---

# Integrare Journey Optimizer con Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/get-started/get-started) ti consente di fornire esperienze connesse, contestuali e personalizzate. Aiuta i tuoi clienti a prendere familiarità con il passaggio successivo nel loro percorso.

Puoi configurare i dati generati da Journey Optimizer per eseguire analisi avanzate in Customer Journey Analytics. Puoi configurare automaticamente questa integrazione. Se necessario, puoi effettuare personalizzazioni manuali aggiuntive ai set di dati, alle dimensioni o alle metriche disponibili nella connessione o nelle visualizzazioni dati.

## Configurare automaticamente l’integrazione di Journey Optimizer

{{release-limited-testing-section}}

Journey Optimizer supporta l’utilizzo del Customer Journey Analytics come motore di reporting. Consulta [Introduzione alla nuova interfaccia di reporting](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja) nella documentazione di Journey Optimizer.

Dopo aver abilitato la generazione di rapporti di Customer Journey Analytics per Journey Optimizer, viene automaticamente [connessione](/help/connections/overview.md) e [visualizzazione dati](/help/data-views/data-views.md) vengono create per la sandbox specifica.

### Connessione

La connessione ha il nome **[!UICONTROL AJO Enabled Connection (*nome sandbox *)]**e ha i seguenti valori predefiniti per la configurazione e i set di dati:

| **Impostazioni della connessione** | Valore |
|---|---| 
| [!UICONTROL Connection name] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL Connection description] | [!UICONTROL *Descrivi qui la tua connessione*] |
| [!UICONTROL Tags] | [!UICONTROL *Seleziona tag*] |


| **Impostazioni dati** | Valore |
|---|---| 
| [!UICONTROL Enable rolling data window] | Attivato. [!UICONTROL Selected number of months] `13`. |
| [!UICONTROL Sandbox] | [!UICONTROL *nome della sandbox*] (disattivato; non è possibile modificare questa impostazione). |
| [!UICONTROL Average number of daily events] | meno di 1 milione (disabilitato; non è possibile modificare questa impostazione). |


| Nome del set di dati | Schema | Tipo di set di dati | Tipo di origine dati | ID persona | Chiave | Chiave corrispondente | Importare nuovi dati | Recupero dati |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL AJO Entity Dataset] | [!UICONTROL AJO Entity Record Schema] | [!UICONTROL Lookup] | [!UICONTROL Other] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![Stato verde](assets/../../connections/assets/status-green.svg) On | ![Stato grigio](assets/../../connections/assets/status-gray.svg) Disattivato |
| [!UICONTROL Journey Step Events] | [!UICONTROL Journey Step Event schema for Journey Orchestration] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL  IdentityMap(\<primary\>)] | - | - | ![Stato verde](assets/../../connections/assets/status-green.svg) On | ![Stato grigio](assets/../../connections/assets/status-gray.svg) Disattivato |
| [!UICONTROL AJO Email Tracking Experience Event Dataset] | [!UICONTROL AJO Email Tracking Experience Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Stato verde](assets/../../connections/assets/status-green.svg) On | ![Stato grigio](assets/../../connections/assets/status-gray.svg) Disattivato |
| [!UICONTROL AJO Email Tracking Experience Event Dataset] | [!UICONTROL AJO Email Tracking Experience Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Stato verde](assets/../../connections/assets/status-green.svg) On | ![Stato grigio](assets/../../connections/assets/status-gray.svg) Disattivato |
| [!UICONTROL AJO Message Feedback Event Dataset] | [!UICONTROL AJO Message Feedback Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Stato verde](assets/../../connections/assets/status-green.svg) On | ![Stato grigio](assets/../../connections/assets/status-gray.svg) Disattivato |
| [!UICONTROL AJO Push Tracking Experience Event Dataset] | [!UICONTROL AJO Push Tracking Experience Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Stato verde](assets/../../connections/assets/status-green.svg) On | ![Stato grigio](assets/../../connections/assets/status-gray.svg) Disattivato |


### Visualizzazione dati

La visualizzazione dati ha il nome **Abilita visualizzazione dati di AJO (*nome sandbox*)**.

- In **[!UICONTROL Configure]** , i seguenti valori sono configurati come predefiniti.

  | Impostazioni | Valore |
  |---|---|
  | [!UICONTROL Connection] | Connessione abilitata per AJO (*nome sandbox*) |
  | [!UICONTROL Name] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL External ID] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` (derivato dal nome) |
  | [!UICONTROL Description] | `undefined` |

  {style="table-layout:fixed"}

  | Compatibilità | Valore |
  |---|---|
  | [!UICONTROL Set as default data view in Adobe Journey Optimizer] | Abilitato (impostazione predefinita).<br/><br/>Questa opzione di configurazione consente di designare una visualizzazione dati da utilizzare con Journey Optimizer, senza la necessità di eseguire la configurazione manuale. Per informazioni su come abilitare questa opzione di configurazione (se non è già abilitata per impostazione predefinita), vedere [Compatibilità](/help/data-views/create-dataview.md#compatibility) sezione in [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md). <br/><br/>Quando si disattiva l&#39;opzione, viene visualizzata una finestra di dialogo in cui viene richiesto se si desidera continuare a modificare la visualizzazione dati predefinita. Quando selezioni **[!UICONTROL Continue]**, è necessario selezionare un’altra visualizzazione dati come predefinita. Seleziona **[!UICONTROL Confirm]** per confermare la selezione. Seleziona **[!UICONTROL Cancel]** per annullare la modifica della visualizzazione dati predefinita. |

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


- In **Componenti** scheda:
   - Tutte le metriche e le dimensioni che hanno [!UICONTROL (AJO)] aggiunti al nome vengono aggiunti automaticamente come parte di questa configurazione automatica.
   - Alcune delle metriche o dimensioni che sono state aggiunte automaticamente si basano su campi derivati. Questi campi derivati sono creati in modo specifico per questa integrazione. Ad esempio, la metrica [!UICONTROL Landing Page Clicks (AJO)] è basato su [!UICONTROL Landing Page Clicks] campo derivato.
   - Alcune delle metriche o dimensioni hanno una configurazione aggiuntiva. Ad esempio: [!UICONTROL Spam Complaint (AJO)] ha [!UICONTROL Format] e [!UICONTROL Include Exclude Values] impostazioni applicate.
   - Tutte le metriche e le dimensioni aggiunte automaticamente hanno un’etichetta di contesto denominata `:`*`name_of_metric_or_dimension`*. Ad esempio, il [!UICONTROL Landing Page Clicks (AJO)] la metrica ha l’etichetta di contesto `: Landing page clicks (AJO)`.

- In **[!UICONTROL Settings]** , non vengono applicati valori di configurazione specifici

>[!IMPORTANT]
>
>La modifica di uno qualsiasi dei valori configurati automaticamente per la connessione e la visualizzazione dati ha conseguenze per il reporting di Journey Optimizer che si basa sull’integrazione del Customer Journey Analytics configurata automaticamente e la utilizza.


## Configurare manualmente una visualizzazione dati da utilizzare con Journey Optimizer

Le sezioni seguenti descrivono come utilizzare manualmente i dati generati da Journey Optimizer per eseguire analisi avanzate di Customer Journey Analytics. Ciò è necessario solo se [opzione di configurazione automatica](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) non è sufficiente per le tue esigenze.

### Invia dati da Journey Optimizer a Experience Platform

Adobe Experience Platform funge da origine dati centrale e da collegamento tra Journey Optimizer e Customer Journey Analytics. Consulta [Introduzione ai set di dati](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) nella guida utente di Journey Optimizer per i passaggi su come inviare dati Journey Optimizer ad Experience Platform come set di dati.

### Creare una connessione in Customer Journey Analytics

Una volta che i dati di Journey Optimizer sono in Adobe Experience Platform, puoi [Creare una connessione](/help/connections/create-connection.md) in base ai set di dati di Journey Optimizer. Oppure puoi aggiungere set di dati di Journey Optimizer a una connessione esistente.

Seleziona e configura i seguenti set di dati:

| Set di dati | Tipo di set di dati | Impostazioni della connessione | Descrizione |
| --- | --- | --- | --- |
| Set di dati evento feedback messaggio AJO | Evento | ID persona: `IdentityMap` | Contiene eventi di consegna dei messaggi, ad esempio “[!UICONTROL Sends]” e “[!UICONTROL Bounces]”. |
| Set di dati evento esperienza di tracciamento e-mail AJO | Evento | ID persona: `IdentityMap` | Contiene eventi di tracciamento e-mail, come “[!UICONTROL Opens]”, “[!UICONTROL Clicks]”, e “[!UICONTROL Unsubscribes]”. |
| Set di dati evento di tracciamento push AJO | Evento | ID persona: `IdentityMap` | Contiene eventi di tracciamento push, come “[!UICONTROL App Launches]”. |
| Eventi passaggio percorso | Evento | ID persona: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Contiene eventi che mostrano quali profili hanno partecipato a ciascun nodo del percorso. |
| Set di dati di entità AJO | Ricerca | Chiave: `_id`<br>Chiave corrispondente: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contiene classificazioni che associano i metadati di Percorsi e Campaign a tutti i dati evento Journey Optimizer. |

{style="table-layout:auto"}


### Configurare la vista dati in modo da adattarla alle dimensioni e alle metriche di Journey Optimizer

Dopo aver creato una connessione, puoi creare una o più [Viste dati](/help/data-views/create-dataview.md) per configurare le dimensioni e le metriche desiderate disponibili in Customer Journey Analytics.

>[!NOTE]
>
>Le discrepanze di dati tra Journey Optimizer e il Customer Journey Analytics sono in genere inferiori all’1-2%. È possibile che si verifichino discrepanze maggiori per i dati raccolti nelle ultime due ore. Per attenuare le discrepanze dovute ai tempi di elaborazione, utilizza intervalli di date escludendo “oggi”.


#### Configurare dimensioni nella visualizzazione dati

Per ottenere una parità approssimativa con dimensioni simili in Journey Optimizer, puoi creare le dimensioni seguenti in una visualizzazione dati. Consulta [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Data View Manager per informazioni dettagliate sulle opzioni di personalizzazione delle dimensioni.

| Dimensione | Elemento dello schema | Impostazioni del componente |
| --- | --- | --- |
| Nome del percorso | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo di componente: dimensione |
| Nome e versione del percorso | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Tipo di componente: dimensione |
| Nome del nodo del percorso | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeName` | Tipo di componente: dimensione |
| Tipo di nodo del percorso | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | Tipo di componente: dimensione |
| Nome della campagna | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | Tipo di componente: dimensione |
| Canale | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | Tipo di componente: dimensione |
| Titolo push | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | Tipo di componente: dimensione |
| Oggetto dell’e-mail | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | Tipo di componente: dimensione |
| Etichetta del collegamento | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | Tipo di componente: dimensione |
| Nome dell’esperimento | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | Tipo di componente: dimensione<br>Etichette di contesto: esperimento Sperimentazione |
| Nome del trattamento | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | Tipo di componente: dimensione<br>Etichette di contesto: variante Sperimentazione |
| Motivo errore di consegna delle e-mail | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | Tipo di componente: dimensione |
| Motivo esclusione della consegna delle e-mail | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | Tipo di componente: dimensione |
| Etichetta elemento | `_experience.decisioning.propositionAction.label` | Tipo di componente: dimensione |

{style="table-layout:auto"}

#### Configurare le metriche nella visualizzazione dati

Per ottenere una parità approssimativa con metriche simili in Journey Optimizer, in una visualizzazione dati puoi creare le metriche seguenti. Vedi [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati per informazioni sulle opzioni di personalizzazione delle metriche.

| Metrica | Descrizione | Elemento dello schema | Impostazioni del componente |
| --- | --- | --- | --- |
| Messaggi non recapitati | Numero di messaggi non recapitati, compresi i mancati recapiti immediati e dopo la consegna. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo di componente: metrica<br>Includi valori di esclusione: se sono soddisfatti i criteri<br>È uguale a: `bounce`, è uguale a: `denylist` |
| Mancati recapiti dopo la consegna | Alcuni servizi e-mail segnalano le e-mail consegnate, e successivamente ne segnalano il mancato recapito. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | Tipo di componente: metrica<br>Includi valori di esclusione: è uguale a `async` |
| Clic su e-mail | Numero di clic all’interno dei messaggi. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo di componente: metrica<br>Includi valori di esclusione: è uguale a `click` |
| E-mail aperte | Numero di messaggi aperti. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo di componente: metrica<br>Includi valori di esclusione: è uguale a `open` |
| Errori | Numero di messaggi che hanno generato un errore | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo di componente: metrica<br>Includi valori di esclusione: è uguale a `error` |
| Messaggi esclusi | Il numero di messaggi esclusi. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo di componente: metrica<br>Includi valori di esclusione: è uguale a `exclude` |
| Invii | Numero di messaggi accettati da provider e-mail. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo di componente: metrica<br>Includi valori di esclusione: è uguale a `sent` |
| Segnalazioni di spam | Numero di segnalazioni di spam. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo di componente: metrica<br>Valori da includere/escludere: è uguale a `spam_complaint` |
| Abbonamenti annullati | Numero di abbonamenti annullati. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo di componente: metrica<br>Includi valori di esclusione: è uguale a `unsubscribe` |
| Invii Edge | Il numero di volte in cui la rete Edge invia un messaggio all’SDK Web o Mobile | Utilizzare l’elemento stringa dello schema `_experience.decisioning.propositionEventType.send` | |
| Visualizzazioni in entrata | Numero di volte in cui un messaggio Web o InApp viene mostrato all’utente | Utilizzare l’elemento stringa dello schema `_experience.decisioning.propositionEventType.display` | |
| Clic in entrata | Numero di clic sui messaggi Web o InApp | Utilizzare l’elemento stringa dello schema `_experience.decisioning.propositionEventType.interact` | |
| Trigger InApp | Il numero di volte che il motore decisionale ha suggerito di visualizzare il messaggio. L’SDK di Mobile potrebbe ignorare la decisione, riducendo il numero di visualizzazioni effettive. | Utilizzare l’elemento stringa dello schema `_experience.decisioning.propositionEventType.trigger` | |
| Eliminazioni InApp | Il numero di volte in cui un messaggio InApp viene rimosso dall’interfaccia utente dall’SDK | Utilizzare l’elemento stringa dello schema `_experience.decisioning.propositionEventType.dismiss` | |

{style="table-layout:auto"}

#### Configurare le metriche calcolate in Analysis Workspace

Dopo aver configurato le dimensioni e le metriche desiderate per il set di dati di Journey Optimizer, puoi anche configurare le [Metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md) per ottenere ulteriori informazioni su tali dati. Queste metriche calcolate si basano sulle metriche precedenti create nella Gestione visualizzazione dati.

| Metrica calcolata | Descrizione | Formula |
| --- | --- | --- |
| Messaggi inviati | Numero totale di messaggi inviati. Include i messaggi con successo o non riusciti. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Messaggi consegnati | Numero di e-mail consegnate ai clienti. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
