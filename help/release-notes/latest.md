---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1b39449fa58157fb61d619de82235cba326ffe2c
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 29%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (marzo 2024)

**Ultimo aggiornamento**: sabato 8 marzo 2024

Queste note sulla versione coprono il periodo di rilascio compreso tra la fine del 13 marzo 2024 e aprile 2024. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nuova colonna disponibile nella pagina di destinazione Progetti** | Il **[!UICONTROL Last used]** è ora disponibile quando si visualizza la scheda Progetti nella [Pagina di destinazione Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html). Queste informazioni possono essere utili per determinare se un progetto è utile per gli utenti dell’organizzazione, mostrando la data e l’ora dell’ultima apertura del progetto. Precedentemente, il **[!UICONTROL Last used]** Questa colonna era disponibile solo nelle aree Gestione metriche calcolate, Gestione segmenti e Gestione avvisi. |  | giovedì 13 marzo 2024 |
| **Metriche di utilizzo** | L’interfaccia delle metriche di utilizzo mostra l’utilizzo delle righe acquisite e segnalabili in tutte le connessioni. Questa interfaccia consente di determinare se l’utilizzo del Customer Journey Analytics è conforme a quanto stabilito contrattualmente. |  | giovedì 13 marzo 2024 |
| **Reporting di Media Analytics - Pubblico medio per minuto (AMA)** | Il pannello Pubblico medio per minuto è ora disponibile in CJA. I clienti Media Analytics possono utilizzare il pannello Pubblico medio per minuto per comprendere meglio il consumo medio dei loro contenuti. Il pubblico medio per minuto consente di confrontare la programmazione di qualsiasi lunghezza o genere. Inoltre, i clienti possono confrontare o aggiungere questo pubblico medio per minuto digitale alle metriche di minuti medi della TV lineare. Questo pannello offre maggiore flessibilità per misurare il pubblico medio per i periodi di tempo personalizzati, nonché quando la classificazione della durata è stata aggiornata dopo l’evento. |  | mercoledì 12 marzo 2024 |
| **Trasformazione dello schema B2B per la persona all’account** | Consente di trasformare i set di dati per supportare meglio le ricerche basate su persone in scenari di reporting B2B di Customer Journey Analytics. Questa funzionalità è disponibile per i set di dati per gli schemi B2B basati sulle seguenti classi:<ul><li>Relazione della persona dell’account aziendale XDM</li><li>Relazione della persona dell’opportunità di business XDM</li><li>Membri dell’elenco di marketing aziendale XDM</li><li>Membri della campagna aziendale XDM</li></ul> | | mercoledì 26 marzo 2024 |
| **Adobe Product Analytics: confrontare eventi all’interno di un singolo passaggio funnel** | Nella vista Funnel: Friction, ora puoi confrontare gli eventi all’interno di un singolo passaggio funnel. Questa funzione è particolarmente utile quando il percorso dispone di opzioni per i passaggi o di un passaggio in cui viene eseguito un esperimento A/B. | sabato 29 marzo 2024 | sabato 12 aprile 2024 |
| **Gli amministratori possono gestire tutte le posizioni all’interno dell’organizzazione** | Una nuova opzione nella pagina Posizioni consente agli amministratori di visualizzare e gestire tutte le posizioni dell’organizzazione. In precedenza, gli amministratori potevano visualizzare e gestire solo le posizioni create. | | Aprile 2024 |
| **I tipi di pubblico vengono pubblicati in una nuova sezione &quot;Tipi di pubblico&quot; nell’Experience Platform** | I tipi di pubblico pubblicati dal Customer Journey Analytics sono ora disponibili nella nuova sezione &quot;Tipi di pubblico&quot; di questo Experience Platform. In precedenza, i tipi di pubblico pubblicati da Customer Journey Analytics erano disponibili in Platform nella sezione &quot;Segmenti&quot;. Questo miglioramento offre i seguenti vantaggi:<ul><li>I tipi di pubblico non hanno più un ritardo di 1 ora prima di essere visualizzati in Platform; sono disponibili pochi secondi dopo la pubblicazione.</li><li>I tipi di pubblico possono essere ordinati in Platform utilizzando la colonna &quot;Origine&quot;, che mostra l’applicazione da cui il pubblico è stato pubblicato originariamente.</li><li>Le opzioni di filtro e ordinamento disponibili in Platform consentono di trovare più rapidamente i tipi di pubblico rilevanti.</li></ul>Per ulteriori informazioni, consulta la sezione [Utilizzare i tipi di pubblico di Customer Journey Analytics in Experienci Platform](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=en#audiences-aep). |  | Aprile 2024 |
| **Rilevamento bot di Experience Edge** | [Rilevamento bot](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) consente di identificare gli eventi generati da Web SDK, Mobile SDK e Server API come generati da spider e bot noti. | | martedì 29 aprile 2024 |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-340429; AN-341544; AN-341974; AN-342176; AN-342391

## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| **Sono stati aggiornati i collegamenti nelle visualizzazioni dati e nelle interfacce delle connessioni.** | Febbraio 15 | All’inizio di marzo, Adobe pianifica di aggiornare i seguenti collegamenti nell’interfaccia utente del prodotto di Customer Journey Analytics. Aggiornare di conseguenza i segnalibri.<ul><li>**Pagina Visualizzazioni dati, Gestione visualizzazioni dati**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Creare una nuova visualizzazione dati**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Modifica visualizzazione dati**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Nuovo collegamento](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Gestione connessioni**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Informazioni sulle connessioni**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Modifica connessione**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Crea nuova connessione**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |
| Aggiunte di membri agli oggetti API di Adobe | 17 gennaio 2024 | Adobe può aggiungere membri di richiesta e risposta facoltativi (coppie nome/valore) agli oggetti API esistenti senza preavviso o modifiche nel controllo delle versioni. Tali aggiunte dovrebbero essere modifiche che non comportano interruzioni per l’implementazione. Adobe consiglia di fare riferimento alla documentazione API di qualsiasi strumento di terze parti integrato con le nostre API, in modo che tali aggiunte, se non comprese, vengano ignorate durante l’elaborazione. Adobe non rimuove né aggiunge parametri richiesti senza prima fornire una notifica standard tramite le note sulla versione. |

{style="table-layout:auto"}

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2023](/help/release-notes/2023.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
