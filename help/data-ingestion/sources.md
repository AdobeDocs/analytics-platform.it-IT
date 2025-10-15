---
title: Inserire e utilizzare i dati utilizzando i connettori di origine
description: Spiega come inserire e utilizzare i dati utilizzando i connettori di origine in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: 813d3213-86b3-431a-821c-174e5e36d032
role: Admin
source-git-commit: bc2c959497230d7672d43d5cd409ca62d4627d6a
workflow-type: tm+mt
source-wordcount: '1888'
ht-degree: 76%

---

# Inserire e utilizzare i dati utilizzando i connettori di origine

Questa guida introduttiva spiega come inserire dati in Adobe Experience Platform utilizzando un connettore di origine per un provider di dati e quindi utilizzarli in Customer Journey Analytics.

A questo scopo, è necessario:

- **Configurare uno schema e un set di dati** in Adobe Experience Platform per definire il modello (schema) dei dati da raccogliere e dove raccogliere effettivamente i dati (set di dati).

- **Utilizzare un connettore di origine** in Adobe Experience Platform per inserire i dati nel set di dati configurato.

- **Impostare una connessione** in Customer Journey Analytics. Questa connessione deve includere almeno il set di dati di Adobe Experience Platform.

- **Configurare una visualizzazione dati** in Customer Journey Analytics per definire le metriche e le dimensioni da utilizzare in Analysis Workspace.

- **Configurare un progetto** in Customer Journey Analytics per generare rapporti e visualizzazioni.



>[!NOTE]
>
>Questa guida rapida è una guida semplificata su come acquisire i dati utilizzando un connettore di origine in Adobe Experience Platform e utilizzarli in Customer Journey Analytics. Ti consigliamo vivamente di esaminare le informazioni aggiuntive quando vi fai riferimento.


## Configurare uno schema e un set di dati

Per acquisire i dati in Adobe Experience Platform, devi innanzitutto definire quali dati desideri raccogliere. Tutti i dati inseriti in Adobe Experience Platform devono essere conformi a una struttura standard e denormalizzata affinché vengano riconosciuti e utilizzati dalle capacità e funzionalità a valle. Experience Data Model (XDM) è il framework standard che fornisce la struttura sotto forma di schemi.

Una volta definito uno schema, utilizza uno o più set di dati per memorizzare e gestire la raccolta di dati. Un set di dati è un costrutto di archiviazione e gestione per una raccolta di dati (in genere una tabella) che contiene uno schema (colonne) e dei campi (righe).

Tutti i dati inseriti in Adobe Experience Platform devono essere conformi a uno schema predefinito prima di poter essere memorizzati come set di dati.

### Configurare uno schema

Per questa introduzione, immagina di voler raccogliere alcuni dati relativi alla fidelizzazione, ad esempio ID di fidelizzazione, punti di fidelizzazione e stato di fidelizzazione.
Devi innanzitutto definire uno schema che modella questi dati.

Per configurare lo schema:

1. Nell’interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Schemas]** (Schemi) all’interno di [!UICONTROL DATA MANAGEMENT] (GESTIONE DATI).

1. Selezionare **[!UICONTROL Create schema]**.
.
1. Nel passaggio Selezionare una classe della procedura guidata Crea schema:

   1. Seleziona **[!UICONTROL Individual Profile]**.

      ![Crea una finestra dello schema con profilo individuale selezionato](./assets/create-pr-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Per modellare il _comportamento_ di un profilo (come nome di scena, premere il pulsante per aggiungere al carrello) viene utilizzato uno schema evento esperienza. Per modellare gli _attributi_ del profilo (come nome, e-mail, genere) viene utilizzato uno schema Individual Profile.

   1. Seleziona **[!UICONTROL Next]**.


1. In [!UICONTROL Name and review step] della procedura guidata [!UICONTROL Create schema]:

   1. Immetti un **[!UICONTROL Schema display name]** per lo schema e (facoltativamente) una **[!UICONTROL Description]**.

      ![Finestra Crea schema con i campi per denominare lo schema &#x200B;](./assets/create-pr-schema-wizard-step-2.png)

   1. Seleziona **[!UICONTROL Finish]**.

1. Nella scheda Struttura dello schema di esempio:

   1. Seleziona **[!UICONTROL + Add]** in [!UICONTROL Field groups].

      ![Finestra Crea schema che mostra il gruppo di campi Aggiungi](./assets/add-field-group-button.png)

      I gruppi di campi sono raccolte riutilizzabili di oggetti e attributi che consentono di estendere facilmente gli schemi.

   1. Nella finestra di dialogo [!UICONTROL Add fields groups] (Aggiungi gruppi di campi) seleziona il gruppo di campi **[!UICONTROL Loyalty Details]** dall’elenco.

      ![AEP Web SDK ExperienceEvent fieldgroup](./assets/loyalty-fieldgroup.png)

      Puoi selezionare il pulsante di anteprima per visualizzare un’anteprima dei campi che fanno parte del gruppo di campi.

      ![Anteprima AEP Web SDK ExperienceEvent fieldgroup](./assets/loyalty-fieldgroup-preview.png)

      Seleziona **[!UICONTROL Back]** (Indietro) per chiudere l’anteprima.

   1. Seleziona **[!UICONTROL Add field groups]** (Aggiungi gruppi di campi).

1. Seleziona **[!UICONTROL +]** accanto al nome dello schema nel pannello [!UICONTROL Structure] (Struttura).

   ![Pulsante per l’aggiunta di campi nello schema di esempio](./assets/example-loalty-schema-plus.png)

1. Nel pannello [!UICONTROL Field Properties] (Proprietà campo), inserisci `Identification` come nome, **[!UICONTROL Identification]** (Identificazione) come [!UICONTROL Display name] (Nome di visualizzazione), seleziona **[!UICONTROL Object]** (Oggetto) come [!UICONTROL Type] (Tipo) e seleziona **[!UICONTROL Profile Core v2]** come [!UICONTROL Field Group] (Gruppo di campo).

   ![Oggetto di identificazione](./assets/identifcation-loyalty-field.png)

   Questo oggetto di identificazione aggiunge funzionalità di identificazione allo schema. Nel tuo caso, immagina di voler identificare le informazioni sulla fidelizzazione utilizzando l’indirizzo e-mail nei tuoi dati batch.

   Seleziona **[!UICONTROL Apply]** (Applica) per aggiungere questo oggetto allo schema.

1. Seleziona il campo **[!UICONTROL email]** nell’oggetto di identificazione appena aggiunto e seleziona **[!UICONTROL Identity]** (identità) e **[!UICONTROL Email]** dall’elenco [!UICONTROL Identity namespace] (Spazio dei nomi dell’identità) nel pannello [!UICONTROL Field Properties] (Proprietà campo).

   ![Specificare l’e-mail come identità](./assets/specify-email-loyalty-id.png)

   Stai specificando l’indirizzo e-mail come identità che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili.

   Seleziona **[!UICONTROL Apply]** (Applica). Nell’attributo e-mail viene visualizzata l’icona di un’impronta digitale.

1. Seleziona il livello principale dello schema (con il nome dello schema), quindi seleziona il pulsante **[!UICONTROL Profile]** (Profilo).

   Viene richiesto di abilitare lo schema per il profilo. Una volta abilitato, quando i dati vengono inseriti in set di dati basati su questo schema, tali dati vengono uniti su Real-Time Customer Profile.

   Per ulteriori informazioni, consulta la sezione [Abilitare lo schema per l’utilizzo in Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it#profile).

   >[!IMPORTANT]
   >
   >    Una volta salvato uno schema abilitato per il profilo, non è più possibile disattivarlo per il profilo.

   ![Abilitare lo schema per il profilo](./assets/enable-for-profile.png)

1. Seleziona **[!UICONTROL Save]** (Salva) per salvare lo schema.

Hai creato uno schema minimo che modella i dati di fidelizzazione che puoi inserire in Adobe Experience Platform. Lo schema consente l’identificazione dei profili tramite l’indirizzo e-mail. Abilitando lo schema per il profilo, garantisci che i dati della tua origine di streaming vengano aggiunti a Real-Time Customer Profile.

Per ulteriori informazioni sull’aggiunta e la rimozione di gruppi di campi e singoli campi a uno schema, consulta la sezione [Creare e modificare schemi nell’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=it).

### Configurare un set di dati

Con lo schema, hai definito il modello dati. Ora devi definire il costrutto per memorizzare e gestire tali dati, che viene eseguito tramite set di dati.

Per configurare il set di dati:

1. Nell’interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Datasets]** (Set di dati) all’interno di [!UICONTROL DATA MANAGEMENT] (GESTIONE DATI).

2. Seleziona **[!UICONTROL Create dataset]** (Crea set di dati).

   ![Creare un set di dati](./assets/create-dataset.png)

3. Seleziona **[!UICONTROL Create dataset from schema]** (Crea set di dati da schema).

   ![Creare un set di dati da uno schema](./assets/create-dataset-from-schema.png)

4. Seleziona lo schema creato in precedenza e seleziona **[!UICONTROL Next]** (Avanti).

5. Assegna un nome al set di dati e (facoltativamente) fornisci una descrizione.

   ![Assegnare un nome al set di dati](./assets/name-your-datatest.png)

6. Seleziona **[!UICONTROL Finish]** (Fine).

7. Seleziona il pulsante **[!UICONTROL Profile]** (Profilo).

   Viene richiesto di abilitare il set di dati per il profilo. Una volta abilitato, il set di dati arricchisce i profili dei clienti in tempo reale con i relativi dati inseriti.

   >[!IMPORTANT]
   >
   >    Puoi abilitare un set di dati per il profilo solo quando lo schema a cui aderisce il set di dati è abilitato anche per il profilo.

   ![Abilitare lo schema per il profilo](./assets/loyalty-dataset-profile.png)

Per ulteriori informazioni su come visualizzare, visualizzare in anteprima, creare, eliminare un set di dati, consulta la sezione [Guida all’interfaccia utente dei set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it). E come abilitare un set di dati per Real-Time Customer Profile.


## Utilizzare un connettore di origine

A seconda della fonte da cui ricevi i dati di fidelizzazione, scegli il connettore di origine pertinente disponibile in Adobe Experience Platform.

Puoi acquisire dati da diverse origini. Di seguito sono riportate solo alcune delle numerose fonti disponibili:

- Applicazioni Adobe (i connettori di origine includono [Adobe Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/analytics), [Adobe Audience Manager](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/audience-manager) e altri)

- Archiviazione cloud (i connettori di origine includono [Amazon S3](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/cloud-storage/s3), [Azure Blob](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/cloud-storage/blob) e altri)

- Database (i connettori di origine includono [Snowflake](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/databases/snowflake), [Microsoft SQL Server](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/databases/sql-server) e altri)

Per configurare un connettore di origine:

1. In Adobe Experience Platform, seleziona **[!UICONTROL Sources]** da [!UICONTROL CONNECTIONS] nella barra a sinistra.

1. Selezionare il connettore di origine dall&#39;elenco dei connettori di origine disponibili.

   Ogni connettore segue un flusso di lavoro simile:

   1. **[!UICONTROL Authentication]** (Autenticazione): fornisci i dettagli di autenticazione per accedere all’origine dei dati.

   1. **[!UICONTROL Select data]** (Seleziona dati): seleziona i dati di origine da inserire.

   1. **[!UICONTROL Dataflow detail]**: fornire ulteriori dettagli sul flusso di dati, ad esempio il nome e il set di dati da utilizzare.

   1. **[!UICONTROL Mapping]** (Mappatura): puoi mappare i campi dei dati di origine in arrivo agli attributi dello schema associato al set di dati selezionato.

   1. **[!UICONTROL Scheduling]**: se disponibile, puoi pianificare l’acquisizione dei dati.

   1. **[!UICONTROL Review]** (Revisione): viene visualizzata una revisione della definizione del connettore di origine.

1. Ogni connettore fornisce una documentazione dettagliata. Per accedere a questa documentazione:

   1. Nel riquadro del connettore, seleziona **[!UICONTROL ...]** accanto a [!UICONTROL Set up] (Configura) o [!UICONTROL Add data] (Aggiungi dati).

      ![Visualizzare la documentazione](./assets/sourceconnector-documentation.png)

   1. Seleziona **[!UICONTROL View documentation]** (Visualizza documentazione).

Per informazioni sull&#39;utilizzo del connettore di origine di Adobe Analytics, vedere [Acquisire e utilizzare dati da Adobe Analytics](./analytics.md) tradizionale.

Per informazioni sull&#39;utilizzo del connettore di origine API HTTP, vedere [Acquisire e utilizzare dati in streaming](./streaming.md).

Consulta la sezione [Panoramica dei connettori di origine](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=it#terms-and-conditions) per una panoramica dei connettori di origine, compresi i collegamenti a ulteriori informazioni per ciascun connettore.


## Configurare una connessione

Per utilizzare i dati di Adobe Experience Platform in Customer Journey Analytics, crea una connessione che include i dati risultanti dalla configurazione dello schema, del set di dati e del flusso di lavoro.

Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti su questi set di dati, devi prima stabilire una connessione tra i set di dati in Adobe Experience Platform e Workspace.

Per creare la connessione:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, selezionare **[!UICONTROL Connections]**, facoltativamente da **[!UICONTROL Data management]**, nel menu principale.

1. Seleziona **[!UICONTROL Create new connection]** (Crea uova connessione).

1. Nella schermata **[!UICONTROL Untitled connection]** (Connessione senza titolo):

   1. Assegna un nome e una descrizione alla connessione in **[!UICONTROL Connection Settings]** (Impostazioni della connessione).

   1. Seleziona la sandbox corretta dall’elenco **[!UICONTROL Sandbox]** in **[!UICONTROL Data settings]** (Impostazioni dati) e seleziona il numero di eventi giornalieri dall’elenco **[!UICONTROL Average number of daily events]** (Numero medio di eventi giornalieri).

      ![Impostazioni della connessione](./assets/cja-connections-1.png)

   1. Seleziona **[!UICONTROL Add datasets]** (Aggiungi set di dati).

1. Nel passaggio **[!UICONTROL Select datasets]** (Seleziona set di dati) in **[!UICONTROL Add datasets]** (Aggiungi set di dati):

   1. Seleziona il set di dati creato in precedenza (`Example Loyalty Dataset` (Set di dati di fidelizzazione di esempio)) e qualsiasi altro set di dati da includere nella connessione.

      ![Aggiungere set di dati](./assets/cja-connections-2.png)

   1. Seleziona **[!UICONTROL Next]** (Avanti).

1. Nel passaggio **[!UICONTROL Datasets settings]** (Impostazioni set di dati) in **[!UICONTROL Add datasets]** (Aggiungi set di dati):

   Per ogni set di dati:

   1. Seleziona un [!UICONTROL Person ID] (ID persona) tra le identità disponibili definite negli schemi di set di dati in Adobe Experience Platform.

   1. Seleziona l’origine dati corretta dall’elenco [!UICONTROL Data source type] (Tipo di origine dati). Se specifichi **[!UICONTROL Other]** (Altro), aggiungi una descrizione per l’origine dati.

   1. Imposta **[!UICONTROL Import all new data]** (Importa tutti i nuovi dati) e **[!UICONTROL Dataset backfill existing data]** (Dati esistenti di backfill del set di dati) secondo le tue preferenze.

      ![Configurare i set di dati](./assets/cja-connections-3.png)

   1. Seleziona **[!UICONTROL Add datasets]** (Aggiungi set di dati).

   1. Seleziona **[!UICONTROL Save]** (Salva).

Dopo aver creato una [connessione](/help/connections/overview.md), è possibile eseguire varie attività di gestione, ad esempio [selezionare e combinare i set di dati](/help/connections/combined-dataset.md), [controllare lo stato dei set di dati di una connessione e lo stato dell&#39;acquisizione dei dati](/help/connections/manage-connections.md) e altro ancora.

## Configurare una visualizzazione dati

Una visualizzazione dati è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati da una connessione. Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace, e da quali colonne tali dimensioni e metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione alle attività di reporting in Analysis Workspace.

Per creare la visualizzazione dati:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, selezionare **[!UICONTROL Data views]**, facoltativamente da **[!UICONTROL Data management]**, nel menu principale.

2. Seleziona **[!UICONTROL Create new data view]** (Crea nuova visualizzazione dati).

3. Nel passaggio [!UICONTROL Configure] (Configura):

   Seleziona la connessione dall’elenco [!UICONTROL Connection] (Connessioni).

   Assegna un nome e (facoltativamente) una descrizione alla connessione.

   ![Configurare la visualizzazione dati](./assets/cja-dataview-1.png)

   Seleziona **[!UICONTROL Save and continue]** (Salva e continua).

4. Nel passaggio [!UICONTROL Components] (Componenti):

   Aggiungi qualsiasi campo dello schema e/o componente standard che desideri includere nelle caselle dei componenti [!UICONTROL METRICS] (METRICHE) o [!UICONTROL DIMENSIONS] (DIMENSIONI).

   ![Componenti della visualizzazione dati](./assets/cja-dataview-2.png)

   Seleziona **[!UICONTROL Save and continue]** (Salva e continua).

5. Nel passaggio [!UICONTROL Settings] (Impostazioni):

   ![Impostazioni della visualizzazione dati](./assets/cja-dataview-3.png)

   Lascia le impostazioni così come sono e seleziona **[!UICONTROL Save and finish]** (Salva e fine).

Consulta [Panoramica delle visualizzazioni dati](../data-views/data-views.md) per ulteriori informazioni su come creare e modificare una visualizzazione dati, quali componenti sono disponibili per l&#39;utilizzo nella visualizzazione dati e come utilizzare le impostazioni di segmenti e sessioni.


## Configurare un progetto

Analysis Workspace è uno strumento basato su browser flessibile che consente di creare rapidamente le analisi e condividere i dati rilevati sulla base dei tuoi dati. Usa i progetti Workspace per combinare componenti dati, tabelle e visualizzazioni per sviluppare analisi da condividere con altri nella tua organizzazione.

Per creare il progetto:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, seleziona **[!UICONTROL Projects]** nel menu principale.

2. Seleziona **[!UICONTROL Projects]** (Progetti) nel pannello di navigazione a sinistra.

3. Seleziona **[!UICONTROL Create project]** (Crea progetto).

   ![Progetto Workspace](./assets/cja-projects-1.png)

   Seleziona **[!UICONTROL Blank project]** (Progetto vuoto).

   ![Workspace - Progetto vuoto](./assets/cja-projects-2.png)

4. Seleziona la visualizzazione dati dall’elenco.

   ![Visualizzazione Select Data (Seleziona dati) di Workspace](./assets/cja-projects-3.png).

5. Per creare il primo rapporto, inizia a trascinare dimensioni e metriche su [!UICONTROL Freeform table] in [!UICONTROL Panel]. Ad esempio, trascina `Program Points Balance` e `Page View` come metriche e `email` come dimensione per ottenere una panoramica rapida dei profili che hanno visitato il tuo sito Web e che fanno parte del programma di fidelizzazione per la raccolta di punti di fidelizzazione.

   ![Workspace - Primo rapporto](./assets/cja-projects-5.png)

Per ulteriori informazioni su come creare progetti e generare analisi utilizzando componenti, visualizzazioni e pannelli, consulta la sezione [Panoramica di Analysis Workspace](../analysis-workspace/home.md).

>[!SUCCESS]
>
>Hai completato tutti i passaggi. Partendo dalla definizione dei dati di fidelizzazione da raccogliere (schema) e di dove memorizzarli (set di dati) in Adobe Experience Platform, hai configurato il connettore di origine appropriato che ti fornisse i dati di fidelizzazione. Hai definito una connessione in Customer Journey Analytics per utilizzare i dati di fidelizzazione inseriti e altri dati. La definizione della visualizzazione dati ti consente di specificare la dimensione e le metriche da utilizzare e infine hai creato il tuo primo progetto per la visualizzazione e l’analisi dei dati.
