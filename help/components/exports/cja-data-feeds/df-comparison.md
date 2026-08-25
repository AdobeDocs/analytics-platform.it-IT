---
description: Scopri come confrontare la funzionalità dei feed dati in Customer Journey Analytics e Adobe Analytics
keywords: clickstream;feed dati;datafeed;feed dati
title: Confrontare la funzionalità dei feed di dati in Customer Journey Analytics e Adobe Analytics
feature: Components
hide: true
exl-id: 32b71016-7c53-409f-9ce4-521a40e2eb96
autotag-review: '2026-05-19T08:44:26.806Z'
TQID: 'https://experienceleague.adobe.com/R7c5-VutwSkyghNvwC2gZv2KUEJoa263AN0Tkdg3w4o'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 82ccb1359540e5200641b33c3d4aef7f2447003f
workflow-type: tm+mt
source-wordcount: 1451
ht-degree: 1%

---

# Confrontare i feed di dati in Customer Journey Analytics e Adobe Analytics

{{release-limited-testing}}

I feed di dati sia in Customer Journey Analytics che in Adobe Analytics consentono di esportare dati non elaborati in piattaforme di terze parti.

Se in precedenza hai utilizzato feed di dati in Adobe Analytics, utilizza le seguenti informazioni per comprendere le differenze nelle funzioni e nei concetti disponibili:

## Funzioni disponibili solo nei feed dati di Customer Journey Analytics

Se esegui la migrazione da Adobe Analytics, le seguenti funzioni sono nuove nei feed dati di Customer Journey Analytics:

* **Campi derivati**: componenti personalizzati creati da trasformazioni basate su regole che possono essere inclusi nello schema del feed.

* **Unione**: risoluzione identità tra dispositivi che collega gli eventi tra dispositivi a una singola persona.

* **Modello dati strutturato**: i feed vengono generati e consegnati utilizzando dati strutturati anziché stringhe flat.

* **Barra dei componenti di Analysis Workspace**: seleziona dimensioni e metriche utilizzando la stessa barra dei componenti di Analysis Workspace, anziché un elenco statico di nomi di variabili.

* **Segmentazione**: i segmenti applicati alla visualizzazione dati vengono ereditati automaticamente e altri segmenti possono essere applicati direttamente al feed.

* **Fuso orario della visualizzazione dati**: le finestre di consegna dei feed sono allineate al fuso orario della visualizzazione dati.

* **Output Parquet**: i file vengono consegnati in formato Parquet e supportano in modo nativo dati nidificati e strutturati complessi.

* **Percorsi di partizione in stile hive**: i file di output utilizzano percorsi in stile hive per eseguire query efficienti negli ambienti del data lake.

* **Propagazione aggiornamento componente**: le modifiche ai componenti nella visualizzazione dati vengono propagate automaticamente al feed.

<!-- * Web MCP when it's added -->

La tabella [Confronto funzionalità](#functionality-comparison) seguente descrive in dettaglio ciascuna di queste funzionalità, insieme alle differenze nelle funzionalità esistenti in entrambi i prodotti.


## Confronto delle funzionalità

| **Concetti e opzioni di configurazione** | **Customer Journey Analytics** | **Adobe Analytics** |
|---------|----------|---------|
| **Input dati**<br/> Tipo di dati che è possibile raccogliere e includere nei feed di dati. | Supporta l’input di dati cross-channel, tra cui dati web, dati dei call center, dati dei punti vendita e altro ancora. | Supporta principalmente l’input di dati web e mobili. Altri tipi di dati (come i dati dei call center o dei punti vendita) possono essere acquisiti tramite origini di dati, ma con funzionalità di elaborazione molto limitate. |
| **Elaborazione dati**<br/> I dati vengono elaborati in fasi diverse, a seconda del prodotto in uso. | I dati vengono elaborati al **momento del rapporto**, pertanto molte funzionalità di reporting possono essere utilizzate per modificare i dati storici, ad esempio unione, campi derivati e segmentazione. | I dati vengono elaborati al **momento della raccolta**, pertanto le funzionalità di reporting come le regole di elaborazione e le regole VISTA non influiscono sui dati storici. |
| **Unione**<br/> Risoluzione delle identità cross-device e cross-channel che collega gli eventi a una singola persona. | Supportato. Le identità unite possono essere incluse nelle esportazioni di feed di dati quando l’unione è configurata sulla connessione. | Non supportato. L’identità del visitatore viene determinata al momento della raccolta dai cookie dell’ID visitatore; non è disponibile alcuna risoluzione cross-device successiva alla raccolta. |
| **Frequenza di consegna**<br/> Determina la frequenza con cui il feed di dati viene inviato e la finestra di tempo inclusa nel feed. | **Giornaliero** (dalla mezzanotte alla mezzanotte nel fuso orario della visualizzazione dati) o **Orario**. | **Giornaliero** (dalla mezzanotte alla mezzanotte nel fuso orario della suite di rapporti) o **Orario**. <p>I feed di 15 minuti sono possibili ma non disponibili per impostazione predefinita.</p> |
| **Risultati con arrivo in ritardo**<br/> I cui timestamp appartengono a una finestra di frequenza di consegna precedente, ma arrivano dopo che tale finestra è già trascorsa. <p>Ad esempio, gli hit in arrivo tardivo potrebbero provenire da un’app mobile che memorizza in buffer gli eventi mentre è offline e li invia quando si riconnette.</p> | L&#39;impostazione **Ritardo elaborazione** controlla per quanto tempo il sistema attende dopo la chiusura della finestra di frequenza prima di attivare l&#39;esportazione, consentendo un tempo supplementare per l&#39;arrivo dei dati ritardati. | Gli hit in arrivo possono essere **inclusi o esclusi** tramite l&#39;opzione di configurazione **Hit in arrivo ritardato**. <p>L&#39;impostazione dell&#39;**Intervallo di lookback** controlla la distanza che il sistema raggiunge per includere i dati ritardati.</p> |
| **Risultati fuori servizio**<br/> I cui timestamp non corrispondono all&#39;ordine in cui sono stati ricevuti. | Poiché Customer Journey Analytics accetta sia dati in streaming che in batch, non c’è garanzia che gli eventi per una determinata persona arrivino in ordine di marca temporale. Anche se Customer Journey Analytics riordina per marca temporale per persona, può esportare solo i dati arrivati. Ciò significa che gli hit in arrivo tardivo potrebbero essere esportati dopo gli hit con una marca temporale successiva.<p>L&#39;impostazione **Ritardo elaborazione** consente di ridurre gli eventi fuori servizio nell&#39;output del feed dati, dando più tempo per l&#39;arrivo dei dati batch prima dell&#39;esportazione. L’ordine degli eventi nella consegna non è garantito.</p><p>**Importante**: il consumatore finale dei dati del feed di dati deve essere in grado di gestire marche temporali non ordinate, per persona, perché l&#39;ordine degli hit nella consegna del feed di dati non è garantito.</p> | Adobe Analytics richiede che i dati arrivino in ordine per visitatore al momento della raccolta, ma l’ordine degli hit nella consegna del feed di dati non è garantito.</p> |
| **Finestra di backfill**<br/> Esporta i dati storici tra due date precedenti. | Limitato alla finestra continua dei dati della connessione. | Limitato al limite di conservazione dei dati della suite di rapporti: **25 mesi** per impostazione predefinita. |
| **Schema**<br/> Lo schema feed dati determina quali colonne sono disponibili per l&#39;inclusione in un feed dati. | Lo schema del feed dati si basa sulla configurazione della visualizzazione dati.  I componenti disponibili per l’inclusione nello schema feed dati sono un sottoinsieme dei componenti disponibili nella configurazione della visualizzazione dati. | Elenco statico predefinito di oltre 1.100 variabili. Molte colonne vengono esportate come **coppie pre- e post-elaborate** (ad esempio, `eVar1` / `post_eVar1`), che rappresenta gran parte del conteggio delle colonne. |
| **Generatore feed dati**<br/> Interfaccia utilizzata per configurare le colonne incluse in un feed dati. | Utilizza una barra dei componenti con le stesse dimensioni e metriche denominate disponibili nella visualizzazione dati, in base all’esperienza Analysis Workspace. | Utilizza un elenco semplice di nomi di variabili non elaborati (ad esempio `eVar1`, `prop5`) selezionati da un set predefinito di circa 1.100+ colonne. I componenti non vengono denominati o descritti oltre il loro identificatore di variabile. |
| **Campi derivati**<br/> Componenti personalizzati definiti utilizzando trasformazioni basate su regole applicate al momento della generazione del rapporto. | Supportato. I componenti dei campi derivati possono essere inclusi nello schema del feed dati insieme a dimensioni e metriche standard. | Non supportato. |
| **Aggiornamenti dei componenti**<br/> Indica se le modifiche alla configurazione dei componenti verranno applicate all&#39;output dei feed di dati futuri. | Le modifiche ai componenti nella visualizzazione dati (ad esempio la ridenominazione o la rimozione di una dimensione) si propagano automaticamente ai feed di dati futuri. | Non applicabile. Lo schema a colonne è predefinito e statico; non sono presenti componenti a livello di visualizzazione dati da aggiornare. |
| **Ricerche**<br/> Le ricerche dinamiche ti consentono di ricevere file di ricerca aggiuntivi nel feed di dati, altrimenti non disponibili. | Non necessario, perché le ricerche e le classificazioni sono entrambe disponibili come dimensioni curate direttamente nella visualizzazione dati. Quando curi una ricerca o una classificazione come dimensione nella visualizzazione dati, i valori risolti vengono visualizzati come colonne regolari nell’output Parquet, in linea con i dati dell’evento, non come file di riferimento separati. | Utilizzato per far corrispondere un numero da una colonna di feed dati a un valore effettivo. Specifiche per determinati set di elementi (browser, sistema operativo, dispositivo mobile e vengono applicate come file separato fornito con il feed di dati). |
| **Definizione della sessione**<br/> Definizione del limite di una visita o di una sessione, che influisce sul modo in cui gli eventi vengono raggruppati e attribuiti. | Definito nella visualizzazione dati. | Definito al momento della raccolta. |
| **Segmentazione**<br/> La possibilità di filtrare l&#39;output del feed dati utilizzando i segmenti. | I segmenti applicati alla visualizzazione dati vengono ereditati automaticamente dal feed di dati. Ulteriori segmenti possono essere applicati direttamente a un singolo feed di dati. | Non supportato. I feed di dati esportano tutti i dati raccolti senza filtrare i segmenti. |
| **Metriche calcolate**<br/> Metriche personalizzate che è possibile creare dalle metriche esistenti. | Non disponibile | Non disponibile |
| **Modello di persistenza**<br/> Specificare se i valori delle dimensioni persistono da un evento all&#39;altro. | Flessibile. Le impostazioni di persistenza dalla visualizzazione dati (allocazione e scadenza) vengono applicate al momento della generazione del feed. Supporta tutte le impostazioni di allocazione disponibili in una visualizzazione dati: **Originale**, **Più recente**, **Tutto**, **Primo noto** e **Ultimo noto**. | Sono rappresentati solo i modelli di attribuzione **più recenti (ultimo contatto)** e **originali (primo contatto)**. L’allocazione lineare viene gestita come l’ultimo contatto. |
| **Formato del file di output**<br/> Formato utilizzato per i file di output del feed di dati recapitati nella destinazione cloud. | Parquet<p>Supporta in modalità nativa dati nidificati e strutturati complessi. Gli elenchi di prodotti sono rappresentati come array strutturati/oggetti nidificati. </p><p>Richiede uno strumento che riconosca il Parquet per leggere, come BigQuery, Snowflake o Apache Spark.</p> | TSV<p>Righe piatte leggibili dall&#39;utente. Non supporta i dati strutturati in modo nativo; i campi complessi come gli elenchi di prodotti devono essere codificati come stringhe delimitate proprietarie che richiedono una logica di analisi personalizzata.</p> |
| **Percorsi dei file di output**<br/> Struttura di directory utilizzata per i file di output consegnati. | Utilizza **Percorsi di partizione in stile hive** (ad esempio, `year=2024/month=01/day=15/`), consentendo l&#39;eliminazione efficiente delle partizioni durante l&#39;esecuzione di query sui dati in ambienti di data lake come Databricks o Apache Spark. | Utilizza una struttura di directory piatta. I percorsi in stile hive non sono supportati. |
| **Destinazioni di consegna**<br/> I percorsi di archiviazione cloud in cui è possibile inviare i file di output del feed di dati. | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform. | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform. <p>Supporta anche **SFTP**.</p> |

{style="table-layout:auto"}

