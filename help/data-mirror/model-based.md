---
title: Eseguire il mirroring e utilizzare dati basati su modelli
description: Spiegare come eseguire il mirroring e utilizzare i dati basati su modelli in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: 17f72954-085c-46a8-bc28-6af0a4eb159a
source-git-commit: edf7bdac87d9bed48244ad80521bbbf83c48f7b6
workflow-type: tm+mt
source-wordcount: '2004'
ht-degree: 16%

---

# Eseguire il mirroring e utilizzare dati basati su modelli

{{release-limited-testing}}

Questa guida rapida spiega come utilizzare [Experience Platform Data Mirror per Customer Journey Analytics](data-mirror.md) per eseguire il mirroring dei dati basati su modelli da una soluzione nativa di data warehouse in Adobe Experience Platform. E poi usate quei dati in Customer Journey Analytics.

Per eseguire questo caso d’uso, è necessario:

* **Utilizzare una soluzione nativa di data warehouse** per memorizzare i dati di cui si desidera eseguire il mirroring in Experience Platform. E poi utilizzare quei dati in Customer Journey Analytics per generare rapporti e per analizzarli.

* **Imposta uno schema** in Experience Platform per definire il modello (schema) dei dati di cui vuoi eseguire il mirroring.

* **Utilizza un connettore di origine** in Experience Platform per ottenere i dati con mirroring in un set di dati.

* **Impostare una connessione** in Customer Journey Analytics. Questa connessione deve (almeno) includere il set di dati basato su modello di Experience Platform.

* **Configurare una visualizzazione dati** in Customer Journey Analytics per definire le metriche e le dimensioni da utilizzare in Analysis Workspace.

* **Configurare un progetto** in Customer Journey Analytics per generare rapporti e visualizzazioni.

Experience Platform Data Mirror per Customer Journey Analytics richiede schemi basati su modelli.



>[!NOTE]
>
>Questa guida rapida è una guida semplificata su come specchiare i dati basati su modelli in Adobe Experience Platform e utilizzarli in Customer Journey Analytics. Ti consigliamo vivamente di esaminare le informazioni aggiuntive quando vi fai riferimento.


## Utilizzare una soluzione nativa di data warehouse

Questa guida rapida utilizza [[!DNL Google BigQuery]](datawarehouse.md#google-bigquery) come soluzione nativa del data warehouse. Altre [soluzioni supportate](datawarehouse.md) sono [[!DNL Snowflake]](datawarehouse.md#snowflake) e [[!DNL Azure Databricks]](datawarehouse.md#azure-databricks).

All&#39;interno di [!DNL Google BigQuery], i seguenti dati di esempio vengono memorizzati e aggiornati regolarmente in una tabella denominata **[!UICONTROL eventdata]**.

+++ Dettagli dei dati evento di esempio

| timestamp | id | pagename | personid | trackingcode | ordini | importo ricavi |
| :---                      |  ---: | :---              | :---            | :---          |   ---: | :---           |
| 06/03/2025 T19:15:39+00:00 | 10001 | pagina home | person-1abc123 | abc123 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10002 | pagina di conferma | person-1abc123 |               | 1 | 174,25 |
| 06/03/2025 T19:15:39+00:00 | 10003 | pagina home | person-2def123 | def123 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10004 | pagina home | person-3ghi123 | ghi123 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10005 | pagina di conferma | person-3ghi123 |               | 1 | 149,25 |
| 06/03/2025 T19:15:39+00:00 | 10006 | pagina home | person-4abc456 | abc456 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10007 | pagina home | person-5def456 | def456 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10008 | pagina home | person-6ghi456 | ghi456 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10009 | pagina di conferma | person-6ghi456 |               | 1 | 159,25 |
| 06/03/2025 T19:15:39+00:00 | 10010 | pagina home | person-7abc789 | abc789 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10011 | pagina home | person-8def789 | def789 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10012 | pagina home | person-9ghi789 | ghi789 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10013 | pagina di conferma | person-9ghi789 |               | 1 | 124,25 |
| 06/03/2025 T19:15:39+00:00 | 10014 | pagina home | person-10abc987 | abc987 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10015 | pagina home | person-11def987 | def987 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10016 | pagina home | person-12ghi987 | ghi987 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10017 | pagina home | person-13abc654 | abc654 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10018 | pagina home | person-14def654 | def654 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10019 | pagina home | person-15ghi654 | ghi654 |        |                |
| 06/03/2025 T19:15:39+00:00 | 10020 | pagina di conferma | person-15ghi654 |               | 1 | 174,25 |

+++

I dati vengono memorizzati in una tabella di database con uno schema associato. Per esaminare la tabella del database:

1. Accedi a Google BigQuery.
1. Seleziona **[!UICONTROL BigQuery]** > **[!UICONTROL Studio]**.
1. Seleziona il progetto, il set di dati e la tabella. Nella scheda **[!UICONTROL Schema]** viene visualizzata una panoramica dello schema per i dati dell&#39;evento.

   ![BigQuery Google - Schema](assets/googlebg-schema.png)

Per esaminare i dati:

1. Seleziona **[!UICONTROL Query]**.
1. Eseguire una query di esempio nell&#39;editor delle query, dove `project` è il nome del progetto e `datasets` è il nome dei set di dati:

   ```sql
   SELECT * FROM `project.datasets.eventdata` LIMIT 100
   ```

   ![BigQuery Google - Query di esempio](assets/googlebg-samplequery.png)

In Experience Platform Data Mirror per Customer Journey Analytics, le tabelle nella soluzione nativa del data warehouse devono essere abilitate per la cronologia delle modifiche. Per verificare che la tabella sia abilitata per la cronologia modifiche:

1. Eseguire l&#39;istruzione SQL seguente nell&#39;editor delle query per verificare l&#39;impostazione, dove `project` è il nome del progetto e `datasets` è il nome dei set di dati:

   ```sql
   SELECT
      table_name,
      MAX(CASE WHEN option_name = 'enable_change_history' THEN option_value END) AS enable_change_history
   FROM `project.datasets.INFORMATION_SCHEMA.TABLE_OPTIONS`
   WHERE table_name = 'eventdata'
   GROUP BY table_name
   ORDER BY table_name;
   ```

1. Se il risultato non è **[!UICONTROL TRUE]**, utilizzare la seguente istruzione SQL per abilitare la cronologia delle modifiche, dove `project` è il nome del progetto e `datasets` è il nome dei set di dati:

   ```sql
   ALTER TABLE `project.datasets.eventdata` 
   SET OPTIONS (enable_change_history = TRUE);
   ```

I dati nella tabella nella soluzione nativa del data warehouse sono pronti per Experience Platform Data Mirror per Customer Journey Analytics.


## Configurare uno schema

Per eseguire il mirroring dei dati in Experience Platform, devi innanzitutto definire lo schema per i dati. Tutti i dati di cui desideri eseguire il mirroring in Experience Platform e che utilizzano Experience Platform Data Mirror for Customer Journey Analytics devono essere conformi a uno schema basato su modello.

Definisci uno schema che modella questi dati. Per configurare lo schema:

1. Nell’interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Schemas]** (Set di dati) all’interno di **[!UICONTROL Data Management]** (GESTIONE DATI).

1. Seleziona **[!UICONTROL Create schema]** (Crea set di dati).
1. Dal menu a discesa, selezionare **[!UICONTROL Model-based]**.
1. Se viene visualizzata una finestra a comparsa con l&#39;opzione di selezionare tra **[!UICONTROL Create manually]** o **[!UICONTROL Upload a DDL file]**:
   1. Seleziona **[!UICONTROL select Create manually]**.

      ![Configurazione dello schema - Creazione manuale](assets/model-based-manual.png)

   1. Seleziona **[!UICONTROL Next]**.
1. Nell&#39;interfaccia **[!UICONTROL Schemas]** > **[!UICONTROL Create model-based schema]**:
   1. Immetti **[!UICONTROL Schema display name]**. Ad esempio: `Sample Event Feed Schema`.
   1. Immetti **[!UICONTROL Description]**. Ad esempio: `Sample event feed schema for a model-based schema`.
   1. Seleziona **[!UICONTROL Time series]** (Schema predefinito) come **[!UICONTROL Schema behavior]** (Schema di destinazione). Selezionare **[!UICONTROL Time series]** per i dati basati su serie temporali e **[!UICONTROL Record]** per i dati basati su record. Il comportamento definisce la struttura dello schema e le proprietà incluse.

      Experience Platform Data Mirror per Customer Journey Analytics viene utilizzato principalmente per i dati delle serie temporali (ad esempio, i dati degli eventi).

      ![Configurazione schema](assets/model-based-create-schema.png)

   1. Seleziona **[!UICONTROL Finish]**.

1. Nell&#39;interfaccia **[!UICONTROL Schemas]** > **[!UICONTROL Sample Event Feed Schema]** viene visualizzato un avviso che indica che gli schemi basati su modelli supportano l&#39;acquisizione come righe di modifica.

   ![Configurazione schema](assets/model-based-create-schema-empty.png)

   L’acquisizione come righe di modifica è nota anche come Change Data Capture (CDC). Per supportare l’acquisizione dei dati di modifica, lo schema richiede:

   * Chiave primaria.
   * Descrittore della versione.
   * Descrittore della marca temporale per i dati della serie temporale.

1. Seleziona ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) accanto a **[!UICONTROL Sample Event Feed Schema]** per iniziare ad aggiungere campi allo schema. Aggiungi i campi seguenti con tipo di dati e attributi aggiuntivi allo schema.

   | Nome campo: | Nome visualizzato | Tipo | Attributi aggiuntivi |
   |---|---|---|---|
   | `id` | `Id` | **[!UICONTROL Integer]** | Descrittore di versione ![SelectBox](/help/assets/icons/SelectBox.svg) |
   | `orders` | `Orders` | **[!UICONTROL Integer]** | |
   | `pagename` | `Page Name` | **[!UICONTROL String]** | |
   | `personid` | `Person Id` | **[!UICONTROL String]** | ![SelectBox](/help/assets/icons/SelectBox.svg) Chiave primaria<br/>![SelectBox](/help/assets/icons/SelectBox.svg) Identity<br/>Selezionare CRMID per lo spazio dei nomi Identity. |
   | `revenueamount` | `Revenue Amount` | **[!UICONTROL Double]** | |
   | `timestamp` | `Timestamp` | **[!UICONTROL DateTime]** | ![SelectBox](/help/assets/icons/SelectBox.svg) descrittore timestamp |
   | `trackingcode` | `Tracking Code` | **[!UICONTROL String]** | |


   * Campo **[!UICONTROL id]** configurato come **[!UICONTROL Version descriptor]**.

     ![Descrittore versione](assets/platform-schema-id.png)

   * Il campo **[!UICONTROL personid]** è configurato insieme a **[!UICONTROL timestamp]** come **[!UICONTROL Primary key]**. Selezionare ![Aggiungi](/help/assets/icons/Add.svg) **[!UICONTROL Create composite primary key]** per creare una chiave composita.

     ![Chiave composita](assets/platform-schema-compositekey.png)

     Anche il campo **[!UICONTROL personid]** è configurato come **[!UICONTROL Identity]**, con **[!UICONTROL CRMID]** come **[!UICONTROL Identity namespace]**.

     ![Descrittore della persona](assets/platform-schema-personid.png)

   * Il campo **[!UICONTROL timestamp]** è configurato insieme al campo **[!UICONTROL personid]** come **[!UICONTROL Primary key]**. Anche il campo **[!UICONTROL timestamp]** è configurato come **[!UICONTROL Timestamp descriptor]**. È sufficiente definire un campo come **[!UICONTROL Timestamp descriptor]** per i dati basati su modello della serie temporale.

     ![Descrittore marca temporale](assets/platform-schema-timestamp.png)


   Se **[!UICONTROL Primary key]**, **[!UICONTROL Version descriptor]** e **[!UICONTROL Timestamp descriptor]** sono stati definiti correttamente, l&#39;avviso sopra la definizione dello schema scompare.

1. Seleziona **[!UICONTROL Save]** (Salva) per salvare lo schema.


## Utilizzare un connettore di origine

Utilizza un connettore di origine per collegare la soluzione nativa di data warehouse ad Experience Platform.

Nell’interfaccia di Experience Platform:

1. Seleziona **[!UICONTROL Sources]**.
1. Selezionare o cercare **[!UICONTROL Google BigQuery]**.
1. Seleziona **[!UICONTROL Add data]**.

La procedura guidata Aggiungi dati illustra i passaggi seguenti per connettere i dati dalla tabella in [!DNL Google BigQuery] ad Experience Platform.

### Autenticazione

Nel passaggio **[!UICONTROL Authentication]**, seleziona:

* **[!UICONTROL Existing account]** quando si dispone già di una configurazione account per Google BigQuery. Procedi al passaggio [Seleziona dati](#select-data).
* **[!UICONTROL New account]** quando è necessario connettersi a Google BigQuery.
   1. Specificare un **[!UICONTROL Account name]** e (facoltativo) **[!UICONTROL Description]**.
   1. Selezionare **[!UICONTROL Authentication type]**: **[!UICONTROL Basic Authentication]** o **[!UICONTROL Service Authentication]**. In base alla selezione, fornisci l’input richiesto.
   1. Seleziona **[!UICONTROL Connect to source]**

      ![BigQuery Google - Autenticazione](assets/googlebg-authentication.png)

      Verifica della connessione. Un ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg) **[!UICONTROL Connected]** ha indicato una connessione riuscita.

   1. Seleziona **[!UICONTROL Next]**.

  Consulta la documentazione di Experience Platform per informazioni dettagliate su come connettersi e autenticare quando utilizzi il connettore [Azure Databricks](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/databricks) o [Snowflake](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/snowflake).


### Selezionare i dati

Nel passaggio **[!UICONTROL Select data]** (Configura):

1. Selezionare la tabella dall&#39;elenco delle tabelle. Ad esempio: **[!UICONTROL eventdata]**.

   ![Experience Platform - Connettore Source - Seleziona dati](assets/platform-sources-selectdata-event.png)

   Viene visualizzato un esempio dei dati per la verifica.

1. Seleziona **[!UICONTROL Next]** (Avanti) per continuare.


### Dettagli del flusso di dati

Nel passaggio **[!UICONTROL Dataflow detail]** (Configura):

1. Seleziona **[!UICONTROL Enable change data capture]**. Viene visualizzata una casella di informazioni **[!UICONTROL Change data capture requirement]** con ulteriori informazioni.
1. Selezionare **[!UICONTROL New dataset]** per **[!UICONTROL Target dataset]** per creare un nuovo set di dati contenente i dati con mirroring.
1. Immetti un **[!UICONTROL Output dataset name]**. Ad esempio: `event-data-mirror`.
1. Selezionare lo schema basato su modello creato in precedenza dal menu a discesa **[!UICONTROL Schema]**. Ad esempio: **[!UICONTROL Sample Event Feed Schema]**.

   ![Experience Platform - Connettore Source - Dettagli flusso di dati](assets/platform-sources-dataflowdetail-event.png)

1. Specifica altri dettagli.
1. Seleziona **[!UICONTROL Next]**.


### Mappatura

Nel passaggio **[!UICONTROL Mapping]** (Configura):

1. Mappa i campi. Dallo schema in Google BigQuery (**[!UICONTROL Source data]**) ai campi nello schema definiti in Experience Platform (**[!UICONTROL Target fields]**).

   ![Experience Platform - Connettore Source - Mappatura](assets/platform-sources-mapping.png)

1. Se tutti i campi sono mappati correttamente, selezionare **[!UICONTROL Next]** per continuare.


### Pianificazione

Nel passaggio **[!UICONTROL Scheduling]** (Configura):

1. Specificare **[!UICONTROL Frequency]** e **[!UICONTROL Interval]** per pianificare la sincronizzazione dei dati con mirroring.
1. Specificare **[!UICONTROL Start time]** per la pianificazione.

   ![Experience Platform - Connettore Source - Pianificazione](assets/platform-sources-scheduling.png)

1. Seleziona **[!UICONTROL Next]** (Avanti) per continuare.


### Rivedi

Nel passaggio **[!UICONTROL Review]**.

1. Controlla la configurazione del connettore di origine.

   ![Experience Platform - Connettore Source - Revisione](assets/platform-sources-review.png)

1. Seleziona **[!UICONTROL Finish]**. Viene visualizzato il flusso di dati configurato.

   ![Experience Platform - Connettore Source - Flusso di dati](assets/platform-sources-finish.png)


## Configurare una connessione

In questa guida rapida puoi creare una nuova connessione per utilizzare i dati con mirroring da Experience Platform. In alternativa, è possibile aggiungere i dati con mirroring a una connessione esistente.

Nell’interfaccia di Customer Journey Analytics:

1. Seleziona **[!UICONTROL Connections]** dal menu **[!UICONTROL Data Management]**.
1. Seleziona **[!UICONTROL Create new connection]**.
1. Specificare i parametri obbligatori **[!UICONTROL Connection name]**, **[!UICONTROL Sandbox]**, **[!UICONTROL Average number of daily evens]** e altri parametri facoltativi.
1. Seleziona **[!UICONTROL Add datasets]**.

   1. Nel passaggio **[!UICONTROL Select datasets]** di **[!UICONTROL Add datasets]**:

      1. Seleziona il set di dati contenente i dati con mirroring. Ad esempio: **[!UICONTROL event-data-mirror]**. Il set di dati ha **[!UICONTROL Model]** come **[!UICONTROL Dataset type]**.

         ![CJA - Connessioni - Aggiungi set di dati](assets/cja-add-dataset.png)

      1. Aggiungi eventuali set di dati aggiuntivi rilevanti per la connessione.
      1. Seleziona **[!UICONTROL Next]**.

   1. Nel passaggio **[!UICONTROL Dataset settings]** di **[!UICONTROL Add datasets]**:

      Per il set di dati basato su modello **[!UICONTROL event-data-mirror]**

      1. Seleziona **[!UICONTROL Event]** come **[!UICONTROL Dataset type]**.
      1. Selezionare il campo **[!UICONTROL PersonId]** come **[!UICONTROL Person ID]**.
      1. **[!UICONTROL Timestamp]** viene popolato automaticamente come **[!UICONTROL Timestamp]**.
      1. Seleziona **[!UICONTROL Other]** come **[!UICONTROL Data source type]**.
      1. Immetti `Google BigQuery Event Data` come **[!UICONTROL Data source description]**.
      1. Specificare altri dettagli, ad esempio **[!UICONTROL Import all new data]** e **[!UICONTROL Backfill all existing data]**.

         ![CJA - Connessione - Impostazioni set di dati](assets/cja-add-dataset-2.png)

      Facoltativamente, specifica i dettagli per altri set di dati.

   1. Seleziona **[!UICONTROL Add datasets]** (Aggiungi set di dati).
1. Seleziona **[!UICONTROL Save]** (Salva).

Dopo aver creato una [connessione](/help/connections/overview.md), puoi eseguire varie attività di gestione. Ad esempio [selezione e combinazione di set di dati](/help/connections/combined-dataset.md), [controllo dello stato dei set di dati di una connessione e dello stato di acquisizione dei dati](/help/connections/manage-connections.md) e altro ancora.


## Configurare una visualizzazione dati

Per creare la visualizzazione dati:

1. Nell&#39;interfaccia di Customer Journey Analytics, selezionare **[!UICONTROL Data views]**, facoltativamente da **[!UICONTROL Data management]**, nel menu principale.

2. Seleziona **[!UICONTROL Create new data view]** (Crea nuova visualizzazione dati).

3. Nel passaggio **[!UICONTROL Configure]** (Configura):

   1. Seleziona la connessione dall’elenco **[!UICONTROL Connection]** (Connessioni).

   1. Assegna un nome e (facoltativamente) una descrizione alla connessione.

   1. Seleziona **[!UICONTROL Save and continue]** (Crea nuova visualizzazione dati).

4. Nel passaggio **[!UICONTROL Components]** (Configura):

   1. Aggiungere qualsiasi campo schema e/o componente standard che si desidera includere nelle caselle del componente **[!UICONTROL METRICS]** o **[!UICONTROL DIMENSIONS]**. Assicurati di aggiungere campi rilevanti dal set di dati che contiene i dati con mirroring. Per accedere a questi campi:

      1. Seleziona **[!UICONTROL Event datasets]** (Aggiungi set di dati).
      1. Seleziona **[!UICONTROL Adhoc & Model-based fields]** (Salva).
      1. Trascinare i campi dagli schemi basati su modelli in **[!UICONTROL METRICS]** o **[!UICONTROL DIMENSIONS]**.

         ![Aggiungi campo basato su modello come componenti](assets/cja-add-dataset-folder-dv.png)

   1. Definire i campi derivati per i campi che non hanno il tipo corretto, non sono nel formato corretto o che si desidera modificare per altri motivi. Ad esempio, per **[!UICONTROL Revenue Amount]**.

      1. Seleziona **[!UICONTROL Create derived field.]**
      1. Nell’editor campi derivati:
         1. Definisci un nuovo campo `Revenue Amount (Numeric)`, come indicato di seguito.

            ![CJA - Visualizzazione dati - Campo derivato](assets/cja-dataview-derived-fields.png)

         1. Seleziona **[!UICONTROL Save]**.
      1. Trascina il nuovo campo derivato **[!UICONTROL Revenue Amount (Numeric)]** e rilascia il campo in **[!UICONTROL METRICS]**.

         ![CJA - Visualizzazione dati - Campi basati su modello](assets/cja-add-dataset-folder-dv.png)

   1. Seleziona **[!UICONTROL Save and continue]** (Crea nuova visualizzazione dati).

5. Nel passaggio **[!UICONTROL Settings]** (Configura):

   Lascia le impostazioni così come sono e seleziona **[!UICONTROL Save and finish]** (Salva e fine).

Per ulteriori informazioni su come creare e modificare una visualizzazione dati, vedere [Panoramica delle visualizzazioni dati](../data-views/data-views.md). Quali componenti sono disponibili per l’utilizzo nella visualizzazione dati e come utilizzare le impostazioni di segmenti e sessioni.


## Configurare un progetto

Analysis Workspace è uno strumento di browser flessibile che consente di creare analisi rapidamente e condividere informazioni basate sui dati. Usa i progetti Workspace per combinare componenti dati, tabelle e visualizzazioni per sviluppare analisi da condividere con altri nella tua organizzazione.

Per creare il progetto:

1. Nell&#39;interfaccia di Customer Journey Analytics, seleziona **[!UICONTROL Workspace]** nel menu principale.

2. Seleziona **[!UICONTROL Projects]** (Progetti) nel pannello di navigazione a sinistra.

3. Seleziona **[!UICONTROL Create project]**. Nel popup:


   1. Seleziona **[!UICONTROL Blank Workspace project]** (Aggiungi set di dati).

   1. Seleziona **[!UICONTROL Create]** (Salva).


4. Nell&#39;area di lavoro **[!UICONTROL New project]**, accertati che la [visualizzazione dati](#set-up-a-data-view) sia selezionata. La visualizzazione dati è collegata alla [connessione](#set-up-a-connection) che contiene i dati con mirroring.

5. Per creare il primo rapporto, trascina dimensioni e metriche su **[!UICONTROL Freeform table]** nel pannello **[!UICONTROL Freeform]**. Trascinare **[!UICONTROL Revenue Amount (Numeric)]** su **[!UICONTROL _Trascinare una metrica qui_]**. Trascinare **[!UICONTROL PersonId]** e rilasciare il campo sull&#39;intestazione della prima colonna. Effettua altre regolazioni che ritieni opportune.

   Il risultato finale è una panoramica dei profili e dei relativi ricavi basati su dati con mirroring provenienti da una tabella BigQuery di Google.

   ![Workspace - Progetto di esempio](assets/cja-sample-project.png)

Per ulteriori informazioni su come creare progetti e generare analisi utilizzando componenti, visualizzazioni e pannelli, consulta la sezione [Panoramica di Analysis Workspace](../analysis-workspace/home.md).

>[!SUCCESS]
>
>Hai completato tutti i passaggi. Per iniziare, definisci quali dati di mirroring desideri raccogliere (schema) da una soluzione nativa di data warehouse. E dove memorizzare tali dati (set di dati) in Experience Platform. Hai configurato il connettore di origine appropriato per fornire i dati con mirroring in Experience Platform. Hai definito una connessione in Customer Journey Analytics per utilizzare i dati dell’evento con mirroring e (facoltativamente) altri dati. La definizione della visualizzazione dati ti consente di specificare la dimensione e le metriche da utilizzare dai dati con mirroring. E infine hai creato il tuo primo progetto visualizzando e analizzando i tuoi dati con mirroring.
