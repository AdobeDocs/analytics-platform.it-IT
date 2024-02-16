---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 22b87a6f64c296e3eb05ec3b7076bf6dfa2935f9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 44%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (febbraio 2024)

**Ultimo aggiornamento**: giovedì 14 febbraio 2024

Queste note sulla versione coprono il periodo di rilascio compreso tra la fine del 14 febbraio 2024 e l’11 marzo 2024. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzionalità | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Previsioni di serie temporali** | [Previsione](../analysis-workspace/c-forecast/forecasting.md) è una nuova funzione di Analysis Workspace utilizzata per prevedere una metrica standard o calcolata con qualsiasi granularità temporale supportata (oraria, giornaliera, settimanale, mensile e annuale) per le tabelle a forma libera e i grafici a linee. | giovedì 31 gennaio 2024 | giovedì 21 febbraio 2024 |
| **Reporting di Media Analytics - Pubblico medio per minuto (AMA)** | Il pannello Pubblico medio per minuto è ora disponibile in CJA. I clienti Media Analytics possono utilizzare il pannello Pubblico medio per minuto per comprendere meglio il consumo medio dei loro contenuti. Il pubblico medio per minuto consente di confrontare la programmazione di qualsiasi lunghezza o genere. Inoltre, i clienti possono confrontare o aggiungere questo pubblico medio per minuto digitale alle metriche di minuti medi della TV lineare. Questo pannello offre maggiore flessibilità per misurare il pubblico medio per i periodi di tempo personalizzati, nonché quando la classificazione della durata è stata aggiornata dopo l’evento. |  | Febbraio 2024 |
| **Metriche del conteggio delle righe per i dati di ricerca e profilo** | Le metriche del conteggio delle righe per i set di dati, configurate come parte di una connessione, ora includono i record aggiunti, saltati o eliminati dai set di dati di profilo e di ricerca. |  | giovedì 14 febbraio 2024 |
| **Rilevamento bot di Experience Edge** | [Rilevamento bot](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) consente di identificare gli eventi generati da Web SDK, Mobile SDK e Server API come generati da spider e bot noti. | | giovedì 21 febbraio 2024 |
| **Metriche di utilizzo** | L’interfaccia delle metriche di utilizzo mostra l’utilizzo delle righe acquisite e segnalabili in tutte le connessioni. Questa interfaccia consente di determinare se l’utilizzo del Customer Journey Analytics è conforme a quanto stabilito contrattualmente. | mercoledì 20 febbraio 2024 | Inizio marzo 2024 |
| **Adobe Product Analytics: condividi con chiunque** | Consente di condividere un collegamento in sola lettura ai progetti Adobe Product Analytics con persone che non hanno accesso al Product Analytics. |  | giovedì 21 febbraio 2024 |
| **Adobe Product Analytics: applicare le metriche calcolate** | È ora possibile accedere alle metriche calcolate create in Analysis Workspace o nel generatore di metriche calcolate nella vista Tendenze: Utilizzo, per creare tendenze e confrontare le metriche nel tempo. |  | sabato 16 febbraio 2024 |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-333172; AN-336887; AN-337402; AN-337593; AN-338482; AN-338684; AN-339883; AN-340200

## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| Aggiunte di membri agli oggetti API di Adobe | 17 gennaio 2024 | Adobe può aggiungere membri di richiesta e risposta facoltativi (coppie nome/valore) agli oggetti API esistenti senza preavviso o modifiche nel controllo delle versioni. Tali aggiunte dovrebbero essere modifiche che non comportano interruzioni per l’implementazione. Adobe consiglia di fare riferimento alla documentazione API di qualsiasi strumento di terze parti integrato con le nostre API, in modo che tali aggiunte, se non comprese, vengano ignorate durante l’elaborazione. Adobe non rimuove né aggiunge parametri richiesti senza prima fornire una notifica standard tramite le note sulla versione. |

{style="table-layout:auto"}

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2023](/help/release-notes/2023.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
