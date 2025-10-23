---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 0fff87aea456ca34169b63601e0cf239e178ebf8
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 92%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (ottobre 2025)

**Ultimo aggiornamento**: 14 ottobre 2025

Queste note sulla versione coprono il periodo di rilascio compreso tra ottobre e gli inizi di novembre 2025. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Criteri di filtro inclusi nelle visualizzazioni a linee e nei grafici sparkline** | Tutti i criteri di filtro di ricerca applicati a un filtro di tabella a forma libera ora vengono sempre inclusi nei grafici sparkline. Inoltre, puoi includere i criteri di filtro di ricerca in qualsiasi visualizzazione a linee collegata.<p>Puoi configurare le visualizzazioni a linee in modo da includere i criteri di filtro di ricerca selezionando il grafico sparkline nell’intestazione della colonna della metrica della tabella collegata.</p><p>In precedenza, i criteri di filtro di ricerca non venivano inclusi nelle visualizzazioni a linee collegate o sparkline.</p><p>Per ulteriori informazioni, consulta [Visualizzare i dati di tendenza per una tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).</p> | | 15 ottobre 2025 |
| **Narrazione dei dati: generazione di presentazioni con diapositive dai rapporti di Workspace** | È ora possibile generare automaticamente una presentazione con diapositive (in formato .pptx) basata su un rapporto di Analysis Workspace. Workspace rileva le informazioni chiave nel rapporto e le converte in diapositive pronte per gli stakeholder.<p>Questa funzione riduce il tempo e le attività necessarie per far emergere i risultati, creare relazioni per i dirigenti e comunicare l’impatto sul business.</p><p>Per ulteriori informazioni, vedere [Narrazione dei dati: generare presentazioni di diapositive dai report di Workspace](/help/analysis-workspace/curate-share/generate-slides.md).</p> | 22 ottobre 2025 | Gennaio 2026 |
| **Reporting in tempo reale** | [Il reporting in tempo reale in Customer Journey Analytics](/help/components/real-time/real-time.md) visualizza e aggiorna dati e visualizzazioni in uno o più pannelli in Analysis Workspace in tempo reale. | 18 settembre 2025 (rilascio originariamente pianificato per il 15 agosto 2025) | 22 ottobre 2025 |
| **Supporto per il mirroring dei dati** | Grazie al supporto degli schemi basati su modelli e alla modifica della funzionalità di acquisizione dati (CDC) per connettori di origine specifici in Experience Platform, Customer Journey Analytics sarà in grado di supportare la funzionalità [mirroring dati](/help/data-mirror/data-mirror.md) di soluzioni data warehouse come [!DNL Snowflake], [!DNL Azure Databricks] e [!DNL Google BigQuery].<p>Contatta il team Adobe Account per accedere alla versione Beta.</p> | Versione Beta: 24 settembre 2025 | Da definire |
| **Unione nelle connessioni** | Semplifica l’unione in Customer Journey Analytics. Invece di duplicare un set di dati e applicare l’unione al set di dati duplicato, l’unione viene ora eseguita al momento dell’acquisizione dei dati in Customer Journey Analytics, eliminando il requisito di set di dati e schemi duplicati. <p>Inoltre, invece di dover richiedere l’unione tramite l’assistenza clienti, ora puoi iniziare a eseguire l’unione da un’interfaccia utente Connessioni aggiornata.</p><p> *Le date di rilascio comunicate in precedenza sono state posticipate a causa di ulteriori attività necessarie. Le nuove date di rilascio si sovrappongono al periodo delle festività, introducendo ulteriori vincoli per il rilascio. Per garantire la stabilità e ridurre al minimo le interruzioni durante tale periodo, è stato ora pianificato un rollout graduale.*</p> <p>Il collegamento alla documentazione seguirà a breve.</p> | 28 ottobre 2025 | 30 aprile 2026 |
| **Servizi di contenuti multimediali in streaming: supporto dei dati di pianificazione** | Ora puoi caricare dati pianificati di contenuti multimediali live in streaming precedenti per tracciare in modo più semplice e preciso il pubblico.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Il link alla documentazione seguirà a breve.<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | 29 ottobre 2025 |
| **Connettore di origine di Analytics: ricerca di suite di rapporti in Experience Platform** | Chi dispone di un numero elevato di suite di rapporti ora può cercare la suite di rapporti a cui connettersi all’interno del flusso di lavoro del flusso di dati del connettore di origine di Analytics. <p>In precedenza, era necessario paginare un elenco potenzialmente lungo di suite di rapporti.</p><p>Il collegamento alla documentazione seguirà a breve. | | 30 ottobre 2025 |
| **Contenuti in streaming: sono stati aggiornati i campi XDM per la raccolta dati dei contenuti in streaming in Adobe Experience Platform** | Durante la raccolta dei dati dei contenuti in streaming in Adobe Experience Platform, i percorsi dei campi XDM mostrati sotto l’intestazione “Percorso dei campi XDM” nella documentazione sui parametri per contenuti in streaming non devono più essere utilizzati. La clientela che ha implementato il connettore di origine di Analytics per raccogliere i contenuti in streaming in Platform prima del 9 maggio 2025 deve effettuare la migrazione delle le configurazioni esistenti ai percorsi dei campi mediaReporting, come mostrato nell’intestazione “Percorso dei campi XDM per il reporting” della documentazione sui parametri dei contenuti multimediali in streaming.<p> Questi percorsi dei campi si trovano nelle pagine seguenti e sono contrassegnati come “Obsoleti”: [Parametri audio e video](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parametri annuncio](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/ad-parameters), [Parametri capitolo](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametri stato del lettore](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parametri qualità](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/quality-parameters). Per la clientela che implementa il connettore di origine di Analytics dopo il 9 maggio 2025 e sta già utilizzando solo i percorsi XDM mediaReporting, non è richiesta alcuna azione.</p><p>L’acquisizione dei dati sui percorsi dei campi XDM obsoleti continuerà fino alla fine di ottobre 2025. Successivamente, i percorsi dei campi obsoleti verranno rimossi del tutto e non saranno più visibili nell’interfaccia utente dello schema di Adobe Experience Platform e i dati verranno inviati solo utilizzando i percorsi dei campi mediaReporting.</p><p>Per ulteriori informazioni, consulta [Effettuare la migrazione di un’implementazione del connettore di origine di Analytics ai campi XDM per contenuti multimediali in streaming aggiornati](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Contatta i servizi Adobe Consulting o il team del tuo account per ricevere supporto alla migrazione. </p> |  | Ottobre 2025 |

## Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-400507, AN-400265, AN-399209, AN-397146, AN-394992, AN-390795
**Componenti**:
**Content Analytics**:
**Esportazioni**: AN-399012, AN-388578
**Analisi guidata**:
**Implementazione**: AN-397551, AN-397550, AN-397190, AN-396127
**Report Builder**: AN-401127, AN-400618, AN-392971, AN-391692
**Reporting**:
**Segmentazione**:
**Rapporti pianificati**:
**Metriche e dimensioni condivise**:
**Altro**:


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
