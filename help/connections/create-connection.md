---
title: Creare una connessione
description: Descrive come creare una connessione a un set di dati di Platform in Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
source-git-commit: cc12f77d3a0cb9b27a5d0c6a92c35faf2b6e6e35
workflow-type: tm+mt
source-wordcount: '2512'
ht-degree: 57%

---

# Creare una connessione

L’esperienza di creazione e modifica della connessione porta tutte le impostazioni di configurazione del set di dati e della connessione al centro dello schermo con un flusso di lavoro facilitato. Fornisce una selezione dei set di dati, una configurazione e un’esperienza di revisione dettagliate con informazioni critiche come tipo di set di dati, dimensioni, schema, ID set di dati, stato del batch, stato di backfill, ID persona e molto altro per ridurre il rischio di configurazione errata della connessione. Ecco una panoramica delle funzionalità:

* Quando si crea la connessione è possibile abilitare una finestra continua di conservazione dei dati.
* È possibile aggiungere e rimuovere i set di dati da una connessione. Quando si rimuove un set di dati, questo viene rimosso dalla connessione e influisce su tutte le visualizzazioni dati associate e sui progetti Analysis Workspace sottostanti.
* Puoi abilitare e richiedere dati di retrocompilazione per set di dati.
* Puoi modificare i set di dati, ad esempio per richiedere un’altra retrocompilazione.
* Puoi importare dati esistenti per set di dati.

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

## Prerequisiti

È necessario disporre di **Seleziona** per aggiungere un numero illimitato di set di dati a una connessione. Il **Foundation** è limitato a un set di dati. In caso di dubbi sul pacchetto di Customer Journey Analytics disponibile, contattare l&#39;amministratore&#x200B;

## Creare e configurare la connessione {#create-connection}

1. In Customer Journey Analytics, fai clic su **[!UICONTROL Connections]** scheda.
1. Fai clic su **[!UICONTROL Create new connection]**.

   ![Impostazioni della connessione](assets/create-conn1.png)

1. Configura le impostazioni della connessione.

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Connection name]** | Assegna un nome univoco alla connessione. |
   | **[!UICONTROL Connection description]** | Descrivi lo scopo della connessione. |
   | **[!UICONTROL Sandbox]** | Scegli una sandbox in Experience Platform che contiene i set di dati per cui desideri creare una connessione.<p>Adobe Experience Platform fornisce [sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it) che permettono di suddividere una singola istanza Platform in ambienti virtuali separati, utili per le attività di sviluppo e aggiornamento delle applicazioni di esperienza digitale. Puoi considerare le sandbox come &quot;silos di dati&quot; che contengono set di dati. Le sandbox vengono utilizzate per controllare l’accesso ai set di dati.<p>Dopo aver selezionato la sandbox, la barra a sinistra mostra tutti i set di dati nella sandbox da cui puoi richiamarli. |
   | **[!UICONTROL Enable rolling data window]** | Questa casella di controllo, se selezionata, consente di definire la conservazione dei dati di Customer Journey Analytics come finestra continua in mesi (1 mese, 3 mesi, 6 mesi e così via), a livello di connessione.<p>La conservazione dei dati si basa sulle marche temporali dei set di dati dell’evento e si applica solo ai set di dati dell’evento. Non esiste alcuna impostazione di finestra continua per i set di dati di profilo o di ricerca, in quanto non sono disponibili marche temporali applicabili. Tuttavia, se la connessione include un profilo o set di dati di ricerca (oltre a uno o più set di dati evento), tali dati vengono conservati per lo stesso periodo di tempo.<p> Il vantaggio principale consiste nell’archiviare o generare rapporti solo sui dati applicabili e utili, nonché nell’eliminare i dati meno recenti che non sono più utili. Ti aiuta a rispettare i limiti del tuo contratto e riduce il rischio di sovraccosti.<p>Se lasci l’impostazione predefinita (non selezionata), il periodo di conservazione dei dati viene sostituito dall’impostazione di conservazione dei dati di Adobe Experience Platform. Se disponi di 25 mesi di dati in Experienci Platform, il Customer Journey Analytics ottiene 25 mesi di dati tramite backfill. Se elimini 10 di questi mesi in Platform, il Customer Journey Analytics mantiene i restanti 15 mesi. |
   | **[!UICONTROL Add datasets]** (vedi di seguito) | Aggiungi i set di dati se nell’elenco dei set di dati non sono presenti set di dati. |
   | **[!UICONTROL Dataset name]** | Seleziona uno o più set di dati da richiamare nel Customer Journey Analytics e fai clic su **[!UICONTROL Add]**.<p>Se hai molti set di dati tra cui scegliere, puoi cercare quelli giusti utilizzando la barra di ricerca sopra l’elenco dei set di dati. |
   | **[!UICONTROL Last updated]** | Solo per i set di dati evento, questa impostazione viene impostata automaticamente sul campo marca temporale predefinito dagli schemi basati su eventi in Experience Platform. “N/A” significa che il set di dati non contiene dati. |
   | **[!UICONTROL Schema]** | Il [schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=it) in base al quale il set di dati è stato creato in Adobe Experience Platform. |
   | **[!UICONTROL Dataset type]** | Per ogni set di dati aggiunto alla connessione, Customer Journey Analytics imposta automaticamente il tipo di set di dati in base ai dati in arrivo. Esistono 3 tipi diversi di set di dati: dati evento, dati profilo e dati di ricerca. Nella tabella seguente puoi trovare una spiegazione dei tipi di set di dati. |
   | **[!UICONTROL Person ID]** | Seleziona un ID persona dall’elenco a discesa delle identità disponibili. Queste identità sono state definite nello schema del set di dati in Experience Platform. Vedi di seguito per informazioni su come utilizzare Identity Map come ID persona.<p>IMPORTANTE: se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Guarda [questo video](https://www.youtube.com/watch?v=G_ttmGl_LRU) su come definire un’identità in Experience Platform. |
   | **[!UICONTROL Key]** | Solo per i set di dati di ricerca (ad esempio _id). |
   | **[!UICONTROL Matching Key]** | Solo per i set di dati di ricerca (ad esempio _id). |
   | **[!UICONTROL Import new data]** | Imposta su On o Off. |
   | **[!UICONTROL Backfill data]** | Puoi richiedere di eseguire il backfill dei dati in un set di dati in base a marche temporali di evento. Ad esempio, puoi richiedere di eseguire il backfill degli ultimi 7 giorni di dati, configurare l’ID persona corretto e verificare la corretta configurazione della tua connessione. Se tutto sembra a posto, puoi eseguire facilmente il backfill di tutti i dati rimanenti.<p>Inoltre, puoi abilitare l’importazione di nuovi dati per set di dati. Ad esempio, puoi abilitare l’importazione di nuovi dati solo per i dati di ricerca. |
   | **[!UICONTROL Backfill status]** | Indica se vengono elaborati dati di retrocompilazione. |

   {style="table-layout:auto"}

## Aggiungere e configurare i set di dati {#add-dataset}

Con il nuovo flusso di lavoro è possibile aggiungere un set di dati di Experience Platform quando si crea una connessione.

1. Nella finestra di dialogo delle impostazioni della connessione, fai clic su **[!UICONTROL Add datasets]**.

2. Seleziona uno o più set di dati e fai clic su **[!UICONTROL Next]**. Almeno un set di dati evento deve far parte della connessione.

3. Ora configura singolarmente ciascun set di dati.

   ![Configurare i set di dati](assets/add-dataset.png)

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Person ID]** | Seleziona un ID persona dall’elenco a discesa delle identità disponibili. Queste identità sono state definite nello schema del set di dati in Experience Platform. Vedi di seguito per informazioni su come utilizzare Identity Map come ID persona.<p>Se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Guarda questo video su come definire un’identità in Experience Platform. |
   | **[!UICONTROL Timestamp]** | Solo per i set di dati evento, questa impostazione viene impostata automaticamente sul campo marca temporale predefinito dagli schemi basati su eventi in Experience Platform. |
   | **[!UICONTROL Data source type]** | Selezionare un tipo di origine dati. <br/>I tipi di origini dati includono: <ul><li>[!UICONTROL Web data]</li><li>[!UICONTROL Mobile App data]</li><li>[!UICONTROL POS data]</li><li>[!UICONTROL CRM data]</li><li>[!UICONTROL Survey data]</li><li>[!UICONTROL Call Center data]</li><li>[!UICONTROL Product data]</li><li> [!UICONTROL Accounts data]</li><li> [!UICONTROL Transaction data]</li><li>[!UICONTROL Customer Feedback data]</li><li> [!UICONTROL Other]</li></ul>Questo campo viene utilizzato per esaminare i tipi di origini dati in uso. |
   | **[!UICONTROL Import new data]** | Seleziona questa opzione se desideri stabilire una connessione continua, in modo che tutti i nuovi batch di dati aggiunti ai set di dati della connessione vengano automaticamente trasmessi a Workspace. Può essere impostato su [!UICONTROL On] o [!UICONTROL Off]. |
   | **[!UICONTROL Dataset backfill]** | Seleziona **[!UICONTROL Request backfill]** per la retrocompilazione dei dati storici.<ul><li>È possibile retrocompilare ogni set di dati singolarmente.</li><li>Assegna la priorità ai nuovi dati aggiunti a un set di dati nella connessione in modo che abbiano la latenza più bassa.</li><li>Eventuali dati di retrocompilazione (storici) vengono importati a una velocità più bassa. La latenza è influenzata dalla quantità di dati storici disponibili.</li><li>Il connettore di origine di Analytics importa fino a 13 mesi di dati (indipendentemente dalle dimensioni) per le sandbox di produzione. La retrocompilazione nelle sandbox non di produzione è limitata a 3 mesi.</li></ul> |
   | **[!UICONTROL Backfill status]** | Gli indicatori di stato possibili sono:<ul><li>Success (Operazione riuscita)</li><li>X backfill(s) processing (Elaborazione di X retrocompilazioni)</li><li>Off</li></ul> |
   | **[!UICONTROL Dataset ID]** | Questo ID viene generato automaticamente. |
   | **[!UICONTROL Description]** | Descrizione specificata quando è stato creato il set di dati. |
   | **[!UICONTROL Dataset size]** | Dimensione del set di dati. |
   | **[!UICONTROL Schema]** | Schema in base al quale il set di dati è stato creato in Adobe Experience Platform. |
   | **[!UICONTROL Dataset]** | Nome del set di dati. |
   | **[!UICONTROL Preview]**: `<dataset name>` | Visualizza in anteprima il set di dati con le colonne Data, Mio ID e Identificatore. |
   | **[!UICONTROL Remove]** | Puoi eliminare o rimuovere il set di dati e modificare l’ID persona senza eliminare l’intera connessione. L’eliminazione o la rimozione di riduce i costi associati all’acquisizione dei dati e il complicato processo di ricreazione dell’intera connessione e delle visualizzazioni dati associate. |

   {style="table-layout:auto"}

## Anteprima della connessione {#preview}

Per visualizzare in anteprima la connessione creata, fai clic su **[!UICONTROL Connection preview]** nella finestra di dialogo delle impostazioni della connessione.

![Anteprima della connessione](assets/create-conn4.png)

Questa anteprima contiene alcune colonne che elencano la configurazione della connessione. I tipi di colonna visualizzati dipendono dai singoli set di dati.

## Tipi di set di dati {#dataset-types}

Per ogni set di dati aggiunto alla connessione: [!UICONTROL Customer Journey Analytics] imposta automaticamente il tipo di set di dati in base ai dati in arrivo.

>[!IMPORTANT]
>
>È necessario aggiungere almeno un set di dati evento come parte di una connessione.

Esistono tre tipi diversi di set di dati: [!UICONTROL Event] dati, [!UICONTROL Profile] dati, e [!UICONTROL Lookup] dati.

| Tipo di set di dati | Descrizione | Marca temporale | Schema | ID persona |
|---|---|---|---|---|
| **[!UICONTROL Event]** | Dati che rappresentano eventi nel tempo (ad esempio visite web, interazioni, transazioni, dati POS, dati dei sondaggi, dati ad impression e così via). Ad esempio, questi dati potrebbero essere tipici dati di click-stream, con un ID cliente o un ID cookie e una marca temporale. Con i dati evento hai la flessibilità di scegliere quale ID usare come ID persona. | È impostato automaticamente sul campo marca temporale predefinito dagli schemi basati sull’evento in [!UICONTROL Experience Platform]. | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con il comportamento “Serie temporali”. Alcuni esempi includono “XDM Experience Event” o “XDM Decision Event”. | Puoi scegliere l’ID persona da includere. Ogni schema di set di dati definito in Experience Platform può avere un proprio set di una o più identità definite e associate a uno spazio dei nomi identità. Ognuna di queste identità può essere utilizzata come ID persona. Alcuni esempi includono Cookie ID (ID cookie), Stitched ID (ID di unione), User ID (ID utente), Tracking Code (Codice di monitoraggio) e così via. |
| **[!UICONTROL Lookup]** | Ora puoi aggiungere set di dati come ricerche di campi all’interno di tutti i tipi di set di dati: Profilo, Ricerca ed Evento (questi ultimi sono sempre stati supportati). Questa funzionalità aggiuntiva estende la capacità di CJA di supportare modelli di dati complessi, tra cui CDP B2B. Questi dati vengono utilizzati per cercare i valori o le chiavi presenti nei dati evento, profilo o ricerca. È possibile aggiungere fino a due livelli di ricerca. (Tieni presente che [Campi derivati](/help/data-views/derived-fields/derived-fields.md) non può essere utilizzato come chiave corrispondente per le ricerche in Connessioni.) Ad esempio, puoi caricare dati ricerca per mappare gli ID numerici presenti nei dati evento sui nomi dei prodotti. Consulta [Caso di utilizzo B2B](/help/use-cases/b2b/b2b.md) ad esempio. | N/D | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con comportamento “Record”, ad eccezione della classe “Profilo individuale XDM”. | N/D |
| **[!UICONTROL Profile]** | Dati applicati a persone, utenti o clienti in [!UICONTROL Event] dati. Ad esempio, consente di caricare dati di gestione delle relazioni con i clienti riguardanti i tuoi clienti. | N/D | Qualsiasi schema predefinito o personalizzato basato sulla classe “Profilo individuale XDM”. | Puoi scegliere l’ID persona da includere. Ogni set di dati definito in [!DNL Experience Platform] dispone del proprio set di uno o più ID persona definiti, ad esempio Cookie ID (ID cookie), Stitched ID (ID di unione), User ID (ID utente), Tracking Code (Codice di tracciamento) e così via.<br>![ID persona ](assets/person-id.png)**Nota**: se crei una connessione che include set di dati con ID diversi, il reporting lo riflette. Per unire in modo efficace i set di dati è necessario utilizzare lo stesso ID persona. |

{style="table-layout:auto"}

## Utilizzo di campi numerici come chiavi e valori di ricerca {#numeric}

Questa funzionalità di ricerca è utile se si desidera aggiungere un campo numerico, ad esempio un costo o un margine, a un campo chiave basato su stringhe. Consente ai valori numerici di far parte delle ricerche, sia come chiavi che come valori. Nello schema di ricerca, è possibile che i valori numerici siano associati, ad esempio, a nomi di prodotto, costi delle vendite, costi di marketing della campagna o margini. Ecco un esempio di schema di ricerca in Adobe Experience Platform:

![Schema di ricerca](assets/schema.png)

Ora è possibile inserire questi valori come metriche o dimensioni nei rapporti di Customer Journey Analytics. Quando configuri la connessione e richiami i set di dati di ricerca, puoi modificare i set di dati e selezionare [!UICONTROL Key] e [!UICONTROL Matching Key]:

![Modifica-set di dati](assets/lookup-dataset.png)

Quando configuri una visualizzazione dati basata su questa connessione, i valori numerici vengono aggiunti come componenti alla visualizzazione dati. Qualsiasi progetto basato su questa visualizzazione dati può quindi generare rapporti su questi valori numerici.

## Utilizzare Identity Map come ID persona {#id-map}

Customer Journey Analytics supporta la possibilità di utilizzare Identity Map per il proprio ID persona. Identity Map è una struttura di dati a mappa che ti consente di caricare coppie chiave -> valore. Le chiavi sono spazi dei nomi dell’identità e il valore è una struttura che contiene il valore dell’identità. Identity Map esiste su ogni riga/evento caricato e viene compilato di conseguenza per ogni riga.

Identity Map è disponibile per qualsiasi set di dati che utilizza uno schema basato sulla classe [ExperienceEvent XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it). Quando selezioni un set di dati da includere in una connessione di Customer Journey Analytics, puoi selezionare un campo come ID principale o Identity Map:

![](assets/idmap1.png)

Se selezioni Identity Map, ottieni due opzioni di configurazione aggiuntive:

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Use Primary ID Namespace]** | Questa opzione indica al Customer Journey Analytics, per riga, di trovare l’identità nella Identity Map contrassegnata con un attributo primary=true e utilizzarla come ID persona per quella riga. Questa identità è la chiave primaria utilizzata in Experienci Platform per il partizionamento. E questa identità è anche il candidato principale per l’utilizzo come ID persona di Customer Journey Analytics (a seconda di come il set di dati è configurato in una connessione di Customer Journey Analytics). |
| **[!UICONTROL Namespace]** | (Questa opzione è disponibile solo se non si utilizza lo spazio dei nomi ID primario). Gli spazi dei nomi di identità sono un componente di [ Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=it) che fungono da indicatori del contesto a cui si riferisce un’identità. Se specifichi uno spazio dei nomi, il Customer Journey Analytics cerca la chiave dello spazio dei nomi in Identity Map di ogni riga e utilizza l’identità in tale spazio dei nomi come ID persona per tale riga. Poiché il Customer Journey Analytics non è in grado di eseguire una scansione completa del set di dati di tutte le righe per determinare quali spazi di nomi sono presenti, tutti gli spazi di nomi possibili vengono visualizzati nell’elenco a discesa. È necessario sapere quali spazi dei nomi sono specificati nei dati; questi spazi dei nomi non vengono rilevati automaticamente. |

{style="table-layout:auto"}

### Casi edge di Identity Map {#id-map-edge}

Questa tabella mostra le due opzioni di configurazione quando i casi edge sono presenti e come vengono gestiti:

| Opzione | Nessun ID presente in Identity Map | Più ID, nessuno contrassegnato come primario | Più ID contrassegnati come primari | Singolo ID, contrassegnato come primario o meno | Spazio dei nomi non valido con un ID contrassegnato come primario |
|---|---|---|---|---|---|
| **[!UICONTROL Use Primary ID Namespace] selezionato** | La riga viene rilasciata per Customer Journey Analytics. | La riga viene eliminata per Customer Journey Analytics, in quanto non è specificato alcun ID primario. | Tutti gli ID contrassegnati come primari, sotto tutti gli spazi dei nomi, vengono estratti in un elenco. Vengono quindi ordinati alfabeticamente; con il nuovo ordinamento, il primo spazio dei nomi con il primo ID viene utilizzato come ID persona. | Il singolo ID viene utilizzato come ID persona. | Anche se lo spazio dei nomi può non essere valido (non presente in Adobe Experience Platform), il Customer Journey Analytics utilizza l’ID primario nello spazio dei nomi come ID persona. |
| **[!UICONTROL Specific Identity Map namespace] selezionato** | La riga viene rilasciata per Customer Journey Analytics. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. (Al momento della creazione della connessione è possibile selezionare solo uno spazio dei nomi valido, pertanto non è possibile utilizzare uno spazio dei nomi/un ID non valido come ID persona). |

{style="table-layout:auto"}

## Calcolare il numero medio di eventi giornalieri {#average-number}

Questo calcolo viene eseguito per ogni set di dati della connessione.

1. Vai a [Servizi di query Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=it) e creare una query.

   La query si presenta così:

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   In questo esempio, “analytics_demo_data” è il nome del set di dati.

2. Per mostrare tutti i set di dati esistenti in Adobe Experience Platform, esegui le operazioni seguenti: `Show Tables` query.
