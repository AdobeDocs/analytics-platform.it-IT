---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: d8ff5191ea96b8871f6aaba1fc28211c22a13e0d
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 56%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (settembre 2025)

**Ultimo aggiornamento**: venerdì 11 settembre 2025


Queste note sulla versione coprono il periodo di rilascio da settembre a inizio ottobre 2025. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Aggiornamenti all’interfaccia di utilizzo** | L’[interfaccia di utilizzo](/help/connections/manage-connections.md#usage) ora aggiunge informazioni sul volume dei dati di base e sulla dimensione riga media.<p>Per ulteriori informazioni, vedere [Gestire le connessioni](/help/connections/manage-connections.md#usage).</p> | | 4 settembre 2025 |
| **Miglioramenti durante la migrazione di progetti e componenti in Customer Journey Analytics** | Sono ora disponibili i seguenti miglioramenti per la migrazione di progetti e componenti da Adobe Analytics a Customer Journey Analytics:<ul><li>Eseguire la migrazione di più progetti contemporaneamente.<br/>È possibile migrare fino a 20 progetti alla volta.<br/>In precedenza era possibile migrare un solo progetto alla volta.</li><li>Aggiornare le mappature per dimensioni e metriche già mappate con una migrazione di progetto precedente.<br/>È ora possibile aggiornare queste mappature ogni volta che si esegue la migrazione di un progetto, anche se in precedenza le stesse dimensioni e metriche erano state mappate con una migrazione precedente.<br/>In precedenza, tutte le mappature scelte erano permanenti per tutte le migrazioni future del progetto.</li><li>Sono state migliorate le prestazioni per le organizzazioni con un numero elevato di progetti.</li></ul><p>Questa funzione è disponibile dall’interfaccia di Adobe Analytics. Per ulteriori informazioni, vedere [Migrare componenti e progetti da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/component-migration).</p> | martedì 15 settembre 2025 | venerdì 18 settembre 2025 |
| **Limite chiavi di ricerca aumentato fino a 1 miliardo** | Il numero massimo di chiavi univoche per un set di dati di ricerca ora è fino a 1 miliardo, a seconda del diritto Customer Journey Analytics. <p>In precedenza, il numero massimo era di 10 milioni per tutti i diritti.<p>Per ulteriori informazioni, vedere [Guardrail](/help/technotes/guardrails.md).</p> | | venerdì 18 settembre 2025 |
| **Supporto per schemi ad hoc** | [Gli schemi ad hoc](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/tutorials/ad-hoc) vengono utilizzati in vari flussi di lavoro di acquisizione dati per Experience Platform, inclusa l&#39;acquisizione di file CSV e la creazione di alcuni tipi di connessioni di origine. <p>Questa funzione abilita il supporto per l’utilizzo di schemi ad hoc in Customer Journey Analytics. Come parte della definizione di una connessione, ora puoi selezionare un set di dati basato su uno schema ad hoc e utilizzare i dati nei tuoi progetti di visualizzazione dati e area di lavoro.</p> <p>Il collegamento alla documentazione seguirà a breve.</p> |  | 18 settembre 2025 (rilascio originariamente pianificato per il 28 agosto 2025) |
| **Reporting in tempo reale** | Il reporting in tempo reale in Customer Journey Analytics mostra e aggiorna dati e visualizzazioni in uno o più pannelli di Analysis Workspace in tempo reale.<br/><br/>(Segui il link alla documentazione). | 18 settembre 2025 (rilascio originariamente pianificato per il 15 agosto 2025) | 25 settembre 2025 |
| **Supporto per il mirroring dei dati** | Grazie al supporto di schemi basati su modelli e alla modifica della funzionalità di acquisizione dati (CDC) per connettori di origine specifici in Experience Platform, Customer Journey Analytics sarà in grado di supportare la funzionalità di mirroring dei dati delle soluzioni data warehouse per Snowflake, Databricks e Google BigQuery. <p>Contatta il team del tuo account Adobe per accedere alla versione beta.</p><p>Il collegamento alla documentazione seguirà a breve.</p> | Rilascio di Beta a partire dal 24 settembre | Da definire |
| **Contenuti in streaming: sono stati aggiornati i campi XDM per la raccolta dati dei contenuti in streaming in Adobe Experience Platform** | Durante la raccolta dei dati dei contenuti in streaming in Adobe Experience Platform, i percorsi dei campi XDM mostrati sotto l’intestazione “Percorso dei campi XDM” nella documentazione sui parametri per contenuti in streaming non devono più essere utilizzati. La clientela che ha implementato il connettore di origine di Analytics per raccogliere i contenuti in streaming in Platform prima del 9 maggio 2025 deve effettuare la migrazione delle le configurazioni esistenti ai percorsi dei campi mediaReporting, come mostrato nell’intestazione “Percorso dei campi XDM per il reporting” della documentazione sui parametri dei contenuti multimediali in streaming.<p> Questi percorsi dei campi si trovano nelle pagine seguenti e sono contrassegnati come “Obsoleti”: [Parametri audio e video](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parametri annuncio](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/ad-parameters), [Parametri capitolo](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametri stato del lettore](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parametri qualità](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/quality-parameters). Per la clientela che implementa il connettore di origine di Analytics dopo il 9 maggio 2025 e sta già utilizzando solo i percorsi XDM mediaReporting, non è richiesta alcuna azione.</p><p>L’acquisizione dei dati sui percorsi dei campi XDM obsoleti continuerà fino alla fine di ottobre 2025. Successivamente, i percorsi dei campi obsoleti verranno rimossi del tutto e non saranno più visibili nell’interfaccia utente dello schema di Adobe Experience Platform e i dati verranno inviati solo utilizzando i percorsi dei campi mediaReporting.</p><p>Per ulteriori informazioni, consulta [Effettuare la migrazione di un’implementazione del connettore di origine di Analytics ai campi XDM per contenuti multimediali in streaming aggiornati](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Contatta i servizi Adobe Consulting o il team del tuo account per ricevere supporto alla migrazione. </p> |  | Ottobre 2025 |
| **Unione nelle connessioni** | Semplifica l’unione in Customer Journey Analytics. Invece di duplicare un set di dati e applicare l’unione al set di dati duplicato, l’unione viene ora eseguita al momento dell’acquisizione dei dati in Customer Journey Analytics, eliminando il requisito di set di dati e schemi duplicati. <p>Inoltre, invece di dover richiedere l’unione tramite l’assistenza clienti, ora puoi iniziare a eseguire l’unione da un’interfaccia utente Connessioni aggiornata.</p><p> *Le date di rilascio comunicate in precedenza sono state posticipate a causa di ulteriori attività necessarie. Le nuove date di rilascio si sovrappongono al periodo delle festività, introducendo ulteriori vincoli per il rilascio. Per garantire la stabilità e ridurre al minimo le interruzioni durante tale periodo, è stato ora pianificato un rollout graduale.*</p> <p>Il collegamento alla documentazione seguirà a breve.</p> | Fine ottobre 2025 | Fine gennaio 2026 |

## Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-391719, AN-380838, AN-389402, AN-389373, AN-390851, AN-391593, AN-391404, AN-393064, AN-379337
**Componenti**: AN-393810
**Content Analytics**:
**Analisi guidata**:
**Platform**:
**Report Builder**: AN-387741, AN-386777, AN-388720, AN-389343
**Generazione rapporti**: AN-391439, AN-391228, AN-393620, AN-393640, AN-391334, AN-393304
**Segmentazione**:
**Rapporti pianificati**: AN-391150, AN-390474
**Metriche e dimensioni condivise**:
**Altro**: AN-387858


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
