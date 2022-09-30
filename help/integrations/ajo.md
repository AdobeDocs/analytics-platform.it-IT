---
title: Integrare Adobe Journey Optimizer con il Customer Journey Analytics
description: Inserisci i dati generati da AJO e analizzali utilizzando Analysis Workspace all’interno di CJA.
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 3%

---


# Integrare Adobe Journey Optimizer con il Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=it) ti consente di fornire esperienze connesse, contestuali e personalizzate. Aiuta a esporre i clienti al passaggio successivo nel loro percorso di clienti.

Puoi importare i dati generati da Journey Optimizer per eseguire analisi avanzate in Customer Journey Analytics eseguendo le seguenti operazioni:

## Inviare dati da Journey Optimizer a Adobe Experience Platform

Adobe Experience Platform funge da origine dati centrale e da collegamento tra Journey Optimizer e il Customer Journey Analytics. Vedi [Introduzione ai set di dati](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html) nella guida utente di Journey Optimizer per informazioni su come inviare dati Journey Optimizer a Platform as a Dataset.

## Crea una connessione nel Customer Journey Analytics

Una volta che i dati di Journey Optimizer sono in Adobe Experience Platform, puoi [Creare una connessione](/help/connections/create-connection.md) in base al set di dati di Journey Optimizer. Seleziona il set di dati inviato a Platform.

## Configurare la visualizzazione dati in modo da adattarla alle dimensioni e alle metriche di Journey Optimizer

Dopo la creazione di una connessione, puoi crearne una o più [Visualizzazioni dati](/help/data-views/create-dataview.md) per configurare le dimensioni e le metriche desiderate disponibili nel Customer Journey Analytics.

Puoi creare le metriche seguenti in una visualizzazione dati per ottenere una parità approssimativa con metriche simili in Journey Optimizer. Vedi [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) in Gestione visualizzazione dati per informazioni su come personalizzare dimensioni e metriche.

| Metrica | Descrizione | Impostazioni di Visualizzazione dati |
| --- | --- | --- |
| Rimbalzi | Numero di messaggi rimbalzati | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` con le seguenti impostazioni:<br>Tipo di componente: Metrica<br>Includi valori di esclusione: Se sono soddisfatti dei criteri<br>È Uguale a: `bounce`<br>È Uguale a: `denylist` |
| Errori | Numero di messaggi che hanno generato un errore | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` con le seguenti impostazioni:<br>Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `error` |
| Escludi | Numero di messaggi esclusi | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` con le seguenti impostazioni:<br>Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `exclude` |
| Annulla sottoscrizione | Numero di annullamenti di abbonamenti | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageInteraction.interactionType` con le seguenti impostazioni:<br>Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `unsubscribe` |
| Clic | Numero di clic all’interno dei messaggi | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageInteraction.interactionType` con le seguenti impostazioni:<br>Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `click` |
| Aperture | Numero di messaggi aperti | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageInteraction.interactionType` con le seguenti impostazioni:<br>Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `open` |
| Disturbi dello spam | Il conteggio delle denunce di spam | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageInteraction.interactionType` con le seguenti impostazioni:<br>Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `spam_complaint` |
| Messaggi inviati | Numero di messaggi inviati correttamente | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` con le seguenti impostazioni:<br>Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `sent` |
| Errori di sincronizzazione | Numero totale di messaggi non sincronizzati | Utilizza l’elemento stringa dello schema `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` con le seguenti impostazioni:<br>Tipo di componente: Metrica<br>Includi valori di esclusione: Uguale `sync` |

{style=&quot;table-layout:auto&quot;}

## Configurare le metriche calcolate utilizzando le metriche di Journey Optimizer

Dopo aver configurato le dimensioni e le metriche desiderate per il set di dati di Journey Optimizer, puoi anche configurare [Metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md) per ulteriori informazioni su tali dati. Queste metriche calcolate si basano sulle metriche sopra riportate create in Data View Manager.

| Metrica calcolata | Descrizione | Formula |
| --- | --- | --- |
| Totale messaggi inviati | Numero totale di messaggi inviati, completati o non riusciti | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Differenze nel reporting tra Journey Optimizer e Customer Journey Analytics

Le discrepanze di dati tra i prodotti si situano in genere tra l’1 e il 2%. Differenze maggiori tra i prodotti possono essere potenzialmente attribuite ai seguenti elementi:

* Il tempo di elaborazione dei dati in arrivo può essere leggermente diverso tra i prodotti, in particolare per i dati raccolti nelle ultime due ore. Utilizza intervalli di date esclusi oggi per attenuare le discrepanze che coinvolgono i tempi di elaborazione.
* La metrica calcolata &quot;Messaggi totali inviati&quot; non include la metrica &quot;Tentativi&quot;. I dati per la metrica &quot;Nuovi tentativi&quot; non sono inclusi nel set di dati, poiché mostrano numeri potenzialmente più bassi nei rapporti di CJA rispetto ai rapporti di AJO. Tuttavia, i dati dei tentativi vengono convertiti nella metrica &quot;Messaggi inviati con successo&quot; o &quot;Rimbalzi&quot;. Utilizza intervalli di date settimanali o precedenti per attenuare le discrepanze con la metrica &quot;Totale messaggi inviati&quot; tra i prodotti.
