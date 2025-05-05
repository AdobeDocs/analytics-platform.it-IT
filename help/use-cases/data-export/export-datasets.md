---
title: Set di dati di esportazione Customer Journey Analytics
description: Descrive come utilizzare i set di dati di esportazione per eseguire il backup dei dati.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
source-git-commit: 9fef1fddbb4b51efb9282e3ef13501bd498a4546
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 1%

---

# Esportare i set di dati

Questo articolo illustra come utilizzare [!DNL Customer Journey Analytics Export datasets] per implementare il seguente [caso d&#39;uso per l&#39;esportazione dei dati](overview.md):

- Backup dei dati

## Introduzione

L&#39;esportazione dei dati tramite [!DNL Experience Platform Export datasets] consente di esportare i dati dalle visualizzazioni dati del Customer Journey Analytics a qualsiasi destinazione di archiviazione cloud.

![Estensione BI](../assets/export-datasets.svg)

## Ulteriori informazioni

Puoi esportare i set di dati non elaborati dal data lake in Experience Platform nelle destinazioni di archiviazione cloud. Questa esportazione si trova nella terminologia di Experience Platform Destinations, o destinazioni di esportazione del set di dati. Per una panoramica, consulta [Esportare i set di dati nelle destinazioni dell&#39;archiviazione cloud](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/export-datasets).

Sono supportate le seguenti destinazioni di archiviazione cloud:

- [Archiviazione Azure Data Lake Gen2](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Area di destinazione dati](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [BLOB di Azure](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### Interfaccia utente Experience Platform

Puoi esportare e pianificare l’esportazione dei set di dati tramite l’interfaccia utente di Experience Platform. Questa sezione descrive i passaggi necessari.

#### Seleziona destinazione

Dopo aver determinato la destinazione dell&#39;archiviazione cloud in cui desideri esportare il set di dati, [seleziona la destinazione](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Se non hai ancora configurato una destinazione per l&#39;archiviazione cloud preferita, devi [creare una nuova connessione di destinazione](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/connect-destination).

Durante la configurazione di una destinazione, puoi definire:

- il tipo di file (JSON o Parquet),
- se il file risultante deve essere compresso o meno e
- se un file manifesto deve essere incluso o meno.


#### Seleziona set di dati

Dopo aver selezionato la destinazione, nel passaggio successivo di **[!UICONTROL Select datasets]** devi selezionare il set di dati dall&#39;elenco dei set di dati. Se hai creato più query pianificate e desideri che i set di dati vengano inviati alla stessa destinazione di archiviazione cloud, puoi selezionare i set di dati corrispondenti. Per ulteriori informazioni, consulta [Selezionare i set di dati](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets).

#### Pianificare l’esportazione di set di dati

Infine, pianificare l&#39;esportazione del set di dati come parte del passaggio **[!UICONTROL Scheduling]**. In questo passaggio puoi definire la pianificazione e se l’esportazione del set di dati deve essere incrementale o meno. Per ulteriori informazioni, consulta [Pianificazione esportazione set di dati](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling).


#### Passaggi finali

[Rivedi](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/export-datasets#review) la selezione e, se corretto, inizia a esportare il set di dati nella destinazione dell&#39;archiviazione cloud.

Innanzitutto, devi [verificare](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/export-datasets#verify) che l&#39;esportazione dei dati sia andata a buon fine. Durante l&#39;esportazione dei set di dati, Experience Platform crea uno o più file `.json` o `.parquet` nel percorso di archiviazione definito nella destinazione. I nuovi file verranno archiviati nel percorso di archiviazione in base alla pianificazione di esportazione configurata. In Experience Platform viene creata una struttura di cartelle nel percorso di archiviazione specificato come parte della destinazione selezionata, in cui vengono depositati i file esportati. Viene creata una nuova cartella per ogni esportazione, seguendo il modello: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Il nome di file predefinito viene generato in modo casuale e garantisce che i nomi di file esportati siano univoci.

### API del servizio Flusso

In alternativa, puoi esportare e pianificare l’esportazione dei set di dati utilizzando le API. I passaggi necessari sono documentati in [Esporta i set di dati utilizzando l&#39;API del servizio Flusso](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/api/export-datasets).

#### Introduzione

Per esportare i set di dati, assicurati di disporre delle [autorizzazioni richieste](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/api/export-datasets#permissions). Verifica inoltre che la destinazione in cui desideri inviare il set di dati supporti l’esportazione dei set di dati. È quindi necessario [raccogliere i valori per le intestazioni obbligatorie e facoltative](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) utilizzate nelle chiamate API. È inoltre necessario [identificare la specifica di connessione e gli ID delle specifiche di flusso della destinazione](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) in cui si desidera esportare i set di dati.

#### Recuperare i set di dati idonei

È possibile [recuperare un elenco di set di dati idonei](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) per l&#39;esportazione e verificare se il set di dati fa parte di tale elenco utilizzando l&#39;API [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets).


#### Crea connessione sorgente

Successivamente, è necessario [creare una connessione di origine](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/api/export-datasets#create-source-connection) per il set di dati, utilizzando il relativo ID univoco, che si desidera esportare nella destinazione dell&#39;archiviazione cloud. Utilizza l&#39;API [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection).

#### Autentica nella destinazione (crea connessione di base)

È ora necessario [creare una connessione di base](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/api/export-datasets#create-base-connection) per autenticare e archiviare in modo sicuro le credenziali nella destinazione di archiviazione cloud utilizzando l&#39;API [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection).


#### Fornire parametri di esportazione

Successivamente, è necessario [creare una connessione di destinazione aggiuntiva in cui memorizzare i parametri di esportazione](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/api/export-datasets#create-target-connection) per il set di dati utilizzando, ancora una volta, l&#39;API [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection). Questi parametri di esportazione includono posizione, formato file, compressione e altro ancora.

#### Imposta flusso di dati

Infine, [imposta il flusso di dati](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/api/export-datasets#create-dataflow) per garantire che il set di dati venga esportato nella destinazione di archiviazione cloud utilizzando l&#39;API [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow). In questo passaggio è possibile definire la pianificazione per l&#39;esportazione utilizzando il parametro `scheduleParams`.

#### Convalida flusso di dati

Per [verificare le esecuzioni riuscite del flusso di dati](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), utilizza l&#39;API [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns), specificando l&#39;ID del flusso di dati come parametro di query. Questo ID del flusso di dati è un identificatore restituito quando imposti il flusso di dati.

[Verifica](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/export-datasets#verify) un&#39;esportazione dei dati completata. Durante l&#39;esportazione dei set di dati, Experience Platform crea uno o più file `.json` o `.parquet` nel percorso di archiviazione definito nella destinazione. I nuovi file verranno archiviati nel percorso di archiviazione in base alla pianificazione di esportazione configurata. In Experience Platform viene creata una struttura di cartelle nel percorso di archiviazione specificato come parte della destinazione selezionata, in cui vengono depositati i file esportati. Viene creata una nuova cartella per ogni esportazione, seguendo il modello: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Il nome di file predefinito viene generato in modo casuale e garantisce che i nomi di file esportati siano univoci.
