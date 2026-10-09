---
title: Note sulla versione corrente di Customer Journey Analytics
description: Consulta le ultime note sulla versione di Customer Journey Analytics, incluse nuove funzioni, problemi risolti e versioni rimandate per il periodo corrente.
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
    internal-label: Templates
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
    internal-label: Audiences
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
    internal-label: Connections
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: c9d7bb10d15aa25bf3fa6dcd2e95fea39cd6faf7
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 27%
---
# Note sulla versione corrente di Customer Journey Analytics (ottobre 2026)

**Ultimo aggiornamento**: 7 ottobre 2026

Queste note sulla versione coprono il periodo di rilascio di ottobre 2026. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Autorizzazione di sola lettura per il server Customer Journey Analytics MCP**<br/> Gli amministratori ora possono concedere agli utenti l&#39;accesso in sola lettura al server Customer Journey Analytics MCP. Il nuovo elemento di autorizzazione [!UICONTROL Accesso in sola lettura MCP] consente agli utenti di accedere a tutti gli strumenti di sola lettura, senza consentire loro di creare progetti, segmenti o metriche calcolate.<p>L&#39;elemento di autorizzazione esistente [!UICONTROL Accesso MCP] è stato rinominato [!UICONTROL Accesso completo MCP]. Gli utenti con questa autorizzazione possono accedere a tutti gli strumenti, compresi quelli che creano, modificano o eliminano componenti.</p><p>Per ulteriori informazioni, vedere [Impostare le autorizzazioni](https://developer.adobe.com/analytics-mcp/docs/guides/permissions) nella documentazione del server Customer Journey Analytics MCP.</p> | | 6 ottobre 2026 |
| **Analizzare le esperienze dei clienti LLM in Analysis Workspace con Informazioni sulla conversazione**<br/> Customer Journey Analytics ora inserisce dati di chat non strutturati in Analysis Workspace, consentendo di creare rapporti sulle esperienze di navigazione e acquisto basate su LLM che si verificano nelle proprietà.<p>Con questa funzionalità è possibile:</p><ul><li>Raccogli i prompt, le risposte e i metadati degli agenti dagli agenti di conversazione (agenti personalizzati della tua organizzazione o Adobe Brand Concierge) tramite Web SDK.</li><li>Analizza l’intento, il tono e il sentiment in modo da comprendere cosa chiedono i clienti, come risponde il tuo agente e come i clienti percepiscono le loro interazioni.</li><li>Analizza in scala utilizzando lo schema, i set di dati e le visualizzazioni dati esistenti, quindi acquisisci informazioni in Analysis Workspace.</li><li>Connetti le conversazioni ai risultati legando le interazioni degli agenti ai percorsi di clienti più ampi, in modo da poter misurare l’impatto reale sulla conversione, sul coinvolgimento e altro ancora.</li></ul><p>In precedenza, le esperienze basate su LLM erano difficili da misurare e quasi impossibili da collegare ai percorsi di clienti esistenti.</p><p>Per ulteriori informazioni, vedere [Informazioni sulla conversazione](/help/conversation-insights/overview.md).</p> | | 8 ottobre 2026<p>(Originariamente pianificato per il 22 settembre 2026)</p> |
| **Genera automaticamente le descrizioni dei componenti** <br/>Ora puoi generare automaticamente le descrizioni per dimensioni, metriche, metriche calcolate, segmenti e intervalli di date. Questo consente agli utenti di Workspace di capire quali componenti utilizzare, soprattutto nelle organizzazioni con librerie di componenti di grandi dimensioni. <p>È possibile generare una descrizione per un singolo componente o per più componenti contemporaneamente.</p> <p>Il link alla documentazione seguirà a breve.<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 28 ottobre 2026 |
| **Integrazione di Adobe Brand Visibility**<br/> Connetti Adobe Brand Visibility con i dati Customer Journey Analytics della tua organizzazione in modo da poter misurare in che modo l&#39;individuazione basata sull&#39;intelligenza artificiale si traduce in un coinvolgimento reale del sito Web e in risultati di business.<p>Il collegamento alla documentazione seguirà a breve.</p> | | Ottobre 2026 |


### Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-495340, AN-494789, AN-493307, AN-468900
**Componenti**: AN-492523
**Connessioni**: AN-492236
**Content Analytics**:
**Analisi guidata**: AN-495592
**Esportazioni**: AN-495077, AN-494337, AN-486563, AN-469919, AN-462560, AN-462372
**Visualizzazioni dati**: AN-492093, AN-467770, AN-455367, AN-444467
**Acquisizione dei dati**: AN-496439, AN-495339, AN-493456, AN-491984, AN-490515, AN-490479, AN-470065
**Implementazione**:
**Report Builder**: AN-496602, AN-494224, AN-493737, AN-493508, AN-493505, AN-492806, AN-468981, AN-454376
**Generazione rapporti**: AN-495661, AN-493562, AN-487058, AN-478768
**Segmentazione**:
**Rapporti pianificati**: AN-491103, AN-468049
**Metriche e dimensioni condivise**: AN-493722
**Analisi del pubblico**: AN-469101
**Altro**: AN-493865

## Funzioni posticipate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Generazione rapporti sulla popolazione totale**<br/>&#x200B;È ora possibile analizzare e creare rapporti sulle entità definite nei set di dati di profilo e di ricerca esistenti in una connessione Customer Journey Analytics. Tale analisi e reporting vanno oltre la serie temporale di eventi dai set di dati evento. <p>Questa funzionalità consente di abilitare nuove classi di query, metriche e definizioni di pubblico che riflettono l’intero ambito della base clienti di un’azienda.</p><p>Il collegamento alla documentazione seguirà a breve.</p> | | Da definire<p>(Originariamente pianificato per il 22 settembre 2026)</p> |
| **Servizi di contenuti multimediali in streaming: supporto dei dati di pianificazione** <br/>Puoi caricare dati di pianificazione di precedenti contenuti live multimediali in streaming per monitorare l’audience con maggiore facilità e precisione.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con la pianificazione del caricamento dei dati:</p><ul><li>Piattaforme FAST (Free Ad-Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 ottobre 2025 | Da definire<p>(Originariamente previsto per il 29 ottobre 2025)</p> |

>[!MORELIKETHIS]
>
>* [Note sulla versione precedente di Customer Journey Analytics per il 2026](/help/release-notes/2026.md)
>* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
>* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
>* [Note sulla versione di CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
>* [Aggiornamenti alla documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)

