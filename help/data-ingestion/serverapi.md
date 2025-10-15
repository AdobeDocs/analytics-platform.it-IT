---
title: Acquisire dati tramite l’API server di Adobe Experience Platform Edge Network
description: Spiegare come acquisire i dati in Customer Journey Analytics tramite l’API server di Adobe Experience Platform Edge Network e Edge Network
solution: Customer Journey Analytics
feature: Basics
exl-id: 6bfb7254-5bb7-45c6-86a2-0651a0d222fa
role: Admin
source-git-commit: bc2c959497230d7672d43d5cd409ca62d4627d6a
workflow-type: tm+mt
source-wordcount: '2180'
ht-degree: 59%

---

# Acquisire dati tramite API server di Edge Network

Questa guida rapida spiega come acquisire i dati di tracciamento da dispositivi come dispositivi IoT, set-top box, console di gioco e applicazioni desktop direttamente in Adobe Experience Platform utilizzando l’API server di Adobe Experience Platform Edge Network e Edge Network. Quindi utilizza tali dati in Customer Journey Analytics.

A questo scopo, devi:

- **Configurare uno schema e un set di dati** in Adobe Experience Platform per definire il modello (schema) dei dati da raccogliere e dove raccogliere effettivamente i dati (set di dati).

- **Configurare un flusso di dati** per configurare la rete Edge di Adobe Experience Platform in modo che i dati raccolti vengano indirizzati al set di dati configurato in Adobe Experience Platform.

- **Utilizza l&#39;API server** per inviare dati direttamente dall&#39;applicazione o dal gioco in esecuzione su un desktop, una console di gioco, un dispositivo IoT o un set-top box allo stream di dati.

- **Distribuire e convalidare**. Crea un ambiente in cui puoi eseguire iterazioni sullo sviluppo; una volta convalidato tutto, pubblicalo live nell’ambiente di produzione.

- **Impostare una connessione** in Customer Journey Analytics. Questa connessione deve includere almeno il set di dati di Adobe Experience Platform.

- **Configurare una visualizzazione dati** in Customer Journey Analytics per definire le metriche e le dimensioni da utilizzare in Analysis Workspace.

- **Configurare un progetto** in Customer Journey Analytics per generare rapporti e visualizzazioni.

>[!NOTE]
>
>Questa guida rapida è una guida semplificata su come acquisire in Adobe Experience Platform i dati raccolti da un’applicazione o un gioco in esecuzione su un dispositivo IoT, un set-top box, una console di gioco o un desktop e utilizzarli in Customer Journey Analytics. Ti consigliamo vivamente di esaminare le informazioni aggiuntive quando vi fai riferimento.


## Configurare uno schema e un set di dati

Per acquisire i dati in Adobe Experience Platform, devi innanzitutto definire quali dati desideri raccogliere. Tutti i dati inseriti in Adobe Experience Platform devono essere conformi a una struttura standard e denormalizzata affinché vengano riconosciuti e utilizzati dalle capacità e funzionalità a valle. Experience Data Model (XDM) è il framework standard che fornisce una struttura sotto forma di schemi.

Una volta definito uno schema, utilizza uno o più set di dati per memorizzare e gestire la raccolta di dati. Un set di dati è un costrutto di archiviazione e gestione per una raccolta di dati (in genere una tabella) che contiene uno schema (colonne) e dei campi (righe).

Tutti i dati inseriti in Adobe Experience Platform devono essere conformi a uno schema predefinito prima di poter essere memorizzati come set di dati.

### Configurare uno schema

Desideri tenere traccia di alcuni dati minimi dai profili che giocano al tuo gioco su una console, ad esempio identificazione, punteggi, avanzamento e altre informazioni.
Devi innanzitutto definire uno schema che modella questi dati.

Per configurare lo schema:

1. Nell’interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Schemas]** (Schemi) all’interno di [!UICONTROL DATA MANAGEMENT] (GESTIONE DATI).

1. Selezionare **[!UICONTROL Create schema]**.
.
1. Nel passaggio Selezionare una classe della procedura guidata Crea schema:

   1. Seleziona **[!UICONTROL Experience Event]**.

      ![Creare uno schema](./assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Per modellare il _comportamento_ di un profilo (come nome di scena, premere il pulsante per aggiungere al carrello) viene utilizzato uno schema evento esperienza. Per modellare gli _attributi_ del profilo (come nome, e-mail, genere) viene utilizzato uno schema Individual Profile.

   1. Seleziona **[!UICONTROL Next]**.


1. In [!UICONTROL Name and review step] della procedura guidata [!UICONTROL Create schema]:

   1. Immetti un **[!UICONTROL Schema display name]** per lo schema e (facoltativamente) una **[!UICONTROL Description]**.

      ![Assegnare un nome allo schema](./assets/create-ee-schema-wizard-step-2.png)

   1. Seleziona **[!UICONTROL Finish]**.

1. Nella scheda Struttura dello schema di esempio:

   1. Seleziona **[!UICONTROL + Add]** (Aggiungi) in [!UICONTROL Field groups] (Gruppi di campi).

      ![Aggiungere un gruppo di campi](./assets/add-field-group-button.png)

      I gruppi di campi sono raccolte riutilizzabili di oggetti e attributi che consentono di estendere facilmente lo schema.

   1. Nella finestra di dialogo [!UICONTROL Add fields groups], seleziona il gruppo di campi **[!UICONTROL Blinding Light]** dall&#39;elenco. Questo gruppo di campi è stato creato per tenere traccia dei progressi degli utenti durante l&#39;esecuzione di un gioco fittizio intitolato Blinding Light su una console.

      ![Gruppo di campi Luce accecante](assets/schema-fieldgroup-blindinglight.png)

      Puoi selezionare il pulsante di anteprima per visualizzare un’anteprima dei campi che fanno parte del gruppo di campi, ad esempio `scores > afterMatch`.

      ![Anteprima gruppo di campi Luce accecante](assets/schema-fieldgroup-blindinglight-preview.png)

      Seleziona **[!UICONTROL Back]** (Indietro) per chiudere l’anteprima.

   1. Seleziona **[!UICONTROL Add field groups]** (Aggiungi gruppi di campi).

1. Seleziona **[!UICONTROL +]** accanto al nome dello schema.

   ![Pulsante per l’aggiunta di campi nello schema di esempio](./assets/example-gamingschema-plus.png)

1. Nel pannello [!UICONTROL Field Properties], immetti `identification` come [!UICONTROL Field name], **[!UICONTROL Identification]** come [!UICONTROL Display name], seleziona **[!UICONTROL Object]** come [!UICONTROL Type] e seleziona **[!UICONTROL ExperienceEvent Core v2.1]** come [!UICONTROL Field Group].

   >[!NOTE]
   >
   >Se tale gruppo di campi non è disponibile, cercane un altro contenente campi di identità. Oppure [crea un nuovo gruppo di campi](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=it) e [aggiungi nuovi campi di identità](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html?lang=it#define-a-identity-field) (come `ecid`, `crmId` e altri di cui hai bisogno) al gruppo di campi e seleziona il nuovo gruppo di campi.

   ![Oggetto di identificazione](./assets/identification-field-gaming.png)

   L’oggetto di identificazione aggiunge funzionalità di individuazione dello schema. Nel tuo caso, vuoi identificare i profili che giocano al tuo gioco utilizzando l’ID Experience Cloud e l’indirizzo e-mail che utilizzano per accedere alla loro console di gioco. Sono disponibili molti altri attributi per tenere traccia dell’identificazione della persona.

   Seleziona **[!UICONTROL Apply]** (Applica) per aggiungere questo oggetto allo schema.

1. Seleziona il campo **[!UICONTROL ecid]** nell’oggetto di identificazione appena aggiunto e seleziona **[!UICONTROL Identity]** (Identità) e **[!UICONTROL Primary Identity]** (Identità principale) e **[!UICONTROL ECID]** dall’elenco [!UICONTROL Identity namespace] (Spazio dei nomi dell’identità) nel pannello di destra.

   ![Specificare ECID come identità](./assets/specify-identity-gaming.png)

   Stai specificando l’Experience Cloud Identity come identità principale che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili con lo stesso ECID.

   Seleziona **[!UICONTROL Apply]** (Applica). Nell’attributo ecid viene visualizzata l’icona di un’impronta digitale.

1. Seleziona il campo **[!UICONTROL email]** nell’oggetto di identificazione appena aggiunto e seleziona **[!UICONTROL Identity]** (identità) e **[!UICONTROL Email]** dall’elenco [!UICONTROL Identity namespace] (Spazio dei nomi dell’identità) nel pannello [!UICONTROL Field Properties] (Proprietà campo).

   ![Specificare l’e-mail come identità](./assets/specify-email-identity-gaming.png)

   Stai specificando l’indirizzo e-mail come un’altra identità che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili.

   Seleziona **[!UICONTROL Apply]** (Applica). Nell’attributo e-mail viene visualizzata l’icona di un’impronta digitale.

   Seleziona **[!UICONTROL Save]** (Salva).

1. Seleziona l’elemento principale dello schema che visualizza il nome dello schema, quindi seleziona il pulsante **[!UICONTROL Profile]** (Profilo).

   Viene richiesto di abilitare lo schema per il profilo. Una volta abilitato, quando i dati vengono inseriti in set di dati basati su questo schema, tali dati vengono uniti su Real-Time Customer Profile.

   Per ulteriori informazioni, consulta la sezione [Abilitare lo schema per l’utilizzo in Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it#profile).

   >[!IMPORTANT]
   >
   >    Una volta salvato uno schema abilitato per il profilo, non è più possibile disattivarlo per il profilo.

   ![Abilitare lo schema per il profilo](./assets/enable-for-profile.png)

1. Seleziona **[!UICONTROL Save]** (Salva) per salvare lo schema.

Hai creato uno schema minimo che modella i dati che puoi acquisire dal gioco. Lo schema consente di identificare i profili utilizzando Experience Cloud Identity e l’indirizzo e-mail. Attivando lo schema per il profilo, puoi garantire che i dati acquisiti dal gioco da console vengano aggiunti al Profilo cliente in tempo reale.

Oltre ai dati sul comportamento, puoi anche acquisire i dati degli attributi del profilo dalla console (ad esempio i dettagli dei profili connessi alla console).

Per acquisire i dati del profilo:

- Crea uno schema basato sulla classe di profilo individuale XDM.

- Aggiungi il gruppo di campi Profile Core v2 allo schema.

- Aggiungi un oggetto di identificazione basato sul gruppo di campi Profile Core v2.

- Definisci l’ID Experience Cloud come identificatore principale e l’e-mail come identificatore.

- Abilitare lo schema per il profilo

Per ulteriori informazioni sull’aggiunta e la rimozione di gruppi di campi e singoli campi a uno schema, consulta la sezione [Creare e modificare schemi nell’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=it).

### Configurare un set di dati

Con lo schema, hai definito il modello dati. Ora devi definire il costrutto per memorizzare e gestire tali dati utilizzando i set di dati.

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

   ![Abilitare lo schema per il profilo](./assets/aepwebsdk-dataset-profile.png)

Per ulteriori informazioni su come visualizzare, visualizzare in anteprima, creare, eliminare un set di dati, consulta la sezione [Guida all’interfaccia utente dei set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it). E come abilitare un set di dati per Real-Time Customer Profile.

## Configurare un flusso di dati

Un flusso di dati rappresenta la configurazione lato server durante l’implementazione degli SDK Adobe Experience Platform Web e Mobile e dell’API server di Adobe Experience Platform Edge Network. Durante la raccolta dei dati con gli SDK di Adobe Experience Platform e le API server di Edge Network, i dati vengono inviati a Adobe Experience Platform Edge Network. È il flusso di dati che determina a quali servizi vengono inoltrati i dati.

Nella configurazione, desideri che i dati raccolti dal gioco vengano inviati al set di dati in Adobe Experience Platform.

Per impostare il flusso di dati:

1. Nell’interfaccia utente di Adobe Experience Platform, seleziona **[!UICONTROL Datastreams]** (Flussi di dati) da [!UICONTROL DATA COLLECTION] (RACCOLTE DATI) nella barra a sinistra.

2. Seleziona **[!UICONTROL New Datastream]** (Nuovo flusso di dati).

3. Assegna un nome e una descrizione al tuo flusso di dati. Seleziona lo schema dall’elenco [!UICONTROL Event Schema] (Schema eventi).

   ![Nuovo flusso di dati](./assets/new-datastream.png)

4. Seleziona **[!UICONTROL Save]** (Salva).

5. Seleziona **[!UICONTROL Add Service]** (Aggiungi servizio).

6. Nella schermata [!UICONTROL Add Service screen] (Aggiungi servizio):

   1. Seleziona **[!UICONTROL Adobe Experience Platform]** dall’elenco [!UICONTROL Service] (Servizio).

   2. Assicurati di aver selezionato **[!UICONTROL Enabled]** (Abilitato).

   3. Seleziona il set di dati dall’elenco [!UICONTROL Event Dataset] (Set di dati evento).

      ![Servizio AEP del flusso di dati](./assets/datastream-aep-service.png)

   4. Abbandona le altre impostazioni e seleziona **[!UICONTROL Save]** per salvare il flusso di dati.

Il flusso di dati è ora configurato per inoltrare i dati raccolti dal gioco al set di dati in Adobe Experience Platform.

Per ulteriori informazioni su come configurare un flusso di dati e come gestire i dati sensibili consulta la sezione [Panoramica dei flussi di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=it).

## Utilizzare l’API server di Edge Network

Durante lo sviluppo del gioco, puoi aggiungere chiamate pertinenti all’API server di Adobe Experience Platform Edge Network, se necessario.

Ad esempio, per aggiornare il punteggio del lettore, puoi utilizzare:

```
curl -X POST "https://server.adobedc.net/ee/v2/interact?dataStreamId={DATASTREAM_ID}"
-H "Authorization: Bearer {TOKEN}"
-H "x-gw-ims-org-id: {ORG_ID}"
-H "x-api-key: {API_KEY}"
-H "Content-Type: application/json"
-d '{
   "event": {
      "xdm": {
         "identityMap": {
            "Email_LC_SHA256": [
               {
                  "id": "0c7e6a405862e402eb76a70f8a26fc732d07c32931e9fae9ab1582911d2e8a3b",
                  "primary": true
               }
            ]
         },
         "eventType": "game.scoreUpdate",
         "{sandbox}": {
            "scores": {
               "afterMatch": 132391",
            }
         },
         "timestamp": "2021-08-09T14:09:20.859Z"
      }
   }
}'
```

Nell&#39;esempio di richiesta POST, `{DATASTREAM_ID}` punta all&#39;identificatore dello stream di dati di esempio configurato in precedenza. `{sandbox}` è il nome univoco della sandbox che identifica il percorso del gruppo di campi Luce accecante personalizzato.

Per ulteriori informazioni sull&#39;utilizzo dell&#39;API server di Edge Network, vedere [Raccolta dati interattiva](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=it) e [Raccolta dati non interattiva](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html).

## Configurare una connessione

Per utilizzare i dati di Adobe Experience Platform in Customer Journey Analytics, crea una connessione che include i dati risultanti dalla configurazione dello schema, del set di dati e del flusso di lavoro.

Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti su questi set di dati, devi prima stabilire una connessione tra i set di dati in Adobe Experience Platform e Workspace.

Per creare la connessione:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, selezionare **[!UICONTROL Connections]**, facoltativamente da **[!UICONTROL Data management]**, nel menu principale.

2. Seleziona **[!UICONTROL Create new connection]** (Crea uova connessione).

3. Nella schermata [!UICONTROL Untitled connection] (Connessione senza titolo):

   Assegna un nome e una descrizione alla connessione in [!UICONTROL Connection Settings] (Impostazioni della connessione).

   Seleziona la sandbox corretta dall’elenco [!UICONTROL Sandbox] in [!UICONTROL Data settings] (Impostazioni dati) e seleziona il numero di eventi giornalieri dall’elenco [!UICONTROL Average number of daily events] (Numero medio di eventi giornalieri).

   ![Impostazioni della connessione](./assets/cja-connections-1.png)

   Seleziona **[!UICONTROL Add datasets]** (Aggiungi set di dati).

   Nel passaggio [!UICONTROL Select datasets] (Seleziona set di dati) in [!UICONTROL Add datasets] (Aggiungi set di dati):

   - Seleziona i set di dati creati in precedenza e/o altri set di dati rilevanti che desideri includere nella connessione

   - Seleziona **[!UICONTROL Next]** (Aggiungi set di dati).

   Nel passaggio [!UICONTROL Datasets settings] (Impostazioni set di dati) in [!UICONTROL Add datasets] (Aggiungi set di dati):

   - Per ogni set di dati:

      - Seleziona un [!UICONTROL Person ID] (ID persona) tra le identità disponibili definite negli schemi di set di dati in Adobe Experience Platform.

      - Seleziona l’origine dati corretta dall’elenco [!UICONTROL Data source type] (Tipo di origine dati). Se specifichi **[!UICONTROL Other]** (Altro), aggiungi una descrizione per l’origine dati.

      - Imposta **[!UICONTROL Import all new data]** (Importa tutti i nuovi dati) e **[!UICONTROL Dataset backfill existing data]** (Dati esistenti di backfill del set di dati) secondo le tue preferenze.

   - Seleziona **[!UICONTROL Add datasets]** (Aggiungi set di dati).

   Seleziona **[!UICONTROL Save]** (Salva).

Per ulteriori informazioni su come creare e gestire una connessione e come selezionare e combinare i set di dati, consulta la sezione [Panoramica delle connessioni](../connections/overview.md).

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

   Seleziona **[!UICONTROL Save and continue]** (Crea nuova visualizzazione dati).

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

5. Per creare il primo rapporto, inizia a trascinare dimensioni e metriche su [!UICONTROL Freeform table] in [!UICONTROL Panel].

Per ulteriori informazioni su come creare progetti e generare analisi utilizzando componenti, visualizzazioni e pannelli, consulta la sezione [Panoramica di Analysis Workspace](../analysis-workspace/home.md).

>[!SUCCESS]
>
>Hai completato tutti i passaggi. A partire dalla definizione dei dati da raccogliere (schema) e della posizione in cui memorizzarli (set di dati) in Adobe Experience Platform. Hai configurato un flusso di dati in Edge Network per garantire che i dati possano essere inoltrati a tale set di dati. Poi hai utilizzato l’API server di Edge Network per inviare tali dati allo stream di dati. Hai definito una connessione in Customer Journey Analytics per utilizzare i tuoi dati di gioco e altri dati. La definizione della visualizzazione dati ti consente di specificare la dimensione e le metriche da utilizzare; infine, hai creato il tuo primo progetto per visualizzare e analizzare i dati del gioco.
