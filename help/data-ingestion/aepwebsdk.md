---
title: Acquisire dati tramite Adobe Experience Platform Web SDK e la rete Edge
description: Spiegare come inserire dati in Customer Percorsi Analytics tramite Adobe Experience Platform Web SDK e Edge Network
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: f910f8e810c5c5d6f4d43aff2b609d8bf6c131ca
workflow-type: tm+mt
source-wordcount: '3277'
ht-degree: 11%

---


# Acquisire dati tramite Adobe Experience Platform Web SDK e la rete Edge

Questa guida rapida spiega come inserire i dati di tracciamento dei siti web direttamente in Adobe Experience Platform utilizzando Adobe Experience Platform Web SDK e Edge Network e quindi utilizzarli in Customer Journey Analytics.

A questo scopo, devi:

- **Configurare uno schema e un set di dati** in Adobe Experience Platform per definire il modello (schema) dei dati da raccogliere e dove raccogliere effettivamente i dati (set di dati).

- **Configurare un datastream** per configurare Adobe Experience Platform Edge Network in modo che i dati raccolti vengano indirizzati al set di dati configurato in Adobe Experience Platform.

- **Usa tag** per configurare facilmente regole ed elementi dati rispetto ai dati presenti nel livello dati sul sito web e assicurarsi che i dati vengano inviati al datastream configurato su Adobe Experience Platform Edge Network.

- **Distribuisci e convalida**. Disporre di un ambiente in cui puoi eseguire iterazioni sullo sviluppo dei tag e, una volta convalidato tutto, pubblicarlo in diretta nell’ambiente di produzione.

- **Impostare una connessione** in Customer Journey Analytics. Questa connessione deve includere almeno il set di dati Adobe Experience Platform.

- **Configurare una visualizzazione dati** in Customer Journey Analytics per definire le metriche e le dimensioni da utilizzare in Analysis Workspace.

- **Configurare un progetto** in Customer Journey Analytics per generare rapporti e visualizzazioni.

>[!NOTE]
>
>Questa è una guida semplificata su come acquisire i dati raccolti dal sito in Adobe Experience Platform e utilizzarli nel Customer Journey Analytics.  Si raccomanda vivamente di studiare le informazioni aggiuntive quando si fa riferimento a tali informazioni.


## Configurare uno schema e un set di dati

Per acquisire i dati in Adobe Experience Platform, devi innanzitutto definire quali dati desideri raccogliere. Tutti i dati acquisiti in Adobe Experience Platform devono essere conformi a una struttura standard e denormalizzata per essere riconosciuti e sfruttati dalle funzionalità e funzionalità a valle. Experience Data Model (XDM) è il framework standard che fornisce questa struttura sotto forma di schemi.

Una volta definito uno schema, utilizzerai uno o più set di dati per memorizzare e gestire la raccolta di dati. Un set di dati è un costrutto di archiviazione e gestione per una raccolta di dati, in genere una tabella, che contiene uno schema (colonne) e dei campi (righe).

Tutti i dati acquisiti in Adobe Experience Platform devono essere conformi a uno schema predefinito prima di poter essere mantenuti come set di dati.

### Configurazione di uno schema

Desideri tenere traccia di alcuni dati minimi provenienti dai profili che visitano il tuo sito web, ad esempio nome della pagina, identificazione, ecc.
A questo scopo, devi innanzitutto definire uno schema che modelli questi dati.

Per impostare lo schema:

1. Nell’interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Schemas]** entro [!UICONTROL DATA MANAGEMENT].

2. Seleziona **[!UICONTROL Create schema]**. Seleziona **[!UICONTROL XDM ExperienceEvent]** dall’elenco delle opzioni.

   ![Creare uno schema](./assets/create-ee-schema.png)

   >[!INFO]
   >
   >    Viene utilizzato uno schema Evento esperienza per modellare _comportamento_ di un profilo (come visualizzazione pagina, aggiungi al carrello). Per modellare il profilo viene utilizzato uno schema di profilo individuale _attributes_ (come nome, e-mail, genere).


3. In [!UICONTROL Untitled schema] schermo:

   1. Immetti un nome visualizzato per lo schema e (facoltativo) una descrizione.

      ![Denomina lo schema](./assets/name-schema.png)

   2. Seleziona **[!UICONTROL + Add]** in [!UICONTROL Field groups].

      ![Aggiungi gruppo di campi](./assets/add-field-group-button.png)

      I gruppi di campi sono raccolte riutilizzabili di oggetti e attributi che consentono di estendere facilmente lo schema.

   3. In [!UICONTROL Add fields groups] seleziona la finestra di dialogo **[!UICONTROL AEP Web SDK ExperienceEvent]** gruppo di campi dall&#39;elenco.

      ![AEP Web SDK ExperienceEvent gruppo di campi](./assets/select-aepwebsdk-experienceevent.png)

      È possibile selezionare il pulsante anteprima per visualizzare un’anteprima dei campi che fanno parte del gruppo di campi, ad esempio `web > webPageDetails > name`.

      ![Anteprima gruppo di campi ExperienceEvent dell&#39;SDK per web AEP](./assets/aepwebsdk-experiencevent-preview.png)

      Seleziona **[!UICONTROL Back]** per chiudere l&#39;anteprima.

   4. Seleziona **[!UICONTROL Add field groups]**.

4. Seleziona **[!UICONTROL +]** accanto al nome dello schema nel [!UICONTROL Structure] pannello.

   ![Esempio di pulsante Aggiungi campo schema](./assets/example-schema-plus.png)

5. In [!UICONTROL Field Properties] pannello, immetti `Identification` come nome, **[!UICONTROL Identification]** come [!UICONTROL Display name], seleziona **[!UICONTROL Object]** come [!UICONTROL Type] e seleziona **[!UICONTROL ExperienceEvent Core v2.1]** come [!UICONTROL Field Group].

   ![Oggetto di identificazione](./assets/identification-field.png)

   Questo aggiungerà funzionalità di identificazione allo schema. Nel tuo caso, vuoi identificare i profili che visitano il tuo sito utilizzando l’ID Experience Cloud e l’indirizzo e-mail. Sono disponibili molti altri attributi per monitorare l’identificazione del visitatore (ad esempio, ID cliente, ID fedeltà, ecc.).

   Seleziona **[!UICONTROL Apply]** per aggiungere questo oggetto allo schema.

6. Seleziona la **[!UICONTROL ecid]** nell&#39;oggetto di identificazione appena aggiunto e selezionare **[!UICONTROL Identity]** e **[!UICONTROL Primary Identity]** e **[!UICONTROL ECID]** dal [!UICONTROL Identity namespace] nel pannello di destra.

   ![ECID specificato come identità](./assets/specify-identity.png)

   Stai specificando l’identità Experience Cloud come identità principale che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili con lo stesso ECID.

   Seleziona **[!UICONTROL Apply]**. Nell’attributo ecid viene visualizzata l’icona relativa all’impronta digitale.

7. Seleziona la **[!UICONTROL email]** nell&#39;oggetto di identificazione appena aggiunto e selezionare **[!UICONTROL Identity]** e **[!UICONTROL Email]** dal [!UICONTROL Identity namespace] nell&#39;elenco [!UICONTROL Field Properties] pannello.

   ![E-mail specifica come identità](./assets/specify-email-identity.png)

   Stai specificando l’indirizzo e-mail come un’altra identità che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili.

   Seleziona **[!UICONTROL Apply]**. Nell’attributo e-mail verrà visualizzata l’icona relativa all’impronta digitale.

   Seleziona **[!UICONTROL Save]**.

8. Seleziona l’elemento principale dello schema che visualizza il nome dello schema, quindi seleziona la **[!UICONTROL Profile]** interruttore.

   Verrà richiesto di abilitare lo schema per il profilo. Una volta abilitati, quando i dati vengono acquisiti in set di dati basati su questo schema, tali dati verranno uniti nel Profilo del cliente in tempo reale.

   Vedi [Abilitare lo schema per l’utilizzo nel profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en#profile) per ulteriori informazioni.

   >[!IMPORTANT]
   >
   >    Una volta salvato uno schema abilitato per il profilo, non è più possibile disattivarlo per il profilo.

   ![Abilita schema per profilo](./assets/enable-for-profile.png)

9. Seleziona **[!UICONTROL Save]** per salvare lo schema.

Hai creato uno schema minimo che modella i dati che puoi acquisire dal tuo sito web. Lo schema consente di identificare i profili utilizzando l’identità Experience Cloud e l’indirizzo e-mail. Attivando lo schema per il profilo, assicurati che i dati acquisiti dal tuo sito web vengano aggiunti al Profilo del cliente in tempo reale.

Accanto ai dati sul comportamento, puoi anche acquisire i dati degli attributi del profilo dal sito (ad esempio i dettagli dei profili che si abbonano a una newsletter).

Per acquisire questi dati del profilo, effettua le seguenti operazioni:

- Crea uno schema basato sulla classe Profilo individuale XDM.

- Aggiungi il gruppo di campi Profilo Core v2 allo schema.

- Aggiungi un oggetto di identificazione basato sul gruppo di campi Profilo Core v2 .

- Definisci ecid come identificatore principale e l’e-mail come identificatore.

- Abilitare lo schema per il profilo

Vedi [Creare e modificare schemi nell’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html) per ulteriori informazioni sull&#39;aggiunta e la rimozione di gruppi di campi e singoli campi in uno schema.

### Configurare un set di dati

Con lo schema hai definito il modello dati. Ora devi definire il costrutto per memorizzare e gestire tali dati. Questo avviene tramite i set di dati.

Per impostare il set di dati:

1. Nell’interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Datasets]** entro [!UICONTROL DATA MANAGEMENT].

2. Seleziona **[!UICONTROL Create dataset]**.

   ![Creare un set di dati](./assets/create-dataset.png)

3. Seleziona **[!UICONTROL Create dataset from schema]**.

   ![Creare un set di dati dallo schema](./assets/create-dataset-from-schema.png)

4. Seleziona lo schema creato in precedenza e seleziona **[!UICONTROL Next]**.

5. Denomina il set di dati e (facoltativo) fornisci una descrizione.

   ![Set di dati nome](./assets/name-your-datatest.png)

6. Seleziona **[!UICONTROL Finish]**.

7. Seleziona la **[!UICONTROL Profile]** interruttore.

   Viene richiesto di abilitare il set di dati per il profilo. Una volta attivato, il set di dati arricchirà i profili dei clienti in tempo reale con i relativi dati acquisiti.

   >[!IMPORTANT]
   >
   >    Puoi abilitare un set di dati per il profilo solo quando lo schema a cui aderisce il set di dati è abilitato anche per il profilo.

   ![Abilita schema per profilo](./assets/aepwebsdk-dataset-profile.png)

Vedi [Guida all’interfaccia utente dei set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it) per ulteriori informazioni su come visualizzare, visualizzare in anteprima, creare, eliminare un set di dati. E come abilitare un set di dati per il profilo cliente in tempo reale.

## Configurare un datastream

Un datastream rappresenta la configurazione lato server quando si implementano gli SDK per web e dispositivi mobili di Adobe Experience Platform. Durante la raccolta di dati con gli SDK Adobe Experience Platform, i dati vengono inviati a Adobe Experience Platform Edge Network. È il datastream che determina a quali servizi vengono inoltrati i dati.

Nella configurazione, desideri che i dati raccolti dal sito web vengano inviati al set di dati in Adobe Experience Platform.

Per impostare il datastream:

1. Nell’interfaccia utente di Adobe Experience Platform, seleziona **[!UICONTROL Datastreams]** da [!UICONTROL DATA COLLECTION] nella barra a sinistra.

2. Seleziona **[!UICONTROL New Datastream]**.

3. Denomina e descrivi il tuo datastream. Seleziona lo schema dal [!UICONTROL Event Schema] elenco.

   ![Nuovo Datastream](./assets/new-datastream.png)

4. Seleziona **[!UICONTROL Save]**.

5. Seleziona **[!UICONTROL Add Service]**.

6. In [!UICONTROL Add Service screen]:

   1. Seleziona **[!UICONTROL Adobe Experience Platform]** dall&#39;elenco.[!UICONTROL Service]

   2. Assicurati **[!UICONTROL Enabled]** è selezionato.

   3. Seleziona il set di dati dal [!UICONTROL Event Dataset] elenco.

      ![Servizio AEP Datastream](./assets/datastream-aep-service.png)

   4. Lascia le altre impostazioni e seleziona **[!UICONTROL Save]** per salvare il datastream.

Il datastream è ora configurato per inoltrare i dati raccolti dal sito web al set di dati in Adobe Experience Platform.

Vedi [Panoramica dei Datastreams](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=it) per ulteriori informazioni su come configurare un datastream e come gestire i dati sensibili.



## Usa tag

Utilizza la funzione Tag in Adobe Experience Platform per implementare il codice sul tuo sito per raccogliere effettivamente i dati. Questa soluzione per la gestione dei tag consente di implementare il codice e altri requisiti di assegnazione tag. I tag offrono un’integrazione diretta con Adobe Experience Platform tramite l’estensione Adobe Experience Platform Web SDK.

### Creare il tag

1. Nell’interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Tags]** entro [!UICONTROL DATA COLLECTION].

2. Seleziona **[!UICONTROL New Property]**.

   Assegna un nome al tag e seleziona **[!UICONTROL Web]** e immetti un nome di dominio. Seleziona **[!UICONTROL Save]** per continuare.

   ![Creare una proprietà](./assets/create-property.png)

### Configurare il tag

Dopo aver creato il tag , devi configurarlo con le estensioni corrette e configurare elementi dati e regole in base a come desideri tenere traccia del sito e inviare dati a Adobe Experience Platform.

Seleziona il tag appena creato dall’elenco di [!UICONTROL Tag Properties] per aprirlo.


#### **Estensioni**

Aggiungi l’estensione Adobe Platform Web SDK al tag per assicurarti di poter inviare dati a Adobe Experience Platform (tramite il datastream).

Per creare e configurare l&#39;estensione Adobe Experience Platform Web SDK:

1. Seleziona **[!UICONTROL Extensions]** nella barra a sinistra.

2. Seleziona **[!UICONTROL Catalog]** nella barra superiore.

3. Cerca o scorri fino all’estensione Adobe Experience Platform Web SDK e seleziona **[!UICONTROL Install]** per installarlo.

   <img src="./assets/aepwebsdk-extension.png" width="35%"/>

4. Seleziona la sandbox e il datastream creato in precedenza per il tuo [!UICONTROL Production Environment] e (facoltativo) [!UICONTROL Staging Environment] e [!UICONTROL Development Environment].

   ![Configurazione dell&#39;estensione AEP Web SDK](./assets/aepwebsk-extension-datastreams.png)

   Seleziona **[!UICONTROL Save]**.

Vedi [Configurare l’estensione Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) per ulteriori informazioni.

Vuoi anche impostare l&#39;estensione del servizio Experience Cloud ID per poter facilmente usare il servizio Experience Cloud ID. Il servizio Experience Cloud ID identifica i visitatori in tutte le soluzioni Adobe Experience Cloud.

Per creare e configurare l&#39;estensione del servizio Experience Cloud ID:

1. Seleziona **[!UICONTROL Extensions]** nella barra a sinistra.

2. Seleziona **[!UICONTROL Catalog]** nella barra superiore.

3. Cerca o scorri fino all’estensione del servizio Experience Cloud ID e seleziona **[!UICONTROL Install]** per installarlo.

   <img src="./assets/ecid-extension.png" width="35%"/>

4. Lascia tutte le configurazioni come predefinite.

5. Seleziona **[!UICONTROL Save]**.

#### **Elementi dati**

Gli elementi dati sono i blocchi costitutivi per il dizionario dati (o mappa dati). Utilizza elementi dati per raccogliere, organizzare e distribuire dati in tutta la tecnologia marketing e pubblicitaria. Puoi impostare elementi dati nel tag che leggono dal livello dati e possono essere utilizzati per inviare dati a Adobe Experience Platform.

Esistono diversi tipi di elementi dati. In primo luogo, configurerai un elemento dati per acquisire il nome della pagina che i visitatori visualizzano sul tuo sito.

Per definire un elemento dati nome pagina:

1. Seleziona **[!UICONTROL Data Elements]** nella barra a sinistra.

2. Seleziona **[!UICONTROL Add Data Element]**.

3. In [!UICONTROL Create Data Element] finestra di dialogo:

   - Denomina l&#39;elemento dati, ad esempio `Page Name`.

   - Seleziona **[!UICONTROL Core]** dall&#39;elenco.[!UICONTROL Extension]

   - Seleziona **[!UICONTROL Page Info]** dall&#39;elenco.[!UICONTROL Data Element Type]

   - Seleziona **[!UICONTROL Title]** dall&#39;elenco.[!UICONTROL Attribute]

      ![Crea elemento data utilizzando le informazioni di pagina](./assets/create-dataelement-1.png)

      In alternativa, puoi usare il valore da una variabile del livello dati, ad esempio `pageName` e [!UICONTROL JavaScript Variable] tipo di elemento dati per definire l’elemento dati.

      ![Creare un elemento dati utilizzando una variabile Javascript](./assets/create-dataelement-2.png)

   - Seleziona **[!UICONTROL Save]**.

Ora desideri impostare un elemento dati che faccia riferimento all’ID Experience Cloud fornito automaticamente dall’SDK per web Adobe Experience Platform e disponibile tramite l’estensione del servizio ID Experience Cloud.

Per definire un elemento dati ECID:

1. Seleziona **[!UICONTROL Data Elements]** nella barra a sinistra.

2. Seleziona **[!UICONTROL Add Data Element]**.

3. In [!UICONTROL Create Data Element] finestra di dialogo:

   - Denomina l&#39;elemento dati, ad esempio `ECID`.

   - Seleziona **[!UICONTROL Experience Cloud ID Service]** dall&#39;elenco.[!UICONTROL Extension]

   - Seleziona **[!UICONTROL ECID]** dall&#39;elenco.[!UICONTROL Data Element Type]

      ![Elemento dati ECID](./assets/ecid-dataelement.png)

   - Seleziona **[!UICONTROL Save]**.

Infine, ora desideri mappare uno qualsiasi degli elementi dati specifici allo schema definito in precedenza. È necessario definire un altro elemento dati che fornisca una rappresentazione dello schema XDM.

Per definire un elemento dati oggetto XDM:

1. Seleziona **[!UICONTROL Data Elements]** nella barra a sinistra.

2. Seleziona **[!UICONTROL Add Data Element]**.

3. In [!UICONTROL Create Data Element] finestra di dialogo:

   - Denomina l&#39;elemento dati, ad esempio `XDM - Page View`.

   - Seleziona **[!UICONTROL Adobe Experience Platform Web SDK]** dall&#39;elenco.[!UICONTROL Extension]

   - Seleziona **[!UICONTROL XDM Object]** dall&#39;elenco.[!UICONTROL Data Element Type]

   - Seleziona la sandbox dal [!UICONTROL Sandbox] elenco.

   - Seleziona lo schema dal [!UICONTROL Schema] elenco.

   - Mappa la `identification > core > ecid` all’elemento dati ECID, definito nello schema. Seleziona l’icona del cursore per scegliere facilmente l’elemento dati ECID dall’elenco degli elementi dati.

      ![Scegli elemento dati ECID](./assets/pick-ecid-dataelement.png)

      ![Mappa elemento dati ECID](./assets/map-ecid.png)


   - Mappa la `web > webPageDetails > name` Attributo, definito nello schema, all’elemento dati Nome pagina.

      ![Elemento dati Nome pagina mappa](./assets/map-pagename.png)

   - Seleziona **[!UICONTROL Save]**.


#### **Regole**

I tag in Adobe Experience Platform seguono un sistema basato su regole. Cercano le interazione degli utenti e i relativi dati. Quando i criteri descritti nelle tue regole vengono soddisfatti, la regola attiva l&#39;estensione, lo script o il codice lato client identificato. Puoi utilizzare le regole per inviare dati (come un oggetto XDM) ad Adobe Experience Platform utilizzando l’estensione Adobe Experience Platform Web SDK.

Per definire una regola:

1. Seleziona **[!UICONTROL Rules]** nella barra a sinistra.

2. Seleziona **[!UICONTROL Create New Rule]**.

3. In [!UICONTROL Create Rule] finestra di dialogo:

   - Denomina la regola, ad esempio `Page View`.

   - Seleziona **[!UICONTROL + Add]** sotto [!UICONTROL Events].

   - In [!UICONTROL Event Configuration] finestra di dialogo:

      - Seleziona **[!UICONTROL Core]** dall&#39;elenco.[!UICONTROL Extension]

      - Seleziona **[!UICONTROL Window Loaded]** dall&#39;elenco.[!UICONTROL Event Type]

         ![Regola - Configurazione evento](./assets/event-windowloaded-pageview.png)

      - Seleziona **[!UICONTROL Keep Changes]**.
   - Seleziona **[!UICONTROL + Add]** sotto [!UICONTROL Actions].

   - In [!UICONTROL Action Configuration] finestra di dialogo:

      - Seleziona **[!UICONTROL Adobe Experience Platform Web SDK]** dall&#39;elenco.[!UICONTROL Extension]

      - Seleziona **[!UICONTROL Send Event]** dall&#39;elenco.[!UICONTROL Action Type]

      - Seleziona **[!UICONTROL web.webpagedetails.pageViews]** dall&#39;elenco.[!UICONTROL Type]

      - Seleziona l’icona del cursore accanto a  [!UICONTROL XDM data] e seleziona **[!UICONTROL XDM - Page View]** dall’elenco degli elementi dati.

         ![Regola - Configurazione azione](./assets/action-pageview-xdm.png)

      - Seleziona **[!UICONTROL Keep Changes]**.
   - La regola dovrebbe avere un aspetto simile a:

      ![Crea regola](assets/rule-pageview.png)

   - Seleziona **[!UICONTROL Save]**.





Questo è solo un esempio di definizione di una regola che invia dati XDM, contenenti valori da altri elementi di dati, a Adobe Experience Platform.

Puoi utilizzare le regole in diversi modi nel tag per manipolare le variabili (utilizzando gli elementi dati).

Vedi [Regole](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html) per ulteriori informazioni.

### Creare e pubblicare il tag

Dopo aver definito elementi dati e regole, devi generare e pubblicare il tag. Quando crei una build della libreria, devi assegnarla a un ambiente. Le estensioni, le regole e gli elementi dati della build vengono quindi compilati e inseriti nell’ambiente assegnato. Ogni ambiente fornisce un codice di incorporamento univoco che consente di integrare la build assegnata nel sito.

Per generare e pubblicare il tag:

1. Seleziona **[!UICONTROL Publishing Flow]** dalla barra a sinistra.

2. Seleziona **[!UICONTROL Select a working library]**, seguita da **[!UICONTROL Add Library…]**.

3. In [!UICONTROL Create Libray] finestra di dialogo:

   - Assegna un nome alla libreria.

   - Seleziona **[!UICONTROL Development (development)]** dall&#39;elenco.[!UICONTROL Environment]

   - Seleziona **[!UICONTROL + Add All Changed Resources]**.

      ![Pubblica - Crea libreria](./assets/create-library-aep.png)

   - Seleziona **[!UICONTROL Save & Build to Development]**.

   Questo consente di salvare e creare il tag per l’ambiente di sviluppo. Un punto verde indica la corretta compilazione del tag nell’ambiente di sviluppo.

4. È possibile selezionare **[!UICONTROL ...]** per ricreare la libreria o spostarla in un ambiente di staging o produzione.

   ![Pubblica - Crea libreria](./assets/build-library.png)

I tag di Adobe Experience Platform supportano flussi di lavoro di pubblicazione semplici e complessi che dovrebbero adattarsi alla distribuzione di Adobe Experience Platform Web SDK.

Vedi [Panoramica sulla pubblicazione](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) per ulteriori informazioni.


### Recupera il codice del tag

Infine devi installare il tag sul sito web che desideri monitorare. Questo implica il posizionamento del codice nel tag di intestazione del modello del sito web.

Per ottenere il codice che fa riferimento al tag:

1. Seleziona **[!UICONTROL Environments]** nella barra a sinistra.

2. Dall’elenco degli ambienti, seleziona il pulsante di installazione (casella) corretto.

   In [!UICONTROL Web Install Instructions] seleziona il pulsante copia accanto al codice script che dovrebbe essere simile al seguente:

   ```javascript
   <script src="https://assets.adobedtm.com/2a518741ab24/806645a0b9bb/launch-716db315b4e2-development.min.js" async></script>
   ```

   ![Ambiente](./assets/environment.png)

3. Seleziona **[!UICONTROL Close]**.

Invece del codice per l&#39;ambiente di sviluppo, potresti aver selezionato un altro ambiente (staging, produzione) in base al punto in cui stai distribuendo l&#39;SDK Web di Adobe Experience Platform.

Vedi [Ambienti](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?) per ulteriori informazioni.

## Distribuisci e convalida

Ora puoi distribuire il codice nella versione di sviluppo del tuo sito web all’interno di `<head>` tag . Una volta distribuito, il sito web inizierà a raccogliere dati in Adobe Experience Platform.

Convalida l’implementazione, correggilo laddove necessario e una volta corretto, distribuiscila nel tuo ambiente di staging e produzione utilizzando la funzione di flusso di lavoro di pubblicazione dei tag.

## Configurazione di una connessione

Per utilizzare i dati Adobe Experience Platform nel Customer Journey Analytics, è necessario creare una connessione che includa i dati risultanti dalla configurazione dello schema, del set di dati e del flusso di lavoro.

Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti su questi set di dati, è innanzitutto necessario stabilire una connessione tra i set di dati in Adobe Experience Platform e Workspace.

Per creare la connessione:

1. Nell’interfaccia utente del Customer Journey Analytics, seleziona **[!UICONTROL Connections]** nella navigazione superiore.

2. Seleziona **[!UICONTROL Create new connection]**.

3. In [!UICONTROL Untitled connection] schermo:

   Assegnare un nome e descrivere la connessione in [!UICONTROL Connection Settings].

   Seleziona la sandbox corretta dal [!UICONTROL Sandbox] elenco in [!UICONTROL Data settings] e seleziona il numero di eventi giornalieri dal [!UICONTROL Avergage number of daily events] elenco.

   ![Impostazioni connessione](./assets/cja-connections-1.png)

   Seleziona **[!UICONTROL Add datsets]**.

   In [!UICONTROL Select datasets] passo [!UICONTROL Add datasets]:

   - Seleziona il set di dati creato in precedenza (`Example dataset`) e qualsiasi altro set di dati da includere nella connessione.

      ![Aggiungi set di dati](./assets/cja-connections-2b.png)

   - Seleziona **[!UICONTROL Next]**.
   In [!UICONTROL Datasets settings] passo [!UICONTROL Add datasets]:

   - Per ogni set di dati:

      - Seleziona una [!UICONTROL Person ID] dalle identità disponibili definite negli schemi di set di dati in Adobe Experience Platform.

      - Seleziona l’origine dati corretta dal [!UICONTROL Data source type] elenco. Se si specifica **[!UICONTROL Other]** quindi aggiungi una descrizione per l’origine dati.

      - Imposta **[!UICONTROL Import all new data]** e **[!UICONTROL Dataset backfill existing data]** secondo le tue preferenze.

      ![Configurare i set di dati](./assets/cja-connections-3.png)

   - Seleziona **[!UICONTROL Add datasets]**.
   Seleziona **[!UICONTROL Save]**.

Vedi [Panoramica delle connessioni](../connections/overview.md) per ulteriori informazioni su come creare e gestire una connessione e come selezionare e combinare i set di dati.

## Configurare una visualizzazione dati

Una visualizzazione dati è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati da una connessione. Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace, e da quali colonne tali dimensioni e metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione alle attività di reporting in Analysis Workspace.

Per creare la visualizzazione dati:

1. Nell’interfaccia utente del Customer Journey Analytics, seleziona **[!UICONTROL Data views]** nella navigazione superiore.

2. Seleziona **[!UICONTROL Create new data view]**.

3. In [!UICONTROL Configure] passo:

   Seleziona la connessione dal [!UICONTROL Connection] elenco.

   Nome e (facoltativamente) descrizione della connessione.

   ![Configurazione della visualizzazione dati](./assets/cja-dataview-1.png)

   Seleziona **[!UICONTROL Save and continue]**.

4. In [!UICONTROL Components] passo:

   Aggiungi qualsiasi campo dello schema e/o componente standard da includere nel [!UICONTROL METRICS] o [!UICONTROL DIMENSIONS] caselle dei componenti.

   ![Componenti della visualizzazione dati](./assets/cja-dataview-2.png)

   Seleziona **[!UICONTROL Save and continue]**.

5. In [!UICONTROL Settings] passo:

   Impostazioni della ![visualizzazione dati](./assets/cja-dataview-3.png)

   Lascia le impostazioni così come sono e seleziona **[!UICONTROL Save and finish]**.

Vedi [Panoramica delle visualizzazioni dati](../data-views/data-views.md) per ulteriori informazioni su come creare e modificare una visualizzazione dati, quali componenti sono disponibili per la visualizzazione dati e come utilizzare le impostazioni di filtro e sessioni.


## Configurare un progetto

Analysis Workspace è uno strumento browser flessibile che ti consente di creare rapidamente analisi e condividere informazioni basate sui tuoi dati. Puoi utilizzare i progetti Workspace per combinare componenti dati, tabelle e visualizzazioni per creare le tue analisi e condividerle con chiunque all’interno della tua organizzazione.

Per creare il progetto:

1. Nell’interfaccia utente del Customer Journey Analytics, seleziona **[!UICONTROL Projects]** nella navigazione superiore.

2. Seleziona **[!UICONTROL Projects]** nella navigazione a sinistra.

3. Seleziona **[!UICONTROL Create project]**.

   ![Progetto Workspace](./assets/cja-projects-1.png)

   Seleziona **[!UICONTROL Blank project]**.

   ![Workspace - Progetto vuoto](./assets/cja-projects-2.png)

4. Seleziona la visualizzazione dati dall’elenco.

   ![Visualizzazione dati Seleziona area di lavoro](./assets/cja-projects-3.png).

5. Inizia a trascinare dimensioni e metriche sul [!UICONTROL Freeform table] in [!UICONTROL Panel] per creare il primo rapporto. Ad esempio, trascina `Program Points Balance` e `Page View` come metriche e `email` come dimensione per ottenere una rapida panoramica dei profili che hanno visitato il tuo sito web e che fanno anche parte del programma fedeltà che raccoglie punti fedeltà.

   ![Area di lavoro - Primo rapporto](./assets/cja-projects-5.png)

Vedi [Panoramica di Analysis Workspace](../analysis-workspace/home.md) per ulteriori informazioni su come creare progetti e generare analisi utilizzando componenti, visualizzazioni e pannelli.

>[!SUCCESS]
>
>Hai completato tutti i passaggi. A partire dalla definizione dei dati da raccogliere (schema) e di dove memorizzarli (set di dati) in Adobe Experience Platform, hai configurato un datastream su Edge Network per garantire che i dati possano essere inoltrati a tale set di dati. Quindi hai definito e implementato il tag contenente le estensioni (Adobe Experience Platform Web SDK, Experience Cloud ID Service), gli elementi dati e le regole per acquisire i dati dal tuo sito web e inviarli al tuo datastream. Hai definito una connessione in Customer Journey Analytics per utilizzare i dati di tracciamento del tuo sito web e altri dati. La definizione della visualizzazione dati ti consente di specificare la dimensione e le metriche da utilizzare e infine hai creato il tuo primo progetto per la visualizzazione e l’analisi dei dati.
