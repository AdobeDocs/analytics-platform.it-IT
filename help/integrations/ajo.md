---
title: Integrare Adobe Journey Optimizer con Customer Journey Analytics
description: Inserire i dati generati da Adobe Journey Optimizer e analizzarli utilizzando Analysis Workspace all’interno di Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '855'
ht-degree: 100%

---

# Integrare Adobe Journey Optimizer con Adobe Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=it) ti consente di fornire esperienze connesse, contestuali e personalizzate. Aiuta i tuoi clienti a prendere familiarità con il passaggio successivo nel loro percorso.

Puoi importare i dati generati da Journey Optimizer per eseguire analisi avanzate in Customer Journey Analytics eseguendo i seguenti passaggi:

## Inviare dati da Journey Optimizer ad Adobe Experience Platform

Adobe Experience Platform funge da origine dati centrale e da collegamento tra Journey Optimizer e Customer Journey Analytics. Consulta [Introduzione ai set di dati](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=it) nella guida utente di Journey Optimizer per i passaggi su come inviare dati Journey Optimizer a Platform come set di dati.

## Creare una connessione in Customer Journey Analytics

Una volta che i dati di Journey Optimizer sono in Adobe Experience Platform, puoi [Creare una connessione](/help/connections/create-connection.md) in base ai set di dati di Journey Optimizer. Oppure puoi aggiungere set di dati di Journey Optimizer a una connessione esistente.

Seleziona e configura i seguenti set di dati:

| Set di dati | Tipo di set di dati | Impostazioni della connessione | Descrizione |
| --- | --- | --- | --- |
| Set di dati evento feedback messaggio AJO | Evento | ID persona: `IdentityMap` | Contiene eventi di consegna dei messaggi, ad esempio “[!UICONTROL Sends]” e “[!UICONTROL Bounces]”. |
| Set di dati evento esperienza di tracciamento e-mail AJO | Evento | ID persona: `IdentityMap` | Contiene eventi di tracciamento e-mail, come “[!UICONTROL Opens]”, “[!UICONTROL Clicks]”, e “[!UICONTROL Unsubscribes]”. |
| Set di dati evento di tracciamento push AJO | Evento | ID persona: `IdentityMap` | Contiene eventi di tracciamento push, come “[!UICONTROL App Launches]”. |
| Eventi passaggio percorso | Evento | ID persona: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Contiene eventi che mostrano quali profili hanno partecipato a ciascun nodo del percorso. |
| Set di dati di entità AJO | Ricerca | Chiave: `_id`<br>Chiave corrispondente: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contiene classificazioni che associano i metadati di percorso e campagna a tutti i dati evento Adobe Journey Optimizer. |

{style="table-layout:auto"}


## Configurare la vista dati in modo da adattarla alle dimensioni e alle metriche di Journey Optimizer

Dopo aver creato una connessione, puoi creare una o più [Viste dati](/help/data-views/create-dataview.md) per configurare le dimensioni e le metriche desiderate disponibili in Customer Journey Analytics.

>[!NOTE]
>
>Le discrepanze di dati tra Adobe Journey Optimizer e Customer Journey Analytics sono in genere inferiori all’1-2%. È possibile che si verifichino discrepanze maggiori per i dati raccolti nelle ultime due ore. Per attenuare le discrepanze dovute ai tempi di elaborazione, utilizza intervalli di date escludendo “oggi”.


### Configurare dimensioni nella visualizzazione dati

Per ottenere una parità approssimativa con dimensioni simili in Journey Optimizer, puoi creare le dimensioni seguenti in una visualizzazione dati. Vedi [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati per informazioni sulle opzioni di personalizzazione della dimensione.

| Dimensione | Elemento dello schema | Impostazioni del componente |
| --- | --- | --- |
| Nome del percorso | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo di componente: dimensione |
| Nome e versione del percorso | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Tipo di componente: dimensione |
| Nome del nodo del percorso | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo di componente: dimensione |
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

### Configurare le metriche nella visualizzazione dati

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
| Invii Edge | Il numero di volte in cui la rete Edge invia un messaggio all’SDK Web o Mobile | Utilizzare l’elemento stringa dello schema `_experience.decisioning.propositionEventType.send` |
| Visualizzazioni in entrata | Numero di volte in cui un messaggio Web o InApp viene mostrato all’utente | Utilizzare l’elemento stringa dello schema `_experience.decisioning.propositionEventType.display` |
| Clic in entrata | Numero di clic sui messaggi Web o InApp | Utilizzare l’elemento stringa dello schema `_experience.decisioning.propositionEventType.interact` |
| Trigger InApp | Il numero di volte che il motore decisionale ha suggerito di visualizzare il messaggio. Mobile SDK potrebbe ignorare la decisione di ridurre il numero di visualizzazioni effettive. | Utilizzare l’elemento stringa dello schema `_experience.decisioning.propositionEventType.trigger` |
| Eliminazioni InApp | Il numero di volte in cui un messaggio InApp viene rimosso dall’interfaccia utente dall’SDK | Utilizzare l’elemento stringa dello schema `_experience.decisioning.propositionEventType.dismiss` |

{style="table-layout:auto"}

### Configurare le metriche calcolate in Analysis Workspace

Dopo aver configurato le dimensioni e le metriche desiderate per il set di dati di Journey Optimizer, puoi anche configurare le [Metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md) per ottenere ulteriori informazioni su tali dati. Queste metriche calcolate si basano sulle metriche precedenti create nella Gestione visualizzazione dati.

| Metrica calcolata | Descrizione | Formula |
| --- | --- | --- |
| Messaggi inviati | Numero totale di messaggi inviati. Include i messaggi con successo o non riusciti. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Messaggi consegnati | Numero di e-mail consegnate ai clienti. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
