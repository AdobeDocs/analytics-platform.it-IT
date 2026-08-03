---
title: Note sulla versione corrente di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 2f745f65808e47fd6c0862fe23b6de6ca12ecfff
workflow-type: tm+mt
source-wordcount: 826
ht-degree: 32%

---

# Note sulla versione corrente di Customer Journey Analytics (luglio 2026)

**Ultimo aggiornamento**: 8 luglio 2026

Queste note sulla versione coprono il periodo di rilascio di luglio 2026. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Integrazione Brand Visibility**<br> La [Integrazione Brand Visibility in entrata](/help/integrations/bv.md#inbound-integration) consente di acquisire dati Brand Visibility in Customer Journey Analytics per ulteriori analisi. | 28 luglio 2026 | 28 luglio 2026 |
| **Analisi sub-evento** <br/>[Analisi sub-evento](/help/components/segments/sub-event.md) consente di analizzare i dati a un livello più granulare del livello evento. Invece di filtrare eventi interi, puoi segmentare singoli contenitori all’interno di un evento. <p>Ad esempio, puoi creare segmenti per una categoria di prodotti specifica senza includere tutti gli altri prodotti acquistati nello stesso ordine. È inoltre possibile definire oggetti o array che fanno parte dei dati evento come [contenitori personalizzati](/help/data-views/create-dataview.md#custom-containers) separati all&#39;interno di una visualizzazione dati. | 21 luglio 2026 | Fine di luglio 2026 |
| **B2B edition: supporto per set di dati ad hoc e relazionali** <br/>I set di dati ad hoc e relazionali sono ora supportati anche nelle connessioni basate su account in Customer Journey Analytics B2B edition.<p>Il collegamento alla documentazione seguirà a breve.</p> | | 20 luglio 2026 |
| **Collaboratore aziendale CX: Analizza dati Customer Journey Analytics** <br/>La chat di Collaboratore aziendale CX Adobe ora può eseguire analisi avanzate dei dati che in precedenza erano possibili solo in Analysis Workspace. Chat con collaboratori accede ai dati dalle visualizzazioni dati di Customer Journey Analytics, consentendoti di esplorarli e ottenere risposte a prompt in linguaggio naturale.<p>Per ulteriori informazioni, vedere [Analizzare i dati di Customer Journey Analytics tramite Chat con coworking](https://experienceleague.adobe.com/en/docs/cx-enterprise-coworker/content/chat/analytics-chat).</p> | | 23 luglio 2026 |
| **CX Enterprise Coworker: convalida i dati durante la migrazione da Adobe Analytics a Customer Journey Analytics** <br/>Una nuova abilità in CX Enterprise Coworker consente di convalidare i dati dell&#39;implementazione Customer Journey Analytics rispetto ai dati dell&#39;implementazione Adobe Analytics esistente. <p>Questa abilità confronta automaticamente ogni dimensione, metrica e tendenza singolarmente in base alle esigenze. Può anche confrontare tutte le suite di rapporti di Adobe Analytics con tutte le visualizzazioni dati di Customer Journey Analytics. L’abilità genera quindi informazioni basate sull’intelligenza artificiale e consigli da implementare per facilitare la migrazione a Customer Journey Analytics.</p><p>Per ulteriori informazioni, vedere [Convalidare i dati con Coworker durante l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/data-validation-aa-cja).</p> | | 24 luglio 2026 |
| **Le classificazioni in linea**<br/>[ Classificazioni in linea](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md#inline-classifications) consentono di rinominare o combinare le righe in una tabella a forma libera. E per creare un campo derivato dalle righe modificate di una tabella. | 20 luglio 2026 | 25 luglio 2026 |
| **Content Analytics: dati multimediali a pagamento** <br/>I file multimediali a pagamento sono ora disponibili come terzo canale per Content Analytics.<p>Il collegamento alla documentazione seguirà a breve.</p> | | 31 luglio 2026 |
| **Aggiornamento dell&#39;interfaccia di utilizzo delle connessioni** <br/>Nell&#39;interfaccia [Utilizzo](/help/connections/manage-connections.md#usage) durante la gestione delle connessioni è ora possibile visualizzare i dettagli di utilizzo per ogni singolo modulo, ad esempio Customer Journey Analytics o Customer Journey Analytics B2B edition. <br/>È inoltre possibile suddividere i report sull&#39;utilizzo per ciascuno dei moduli per mese. | 23 luglio 2026 | 30 luglio 2026 |

### Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-457527, AN-451161, AN-459034, AN-458071, AN-458398
**Componenti**:
**Connessioni**: AN-457065
**Content Analytics**:
**Analisi guidata**:
**Esportazioni**:
**Visualizzazioni dati**: AN-453201
**Acquisizione dati**:
**Implementazione**:
**Report Builder**: AN-457533, AN-453683
**Generazione rapporti**: AN-457607, AN-447692, AN-451259, AN-455713
**Segmentazione**:
**Rapporti pianificati**: AN-450715
**Metriche e dimensioni condivise**:
**Analisi del pubblico**:
**Altro**: AN-457063

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

