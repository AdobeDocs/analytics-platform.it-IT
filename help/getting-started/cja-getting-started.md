---
title: Guida introduttiva all'analisi del percorso del cliente
description: Guida Introduttiva All'Analisi Del Percorso Del Cliente.
translation-type: tm+mt
source-git-commit: fb2b5868db69bfff3345abcd69b0b70112fdcf3c

---


# Guida introduttiva all&#39;analisi del percorso del cliente

Per implementare Analisi percorso cliente, devi seguire questo flusso di lavoro. Alcune attività iniziali vengono eseguite in Adobe Experience Platform, altre in Customer Journey Analytics.

| Attività | Dove eseguito | Dettagli |
|---|---|---|
| **Passaggio 1: Come ottenere i dati in Adobe Experience Platform** | Adobe Experience Platform | Esistono diversi modi per acquisire i dati sia per i casi di utilizzo in streaming che per quelli in batch, tra cui le API e un&#39;interfaccia grafica per il caricamento dei dati. Experience Platform è in grado di importare dati da cose come:<ul><li>Archiviazione S3</li><li>Archiviazione BLOB di Azure</li><li>Kafka Streams</li><li>Trasferimenti SFTP</li><li>Caricamenti di file CSV</li><li>Caricamenti di file JSON</li></ul> |
| **Passaggio 2: Preparare lo schema dati** | Adobe Experience Platform | Utilizzate [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) per standardizzare i dati sull&#39;esperienza cliente e definire schemi per la gestione dell&#39;esperienza cliente. |
| **Passaggio 3: Creare un dataset basato sullo schema** | Adobe Experience Platform | I dati in Piattaforma sono costituiti da set di dati, ad esempio set di dati e-mail, set di dati CRM, set di dati POS, set di dati Adobe Analytics, ecc. Ciascun set di dati è costituito da uno schema e da batch di dati. Puoi creare un set di dati [in Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).<br>Anche se lo schema per i set di dati che è possibile importare in Customer Journey Analytics è flessibile, deve essere conforme ad alcune regole di base. È consigliabile assicurarsi che i dati soddisfino questi requisiti prima di caricarli in Piattaforma. (Lo schema include metriche e dimensioni.)<br>Esistono tre tipi di dati compatibili con l&#39;analisi del percorso cliente:<ul><li>**Dati** evento: Dati che rappresentano eventi nel tempo (ad esempio visite Web, interazioni, transazioni, dati POS, dati sondaggio, dati ad impression, ecc.). Si tratta di dati tipici del clickstream, con un ID cliente o un ID cookie e una marca temporale. Con i dati dell’evento, vi consentiamo di utilizzare l’ID desiderato.</li><li>**Dati** di ricerca: Questi dati vengono utilizzati per cercare i valori o le chiavi presenti nei dati dell&#39;evento o del profilo. Ad esempio, potete caricare dati di ricerca che mappano ID numerici nei dati dell&#39;evento ai nomi dei prodotti.</li><li>**Dati** profilo: Dati applicati ai visitatori, utenti o clienti nei dati dell’evento. Ad esempio, consente di caricare dati CRM sui clienti.</li></ul> |
| **Passaggio 4:creare connessioni tra set di dati della piattaforma e analisi del percorso cliente** | Customer Journey Analytics | Consultate [Creare una connessione](/help/connections/create-connection.md). |
| **Passaggio 5: Creazione di viste dati** | Customer Journey Analytics | Consultate [Creare una visualizzazione](/help/data-views/create-dataview.md)dati. |
| **Passaggio 6: Report sui dati multicanale in Workspace** | Customer Journey Analytics | Consultate [Eseguire analisi](/help/projects/perform-basic-analysis.md) di base ed [Eseguire analisi](/help/projects/perform-adv-analysis.md)avanzate. |

## Prerequisiti

Analisi del percorso del cliente è disponibile per i clienti che

* Sono clienti Adobe Analytics [Select, Prime o Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) e
* dispongono del provisioning per [Adobe Experience Platform](https://www.adobe.com/experience-platform.html)e
* Hai acquistato lo SKU di analisi del percorso del cliente

## Preparare lo schema dati

[Creazione di uno schema con l&#39;Editor di schema](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## Passaggio 1: Come ottenere i dati in Adobe Experience Platform

Prima di poter sfruttare i dati di Experience Platform in CJA, devi trasferire tali dati nella piattaforma. Esistono diversi modi per farlo:

* Se desideri inserire i dati esistenti di Adobe Analytics, usa il connettore della piattaforma Adobe Analytics.
* Per acquisire altri dati, utilizzare formati come: Archiviazione S3, Archiviazione BLOB di Azure, Streams Kafka, Trasferimenti SFTP, Caricamenti di file CSV, Caricamenti di file JSON

### Fase 1 bis: Trasmissione dei dati Analytics esistenti in Adobe Experience Platform

Utilizza il connettore della piattaforma Adobe Analytics fornito con i prodotti per l’importazione di dati Adobe Analytics tradizionali nella piattaforma. Puoi creare una connessione sorgente per ogni suite di rapporti. Consultate [Creare una connessione sorgente con Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) nella documentazione di Adobe Experience Platform.

Una volta creata la connessione, viene automaticamente creato uno schema di destinazione e un dataset che contiene i dati in arrivo. Inoltre, si verifica il recupero dei dati e vengono acquisiti fino a 13 mesi di dati storici. Al termine dell&#39;assimilazione iniziale, potete procedere con `Step 4` la creazione di una connessione tra il set di dati di Analytics e l&#39;analisi del percorso del cliente.

### Passaggio 1 ter: Assegna altri tipi di dati

[L’assimilazione](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md) in batch consente di trasferire i dati in Experience Platform come file in batch. I batch sono unità di dati costituite da uno o più file da assimilare come singola unità. Una volta ingeriti, i batch forniscono i metadati che descrivono il numero di record correttamente acquisiti, nonché tutti i record con errore e i messaggi di errore associati. I file di dati caricati manualmente, come file .CSV semplici (mappati a schemi XDM) e i fotogrammi di dati Parquet, devono essere acquisiti con questo metodo.

[L’assimilazione](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) dello streaming consente di inviare in tempo reale dati da dispositivi lato client e lato server a Experience Platform.

[Altri connettori](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md) di origine consentono di acquisire dati da fonti esterne e allo stesso tempo di strutturare, etichettare e migliorare i dati in arrivo tramite i servizi della piattaforma. Puoi assimilare i dati da diverse origini come applicazioni Adobe (Adobe Analytics, Audience Manager, Experience Platform Launch, Target), archiviazione basata sul cloud (Azure Blob, Amazon S3, FTP/SFTP, Google Cloud Storage), software di terze parti e CRM (Microsoft Dynamics 365, Salesforce).

## Passaggio 2: Preparare lo schema dati

bnbnbnbn
