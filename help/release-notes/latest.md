---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 65b4339b4a1b27c41cfe442482a54661989d704b
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 70%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (aprile 2025)

**Ultimo aggiornamento**: venerdì 8 maggio 2025

Queste note sulla versione coprono il periodo di rilascio compreso tra il 27 marzo e il 15 maggio 2025. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Dimensione profondità evento** | Una nuova dimensione Profondità evento viene aggiunta all&#39;elenco di [dimensioni standard](/help/components/dimensions/overview.md#standard-dimensions) per una visualizzazione dati. |  | venerdì 8 maggio 2025 |
| **Aumento dei limiti di esportazione della tabella completa** | Il numero di colonne utilizzabili dai clienti con l’esportazione di tabelle complete viene aumentato da 5 dimensioni e 5 metriche a 10 dimensioni e 10 metriche. Questo aumento si applica a tutti i livelli Customer Journey Analytics. I diritti per il numero di righe che è possibile esportare non vengono modificati. |  | 30 aprile 2025 |
| **Aggiornamento della riga “Nessun valore” nelle dimensioni numeriche** | Per le dimensioni numeriche, questo aggiornamento consente di<ul><li>Utilizza l’elemento dimensionale &quot;No Value&quot; (Nessun valore) in un segmento.</li><li>eseguire un raggruppamento in un rapporto sulla riga “Nessun valore”.</li></ul> [Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | | 27 marzo 2025 |
| **Adobe Content Analytics** | Adobe Content Analytics consente di analizzare in modo rapido e semplice grandi volumi di dati sui contenuti per scoprire tendenze, individuare anomalie, identificare il sovraccarico di contenuti e ottenere informazioni approfondite dall’esposizione dei contenuti.<p>Con modelli di reporting predefiniti e nuove funzioni come il controllo risorse è possibile risparmiare tempo. Questa funzionalità consente non solo di visualizzare la risorsa in linea con i dati, ma anche di aprire ogni risorsa per i dettagli di riepilogo quali prestazioni, posizionamenti, attributi e altro ancora.<p>È possibile analizzare questo nuovo set di dati di contenuto nel contesto dell’intero percorso cliente per rispondere a domande aziendali importanti, valutare le prestazioni dei contenuti, migliorare la segmentazione, identificare opportunità di ottimizzazione e definire nuovi tipi di pubblico per l’attivazione.<p>Content Analytics è un componente aggiuntivo di Customer Journey Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/analytics-platform/using/content-analytics/content-analytics) |  | 27 marzo 2025 |
| **Media Collection: aggiornamenti del connettore di origine di Adobe per il nuovo XDM per Media Reporting** | Il connettore di origine di Analytics mappa automaticamente i dati di contenuti multimediali in streaming in Adobe Analytics agli stessi campi utilizzati da Web SDK. Precedentemente, i dati erano mappati sia sulle vecchie che sulle nuove posizioni, ma solo la nuova posizione verrà utilizzata in futuro. [Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 31 marzo 2025 |
| **Sono stati aggiornati i campi XDM per la raccolta dei dati di Streaming Media in Adobe Experience Platform** | Durante la raccolta di dati Streaming Media in Adobe Experience Platform, i percorsi dei campi XDM mostrati nell’intestazione &quot;Percorso campo XDM&quot; della documentazione sui parametri Streaming Media non devono più essere utilizzati. I percorsi dei campi sono disponibili nelle pagine seguenti e sono contrassegnati come &quot;Obsoleti&quot;: [Parametri audio e video](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parametri annuncio](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/ad-parameters), [Parametri capitolo](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametri stato lettore](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parametri qualità](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/quality-parameters). <p>I clienti devono invece migrare ai percorsi dei campi `mediaReporting`, come mostrato nell&#39;intestazione &quot;Percorso campo XDM per reporting&quot; della documentazione dei parametri di Streaming Media di cui sopra.<p>Durante un periodo transitorio di tre mesi, l’acquisizione dei dati sui percorsi dei campi XDM obsoleti continuerà. Tuttavia, alla fine di luglio 2025, i percorsi dei campi obsoleti verranno completamente rimossi e non saranno più visibili nell’interfaccia utente dello schema di Adobe Experience Platform e i dati verranno inviati solo utilizzando i percorsi dei campi `mediaReporting`.<p>I clienti che hanno implementato il connettore di origine di Analytics per raccogliere i dati di Streaming Media in Platform prima del 22 aprile 2025 devono migrare le configurazioni esistenti per utilizzare i nuovi percorsi dei campi. Questa migrazione deve essere completata entro la fine di luglio 2025. Contatta i servizi Adobe Consulting o il team del tuo account per ricevere supporto alla migrazione. Per la clientela che implementa il connettore di origine di Analytics dopo il 22 aprile 2025 non è richiesta alcuna azione.</p> |  | 22 aprile 2025 |
| **Modifica terminologica di “Filtri” in “Segmenti”** | In precedenza, Adobe Customer Journey Analytics definiva i segmenti “filtri”. Questa terminologia è ora in linea con Adobe Analytics. I “filtri” vengono ora denominati “segmenti”. (Ovviamente, i filtri di ricerca sono ancora denominati &quot;filtri&quot;.) L’interfaccia utente e la documentazione sono state aggiornate. | | 16 aprile 2025 |
| **Unione: recupero di ID permanenti e transitori da IdentityMap XDM** | Questa funzione fornisce supporto per l’utilizzo di identità memorizzate in IdentityMap XDM nel processo di unione. IdentityMap può essere utilizzato per l’ID persistente o transitorio per l’unione basata sui campi e per l’ID persistente per l’unione basata sui grafici.  È possibile utilizzare uno spazio dei nomi specifico o un’identità primaria da identityMap. Ulteriori informazioni sono disponibili [qui](https://experienceleague.adobe.com/it/docs/analytics-platform/using/stitching/fbs#identitymap) e [qui](https://experienceleague.adobe.com/it/docs/analytics-platform/using/stitching/gbs#identitymap) |  | martedì 28 aprile 2025 |
| **Metriche e dimensioni condivise tra le visualizzazioni dati** | Consente di applicare impostazioni di dimensioni e metriche a più visualizzazioni dati. Le modifiche apportate a una dimensione o metrica condivisa si applicano a tutte le istanze di tale dimensione o metrica in tutte le visualizzazioni dati applicabili. Questa interfaccia consente agli amministratori di Customer Journey Analytics di gestire più facilmente i componenti quando vengono utilizzate più visualizzazioni dati. [Ulteriori informazioni](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 30 aprile 2025 |


## Correzioni in Customer Journey Analytics

**Admin Console**: AN-370228
**Analysis Workspace**: AN-371933; AN- 371933; AN-371979
**Tipi di pubblico**: AN-373032
**Impostazioni dei componenti**: AN-367400
**Campi derivati**: AN-370614; AN-370959
**Posizioni di esportazione**: AN-371670
**Esportazione tabella completa**: AN-360492; AN-369204; AN-370755;AN-372294; AN-372363; AN-372754; AN-373040; AN-373081; AN-373168
**Area di lavoro del percorso**: AN-373294
**App per dispositivi mobili**: AN-363169; AN-368496; AN-371766
**Utilizzo prodotto**: AN-369501
**Generazione rapporti**: AN-369085; AN-371094; AN-372580


## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| N/D | | |

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2025](/help/release-notes/2025.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
