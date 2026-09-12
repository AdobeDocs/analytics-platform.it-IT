---
title: Note sulla versione corrente di Customer Journey Analytics
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
source-git-commit: f3aad257d518373812176cb123d799b83cf45520
workflow-type: tm+mt
source-wordcount: 1261
ht-degree: 20%

---

# Note sulla versione corrente di Customer Journey Analytics (settembre 2026)

**Ultimo aggiornamento**: 9 settembre 2026

Queste note sulla versione coprono il periodo di rilascio di settembre 2026. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Plug-in server MCP Customer Journey Analytics**<br/> Utilizza i nuovi plug-in server MCP Customer Journey Analytics per ChatGPT e Claude per accedere rapidamente ai tuoi dati. <p>Per ulteriori informazioni, vedere [Connessione a ChatGPT](https://developer.adobe.com/analytics-mcp/docs/guides/chatgpt) e [Connessione a Claude](https://developer.adobe.com/analytics-mcp/docs/guides/claude).</p> | 1 settembre 2026 | 1 settembre 2026 |
| **Supporto per etichette di utilizzo dati aggiuntive**<br> Customer Journey Analytics ora supporta le seguenti etichette di utilizzo dati aggiuntive per gli elementi all&#39;interno di un set di dati:<ul><li>C2 - Limitare l’esportazione di dati di terze parti (disponibile ora)</li><li>C3 - Limitare la combinazione di dati direttamente identificabili (disponibile ora)</li><li>C9 - Limitare la scienza dei dati (il cui rilascio è pianificato per agosto o settembre)</li></ul><p>Per ulteriori informazioni, consulta [Etichette, criteri e azioni di marketing](/help/data-views/data-governance.md).</p> | | 3 settembre 2026 |
| **Filtro e reporting dei criteri di consenso**<br> Puoi ora segnalare i visitatori che corrispondono ai tuoi criteri di consenso di Adobe Experience Platform. Le dimensioni e le metriche dei criteri di consenso vengono aggiunte alle visualizzazioni dati della connessione.<p>Inoltre, puoi escludere i visitatori non autorizzati prima che i loro dati vengano acquisiti in Customer Journey Analytics.</p><p>Il link alla documentazione seguirà a breve.<!--For more information, see Consent reporting and filtering overview.--></p> | | Settembre 2026 |
| **Limitare i segmenti all&#39;intervallo di date del rapporto**<br/> I dati in un rapporto di Workspace possono estendersi oltre l&#39;intervallo di date del rapporto quando un segmento include componenti per l&#39;intervallo di date.<p>È ora disponibile una nuova opzione che consente di limitare i risultati all’intervallo di date del rapporto indipendentemente da qualsiasi componente data incluso nel segmento.</p><p>Questa opzione è disponibile quando crei o modifichi un segmento il cui contenitore di primo livello è Persona.</p><p>Per ulteriori informazioni, vedere [Generare segmenti](/help/components/segments/seg-builder.md#components).</p> | 26 agosto 2026 | 9 settembre 2026 |
| **Analizzare le esperienze dei clienti LLM in Analysis Workspace con Informazioni sulla conversazione**<br/> Customer Journey Analytics ora inserisce dati di chat non strutturati in Analysis Workspace, consentendo di creare rapporti sulle esperienze di navigazione e acquisto basate su LLM che si verificano nelle proprietà.<p>Con questa funzionalità è possibile:</p><ul><li>Raccogli i prompt, le risposte e i metadati degli agenti dagli agenti di conversazione (agenti personalizzati della tua organizzazione o Adobe Brand Concierge) tramite Web SDK.</li><li>Analizza l’intento, il tono e il sentiment in modo da comprendere cosa chiedono i clienti, come risponde il tuo agente e come i clienti percepiscono le loro interazioni.</li><li>Analizza in scala utilizzando lo schema, i set di dati e le visualizzazioni dati esistenti, quindi acquisisci informazioni in Analysis Workspace.</li><li>Connetti le conversazioni ai risultati legando le interazioni degli agenti ai percorsi di clienti più ampi, in modo da poter misurare l’impatto reale sulla conversione, sul coinvolgimento e altro ancora.</li></ul><p>In precedenza, le esperienze basate su LLM erano difficili da misurare e quasi impossibili da collegare ai percorsi di clienti esistenti.</p><p>Il collegamento alla documentazione seguirà a breve.</p> | | 22 settembre 2026 |
| **Generazione rapporti sulla popolazione totale**<br/>&#x200B;È ora possibile analizzare e creare rapporti sulle entità definite nei set di dati di profilo e di ricerca esistenti in una connessione Customer Journey Analytics. Tale analisi e reporting vanno oltre la serie temporale di eventi dai set di dati evento. <p>Questa funzionalità consente di abilitare nuove classi di query, metriche e definizioni di pubblico che riflettono l’intero ambito della base clienti di un’azienda.</p><p>Il collegamento alla documentazione seguirà a breve.</p> | | 22 settembre 2026 |
| **Avvisi orari**<br/>&#x200B;È ora possibile impostare la granularità temporale di un avviso su Oraria.<p>Gli avvisi orari sono destinati ai dati che arrivano entro una determinata ora. Se i dati hanno una latenza superiore a un’ora, una granularità più lunga garantisce che l’avviso valuti i dati completi. Se non sei sicuro di quanto tempo richiede l’invio dei dati, contatta un data engineer.</p>p>(Link alla documentazione da seguire).</p> | | Settembre 2026 |
| **La consegna degli avvisi rispetta rigorosamente il ritardo configurato**<br/> Gli avvisi vengono ora consegnati alla fine della finestra di ritardo impostata, indipendentemente dal fatto che i dati siano completi o ancora in ricezione per l&#39;intervallo di eventi specificato. Eventuali dati che arrivano dopo la finestra di ritardo non vengono inclusi nell’avviso.<p>In precedenza, gli avvisi includevano un controllo dell’elaborazione in background in attesa di dati in arrivo in ritardo, anche se ciò significava che gli avvisi venivano consegnati dopo la finestra di ritardo configurata.</p>p>(Link alla documentazione da seguire).</p> | | Settembre 2026 |
| **Integrazione di Adobe Brand Visibility**<br/> Connetti Adobe Brand Visibility con i dati Customer Journey Analytics della tua organizzazione in modo da poter misurare in che modo l&#39;individuazione basata sull&#39;intelligenza artificiale si traduce in un coinvolgimento reale del sito Web e in risultati di business.<p>Il collegamento alla documentazione seguirà a breve.</p> | | Settembre 2026 |
| **Nuove competenze per l&#39;aggiornamento e l&#39;implementazione in CX Enterprise Coworker**<br> Verranno acquisite da Coworker. Queste competenze aiutano a semplificare gli aggiornamenti e le implementazioni per Customer Journey Analytics:<ul><li>**Competenze nelle guide all&#39;implementazione**: genera un elenco personalizzato di passaggi e raccomandazioni per l&#39;aggiornamento o l&#39;implementazione. Le linee guida per l’aggiornamento e l’implementazione possono quindi essere trasformate in un progetto Collaboratore utilizzando un playbook predefinito.</li><li>**Competenze per l&#39;elenco di controllo dell&#39;implementazione e dell&#39;aggiornamento intelligente**: utilizza il progetto CoWorker per gestire e tenere traccia dell&#39;avanzamento dell&#39;implementazione rispetto all&#39;elenco di controllo dell&#39;implementazione o dell&#39;aggiornamento personalizzato, mantenere lo stato del progetto, collaborare tra team, assegnare attività e introdurre gate di approvazione laddove necessario.</li><li>**Competenze di convalida dei dati**: verifica che l&#39;implementazione sia configurata correttamente e allineata alle best practice.</li></ul><p>(Link alla documentazione da seguire.)</p> | | 30 settembre 2026 |

### Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373, AN-492801 488821, AN-488452, AN-486517, AN-478930, AN-468325
**Componenti**:
**Connessioni**: AN-451458, AN-365942
**Content Analytics**:
**Analisi guidata**: AN-485600
**Esportazioni**: AN-489161, AN-467131, AN-464746, AN-469034, AN-447252, AN-437803, AN-394444
**Visualizzazioni dati**: AN-478732, AN-468836, AN-467851, AN-487651, AN-423592
**Acquisizione dei dati**: AN-489829, AN-489722, AN-469451, AN-467436, AN-467049, AN-466087, AN-465049, AN-463524, AN-457433, AN-490288, AN-487500, AN-390916, AN-342311
**Implementazione**:
**Report Builder**: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695, AN-492330, AN-490564, AN-468293, AN-460921
**Generazione rapporti**: AN-479145, AN-469095, AN-468070, AN-467786, AN-456684, AN-465257, AN-422685, AN-406114, AN-356706, AN-322733
**Segmentazione**: AN-486561, AN-278260
**Rapporti pianificati**: AN-479157
**Metriche e dimensioni condivise**:
**Analisi del pubblico**: AN-468237, AN-462553
**Altro**: AN-469601, AN-462817, AN-362308, AN-349757, AN-326432, AN-326345, AN-324341, AN-309317

## Funzioni posticipate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Servizi di contenuti multimediali in streaming: supporto dei dati di pianificazione** <br/>Puoi caricare dati di pianificazione di precedenti contenuti live multimediali in streaming per monitorare l’audience con maggiore facilità e precisione.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con la pianificazione del caricamento dei dati:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 ottobre 2025 | Da definire<p>(Originariamente previsto per il 29 ottobre 2025)</p> |

>[!MORELIKETHIS]
>
>* [Note sulla versione precedente di Customer Journey Analytics per il 2026](/help/release-notes/2026.md)
>* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
>* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
>* [Note sulla versione di CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
>* [Aggiornamenti alla documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)

