---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 9c3546c33914feb7a00b5bb78a575dd511cabb5f
workflow-type: tm+mt
source-wordcount: 615
ht-degree: 44%

---

# Note sulla versione corrente di Customer Journey Analytics (giugno 2026)

**Ultimo aggiornamento**: 25 giugno 2026

Queste note sulla versione coprono il periodo di rilascio di giugno 2026. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Data Mirror** <br/>[Data Mirror](/help/data-mirror/data-mirror.md) è una funzionalità di Experience Platform che consente l&#39;acquisizione delle modifiche a livello di riga (acquisizione dei dati di modifica) da soluzioni data warehouse esterne ([!DNL Snowflake], [!DNL Azure Databricks] e [!DNL Google BigQuery]) in Customer Journey Analytics utilizzando schemi relazionali. Mantiene le relazioni tra i dati, applica l’univocità e supporta il controllo delle versioni senza richiedere processi ETL (Extract, Transform, and Load) a monte. | 25 marzo 2026 | 17 giugno 2026 |
| **Convalida i dati nell&#39;Assistente di intelligenza artificiale** <br/>Puoi utilizzare l&#39;Assistente di intelligenza artificiale per [convalidare la qualità dei tuoi set di dati di Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/data-validation). Grazie alla tecnologia di Agent Orchestrator, la funzionalità di convalida dei dati può eseguire convalide statistiche e semantiche sui set di dati, analizzare i campi dei set di dati, identificare i problemi di qualità dei dati e restituire riepiloghi in linguaggio naturale con informazioni fruibili. | | 22 giugno 2026 |

### Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-456858, AN-455865, AN-455706, AN-455592, AN-455484, AN-455180, AN-454999, AN-454170, AN-454145, AN-453793, AN-452921, AN-452009, AN-451958, AN-451643, AN-451600, AN-451525, AN-451477, AN-451262, AN-451161, AN-450772 443594 434416, AN-, AN-
**Componenti**:
**Connessioni**: AN-457065, AN-453705
**Content Analytics**: AN-451203, AN-447596
**Analisi guidata**:
**Esportazioni**: AN-452006, AN-451989, AN-440567
**Visualizzazioni dati**: AN-451198
**Implementazione**:
**Report Builder**: AN-440912, AN-457586, AN-457533, AN-455713, AN-455623, AN-455063, AN-454512, AN-454053, AN-453977, AN-453781, AN-453683, AN-451974, AN-451735, AN-451731, AN-451190, AN-449813, AN-447173, AN-447139, AN-446184, AN-445794 445354 442819, AN-, AN-
**Generazione rapporti**: AN-454589, AN-454517, AN-453982, AN-451822, AN-451497, AN-451463, AN-451259, AN-451215, AN-450661, AN-447699, AN-448375, AN-447692
**Segmentazione**:
**Rapporti pianificati**: AN-451980, AN-451882, AN-450715
**Metriche e dimensioni condivise**:
**Analisi del pubblico**: AN-449656, AN-450400
**Altro**: AN-457063, AN-454140, AN-453937, AN-453825, AN-452959, AN-452934, AN-452296, AN-451781, AN-450974

## Funzioni posticipate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Servizi multimediali in streaming: supporto dei dati di pianificazione** <br/>Ora puoi caricare dati di pianificazione di precedenti contenuti live multimediali in streaming per monitorare l’audience con maggiore facilità e precisione.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare i dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data) | 29 ottobre 2025 | Da definire<p>(Originariamente previsto per il 29 ottobre 2025)</p> |

>[!MORELIKETHIS]
>
>* [Note sulla versione precedente di Customer Journey Analytics per il 2026](/help/release-notes/2026.md)
>* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
>* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
>* [Note sulla versione di CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
>* [Aggiornamenti alla documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)

