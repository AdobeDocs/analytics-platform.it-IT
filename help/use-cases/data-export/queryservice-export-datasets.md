---
title: Servizio query di Experience Platform (Data Distiller) ed esporta set di dati
description: Descrive come utilizzare Query Service (Data Distiller) ed esportare set di dati per esportare i dati.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 14a90758-91eb-4610-8802-1edfdb8b9689
source-git-commit: 20ead546897ad517840f95a5ec4dcd7f830afe8c
workflow-type: tm+mt
source-wordcount: '2642'
ht-degree: 2%

---

# Servizio query (Data Distiller) ed esporta set di dati

Questo articolo illustra come utilizzare la combinazione di Experience Platform Query Service (Data Distiller) ed esportazione di set di dati per implementare i seguenti [casi d&#39;uso per l&#39;esportazione di dati](overview.md):

- Convalida dei dati
- Data Lake, Data Warehouse di strumenti BI
- Preparazione per l’apprendimento intelligente e automatico artificiale.


Adobe Analytics può implementare questi casi d&#39;uso utilizzando la funzionalità [Feed dati](https://experienceleague.adobe.com/it/docs/analytics/export/analytics-data-feed/data-feed-overview). I feed di dati offrono un modo potente per estrarre dati non elaborati da Adobe Analytics. Questo articolo descrive come estrarre un tipo simile di dati non elaborati da Experience Platform, in modo da poter implementare i casi d’uso sopra menzionati. Se applicabile, le funzionalità descritte in questo articolo vengono confrontate con i feed di dati di Adobe Analytics per chiarire le differenze nei dati e nei processi.

## Introduzione

L’esportazione dei dati tramite Query Service (Data Distiller) e l’esportazione di set di dati consiste in:

- definizione di una **query pianificata** che genera i dati per il feed dati come set di dati di output ![set di dati di output](../assets/output-dataset.svg), utilizzando **Query Service**.
- definizione di un&#39;**esportazione pianificata del set di dati** che esporta il set di dati di output in una destinazione di archiviazione cloud, utilizzando **esportazione del set di dati**.

![Feed dati](../assets/queryservice-export-datasets.svg)


## Prerequisiti

Prima di utilizzare la funzionalità descritta in questo caso d’uso, assicurati di soddisfare tutti i seguenti requisiti:

- Un’implementazione funzionante che raccoglie dati nel data lake di Experience Platform.
- Accedere al componente aggiuntivo Data Distiller per assicurarsi di avere i diritti per eseguire query batch. Per ulteriori informazioni, vedere [Pacchetto servizio query](https://experienceleague.adobe.com/en/docs/experience-platform/query/packaging).
- Accesso alla funzionalità Esporta set di dati, disponibile quando hai acquistato il pacchetto Real-Time CDP Prime o Ultimate, Adobe Journey Optimizer o Customer Journey Analytics. Per ulteriori informazioni, consulta [Esportare i set di dati nelle destinazioni dell&#39;archiviazione cloud](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/export-datasets).
- Una o più destinazioni configurate (ad esempio: Amazon S3, Google Cloud Storage) in cui esportare i dati non elaborati del feed di dati.


## Servizio query

Experience Platform Query Service consente di eseguire query e unire qualsiasi set di dati nel data lake di Experience Platform come se si trattasse di una tabella di database. Puoi quindi acquisire i risultati come nuovo set di dati da utilizzare ulteriormente nel reporting o per l’esportazione.

È possibile utilizzare l&#39;interfaccia utente di Query Service [1}, un client ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/overview)connesso tramite il protocollo PostgresQL[ o ](https://experienceleague.adobe.com/it/docs/experience-platform/query/clients/overview)API RESTful[ per creare e pianificare query che raccolgono i dati per il feed di dati.](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started)

### Crea query

È possibile utilizzare tutte le funzionalità di SQL ANSI standard per le istruzioni SELECT e altri comandi limitati per creare ed eseguire query che generano i dati per il feed di dati. Per ulteriori informazioni, vedere [Sintassi SQL](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/syntax). Oltre a questa sintassi SQL, Adobe supporta:

- [Funzioni definite da Adobe (ADF)](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) predefinite che consentono di eseguire attività di business comuni sui dati evento memorizzati nel data lake di Experience Platform, incluse le funzioni per [Sessionization](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing) e [Attribution](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview),
- diverse [funzioni SQL predefinite](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions),
- [comandi PostgreSQL dei metadati](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/metadata),
- [istruzioni preparate](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/prepared-statements).

#### Colonne feed dati

I campi XDM che puoi utilizzare nella query dipendono dalla definizione dello schema su cui si basano i set di dati. Assicurati di comprendere lo schema sottostante il set di dati. Per ulteriori informazioni, consulta la [Guida dell&#39;interfaccia utente dei set di dati](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide).

Per aiutarti a definire la mappatura tra le colonne Feed dati e i campi XDM, consulta [Mappatura campi di Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). Per ulteriori informazioni su come gestire le risorse XDM, inclusi schemi, classi, gruppi di campi e tipi di dati, consulta anche la [panoramica dell&#39;interfaccia utente degli schemi](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/overview#defining-xdm-fields).

Ad esempio, se desideri utilizzare *nome pagina* come parte del feed dati:

- Nell&#39;interfaccia utente di Adobe Analytics Data Feed, puoi selezionare **[!UICONTROL pagename]** come colonna da aggiungere alla definizione del feed dati.
- In Query Service, includi `web.webPageDetails.name` dal set di dati `sample_event_dataset_for_website_global_v1_1` (in base allo **Schema evento di esempio per il sito Web (Schema evento esperienza globale v1.1)**) nella query. Per ulteriori informazioni, vedere il gruppo di campi dello schema [Dettagli Web](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/web-details).


#### Identità

In Experience Platform sono disponibili varie identità. Quando crei le query, assicurati di eseguire correttamente le query sulle identità.


Spesso le identità si trovano in un gruppo di campi separato. In un&#39;implementazione ECID (`ecid`) può essere definito come parte di un gruppo di campi con un oggetto `core`, che a sua volta fa parte di un oggetto `identification` (ad esempio: `_sampleorg.identification.core.ecid`). Gli ECID potrebbero essere organizzati in modo diverso negli schemi.

In alternativa, è possibile utilizzare `identityMap` per eseguire query sulle identità. `identityMap` è di tipo `Map` e utilizza una [struttura di dati nidificata](#nested-data-structure).

Consulta [Definire i campi di identità nell&#39;interfaccia utente](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/identity) per ulteriori informazioni su come definire i campi di identità in Experience Platform.

Consulta [Identificatori primari nei dati di Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data) per informazioni sul mapping delle identità di Adobe Analytics alle identità di Experience Platform quando si utilizza il connettore di origine di Analytics. Questa mappatura può essere utile per configurare le identità, anche quando non si utilizza il connettore di origine di Analytics.


#### Dati e identificazione a livello di hit

In base all’implementazione, i dati a livello di hit tradizionalmente raccolti in Adobe Analytics ora vengono memorizzati come dati evento con marca temporale in Experience Platform. La tabella seguente è stata estratta da [Mappatura campi di Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields) e mostra alcuni esempi su come mappare le colonne Feed dati di Adobe Analytics specifiche per il livello di hit con i campi XDM corrispondenti nelle query. La tabella mostra anche esempi di identificazione di hit, visite e visitatori tramite i campi XDM.

| Colonna feed dati | Campo XDM | Tipo | Descrizione |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | string | Un identificatore univoco per identificare un hit. |
| `hitid_low` | `_id` | string | Utilizzato con `hitid_high` per identificare un hit in modo univoco. |
| `hitid_high` | `_id` | string | Utilizzato con `hitid_high` per identificare un hit in modo univoco. |
| `hit_time_gmt` | `receivedTimestamp` | string | La marca temporale dell’hit, in base all’ora UNIX®. |
| `cust_hit_time_gmt` | `timestamp` | string | Questa marca temporale viene utilizzata solo nei set di dati abilitati per la marca temporale. Questa marca temporale viene inviata con l’hit, in base all’ora UNIX®. |
| `visid_high` + `visid_low` | `identityMap` | oggetto | Un identificatore univoco per una visita. |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | string | Un identificatore univoco per una visita. |
| `visid_high` | `endUserIDs._experience.aaid.primary` | booleano | Utilizzato con `visid_low` per identificare una visita in modo univoco. |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | string | Utilizzato con `visid_low` per identificare una visita in modo univoco. |
| `visid_low` | `identityMap` | oggetto | Utilizzato con `visid_high` per identificare una visita in modo univoco. |
| `cust_visid` | `identityMap` | oggetto | L’ID visitatore del cliente. |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | oggetto | L’ID visitatore del cliente. |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | booleano | Il codice spazio dei nomi ID visitatore del cliente. |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | string | Utilizzato con `visid_low` per identificare in modo univoco l&#39;ID visitatore del cliente. |
| `geo\_*` | `placeContext.geo.* ` | stringa, numero | Dati di geolocalizzazione, come paese, regione, città e altri |
| `event_list` | `commerce.purchases`, `commerce.productViews`, `commerce.productListOpens`, `commerce.checkouts`, `commerce.productListAdds`, `commerce.productListRemovals`, `commerce.productListViews`, `_experience.analytics.event101to200.*`, ..., `_experience.analytics.event901_1000.*` | string | Eventi di e-commerce standard e personalizzati attivati sull’hit. |
| `page_event` | `web.webInteraction.type` | string | Tipo di hit inviato nella richiesta di immagine (hit standard, collegamento di download, collegamento di uscita o collegamento personalizzato su cui è stato fatto clic). |
| `page_event` | `web.webInteraction.linkClicks.value` | numero | Tipo di hit inviato nella richiesta di immagine (hit standard, collegamento di download, collegamento di uscita o collegamento personalizzato su cui è stato fatto clic). |
| `page_event_var_1` | `web.webInteraction.URL` | string | Variabile utilizzata solo nelle richieste di immagini per il tracciamento dei collegamenti. Questa variabile contiene l’URL del collegamento di download, del collegamento di uscita o del collegamento personalizzato su cui è stato fatto clic. |
| `page_event_var_2` | `web.webInteraction.name` | string | Variabile utilizzata solo nelle richieste di immagini per il tracciamento dei collegamenti. Elenca il nome personalizzato del collegamento, se specificato. |
| `paid_search` | `search.isPaid` | booleano | Flag impostato se l’hit corrisponde al rilevamento di ricerche a pagamento. |
| `ref_type` | `web.webReferrertype` | string | Un ID numerico che rappresenta il tipo di riferimento per l’hit. |

#### Pubblica colonne

I feed di dati di Adobe Analytics utilizzano il concetto di colonne con prefisso `post_`, che sono colonne contenenti dati dopo l’elaborazione. Per ulteriori informazioni, consulta [Domande frequenti sui feed di dati](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/df-faq#post).

I dati raccolti nei set di dati tramite Experience Platform Edge Network (Web SDK, Mobile SDK, Server API) non hanno alcun concetto di `post_` campi. Di conseguenza, `post_` colonne di feed dati con prefisso e *non*-`post_` colonne di feed dati con prefisso vengono mappate sugli stessi campi XDM. Ad esempio, entrambe le colonne di feed dati `page_url` e `post_page_url` sono mappate sullo stesso campo XDM `web.webPageDetails.URL`.

Vedi [Confrontare l&#39;elaborazione dei dati in Adobe Analytics e Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons) per una panoramica della differenza nell&#39;elaborazione dei dati.

Il tipo di dati della colonna con prefisso `post_`, se raccolto nel data lake di Experience Platform, richiede tuttavia trasformazioni avanzate prima di poter essere utilizzato correttamente in un caso di utilizzo di feed di dati. L&#39;esecuzione di queste trasformazioni avanzate nelle query comporta l&#39;utilizzo di [funzioni definite da Adobe](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) per la sessionizzazione, l&#39;attribuzione e la deduplicazione. Vedi [Esempi](#examples) su come utilizzare queste funzioni.

#### Ricerche

Per cercare dati da altri set di dati, utilizzare la funzionalità SQL standard (`WHERE` clausola, `INNER JOIN`, `OUTER JOIN` e altri).

#### Calcoli

Per eseguire calcoli sui campi (colonne), utilizzare le funzioni SQL standard (ad esempio `COUNT(*)`) o la parte [funzioni e operatori matematici e statistici](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#math) di Spark SQL. Inoltre, [funzioni finestra](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions#window-functions) forniscono supporto per aggiornare le aggregazioni e restituire singoli elementi per ogni riga in un sottoinsieme ordinato. Vedi [Esempi](#examples) su come utilizzare queste funzioni.

#### Struttura dati nidificata

Gli schemi su cui si basano i set di dati spesso contengono tipi di dati complessi, tra cui strutture di dati nidificate. `identityMap` è un esempio di struttura di dati nidificata. Vedere di seguito un esempio di dati `identityMap`.

```json
{
   "identityMap":{
      "FPID":[
         {
            "id":"55613368189701342632255821452918751312",
            "authenticatedState":"ambiguous"
         }
      ],
      "CRM":[
         {
            "id":"2394509340-30453470347",
            "authenticatedState":"authenticated"
         }
      ]
   }
}
```

È possibile utilizzare [`explode()` o altre funzioni di array](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#arrays) da Spark SQL per accedere ai dati all&#39;interno di una struttura di dati nidificata, ad esempio:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

In alternativa, puoi fare riferimento a singoli elementi utilizzando la notazione del punto. Ad esempio:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Per ulteriori informazioni, consulta [Utilizzo di strutture dati nidificate in Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/nested-data-structures).


#### Esempi

Per le query:

- che utilizzano dati provenienti da set di dati nel data lake di Experience Platform,
- sfrutta le funzionalità aggiuntive di Adobe Defined Functions e/o Spark SQL e
- che fornirebbe risultati simili a quelli di un feed di dati Adobe Analytics equivalente,

vedi:

- [esplorazione abbandonata](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/abandoned-browse)
- [analisi attribuzione](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/attribution-analysis)
- [filtro bot](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/bot-filtering)
- e altri [casi d&#39;uso supportati nella guida di Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/overview).

Di seguito è riportato un esempio per applicare correttamente l’attribuzione tra le sessioni e che illustra come

- utilizzare gli ultimi 90 giorni come lookback,
- applicare funzioni di finestra come sessionizzazione e/o attribuzione e
- limitare l&#39;output in base a `ingest_time`.

  +++ Dettagli

  Per fare questo, devi...

   - Utilizzare una tabella di stato di elaborazione, `checkpoint_log`, per tenere traccia dell&#39;ora corrente rispetto all&#39;ultima acquisizione. Per ulteriori informazioni, consulta [questa guida](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/incremental-load).
   - disabilita l&#39;eliminazione delle colonne di sistema, in modo da poter utilizzare `_acp_system_metadata.ingestTime`.
   - Utilizza un valore più interno di `SELECT` per acquisire i campi che desideri utilizzare e limitare gli eventi al periodo di lookback per i calcoli di sessionizzazione e/o attribuzione. Ad esempio, 90 giorni.
   - Utilizzare un livello successivo `SELECT` per applicare la sessionizzazione e/o le funzioni della finestra di attribuzione e altri calcoli.
   - Utilizza `INSERT INTO` nella tabella di output per limitare il lookback solo agli eventi arrivati dall&#39;ultima elaborazione. Per eseguire questa operazione, filtrare su `_acp_system_metadata.ingestTime ` rispetto all&#39;ultima volta memorizzata nella tabella dello stato di elaborazione.

  **Esempio di funzioni della finestra di sessionizzazione**

  ```sql
  $$ BEGIN
     -- Disable dropping system columns
     set drop_system_columns=false; 
  
     -- Initialize variables
     SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
     -- Get the last processed batch ingestion time
     SET @from_batch_ingestion_time = SELECT coalesce(last_batch_ingestion_time, 'HEAD') 
        FROM checkpoint_log a 
        JOIN (
              SELECT MAX(process_timestamp) AS process_timestamp 
              FROM checkpoint_log
              WHERE process_name = 'data_feed' 
              AND process_status = 'SUCCESSFUL'
        ) b
        ON a.process_timestamp = b.process_timestamp;
  
     -- Get the last batch ingestion time
     SET @to_batch_ingestion_time = SELECT MAX(_acp_system_metadata.ingestTime) 
        FROM events_dataset;
  
     -- Sessionize the data and insert into data_feed.
     INSERT INTO data_feed
     SELECT *
     FROM (
        SELECT
              userIdentity,
              timestamp,
              SESS_TIMEOUT(timestamp, 60 * 30) OVER (
                 PARTITION BY userIdentity
                 ORDER BY timestamp
                 ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
              ) AS session_data,
              page_name,
              ingest_time
        FROM (
              SELECT
                 userIdentity,
                 timestamp,
                 web.webPageDetails.name AS page_name,
                 _acp_system_metadata.ingestTime AS ingest_time
              FROM events_dataset
              WHERE timestamp >= current_date - 90
        ) AS a
        ORDER BY userIdentity, timestamp ASC
     ) AS b
     WHERE b.ingest_time >= @from_batch_ingestion_time;
  
     -- Update the checkpoint_log table
     INSERT INTO checkpoint_log
     SELECT
        'data_feed' process_name,
        'SUCCESSFUL' process_status,
        cast(@to_batch_ingestion_time AS string) last_batch_ingestion_time,
        cast(@last_updated_timestamp AS TIMESTAMP) process_timestamp
  END
  $$;
  ```

  **Esempio di funzioni della finestra di attribuzione**

  ```sql
  $$ BEGIN
   SET drop_system_columns=false;
  
  -- Initialize variables
   SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
  -- Get the last processed batch ingestion time 1718755872325
   SET @from_batch_ingestion_time =
       SELECT coalesce(last_snapshot_id, 'HEAD')
       FROM checkpoint_log a
       JOIN (
           SELECT MAX(process_timestamp) AS process_timestamp
           FROM checkpoint_log
           WHERE process_name = 'data_feed'
           AND process_status = 'SUCCESSFUL'
       ) b
       ON a.process_timestamp = b.process_timestamp;
  
   -- Get the last batch ingestion time 1718758687865
   SET @to_batch_ingestion_time =
       SELECT MAX(_acp_system_metadata.ingestTime)
       FROM demo_data_trey_mcintyre_midvalues;
  
   -- Sessionize the data and insert into new_sessionized_data
   INSERT INTO new_sessionized_data
   SELECT *
   FROM (
       SELECT
           _id,
           timestamp,
           struct(User_Identity,
           cast(SESS_TIMEOUT(timestamp, 60 * 30) OVER (
               PARTITION BY User_Identity
               ORDER BY timestamp
               ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
           ) as string) AS SessionData,
           to_timestamp(from_unixtime(ingest_time/1000, 'yyyy-MM-dd HH:mm:ss')) AS IngestTime,      
           PageName,
           first_url,
           first_channel_type
             ) as _demosystem5
       FROM (
           SELECT
               _id,
               ENDUSERIDS._EXPERIENCE.MCID.ID as User_Identity,
               timestamp,
               web.webPageDetails.name AS PageName,
              attribution_first_touch(timestamp, '', web.webReferrer.url) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_url,
              attribution_first_touch(timestamp, '',channel.typeAtSource) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_channel_type,
               _acp_system_metadata.ingestTime AS ingest_time
           FROM demo_data_trey_mcintyre_midvalues
           WHERE timestamp >= current_date - 90
       )
       ORDER BY User_Identity, timestamp ASC    
   )
   WHERE _demosystem5.IngestTime >= to_timestamp(from_unixtime(@from_batch_ingestion_time/1000, 'yyyy-MM-dd HH:mm:ss'));
  
  -- Update the checkpoint_log table
  INSERT INTO checkpoint_log
  SELECT
     'data_feed' as process_name,
     'SUCCESSFUL' as process_status,
     cast(@to_batch_ingestion_time AS string) as last_snapshot_id,
     cast(@last_updated_timestamp AS timestamp) as process_timestamp;
  
  END
  $$;
  ```

  +++


### Pianifica query

Pianifica la query per assicurarti che venga eseguita e che i risultati vengano generati nell’intervallo desiderato.

#### Utilizzo dell’editor delle query

È possibile pianificare una query utilizzando l&#39;Editor query. Quando pianifichi la query, definisci un set di dati di output. Per ulteriori informazioni, vedere [Pianificazioni query](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/query-schedules).


#### Utilizzo dell’API Query Service

In alternativa, puoi utilizzare le API RESTful per definire una query e pianificarla. Per ulteriori informazioni, consulta la [Guida API di Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started).
Accertati di definire il set di dati di output come parte della proprietà facoltativa `ctasParameters` durante la creazione della query ([Crea una query](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) o durante la creazione della pianificazione di una query ([Crea una query pianificata](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Esportare i set di dati

Dopo aver creato e pianificato la query e verificato i risultati, puoi esportare i set di dati non elaborati nelle destinazioni dell’archiviazione cloud. Questa esportazione si trova nella terminologia di Experience Platform Destinations, o destinazioni di esportazione del set di dati. Per una panoramica, consulta [Esportare i set di dati nelle destinazioni dell&#39;archiviazione cloud](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/export-datasets).

Sono supportate le seguenti destinazioni di archiviazione cloud:

- [Archiviazione Azure Data Lake Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Area di destinazione dati](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3)
- [BLOB di Azure](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp)


### Interfaccia utente di Experience Platform

Puoi esportare e pianificare l’esportazione dei set di dati di output tramite l’interfaccia utente di Experience Platform. Questa sezione descrive i passaggi necessari.

#### Seleziona destinazione

Dopo aver determinato la destinazione dell&#39;archiviazione cloud in cui esportare il set di dati di output, [selezionare la destinazione](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Se non hai ancora configurato una destinazione per l&#39;archiviazione cloud preferita, devi [creare una nuova connessione di destinazione](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Come parte della configurazione di una destinazione, puoi

- definire il tipo di file (JSON o Parquet),
- se il file risultante deve essere compresso o meno e
- se un file manifesto deve essere incluso o meno.


#### Seleziona set di dati

Dopo aver selezionato la destinazione, nel prossimo passaggio **[!UICONTROL Seleziona set di dati]** devi selezionare il set di dati di output dall&#39;elenco dei set di dati. Se hai creato più query pianificate e desideri che i set di dati di output vengano inviati alla stessa destinazione di archiviazione cloud, puoi selezionare i set di dati di output corrispondenti. Per ulteriori informazioni, consulta [Selezionare i set di dati](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets).

#### Pianificare l’esportazione di set di dati

Infine, pianificare l&#39;esportazione del set di dati come parte del passaggio **[!UICONTROL Pianificazione]**. In questo passaggio puoi definire la pianificazione e se l’esportazione del set di dati di output deve essere incrementale o meno. Per ulteriori informazioni, consulta [Pianificazione esportazione set di dati](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling).


#### Passaggi finali

[Rivedi](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) la selezione e, se corretto, inizia a esportare il set di dati di output nella destinazione dell&#39;archiviazione cloud.

È necessario [verificare](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) un&#39;esportazione dei dati completata. Durante l&#39;esportazione dei set di dati, Experience Platform crea uno o più file `.json` o `.parquet` nel percorso di archiviazione definito nella destinazione. I nuovi file verranno archiviati nel percorso di archiviazione in base alla pianificazione di esportazione configurata. Experience Platform crea una struttura di cartelle nel percorso di archiviazione specificato come parte della destinazione selezionata, dove deposita i file esportati. Viene creata una nuova cartella per ogni esportazione, seguendo il modello: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Il nome di file predefinito viene generato in modo casuale e garantisce che i nomi di file esportati siano univoci.

### API del servizio Flusso

In alternativa, puoi esportare e pianificare l’esportazione dei set di dati di output utilizzando le API. I passaggi necessari sono documentati in [Esporta i set di dati utilizzando l&#39;API del servizio Flusso](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### Introduzione

Per esportare i set di dati, assicurati di disporre delle [autorizzazioni richieste](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). Verifica inoltre che la destinazione in cui desideri inviare il set di dati di output supporti l’esportazione dei set di dati. È quindi necessario [raccogliere i valori per le intestazioni obbligatorie e facoltative](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) utilizzate nelle chiamate API. È inoltre necessario [identificare la specifica di connessione e gli ID delle specifiche di flusso della destinazione](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) in cui si desidera esportare i set di dati.

#### Recuperare i set di dati idonei

È possibile [recuperare un elenco di set di dati idonei](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) per l&#39;esportazione e verificare se il set di dati di output fa parte di tale elenco utilizzando l&#39;API [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets).


#### Crea connessione sorgente

Successivamente è necessario [creare una connessione di origine](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) per il set di dati di output, utilizzando il relativo ID univoco, che si desidera esportare nella destinazione dell&#39;archiviazione cloud. Utilizza l&#39;API [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection).

#### Autentica nella destinazione (crea connessione di base)

È ora necessario [creare una connessione di base](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) per autenticare e archiviare in modo sicuro le credenziali nella destinazione di archiviazione cloud utilizzando l&#39;API [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection).


#### Fornire parametri di esportazione

Successivamente, è necessario [creare una connessione di destinazione aggiuntiva che memorizzi i parametri di esportazione](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) per il set di dati di output utilizzando, ancora una volta, l&#39;API [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection). Questi parametri di esportazione includono posizione, formato file, compressione e altro ancora.

#### Imposta flusso di dati

Infine, [imposta il flusso di dati](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) per garantire che il set di dati di output venga esportato nella destinazione di archiviazione cloud utilizzando l&#39;API [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow). In questo passaggio è possibile definire la pianificazione per l&#39;esportazione utilizzando il parametro `scheduleParams`.

#### Convalida flusso di dati

Per [verificare le esecuzioni riuscite del flusso di dati](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), utilizza l&#39;API [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns), specificando l&#39;ID del flusso di dati come parametro di query. Questo ID del flusso di dati è un identificatore restituito quando imposti il flusso di dati.

[Verifica](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) un&#39;esportazione dei dati completata. Durante l&#39;esportazione dei set di dati, Experience Platform crea uno o più file `.json` o `.parquet` nel percorso di archiviazione definito nella destinazione. I nuovi file verranno archiviati nel percorso di archiviazione in base alla pianificazione di esportazione configurata. Experience Platform crea una struttura di cartelle nel percorso di archiviazione specificato come parte della destinazione selezionata, dove deposita i file esportati. Viene creata una nuova cartella per ogni esportazione, seguendo il modello: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Il nome di file predefinito viene generato in modo casuale e garantisce che i nomi di file esportati siano univoci.

## Conclusione

In breve, l’emulazione della funzionalità Feed dati di Adobe Analytics implica la configurazione di query pianificate tramite Query Service e l’utilizzo dei risultati di tali query nelle esportazioni di set di dati pianificate.

>[!IMPORTANT]
>
>In questo caso d’uso sono coinvolti due scheduler. Per garantire il corretto funzionamento della funzionalità dei feed dati emulati, assicurati che le pianificazioni configurate in Query Service e le esportazioni di dati non interferiscano.
