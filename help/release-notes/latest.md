---
title: Note sulla versione di Customer Journey Analytics
description: Visualizza le note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7e98a1abbab4b954df5f7759879203c1d355fd50
workflow-type: tm+mt
source-wordcount: '1124'
ht-degree: 28%

---

# Note sulla versione corrente di Customer Journey Analytics (febbraio 2026)

**Ultimo aggiornamento**: giovedì 11 febbraio 2026

Queste note sulla versione coprono il periodo di rilascio di febbraio 2026. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ------- | ---- |
| **Sostituzioni intestazione** <p>In Content Analytics è possibile specificare un nome di intestazione e un valore di intestazione segreto. Questa [intestazione sostituisce la configurazione](/help/content-analytics/config/guided.md#header-overrides) in modo che Content Analytics invii intestazioni HTTP personalizzate per ignorare le tecnologie di rilevamento bot o traffico gate implementate.</p> |  | martedì 2 febbraio 2026 |
| **Includere più colonne di dimensione in una tabella a forma libera**<p>Ora è possibile includere fino a 5 colonne di dimensione in una tabella a forma libera, consentendo di visualizzare più elementi dimensionali uno accanto all’altro. Ogni riga di elementi dimensionali si comporta come un singolo elemento dimensionale concatenato.</p><p>Puoi applicare filtri, ordinamento, raggruppamenti e altro ancora alle tabelle a forma libera con più colonne di dimensioni per creare un’analisi più approfondita e personalizzata.</p><p>In precedenza, era possibile includere solo 1 colonna dimensione in una tabella a forma libera.</p><p>Per ulteriori informazioni, vedere [Includere più colonne di dimensione in una tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | giovedì 28 gennaio 2026 | giovedì 18 febbraio 2026 |
| **Ordinare le tabelle per più colonne**<p>Ora è possibile ordinare i dati di una tabella a forma libera in base a più colonne in Analysis Workspace, che si tratti di dimensioni o metriche.</p><p>Quando si ordinano dati per più colonne, i dati vengono ordinati in base alla priorità assegnata a ciascuna colonna. Accanto all’icona di ordinamento viene visualizzata la numerazione delle priorità.</p><p>Per ulteriori informazioni, vedere [Filtrare e ordinare tabelle a forma libera](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | giovedì 28 gennaio 2026 | giovedì 18 febbraio 2026 |
| **Miglioramenti all&#39;esportazione di tabelle complete**<p>L’esportazione di una tabella completa include i seguenti miglioramenti:</p><p>Miglioramenti alla creazione e alla configurazione delle esportazioni</p><ul><li>Crea un’esportazione dalla pagina Esportazioni. In precedenza, era possibile creare un’esportazione da Analysis Workspace solo facendo clic con il pulsante destro del mouse sulla tabella.</li><li>Aggiungi un nuovo account o percorso durante la creazione di un’esportazione.</li><li>Automatizza la creazione di nomi di file e il posizionamento delle cartelle per i file esportati. In questo modo i nomi dei file possono essere prevedibili e organizzati in cartelle in modo logico. In precedenza, i nomi dei file erano imprevedibili e raggruppati in un’unica cartella.</li><li>Supporto per l’esportazione di dati come file Parquet per una migliore compatibilità con data warehouse. In precedenza erano supportati solo CSV e JSON.</li></ul><p>Miglioramenti alla gestione delle esportazioni</p><ul><li>Rinnova o annulla una o più esportazioni dalla pagina Esportazioni.</li><li>Invia nuovamente una o più esportazioni dalla pagina Registri.</li><li>Invia un messaggio e-mail a singoli utenti o gruppi quando un’esportazione non riesce o sta per scadere.</li><li>Messaggi di errore più precisi per le esportazioni non riuscite.</li></ul><p>Miglioramenti di metriche calcolate, segmenti e dimensioni</p><ul><li>Supporto di funzioni metriche calcolate aggiuntive. In precedenza erano supportate solo semplici funzioni matematiche.</li><li>Applicare i segmenti durante la creazione di un’esportazione.</li><li>Supporto per dimensioni a doppio tipo di dati per una maggiore precisione.</li></ul><p>Miglioramenti amministrativi</p><ul><li>Gli amministratori ora possono visualizzare tutte le esportazioni e i registri, indipendentemente da chi li ha creati.</li></ul><p>Il collegamento alla documentazione seguirà a breve.</p> | giovedì 18 febbraio 2026 | giovedì 4 marzo 2026 |
| **Content Analytics: anteprime e miniature di visualizzazione a dispersione** <p>Quando visualizzi una visualizzazione a dispersione in Content Analytics, ora compare una miniatura della risorsa quando passi il cursore del mouse su un punto nel grafico. Questa miniatura consente di vedere in modo rapido e semplice quale contenuto viene rappresentato nel grafico.</p><p>Il collegamento alla documentazione seguirà a breve.</p> | mercoledì 17 febbraio 2026 | martedì 2 marzo 2026 |
| **Content Analytics: anteprime e anteprime delle visualizzazioni a barre** <p>Quando visualizzi una visualizzazione a barre orizzontali in Content Analytics, ora compare una miniatura della risorsa quando passi il cursore del mouse su una barra nel grafico. Questa miniatura consente di vedere in modo rapido e semplice quale contenuto viene rappresentato nel grafico.</p><p>Il collegamento alla documentazione seguirà a breve.</p> | martedì 23 febbraio 2026 | martedì 9 marzo 2026 |
| **Aggiornamento della funzione Approximate Count Distinct**<p>L&#39;algoritmo probabilistico HLL utilizzato nella funzione Approximate Count Distinct verrà presto aggiornato. L’output risultante per i numeri che utilizzano questa funzione potrebbe cambiare leggermente rispetto ai numeri storici, come segue:<ul><li>Quando si contano quantità molto piccole di valori univoci, i risultati saranno migliorati per utilizzare conteggi esatti anziché stime.</li><li>Quando si contano dati più grandi, le stime di conteggio manterranno la stessa precisione di prima di questo aggiornamento (le stime sono accurate entro il 5% del numero esatto, il 95% del tempo).</li></ul><p>Per ulteriori informazioni sulla funzione Approximate Count Distinct, vedere [Approximate Count Distinct](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) in [Funzioni avanzate](/help/components/calc-metrics/cm-adv-functions.md)</p> |  | Marzo 2026 |
| **Supporto per il mirroring dei dati**  <p>Grazie al supporto di schemi basati su modelli e alla funzionalità di modifica di acquisizione dati (CDC) per connettori di origine specifici in Experience Platform, Customer Journey Analytics sarà in grado di supportare la funzionalità di [mirroring dei dati](/help/data-mirror/data-mirror.md) delle soluzioni data warehouse come [!DNL Snowflake], [!DNL Azure Databricks] e [!DNL Google BigQuery].</p><p>Contatta il team Adobe Account per accedere alla versione Beta.</p> | Versione Beta: 24 settembre 2025 | Da definire |
| **Servizi di contenuti multimediali in streaming: supporto dei dati di pianificazione** <p>Ora puoi caricare i dati di pianificazione dei contenuti live in streaming per monitorare più facilmente e con precisione il pubblico.</p><p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare i dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 ottobre 2025 | Prima metà del 2026<p>Rilascio originariamente pianificato per il 29 ottobre 2025</p> |

## Correzioni in Customer Journey Analytics

**Analysis Workspace**: AN-421930, AN-424997, AN-424194, AN-425515, AN-425254, AN-423174, AN-428834, AN-306540, AN-426014, AN-427801
**Componenti**:
**Content Analytics**:
**Analisi guidata**:
**Esportazioni**: AN-422041, AN-421599, AN-422112
**Visualizzazioni dati**:
**Implementazione**:
**Report Builder**: AN-391415, AN-425125
**Generazione rapporti**: AN-425817, AN-424362, AN-425752, AN-425278, AN-422249, AN-403446, AN-424727, AN-426791, AN-427985
**Segmentazione**: AN-428905, AN-428232
**Rapporti pianificati**: AN-425484, AN-425137
**Metriche e dimensioni condivise**:
**Altro**: AN-428833, AN-425074


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
