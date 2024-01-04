---
title: Inserire dati tramite Adobe Experience Platform Web SDK
description: Spiega come inserire dati in Customer Journey Analytics tramite Adobe Experience Platform Web SDK e la rete Edge
solution: Customer Journey Analytics
feature: Basics
exl-id: 0b595e9e-0dcf-4c70-ac6d-5a2322824328
role: Admin
source-git-commit: 59da35ddbdf06da354af4ab469a357caae41bd26
workflow-type: tm+mt
source-wordcount: '3279'
ht-degree: 83%

---

# Inserire dati tramite Adobe Experience Platform Web SDK

Questa guida introduttiva spiega come inserire i dati di tracciamento dei siti Web direttamente in Adobe Experience Platform utilizzando l’SDK per Web di Adobe Experience Platform e la rete Edge e quindi utilizzarli in Customer Journey Analytics.

A questo scopo, è necessario:

- **Configurare uno schema e un set di dati** in Adobe Experience Platform per definire il modello (schema) dei dati da raccogliere e dove raccogliere effettivamente i dati (set di dati).

- **Configurare un flusso di dati** per configurare la rete Edge di Adobe Experience Platform in modo che i dati raccolti vengano indirizzati al set di dati configurato in Adobe Experience Platform.

- **Usare i tag** per configurare facilmente regole ed elementi dati rispetto ai dati presenti nel livello dati sul sito Web. Quindi assicurati che i dati siano inviati al flusso di dati configurato sulla rete Edge di Adobe Experience Platform.

- **Distribuire e convalidare**. Disporre di un ambiente in cui puoi eseguire iterazioni sullo sviluppo dei tag e, una volta convalidato tutto, pubblicarlo in diretta nell’ambiente di produzione.

- **Impostare una connessione** in Customer Journey Analytics. Questa connessione deve includere almeno il set di dati di Adobe Experience Platform.

- **Configurare una visualizzazione dati** in Customer Journey Analytics per definire le metriche e le dimensioni da utilizzare in Analysis Workspace.

- **Configurare un progetto** in Customer Journey Analytics per generare rapporti e visualizzazioni.

>[!NOTE]
>
> Questa guida rapida è una guida semplificata su come acquisire in Adobe Experience Platform i dati raccolti dal sito e utilizzarli in Customer Journey Analytics. Ti consigliamo vivamente di esaminare le informazioni aggiuntive quando vi fai riferimento.


## Configurare uno schema e un set di dati

Per acquisire i dati in Adobe Experience Platform, devi innanzitutto definire quali dati desideri raccogliere. Tutti i dati inseriti in Adobe Experience Platform devono essere conformi a una struttura standard e denormalizzata affinché vengano riconosciuti e utilizzati dalle capacità e funzionalità a valle. Experience Data Model (XDM) è il framework standard che fornisce questa struttura sotto forma di schemi.

Una volta definito uno schema, utilizza uno o più set di dati per memorizzare e gestire la raccolta di dati. Un set di dati è un costrutto di archiviazione e gestione per una raccolta di dati (in genere una tabella) che contiene uno schema (colonne) e dei campi (righe).

Tutti i dati inseriti in Adobe Experience Platform devono essere conformi a uno schema predefinito prima di poter essere memorizzati come set di dati.

### Configurare uno schema

Immagina di voler tenere traccia di alcuni dati minimi provenienti dai profili che visitano il tuo sito Web, ad esempio il nome della pagina o l’identificazione.
Devi innanzitutto definire uno schema che modella questi dati.

Per configurare lo schema:

1. Nell’interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Schemas]** (Schemi) all’interno di [!UICONTROL DATA MANAGEMENT] (GESTIONE DATI).

1. Seleziona **[!UICONTROL Create schema]**. .
1. Nel passaggio Selezionare una classe della procedura guidata Crea schema:

   1. Seleziona **[!UICONTROL Experience Event]**.

      ![Creare uno schema che evidenzi l’evento esperienza](./assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Per modellare l’evento viene utilizzato uno schema Experience Event _comportamento_ di un profilo (come nome della scena, pulsante per aggiungerlo al carrello). Per modellare gli _attributi_ del profilo (come nome, e-mail, genere) viene utilizzato uno schema Individual Profile.

   1. Seleziona **[!UICONTROL Next]**.


1. In [!UICONTROL Name and review step] del [!UICONTROL Create schema] procedura guidata:

   1. Immetti un **[!UICONTROL Schema display name]** per lo schema e (facoltativo) un **[!UICONTROL Description]**.

      ![Finestra Crea schema con il nome dei campi schema](./assets/create-ee-schema-wizard-step-2.png)

   1. Seleziona **[!UICONTROL Finish]**.

1. Nella scheda Struttura dello schema di esempio:

   1. Seleziona **[!UICONTROL + Add]** (Aggiungi) in [!UICONTROL Field groups] (Gruppi di campi).

      ![Aggiungere un gruppo di campi](./assets/add-field-group-button.png)

      I gruppi di campi sono raccolte riutilizzabili di oggetti e attributi che consentono di estendere facilmente lo schema.

   1. Nella finestra di dialogo [!UICONTROL Add fields groups] (Aggiungi gruppi di campi) seleziona il gruppo di campi **[!UICONTROL AEP Web SDK ExperienceEvent]** dall’elenco.

      ![AEP Web SDK ExperienceEvent fieldgroup](./assets/select-aepwebsdk-experienceevent.png)

      Puoi selezionare il pulsante di anteprima per visualizzare un’anteprima dei campi che fanno parte del gruppo di campi, ad esempio `web > webPageDetails > name`.

      ![Anteprima AEP Web SDK ExperienceEvent fieldgroup](./assets/aepwebsdk-experiencevent-preview.png)

      Seleziona **[!UICONTROL Back]** (Indietro) per chiudere l’anteprima.

   1. Seleziona **[!UICONTROL Add field groups]** (Aggiungi gruppi di campi).

1. Seleziona **[!UICONTROL +]** accanto al nome dello schema nel pannello [!UICONTROL Structure] (Struttura).

   ![Pulsante per l’aggiunta di campi nello schema di esempio](./assets/example-schema-plus.png)

1. Nel pannello [!UICONTROL Field Properties] (Proprietà campo), inserisci `Identification` come nome, **[!UICONTROL Identification]** (Identificazione) come [!UICONTROL Display name] (Nome di visualizzazione), seleziona **[!UICONTROL Object]** (Oggetto) come [!UICONTROL Type] (Tipo) e seleziona **[!UICONTROL ExperienceEvent Core v2.1]** come [!UICONTROL Field Group] (Gruppo di campo).

   >[!NOTE]
   >
   >Se tale gruppo di campi non è disponibile, cercare un altro gruppo di campi contenente campi di identità. Oppure [crea un nuovo gruppo di campi](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=en) e [aggiungi nuovi campi di identità](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html?lang=en#define-a-identity-field) (like `ecid`, `crmId`e altri elementi necessari) al gruppo di campi e selezionarlo.

   ![Oggetto di identificazione](./assets/identification-field.png)

   L’oggetto di identificazione aggiunge funzionalità di identificazione allo schema. Nel tuo caso, immagina di voler identificare i profili che visitano il tuo sito utilizzando l’Experience Cloud ID e l’indirizzo e-mail. Sono disponibili molti altri attributi per tenere traccia dell’identificazione della persona (ad esempio ID cliente, ID fedeltà).

   Seleziona **[!UICONTROL Apply]** (Applica) per aggiungere questo oggetto allo schema.

1. Seleziona il campo **[!UICONTROL ecid]** nell’oggetto di identificazione appena aggiunto e seleziona **[!UICONTROL Identity]** (Identità) e **[!UICONTROL Primary Identity]** (Identità principale) e **[!UICONTROL ECID]** dall’elenco [!UICONTROL Identity namespace] (Spazio dei nomi dell’identità) nel pannello di destra.

   ![Specificare ECID come identità](./assets/specify-identity.png)

   Stai specificando l’Experience Cloud Identity come identità principale che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili con lo stesso ECID.

   Seleziona **[!UICONTROL Apply]** (Applica). Nell’attributo ecid viene visualizzata l’icona di un’impronta digitale.

1. Seleziona il campo **[!UICONTROL email]** nell’oggetto di identificazione appena aggiunto e seleziona **[!UICONTROL Identity]** (identità) e **[!UICONTROL Email]** dall’elenco [!UICONTROL Identity namespace] (Spazio dei nomi dell’identità) nel pannello [!UICONTROL Field Properties] (Proprietà campo).

   ![Specificare l’e-mail come identità](./assets/specify-email-identity.png)

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

Hai creato uno schema minimo che modella i dati che puoi acquisire dal tuo sito Web. Lo schema consente di identificare i profili utilizzando Experience Cloud Identity e l’indirizzo e-mail. Attivando lo schema per il profilo, garantisci che i dati acquisiti dal tuo sito Web vengano aggiunti a Real-Time Customer Profile.

Accanto ai dati sul comportamento, puoi anche acquisire i dati degli attributi del profilo dal sito (ad esempio i dettagli dei profili che si abbonano a una newsletter).

Per acquisire questi dati del profilo:

- Crea uno schema basato sulla classe di profilo individuale XDM.

- Aggiungi il gruppo di campi Profile Core v2 allo schema.

- Aggiungi un oggetto di identificazione basato sul gruppo di campi Profile Core v2.

- Definisci l’ID Experience Cloud come identificatore principale e invia un’e-mail come identificatore.

- Abilitare lo schema per il profilo

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

   Viene richiesto di abilitare il set di dati per il profilo. Una volta attivato, il set di dati arricchisce i profili dei clienti in tempo reale con i relativi dati inseriti.

   >[!IMPORTANT]
   >
   >    Puoi abilitare un set di dati per il profilo solo quando lo schema a cui aderisce il set di dati è abilitato anche per il profilo.

   ![Abilitare lo schema per il profilo](./assets/aepwebsdk-dataset-profile.png)

Per ulteriori informazioni su come visualizzare, visualizzare in anteprima, creare, eliminare un set di dati, consulta la sezione [Guida all’interfaccia utente dei set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it). E come abilitare un set di dati per Real-Time Customer Profile.

## Configurare un flusso di dati

Un flusso di dati rappresenta la configurazione lato server quando si implementano gli SDK per Web e dispositivi mobili di Adobe Experience Platform. Durante la raccolta di dati con gli SDK di Adobe Experience Platform, i dati vengono inviati alla rete Edge di Adobe Experience Platform. È lo stream di dati che determina a quali servizi vengono inoltrati i dati.

Nella configurazione, desideri che i dati raccolti dal sito Web vengano inviati al set di dati in Adobe Experience Platform.

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

Il flusso di dati è ora configurato per inoltrare i dati raccolti dal sito Web al set di dati in Adobe Experience Platform.

Per ulteriori informazioni su come configurare un flusso di dati e come gestire i dati sensibili consulta la sezione [Panoramica dei flussi di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=en).



## Usare i tag

Per implementare il codice sul sito per raccogliere effettivamente i dati, utilizza la funzione Tag in Adobe Experience Platform. Questa soluzione per la gestione dei tag consente di implementare il codice e altri requisiti di assegnazione dei tag. I tag offrono un’integrazione diretta con Adobe Experience Platform tramite l’estensione dell’SDK per Web di Adobe Experience Platform.

### Creare il tag

1. Nell’interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Tags]** (Tag) all’interno di [!UICONTROL DATA COLLECTION] (GESTIONE DATI).

2. Seleziona **[!UICONTROL New Property]** (Nuova proprietà).

   Assegna un nome al tag, seleziona **[!UICONTROL Web]** e immetti un nome di dominio. Seleziona **[!UICONTROL Save]** (Salva) per continuare.

   ![Creare una proprietà](./assets/create-property.png)

### Configurare il tag

Dopo aver creato il tag, devi configurarlo con le estensioni corrette e configurare elementi dati e regole in base a come desideri tenere traccia del sito e inviare dati a Adobe Experience Platform.

Seleziona il tag appena creato dall’elenco [!UICONTROL Tag Properties] (Proprietà tag) per aprirlo.


#### **Estensioni**

Per garantire che tu possa inviare dati a Adobe Experience Platform (tramite lo stream di dati), aggiungi l’estensione Adobe Platform Web SDK al tag.

Per creare e configurare l’estensione Adobe Experience Platform Web SDK:

1. Seleziona **[!UICONTROL Extensions]** (Estensioni) nella barra a sinistra.

2. Seleziona **[!UICONTROL Catalog]** (Catalogo) nella barra superiore.

3. Cerca o scorri fino all’estensione Adobe Experience Platform Web SDK e seleziona **[!UICONTROL Install]** (Installa) per installarlo.

   <img src="./assets/aepwebsdk-extension.png" width="35%"/>

4. Seleziona la sandbox e il flusso di dati creato in precedenza per il tuo [!UICONTROL Production Environment] (Ambiente di produzione) e (facoltativamente) [!UICONTROL Staging Environment] (Ambiente di gestione temporanea) e [!UICONTROL Development Environment] (Ambiente di sviluppo).

   ![Configurazione dell’estensione AEP Web SDK](./assets/aepwebsk-extension-datastreams.png)

   Seleziona **[!UICONTROL Save]** (Salva).

Per ulteriori informazioni, consulta la sezione [Configurare l’estensione Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html).

Immagina di voler impostare l’estensione Experience Cloud ID Service per poter utilizzare facilmente l’ID Experience Cloud. Il servizio ID Experience Cloud identifica le persone in tutte le soluzioni Adobe Experience Cloud.

Per creare e configurare l’estensione Experience Cloud ID Service:

1. Seleziona **[!UICONTROL Extensions]** (Estensioni) nella barra a sinistra.

2. Seleziona **[!UICONTROL Catalog]** (Catalogo) nella barra superiore.

3. Cerca o scorri fino all’estensione Experience Cloud ID Service e seleziona **[!UICONTROL Install]** (Installa) per installarlo.

   <img src="./assets/ecid-extension.png" width="35%"/>

4. Lascia tutte le configurazioni come predefinite.

5. Seleziona **[!UICONTROL Save]** (Salva).

#### **Elementi dati**

Gli elementi dati sono i blocchi costitutivi per il dizionario dati (o mappa dati). Utilizza elementi dati per raccogliere, organizzare e distribuire dati in tutta la tecnologia marketing e pubblicitaria. Puoi impostare elementi dati nel tag che leggono dal livello dati e possono essere utilizzati per inviare dati ad Adobe Experience Platform.

Esistono diversi tipi di elementi dati. Devi innanzitutto impostare un elemento dati per acquisire il nome della pagina che le persone visualizzano sul tuo sito.

Per definire un elemento dati nome pagina:

1. Seleziona **[!UICONTROL Data Elements]** (Elementi dati) nella barra a sinistra.

2. Seleziona **[!UICONTROL Add Data Element]** (Aggiungi elemento dati).

3. Nella finestra di dialogo [!UICONTROL Create Data Element] (Crea elemento dati):

   - Assegna un nome all’elemento dati, ad esempio `Page Name` (Nome pagina).

   - Seleziona **[!UICONTROL Core]** dall’elenco [!UICONTROL Extension] (Estensioni).

   - Seleziona **[!UICONTROL Page Info]** (Info pagina) dall’elenco [!UICONTROL Data Element Type] (Tipo di elemento dati).

   - Seleziona **[!UICONTROL Title]** (Titolo) dall’elenco [!UICONTROL Attribute] (Attributo).

     ![Creare un elemento dati utilizzando le informazioni della pagina](./assets/create-dataelement-1.png)

     In alternativa, puoi usare il valore da una variabile del livello dati, ad esempio `pageName` e il tipo di elemento dati [!UICONTROL JavaScript Variable] (Variabile JavaScript) per definire l’elemento dati.

     ![Creare un elemento dati utilizzando una variabile Javascript](./assets/create-dataelement-2.png)

   - Seleziona **[!UICONTROL Save]** (Salva).

Ora immagina di voler impostare un elemento dati che faccia riferimento all’ID Experience Cloud fornito automaticamente dall’SDK per Web Adobe Experience Platform e disponibile tramite l’estensione Experience Cloud ID Service.

Per definire un elemento dati ECID:

1. Seleziona **[!UICONTROL Data Elements]** (Elementi dati) nella barra a sinistra.

2. Seleziona **[!UICONTROL Add Data Element]** (Aggiungi elemento dati).

3. Nella finestra di dialogo [!UICONTROL Create Data Element] (Crea elemento dati):

   - Assegna un nome all’elemento dati, ad esempio `ECID` (Nome pagina).

   - Seleziona **[!UICONTROL Experience Cloud ID Service]** dall’elenco [!UICONTROL Extension] (Estensioni).

   - Seleziona **[!UICONTROL ECID]** dall’elenco [!UICONTROL Data Element Type] (Tipo di elemento dati).

     ![Elemento dati ECID](./assets/ecid-dataelement.png)

   - Seleziona **[!UICONTROL Save]** (Salva).

Infine, ora immagina di voler mappare uno qualsiasi degli elementi dati specifici allo schema definito in precedenza. Puoi definire un altro elemento dati che fornisce una rappresentazione dello schema XDM.

Per definire un elemento dati oggetto XDM:

1. Seleziona **[!UICONTROL Data Elements]** (Elementi dati) nella barra a sinistra.

2. Seleziona **[!UICONTROL Add Data Element]** (Aggiungi elemento dati).

3. Nella finestra di dialogo [!UICONTROL Create Data Element] (Crea elemento dati):

   - Assegna un nome all’elemento dati, ad esempio `XDM - Page View` (Nome pagina).

   - Seleziona **[!UICONTROL Adobe Experience Platform Web SDK]** dall’elenco [!UICONTROL Extension] (Estensioni).

   - Seleziona **[!UICONTROL XDM Object]** (Oggetto XDM) dall’elenco [!UICONTROL Data Element Type] (Tipo di elemento dati).

   - Seleziona la sandbox dall’elenco [!UICONTROL Sandbox].

   - Seleziona lo schema dall’elenco [!UICONTROL Schema].

   - Mappa l’attributo `identification > core > ecid` all’elemento dati ECID, definito nello schema. Seleziona l’icona del cilindro per scegliere facilmente l’elemento dati ECID dall’elenco degli elementi dati.

     ![Scegli l’elemento dati ECID](./assets/pick-ecid-dataelement.png)

     ![Mappa l’elemento dati ECID](./assets/map-ecid.png)


   - Mappa l’attributo `web > webPageDetails > name` all’elemento dati Page Name (Nome pagina), definito nello schema.

     ![Mappa l’elementi dati Page Name (Nome pagina)](./assets/map-pagename.png)

   - Seleziona **[!UICONTROL Save]** (Salva).


#### **Regole**

I tag in Adobe Experience Platform seguono un sistema basato su regole. Cercano le interazione degli utenti e i relativi dati. Quando i criteri descritti nelle tue regole vengono soddisfatti, la regola attiva l’estensione, lo script o il codice lato client identificato. Puoi utilizzare le regole per inviare dati (come un oggetto XDM) in Adobe Experience Platform utilizzando l’estensione Adobe Experience Platform Web SDK.

Per definire una regola:

1. Seleziona **[!UICONTROL Rules]** (Regole) nella barra a sinistra.

2. Seleziona **[!UICONTROL Create New Rule]** (Aggiungi elemento dati).

3. Nella finestra di dialogo [!UICONTROL Create Rule] (Crea regola):

   - Assegna un nome alla regola, ad esempio `Page View`.

   - Seleziona **[!UICONTROL + Add]** (Aggiungi) sotto [!UICONTROL Events] (Eventi).

   - Nella finestra di dialogo [!UICONTROL Event Configuration] (Configurazione evento):

      - Seleziona **[!UICONTROL Core]** dall’elenco [!UICONTROL Extension] (Estensioni)

      - Seleziona **[!UICONTROL Window Loaded]** (Finestra caricata) dall’elenco [!UICONTROL Event Type] (Estensioni)

        ![Regola - Configurazione evento](./assets/event-windowloaded-pageview.png)

      - Seleziona **[!UICONTROL Keep Changes]** (Mantieni modifiche).



   - Seleziona **[!UICONTROL + Add]** (Aggiungi) sotto [!UICONTROL Actions] (Azioni).

   - Nella finestra di dialogo [!UICONTROL Action Configuration] (Configurazione evento):

      - Seleziona **[!UICONTROL Adobe Experience Platform Web SDK]** dall’elenco [!UICONTROL Extension] (Estensioni)

      - Seleziona **[!UICONTROL Send Event]** (Info pagina) dall’elenco [!UICONTROL Action Type] (Tipo di elemento dati).

      - Seleziona **[!UICONTROL web.webpagedetails.pageViews]** dall’elenco [!UICONTROL Type] (Tipo)

      - Seleziona l’icona del cilindro accanto a [!UICONTROL XDM data] (Dati XDM) e seleziona **[!UICONTROL XDM - Page View]** (XDM - Vista pagina) dall’elenco degli elementi dati.

     ![Regola - Configurazione azione](./assets/action-pageview-xdm.png)

      - Seleziona **[!UICONTROL Keep Changes]** (Mantieni modifiche).

   - L’aspetto della regola dovrebbe essere il seguente:

     ![Crea regola](assets/rule-pageview.png)

   - Seleziona **[!UICONTROL Save]** (Salva).

Quanto sopra è solo un esempio di definizione di una regola che invia a Adobe Experience Platform dati XDM, contenenti valori da altri elementi di dati.

Puoi utilizzare le regole in vari modi nel tag per manipolare le variabili (utilizzando gli elementi dati).

Per ulteriori informazioni, consulta la sezione [Regole](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=it) per ulteriori informazioni.

### Creare e pubblicare il tag

Dopo aver definito elementi dati e regole, devi generare e pubblicare il tag. Quando crei una build della libreria, devi assegnarla a un ambiente. Le estensioni, le regole e gli elementi dati della build vengono quindi compilati e inseriti nell’ambiente assegnato. Ogni ambiente fornisce un codice di incorporamento univoco che consente di integrare la build assegnata nel sito.

Per generare e pubblicare il tag:

1. Seleziona **[!UICONTROL Publishing Flow]** (Flusso di pubblicazione) nella barra a sinistra.

2. Seleziona **[!UICONTROL Select a working library]** (Seleziona una libreria di lavoro) e poi **[!UICONTROL Add Library…]** (Aggiungi libreria...).

3. Nella finestra di dialogo [!UICONTROL Create Library] (Crea libreria):

   - Assegna un nome alla libreria.

   - Seleziona **[!UICONTROL Development (development)]** dall’elenco.[!UICONTROL Environment]

   - Seleziona **[!UICONTROL + Add All Changed Resources]** (Crea set di dati).

     ![Pubblica - Crea libreria](./assets/create-library-aep.png)

   - Seleziona **[!UICONTROL Save & Build to Development]** (Salva e crea per lo sviluppo).

   Il tag viene salvato e generato per l’ambiente di sviluppo. Un punto verde indica la corretta compilazione del tag nell’ambiente di sviluppo.

4. È possibile selezionare **[!UICONTROL ...]** per ricreare la libreria o spostarla in un ambiente di gestione temporanea o produzione.

   ![Pubblica - Libreria di compilazione](./assets/build-library.png)

I tag Adobe Experience Platform supportano flussi di lavoro di pubblicazione semplici o complessi che devono adattarsi alla distribuzione dell’SDK Web di Adobe Experience Platform.

Per ulteriori informazioni, consulta la sezione [Panoramica di pubblicazione](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=it).


### Recuperare il codice del tag

Infine, devi installare il tag sul sito web di cui desideri tenere traccia, il che implica il posizionamento di codice nel tag di intestazione del modello del sito web.

Per ottenere il codice che fa riferimento al tag:

1. Seleziona **[!UICONTROL Environments]** (Ambienti) nella barra a sinistra.

2. Dall’elenco degli ambienti, seleziona il pulsante di installazione (casella) corretto.

   Nella finestra di dialogo [!UICONTROL Web Install Instructions] (Istruzioni per l’installazione Web) seleziona il pulsante di copia accanto al codice script che dovrebbe essere simile al seguente:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Ambiente](./assets/environment.png)

3. Seleziona **[!UICONTROL Close]** (Chiudi).

Invece del codice per l’ambiente di sviluppo, potresti aver selezionato un altro ambiente (gestione temporanea, produzione) in base al punto in cui stai distribuendo l’SDK Web di Adobe Experience Platform.

Per ulteriori informazioni, consulta la sezione [Ambienti](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=it).

## Distribuire e convalidare

Ora puoi distribuire il codice nella versione di sviluppo del tuo sito Web all’interno del tag `<head>`. Una volta implementato, il sito Web inizia a raccogliere dati in Adobe Experience Platform.

Convalida l’implementazione, correggila laddove necessario e una volta corretta, distribuiscila nel tuo ambiente di gestione temporanea e produzione utilizzando la funzione di flusso di lavoro di pubblicazione dei tag.

## Configurare una connessione

Per utilizzare i dati di Adobe Experience Platform in Customer Journey Analytics, crea una connessione che include i dati risultanti dalla configurazione dello schema, del set di dati e del flusso di lavoro.

Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti su questi set di dati, devi prima stabilire una connessione tra i set di dati in Adobe Experience Platform e Workspace.

Per creare la connessione:

1. Nell’interfaccia utente di Customer Journey Analytics, seleziona **[!UICONTROL Connections]** (Connessioni) nel pannello di navigazione superiore.

2. Seleziona **[!UICONTROL Create new connection]** (Crea uova connessione).

3. Nella schermata [!UICONTROL Untitled connection] (Connessione senza titolo):

   Assegna un nome e una descrizione alla connessione in [!UICONTROL Connection Settings] (Impostazioni della connessione).

   Seleziona la sandbox corretta dall’elenco [!UICONTROL Sandbox] in [!UICONTROL Data settings] (Impostazioni dati) e seleziona il numero di eventi giornalieri dall’elenco [!UICONTROL Average number of daily events] (Numero medio di eventi giornalieri).

   ![Impostazioni della connessione](./assets/cja-connections-1.png)

   Seleziona **[!UICONTROL Add datasets]** (Aggiungi set di dati).

   Nel passaggio [!UICONTROL Select datasets] (Seleziona set di dati) in [!UICONTROL Add datasets] (Aggiungi set di dati):

   - Seleziona il set di dati creato in precedenza (`Example dataset` (Set di dati di fidelizzazione di esempio)) e qualsiasi altro set di dati da includere nella connessione.

     ![Aggiungere set di dati](./assets/cja-connections-2b.png)

   - Seleziona **[!UICONTROL Next]** (Avanti).

   Nel passaggio [!UICONTROL Datasets settings] (Impostazioni set di dati) in [!UICONTROL Add datasets] (Aggiungi set di dati):

   - Per ogni set di dati:

      - Seleziona un [!UICONTROL Person ID] (ID persona) tra le identità disponibili definite negli schemi di set di dati in Adobe Experience Platform.

      - Seleziona l’origine dati corretta dall’elenco [!UICONTROL Data source type] (Tipo di origine dati). Se specifichi **[!UICONTROL Other]** (Altro), aggiungi una descrizione per l’origine dati.

      - Imposta **[!UICONTROL Import all new data]** (Importa tutti i nuovi dati) e **[!UICONTROL Dataset backfill existing data]** (Dati esistenti di backfill del set di dati) secondo le tue preferenze.

     ![Configurare i set di dati](./assets/cja-connections-3b.png)

   - Seleziona **[!UICONTROL Add datasets]** (Aggiungi set di dati).

   Seleziona **[!UICONTROL Save]** (Salva).

Per ulteriori informazioni su come creare e gestire una connessione e come selezionare e combinare i set di dati, consulta la sezione [Panoramica delle connessioni](../connections/overview.md).

## Configurare una visualizzazione dati

Una visualizzazione dati è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati da una connessione. Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace, e da quali colonne tali dimensioni e metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione alle attività di reporting in Analysis Workspace.

Per creare la visualizzazione dati:

1. Nell’interfaccia utente di Customer Journey Analytics, seleziona **[!UICONTROL Data views]** (Visualizzazioni dati) nel pannello di navigazione superiore.

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

Per ulteriori informazioni su come creare e modificare una visualizzazione dati, quali componenti sono disponibili per la visualizzazione dati e come utilizzare le impostazioni di filtro e sessioni, consulta la sezione [Panoramica delle visualizzazioni dati](../data-views/data-views.md).


## Configurare un progetto

Analysis Workspace è uno strumento basato su browser flessibile che consente di creare rapidamente le analisi e condividere i dati rilevati sulla base dei tuoi dati. Usa i progetti Workspace per combinare componenti dati, tabelle e visualizzazioni per sviluppare analisi da condividere con altri nella tua organizzazione.

Per creare il progetto:

1. Nell’interfaccia utente di Customer Journey Analytics, seleziona **[!UICONTROL Projects]** (Progetti) nel pannello di navigazione superiore.

2. Seleziona **[!UICONTROL Projects]** (Progetti) nel pannello di navigazione a sinistra.

3. Seleziona **[!UICONTROL Create project]** (Crea progetto).

   ![Progetto Workspace](./assets/cja-projects-1.png)

   Seleziona **[!UICONTROL Blank project]** (Progetto vuoto).

   ![Workspace - Progetto vuoto](./assets/cja-projects-2.png)

4. Seleziona la visualizzazione dati dall’elenco.

   ![Visualizzazione Select Data (Seleziona dati) di Workspace](./assets/cja-projects-3.png).

5. Per creare il primo rapporto, inizia a trascinare dimensioni e metriche sulla [!UICONTROL Freeform table] nel [!UICONTROL Panel]. Ad esempio, trascina `Program Points Balance` e `Page View` come metriche e `email` come dimensione per ottenere una panoramica rapida dei profili che hanno visitato il tuo sito Web e che fanno parte del programma di fidelizzazione per la raccolta di punti di fidelizzazione.

   ![Workspace - Primo rapporto](./assets/cja-projects-5.png)

Per ulteriori informazioni su come creare progetti e generare analisi utilizzando componenti, visualizzazioni e pannelli, consulta la sezione [Panoramica di Analysis Workspace](../analysis-workspace/home.md).

>[!SUCCESS]
>
>Hai completato tutti i passaggi. A partire dalla definizione dei dati da raccogliere (schema) e della posizione in cui memorizzarli (set di dati) in Adobe Experience Platform. Hai quindi configurato un flusso di dati sulla rete Edge per garantire che i dati possano essere inoltrati a tale set di dati. Quindi hai definito e implementato il tag contenente le estensioni (Adobe Experience Platform Web SDK, Experience Cloud ID Service), gli elementi dati e le regole per acquisire i dati dal tuo sito Web e inviarli al tuo flusso di dati. Hai definito una connessione in Customer Journey Analytics per utilizzare i dati di tracciamento del tuo sito Web e altri dati. La definizione della visualizzazione dati ti consente di specificare la dimensione e le metriche da utilizzare e infine hai creato il tuo primo progetto per la visualizzazione e l’analisi dei dati.
