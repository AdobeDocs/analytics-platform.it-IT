---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 701279f92877ee186160f901f0d4df74fd42f547
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 36%

---

# Note sulla versione corrente di Customer Journey Analytics (aprile 2026)

**Ultimo aggiornamento**: 9 aprile 2026

Queste note sulla versione coprono il periodo di rilascio di aprile 2026. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Supporto per la lingua italiana**<br/> La lingua italiana (it-IT) è ora supportata in Analysis Workspace in Customer Journey Analytics. <p>Customer Journey Analytics supporta tutte le lingue supportate nell&#39;interfaccia utente di Experience Platform, come descritto in [Browser e supporto delle lingue per l&#39;interfaccia utente di Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/landing/platform-ui/browser-language-support#language-support).</p><p>Puoi [modificare la lingua predefinita](https://experienceleague.adobe.com/it/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language) in Experience Platform.</p> | | giovedì 8 aprile 2026 |
| **Convalida dei dati in Adobe Engineering Agent** <br/>In Data Engineering Agent sono disponibili nuove competenze per la convalida dei dati. Queste competenze aiutano i team a valutare rapidamente la qualità dei dati direttamente in Adobe Experience Platform, prima che i dati vengano analizzati in Customer Journey Analytics. <p>Le competenze di convalida dei dati consentono la convalida a richiesta, a livello di campo e a livello di set di dati, combinando riepiloghi statistici con il rilevamento intelligente di valori non validi o anomali. </p><p>L’utilizzo delle competenze di convalida dei dati riduce lo sforzo di controllo qualità manuale e accelera l’onboarding e le trasformazioni affidabili dei dati nei flussi di lavoro di ingegneria dei dati.</p><p>Il link alla documentazione seguirà a breve.<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/it/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | Fine di aprile 2026 <p>Rilascio originariamente pianificato per il mercoledì 31 marzo 2026</p> |
| **Server MCP per Customer Journey Analytics** <br/>È ora possibile collegare Customer Journey Analytics ai flussi di lavoro agenti esistenti utilizzando MCP (Model Context Protocol). Puoi richiedere rapporti e informazioni utilizzando il linguaggio naturale.<p>Il collegamento alla documentazione seguirà a breve.</p> | | Fine di aprile 2026 |
| **Servizi multimediali in streaming: supporto dei dati di pianificazione** <br/>È ora possibile caricare i dati di pianificazione di contenuti multimediali in streaming passati per tenere traccia in modo più semplice e preciso del pubblico.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare i dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 ottobre 2025 | Prima metà del 2026<p>Rilascio originariamente pianificato per il 29 ottobre 2025</p> |
| **Generazione rapporti API per più dimensioni**<br/> Generare rapporti su più dimensioni in una singola richiesta API ed eseguire ricerche a livello di dimensione. [Ulteriori informazioni](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | Marzo 2026 |
| **Ordinamento API a più colonne**<br/>&#x200B;È possibile ordinare più oggetti dimensione e metrica in una richiesta API. Puoi combinare dimensioni e metriche nella stessa definizione di ordinamento. [Ulteriori informazioni](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | Marzo 2026 |

## Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-442813, AN-442410, AN-442231, AN-441943, AN-441717, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Componenti**:
**Connessioni**: AN-442824, AN-440937, AN-440092, AN-429781
**Content Analytics**:
**Analisi guidata**:
**Esportazioni**:
**Visualizzazioni dati**: AN-442809, AN-434824, AN-434210, AN-424000
**Implementazione**:
**Report Builder**: AN-441136, AN-438147, AN-425150
**Generazione rapporti**: AN-443900, AN-441811, AN-441506, AN-440919, AN-440545, AN-440505, AN-440300
**Segmentazione**:
**Report pianificati**:
**Metriche e dimensioni condivise**:
**Altro**: AN-423359, AN-406242, AN-397985


## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| **Rimozione suite di cifratura TLS 1.2** | giovedì 11 febbraio 2026 | Avviso agli amministratori: il 27 maggio 2026 Adobe pianifica di rimuovere il supporto per le seguenti suite di cifratura TLS 1.2 dai server di raccolta dati di Adobe.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>Per la maggior parte delle implementazioni non è richiesta alcuna azione da parte del cliente. Questa modifica interessa principalmente i dati di Analytics inviati da applicazioni native legacy che utilizzano librerie TLS obsolete e un numero limitato di visitatori web su browser o sistemi operativi obsoleti. La rimozione del supporto per queste suite di crittografia migliora la sicurezza e allinea Adobe ai moderni standard di crittografia. Meno dello 0,1% del traffico di raccolta dati si basa attualmente su queste suite di cifratura.</p> |

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2025](/help/release-notes/2025.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
