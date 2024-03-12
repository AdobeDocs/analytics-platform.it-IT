---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e7a591c752714032b765910b35402c0de03e41dd
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 37%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (febbraio 2024)

**Ultimo aggiornamento**: mercoledì 5 marzo 2024

Queste note sulla versione coprono il periodo di rilascio compreso tra la fine di febbraio 2024 e marzo 2024. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Previsioni di serie temporali** | [Previsione](../analysis-workspace/c-forecast/forecasting.md) è una nuova funzione di Analysis Workspace utilizzata per prevedere una metrica standard o calcolata con qualsiasi granularità temporale supportata (oraria, giornaliera, settimanale, mensile e annuale) per le tabelle a forma libera e i grafici a linee. | giovedì 31 gennaio 2024 | giovedì 21 febbraio 2024 |
| **Metriche del conteggio delle righe per i dati di ricerca e profilo** | Le metriche del conteggio delle righe per i set di dati, configurate come parte di una connessione, ora includono i record aggiunti, saltati o eliminati dai set di dati di profilo e di ricerca. |  | giovedì 14 febbraio 2024 |
| **Rilevamento bot Edge Network** | [Rilevamento bot](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) consente di identificare gli eventi generati da Web SDK, Mobile SDK e Server API come generati da spider e bot noti. | | martedì 29 aprile 2024 |
| **Metriche di utilizzo** | L’interfaccia delle metriche di utilizzo mostra l’utilizzo delle righe acquisite e segnalabili in tutte le connessioni. Questa interfaccia consente di determinare se l’utilizzo del Customer Journey Analytics è conforme a quanto stabilito contrattualmente. | mercoledì 20 febbraio 2024 | giovedì 13 marzo 2024 |
| **Adobe Product Analytics: condividi con chiunque** | Consente di condividere un collegamento in sola lettura ai progetti Adobe Product Analytics con persone che non hanno accesso al Product Analytics. |  | Fine di marzo 2024 |
| **Adobe Product Analytics: applicare le metriche calcolate** | È ora possibile accedere alle metriche calcolate create in Analysis Workspace o nel generatore di metriche calcolate nella vista Tendenze: Utilizzo, per creare tendenze e confrontare le metriche nel tempo. |  | sabato 16 febbraio 2024 |
| **Sono stati aggiornati i collegamenti nelle visualizzazioni dati e nelle interfacce delle connessioni.** | All’inizio di marzo, Adobe pianifica di aggiornare i seguenti collegamenti nell’interfaccia utente del prodotto di Customer Journey Analytics. Aggiornare di conseguenza i segnalibri.<ul><li>**Pagina Visualizzazioni dati, Gestione visualizzazioni dati**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Creare una nuova visualizzazione dati**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Modifica visualizzazione dati**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Nuovo collegamento](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Gestione connessioni**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Informazioni sulle connessioni**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Modifica connessione**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Crea nuova connessione**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |  | Marzo 2024 |
| **Reporting di Media Analytics - Pubblico medio per minuto (AMA)** | Il pannello Pubblico medio per minuto è ora disponibile in CJA. I clienti Media Analytics possono utilizzare il pannello Pubblico medio per minuto per comprendere meglio il consumo medio dei loro contenuti. Il pubblico medio per minuto consente di confrontare la programmazione di qualsiasi lunghezza o genere. Inoltre, i clienti possono confrontare o aggiungere questo pubblico medio per minuto digitale alle metriche di minuti medi della TV lineare. Questo pannello offre maggiore flessibilità per misurare il pubblico medio per i periodi di tempo personalizzati, nonché quando la classificazione della durata è stata aggiornata dopo l’evento. <p>Per ulteriori informazioni, consulta [Pannello del pubblico medio per minuto del file multimediale](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)</p> |  | mercoledì 12 marzo 2024 |

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
