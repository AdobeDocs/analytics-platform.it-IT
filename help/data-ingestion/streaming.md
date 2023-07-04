---
title: Inserire e utilizzare i dati in streaming
description: Spiega come inserire e utilizzare i dati in streaming in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: 9984200a-71e6-4697-b46f-f53e8d4c507f
source-git-commit: ff71d21235bd37da73c0b6c628c395da6cda7659
workflow-type: tm+mt
source-wordcount: '1841'
ht-degree: 100%

---

# Inserire e utilizzare i dati in streaming

Questa guida introduttiva spiega come inserire dati in streaming in Adobe Experience Platform e utilizzarli in Customer Journey Analytics.

A questo scopo, è necessario:

- **Configurare uno schema e un set di dati** in Adobe Experience Platform per definire il modello (schema) dei dati da raccogliere e dove raccogliere effettivamente i dati (set di dati).

- **Usare il connettore di origine API HTTP** per inviare facilmente i dati nel set di dati configurato in Adobe Experience Platform.

- **Impostare una connessione** in Customer Journey Analytics. Questa connessione deve includere almeno il set di dati di Adobe Experience Platform.

- **Configurare una visualizzazione dati** in Customer Journey Analytics per definire le metriche e le dimensioni da utilizzare in Analysis Workspace.

- **Configurare un progetto** in Customer Journey Analytics per generare rapporti e visualizzazioni.


>[!NOTE]
>
>Questa è una guida semplificata su come inserire dati in streaming in Adobe Experience Platform e utilizzarli in Customer Journey Analytics. Ti consigliamo vivamente di esaminare le informazioni aggiuntive quando vi fai riferimento.

## Configurare uno schema e un set di dati

Per inserire i dati in Adobe Experience Platform, innanzitutto devi definire quali dati desideri raccogliere. Tutti i dati inseriti in Adobe Experience Platform devono essere conformi a una struttura standard e denormalizzata affinché vengano riconosciuti e utilizzati dalle capacità e funzionalità a valle. Experience Data Model (XDM) è il framework standard che fornisce questa struttura sotto forma di schemi.

Una volta definito uno schema, utilizza uno o più set di dati per memorizzare e gestire la raccolta di dati. Un set di dati è un costrutto di archiviazione e gestione per una raccolta di dati, in genere una tabella, che contiene uno schema (colonne) e dei campi (righe).

Tutti i dati inseriti in Adobe Experience Platform devono essere conformi a uno schema predefinito prima di poter essere memorizzati come set di dati.

### Configurare uno schema

Per questa introduzione, immagina di voler raccogliere alcuni dati relativi alla fidelizzazione, ad esempio ID di fidelizzazione, punti di fidelizzazione e stato di fidelizzazione.
A questo scopo, devi innanzitutto definire uno schema che modelli questi dati.

Per configurare lo schema:

1. Nell’interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Schemas]** (Schemi) all’interno di [!UICONTROL DATA MANAGEMENT] (GESTIONE DATI).

2. Seleziona **[!UICONTROL Create schema]** (Crea schema). Seleziona **[!UICONTROL XDM Individual Profile]** (Profilo individuale XDM) dall’elenco delle opzioni.

   ![Creare uno schema](./assets/create-schema.png)

   >[!INFO]
   >
   >    Per modellare gli _attributi_ del profilo (come nome, e-mail, genere) viene utilizzato uno schema Individual Profile. Per modellare il _comportamento_ di un profilo (come visualizzazione pagina, aggiungi al carrello) viene utilizzato uno schema Experience Event.


3. Nella schermata [!UICONTROL Untitled schema] (Schema senza titolo):

   1. Immetti un nome di visualizzazione per lo schema e (facoltativamente) una descrizione.

      ![Assegnare un nome allo schema](./assets/name-loyalty-schema.png)

   2. Seleziona **[!UICONTROL + Add]** (Aggiungi) in [!UICONTROL Field groups] (Gruppi di campi).

      ![Aggiungere un gruppo di campi](./assets/add-field-group-button.png)

      I gruppi di campi sono raccolte riutilizzabili di oggetti e attributi che consentono di estendere facilmente gli schemi.

   3. Nella finestra di dialogo [!UICONTROL Add fields groups] (Aggiungi gruppi di campi) seleziona il gruppo di campi **[!UICONTROL Loyalty Details]** dall’elenco.

      ![AEP Web SDK ExperienceEvent fieldgroup](./assets/loyalty-fieldgroup.png)

      Puoi selezionare il pulsante di anteprima per visualizzare un’anteprima dei campi che fanno parte del gruppo di campi.

      ![Anteprima AEP Web SDK ExperienceEvent fieldgroup](./assets/loyalty-fieldgroup-preview.png)

      Seleziona **[!UICONTROL Back]** (Indietro) per chiudere l’anteprima.

   4. Seleziona **[!UICONTROL Add field groups]** (Aggiungi gruppi di campi).

4. Seleziona **[!UICONTROL +]** accanto al nome dello schema nel pannello [!UICONTROL Structure] (Struttura).

   ![Pulsante per l’aggiunta di campi nello schema di esempio](./assets/example-loalty-schema-plus.png)

5. Nel pannello [!UICONTROL Field Properties] (Proprietà campo), inserisci `Identification` come nome, **[!UICONTROL Identification]** (Identificazione) come [!UICONTROL Display name] (Nome di visualizzazione), seleziona **[!UICONTROL Object]** (Oggetto) come [!UICONTROL Type] (Tipo) e seleziona **[!UICONTROL Profile Core v2]** come [!UICONTROL Field Group] (Gruppo di campo).

   ![Oggetto di identificazione](./assets/identifcation-loyalty-field.png)

   Aggiunge funzionalità di identificazione allo schema. Nel tuo caso, immagina di voler identificare le informazioni sulla fidelizzazione utilizzando l’indirizzo e-mail nei tuoi dati batch.

   Seleziona **[!UICONTROL Apply]** (Applica) per aggiungere questo oggetto allo schema.

6. Seleziona il campo **[!UICONTROL email]** nell’oggetto di identificazione appena aggiunto e seleziona **[!UICONTROL Identity]** (identità) e **[!UICONTROL Email]** dall’elenco [!UICONTROL Identity namespace] (Spazio dei nomi dell’identità) nel pannello [!UICONTROL Field Properties] (Proprietà campo).

   ![Specificare l’e-mail come identità](./assets/specify-email-loyalty-id.png)

   Stai specificando l’indirizzo e-mail come identità che il servizio Adobe Experience Platform Identity può utilizzare per combinare (unire) il comportamento dei profili.

   Seleziona **[!UICONTROL Apply]** (Applica). Nell’attributo e-mail viene visualizzata l’icona di un’impronta digitale.

7. Seleziona il livello principale dello schema (con il nome dello schema), quindi seleziona il pulsante **[!UICONTROL Profile]** (Profilo).

   Viene richiesto di abilitare lo schema per il profilo. Una volta abilitato, quando i dati vengono inseriti in set di dati basati su questo schema, tali dati vengono uniti su Real-Time Customer Profile.

   Per ulteriori informazioni, consulta la sezione [Abilitare lo schema per l’utilizzo in Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it#profile).

   >[!IMPORTANT]
   >
   >    Una volta salvato uno schema abilitato per il profilo, non è più possibile disattivarlo per il profilo.

   ![Abilitare lo schema per il profilo](./assets/enable-for-profile.png)

8. Seleziona **[!UICONTROL Save]** (Salva) per salvare lo schema.

Hai creato uno schema minimo che modella i dati di fidelizzazione che puoi inserire in Adobe Experience Platform. Lo schema consente l’identificazione dei profili tramite l’indirizzo e-mail. Attivando lo schema per il profilo, garantisci che i dati della tua origine di streaming vengano aggiunti a Real-Time Customer Profile.

Per ulteriori informazioni sull’aggiunta e la rimozione di gruppi di campi e singoli campi a uno schema, consulta la sezione [Creare e modificare schemi nell’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=it).

### Configurare un set di dati

Con lo schema, hai definito il modello dati. Ora devi definire il costrutto per memorizzare e gestire tali dati. Puoi farlo tramite i set di dati.

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

   ![Abilitare lo schema per il profilo](./assets/loyalty-dataset-profile.png)

Per ulteriori informazioni su come visualizzare, visualizzare in anteprima, creare, eliminare un set di dati, consulta la sezione [Guida all’interfaccia utente dei set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it). E come abilitare un set di dati per Real-Time Customer Profile.


## Configurare una connessione streaming API HTTP

L’applicazione di origine invia in streaming i dati conformi allo schema creato e al relativo aspetto.

```json
{
    ...
    "_demosystem4": {
        "identification": {
            "core": {
                "email": "abrocking0@blog.com",
                "loyaltyId": "793406",
            }
        }
    },
    "loyalty": {
        "loyaltyID": [
            "793406"
        ],
        "points": 82.16,
        "status": "Silver"
    }
    ...
}
```

Per eseguire lo streaming di questi dati nel set di dati creato, devi definire un endpoint di streaming a cui inviare i dati. A tale scopo, definisci un connettore di origine API HTTP.

Per creare un connettore di origine API HTTP:

1. Nell’interfaccia utente di Experience Platform, seleziona **[!UICONTROL Sources]** (Origini) sotto [!UICONTROL CONNECTIONS] (CONNESSIONI) nella barra a sinistra.

2. Seleziona **[!UICONTROL Streaming]** dall’elenco [!UICONTROL CATEGORIES] (CATEGORIE).

3. Seleziona **Set up** (Configura) nel riquadro [!UICONTROL HTTP API] (API HTTP).

   ![Riquadro di configurazione dell’API HTTP](./assets/httpapi-tile.png)

4. Nel passaggio [!UICONTROL Authentication] (Autenticazione) della schermata [!UICONTROL Add data] (Aggiungi dati):

   Immetti un nome e una descrizione per la connessione API HTTP.

   Seleziona **[!UICONTROL XDM compatible]** (Compatibile con XDM) per indicare che i dati in streaming sono compatibili con uno schema XDM esistente.

   Seleziona **[!UICONTROL Connect to source]** (Connetti a origine). Se la connessione va a buon fine viene visualizzato [!UICONTROL Connected] (Connessione riuscita).

   ![Autenticazione API HTTP](./assets/httpapi-authentication.png)

   Seleziona **[!UICONTROL Next]** (Avanti) per continuare.

5. Nel passaggio [!UICONTROL Dataflow detail] (Dettagli del flusso di dati) della schermata [!UICONTROL Add data] (Aggiungi dati):

   Seleziona **[!UICONTROL Existing dataset]** (Set di dati esistente), seleziona il set di dati dall’elenco dei set di dati e assegna un nome a [!UICONTROL Dataflow name] (Nome del flusso di dati).

   ![Dettaglio del flusso di dati](./assets/httpapi-dataflowdetail.png)

   Seleziona **[!UICONTROL Next]** (Avanti).

6. Il passaggio [!UICONTROL Review] (Rivedi) nella schermata [!UICONTROL Add data] (Aggiungi dati) fornisce una panoramica della connessione API HTTP.

   ![Dettaglio del flusso di dati](./assets/httpapi-review.png)

   Seleziona **[!UICONTROL Finish]** (Fine).

7. Viene visualizzata la definizione finale dell’endpoint di streaming API HTTP.

   ![Endpoint di streaming API HTTP](./assets/httpapi-streamingendpoint.png)

Puoi copiare l’URL dell’endpoint di streaming e usarlo per configurare la tua applicazione di fidelizzazione per lo streaming dei dati nel set di dati di fidelizzazione di Adobe Experience Platform.

Consulta la sezione [Creare una connessione in streaming API HTTP utilizzando l’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/streaming/http.html?lang=it) per un tutorial molto più completo che spiega come utilizzare l’autenticazione, come mappare i dati quando i dati in arrivo non sono compatibili con lo schema XDM e come creare un nuovo set di dati come parte della configurazione del connettore di streaming.


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

   - Seleziona il set di dati creato in precedenza (`Example Loyalty Dataset` (Set di dati di fidelizzazione di esempio)) e qualsiasi altro set di dati da includere nella connessione.

     ![Aggiungere set di dati](./assets/cja-connections-2.png)

   - Seleziona **[!UICONTROL Next]** (Avanti).

   Nel passaggio [!UICONTROL Datasets settings] (Impostazioni set di dati) in [!UICONTROL Add datasets] (Aggiungi set di dati):

   - Per ogni set di dati:

      - Seleziona un [!UICONTROL Person ID] (ID persona) tra le identità disponibili definite negli schemi di set di dati in Adobe Experience Platform.

      - Seleziona l’origine dati corretta dall’elenco [!UICONTROL Data source type] (Tipo di origine dati). Se specifichi **[!UICONTROL Other]** (Altro), aggiungi una descrizione per l’origine dati.

      - Imposta **[!UICONTROL Import all new data]** (Importa tutti i nuovi dati) e **[!UICONTROL Dataset backfill existing data]** (Dati esistenti di backfill del set di dati) secondo le tue preferenze.

     ![Configurare i set di dati](./assets/cja-connections-3.png)

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

5. Inizia a trascinare dimensioni e metriche su [!UICONTROL Freeform table] (Tabella a forma libera) in [!UICONTROL Panel] (Pannello) per creare il primo rapporto. Ad esempio, trascina `Program Points Balance` e `Page View` come metriche e `email` come dimensione per ottenere una panoramica rapida dei profili che hanno visitato il tuo sito Web e che fanno parte del programma di fidelizzazione per la raccolta di punti di fidelizzazione.

   ![Workspace - Primo rapporto](./assets/cja-projects-5.png)

Per ulteriori informazioni su come creare progetti e generare analisi utilizzando componenti, visualizzazioni e pannelli, consulta la sezione [Panoramica di Analysis Workspace](../analysis-workspace/home.md).

>[!SUCCESS]
>
>Hai completato tutti i passaggi. Partendo dalla definizione dei dati di fidelizzazione da raccogliere (schema) e di dove memorizzarli (set di dati) in Adobe Experience Platform, hai configurato un connettore di origine API HTTP per lo streaming dei dati di fidelizzazione direttamente nel set di dati. La definizione della visualizzazione dati ti consente di specificare la dimensione e le metriche da utilizzare e infine hai creato il tuo primo progetto per la visualizzazione e l’analisi dei dati.
