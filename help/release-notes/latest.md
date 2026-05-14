---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: fed0d4a0a3c956b2db30a2c2108e1e4cde3f3abe
workflow-type: tm+mt
source-wordcount: 787
ht-degree: 47%

---

# Note sulla versione corrente di Customer Journey Analytics (maggio 2026)

**Ultimo aggiornamento**: 13 maggio 2026

Queste note sulla versione coprono il periodo di rilascio di maggio 2026. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Raccolte Postman API CJA** <br/>È disponibile una raccolta Postman scaricabile per la chiamata degli endpoint API CJA.<p>Per ulteriori informazioni, consulta l&#39;[archivio Github Analytics-cja-postman-collections](https://github.com/AdobeDocs/analytics-cja-postman-collections).  </p> | | 1 maggio 2026 |
| **Server MCP per Customer Journey Analytics** <br/>I server MCP (Model Context Protocol) di Analytics consentono di connettere un client MCP supportato ad Adobe Customer Journey Analytics. Una volta connesso, il client MCP può richiamare strumenti specifici per il prodotto per recuperare dati, eseguire query o eseguire operazioni supportate come parte di un flusso di lavoro LLM o agente. Per ulteriori informazioni, vedere [Server MCP di Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Se hai utilizzato questi server MCP durante il periodo beta, tieni presente che esistono URL diversi tra gli endpoint beta e di produzione. Assicurati che tutti i flussi di lavoro agenti creati durante il periodo beta vengano aggiornati per utilizzare gli endpoint di produzione prima del 31 maggio.</p> | | 5 maggio 2026 |
| **Supporto di Content Analytics per le esperienze native di app per dispositivi mobili**<br/> Le organizzazioni possono estendere l&#39;analisi delle prestazioni dei contenuti alle app iOS e Android, acquisendo risorse di immagini ed elementi di esperienza granulari per capire quali contenuti in-app stimolano il coinvolgimento degli utenti e i risultati di business.<p> [La documentazione](/help/content-analytics/content-analytics.md) è stata aggiornata per descrivere le funzionalità e la configurazione del canale mobile. Le informazioni sull&#39;[estensione Content Analytics Mobile SDK](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) sono disponibili su [Adobe Developer](https://developer.adobe.com/).</p><p>Gli approfondimenti sono disponibili per tutti i clienti Adobe Content Analytics.</p> | | 6 maggio 2026 |
| **Convalida dei dati nell’Agente Adobe Engineering** <br/>Nell’Agente Data Engineering sono disponibili nuove competenze per la convalida dei dati. Queste competenze aiutano i team a valutare rapidamente la qualità dei dati direttamente in Adobe Experience Platform, prima che siano analizzati in Customer Journey Analytics. <p>Le competenze per la convalida dei dati consentono la convalida su richiesta, a livello di campo e a livello di set di dati, combinando riepiloghi statistici con il rilevamento intelligente di valori non validi o anomali. </p><p>L’utilizzo delle competenze di convalida dei dati riduce il tempo di controllo qualità manuale e accelera l’onboarding e le trasformazioni affidabili dei dati nei flussi di lavoro di data engineering.</p><p>Il link alla documentazione seguirà a breve.<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 19 maggio 2026 <p>Rilascio originariamente pianificato per il 31 marzo 2026</p> |
| **Content Analytics: anteprime e anteprime di visualizzazioni a linee** <br/>[Le anteprime e le anteprime](/help/content-analytics/report/report.md) sono ora disponibili per le risorse e le esperienze nelle visualizzazioni a linee di Content Analytics. |  | 20 maggio 2026 |
| **Servizi di contenuti multimediali in streaming: supporto dei dati di pianificazione** <br/>Puoi caricare dati di pianificazione di precedenti contenuti live multimediali in streaming per monitorare l’audience con maggiore facilità e precisione.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare i dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 ottobre 2025 | Prima metà del 2026<p>Rilascio originariamente pianificato per il 29 ottobre 2025</p> |

{style="table-layout:auto"}


## Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-439797, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Componenti**:
**Connessioni**: AN-449652, AN-444560, AN-442824, AN-440937, AN-440092, AN-439823, AN-429781
**Content Analytics**:
**Analisi guidata**:
**Esportazioni**: AN-438953, AN-437115
**Visualizzazioni dati**: AN-442809
**Implementazione**:
**Report Builder**: AN-448697, AN-447128, AN-441148, AN-441136, AN-438147, AN-425150
**Generazione rapporti**: AN-445123, AN-442231, AN-442169, AN-441811, AN-441733, AN-440505, AN-440300, AN-434824, AN-434210, AN-424000, AN-423359, AN-406242
**Segmentazione**:
**Report pianificati**:
**Metriche e dimensioni condivise**:
**Altro**: AN-449159, AN-444661, AN-443900, AN-397985

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2025](/help/release-notes/2025.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
