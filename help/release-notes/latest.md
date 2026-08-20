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
source-git-commit: b65a411e35963b97ab159e8c3b61010927ea911d
workflow-type: tm+mt
source-wordcount: 984
ht-degree: 28%

---

# Note sulla versione corrente di Customer Journey Analytics (agosto 2026)

**Ultimo aggiornamento**: 5 agosto 2026

Queste note sulla versione coprono il periodo di rilascio di agosto 2026. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Miglioramenti all&#39;area di lavoro di Percorso**<br> Sono ora disponibili i seguenti miglioramenti all&#39;area di lavoro di Percorso:<ul><li>Confrontare il percorso con un intervallo di tempo precedente. Confrontare il percorso corrente con il percorso 4 settimane prima, 2 trimestri prima, 1 anno prima o con un intervallo di date personalizzato.</li><li>Per un nodo selezionato, mostra gli elementi dimensionali principali che seguono il nodo selezionato in qualsiasi punto del percorso. Utilizzalo quando il nodo selezionato è l’evento chiave nell’analisi e vuoi vedere cosa fanno le persone in qualsiasi momento successivo.<p>In precedenza, potevano essere visualizzati solo i primi nodi immediati prima o dopo il nodo selezionato. </p></li><li>Modificare la forma e lo stile delle frecce tra i nodi. Trascinare le frecce tra i nodi per modificare la forma (curvatura) della freccia e fare clic con il pulsante destro del mouse su una freccia per modificarne lo stile in uno dei seguenti modi: continua, tratteggiata, punteggiata, tratteggiata o animata.</li></ul><p></p>Per ulteriori informazioni, consulta [Configurare le visualizzazioni in un’Area di lavoro del percorso](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md). |  | 18 agosto 2026 |
| **Supporto per etichette di utilizzo dati aggiuntive**<br> Customer Journey Analytics ora supporta le seguenti etichette di utilizzo dati aggiuntive per gli elementi all&#39;interno di un set di dati:<ul><li>C2 - Limitare l’esportazione di dati di terze parti (disponibile ora)</li><li>C3 - Limitare la combinazione di dati direttamente identificabili (disponibile ora)</li><li>C9 - Limitare la scienza dei dati (il cui rilascio è pianificato per agosto o settembre)</li></ul><p>Per ulteriori informazioni, consulta [Etichette, criteri e azioni di marketing](/help/data-views/data-governance.md).</p> | | Agosto o settembre 2026 |
| **Content Analytics: dati multimediali a pagamento** <br/>I file multimediali a pagamento sono ora disponibili come terzo canale per Content Analytics.<p>Il collegamento alla documentazione seguirà a breve.</p> | | 31 agosto 2026 |
| **B2B: l&#39;unione tra persone e account**<br> l&#39;unione degli account B2B arricchisce i set di dati dell&#39;evento con le informazioni sull&#39;account e consente l&#39;analisi completa in tutto il percorso di clienti di Customer Journey Analytics. <p>Quando gli eventi non dispongono di un ID account, richiesto da Customer Journey Analytics B2B edition per l’acquisizione, l’unione di account deriva e aggiunge automaticamente tali informazioni utilizzando il set di dati di mappatura persona-account fornito.</p><p>Il collegamento alla documentazione seguirà a breve.</p> | | Fine di agosto o settembre 2026 |
| **Guida alle prime chiamate dell&#39;API di report di CJA**<br> La guida alle prime chiamate dell&#39;API di Adobe Customer Journey Analytics fornisce istruzioni ed esempi per configurare le richieste di report di base. | | 10 agosto 2026 |
| **Guida con tendenze per la data API di report di CJA**<br> La guida con tendenze per la data API di Adobe Customer Journey Analytics fornisce istruzioni ed esempi per configurare le richieste di report di base. | | 17 agosto 2026 |
| **Limitare i segmenti all&#39;intervallo di date del rapporto**<br/> I dati in un rapporto di Workspace possono estendersi oltre l&#39;intervallo di date del rapporto quando un segmento include componenti per l&#39;intervallo di date.<p>È ora disponibile una nuova opzione che consente di limitare i risultati all’intervallo di date del rapporto indipendentemente da qualsiasi componente data incluso nel segmento. <p>Questa opzione è disponibile quando crei o modifichi un segmento il cui contenitore di primo livello è Persona.</p><p>Per ulteriori informazioni, vedere [Generare segmenti](/help/components/segments/seg-builder.md#components).</p> | 26 agosto 2026 | 9 settembre 2026 |
| **Filtro e reporting dei criteri di consenso**<br> Puoi ora segnalare i visitatori che corrispondono ai tuoi criteri di consenso di Adobe Experience Platform. Le dimensioni e le metriche dei criteri di consenso vengono aggiunte alle visualizzazioni dati della connessione.<p>Inoltre, puoi escludere i visitatori non autorizzati prima che i loro dati vengano acquisiti in Customer Journey Analytics.</p><p>Il link alla documentazione seguirà a breve.<!--For more information, see Consent reporting and filtering overview.--></p> | | Settembre 2026 |

### Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-466867, AN-465995, AN-465315, AN-465313, AN-464375, AN-463634, AN-463248, AN-463175, AN-463049, AN-462347, AN-462124, AN-461922, AN-458398, AN-457849, AN-455002, AN-453357, AN-456863, AN-459816, AN-459034, AN-460774 460671 457760 443594, AN-, AN-, AN-, AN-
**Componenti**:
**Connessioni**: AN-464934, AN-460768
**Content Analytics**:
**Analisi guidata**:
**Esportazioni**: AN-451819, AN-448419, AN-456001
**Visualizzazioni dati**: AN-453201, AN-441965, AN-460967
**Acquisizione dei dati**: AN-462123, AN-451836, AN-453790, AN-459000, AN-456057, AN-461271, AN-459016, AN-460935
**Implementazione**:
**Report Builder**: AN-465346, AN-464768, AN-464580, AN-464301, AN-463048, AN-462800, AN-457042, AN-461033, AN-459042, AN-454250, AN-451735, AN-450776, AN-450200, AN-451665
**Generazione rapporti**: AN-463576, AN-462400, AN-456394, AN-455619, AN-459530, AN-454103, AN-452866, AN-461181
**Segmentazione**: AN-459002, AN-457730, AN-457146
**Rapporti pianificati**: AN-455009, AN-460037, AN-462093
**Metriche e dimensioni condivise**:
**Analisi del pubblico**: AN-458292
**Altro**: AN-466935, AN-462116, AN-454493, AN-457666, AN-457557, AN-456742, AN-437975, AN-460959

## Funzioni posticipate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Servizi multimediali in streaming: supporto dei dati di pianificazione** <br/>Ora puoi caricare dati di pianificazione di precedenti contenuti live multimediali in streaming per monitorare l’audience con maggiore facilità e precisione.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data). | 29 ottobre 2025 | Da definire<p>(Originariamente previsto per il 29 ottobre 2025)</p> |

>[!MORELIKETHIS]
>
>* [Note sulla versione precedente di Customer Journey Analytics per il 2026](/help/release-notes/2026.md)
>* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
>* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
>* [Note sulla versione di CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
>* [Aggiornamenti alla documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)

