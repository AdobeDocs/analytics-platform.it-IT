---
title: Integrare Adobe Journey Optimizer con Customer Journey Analytics
description: Inserire i dati generati da AJO e analizzarli utilizzando Analysis Workspace all’interno di CJA.
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: ht
source-wordcount: '664'
ht-degree: 100%

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

Per ottenere una parità approssimativa con metriche simili in Journey Optimizer, in una visualizzazione dati puoi creare le metriche seguenti. Consulta [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati per informazioni su come personalizzare dimensioni e metriche.

| Metrica | Descrizione | Impostazioni della visualizzazione dati |
| --- | --- | --- |
| Messaggi non recapitati | Numero di messaggi non recapitati | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` con le seguenti impostazioni:<br>Tipo di componente: metrica<br>Includere valori di esclusione: se sono soddisfatti i criteri<br>È uguale a: `bounce`<br>È uguale a: `denylist` |
| Errori | Numero di messaggi che hanno generato un errore | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` con le seguenti impostazioni:<br>Tipo di componente: metrica<br>Includere valori di esclusione: è uguale a `error` |
| Messaggi esclusi | Il numero di messaggi esclusi | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` con le seguenti impostazioni:<br>Tipo di componente: metrica<br>Includere valori di esclusione: è uguale a `exclude` |
| Abbonamenti annullati | Numero di abbonamenti annullati | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageInteraction.interactionType` con le seguenti impostazioni:<br>Tipo di componente: metrica<br>Includere valori di esclusione: è uguale a `unsubscribe` |
| Clic | Numero di clic all’interno dei messaggi | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageInteraction.interactionType` con le seguenti impostazioni:<br>Tipo di componente: metrica<br>Includere valori di esclusione: è uguale a `click` |
| Messaggi aperti | il numero di messaggi aperti | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageInteraction.interactionType` con le seguenti impostazioni:<br>Tipo di componente: metrica<br>Includere valori di esclusione: è uguale a `open` |
| Segnalazioni di spam | Numero di segnalazioni di spam | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageInteraction.interactionType` con le seguenti impostazioni:<br>Tipo di componente: metrica<br>Includere valori di esclusione: è uguale a `spam_complaint` |
| Messaggi inviati correttamente | Numero di messaggi inviati correttamente | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` con le seguenti impostazioni:<br>Tipo di componente: metrica<br>Includere valori di esclusione: è uguale a `sent` |
| Errori di sincronizzazione | Numero totale di messaggi non sincronizzati | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` con le seguenti impostazioni:<br>Tipo di componente: metrica<br>Includere valori di esclusione: è uguale a `sync` |

{style=&quot;table-layout:auto&quot;}

## Configurare le metriche calcolate utilizzando le metriche di Journey Optimizer

Dopo aver configurato le dimensioni e le metriche desiderate per il set di dati di Journey Optimizer, puoi anche configurare le [Metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md) per ottenere ulteriori informazioni su tali dati. Queste metriche calcolate si basano sulle metriche precedenti create nella Gestione visualizzazione dati.

| Metrica calcolata | Descrizione | Formula |
| --- | --- | --- |
| Totale messaggi inviati | Numero totale di messaggi inviati, con successo o non riusciti | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Differenze nel reporting tra Journey Optimizer e Customer Journey Analytics

Le discrepanze di dati tra i prodotti sono genere nell’ordine di 1%-2%. Discrepanze maggiori tra i prodotti possono essere potenzialmente attribuite ai seguenti elementi:

* Il tempo di elaborazione dei dati in arrivo può variare leggermente da un prodotto all’altro, in particolare per i dati raccolti nelle ultime due ore. Per attenuare le discrepanze dovute ai tempi di elaborazione, utilizza intervalli di date escludendo “oggi”.
* La metrica calcolata “Messaggi totali inviati“ non include la metrica “Nuovi tentativi“. I dati per la metrica “Nuovi tentativi“ non sono inclusi nel set di dati, poiché mostrano numeri potenzialmente più bassi nel reporting di CJA rispetto al reporting di AJO. Tuttavia, i dati dei tentativi vengono convertiti nella metrica “Messaggi inviati con successo“ o “Non recapitati“. Utilizza intervalli di date settimanali o precedenti per attenuare le discrepanze nella metrica “Messaggi totali inviati“ da un prodotto all’altro.
