---
title: Integrare Adobe Journey Optimizer (AJO) con Customer Journey Analytics (CJA)
description: Inserire i dati generati da AJO e analizzarli utilizzando Analysis Workspace all’interno di CJA.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
source-git-commit: 9aed4e724c564272071b96c037f4eb0e82572e6f
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 52%

---

# Integrare Adobe Journey Optimizer con Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=it) ti consente di fornire esperienze connesse, contestuali e personalizzate. Aiuta i tuoi clienti a prendere familiarità con il passaggio successivo nel loro percorso.

Puoi importare i dati generati da Journey Optimizer per eseguire analisi avanzate in Customer Journey Analytics eseguendo i seguenti passaggi:

## Inviare dati da Journey Optimizer ad Adobe Experience Platform

Adobe Experience Platform funge da origine dati centrale e da collegamento tra Journey Optimizer e Customer Journey Analytics. Consulta [Introduzione ai set di dati](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=it) nella guida utente di Journey Optimizer per i passaggi su come inviare dati Journey Optimizer a Platform come set di dati.

## Creare una connessione in Customer Journey Analytics

Una volta che i dati di Journey Optimizer sono in Adobe Experience Platform, puoi [Creare una connessione](/help/connections/create-connection.md) in base al set di dati di Journey Optimizer. Selezionare il set di dati inviato a Platform.

## Configurare la vista dati in modo da adattarla alle dimensioni e alle metriche di Journey Optimizer

Dopo aver creato una connessione, puoi creare una o più [Viste dati](/help/data-views/create-dataview.md) per configurare le dimensioni e le metriche desiderate disponibili in Customer Journey Analytics.

>!![NOTE]
Le discrepanze di dati tra AJO e CJA sono in genere inferiori all’1-2%. Sono possibili discrepanze maggiori per i dati raccolti nelle ultime due ore. Per attenuare le discrepanze dovute ai tempi di elaborazione, utilizza intervalli di date escludendo “oggi”.

### Configurare dimensioni nella visualizzazione dati

Puoi creare le seguenti dimensioni in una visualizzazione dati per ottenere una parità approssimativa con dimensioni simili in Journey Optimizer. Vedi [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati per informazioni sulle opzioni di personalizzazione delle dimensioni.

| Dimensione | Elemento schema | Impostazioni del componente |
| --- | --- | --- |
| Nome percorso | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo di componente: Dimension |
| Nome e versione del percorso | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Tipo di componente: Dimension |
| Nome nodo percorso | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo di componente: Dimension |
| Tipo di nodo percorso | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | Tipo di componente: Dimension |
| Nome campagna | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | Tipo di componente: Dimension |
| Canale | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | Tipo di componente: Dimension |
| Titolo push | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | Tipo di componente: Dimension |
| Oggetto e-mail | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | Tipo di componente: Dimension |
| Etichetta collegamento | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | Tipo di componente: Dimension |
| Nome esperimento | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | Tipo di componente: Dimension<br>Etichette contestuali: Sperimentazione |
| Nome del trattamento | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | Tipo di componente: Dimension<br>Etichette contestuali: Variante sperimentale |
| Motivo dell’errore di consegna e-mail | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | Tipo di componente: Dimension |
| Motivo dell’esclusione della consegna e-mail | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | Tipo di componente: Dimension |

{style=&quot;table-layout:auto&quot;}

### Configurare le metriche nella visualizzazione dati

Per ottenere una parità approssimativa con metriche simili in Journey Optimizer, in una visualizzazione dati puoi creare le metriche seguenti. Vedi [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Data View Manager per informazioni dettagliate sulle opzioni di personalizzazione delle metriche.

| Metrica | Descrizione | Elemento schema | Impostazioni del componente |
| --- | --- | --- | --- |
| Messaggi non recapitati | Numero di messaggi non recapitati, compresi i rimbalzi immediati e i mancati recapiti dopo la consegna. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo di componente: Metrica<br>Includi valori di esclusione: Se sono soddisfatti dei criteri<br>È Uguale a: `bounce`, È Uguale A: `denylist` |
| Rimbalzi dopo la consegna | Alcuni servizi e-mail segnalano le e-mail inviate, quindi rimbalzarle in un secondo momento. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `async` |
| Clic su e-mail | Numero di clic all’interno dei messaggi. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `click` |
| Aperture e-mail | il numero di messaggi aperti. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `open` |
| Errori | Numero di messaggi che hanno generato un errore. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `error` |
| Messaggi esclusi | Il numero di messaggi esclusi. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `exclude` |
| Invio | Il numero di messaggi accettati dai provider di posta elettronica. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `sent` |
| Lamentele da spam | Numero di segnalazioni di spam. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `spam_complaint` |
| Abbonamenti annullati | Numero di abbonamenti annullati. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `unsubscribe` |

{style=&quot;table-layout:auto&quot;}

### Configurare le metriche calcolate in Analysis Workspace

Dopo aver configurato le dimensioni e le metriche desiderate per il set di dati di Journey Optimizer, puoi anche configurare le [Metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md) per ottenere ulteriori informazioni su tali dati. Queste metriche calcolate si basano sulle metriche precedenti create nella Gestione visualizzazione dati.

| Metrica calcolata | Descrizione | Formula |
| --- | --- | --- |
| Messaggi inviati | Numero totale di messaggi inviati. Include i messaggi con esito positivo o negativo. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Messaggi consegnati | Il numero di e-mail consegnate ai clienti. | `[Sends] - [Bounces After Delivery]` |

{style=&quot;table-layout:auto&quot;}
