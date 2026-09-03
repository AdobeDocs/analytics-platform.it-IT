---
title: Acquisire dati tramite Adobe Experience Platform Mobile SDK
description: Spiegare come acquisire i dati in Customer Journey Analytics tramite Adobe Experience Platform Mobile SDK e Edge Network
solution: Customer Journey Analytics
feature: Basics
exl-id: fb48b031-e093-4490-b457-69dbb5debe8d
role: Admin
TQID: https://experienceleague.adobe.com/rbgqDkQLPbw-EfhMyUL-eVXZZ1cxMXiQmvU7Si2WCZ8
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: c38ed341-fab2-46df-9d72-88d8166edebb
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 3536
ht-degree: 46%

---

# Acquisire dati tramite Mobile SDK

Questa guida rapida spiega come acquisire i dati di tracciamento delle app mobili direttamente in Adobe Experience Platform utilizzando Adobe Experience Platform Mobile SDK e Edge Network. Quindi utilizza tali dati in Customer Journey Analytics.

A questo scopo, è necessario:

- **Configurare uno schema e un set di dati** in Adobe Experience Platform per definire il modello (schema) dei dati da raccogliere e dove raccogliere effettivamente i dati (set di dati).

- **Configurare un flusso di dati** per configurare la rete Edge di Adobe Experience Platform in modo che i dati raccolti vengano indirizzati al set di dati configurato in Adobe Experience Platform.

- **Utilizza i tag** per configurare facilmente regole ed elementi dati in base ai dati presenti nell&#39;app mobile. Quindi assicurati che i dati siano inviati al flusso di dati configurato sulla rete Edge di Adobe Experience Platform.

- **Distribuire e convalidare**. Disporre di un ambiente in cui puoi eseguire iterazioni sullo sviluppo dei tag e, una volta convalidato tutto, pubblicarlo in diretta nell’ambiente di produzione.

- **Impostare una connessione** in Customer Journey Analytics. Questa connessione deve includere almeno il set di dati di Adobe Experience Platform.

- **Configurare una visualizzazione dati** in Customer Journey Analytics per definire le metriche e le dimensioni da utilizzare in Analysis Workspace.

- **Configurare un progetto** in Customer Journey Analytics per generare rapporti e visualizzazioni.

>[!NOTE]
>
>Questa guida rapida è una guida semplificata su come acquisire in Adobe Experience Platform i dati raccolti dall’applicazione e utilizzarli in Customer Journey Analytics. Ti consigliamo vivamente di esaminare le informazioni aggiuntive quando vi fai riferimento.


## Configurare uno schema e un set di dati

Per inserire i dati in Adobe Experience Platform, innanzitutto devi definire quali dati desideri raccogliere. Tutti i dati inseriti in Adobe Experience Platform devono essere conformi a una struttura standard e denormalizzata affinché vengano riconosciuti e utilizzati dalle capacità e funzionalità a valle. Experience Data Model (XDM) è il framework standard che fornisce una struttura sotto forma di schemi.

Una volta definito uno schema, utilizza uno o più set di dati per memorizzare e gestire la raccolta di dati. Un set di dati è un costrutto di archiviazione e gestione per una raccolta di dati (in genere una tabella) che contiene uno schema (colonne) e dei campi (righe).

Tutti i dati inseriti in Adobe Experience Platform devono essere conformi a uno schema predefinito prima di poter essere memorizzati come set di dati.

### Configurare uno schema

Desideri tenere traccia di alcuni dati minimi dai profili che utilizzano la tua app mobile, ad esempio il nome della scena e l’identificazione.
Devi innanzitutto definire uno schema che modella questi dati.

Per configurare lo schema:

1. Nell&#39;interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Schemi]** in [!UICONTROL GESTIONE DATI].

1. Seleziona **[!UICONTROL Crea schema]**.
.
1. Nel passaggio Selezionare una classe della procedura guidata Crea schema:

   1. Seleziona **[!UICONTROL Evento esperienza]**.

      ![Creare uno schema](./assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Per modellare il _comportamento_ di un profilo (come nome di scena, premere il pulsante per aggiungere al carrello) viene utilizzato uno schema evento esperienza. Per modellare gli _attributi_ del profilo (come nome, e-mail, genere) viene utilizzato uno schema Individual Profile.

   1. Seleziona **[!UICONTROL Avanti]**.


1. Nel [!UICONTROL passaggio Nome e revisione] della procedura guidata [!UICONTROL Crea schema]:

   1. Immetti un **[!UICONTROL nome visualizzato dello schema]** per lo schema e (facoltativo) una **[!UICONTROL Descrizione]**.

      ![Assegnare un nome allo schema](./assets/create-ee-schema-wizard-step-2.png)

   1. Seleziona **[!UICONTROL Fine]**.

1. Nella scheda Struttura dello schema di esempio:

   1. Selezionare **[!UICONTROL + Aggiungi]** in [!UICONTROL Gruppi di campi].

      ![Aggiungere un gruppo di campi](./assets/add-field-group-button.png)

      I gruppi di campi sono raccolte riutilizzabili di oggetti e attributi che consentono di estendere facilmente lo schema.

   1. Nella finestra di dialogo [!UICONTROL Aggiungi gruppi di campi], seleziona il gruppo di campi **[!UICONTROL AEP Mobile SDK ExperienceEvent]** dall&#39;elenco.

      ![Gruppo di campi Dettagli ciclo di vita mobile di AEP](./assets/select-aepmobilesdk-experienceevent.png)

      Puoi selezionare il pulsante di anteprima per visualizzare un’anteprima dei campi che fanno parte del gruppo di campi, ad esempio `application > name`.

      ![Anteprima gruppo di campi Dettagli ciclo di vita mobile di AEP](./assets/aepmobilesdk-experienceevent-preview.png)

      Seleziona **[!UICONTROL Indietro]** per chiudere l&#39;anteprima.

   1. Seleziona **[!UICONTROL Aggiungi gruppi di campi]**.

1. Seleziona **[!UICONTROL +]** accanto al nome dello schema nel pannello [!UICONTROL Struttura].

   ![Pulsante per l’aggiunta di campi nello schema di esempio](./assets/example-mobileschema-plus.png)

1. Nel pannello [!UICONTROL Proprietà campo], immetti `identification` come [!UICONTROL Nome campo], **[!UICONTROL Identificazione]** come [!UICONTROL Nome visualizzato], seleziona **[!UICONTROL Oggetto]** come [!UICONTROL Tipo] e seleziona **[!UICONTROL Core ExperienceEvent v2.1]** come [!UICONTROL Gruppo campi].

   >[!NOTE]
   >
   >Se tale gruppo di campi non è disponibile, cercane un altro contenente campi di identità. Oppure [crea un nuovo gruppo di campi](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=it) e [aggiungi nuovi campi di identità](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html?lang=it#define-a-identity-field) (come `ecid`, `crmId` e altri di cui hai bisogno) al gruppo di campi e seleziona il nuovo gruppo di campi.

   ![Oggetto di identificazione](./assets/identification-field-mobile.png)

   L’oggetto di identificazione aggiunge funzionalità di individuazione dello schema. Nel tuo caso, vuoi identificare i profili utilizzando la tua app mobile utilizzando l’Experience Cloud ID e l’indirizzo e-mail. Sono disponibili molti altri attributi per monitorare l’identificazione del visitatore (ad esempio, ID cliente, ID di fidelizzazione).

   Seleziona **[!UICONTROL Applica]** per aggiungere questo oggetto allo schema.

1. Seleziona il campo **[!UICONTROL ecid]** nell&#39;oggetto di identificazione appena aggiunto, quindi seleziona **[!UICONTROL Identità]** e **[!UICONTROL Identità primaria]** e **[!UICONTROL ECID]** dall&#39;elenco [!UICONTROL Spazio dei nomi identità] nel pannello di destra.

   ![Specificare ECID come identità](./assets/specify-identity-mobile.png)

   Stai specificando l’Experience Cloud Identity come identità principale che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili con lo stesso ECID.

   Seleziona **[!UICONTROL Applica]**. Nell’attributo ecid viene visualizzata l’icona di un’impronta digitale.

1. Seleziona il campo **[!UICONTROL email]** nell&#39;oggetto di identificazione appena aggiunto, quindi seleziona **[!UICONTROL Identity]** e **[!UICONTROL Email]** dall&#39;elenco [!UICONTROL Identity namespace] nel pannello [!UICONTROL Field Properties].

   ![Specificare l’e-mail come identità](./assets/specify-email-identity-mobile.png)

   Stai specificando l’indirizzo e-mail come un’altra identità che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili.

   Seleziona **[!UICONTROL Applica]**. Nell’attributo e-mail viene visualizzata l’icona di un’impronta digitale.

   Seleziona **[!UICONTROL Salva]**.

1. Seleziona l&#39;elemento principale dello schema con il nome dello schema, quindi seleziona l&#39;opzione **[!UICONTROL Profilo]**.

   Viene richiesto di abilitare lo schema per il profilo. Una volta abilitato, quando i dati vengono inseriti in set di dati basati su questo schema, tali dati vengono uniti su Real-Time Customer Profile.

   Per ulteriori informazioni, consulta la sezione [Abilitare lo schema per l’utilizzo in Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it#profile).

   >[!IMPORTANT]
   >
   >    Una volta salvato uno schema abilitato per il profilo, non è più possibile disattivarlo per il profilo.

   ![Abilitare lo schema per il profilo](./assets/enable-for-profile.png)

1. Seleziona **[!UICONTROL Salva]** per salvare lo schema.

Hai creato uno schema minimo che modella i dati che puoi acquisire dall’app mobile. Lo schema consente di identificare i profili utilizzando Experience Cloud Identity e l’indirizzo e-mail. Attivando lo schema per il profilo, puoi garantire che i dati acquisiti dall’app mobile vengano aggiunti al Profilo cliente in tempo reale.

Oltre ai dati sul comportamento, puoi anche acquisire i dati degli attributi del profilo dalla tua app mobile (ad esempio i dettagli dei profili che si abbonano a una newsletter).

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

1. Nell&#39;interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Set di dati]** in [!UICONTROL GESTIONE DATI].

2. Seleziona **[!UICONTROL Crea set di dati]**.

   ![Creare un set di dati](./assets/create-dataset.png)

3. Seleziona **[!UICONTROL Crea set di dati dallo schema]**.

   ![Creare un set di dati da uno schema](./assets/create-dataset-from-schema.png)

4. Seleziona lo schema creato in precedenza e seleziona **[!UICONTROL Successivo]**.

5. Assegna un nome al set di dati e (facoltativamente) fornisci una descrizione.

   ![Assegnare un nome al set di dati](./assets/name-your-datatest.png)

6. Seleziona **[!UICONTROL Fine]**.

7. Selezionare l&#39;opzione **[!UICONTROL Profilo]**.

   Viene richiesto di abilitare il set di dati per il profilo. Una volta abilitato, il set di dati arricchisce i profili dei clienti in tempo reale con i relativi dati inseriti.

   >[!IMPORTANT]
   >
   >    Puoi abilitare un set di dati per il profilo solo quando lo schema a cui aderisce il set di dati è abilitato anche per il profilo.

   ![Abilitare lo schema per il profilo](./assets/aepwebsdk-dataset-profile.png)

Per ulteriori informazioni su come visualizzare, visualizzare in anteprima, creare, eliminare un set di dati, consulta la sezione [Guida all’interfaccia utente dei set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it). E come abilitare un set di dati per Real-Time Customer Profile.

## Configurare un flusso di dati

Un flusso di dati rappresenta la configurazione lato server quando si implementano gli SDK per Web e dispositivi mobili di Adobe Experience Platform. Durante la raccolta di dati con gli SDK di Adobe Experience Platform, i dati vengono inviati alla rete Edge di Adobe Experience Platform. È il flusso di dati che determina a quali servizi vengono inoltrati i dati.

Nella configurazione, desideri che i dati raccolti dall’app mobile vengano inviati al set di dati in Adobe Experience Platform.

Per impostare il flusso di dati:

1. Nell&#39;interfaccia utente di Adobe Experience Platform, seleziona **[!UICONTROL Datastreams]** da [!UICONTROL DATA COLLECTION] nella barra a sinistra.

2. Seleziona **[!UICONTROL Nuovo flusso di dati]**.

3. Assegna un nome e una descrizione al tuo flusso di dati. Seleziona lo schema dall&#39;elenco [!UICONTROL Schema evento].

   ![Nuovo flusso di dati](./assets/new-datastream.png)

4. Seleziona **[!UICONTROL Salva]**.

5. Selezionare **[!UICONTROL Aggiungi servizio]**.

6. Nella schermata [!UICONTROL Aggiungi servizio]:

   1. Selezionare **[!UICONTROL Adobe Experience Platform]** dall&#39;elenco [!UICONTROL Service].

   2. Assicurarsi che **[!UICONTROL Enabled]** sia selezionato.

   3. Seleziona il set di dati dall&#39;elenco [!UICONTROL Set di dati evento].

      ![Servizio AEP del flusso di dati](./assets/datastream-aep-service.png)

   4. Lascia le altre impostazioni e seleziona **[!UICONTROL Salva]** per salvare lo stream di dati.

Lo stream di dati è ora configurato per inoltrare i dati raccolti dall’app mobile al set di dati in Adobe Experience Platform.

Per ulteriori informazioni su come configurare un flusso di dati e come gestire i dati sensibili consulta la sezione [Panoramica dei flussi di dati](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=it).



## Usare i tag

Per implementare il codice sul sito per raccogliere effettivamente i dati, utilizza la funzione Tag in Adobe Experience Platform. Questa soluzione per la gestione dei tag consente di implementare il codice e altri requisiti di assegnazione dei tag. I tag offrono un’integrazione perfetta con Adobe Experience Platform tramite l’estensione Adobe Experience Platform Mobile SDK.

### Creare il tag

1. Nell&#39;interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Tag]** in [!UICONTROL RACCOLTA DATI].

2. Seleziona **[!UICONTROL Nuova proprietà]**.

   Assegna un nome al tag e seleziona **[!UICONTROL Mobile]**. Seleziona **[!UICONTROL Salva]** per continuare.

   ![Creare una proprietà](./assets/create-mobile-property.png)

### Configurare il tag

Dopo aver creato il tag, devi configurarlo con le estensioni corrette e configurare elementi dati e regole in base a come desideri tenere traccia del sito e inviare dati ad Adobe Experience Platform.

Per configurare, seleziona il nuovo tag creato dall&#39;elenco di [!UICONTROL Proprietà tag].


#### **Estensioni**

Aggiungi l’estensione Adobe Platform Edge Network al tag per garantire che tu possa inviare dati a Adobe Experience Platform (tramite lo stream di dati).

Per creare e configurare l&#39;estensione Adobe Experience Platform Mobile SDK:

1. Seleziona **[!UICONTROL Estensioni]** nella barra a sinistra. Puoi vedere che le estensioni Mobile Core e Profile sono già disponibili.

1. Seleziona **[!UICONTROL Catalogo]** nella barra superiore.

1. Cerca o scorri fino all&#39;estensione **[!UICONTROL Adobe Experience Platform Edge Network]** e seleziona **[!UICONTROL Installa]** nel riquadro a destra per installarla.

1. Seleziona la sandbox e lo stream di dati creato in precedenza per il tuo [!UICONTROL ambiente di produzione] e (facoltativo) [!UICONTROL ambiente di staging] e [!UICONTROL ambiente di sviluppo].

   ![Configurazione dell&#39;estensione AEP Mobile SDK](./assets/aepmobilesdk-extension-datastream.png)

1. Immetti il **[!UICONTROL dominio Edge Network]** sotto [!UICONTROL configurazione dominio]. In genere utilizza `<organizationName>.data.adobedc.net`.

1. Seleziona **[!UICONTROL Salva]**.

Per ulteriori informazioni, vedere [Configurare l&#39;estensione Adobe Experience Platform Edge Network](https://developer.adobe.com/client-sdks/documentation/edge-network).

Desideri anche impostare le seguenti estensioni aggiuntive dal catalogo:

- Identità.
- AEP Assurance.
- Consenso.

Per ulteriori informazioni sulle estensioni e sulla relativa configurazione, consulta [Configurare una proprietà tag](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html?lang=it) nell&#39;esercitazione per app mobili su Experience Platform.

#### **Elementi dati**

Gli elementi dati sono i blocchi costitutivi per il dizionario dati (o mappa dati). Utilizza elementi dati per raccogliere, organizzare e distribuire dati in tutta la tecnologia marketing e pubblicitaria. Puoi impostare nel tag elementi di dati che leggono da dati o eventi dell’app mobile e che possono essere utilizzati per inviare dati a Adobe Experience Platform.

Ad esempio, desideri raccogliere il nome dell’operatore dall’app mobile.

Per definire un elemento dati del nome di un vettore:

1. Seleziona **[!UICONTROL Elementi dati]** nella barra a sinistra.

2. Selezionare **[!UICONTROL Aggiungi elemento dati]**.

3. Nella finestra di dialogo [!UICONTROL Crea elemento dati]:

   - Assegna un nome all’elemento dati, ad esempio `Carrier Name` (Nome pagina).

   - Seleziona **[!UICONTROL Mobile Core]** dall&#39;elenco [!UICONTROL Extension].

   - Selezionare **[!UICONTROL Nome gestore]** dall&#39;elenco [!UICONTROL Tipo elemento dati].


     ![Creare un elemento dati utilizzando le informazioni della pagina](./assets/create-dataelement-mobile.png)

   - Seleziona **[!UICONTROL Salva]**.

Puoi creare tutti gli elementi dati desiderati e utilizzarli nelle regole.


#### **Regole**

I tag in Adobe Experience Platform seguono un sistema basato su regole. Cercano le interazione degli utenti e i relativi dati. Quando i criteri descritti nelle tue regole vengono soddisfatti, la regola attiva l’estensione, lo script o il codice lato client identificato. Puoi utilizzare le regole per inviare dati (come un oggetto XDM) in Adobe Experience Platform utilizzando l’estensione Adobe Experience Platform Edge Network.

Ad esempio, desideri inviare i dati dell’evento quando l’app mobile viene utilizzata (in primo piano) e quando l’app mobile non viene utilizzata (viene rimandata in background).

Per definire una regola:

1. Seleziona **[!UICONTROL Regole]** nella barra a sinistra.

2. Seleziona **[!UICONTROL Crea nuova regola]**.

3. Nella finestra di dialogo [!UICONTROL Crea regola]:

   - Assegna un nome alla regola, ad esempio `Application Status`.

   - Seleziona **[!UICONTROL + Aggiungi]** sotto [!UICONTROL Eventi].

   - Nella finestra di dialogo [!UICONTROL Configurazione evento]:

     - Seleziona **[!UICONTROL Mobile Core]** dall&#39;elenco [!UICONTROL Extension].

     - Seleziona **[!UICONTROL Primo piano]** dall&#39;elenco [!UICONTROL Tipo evento].

     - Seleziona **[!UICONTROL Mantieni modifiche]**.

   - Fai clic su ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_AddCircle_18_N.svg) accanto a [!UICONTROL Mobile Core - Foreground].

     - Seleziona **[!UICONTROL Mobile Core]** dall&#39;elenco [!UICONTROL Extension].

     - Selezionare **[!UICONTROL Sfondo]** dall&#39;elenco [!UICONTROL Tipo evento].

     - Seleziona **[!UICONTROL Mantieni modifiche]**.

   - Fai clic su ![Più](https://spectrum.adobe.com/static/icons/workflow_18/Smock_AddCircle_18_N.svg) Aggiungi sotto [!UICONTROL AZIONI]. Nella finestra di dialogo [!UICONTROL Configurazione azione]:

     - Seleziona **[!UICONTROL Adobe Experience Platform Edge Network]** dall&#39;elenco [!UICONTROL Estensione].

     - Seleziona **[!UICONTROL Inoltra evento ad Edge Network]** dall&#39;elenco [!UICONTROL Tipo azione].

     - Seleziona **[!UICONTROL Mantieni modifiche]**.

   - L’aspetto della regola dovrebbe essere il seguente:

     ![Crea regola](assets/rule-appstatus.png)

   - Seleziona **[!UICONTROL Salva]**.

Quanto sopra è solo un esempio di definizione di una regola che invia dati XDM, contenenti lo stato dell’applicazione, ad Adobe Edge Network e a Adobe Experience Platform.

Puoi utilizzare le regole in vari modi nel tag per manipolare le variabili (utilizzando gli elementi dati).

Per ulteriori informazioni, consulta la sezione [Regole](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/#configure-a-rule-to-forward-lifecycle-metrics-to-platform) per ulteriori informazioni.

### Creare e pubblicare il tag

Dopo aver definito elementi dati e regole, devi generare e pubblicare il tag. Quando crei una build della libreria, devi assegnarla a un ambiente. Le estensioni, le regole e gli elementi dati della build vengono quindi compilati e inseriti nell’ambiente assegnato. Ogni ambiente fornisce un codice da incorporare univoco che consente di integrare la build assegnata nel sito.

Per generare e pubblicare il tag:

1. Seleziona **[!UICONTROL Flusso di pubblicazione]** dalla barra a sinistra.

2. Seleziona **[!UICONTROL Seleziona una libreria di lavoro]**, seguita da **[!UICONTROL Aggiungi libreria...]**.

3. Nella finestra di dialogo [!UICONTROL Crea libreria]:

   - Assegna un nome alla libreria.

   - Selezionare **[!UICONTROL Sviluppo (sviluppo)]** dall&#39;elenco [!UICONTROL Ambiente].

   - Selezionare **[!UICONTROL + Aggiungi tutte le risorse modificate]**.

     ![Pubblica - Crea libreria](./assets/build-library-mobile.png)

   - Seleziona **[!UICONTROL Salva e genera in sviluppo]**.

   Il tag viene salvato e quindi creato per il tuo ambiente di sviluppo. Un punto verde indica la corretta compilazione del tag nell’ambiente di sviluppo.

4. È possibile selezionare **[!UICONTROL ...]** per ricompilare la libreria o spostarla in un ambiente di staging o produzione.

I tag Adobe Experience Platform supportano flussi di lavoro di pubblicazione semplici o complessi che dovrebbero adattarsi alla distribuzione dell’Edge Network di Adobe Experience Platform.

Per ulteriori informazioni, consulta la sezione [Panoramica di pubblicazione](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration).


### Recuperare il codice del tag

Infine, devi utilizzare il tag all’interno dell’app mobile di cui desideri tenere traccia.

Per ottenere istruzioni sul codice che spiegano come configurare l’app mobile e utilizzare il tag nell’app:

1. Seleziona **[!UICONTROL Ambienti]** nella barra a sinistra.

2. Dall&#39;elenco degli ambienti, selezionare il pulsante di installazione ![Box](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Box_18_N.svg) corretto.

   Nella finestra di dialogo [!UICONTROL Istruzioni di installazione mobile], seleziona la piattaforma appropriata ([!UICONTROL iOS], [!UICONTROL Android]). Quindi utilizza il pulsante Copia ![Copia](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) accanto a ciascuno dei frammenti di codice pertinenti che desideri utilizzare per configurare e inizializzare l&#39;app mobile:

   ![Ambiente](./assets/environment-mobile.png)

3. Seleziona **[!UICONTROL Chiudi]**.

Invece del codice per l’ambiente di sviluppo, potresti aver selezionato un altro ambiente (staging, produzione) in base alla posizione in cui stai distribuendo Adobe Experience Platform Mobile SDK.

Per ulteriori informazioni, consulta la sezione [Ambienti](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=it).

## Distribuire e convalidare

Ora puoi distribuire il codice all’interno dell’app mobile. Una volta implementata, l’app mobile inizia a raccogliere dati in Adobe Experience Platform.

Convalida l’implementazione, correggila laddove necessario e una volta corretta, implementala nell’ambiente di staging e di produzione utilizzando la funzione di flusso di lavoro di pubblicazione dei tag.

Per informazioni molto più dettagliate, consulta l&#39;esercitazione sull&#39;implementazione di Adobe Experience Cloud nelle app per dispositivi mobili[&#128279;](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/overview.html?lang=it).

## Configurare una connessione

Per utilizzare i dati di Adobe Experience Platform in Customer Journey Analytics, crea una connessione che include i dati risultanti dalla configurazione dello schema, del set di dati e del flusso di lavoro.

Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti su questi set di dati, devi prima stabilire una connessione tra i set di dati in Adobe Experience Platform e Workspace.

Per creare la connessione:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, seleziona **[!UICONTROL Connessioni]**, facoltativamente da **[!UICONTROL Gestione dati]**, nel menu principale.

2. Seleziona **[!UICONTROL Crea nuova connessione]**.

3. Nella schermata [!UICONTROL Connessione senza titolo]:

   Denomina e descrivi la connessione in [!UICONTROL Impostazioni connessione].

   Selezionare la sandbox corretta dall&#39;elenco [!UICONTROL Sandbox] in [!UICONTROL Impostazioni dati] e selezionare il numero di eventi giornalieri dall&#39;elenco [!UICONTROL Numero medio di eventi giornalieri].

   ![Impostazioni della connessione](./assets/cja-connections-1.png)

   Seleziona **[!UICONTROL Aggiungi set di dati]**.

   Nel passaggio [!UICONTROL Seleziona set di dati] in [!UICONTROL Aggiungi set di dati]:

   - Seleziona i set di dati creati in precedenza e/o altri set di dati rilevanti che desideri includere nella connessione (ad esempio i dati degli eventi di esperienza di tracciamento push e i dati del profilo push di Adobe Journey Optimizer)

     ![Aggiungere set di dati](./assets/cja-connections-ajopush.png)

   - Seleziona **[!UICONTROL Avanti]**.

   Nel passaggio [!UICONTROL Impostazioni set di dati] in [!UICONTROL Aggiungi set di dati]:

   - Per ogni set di dati:

     - Seleziona un [!UICONTROL ID persona] dalle identità disponibili definite negli schemi di set di dati in Adobe Experience Platform.

     - Selezionare l&#39;origine dati corretta dall&#39;elenco [!UICONTROL Tipo origine dati]. Se si specifica **[!UICONTROL Altro]**, aggiungere una descrizione per l&#39;origine dati.

     - Imposta **[!UICONTROL Importa tutti i nuovi dati]** e **[!UICONTROL Recupera i dati esistenti del set di dati]** in base alle tue preferenze.

     ![Configurare i set di dati](./assets/cja-connections-ajopushid.png)

   - Seleziona **[!UICONTROL Aggiungi set di dati]**.

   Seleziona **[!UICONTROL Salva]**.

Per ulteriori informazioni su come creare e gestire una connessione e come selezionare e combinare i set di dati, consulta la sezione [Panoramica delle connessioni](../connections/overview.md).

## Configurare una visualizzazione dati

Una visualizzazione dati è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati da una connessione. Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace, e da quali colonne tali dimensioni e metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione alle attività di reporting in Analysis Workspace.

Per creare la visualizzazione dati:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, seleziona **[!UICONTROL Visualizzazioni dati]**, facoltativamente da **[!UICONTROL Gestione dati]**, nel menu principale.

2. Selezionare **[!UICONTROL Crea nuova visualizzazione dati]**.

3. Nel passaggio [!UICONTROL Configura]:

   Selezionare la connessione dall&#39;elenco [!UICONTROL Connessione].

   Assegna un nome e (facoltativamente) una descrizione alla connessione.

   ![Configurare la visualizzazione dati](./assets/cja-dataview-1.png)

   Seleziona **[!UICONTROL Salva e continua]**.

4. Nel passaggio [!UICONTROL Componenti]:

   Aggiungi qualsiasi campo schema e/o componente standard da includere nelle caselle dei componenti [!UICONTROL METRICS] o [!UICONTROL DIMENSIONS].

   ![Componenti della visualizzazione dati](./assets/cja-dataview-2-mobile.png)

   Seleziona **[!UICONTROL Salva e continua]**.

5. Nel passaggio [!UICONTROL Impostazioni]:

   ![Impostazioni della visualizzazione dati](./assets/cja-dataview-3.png)

   Lasciare le impostazioni immutate e selezionare **[!UICONTROL Salva e termina]**.

Consulta [Panoramica delle visualizzazioni dati](../data-views/data-views.md) per ulteriori informazioni su come creare e modificare una visualizzazione dati, quali componenti sono disponibili per l&#39;utilizzo nella visualizzazione dati e come utilizzare le impostazioni di segmenti e sessioni.


## Configurare un progetto

Analysis Workspace è uno strumento basato su browser flessibile che consente di creare rapidamente le analisi e condividere i dati rilevati sulla base dei tuoi dati. Usa i progetti Workspace per combinare componenti dati, tabelle e visualizzazioni per sviluppare analisi da condividere con altri nella tua organizzazione.

Per creare il progetto:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, seleziona **[!UICONTROL Progetti]** nel menu principale.

2. Seleziona **[!UICONTROL Progetti]** nel menu di navigazione a sinistra.

3. Seleziona **[!UICONTROL Crea progetto]**.

   ![Progetto Workspace](./assets/cja-projects-1.png)

   Seleziona **[!UICONTROL Progetto vuoto]**.

   ![Workspace - Progetto vuoto](./assets/cja-projects-2.png)

4. Seleziona la visualizzazione dati dall’elenco.

   ![Visualizzazione Select Data (Seleziona dati) di Workspace](./assets/cja-projects-3.png).

5. Per creare il primo rapporto, inizia a trascinare dimensioni e metriche sulla [!UICONTROL tabella a forma libera] nel [!UICONTROL pannello]. Ad esempio, trascina `Events` come metrica e `Push Title` come dimensione, suddivisi per `Event Type` per ottenere una panoramica delle notifiche push per la tua app mobile e di ciò che è successo a loro.

   ![Workspace - Primo rapporto](./assets/cja-projects-5-mobile.png)

Per ulteriori informazioni su come creare progetti e generare analisi utilizzando componenti, visualizzazioni e pannelli, consulta la sezione [Panoramica di Analysis Workspace](../analysis-workspace/home.md).

>[!SUCCESS]
>
>Hai completato tutti i passaggi. Partendo dalla definizione dei dati da raccogliere (schema) e di dove memorizzarli (set di dati) in Adobe Experience Platform, hai configurato un flusso di dati sulla rete Edge per garantire che i dati possano essere inoltrati a tale set di dati. Quindi hai definito e implementato il tag contenente le estensioni (Adobe Experience Platform Edge Network e altri), gli elementi dati e le regole per acquisire dati dall’app mobile e inviarli allo stream di dati. Hai definito una connessione in Customer Journey Analytics per utilizzare i dati di tracciamento delle notifiche push nell’app mobile e altri dati. La definizione della visualizzazione dati ti consente di specificare la dimensione e le metriche da utilizzare; infine, hai creato il tuo primo progetto per visualizzare e analizzare i dati delle app mobili.
