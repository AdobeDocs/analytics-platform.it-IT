---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3955f7c8da90481610328c0657b33e81ad6c0057
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 47%

---

# Note sulla versione corrente di Customer Journey Analytics (gennaio 2026)

**Ultimo aggiornamento**: giovedì 14 gennaio 2026

Queste note sulla versione coprono il periodo di rilascio di gennaio 2026. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analizzare i tipi di pubblico dai set di dati del profilo di Experience Platform in Customer Journey Analytics** | Ora puoi acquisire i dati sull’iscrizione del pubblico dai set di dati del profilo di Experience Platform in una connessione Customer Journey Analytics. I tipi di pubblico diventano disponibili come nuove dimensioni da utilizzare in Analysis Workspace.<p>Ciò è possibile grazie a una nuova funzionalità di Customer Journey Analytics per acquisire le mappe oggetto XDM, che consente di acquisire gli ID pubblico del profilo.</p><p>In precedenza, era possibile acquisire in Customer Journey Analytics solo semplici mappe XDM.</p><p>Oltre a poter aggiungere i dati sul pubblico come dimensioni a qualsiasi progetto in Analysis Workspace, sono disponibili i seguenti nuovi modelli di Workspace:</p><ul><li>Panoramica di Audience Analytics</li><li>Panoramica sui criteri di consenso</li></ul><p>Per ulteriori informazioni, consulta [Panoramica di Audience Analysis](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/audience-analysis/audience-analysis-overview.html?lang=it).</p> | 22 ottobre 2025 | mercoledì 27 gennaio 2026 <p> (Originariamente pianificato per il 22 gennaio 2026)</p> |
| **Narrazione dei dati: generazione di presentazioni con diapositive dai rapporti di Workspace** | È ora possibile generare automaticamente una presentazione con diapositive (in formato .pptx) basata su un rapporto di Analysis Workspace. Workspace rileva le informazioni chiave nel rapporto e le converte in diapositive pronte per gli stakeholder.<p>Questa funzione riduce il tempo e le attività necessarie per far emergere i risultati, creare relazioni per i dirigenti e comunicare l’impatto sul business.</p><p>Per ulteriori informazioni, consulta [Narrazione dei dati: generazione di presentazioni con diapositive dai rapporti di Workspace](/help/analysis-workspace/curate-share/generate-slides.md).</p> | 22 ottobre 2025 | giovedì 28 gennaio 2026 |
| **Includere più colonne di dimensione in una tabella a forma libera** | Ora è possibile includere fino a 5 colonne di dimensione in una tabella a forma libera, consentendo di visualizzare più elementi dimensionali uno accanto all’altro. Ogni riga di elementi dimensionali si comporta come un singolo elemento dimensionale concatenato.<p>Puoi applicare filtri, ordinamento, raggruppamenti e altro ancora alle tabelle a forma libera con più colonne di dimensioni per creare un’analisi più approfondita e personalizzata.</p><p>In precedenza, era possibile includere solo 1 colonna dimensione in una tabella a forma libera.</p><p>Per ulteriori informazioni, vedere [Includere più colonne di dimensione in una tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | giovedì 28 gennaio 2026 | giovedì 18 febbraio 2026 |
| **Ordinare le tabelle per più colonne** | Ora è possibile ordinare i dati di una tabella a forma libera in base a più colonne in Analysis Workspace, che si tratti di dimensioni o metriche.<p>Quando si ordinano dati per più colonne, i dati vengono ordinati in base alla priorità assegnata a ciascuna colonna. Accanto all’icona di ordinamento viene visualizzata la numerazione delle priorità.</p><p>Il link alla documentazione seguirà a breve.<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | giovedì 28 gennaio 2026 | giovedì 18 febbraio 2026 |
| **Combinare origini dati da più organizzazioni IMS** | Ora puoi utilizzare il connettore Source di Analytics per combinare più origini dati da più organizzazioni IMS. Questo consente alle organizzazioni di avere una visualizzazione combinata dei dati dei propri clienti, anche quando tali dati vengono distribuiti su più organizzazioni IMS. <p>**Nota:** questa configurazione è disponibile solo inviando una richiesta all&#39;Assistenza clienti di Adobe.</p>  <p>Il collegamento alla documentazione seguirà a breve.</p> |  | sabato 30 gennaio 2026 |
| **Unione nelle connessioni** | Il processo di unione in Customer Journey Analytics è ora più semplice. Invece di duplicare un set di dati e applicare l’unione al set di dati duplicato, l’unione viene ora eseguita al momento dell’acquisizione dei dati in Customer Journey Analytics, eliminando il requisito di set di dati e schemi duplicati. <p>Inoltre, ora puoi [iniziare a unire te stesso tramite un&#39;interfaccia Connessioni aggiornata](/help/stitching/use-stitching-ui.md), invece di dover richiedere l&#39;unione tramite l&#39;Assistenza clienti di Adobe.</p><p> *Le date di rilascio precedentemente comunicate sono state posticipate a causa di sforzi aggiuntivi richiesti e della stagione festiva. Per garantire la stabilità e ridurre al minimo le interruzioni durante tale periodo, è stato ora pianificato un rollout graduale.*</p> | 28 ottobre 2025 | sabato 30 gennaio 2026 |
| **Supporto per il mirroring dei dati** | Grazie al supporto di schemi basati su modelli e alla funzionalità di modifica di acquisizione dati (CDC) per connettori di origine specifici in Experience Platform, Customer Journey Analytics sarà in grado di supportare la funzionalità di [mirroring dei dati](/help/data-mirror/data-mirror.md) delle soluzioni data warehouse come [!DNL Snowflake], [!DNL Azure Databricks] e [!DNL Google BigQuery].<p>Contatta il team Adobe Account per accedere alla versione Beta.</p> | Versione Beta: 24 settembre 2025 | Da definire |
| **Servizi di contenuti multimediali in streaming: supporto dei dati di pianificazione** | Ora puoi caricare dati pianificati di contenuti multimediali live in streaming precedenti per tracciare in modo più semplice e preciso il pubblico.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare i dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 ottobre 2025 | Prima metà del 2026<p>Rilascio originariamente pianificato per il 29 ottobre 2025</p> |

## Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-423389, AN-423316, AN-422636, AN-422482, AN-422121, AN-422116, AN-422027, AN-421134, AN-420187, AN-406271, AN-406188, AN-405997, AN-405983, AN-405796, AN-405033, AN-404893, AN-404871, AN-404842, AN-404713, AN-404502 404353 404352 404048 403241 402523 400795 396149 390990 390646 383484 376980 371729 347570 404835, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-
**Componenti**:
**Content Analytics**:
**Analisi guidata**: AN-421274
**Esportazioni**:
**Visualizzazioni dati**: AN-421891, AN-404627
**Implementazione**:
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Generazione rapporti**:
**Segmentazione**:
**Rapporti pianificati**: AN-423087, AN-422686
**Metriche e dimensioni condivise**:
**Altro**: AN-422946, AN-422775, AN-422273, AN-422100, AN-420045, AN-404891, AN-390912


## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| N/D |  |  |

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2025](/help/release-notes/2025.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
