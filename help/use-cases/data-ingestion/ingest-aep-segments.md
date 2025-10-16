---
title: Acquisire e utilizzare i tipi di pubblico di Experience Platform
description: Come acquisire e utilizzare i tipi di pubblico di Experience Platform in Customer Journey Analytics per ulteriori analisi.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
role: Admin
source-git-commit: 5f17863e1f71917442b4813cc2599eb7ed286e5f
workflow-type: tm+mt
source-wordcount: '1290'
ht-degree: 4%

---

# Acquisire e utilizzare i tipi di pubblico di Experience Platform

Questo caso d’uso descrive una soluzione provvisoria per acquisire il pubblico di Experience Platform in Customer Journey Analytics. Questi tipi di pubblico possono essere stati creati nel Generatore di segmenti di Experience Platform, o in Adobe Audience Manager, o in altri strumenti e sono memorizzati nel Profilo cliente in tempo reale. I tipi di pubblico sono costituiti da un set di ID profilo, insieme a tutti gli attributi, gli eventi e altro ancora applicabili. Desideri inserire i dati sul pubblico in Customer Journey Analytics per ulteriori analisi.

## Prerequisiti

* Accesso a [Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/access-control/home), in particolare al profilo cliente in tempo reale.
* Accesso per creare e gestire [schemi](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/home) e [set di dati](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview) di Experience Platform.
* Accesso a [Experience Platform Query Service](https://experienceleague.adobe.com/it/docs/experience-platform/query/home) (e possibilità di scrivere codice SQL).
* Accesso a uno strumento in grado di eseguire alcune trasformazioni di dati.
* Accesso a Customer Journey Analytics. Devi essere un [amministratore di prodotto Customer Journey Analytics](/help/technotes/access-control.md) per creare e modificare connessioni e visualizzazioni dati di Customer Journey Analytics.
* [Autenticazione e accesso alle API di Experience Platform (API Catalog Service e API Segmentation Service)](https://experienceleague.adobe.com/it/docs/experience-platform/landing/platform-apis/api-authentication). Devi creare un progetto nella Console per sviluppatori dell’organizzazione e nella sandbox e assicurarti di disporre delle informazioni necessarie per inviare correttamente le chiamate API.

## Passaggi

La soluzione provvisoria prevede i seguenti passaggi:

1. [Seleziona tipi di pubblico (interfaccia utente di Experience Platform)](#select-audiences).
1. [Crea un set di dati abilitato per il profilo (API Experience Platform)](#create-a-profile-enabled-dataset).
1. [Esporta tipi di pubblico (API di Experience Platform)](#export-audiences).
1. [Trasforma l&#39;output (Experience Platform UI e altro)](#transform-the-output).
1. [Creare uno schema e un set di dati (interfaccia utente di Experience Platform)](#create-a-schema-and-dataset).
1. [Aggiungere o modificare una connessione (interfaccia utente di Customer Journey Analytics)](#add-or-edit-a-connection).
1. [Configurare una visualizzazione dati (interfaccia utente di Customer Journey Analytics)](#configure-a-data-view).
1. [Report and analyze (Interfaccia utente di Customer Journey Analytics)](#report-and-analyze).


### Seleziona i tipi di pubblico

La soluzione inizia con l’identificazione dei tipi di pubblico che desideri acquisire in Customer Journey Analytics.

+++ Identificare i tipi di pubblico

Nell’interfaccia utente di Experience Platform:

1. Selezionare **[!UICONTROL Customer]** > ![SegmentAudience](/help/assets/icons2/SegmentAudience.svg) **[!UICONTROL Audiences]**.
1. Selezionare **[!UICONTROL Browse]** e cercare i tipi di pubblico da acquisire e utilizzare in Customer Journey Analytics. Prendi nota di **[!UICONTROL Audience Id]** per ciascuno dei tipi di pubblico per un utilizzo successivo.

   ![Tipi di pubblico](assets/audiences.png)

+++

### Creare un set di dati abilitato per il profilo

È necessario creare un set di dati basato sullo schema **[!UICONTROL XDM Individual Profile]** basato su core. Non è possibile selezionare tale profilo individuale XDM basato su core come schema quando si crea un set di dati nell’interfaccia utente di Experience Platform. Utilizza invece l&#39;API [Catalog Service per creare un set di dati](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/create#create-a-dataset) basato sullo schema `_xdm.context.profile__union`.

+++ Crea richiesta set di dati

#### Richiesta

```shell
curl -X POST \
  'https://platform.adobe.io/data/foundation/catalog/dataSets?requestDataSource=true' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'Content-Type: application/json' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
   "name": "{DATASET_NAME}",
   "schemaRef": {
      "id": "_xdm.context.profile__union",
      "contentType": "application/vnd.adobe.xed+json;version=1"
   },
   "fileDescription": {
      "persistet": true,
      "containerFormat": "parquet",
      "format": "parquet"
   }
}'
```

Dove:

* `DATASET_NAME` è il nome descrittivo del set di dati. Ad esempio: `Segment Export Job Dataset for CJA`.

#### Risposta

```json
["@/dataSets/{DATASET_ID}"]
```

Dove:

* `DATASET_ID` è l&#39;identificatore del set di dati creato.

+++

### Esporta tipi di pubblico

Esporta il pubblico selezionato nel set di dati appena creato. Utilizza l&#39;API del servizio di segmentazione [&#x200B; per creare un processo di esportazione](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/api/export-jobs#create) che invia i tipi di pubblico al set di dati.

+++ Esporta richiesta processo

```shell
curl -X POST https://platform.adobe.io/data/core/ups/export/jobs \
 -H 'Authorization: Bearer {ACCESS_TOKEN}' \
 -H 'Content-Type: application/json' \
 -H 'x-gw-ims-org-id: {ORG_ID}' \
 -H 'x-api-key: {API_KEY}' \
 -H 'x-sandbox-name: {SANDBOX_NAME}' \
 -d '{
    "fields": "{COMMA_SEPARATED_LIST_OF_FULLY_QUALIFIED_FIELD_NAMES}",
    "filter": {
        "segments": [
            {
                "segmentId": "{AUDIENCE_ID_1}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ],
                "segmentId": "{AUDIENCE_ID_2}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ],
                "segmentId": "{AUDIENCE_ID_3}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ]             
             }
        ]
    },
    "destination":{
        "datasetId": "{DATASET_ID}",
        "segmentPerBatch": false
    },
    "schema":{
        "name": "_xdm.context.profile"
    }
}'
```

Dove

* `COMMA_SEPARATED_LIST_OF_FULLY_QUALIFIED_FIELD_NAMES` potrebbe essere `_demoemea.identification.core.ecid, _demoemea.identification.core.email, _demoemea.identification.core.phoneNumber, person.gender, person.name.firstName, person.name.lastName`. Assicurati di includere almeno i campi rilevanti (come personID (e-mail)) che desideri utilizzare nell’analisi del Percorso di clienti.
* `AUDIENCE_ID_x` sono gli identificatori dei tipi di pubblico che desideri esportare.
* `DATASET_ID` è il set di dati creato.


### Risposta

```json
{
  "..."
  "id": "{EXPORT_JOB_ID}",
  "..."
}
```

Dove

* `EXPORT_JOB_ID` è l&#39;identificatore del processo di esportazione.


+++

Utilizza l&#39;API del servizio di segmentazione [&#x200B; per controllare lo stato del processo di esportazione](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/api/export-jobs#get).

+++ Recuperare una richiesta di processo di esportazione specifica

#### Richiesta

```shell
curl -X GET https://platform.adobe.io/data/core/ups/export/jobs/{EXPORT_JOB_ID} \
 -H 'Authorization: Bearer {ACCESS_TOKEN}' \
 -H 'x-gw-ims-org-id: {ORG_ID}' \
 -H 'x-api-key: {API_KEY}' \
 -H 'x-sandbox-name: {SANDBOX_NAME}'
```

#### Risposta

```json
{
  "..."
  "id": "{EXPORT_JOB_ID}",
  "..."
  "status": "SUCCEEDED",
  "..."
}
```

+++

Dopo il completamento del processo di esportazione, verifica se il set di dati contiene batch correttamente acquisiti.

+++ Controllare lo stato di acquisizione

Nell’interfaccia utente di Experience Platform:

1. Selezionare **[!UICONTROL Data Management]** > ![Dati](/help/assets/icons2/Data.svg) **[!UICONTROL Datasets]**.
1. Selezionare il set di dati creato, ad esempio: **[!UICONTROL Segment Export Job Dataset for CJA]**.

   ![Attività set di dati](assets/dataset-activity.png)

1. Verifica i batch acquisiti. Se il set di dati contiene batch non riusciti, utilizzare **[!UICONTROL Data Management]** > ![Monitoraggio](/help/assets/icons2/Monitoring.svg) **[!UICONTROL Monitoring]** per verificare il motivo. Ad esempio, hai utilizzato un nome di campo che non esiste nello schema.
1. Copia il **[!UICONTROL Table name]** del set di dati. Esempio: **[!UICONTROL segment_export_job_dataset_for_cja]**.  Usa questo nome nel passaggio successivo.

+++


### Trasforma l’output

Il formato dei dati nel set di dati non è corretto per Customer Journey Analytics. Per trasformare i dati, utilizza Experience Platform Query Service per recuperarli.

+++ SQL per recuperare i dati del pubblico esportati

Utilizza un client PSQL che si connette a Experience Platform Query Service.

Nell’interfaccia utente di Experience Platform:

1. Selezionare **[!UICONTROL Data Management]** > ![DataSearch](/help/assets/icons2/DataSearch.svg) **[!UICONTROL Queries]**.
1. Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Credentials]**.

Utilizzare le credenziali per configurare il client PSQL per la connessione a Customer Journey Analytics Query Service.

#### Query

```sql
SELECT ROW_NUMBER() OVER (ORDER BY key)::text as _id, personID, key as audienceMembershipId
FROM (
   SELECT {IDENTITY_TO_USE_AS_PERSON_ID} AS personID, explode(segmentMembership.ups)
   FROM {DATASET_TABLE_NAME}
)
WHERE value.status = 'realized' AND (key = '{AUDIENCE_ID_1}' OR key = 'AUDIENCE_ID_2' OR key = 'AUDIENCE_ID_3')
```

Dove:

* `IDENTITY_TO_USE_AS_PERSON_ID` è uno dei campi definiti come parte del processo di esportazione. Ad esempio: `_demoemea.identification.core.email`.
* `AUDIENCE_ID_x` sono i tipi di pubblico definiti come parte del processo di esportazione. È necessario specificare questi tipi di pubblico ancora una volta, in quanto la specifica nel processo di esportazione è un filtro a livello di riga. Tale filtro a livello di riga restituisce profili per i segmenti specificati con tutte le appartenenze al segmento per ciascuno dei profili.


#### Risultati

Il risultato della query, in formato JSON, dovrebbe essere simile al seguente:

```json
[
   {
      "_id": "1",
      "personID": "{PERSON_ID_x}",
      "audienceMembershipId": "{AUDIENCE_ID_x}"
   },
   {
      "_id": "2",
      "personID": "PERSON_ID_y",
      "audienceMembershipId": "{AUDIENCE_ID_x}"
   }

]
```

Dove:

* `PERSON_ID_x` sono i valori dell&#39;identificatore da utilizzare come ID persona. Ad esempio, `john.doe@gmail.com` quando si utilizza la posta elettronica.
* `AUDIENCE_ID_x` sono gli identificatori del pubblico.

+++

È necessario trasformare questi dati JSON per aggiungere il nome tenant dell’ambiente e fornire un nome più semplice per il pubblico.

+++ Trasforma JSON

Il JSON finale sarà simile al seguente:

```json
[
   {
      "_id": "1",
      "personID": "{PERSON_ID_x}",
      "{TENANT_NAME}": {
         "audienceMembershipId": "{AUDIENCE_ID_x}",
         "audienceMembershipName": "{AUDIENCE_FRIENDLY_NAME_x}"
      }
  },
  {
      "_id": "2",
      "personID": "{PERSON_ID_y}",
      "{TENANT_NAME}": {
         "audienceMembershipId": "{AUDIENCE_ID_y}",
         "audienceMembershipName": "{AUDIENCE_FRIENDLY_NAME_y}"
      }
    }
  }

]
```

Dove:

* `TENANT_NAME` è il nome del tenant. Ad esempio: `_demoemea`.
* `PERSON_ID_x` sono i valori dell&#39;identificatore che si desidera utilizzare come ID persona. Ad esempio, `john.doe@gmail.com` quando si utilizza la posta elettronica.
* `AUDIENCE_ID_x` sono gli identificatori del pubblico.
* `AUDIENCE_FRIENDLY_NAME_x` sono nomi descrittivi di pubblico per gli ID pubblico. Ad esempio: `Luma - Blue+ Members`.

Utilizza lo strumento preferito per trasformare il JSON originale in questo formato.

+++


### Creare uno schema e un set di dati

Per utilizzare il JSON trasformato come dati del pubblico esportati in Customer Journey Analytics, è necessario creare uno schema dedicato.

+++ Crea schema

Per creare lo schema:

Nell’interfaccia utente di Experience Platform:

1. Selezionare **[!UICONTROL Data Management]** > ![Schema](/help/assets/icons2/Schema.svg) **[!UICONTROL Schemas]**.
1. Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create schema]**. Selezionare **[!UICONTROL Standard]** dal menu a discesa.
1. Selezionare **[!UICONTROL Manual]** nella finestra di dialogo **[!UICONTROL Create a schema]** e utilizzare **[!UICONTROL Select]** per continuare.
1. Nella procedura guidata **[!UICONTROL Create schema]**, nel passaggio **[!UICONTROL Select a class]**:
   1. Seleziona **[!UICONTROL Individual Profile]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL Next]** (Salva).
1. Nella procedura guidata **[!UICONTROL Create schema]**, nel passaggio **[!UICONTROL Name and review]**:
   1. Immetti **[!UICONTROL Schema display name]**. Ad esempio: `Audience Export for CJA Schema`.
   1. (facoltativo) Immettere **[!UICONTROL Description]**.
   1. Seleziona **[!UICONTROL Finish]**.
1. Impostare lo schema in modo che contenga un gruppo di campi personalizzato, denominato ad esempio **[!UICONTROL Audience Membership]**, contenente due campi denominati **[!UICONTROL audienceMembershipId]** e **[!UICONTROL audienceMembershipName]**.
1. Assicurarsi che il campo **[!UICONTROL personID]** sia un **[!UICONTROL Identity]**, **[!UICONTROL Primary Identity]** e che abbia **[!UICONTROL Email]** come I&#x200B;**[!UICONTROL dentity namespace]**.

   ![Segmento per esportazione](assets/segment-for-export.png)

1. **[!UICONTROL Apply]** tutte le modifiche. Selezionare **[!UICONTROL Save]** per salvare lo schema.

+++

Crea un set di dati e utilizzalo per acquisire i dati JSON trasformati.

+++ Creare un set di dati e acquisire dati

Nell’interfaccia utente di Experience Platform:

1. Selezionare **[!UICONTROL Data Management]** > ![Schema](/help/assets/icons2/Schema.svg) **[!UICONTROL Datasets]**.
1. Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create dataset]**.
1. Seleziona **[!UICONTROL Create dataset from schema]**.
1. Nella procedura guidata **[!UICONTROL Create dataset from schema]**, nel passaggio **[!UICONTROL Select schema]**:
   1. Seleziona lo schema appena creato. Ad esempio: **[!UICONTROL Audience Export for CJA Schema]**.
   1. Seleziona **[!UICONTROL Next]**.
1. Nella procedura guidata **[!UICONTROL Create dataset from schema]**, nel passaggio **[!UICONTROL Configure dataset]**:
   1. Immetti **[!UICONTROL Name]** per il set di dati.
   1. (facoltativo) Immetti **[!UICONTROL Description]** per il set di dati.
   1. Seleziona **[!UICONTROL Finish]**.
1. In **[!UICONTROL Datasets]** > **[!UICONTROL _nome del set di dati_]**, trascina il file di dati JSON trasformato e rilascia il file in **[!UICONTROL Drag and drop files]**. Questa azione avvia l’acquisizione dei dati JSON esportati nel set di dati.
1. Verifica i batch acquisiti. Se il set di dati contiene batch non riusciti, utilizzare **[!UICONTROL Data Management]** > ![Monitoraggio](/help/assets/icons2/Monitoring.svg) **[!UICONTROL Monitoring]** per verificare il motivo. Ad esempio, hai definito un nome di campo nel JSON che non esiste nello schema.


+++

### Aggiungere o modificare una connessione

Una volta acquisiti correttamente i dati JSON trasformati che contengono i dati sul pubblico da Experience Platform, puoi aggiungere il set di dati a una connessione nuova o esistente in Customer Journey Analytics.

+++ Aggiungi set di dati alla connessione

Nell’interfaccia utente di Customer Journey Analytics:

1. Seleziona **[!UICONTROL Data Management]** > **[!UICONTROL Connections]**.
1. Crea una nuova connessione/ Definisci **[!UICONTROL Connection settings]** e **[!UICONTROL Data settings]**. In alternativa, selezionare una connessione esistente e utilizzare ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit Connection]** per modificare la connessione.
1. Selezionare ![DataAdd](/help/assets/icons/DataAdd.svg) **[!UICONTROL Add datasets]**.
1. Seleziona il set di dati creato e in cui sono stati acquisiti i dati JSON trasformati.
1. Configura il set di dati. Ad esempio:

   ![Connessione - Set di dati con dati del pubblico esportati](assets/connection-add-dataset.png)

1. **[!UICONTROL Save]** connessione.

+++

### Configurare una visualizzazione dati

Configura una visualizzazione dati per la connessione appena creata o modificata.

+++ Definire i componenti del pubblico

1. Seleziona **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.
1. Modificare una visualizzazione dati esistente o crearne una nuova.
1. Nella scheda **[!UICONTROL Components]** della visualizzazione dati, accertati che **[!UICONTROL Audience Membership Id]** e **[!UICONTROL Audience Membership Name]** siano aggiunti come componenti dimensione.

   ![Componenti della visualizzazione dati](assets/dataview-components.png)

1. Selezionare **[!UICONTROL Save and Continue]** per salvare la visualizzazione dati.

+++

### Rapporto e analisi.

Infine, utilizza Analysis Workspace per creare rapporti sui dati del pubblico di Experience Platform in uno o più pannelli che utilizzano la visualizzazione dati con i componenti di iscrizione al pubblico.


<!--

## Step 1: Select audiences in Real-time Customer Profile {#audience}

Experience Platform [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html) lets you see a holistic view of each individual customer by combining data from multiple channels, including online, offline, CRM, and third party. 

You likely already have audiences in RTCP that may have come from various sources. Select one or more audiences to ingest into Customer Journey Analytics. For example, WKND Fly Platinum and Gold Fly Club Members.




## Step 2: Create a Profile Union dataset for the export

In order to export the audience to a dataset that you can ingest in Customer Journey Analytics as profiles, create a dataset whose schema is a Profile [Union schema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html#understanding-union-schemas).

Union schemas are composed of multiple schemas that share the same class and have been enabled for Profile. The union schema enables you to see an amalgamation of all of the fields contained within schemas sharing the same class. Real-time Customer Profile uses the union schema to create a holistic view of each individual customer.

## Step 3: Export an audience to the Profile Union dataset via API call {#export}

Before you can bring an audience into Customer Journey Analytics, you need to export it to an Adobe Experience Platform dataset. This can only be done using the Segmentation API, and specifically the [Export Jobs API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html). 

You can create an export job using the audience ID of your choice, and put the results in the Profile Union Adobe Experience Platform dataset you created in Step 2. Although you can export various attributes/events for the audience, you only need to export the specific profile ID field that matches the person ID field used in the Customer Journey Analytics connection you will be leveraging (see below in Step 5).

## Step 4: Edit the export output 

The results of the export job need to be transformed into a separate Profile dataset in order to be ingested into Customer Journey Analytics.  This transformation can be done with [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html), or another transformation tool of your choice. We only need the Profile ID (that will match the Person ID in Customer Journey Analytics) and one or more audience ID(s) to do the reporting in Customer Journey Analytics.

The standard export job, however, contains more data and so we need to edit this output to remove extraneous data, as well as move some things around.  Also, you need to create a schema/dataset first before you add the transformed data to it.

Here is an example of the export output in the Profile union dataset, **before** any editing:

![Unedited output](../assets/export-unedited.png)

Note the following:

* The audience ID is contained under `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* The status has to be "realized", or "entered", but not "exited".

This is the format of the Profile dataset that you can send into Customer Journey Analytics.

![Edited output](../assets/export-edited.png)

Here are the data elements that need to be present:

* `_aresprodvalidation` string field: Refers to your Organization ID. Yours will be different.
* `personID` string field: This is the standard XDM schema field on Profile datasets to identity the person. Use the Profile ID from the export.
* `audienceMembershipId` string field: The audience ID from the export.  NOTE: This field can be named whatever you want (from your own schema).
* Add a friendly name for the audience (`audienceMembershipIdName`), such as

   ![Friendly audience name](../assets/audience-name.png)
   
* Add other audience metadata if you desire.

## Step 5: Add this Profile dataset to an existing connection in Customer Journey Analytics

You could [create a new connection](/help/connections/create-connection.md), but most customers will want to add the Profile dataset to an existing connection. The audience IDs "enrich" the existing data in Customer Journey Analytics.

## Step 6: Modify existing (or create new) Customer Journey Analytics data view

Add `audienceMembershipId`, `audienceMembershipIdName` and `personID` to the data view.

## Step 7: Report in Workspace

You can now report on `audienceMembershipId`, `audienceMembershipIdName` and `personID` in Workspace.

## Additional notes

* You should  perform this process on a regular cadence, so that audience data is constantly refreshed within Customer Journey Analytics.
* You can import multiple audiences within a single Customer Journey Analytics connection. This adds additional complexity to the process, but it is possible. For this to work, you need to make a few modifications to the above process:
   1. Perform this process for each desired audience in your audience collection within RTCP.
   1. Customer Journey Analytics supports arrays/object arrays in profile datasets. Using an [array of objects](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html) for the audienceMembershipId or audienceMembershipIdName is the best option. 
   1. In your data view, create a new dimension using the Substring transformation on the `audienceMembershipId` field to convert the comma-separated values string to an array. NOTE: there is currently a limit of 10 values in the array.
   1. You can now report on this new dimension `audienceMembershipIds` within Customer Journey Analytics Workspace.

-->