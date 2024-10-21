---
title: Creare o modificare una connessione
description: Descrive come creare o modificare una connessione a un set di dati Experience Platform in Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: ea95b576a9d8309d2c6c2aeba589db1fd28ce499
workflow-type: tm+mt
source-wordcount: '3521'
ht-degree: 94%

---

# Creare o modificare una connessione {#create-or-edit-a-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsadded"
>title="Record aggiunti"
>abstract="Il numero di record (righe) aggiunti a una connessione durante l’intervallo di tempo selezionato per i set di dati selezionati."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsskipped"
>title="Record ignorati"
>abstract="Il numero di record (righe) ignorati durante il trasferimento di dati per una connessione nell’intervallo di tempo selezionato per i set di dati selezionati."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsdeleted"
>title="Record eliminati"
>abstract="Il numero di record (righe) rimossi da una connessione durante l’intervallo di tempo selezionato per i set di dati selezionati"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_lastadded"
>title="Ultimo aggiunto"
>abstract="La marca temporale dell’ultimo batch da qualsiasi set di dati trasferito a una connessione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_enablerollingdatawindow"
>title="Abilita dati a finestra scorrevole"
>abstract="Definisci la conservazione dei dati come finestra scorrevole in mesi a livello di connessione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_averagenumberofdailyuses"
>title="Numero medio di utilizzi giornalieri"
>abstract="Seleziona un intervallo per il numero di eventi giornalieri previsti per l’intera connessione."

<!-- markdownlint-enable MD034 -->



L’esperienza del flusso di lavoro di creazione e modifica delle connessioni porta tutte le impostazioni di configurazione del set di dati e della connessione al centro della schermata con un flusso di lavoro facilitato. Fornisce un’esperienza dettagliata di selezione, configurazione e revisione del set di dati. E ti consente di specificare informazioni critiche come tipo di set di dati, dimensioni, schema, ID set di dati, stato del batch, stato di retrocompilazione, ID persona e molto altro, per ridurre il rischio di configurazione errata della connessione. Di seguito una panoramica delle nuove funzionalità:

* Quando si crea la connessione è possibile abilitare una finestra continua di conservazione dei dati.
* È possibile aggiungere e rimuovere i set di dati da una connessione. Quando si rimuove un set di dati, questo viene rimosso dalla connessione e influisce su tutte le visualizzazioni dati associate e sui progetti Analysis Workspace sottostanti.
* Puoi abilitare e richiedere dati di retrocompilazione per set di dati.
* Puoi modificare i set di dati, ad esempio per richiedere un’altra retrocompilazione.
* Puoi importare dati esistenti per set di dati.

+++ Video che illustra come creare e modificare un’esperienza di connessione

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

+++

## Prerequisiti

Il numero massimo di set di dati che puoi aggiungere a una connessione è limitato a 100. Il mix dipende dal pacchetto di Customer Journey Analytics acquistato dalla tua azienda.

In caso di dubbi sul pacchetto di Customer Journey Analytics di cui disponi, contatta l’amministratore.

| Pacchetto **Select** | Pacchetto **Foundation** |
| --- | --- |
| Qualsiasi combinazione di set di dati evento/profilo/ricerca, fino a 100 | Un set di dati evento per connessione |
|  | Fino a 99 set di dati di profilo, di ricerca o di riepilogo per connessione |

{style="table-layout:auto"}

## Creare e configurare la connessione {#create-connection}

1. In Customer Journey Analytics, seleziona la scheda **[!UICONTROL Connections]**.
1. Seleziona **[!UICONTROL Create new connection]**.

   ![Impostazioni di connessione senza titolo](assets/create-conn1.png)

1. Configura le impostazioni della connessione.

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Connection name]** | Assegna un nome univoco alla connessione. |
   | **[!UICONTROL Connection description]** | Descrivi lo scopo della connessione. |
   | **[!UICONTROL Sandbox]** | Scegli una sandbox in Experience Platform che contiene i set di dati per cui desideri creare una connessione.<p>Adobe Experience Platform fornisce [sandbox](https://experienceleague.adobe.com/it/docs/experience-platform/sandbox/home) che permettono di suddividere una singola istanza Platform in ambienti virtuali separati, utili per le attività di sviluppo e aggiornamento delle applicazioni di esperienza digitale. Puoi considerare le sandbox come “silos di dati” che contengono set di dati. Le sandbox vengono utilizzate per controllare l’accesso ai set di dati.<p>Dopo aver selezionato la sandbox, la barra a sinistra mostra tutti i set di dati nella sandbox da cui puoi richiamarli. |
   | **[!UICONTROL Enable rolling data window]** | La casella di controllo, se selezionata, consente di definire un’impostazione di conservazione dei dati di Customer Journey Analytics come finestra continua in mesi (1 mese, 3 mesi, 6 mesi, ecc.), a livello di connessione.<p>La conservazione dei dati si basa sulle marche temporali dei set di dati dell’evento e si applica solo ai set di dati dell’evento. Non esiste alcuna impostazione di finestra continua per i set di dati di profilo o di ricerca, in quanto non sono disponibili marche temporali applicabili. Tuttavia, se la connessione include un profilo o set di dati di ricerca (oltre a uno o più set di dati evento), tali dati verranno conservati per lo stesso periodo di tempo.<p> Il vantaggio principale consiste nell’archiviare o generare rapporti solo sui dati applicabili e utili, nonché nell’eliminare i dati meno recenti che non sono più utili. Ti aiuta a rispettare i limiti del tuo contratto e riduce il rischio di sovraccosti.<p>Se lasci l’impostazione predefinita (non selezionata), il periodo di conservazione viene sostituito dall’impostazione di conservazione dei dati di Adobe Experience Platform. Se disponi di un valore di 25 mesi di dati in Experience Platform, Customer Journey Analytics può ottenere 25 mesi di dati tramite retrocompilazione. Eliminando10 di questi mesi in Platform, Customer Journey Analytics mantiene i restanti 15 mesi. |
   | **[!UICONTROL Add datasets]** (vedi di seguito) | Aggiungi i set di dati se nell’elenco dei set di dati non sono presenti set di dati. |
   | **[!UICONTROL Dataset name]** | Seleziona uno o più set di dati da richiamare in Customer Journey Analytics e seleziona **[!UICONTROL Add]**.<p>Se sono presenti molti set di dati tra cui scegliere, puoi cercare quelli giusti utilizzando la barra di ricerca apposita sopra l’elenco dei set di dati. |
   | **[!UICONTROL Last updated]** | Solo per i set di dati evento, questa impostazione viene impostata automaticamente sul campo marca temporale predefinito dagli schemi basati su eventi in Experience Platform. “N/A” significa che il set di dati non contiene dati. |
   | **[!UICONTROL Number of records]** | Totale dei record del mese precedente per il set di dati in Experience Platform. |
   | **[!UICONTROL Schema]** | [Schema](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/schema/composition) in base al quale è stato creato il set di dati in Adobe Experience Platform. |
   | **[!UICONTROL Dataset type]** | Per ogni set di dati aggiunto alla connessione, Customer Journey Analytics imposta automaticamente il tipo di set di dati in base ai dati in arrivo. Esistono 3 tipi diversi di set di dati: dati evento, dati profilo e dati di ricerca. Nella tabella seguente puoi trovare una spiegazione dei tipi di set di dati. |
   | **[!UICONTROL Granularity]** | La granularità dei dati nel set di dati; applicabile solo per i set di dati di riepilogo. |
   | **[!UICONTROL Data source type]** | Il tipo di origine dati del set di dati. Non applicabile per i set di dati di riepilogo. |
   | **[!UICONTROL Person ID]** | Seleziona un ID persona dall’elenco a discesa delle identità disponibili. Queste identità sono state definite nello schema del set di dati in Experience Platform. Vedi di seguito per informazioni su come utilizzare Identity Map come ID persona.<p>IMPORTANTE: se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Guarda [questo video](https://www.youtube.com/watch?v=G_ttmGl_LRU) su come definire un’identità in Experience Platform. |
   | **[!UICONTROL Key]** | Solo per i set di dati di ricerca (ad esempio _id). |
   | **[!UICONTROL Matching Key]** | Solo per i set di dati di ricerca (ad esempio _id). |
   | **[!UICONTROL Import new data]** | Imposta su On o Off. |
   | **[!UICONTROL Backfill data]** | Puoi richiedere di eseguire la retrocompilazione dei dati in un set di dati. Ad esempio, puoi richiedere di eseguire la retrocompilazione degli ultimi 7 giorni di dati. Configura il set di dati correttamente e verifica la connessione. Se tutto sembra a posto, puoi eseguire facilmente il backfill di tutti i dati rimanenti.<p>Inoltre, puoi abilitare l’importazione di nuovi dati per set di dati. |
   | **[!UICONTROL Backfill status]** | Questo stato indica se vengono elaborati dati di retrocompilazione. |

   {style="table-layout:auto"}

## Aggiungere e configurare i set di dati {#add-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_primaryID"
>title="ID primario"
>abstract="Seleziona l’ID primario corretto per la connessione: Persona per uno scenario B2C. Conto per uno scenario B2B."

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_optionalContainers"
>title="Contenitori opzionali"
>abstract="Seleziona contenitori aggiuntivi.<br/><br/>**[!UICONTROL Global account]**: abilita la configurazione degli account globali in una connessione.<br/>**[!UICONTROL Opportunity]**: abilita la configurazione delle opportunità in una connessione.<br/>**[!UICONTROL Buying group]**: abilita la configurazione dei gruppi di acquisto in una connessione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_personID"
>title="ID persona"
>abstract="Seleziona un ID persona dalle identità disponibili definite nello schema del set di dati nell’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_accountID"
>title="ID account"
>abstract="Seleziona un ID account (identificatore univoco di un account) dalle identità disponibili definite nello schema del set di dati nell’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_globalAccountID"
>title="ID account globale"
>abstract="Seleziona un ID account globale (l’identificatore univoco di un account globale) dalle identità disponibili definite nello schema del set di dati nell’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_opportunityID"
>title="ID opportunità"
>abstract="Seleziona un ID opportunità (l’identificatore univoco di un’opportunità) dalle identità disponibili definite nello schema del set di dati nell’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_buyingGroupID"
>title="ID gruppo di acquisto"
>abstract="Seleziona un ID gruppo di acquisto (l’identificatore univoco per un gruppo di acquisto) tra le identità disponibili definite nello schema del set di dati nell’Experience Platform."

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_importnewdata"
>title="Importare nuovi dati"
>abstract="Eventuali nuovi batch aggiunti al set di dati di Experience Platform verranno aggiunti automaticamente a questa connessione e resi disponibili per l’analisi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_datasetbackfill"
>title="Retrocompilazione dei set di dati"
>abstract="Questa opzione esegue la retrocompilazione dei dati esistenti (storici) da Experience Platform per questo set di dati nella connessione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_transformdataset"
>title="Trasforma set di dati"
>abstract="Questa opzione trasforma il set di dati in modo che possa essere utilizzato per ricerche basate su persone in scenari B2B. Una volta attivata, la trasformazione del set di dati è irreversibile."

<!-- markdownlint-enable MD034 -->

Con il nuovo flusso di lavoro è possibile aggiungere un set di dati di Experience Platform quando si crea una connessione.

1. Nella finestra di dialogo Impostazioni della connessione, seleziona **[!UICONTROL Add datasets]**.

1. Nel passaggio [!UICONTROL Select datasets] viene visualizzato un elenco dei set di dati di Experience Platform.

   ![Selezionare un set di dati](assets/select-datasets.png)

   Per ogni set di dati, l’elenco mostra:

   | Colonna | Descrizione |
   |---|---|
   | Set di dati | Nome del se di dati. Seleziona il nome per indirizzarti al set di dati in Experience Platform. Seleziona ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) per visualizzare un pop-up con ulteriori dettagli per il set di dati. Puoi selezionare **[!UICONTROL Edit in Platform]** per modificare il set di dati direttamente in Experience Platform. |
   | Tipo di set di dati | Tipo di set di dati: evento, profilo, ricerca e riepilogo. |
   | Numero di record | Totale dei record del mese precedente per il set di dati in Experience Platform. |
   | Schema | Lo schema per il set di dati. Seleziona il nome per indirizzarti allo schema in Experience Platform. |
   | Ultimo batch | Stato dell’ultimo batch acquisito in Experience Platform. Per ulteriori informazioni, consulta [Stati batch](https://experienceleague.adobe.com/it/docs/experience-platform/ingestion/batch/troubleshooting#batch-states). |
   | ID set di dati | ID del set di dati. |
   | Ultimo aggiornamento | Marca temporale dell’ultimo aggiornamento del set di dati. |


1. Seleziona uno o più set di dati e seleziona **[!UICONTROL Next]**. Deve far parte della connessione almeno un set di dati evento.
   * Per modificare le colonne visualizzate per l’elenco dei set di dati, seleziona ![Impostazioni colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) e seleziona le colonne da visualizzare nella finestra di dialogo [!UICONTROL Customize table].
   * Per cercare un set di dati specifico, utilizza il campo di ricerca ![Cerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).
   * Per scegliere tra visualizzare o nascondere i set di dati selezionati, utilizza ![Seleziona](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg) **[!UICONTROL Hide selected]** o **[!UICONTROL Show selected]**.
   * Per rimuovere un set di dati dall’elenco dei set di dati selezionati, utilizza ![Chiudi](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg). Per rimuovere tutti i set di dati selezionati, seleziona **[!UICONTROL Clear all]**.




1. Ora configura singolarmente ciascun set di dati.

   ![Configurare i set di dati](assets/add-dataset.png)

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Person ID]** | Disponibile solo per i set di dati evento e profilo. Seleziona un ID persona dall’elenco a discesa delle identità disponibili. Queste identità sono state definite nello schema del set di dati in Experience Platform. Vedi di seguito per informazioni su come utilizzare Identity Map come ID persona.<p>Se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Consulta [Definire i campi di identità nell’interfaccia utente](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/identity) per ulteriori informazioni. <p>Il valore per l’ID persona selezionato è considerato sensibile a maiuscole e minuscole. Ad esempio: `abc123` e `ABC123` sono due valori diversi. |
   | **[!UICONTROL Timestamp]** | Solo per i set di dati evento e riepilogo, questa impostazione viene settata automaticamente sul campo marca temporale predefinito dagli schemi basati su eventi in Experience Platform. |
   | **[!UICONTROL Key]** | Disponibile solo per i set di dati di ricerca. Chiave da utilizzare per un set di dati di ricerca. |
   | **[!UICONTROL Matching key]** | Disponibile solo per i set di dati di ricerca. Chiave corrispondente per partecipare a uno dei set di dati dell’evento. Se questo elenco è vuoto, probabilmente non hai aggiunto o configurato un set di dati evento. |
   | **[!UICONTROL Timezone]** | Disponibile solo per i dati di riepilogo. Seleziona il fuso orario appropriato per i dati di riepilogo delle serie temporali. |
   | **[!UICONTROL Data source type]** | Seleziona un tipo di origine dati. <br/>I tipi di origini dati includono: <ul><li>[!UICONTROL Web data]</li><li>[!UICONTROL Mobile App data]</li><li>[!UICONTROL POS data]</li><li>[!UICONTROL CRM data]</li><li>[!UICONTROL Survey data]</li><li>[!UICONTROL Call Center data]</li><li>[!UICONTROL Product data]</li><li> [!UICONTROL Accounts data]</li><li> [!UICONTROL Transaction data]</li><li>[!UICONTROL Customer Feedback data]</li><li> [!UICONTROL Other]</li></ul>Questo campo viene utilizzato per esaminare i tipi di origini dati in uso. |
   | **[!UICONTROL Import new data]** | Attiva questa opzione se desideri stabilire una connessione continua. Con una connessione continua, i nuovi batch di dati aggiunti ai set di dati sono disponibili automaticamente in Workspace. |
   | **[!UICONTROL Dataset backfill]** | Abilita **[!UICONTROL Backfill all existing data]** per garantire la retrocompilazione di tutti i dati esistenti.<br/><br/>Seleziona **[!UICONTROL Request backfill]** per eseguire la retrocompilazione dei dati storici per un periodo specifico. Puoi definire fino a 10 periodi di retrocompilazione dei set di dati.<ol><li>Definisci il periodo immettendo i dati di inizio e fine o selezionando le date utilizzando il ![Calendario](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).</li><li>Seleziona **[!UICONTROL Queue backfill]** per aggiungere la retrocompilazione all’elenco, oppure **[!UICONTROL Cancel]** per annullare.</li></ol>Per ogni voce, seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) per modificare il periodo oppure ![Elimina](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) per eliminare la voce.<br/><br/>Informazioni sulle retrocompilazioni:<ul><li>È possibile eseguire la retrocompilazione di ogni set di dati singolarmente.</li><li>Dai priorità ai nuovi dati aggiunti a un set di dati nella connessione in modo che questi dati abbiano la latenza più bassa.</li><li>Eventuali dati di retrocompilazione (storici) vengono importati a una velocità più bassa. La quantità di dati storici influenza la latenza.</li><li>Il connettore origine di Analytics importa fino a 13 mesi di dati (indipendentemente dalle dimensioni) per le sandbox di produzione. La retrocompilazione nelle sandbox non di produzione è limitata a 3 mesi.</li></ul> |
   | **[!UICONTROL Transform dataset]** | Per set di dati di ricerca B2B specifici puoi abilitare la trasformazione di un set di dati per scenari di reporting B2B appropriati basati su persone. Per ulteriori informazioni, consulta [Trasformare i set di dati per le ricerche B2B](transform-datasets-b2b-lookups.md). |
   | **[!UICONTROL Backfill status]** | Gli indicatori di stato possibili sono:<ul><li>Success (Operazione riuscita)</li><li>X backfill(s) processing (Elaborazione di X retrocompilazioni)</li><li>Off</li></ul> |
   | **[!UICONTROL Dataset ID]** | Questo ID viene generato automaticamente. |
   | **[!UICONTROL Description]** | Descrizione specificata quando è stato creato il set di dati. |
   | **[!UICONTROL Dataset size]** | Dimensione del set di dati. |
   | **[!UICONTROL Schema]** | Schema sulla cui base è stato creato il set di dati in Adobe Experience Platform. |
   | **[!UICONTROL Dataset]** | Nome del set di dati. |
   | **[!UICONTROL Preview: *nome del set di dati *]** | Visualizza in anteprima il set di dati con le colonne Data, ID personale e Identificatore. |
   | **[!UICONTROL Remove]** | Puoi eliminare o rimuovere il set di dati e modificare l’ID persona senza eliminare l’intera connessione. L’eliminazione o la rimozione riduce i costi associati all’acquisizione dei dati e il complicato processo di ricreazione dell’intera connessione e delle visualizzazioni dati associate. |

   {style="table-layout:auto"}

## Anteprima della connessione {#preview}

Per visualizzare in anteprima la connessione creata, seleziona **[!UICONTROL Connection preview]** nella finestra di dialogo delle impostazioni della connessione.

![Anteprima della connessione](assets/create-conn4.png)

Questa anteprima contiene alcune colonne contenenti la configurazione della connessione. I tipi di colonna visualizzati dipendono dai singoli set di dati.

## Tipi di set di dati {#dataset-types}

Per ogni set di dati aggiunto alla connessione, [!UICONTROL Customer Journey Analytics] imposta automaticamente il tipo in base ai dati in arrivo.

>[!IMPORTANT]
>
>In una connessione è necessario aggiungere almeno un set di dati di evento o riepilogo.

Esistono tipi diversi di set di dati: dati [!UICONTROL Event], dati [!UICONTROL Profile], dati [!UICONTROL Lookup] e dati [!UICONTROL Summary].

| Tipo di set di dati | Descrizione | Marca temporale | Schema | ID persona |
|---|---|---|---|---|
| **[!UICONTROL Event]** | Dati che rappresentano eventi nel tempo. Ad esempio visite web, interazioni, transazioni, dati POS, dati dei sondaggi, dati ad impression, ecc. Questi dati possono essere ad esempio tipici dati di click-stream, con un ID cliente o un ID cookie e una marca temporale. Con i dati evento hai la flessibilità di scegliere quale ID usare come ID persona. | Automaticamente viene impostato sul campo marca temporale predefinito dagli schemi basati sull’evento in [!UICONTROL Experience Platform]. | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con il comportamento “Serie temporali”. Alcuni esempi includono “XDM Experience Event” o “XDM Decision Event”. | Puoi scegliere l’ID persona da includere. Ogni schema di set di dati definito in Experience Platform può avere un proprio set di una o più identità definite e associate a uno spazio dei nomi identità. Ognuna di queste identità può essere utilizzata come ID persona. Alcuni esempi includono ID cookie, ID di unione, ID utente, Codice di tracciamento, ecc. |
| **[!UICONTROL Lookup]** | Ora puoi aggiungere set di dati come ricerche di campi all’interno di tutti i tipi di set di dati: Profilo, Ricerca ed Evento (l’ultimo è sempre stato supportato). Questa funzionalità aggiuntiva estende la capacità di Customer Journey Analytics di supportare modelli di dati complessi, tra cui B2B. Questi dati vengono utilizzati per cercare i valori o le chiavi presenti nei dati Evento, Profilo o Ricerca. È possibile aggiungere fino a due livelli di ricerca. (Tieni presente che i [Campi derivati](/help/data-views/derived-fields/derived-fields.md) non possono essere utilizzati come chiave corrispondente per le ricerche in Connessioni). Ad esempio, puoi caricare dati ricerca per mappare gli ID numerici presenti nei dati evento sui nomi dei prodotti. Per un esempio, consulta l’[esempio B2B](/help/use-cases/b2b/example.md). | N/D | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con comportamento “Record”, ad eccezione della classe “Profilo individuale XDM”. | N/D |
| **[!UICONTROL Profile]** | Dati applicati a visitatori, utenti o clienti nei dati [!UICONTROL Event]. Ad esempio, consente di caricare dati di gestione delle relazioni con i clienti riguardanti i tuoi clienti. | N/D | Qualsiasi schema predefinito o personalizzato basato sulla classe “Profilo individuale XDM”. | Puoi scegliere l’ID persona da includere. Per ogni set di dati (esclusi i set di dati di riepilogo) definito in [!DNL Experience Platform] viene definito anche uno specifico set di uno o più ID persona. Per esempio ID cookie, ID di unione, ID utente, Codice di tracciamento, ecc.Nota su <br>![ID persona ](assets/person-id.png)****: se crei una connessione che include set di dati con ID diversi, comparirà anche nel reporting. Per unire i set di dati è necessario utilizzare lo stesso ID persona. |
| **Riepilogo** | Dati di serie temporali che non sono legati a un singolo ID persona. I dati di riepilogo rappresentano i dati aggregati a un diverso livello di aggregazione, ad esempio le campagne. Puoi utilizzare questi dati in Customer Journey Analytics per supportare vari casi d’uso. Per ulteriori informazioni, consulta [Dati di riepilogo](/help/data-views/summary-data.md). | Viene impostato automaticamente sul campo marca temporale predefinito dagli schemi delle metriche di riepilogo basati sull’evento in Experience Platform. È supportata solo la granularità oraria o giornaliera. | Qualsiasi schema predefinito o personalizzato basato sulla classe “Metriche di riepilogo XDM”. | N/D |

{style="table-layout:auto"}

## Utilizzo di campi numerici come chiavi e valori di ricerca {#numeric}

Questa funzionalità è utile se desideri aggiungere un campo numerico come un costo o un margine a un campo chiave basato su stringhe. Consente ai valori numerici di far parte delle ricerche, sia come chiavi che come valori. Nello schema di ricerca, è possibile che i valori numerici siano associati, ad esempio, a nomi di prodotto, costi delle vendite, costi di marketing della campagna o margini. Ecco un esempio di schema di ricerca in Adobe Experience Platform:

![Schema di ricerca](assets/schema.png)

L’inserimento di questi valori come metriche o dimensioni nel reporting di Customer Journey Analytics è ora supportato. Quando configuri la connessione e richiami i set di dati di ricerca, puoi modificare i set di dati e selezionare [!UICONTROL Key] e [!UICONTROL Matching Key]:

![Modifica-set di dati](assets/lookup-dataset.png)

Quando configuri una visualizzazione dati basata su questa connessione, i valori numerici vengono aggiunti come componenti alla visualizzazione dati. Qualsiasi progetto basato su questa visualizzazione dati può quindi generare rapporti su questi valori numerici.

## Utilizzare Identity Map come ID persona {#id-map}

Customer Journey Analytics supporta la possibilità di utilizzare Identity Map per il proprio ID persona. Identity Map è una struttura di dati a mappa che ti consente di caricare coppie chiave -> valore. Le chiavi sono spazi dei nomi dell’identità e il valore è una struttura che contiene il valore dell’identità. Identity Map esiste su ogni riga/evento caricato e viene compilato di conseguenza per ogni riga.

Identity Map è disponibile per qualsiasi set di dati che utilizza uno schema basato sulla classe [ExperienceEvent XDM](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/home). Quando selezioni un set di dati da includere in una connessione Customer Journey Analytics, puoi scegliere se avere un campo come ID principale o Identity Map:

![](assets/idmap1.png)

Se selezioni Identity Map, ottieni due opzioni di configurazione aggiuntive:

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Use Primary ID Namespace]** | Questa opzione indica a Customer Journey Analytics come trovare l’identità nella Identity Map contrassegnata con un attributo `primary=true` e utilizzarla come ID persona per quella riga. L’identità è la chiave primaria utilizzata in Experience Platform per il partizionamento. E questa identità è anche il candidato principale per l’utilizzo come ID persona di Customer Journey Analytics (a seconda di come il set di dati è configurato in una connessione Customer Journey Analytics). |
| **[!UICONTROL Namespace]** | (Questa opzione è disponibile solo se non si utilizza lo spazio dei nomi ID primario). Gli spazi dei nomi delle identità sono un componente del [servizio Identity di Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/identity/features/namespaces). Gli spazi dei nomi fungono da indicatori del contesto a cui si riferisce un’identità. Se specifichi uno spazio dei nomi, Customer Journey Analytics cercherà l’Identity Map di ogni riga per questa chiave dello spazio dei nomi e utilizzerà l’identità in tale spazio dei nomi come ID persona per tale riga. Poiché Customer Journey Analytics non è in grado di eseguire una scansione completa del set di dati di tutte le righe per determinare quali spazi dei nomi sono effettivamente presenti, nel menu a discesa vengono elencati tutti gli spazi dei nomi possibili. È necessario sapere quali spazi dei nomi sono specificati nei dati; questi spazi dei nomi non vengono rilevati automaticamente. |

{style="table-layout:auto"}

### Casi edge di Identity Map {#id-map-edge}

Questa tabella mostra le due opzioni di configurazione quando i casi edge sono presenti e come vengono gestiti:

| Opzione | Non ci sono ID presenti in Identity Map | Più ID, nessuno contrassegnato come primario | Più ID contrassegnati come primari | Singolo ID, contrassegnato come primario o meno | Spazio dei nomi non valido con un ID contrassegnato come primario |
|---|---|---|---|---|---|
| **[!UICONTROL Use Primary ID Namespace] selezionato** | Customer Journey Analytics rilascia la riga. | Customer Journey Analytics rilascia la riga, poiché non è specificato alcun ID primario. | Tutti gli ID contrassegnati come primari, sotto tutti gli spazi dei nomi, vengono estratti in un elenco. Sono quindi ordinati alfabeticamente. Con il nuovo ordinamento, il primo spazio dei nomi con il primo ID viene utilizzato come ID persona. | Il singolo ID viene utilizzato come ID persona. | Anche se lo spazio dei nomi può non essere valido (non presente in Adobe Experience Platform), Customer Journey Analytics utilizza l’ID primario nello spazio dei nomi come ID persona. |
| **[!UICONTROL Specific Identity Map namespace] selezionato** | Customer Journey Analytics rilascia la riga. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. (Al momento della creazione della connessione è possibile selezionare solo uno spazio dei nomi valido, pertanto non è possibile utilizzare uno spazio dei nomi/un ID non valido come ID persona). |

{style="table-layout:auto"}

## Calcolare il numero medio di eventi giornalieri {#average-number}

Questo calcolo viene eseguito per ogni set di dati della connessione.

1. Passa a [Servizi query di Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/query/home) e crea una query.

   La query si presenta così:

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   In questo esempio, “analytics_demo_data” è il nome del set di dati.

2. Per mostrare tutti i set di dati esistenti in Adobe Experience Platform, esegui la query `Show Tables`.


## Algoritmo di potatura di set di dati di ricerca di grandi dimensioni

Quando crei una connessione, puoi aggiungere set di dati di grandi dimensioni a scopi di ricerca. Ad esempio, un set di dati che rappresenta un catalogo di prodotti che permette di cercare informazioni descrittive sui prodotti durante la creazione di rapporti e visualizzazioni. Un set di dati di ricerca di grandi dimensioni può superare il massimo di 10 milioni di ricerche univoche attualmente implementate come guardrail, con il risultato di saltare dati aggiuntivi.

Puoi richiedere l’algoritmo di potatura di un set di dati di ricerca di grandi dimensioni. Questa potatura algoritmica mantiene solo i dati nel set di dati di ricerca che corrispondono alle chiavi nel set di dati dell’evento. In questo modo, non è necessario caricare l’intero set di dati di ricerca non potato. Gli elementi utilizzati meno di frequente o meno recenti vengono rimossi, il che potrebbe influenzare leggermente i rapporti, ma offre vantaggi significativi. L’algoritmo torna indietro di 90 giorni e si aggiorna settimanalmente.

Contatta il team di supporto Adobe per ulteriori informazioni e per abilitare questa funzionalità.
