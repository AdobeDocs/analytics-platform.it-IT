---
title: Creare o modificare una connessione
description: Descrive come creare o modificare una connessione a un set di dati di Experience Platform in Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 24b2cdcc2ab2c56775191950af0603f7bedf102b
workflow-type: tm+mt
source-wordcount: '2783'
ht-degree: 79%

---

# Creare o modificare una connessione

L’esperienza di creazione e modifica della connessione porta tutte le impostazioni di configurazione del set di dati e della connessione al centro dello schermo con un flusso di lavoro facilitato. Fornisce un’esperienza dettagliata di selezione, configurazione e revisione dei set di dati. Consente inoltre di specificare informazioni critiche come tipo di set di dati, dimensioni, schema, ID set di dati, stato batch, stato di backfill, ID persona e molto altro, per ridurre il rischio di configurazione errata della connessione. Di seguito una panoramica delle nuove funzionalità:

* Quando si crea la connessione è possibile abilitare una finestra continua di conservazione dei dati.
* È possibile aggiungere e rimuovere i set di dati da una connessione. Quando si rimuove un set di dati, questo viene rimosso dalla connessione e influisce su tutte le visualizzazioni dati associate e sui progetti Analysis Workspace sottostanti.
* Puoi abilitare e richiedere dati di retrocompilazione per set di dati.
* Puoi modificare i set di dati, ad esempio per richiedere un’altra retrocompilazione.
* Puoi importare dati esistenti per set di dati.

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

## Prerequisiti

Il numero massimo di set di dati che puoi aggiungere a una connessione è limitato a 100. Il mix dipende dal pacchetto di Customer Journey Analytics acquistato dalla tua azienda.

In caso di dubbi sul pacchetto di Customer Journey Analytics di cui disponi, contatta l’amministratore.

| Pacchetto **Select** | Pacchetto **Foundation** |
| --- | --- |
| Qualsiasi combinazione di set di dati evento/profilo/ricerca, fino a 100 | Un set di dati evento per connessione |
|  | Fino a 99 set di dati di profilo o di ricerca per connessione |

{style="table-layout:auto"}

## Creare e configurare la connessione {#create-connection}

1. In Customer Journey Analytics, seleziona la scheda **[!UICONTROL Connections]** (Connessioni).
1. Seleziona **[!UICONTROL Create new connection]**.

   ![Impostazioni di connessione senza titolo](assets/create-conn1.png)

1. Configura le impostazioni della connessione.

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Connection name]** | Assegna un nome univoco alla connessione. |
   | **[!UICONTROL Connection description]** | Descrivi lo scopo della connessione. |
   | **[!UICONTROL Sandbox]** | Scegli una sandbox in Experience Platform che contiene i set di dati per cui desideri creare una connessione.<p>Adobe Experience Platform fornisce [sandbox](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) che permettono di suddividere una singola istanza Platform in ambienti virtuali separati, utili per le attività di sviluppo e aggiornamento delle applicazioni di esperienza digitale. Puoi considerare le sandbox come “silos di dati” che contengono set di dati. Le sandbox vengono utilizzate per controllare l’accesso ai set di dati.<p>Dopo aver selezionato la sandbox, la barra a sinistra mostra tutti i set di dati nella sandbox da cui puoi richiamarli. |
   | **[!UICONTROL Enable rolling data window]** | La casella di controllo, se selezionata, consente di definire un’impostazione di conservazione dei dati di Customer Journey Analytics come finestra continua in mesi (1 mese, 3 mesi, 6 mesi, ecc.), a livello di connessione.<p>La conservazione dei dati si basa sulle marche temporali dei set di dati dell’evento e si applica solo ai set di dati dell’evento. Non esiste alcuna impostazione di finestra continua per i set di dati di profilo o di ricerca, in quanto non sono disponibili marche temporali applicabili. Tuttavia, se la connessione include un profilo o set di dati di ricerca (oltre a uno o più set di dati evento), tali dati verranno conservati per lo stesso periodo di tempo.<p> Il vantaggio principale consiste nell’archiviare o generare rapporti solo sui dati applicabili e utili, nonché nell’eliminare i dati meno recenti che non sono più utili. Ti aiuta a rispettare i limiti del tuo contratto e riduce il rischio di sovraccosti.<p>Se lasci l’impostazione predefinita (non selezionata), il periodo di conservazione dei dati viene sostituito dall’impostazione di conservazione dei dati di Adobe Experience Platform. Se disponi di un valore di 25 mesi di dati in Experience Platform, Customer Journey Analytics può ottenere 25 mesi di dati tramite retrocompilazione. Eliminando10 di questi mesi in Platform, Customer Journey Analytics mantiene i restanti 15 mesi. |
   | **[!UICONTROL Add datasets]** (vedi di seguito) | Aggiungi i set di dati se nell’elenco dei set di dati non sono presenti set di dati. |
   | **[!UICONTROL Dataset name]** | Seleziona uno o più set di dati da richiamare nel Customer Journey Analytics e seleziona **[!UICONTROL Add]**.<p>Se sono presenti molti set di dati tra cui scegliere, puoi cercare quelli giusti utilizzando la barra di ricerca apposita sopra l’elenco dei set di dati. |
   | **[!UICONTROL Last updated]** | Solo per i set di dati evento, questa impostazione viene impostata automaticamente sul campo marca temporale predefinito dagli schemi basati su eventi in Experience Platform. “N/A” significa che il set di dati non contiene dati. |
   | **[!UICONTROL Schema]** | [Schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition) in base al quale è stato creato il set di dati in Adobe Experience Platform. |
   | **[!UICONTROL Dataset type]** | Per ogni set di dati aggiunto alla connessione, Customer Journey Analytics imposta automaticamente il tipo di set di dati in base ai dati in arrivo. Esistono 3 tipi diversi di set di dati: dati evento, dati profilo e dati di ricerca. Nella tabella seguente puoi trovare una spiegazione dei tipi di set di dati. |
   | **[!UICONTROL Person ID]** | Seleziona un ID persona dall’elenco a discesa delle identità disponibili. Queste identità sono state definite nello schema del set di dati in Experience Platform. Vedi di seguito per informazioni su come utilizzare Identity Map come ID persona.<p>IMPORTANTE: se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Guarda [questo video](https://www.youtube.com/watch?v=G_ttmGl_LRU) su come definire un’identità in Experience Platform. |
   | **[!UICONTROL Key]** | Solo per i set di dati di ricerca (ad esempio _id). |
   | **[!UICONTROL Matching Key]** | Solo per i set di dati di ricerca (ad esempio _id). |
   | **[!UICONTROL Import new data]** | Imposta su On o Off. |
   | **[!UICONTROL Backfill data]** | Puoi richiedere di eseguire il backfill dei dati in un set di dati in base a marche temporali di evento. Ad esempio, puoi richiedere di eseguire la retrocompilazione degli ultimi 7 giorni di dati. Configura l’ID persona corretto e verifica la connessione. Se tutto sembra a posto, puoi eseguire facilmente il backfill di tutti i dati rimanenti.<p>Inoltre, puoi abilitare l’importazione di nuovi dati per set di dati. |
   | **[!UICONTROL Backfill status]** | Questo stato indica se vengono elaborati dati di backfill. |

   {style="table-layout:auto"}

## Aggiungere e configurare i set di dati {#add-dataset}

Con il nuovo flusso di lavoro è possibile aggiungere un set di dati di Experience Platform quando si crea una connessione.

1. Nella finestra di dialogo Impostazioni della connessione, seleziona **[!UICONTROL Add datasets]**.

2. Nel passaggio [!UICONTROL Select datasets], seleziona uno o più set di dati e quindi scegli **[!UICONTROL Next]**. Deve far parte della connessione almeno un set di dati evento.
   * Per modificare le colonne visualizzate per l’elenco dei set di dati, seleziona ![Impostazioni colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) e seleziona le colonne da visualizzare nella finestra di dialogo [!UICONTROL Customize table].
   * Per cercare un set di dati specifico, utilizza il campo di ricerca ![Cerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).
   * Per scegliere tra visualizzare o nascondere i set di dati selezionati, utilizza ![Seleziona](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg) **[!UICONTROL Hide selected]** o **[!UICONTROL Show selected]**.
   * Per rimuovere un set di dati dall’elenco dei set di dati selezionati, utilizza ![Chiudi](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg). Per rimuovere tutti i set di dati selezionati, seleziona **[!UICONTROL Clear all]**.

   ![Selezionare un set di dati](assets/select-datasets.png)

3. Ora configura i set di dati uno alla volta.

   ![Configurare i set di dati](assets/add-dataset.png)

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Person ID]** | Disponibile solo per i set di dati evento e profilo. Seleziona un ID persona dall’elenco a discesa delle identità disponibili. Queste identità sono state definite nello schema del set di dati in Experience Platform. Vedi di seguito per informazioni su come utilizzare Identity Map come ID persona.<p>Se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Consulta [Definire i campi di identità nell’interfaccia utente](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) per ulteriori informazioni. <p>Il valore per l’ID persona selezionato è considerato sensibile a maiuscole e minuscole. Ad esempio: `abc123` e `ABC123` sono due valori diversi. |
   | **[!UICONTROL Timestamp]** | Solo per i set di dati evento, questa impostazione viene impostata automaticamente sul campo marca temporale predefinito dagli schemi basati su eventi in Experience Platform. |
   | **[!UICONTROL Key]** | Disponibile solo per i set di dati di ricerca. Chiave da utilizzare per un set di dati di ricerca. |
   | **[!UICONTROL Matching key]** | Disponibile solo per i set di dati di ricerca. Chiave corrispondente per partecipare a uno dei set di dati dell’evento. Se questo elenco è vuoto, probabilmente non hai aggiunto o configurato un set di dati evento. |
   | **[!UICONTROL Data source type]** | Seleziona un tipo di origine dati. <br/>I tipi di origini dati includono: <ul><li>[!UICONTROL Web data]</li><li>[!UICONTROL Mobile App data]</li><li>[!UICONTROL POS data]</li><li>[!UICONTROL CRM data]</li><li>[!UICONTROL Survey data]</li><li>[!UICONTROL Call Center data]</li><li>[!UICONTROL Product data]</li><li> [!UICONTROL Accounts data]</li><li> [!UICONTROL Transaction data]</li><li>[!UICONTROL Customer Feedback data]</li><li> [!UICONTROL Other]</li></ul>Questo campo viene utilizzato per esaminare i tipi di origini dati in uso. |
   | **[!UICONTROL Import new data]** | Attiva questa opzione [!UICONTROL On] se desideri stabilire una connessione continua. Quando questa opzione è selezionata, eventuali nuovi batch di dati aggiunti ai set di dati in questa connessione passano automaticamente in Workspace. |
   | **[!UICONTROL Dataset backfill]** | Fai clic su **[!UICONTROL Request backfill]** per eseguire la retrocompilazione dei dati storici.<ul><li>È possibile eseguire la retrocompilazione di ogni set di dati singolarmente.</li><li>Dai priorità ai nuovi dati aggiunti a un set di dati nella connessione in modo che questi dati abbiano la latenza più bassa.</li><li>Eventuali dati di retrocompilazione (storici) vengono importati a una velocità più bassa. La quantità di dati storici influenza la latenza.</li><li>Il connettore di origine di Analytics importa fino a 13 mesi di dati (indipendentemente dalle dimensioni) per le sandbox di produzione. La retrocompilazione nelle sandbox non di produzione è limitata a 3 mesi.</li></ul> |
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

Per visualizzare in anteprima la connessione creata, seleziona **[!UICONTROL Connection preview]** nella finestra di dialogo Impostazioni connessione.

![Anteprima della connessione](assets/create-conn4.png)

Questa anteprima contiene alcune colonne contenenti la configurazione della connessione. I tipi di colonna visualizzati dipendono dai singoli set di dati.

## Tipi di set di dati {#dataset-types}

Per ogni set di dati aggiunto alla connessione, [!UICONTROL Customer Journey Analytics] imposta automaticamente il tipo in base ai dati in arrivo.

>[!IMPORTANT]
>
>Aggiungi almeno un set di dati evento come parte di una connessione.

Esistono tre tipi diversi di set di dati: dati [!UICONTROL Event], dati [!UICONTROL Profile] e dati [!UICONTROL Lookup].

| Tipo di set di dati | Descrizione | Marca temporale | Schema | ID persona |
|---|---|---|---|---|
| **[!UICONTROL Event]** | Dati che rappresentano eventi nel tempo (ad esempio visite web, interazioni, transazioni, dati POS, dati dei sondaggi, dati ad impression, ecc.). Ad esempio, questi dati potrebbero essere tipici dati di click-stream, con un ID cliente o un ID cookie e una marca temporale. Con i dati evento hai la flessibilità di scegliere quale ID usare come ID persona. | Imposta automaticamente sul campo marca temporale predefinito dagli schemi basati sull’evento in [!UICONTROL Experience Platform]. | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con il comportamento “Serie temporali”. Alcuni esempi includono “XDM Experience Event” o “XDM Decision Event”. | Puoi scegliere l’ID persona da includere. Ogni schema di set di dati definito in Experience Platform può avere un proprio set di una o più identità definite e associate a uno spazio dei nomi identità. Ognuna di queste identità può essere utilizzata come ID persona. Alcuni esempi includono ID cookie, ID di unione, ID utente, Codice di tracciamento, ecc. |
| **[!UICONTROL Lookup]** | Ora puoi aggiungere set di dati come ricerche di campi all’interno di tutti i tipi di set di dati: Profilo, Ricerca ed Evento (l’ultimo è sempre stato supportato). Questa funzionalità aggiuntiva estende la capacità di CJA di supportare modelli di dati complessi, tra cui CDP B2B. Questi dati vengono utilizzati per cercare i valori o le chiavi presenti nei dati Evento, Profilo o Ricerca. È possibile aggiungere fino a due livelli di ricerca. (Tieni presente che i [Campi derivati](/help/data-views/derived-fields/derived-fields.md) non possono essere utilizzati come chiave corrispondente per le ricerche in Connessioni). Ad esempio, puoi caricare dati ricerca per mappare gli ID numerici presenti nei dati evento sui nomi dei prodotti. Per un esempio, consulta il [caso d’uso B2B](/help/use-cases/b2b/b2b.md). | N/D | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con comportamento “Record”, ad eccezione della classe “Profilo individuale XDM”. | N/D |
| **[!UICONTROL Profile]** | Dati applicati a visitatori, utenti o clienti nei dati [!UICONTROL Event]. Ad esempio, consente di caricare dati di gestione delle relazioni con i clienti riguardanti i tuoi clienti. | N/D | Qualsiasi schema predefinito o personalizzato basato sulla classe “Profilo individuale XDM”. | Puoi scegliere l’ID persona da includere. Ogni set di dati definito in [!DNL Experience Platform] presenta un proprio set di uno o più ID persona definiti, ad esempio ID cookie, ID di unione, ID utente, Codice di tracciamento e così via.Nota su <br>![ID persona ](assets/person-id.png)****: se crei una connessione che include set di dati con ID diversi, il reporting lo rifletterà. Per unire i set di dati, devi utilizzare lo stesso ID persona. |

{style="table-layout:auto"}

## Utilizzo di campi numerici come chiavi e valori di ricerca {#numeric}

Questa funzionalità è utile se desideri aggiungere un campo numerico come un costo o un margine a un campo chiave basato su stringhe. Consente ai valori numerici di far parte delle ricerche, sia come chiavi che come valori. Nello schema di ricerca, è possibile che i valori numerici siano associati, ad esempio, a nomi di prodotto, costi delle vendite, costi di marketing della campagna o margini. Ecco un esempio di schema di ricerca in Adobe Experience Platform:

![Schema di ricerca](assets/schema.png)

L’inserimento di questi valori come metriche o dimensioni nel reporting di Customer Journey Analytics è ora supportato. Quando configuri la connessione e richiami i set di dati di ricerca, puoi modificare i set di dati e selezionare [!UICONTROL Key] e [!UICONTROL Matching Key]:

![Modifica-set di dati](assets/lookup-dataset.png)

Quando configuri una visualizzazione dati basata su questa connessione, i valori numerici vengono aggiunti come componenti alla visualizzazione dati. Qualsiasi progetto basato su questa visualizzazione dati può quindi generare rapporti su questi valori numerici.

## Utilizzare Identity Map come ID persona {#id-map}

Customer Journey Analytics supporta la possibilità di utilizzare Identity Map per il proprio ID persona. Identity Map è una struttura di dati a mappa che ti consente di caricare coppie chiave -> valore. Le chiavi sono spazi dei nomi dell’identità e il valore è una struttura che contiene il valore dell’identità. Identity Map esiste su ogni riga/evento caricato e viene compilato di conseguenza per ogni riga.

Identity Map è disponibile per qualsiasi set di dati che utilizza uno schema basato sulla classe [ExperienceEvent XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home). Quando selezioni un set di dati da includere in una connessione Customer Journey Analytics, puoi scegliere se avere un campo come ID principale o Identity Map:

![](assets/idmap1.png)

Se selezioni Identity Map, ottieni due opzioni di configurazione aggiuntive:

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Use Primary ID Namespace]** | Questa opzione indica al Customer Journey Analytics, per riga, di trovare l’identità nella Identity Map contrassegnata con un `primary=true` e utilizza tale identità come ID persona per tale riga. L’identità è la chiave primaria utilizzata in Experience Platform per il partizionamento. E questa identità è anche il candidato principale per l’utilizzo come ID persona di Customer Journey Analytics (a seconda di come il set di dati è configurato in una connessione di Customer Journey Analytics). |
| **[!UICONTROL Namespace]** | (Questa opzione è disponibile solo se non si utilizza lo spazio dei nomi ID primario). Gli spazi dei nomi delle identità sono un componente del [Servizio Experienci Platform Identity](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces) che fungono da indicatori del contesto a cui si riferisce un’identità. Se specifichi uno spazio dei nomi, il Customer Journey Analytics cerca la chiave dello spazio dei nomi in Identity Map di ogni riga e utilizza l’identità in tale spazio dei nomi come ID persona per tale riga. Poiché Customer Journey Analytics non è in grado di eseguire una scansione completa del set di dati di tutte le righe per determinare quali spazi dei nomi sono effettivamente presenti, nel menu a discesa vengono elencati tutti gli spazi dei nomi possibili. Scopri quali spazi dei nomi sono specificati nei dati; questi spazi dei nomi non vengono rilevati automaticamente. |

{style="table-layout:auto"}

### Casi edge di Identity Map {#id-map-edge}

Questa tabella mostra le due opzioni di configurazione quando i casi edge sono presenti e come vengono gestiti:

| Opzione | Nessun ID presente in Identity Map | Più ID, nessuno contrassegnato come primario | Più ID contrassegnati come primari | Singolo ID, contrassegnato come primario o meno | Spazio dei nomi non valido con un ID contrassegnato come primario |
|---|---|---|---|---|---|
| **[!UICONTROL Use Primary ID Namespace] selezionato** | Customer Journey Analytics lascia cadere la riga. | Il Customer Journey Analytics rilascia la riga, poiché non è specificato alcun ID primario. | Tutti gli ID contrassegnati come primari, sotto tutti gli spazi dei nomi, vengono estratti in un elenco. Sono quindi ordinati alfabeticamente. Con il nuovo ordinamento, il primo spazio dei nomi con il primo ID viene utilizzato come ID persona. | Il singolo ID viene utilizzato come ID persona. | Anche se lo spazio dei nomi può non essere valido (non presente in Adobe Experience Platform), Customer Journey Analytics utilizza l’ID primario nello spazio dei nomi come ID persona. |
| **[!UICONTROL Specific Identity Map namespace] selezionato** | Customer Journey Analytics lascia cadere la riga. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. (Al momento della creazione della connessione è possibile selezionare solo uno spazio dei nomi valido, pertanto non è possibile utilizzare uno spazio dei nomi/un ID non valido come ID persona). |

{style="table-layout:auto"}

## Calcolare il numero medio di eventi giornalieri {#average-number}

Questo calcolo viene eseguito per ogni set di dati della connessione.

1. Passa a [Servizi query di Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/query/home) e crea una query.

   La query si presenta così:

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   In questo esempio, “analytics_demo_data” è il nome del set di dati.

2. Per mostrare tutti i set di dati esistenti in Adobe Experience Platform, esegui le operazioni seguenti: `Show Tables` query.


## Algoritmo di potatura di set di dati di ricerca di grandi dimensioni

Quando crei una connessione, puoi aggiungere set di dati di grandi dimensioni a scopi di ricerca. Ad esempio, un set di dati che rappresenta un catalogo di prodotti che permette di cercare informazioni descrittive sui prodotti durante la creazione di rapporti e visualizzazioni. Un set di dati di ricerca di questo tipo può superare il massimo di 10 milioni di ricerche univoche attualmente implementate come guardrail, con conseguente salto di dati aggiuntivi.

Puoi richiedere l’algoritmo di potatura di un set di dati di ricerca di grandi dimensioni. Questa potatura algoritmica mantiene solo i dati nel set di dati di ricerca che corrispondono alle chiavi nel set di dati dell’evento. In questo modo, non è necessario caricare l’intero set di dati di ricerca non potato. Gli elementi utilizzati meno di frequente o meno recenti vengono rimossi, il che potrebbe influenzare leggermente i rapporti, ma offre vantaggi significativi. L’algoritmo torna indietro di 90 giorni e si aggiorna settimanalmente.

Contatta il team di supporto Adobe per ulteriori informazioni e per abilitare questa funzionalità.
