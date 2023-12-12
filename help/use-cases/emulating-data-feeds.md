---
title: Funzionalità di emulazione feed dati
description: Scopri come emulare i feed di dati di Adobe Analytics con i dati in Experienci Platform.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: d5719dddfb4cefda761370951973d55b3904032f
workflow-type: tm+mt
source-wordcount: '2103'
ht-degree: 0%

---

# Funzionalità di emulazione feed dati

I feed di dati di Adobe Analytics sono un modo potente per estrarre dati non elaborati da Adobe Analytics. Questo caso d’uso descrive come ottenere da Experienci Platform un tipo simile di dati non elaborati, da utilizzare in altre piattaforme al di fuori di Adobe e a discrezione della tua organizzazione.

## Prerequisiti

Prima di utilizzare la funzionalità descritta in questo caso d’uso, assicurati di soddisfare tutti i seguenti requisiti:

* Un’implementazione funzionante che invia dati online e offline nel Data Lake di Experienci Platform.
* Accesso a Query Service, fornito come parte delle applicazioni basate su Platform o del componente aggiuntivo Data Distiller. Consulta [Pacchetto Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) per ulteriori informazioni.
* Accesso alla funzionalità Esporta set di dati, disponibile per i clienti che hanno acquistato il pacchetto Real-Time CDP Prime o Ultimate, Adobe Journey Optimizer o il Customer Journey Analytics. Consulta [Esportare i set di dati nelle destinazioni dell’archiviazione cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en) per ulteriori informazioni.
* Una o più destinazioni (ad esempio: Amazon S3, Google Cloud Storage) configurate per esportare i dati non elaborati del feed di dati.

## Introduzione

L’emulazione di un feed dati di Adobe Analytics prevede:

* definizione di un **query pianificata** che genera i dati per il feed dati come set di dati di output, utilizzando **Servizio query**.
* definizione di un **esportazione di set di dati pianificata** che esporta il set di dati di output in una destinazione di archiviazione cloud, utilizzando **Esportazione set di dati**.


![Feed dati](assets/data-feed.svg)


## Servizio query

Experienci Platform Query Service consente di eseguire query e unire qualsiasi set di dati in Experienci Platform Data Lake come se si trattasse di una tabella di database. Puoi quindi acquisire i risultati come nuovo set di dati da utilizzare ulteriormente nel reporting o per l’esportazione.

Utilizza il servizio Query [interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en), a [client connesso tramite il protocollo PostgresSQL](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en), o [API RESTful](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) per creare e pianificare query per la raccolta dei dati per il proprio feed di dati.

### Crea query

È possibile utilizzare tutte le funzionalità di SQL ANSI standard per le istruzioni SELECT e altri comandi limitati per creare ed eseguire le query che generano i dati per il feed di dati. Consulta [Sintassi SQL](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) per ulteriori informazioni. Oltre a questa sintassi SQL, Adobe supporta:

* predefinito [Funzioni definite dall&#39;Adobe (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) che consentono di eseguire attività di business comuni sui dati evento memorizzati in Experienci Platform Data Lake, incluse funzioni per [Sessionizzazione](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=it) e [Attribuzione](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=it),
* diversi [Funzioni SQL Spark](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en),
* [comandi PostgreSQL dei metadati](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en),
* [istruzioni preparate](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### Esempi

Di seguito sono elencati alcuni esempi di query che raccolgono dati per i feed di dati. Questi esempi utilizzano `demo_system_event_dataset_for_website_global_v1_1` come set di dati dell’evento esperienza di esempio contenente i dati raccolti dai clienti che interagiscono con il sito web.

+++Primi cinque prodotti

*Quali sono i primi cinque prodotti visualizzati sul sito web?*

```sql
select productListItems.name, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType = 'commerce.productViews'
group  by productListItems.name
order  by 2 desc
limit 5;
```

+++

+++Funnel di interazione del prodotto

*Quali sono le varie interazioni dei prodotti all’interno del sito web?*

```sql
select eventType, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType is not null
and    eventType <> ''
group  by eventType;
```

+++

+++Cosa fanno le persone

*Cosa fanno le persone sul sito prima di raggiungere la pagina &quot;Annulla servizio&quot; come terza pagina in una sessione?*

Questa query utilizza le funzioni definite dall&#39;Adobe `SESS_TIMEOUT` e `NEXT`.

* Il `SESS_TIMEOUT()` riproduce i raggruppamenti di visite trovati con Adobe Analytics. Esegue un raggruppamento basato sul tempo simile, ma con parametri personalizzabili.
* `NEXT()` e `PREVIOUS()` aiutarti a capire come i clienti navigano nel tuo sito.

```sql
SELECT
  webPage,
  webPage_2,
  webPage_3,
  webPage_4,
  count(*) journeys
FROM
  (
      SELECT
        webPage,
        NEXT(webPage, 1, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_2,
        NEXT(webPage, 2, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_3,
        NEXT(webPage, 3, true)
           OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_4,
        session.depth AS SessionPageDepth
      FROM (
            select a._sampleorg.identification.core.ecid as ecid,
                   a.timestamp,
                   web.webPageDetails.name as webPage,
                    SESS_TIMEOUT(timestamp, 60 * 30)
                       OVER (PARTITION BY a._sampleorg.identification.core.ecid
                             ORDER BY timestamp
                             ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)
                  AS session
            from   demo_system_event_dataset_for_website_global_v1_1 a
            where  a._sampleorg.identification.core.ecid in (
                select b._sampleorg.identification.core.ecid
                from   demo_system_event_dataset_for_website_global_v1_1 b
                where  b.web.webPageDetails.name = 'Cancel Service'
            )
        )
)
WHERE SessionPageDepth=1
and   webpage_3 = 'Cancel Service'
GROUP BY webPage, webPage_2, webPage_3, webPage_4
ORDER BY journeys DESC
LIMIT 10;
```

+++

+++Quanto tempo

*Quanto tempo trascorre prima che un visitatore chiami il call center dopo aver visitato la pagina &quot;Annulla servizio&quot;?*

Per rispondere a questo tipo di query, utilizza `TIME_BETWEEN_NEXT_MATCH()` Funzione definita da Adobe. Le funzioni di corrispondenza precedente o successiva forniscono una nuova dimensione che misura il tempo trascorso da un particolare incidente.

```sql
select * from (
       select _sampleorg.identification.core.ecid as ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
where r.webPage = 'Cancel Service'
limit 15;
```

+++

+++Qual è il risultato?

*Qual è il risultato della chiamata al call center da parte dei clienti?*

Per questa query, il `demo_system_event_dataset_for_website_global_v1_1` il set di dati è unito a un esempio `demo_system_event_dataset_for_call_center_global_v1_1` set di dati contenente le interazioni del call center.

```sql
select distinct r.*,
       c._sampleorg.interactionDetails.core.callCenterAgent.callFeeling,
       c._sampleorg.interactionDetails.core.callCenterAgent.callTopic,
       c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled
from (
       select _sampleorg.identification.core.ecid ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
, demo_system_event_dataset_for_call_center_global_v1_1 c
where r.ecid = c._sampleorg.identification.core.ecid
and r.webPage = 'Cancel Service'
and c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled IN (true,false)
and c._sampleorg.interactionDetails.core.callCenterAgent.callTopic IN ('contract', 'invoice','complaint','wifi')
limit 15;
```

+++

+++Coinvolgimento canale di marketing (dati Adobe Analytics)

*Qual è il coinvolgimento tra i canali di marketing per il traffico web incentrato sull’italiano?*

Questo esempio utilizza il set di dati creato automaticamente dal connettore di origine di Adobe Analytics, ad esempio `demo_data_sample_org_midvalues`.

```sql
select 
    channel.typeAtSource, count(*) 
from 
    demo_data_sample_org_midvalues 
where 
    (channel.typeAtSource IS NOT NULL
and
    web.webPageDetails.URL LIKE '%/it/it/%')
group by 
    channel.typeAtSource
order by 2 desc;
```

+++

Per ulteriori query di esempio (avanzate), consulta [navigazione abbandonata](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en), [analisi dell’attribuzione](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en), [filtro bot](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en)e altri esempi nella Guida di Query Service.


#### Identità

Ad Experience Platform, sono disponibili varie identità. Assicurati di eseguire correttamente la query sulle identità. Negli esempi precedenti, ECID è definito come parte di un oggetto core, che a sua volta fa parte di un oggetto di identificazione, entrambi aggiunti allo schema utilizzando un gruppo di campi Core di Experience Event (ad esempio: `_sampleorg.identification.core.ecid`). Gli ECID potrebbero essere organizzati in modo diverso negli schemi.

In alternativa, è possibile utilizzare `identityMap` per eseguire una query per le identità. Questo oggetto è di tipo `Map` e utilizza un [struttura dati nidificata](#nested-data-structure).

Per i dati acquisiti tramite il connettore di origine di Adobe Analytics, potrebbero essere disponibili più identità. L’identificatore primario dipende dall’esistenza di un ECID o AAID. Consulta [Identificatori primari nei dati di Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#how-the-analytics-source-treats-identities) e [AAID, ECID, AACUSTOMID e il connettore di origine di Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) per ulteriori informazioni

#### Colonne feed dati

I campi (colonne) utilizzabili nella query dipendono dalla definizione dello schema su cui si basano i set di dati. Assicurati di comprendere lo schema sottostante il set di dati.

Ad esempio, in alcuni [query di esempio](#examples) hai richiesto *nome pagina*.

* Nell’interfaccia utente di Adobe Analytics Data Feed, puoi selezionare **[!UICONTROL pagename]** come colonna da aggiungere alla definizione del feed dati.
* In Query Service puoi includere: `web.webPageDetails.name` dal `demo_system_event_dataset_for_website_global_v1_1` set di dati (basato su **Sistema di dimostrazione - Schema eventi per il sito web (Global v1.1)** experience event) nella query. Consulta la [Gruppo di campi schema Dettagli web](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) per ulteriori informazioni.

Per comprendere la mappatura tra colonne di dati Adobe Analytics precedenti e campi XDM nel set di dati dell’evento esperienza e nello schema sottostante, consulta [Mappatura dei campi di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=it) e [Gruppo di campi schema Estensione completa Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) per ulteriori informazioni.

Inoltre, le informazioni raccolte automaticamente da Experienci Platform Web SDK (predefinite) potrebbero essere rilevanti anche per identificare le colonne per la query. Consulta [Informazioni raccolte automaticamente](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) per ulteriori informazioni.


#### Ricerche

Per cercare dati da altri set di dati, è possibile utilizzare la funzionalità SQL standard (clausola WHERE, INNER JOIN, OUTER JOIN e altri). Consulta la [Qual è il risultato?](#examples) negli esempi.

#### Calcoli

Per eseguire calcoli sui campi (colonne), è sufficiente utilizzare le funzioni SQL standard, ad esempio `COUNT(*)` nel [Funnel di interazione del prodotto](#examples) negli esempi) o [operatori e funzioni matematiche e statistiche](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) parte di Spark SQL.

#### Struttura dati nidificata

Gli schemi su cui si basano i set di dati spesso contengono tipi di dati complessi, tra cui strutture di dati nidificate. Precedentemente menzionato `identityMap` è un esempio di struttura di dati nidificata. Vedi di seguito per un esempio di `identityMap` dati.

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

È possibile utilizzare [`explode()` o altre funzioni di array](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) da SQL Spark per accedere ai dati all’interno di una struttura di dati nidificata.

Ad esempio:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

In alternativa, puoi fare riferimento a singoli elementi utilizzando la notazione del punto. Ad esempio:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Consulta [Utilizzo delle strutture di dati nidificati in Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en) per ulteriori informazioni.

### Pianifica query

Pianifica la query per assicurarti che venga eseguita e che i risultati vengano generati nell’intervallo desiderato. Quando pianifichi la query, definisci un set di dati di output.

#### Utilizzo dell’editor delle query

È possibile pianificare una query utilizzando l&#39;Editor query. Quando definisci una pianificazione per una query, puoi definire il set di dati di output. Consulta [Pianificazioni query](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) per ulteriori informazioni.


#### Utilizzo dell’API Query Service

In alternativa, puoi utilizzare le API RESTful per definire una query e pianificarla. Consulta [Guida API di Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en_) per ulteriori informazioni.
Assicurati di definire il set di dati di output come parte del `ctasParameters` durante la creazione della query ([Creare una query](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) o durante la creazione della pianificazione per una query ([Creare una query pianificata](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Esportazione set di dati

Dopo aver creato e pianificato la query e verificato che i risultati nei set di dati di output siano in linea con i requisiti, puoi esportare i set di dati non elaborati in destinazioni di archiviazione cloud. Questa esportazione si trova nella terminologia di Experienci Platform Destinations, o destinazioni di esportazione del set di dati. Consulta [Esportare i set di dati nelle destinazioni dell’archiviazione cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en) panoramica.

Sono supportate le seguenti destinazioni di archiviazione cloud:

* [Archiviazione Azure Data Lake Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=en)
* [Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en)
* [Archiviazione cloud Google](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=en)
* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=en#changelog)
* [BLOB di Azure](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=en#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=en#changelog)


### Interfaccia utente Experienci Platform

Puoi esportare e pianificare l’esportazione dei set di dati di output tramite l’interfaccia utente di Experienci Platform. Questa sezione descrive i passaggi necessari.

#### Seleziona destinazione

Dopo aver determinato la destinazione di archiviazione cloud da esportare per il set di dati di output, [seleziona la destinazione](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-destination). Quando non hai ancora configurato una destinazione per l’archiviazione cloud preferita, devi [creare una nuova connessione di destinazione](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=en).

Come parte della configurazione di una destinazione puoi definire il tipo di file (JSON o Parquet), se il file risultante deve essere compresso o meno e se un file manifesto deve essere incluso o meno.


#### Seleziona set di dati

Dopo aver selezionato la destinazione, nel successivo **[!UICONTROL Select datasets]** passaggio è necessario selezionare il set di dati di output dall’elenco dei set di dati. Se hai creato più query pianificate e desideri che i set di dati di output vengano inviati alla stessa destinazione di archiviazione cloud, puoi selezionare i set di dati di output corrispondenti. Consulta [Seleziona i set di dati](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-datasets) per ulteriori informazioni.

#### Pianificare l’esportazione di set di dati

Infine, desideri pianificare l’esportazione del set di dati come parte del **[!UICONTROL Scheduling]** passaggio. In questo passaggio puoi definire la pianificazione e se l’esportazione del set di dati di output deve essere incrementale o meno. Consulta [Pianificare l’esportazione di set di dati](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#scheduling) per ulteriori informazioni.


#### Passaggi finali

[Revisione](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#review) la selezione e, se corretto, avvia l’esportazione del set di dati di output nella destinazione di archiviazione cloud.

Devi [verifica](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) esportazione dei dati riuscita. Durante l’esportazione dei set di dati, in Experienci Platform ne vengono creati uno o più `.json` o `.parquet` file nel percorso di archiviazione definito nella destinazione. I nuovi file verranno archiviati nel percorso di archiviazione in base alla pianificazione di esportazione configurata. In Experience Platform viene creata una struttura di cartelle nel percorso di archiviazione specificato come parte della destinazione selezionata, in cui vengono depositati i file esportati. Per ogni esportazione viene creata una nuova cartella, seguendo il modello: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Il nome di file predefinito viene generato in modo casuale e garantisce che i nomi di file esportati siano univoci.

### API del servizio Flusso

In alternativa, puoi esportare e pianificare l’esportazione dei set di dati di output utilizzando le API. I passaggi necessari sono documentati in [Esportare i set di dati utilizzando l’API del servizio Flusso](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### Introduzione

Assicurati di avere [autorizzazioni richieste](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions) per esportare i set di dati e che la destinazione in cui desideri inviare il set di dati di output supporti l’esportazione dei set di dati. Devi quindi [raccogliere i valori per le intestazioni obbligatorie e facoltative](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) utilizzi nelle chiamate API, nonché [identificare la specifica di connessione e gli ID delle specifiche di flusso della destinazione](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) intendi esportare i set di dati in.

#### Recuperare i set di dati idonei

È possibile [recuperare un elenco di set di dati idonei](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#retrieve-list-of-available-datasets) per l’esportazione e verifica se il set di dati di output fa parte di tale elenco utilizzando [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Crea connessione sorgente

Ora devi [creare una connessione sorgente](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-source-connection) per il set di dati di output, utilizzando il relativo ID univoco, che desideri esportare nella destinazione di archiviazione cloud. Utilizzi il [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Autentica nella destinazione (crea connessione di base)

Ora devi [creare una connessione di base](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-base-connection) per autenticare e archiviare correttamente le credenziali nella destinazione di archiviazione cloud utilizzando [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Fornire parametri di esportazione

Quindi, devi [crea una connessione di destinazione aggiuntiva in cui sono memorizzati i parametri di esportazione](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-target-connection) per il set di dati di output utilizzando, ancora una volta, il [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Questi parametri di esportazione includono posizione, formato file, compressione e altro ancora.

#### Imposta flusso di dati

Finalmente, [impostare il flusso di dati](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-dataflow) per garantire che il set di dati di output venga esportato nella destinazione di archiviazione cloud utilizzando [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. In questo passaggio puoi definire la pianificazione per l’esportazione utilizzando `scheduleParams` parametro.

#### Convalida flusso di dati

A [verificare le esecuzioni corrette del flusso di dati](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#get-dataflow-runs), utilizza [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, specificando l’ID del flusso di dati come parametro di query. Questo ID del flusso di dati è un identificatore restituito quando imposti il flusso di dati.

[Verifica](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) esportazione dei dati riuscita. Durante l’esportazione dei set di dati, in Experienci Platform ne vengono creati uno o più `.json` o `.parquet` file nel percorso di archiviazione definito nella destinazione. I nuovi file verranno archiviati nel percorso di archiviazione in base alla pianificazione di esportazione configurata. In Experience Platform viene creata una struttura di cartelle nel percorso di archiviazione specificato come parte della destinazione selezionata, in cui vengono depositati i file esportati. Per ogni esportazione viene creata una nuova cartella, seguendo il modello: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Il nome di file predefinito viene generato in modo casuale e garantisce che i nomi di file esportati siano univoci.

## Conclusione

In breve, l’emulazione della funzionalità Feed dati di Adobe Analytics implica la configurazione di query pianificate tramite Query Service e l’utilizzo dei risultati di tali query nelle esportazioni di set di dati pianificate.

>[!IMPORTANT]
>
>In questo caso d’uso sono coinvolti due scheduler. Per garantire il corretto funzionamento della funzionalità dei feed dati emulati, assicurati che le pianificazioni configurate in Query Service e le esportazioni di dati non interferiscano.

