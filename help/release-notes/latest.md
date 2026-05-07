---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: ae368ea39b6521e2e350aa7849568cd225ecef90
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 63%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (aprile 2026)

**Ultimo aggiornamento**: 22 aprile 2026

Queste note sulla versione coprono il periodo di rilascio di aprile 2026. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Supporto della lingua italiana**<br/> La lingua italiana (it-IT) è ora supportata in Analysis Workspace di Customer Journey Analytics. <p>Customer Journey Analytics supporta tutte le lingue supportate nell’interfaccia utente di Experience Platform, come descritto in [Browser e lingue supportati dall’interfaccia utente di Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/landing/platform-ui/browser-language-support#language-support).</p><p>Puoi [modificare la lingua predefinita](https://experienceleague.adobe.com/it/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language) in Experience Platform.</p> | | 8 aprile 2026 |
| **Convalida dei dati nell’Agente Adobe Engineering** <br/>Nell’Agente Data Engineering sono disponibili nuove competenze per la convalida dei dati. Queste competenze aiutano i team a valutare rapidamente la qualità dei dati direttamente in Adobe Experience Platform, prima che siano analizzati in Customer Journey Analytics. <p>Le competenze per la convalida dei dati consentono la convalida su richiesta, a livello di campo e a livello di set di dati, combinando riepiloghi statistici con il rilevamento intelligente di valori non validi o anomali. </p><p>L’utilizzo delle competenze di convalida dei dati riduce il tempo di controllo qualità manuale e accelera l’onboarding e le trasformazioni affidabili dei dati nei flussi di lavoro di data engineering.</p><p>Il link alla documentazione seguirà a breve.<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | Maggio 2026 <p>Rilascio originariamente pianificato per il 31 marzo 2026</p> |
| **Server MCP per Customer Journey Analytics** <br/>I server MCP (Model Context Protocol) di Analytics consentono di connettere un client MCP supportato ad Adobe Customer Journey Analytics. Una volta connesso, il client MCP può richiamare strumenti specifici per il prodotto per recuperare dati, eseguire query o eseguire operazioni supportate come parte di un flusso di lavoro LLM o agente. Per ulteriori informazioni, vedere [Server MCP di Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Se hai utilizzato questi server MCP durante il periodo beta, tieni presente che esistono URL diversi tra gli endpoint beta e di produzione. Assicurati che tutti i flussi di lavoro agenti creati durante il periodo beta vengano aggiornati per utilizzare gli endpoint di produzione prima del 31 maggio.</p> | | 5 maggio 2026 |
| **Supporto di Content Analytics per le esperienze native di app per dispositivi mobili**<br/> Le organizzazioni possono estendere l&#39;analisi delle prestazioni dei contenuti alle app iOS e Android, acquisendo risorse di immagini ed elementi di esperienza granulari per capire quali contenuti in-app stimolano il coinvolgimento degli utenti e i risultati di business. [La documentazione](/help/content-analytics/content-analytics.md) è stata aggiornata per descrivere le funzionalità e la configurazione del canale mobile. Le informazioni sull&#39;[estensione Content Analytics Mobile SDK](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) sono disponibili da [Adobe Developer](https://developer.adobe.com).<p>Gli approfondimenti sono disponibili per tutti i clienti Adobe Content Analytics.</p> | 6 maggio 2026 | 6 maggio 2026 |
| **Servizi di contenuti multimediali in streaming: supporto dei dati di pianificazione** <br/>Puoi caricare dati di pianificazione di precedenti contenuti live multimediali in streaming per monitorare l’audience con maggiore facilità e precisione.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare i dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 ottobre 2025 | Prima metà del 2026<p>Rilascio originariamente pianificato per il 29 ottobre 2025</p> |
| **Reporting di API con più dimensioni**<br/> Genera rapporti a più dimensioni in una singola richiesta API ed esegui ricerche a livello di dimensione. [Ulteriori informazioni](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | Marzo 2026 |
| **Ordinamento API a più colonne**<br/> Ordina gli oggetti con più dimensioni e metriche in una richiesta API. Combina dimensioni e metriche nella definizione dello stesso ordinamento. [Ulteriori informazioni](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | Marzo 2026 |

## Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-442813, AN-442410, AN-442231, AN-441943, AN-441717, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Componenti**:
**Connessioni**: AN-442824, AN-440937, AN-440092, AN-429781
**Content Analytics**:
**Analisi guidata**:
**esportazioni**:
**Visualizzazioni dati**: AN-442809, AN-434824, AN-434210, AN-424000
**Implementazione**:
**Report Builder**: AN-441136, AN-438147, AN-425150
**Generazione rapporti**: AN-443900, AN-441811, AN-441506, AN-440919, AN-440545, AN-440505, AN-440300
**Segmentazione**:
**Report pianificati**:
**Metriche e dimensioni condivise**:
**Altro**: AN-423359, AN-406242, AN-397985

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2025](/help/release-notes/2025.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
