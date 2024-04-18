---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 69566b840301f87a6362d6bd16b1e255a14d4e23
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 18%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (aprile 2024)

**Ultimo aggiornamento**: giovedì 17 aprile 2024

Queste note sulla versione coprono il periodo dal 10 aprile 2024 al maggio 2024. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Streaming Media: invia dati Roku a Adobe Experience Platform Edge** | Ora quando [installazione di Media Analytics con Experienci Platform Edge](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge), puoi utilizzare Adobe Experience Platform Roku SDK per inviare dati multimediali in streaming a Adobe Experience Platform. |  | sabato 12 aprile 2024 |
| **Rapporti mensili esposti in Reporting Activity Manager** | Quando si visualizza l’attività di reporting per tutte le connessioni in Reporting Activity Manager, ora è disponibile un grafico che mostra [report/richieste mensili](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) che sono stati eseguiti a livello di organizzazione IMS, sia per il mese corrente che per quello precedente.<p>**Nota:** I dati sono disponibili a partire dal mese di marzo 2024. | | martedì 15 aprile 2024 |
| **Didascalie intelligenti nelle scorecard per dispositivi mobili** | [Sottotitoli intelligenti](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) può aiutare i non analisti a dare un senso migliore ai propri dati senza l’aiuto degli analisti. Sono ora disponibili nelle scorecard di Customer Journey Analytics. |  | giovedì 17 aprile 2024 |
| **Miglioramento delle autorizzazioni per solo progetto [!UICONTROL Workspace] componenti** | In precedenza, se un utente (Utente A) condivideva un progetto con un altro utente (Utente B) e dava all’Utente B l’accesso in modifica per il progetto, l’Utente B sarebbe stato in grado di modificare il progetto. Tuttavia, l’utente B non può modificare [!UICONTROL Quick Segments] incorporato nel progetto. Questa limitazione è ora rimossa - l’utente B può modificare [!UICONTROL Quick Segments] e altri componenti solo progetto incorporati nel progetto condiviso. |  | giovedì 17 aprile 2024 |
| **Gli amministratori possono gestire tutte le posizioni all’interno dell’organizzazione** | Una nuova opzione sul [Pagina Percorsi](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) consente agli amministratori di visualizzare e gestire tutte le posizioni dell’organizzazione. In precedenza, gli amministratori potevano visualizzare e gestire solo le posizioni che avevano creato. |  | giovedì 17 aprile 2024 |
| **Adobe Product Analytics: matrice delle funzioni** | Alimenta le decisioni di investimento capendo quali sono le tue caratteristiche principali, di potenza, una tantum e discutibili. [!UICONTROL Feature matrix] misura gli eventi in base alla frequenza d’uso rispetto alla percentuale di utenti attivi e li confronta con l’uso mediano. | giovedì 17 aprile 2024 | 30 aprile 2024 |
| **Adobe Product Analytics: approfondimenti migliorati in Funnel** | In [Attrito](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) visualizzazioni, le informazioni scritte sono state migliorate per includere categorie, delta e descrizioni al fine di migliorare la comprensibilità del grafico e della tabella. | giovedì 17 aprile 2024 | sabato 26 aprile 2024 |
| **Adobe Product Analytics: visualizzazione di conservazione avanzata** | Sono state aggiunte diverse funzionalità al [Mantenimento](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/retention/retention-rates) visualizzazione dei tassi per informazioni più approfondite e personalizzabili sulla conservazione:<ul><li>Scollega eventi di inizio e di ritorno</li><li>Confrontare più eventi di ritorno in un&#39;unica vista</li><li>Personalizza il modello di conservazione applicato con il o dopo (non limitato), su ciascuna impostazione (limitato) e tra parentesi</li><li>Mostra e nascondi singole righe della coorte nel grafico</li></ul> | giovedì 24 aprile 2024 | giovedì 8 maggio 2024 |
| **Adobe Product Analytics: confrontare eventi all’interno di un singolo passaggio funnel** | Ora puoi confrontare gli eventi all’interno di un singolo passaggio funnel in [Attrito](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) visualizzazione. Questa funzione è particolarmente utile quando il percorso dispone di opzioni per i passaggi o di un passaggio in cui viene eseguito un esperimento A/B. | mercoledì 23 aprile 2024 | sabato 3 maggio 2024 |
| **Trasformazione dello schema B2B per la persona all’account** | Consente di trasformare i set di dati per supportare meglio le ricerche basate su persone in scenari di reporting B2B di Customer Journey Analytics. Questa funzionalità è disponibile per i set di dati per gli schemi B2B basati sulle seguenti classi:<ul><li>Relazione della persona dell’account aziendale XDM</li><li>Relazione della persona dell’opportunità di business XDM</li><li>Membri dell’elenco di marketing aziendale XDM</li><li>Membri della campagna aziendale XDM</li></ul> | | giovedì 1 maggio 2024 |
| **Rilevamento bot di Experience Edge** | [Rilevamento bot](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=it) consente di identificare gli eventi generati da Web SDK, Mobile SDK e Server API come generati da spider e bot noti. | | giovedì 1 maggio 2024 |
| **Campi derivati: funzione successiva o precedente** | Queste nuove funzioni consentono di prendere un campo come input e quindi identificare il valore n-precedente o n-successivo per ottenere una migliore visualizzazione nel percorso di utenti. Questa funzionalità può anche essere combinata con altre funzioni in [!UICONTROL Derived Fields], ad esempio [!UICONTROL Concatenate], per creare nuove dimensioni. |  | giovedì 1 maggio 2024 |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-319662; AN-337894; AN-338469; AN-340147; AN-340200; AN-340443; AN-341594; AN-342442; AN-342976; AN-343020; AN-343469; AN-343703; AN-343938; AN-344614; AN-344677;

## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| **Sono stati aggiornati i collegamenti nelle visualizzazioni dati e nelle interfacce delle connessioni.** | Febbraio 15 | All’inizio di marzo, Adobe pianifica di aggiornare i seguenti collegamenti nell’interfaccia utente del prodotto di Customer Journey Analytics. Aggiornare di conseguenza i segnalibri.<ul><li>**Pagina Visualizzazioni dati, Gestione visualizzazioni dati**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Creare una nuova visualizzazione dati**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Modifica visualizzazione dati**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Nuovo collegamento](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Gestione connessioni**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Informazioni sulle connessioni**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Modifica connessione**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Crea nuova connessione**: [Collegamento esistente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Nuovo collegamento](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |

{style="table-layout:auto"}

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2024](/help/release-notes/2024.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
