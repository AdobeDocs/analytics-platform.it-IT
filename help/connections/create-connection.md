---
title: Creare una connessione
description: Descrive come creare una connessione a un set di dati di Platform in Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
source-git-commit: 322961b416deb049010d9e4e3f2301300a116ee4
workflow-type: tm+mt
source-wordcount: '2062'
ht-degree: 67%

---

# Creare una connessione

Un nuovo flusso di lavoro Connessioni è stato recentemente avviato in Customer Journey Analytics (CJA). Ecco una panoramica delle nuove funzionalità:

* È possibile abilitare una finestra di conservazione dei dati in sequenza al momento della creazione della connessione.
* È possibile aggiungere e rimuovere i set di dati da una connessione. La rimozione di un set di dati lo rimuove dalla connessione e influisce su tutte le visualizzazioni dati associate e sui progetti Analysis Workspace sottostanti.
* Puoi abilitare e richiedere il backfill dei dati per set di dati.
* È possibile modificare i set di dati, ad esempio per richiedere un altro backfill.
* Puoi importare dati esistenti per set di dati.

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

## Creare e configurare la connessione {#create-connection}

1. In CJA, fai clic sul pulsante **[!UICONTROL Connections]** scheda .
1. Fai clic su **[!UICONTROL Create new connection]**.

   ![Impostazioni di connessione](assets/create-conn1.png)

1. Configura le impostazioni di connessione.

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Connection name]** | Immettere un nome univoco per la connessione. |
   | **[!UICONTROL Connection description]** | Descrivere lo scopo di questa connessione. |
   | **[!UICONTROL Sandbox]** | Scegli una sandbox in Experience Platform che contiene i set di dati per cui desideri creare una connessione.<p>Adobe Experience Platform fornisce [sandboxe](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it) che permettono di suddividere una singola istanza Platform in ambienti virtuali separati, utili per le attività di sviluppo e aggiornamento delle applicazioni di esperienza digitale. Potete considerare le sandbox come &quot;silos di dati&quot; che contengono set di dati. Le sandbox vengono utilizzate per controllare l’accesso ai set di dati.<p>Dopo aver selezionato la sandbox, la barra a sinistra mostra tutti i set di dati nella sandbox da cui puoi richiamare. |
   | **[!UICONTROL Enable rolling data window]** | Questa casella di controllo, se selezionata, ti consente di definire la conservazione dei dati CJA come finestra continua in mesi (1 mese, 3 mesi, 6 mesi, ecc.), a livello di connessione.<p>La conservazione dei dati si basa sulle marche temporali dei set di dati dell’evento e si applica solo ai set di dati dell’evento. Non esiste alcuna impostazione della finestra dati continua per i set di dati di profilo o di ricerca, in quanto non sono disponibili marche temporali applicabili. Tuttavia, se la connessione include un profilo o set di dati di ricerca (oltre a uno o più set di dati evento), tali dati verranno conservati per lo stesso periodo di tempo.<p> Il vantaggio principale consiste nell’archiviare o generare rapporti solo sui dati applicabili e utili, nonché nell’eliminare i dati meno recenti che non sono più utili. Ti aiuta a rispettare i limiti del tuo contratto e riduce il rischio di sovraccosti.<p>Se si lascia l’impostazione predefinita (non selezionata), il periodo di conservazione dei dati verrà sostituito dall’impostazione di conservazione dei dati di Adobe Experience Platform. Se ad Experience Platform disponi di 25 mesi di dati, CJA riceverà 25 mesi di dati tramite backfill. Se elimini 10 di questi mesi in Platform, CJA manterrà i restanti 15 mesi. |
   | **[!UICONTROL Add datasets]** (vedi sotto) | Aggiungi i set di dati se nell’elenco dei set di dati non sono presenti set di dati. |
   | **[!UICONTROL Dataset name]** | Seleziona uno o più set di dati da richiamare nel Customer Journey Analytics e fai clic su **[!UICONTROL Add]**.<p>Se hai molti set di dati tra cui scegliere, puoi cercare quelli giusti utilizzando la barra di ricerca per i set di dati di Ricerca sopra l’elenco dei set di dati. |
   | **[!UICONTROL Last updated]** | Solo per i set di dati evento, questa impostazione viene impostata automaticamente sul campo timestamp predefinito dagli schemi basati su eventi in Experience Platform. &quot;N/D&quot; significa che questo set di dati non contiene dati. |
   | **[!UICONTROL Schema]** | questo è lo [schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en) in base a cui il set di dati è stato creato in Adobe Experience Platform. |
   | **[!UICONTROL Dataset type]** | Per ogni set di dati aggiunto alla connessione, Customer Journey Analytics imposta automaticamente il tipo di set di dati in base ai dati in arrivo. Esistono 3 tipi di set di dati diversi: Dati evento, dati profilo e dati di ricerca. Vedi la tabella seguente per una spiegazione dei tipi di set di dati. |
   | **[!UICONTROL Person ID]** | seleziona un ID persona dall’elenco a discesa delle identità disponibili. Queste identità sono state definite nello schema del set di dati in Experience Platform. Vedi di seguito per informazioni su come utilizzare Identity Map come ID persona.<p>IMPORTANTE: Se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Visualizza [questo video](https://www.youtube.com/watch?v=G_ttmGl_LRU) su come definire un’identità in Experience Platform. |
   | **[!UICONTROL Key]** | Solo per i set di dati di ricerca (ad esempio _id). |
   | **[!UICONTROL Matching Key]** | Solo per i set di dati di ricerca (ad esempio _id). |
   | **[!UICONTROL Import new data]** | Impostare su On o Off. |
   | **[!UICONTROL Backfill data]** |  |
   | **[!UICONTROL Backfill status]** | Indica se vengono elaborati dati di backfill. |

   {style=&quot;table-layout:auto&quot;}

## Aggiungere e configurare i set di dati {#add-dataset}

Il nuovo flusso di lavoro consente di aggiungere un set di dati di Experience Platform quando si crea una connessione.

1. Nella finestra di dialogo Impostazioni connessione fare clic su **[!UICONTROL Add datasets]**.
1. Seleziona uno o più set di dati e fai clic su **[!UICONTROL Next]**.

   Tieni presente che almeno un set di dati evento deve far parte della connessione.
1. Ora configura i set di dati uno per uno.

   ![Configurare i set di dati](assets/add-dataset.png)

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Person ID]** | seleziona un ID persona dall’elenco a discesa delle identità disponibili. Queste identità sono state definite nello schema del set di dati in Experience Platform. Vedi di seguito per informazioni su come utilizzare Identity Map come ID persona.<p>Se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Visualizza questo video su come definire un’identità in Experience Platform. |
   | **[!UICONTROL Timestamp]** | Solo per i set di dati evento, questa impostazione viene impostata automaticamente sul campo timestamp predefinito dagli schemi basati su eventi in Experience Platform. |
   | **[!UICONTROL Import new data]** | Seleziona questa opzione se desideri stabilire una connessione continua in modo che tutti i nuovi batch di dati aggiunti ai set di dati in questa connessione passino automaticamente in Workspace. Può essere impostato su On o Off. |
   | **[!UICONTROL Dataset backfill]** | Fai clic su **[!UICONTROL Request backfill]** per eseguire il backfill dei dati storici.<ul><li>È possibile retrocompilare ogni set di dati singolarmente.</li><li>Diamo priorità ai nuovi dati aggiunti a un set di dati nella connessione in modo che questi dati abbiano la latenza più bassa.</li><li>Eventuali dati di retrocompilazione (storici) vengono importati a una velocità più bassa. La latenza è influenzata da quanti dati storici si hanno.</li><li>Il Connettore sorgente Adobe Analytics importa fino a 13 mesi di dati, indipendentemente dalle dimensioni.</li></ul> |
   | **[!UICONTROL Backfill status]** | Gli indicatori di stato possibili sono:<ul><li>Operazione riuscita</li><li>Elaborazione di X backfill</li><li>Disattivato</li></ul> |
   | **[!UICONTROL Dataset ID]** | questo ID viene generato automaticamente. |
   | **[!UICONTROL Description]** | Descrizione data alla creazione del set di dati. |
   | **[!UICONTROL Dataset size]** | Dimensione del set di dati. |
   | **[!UICONTROL Schema]** | questo è lo schema in base a cui il set di dati è stato creato in Adobe Experience Platform. |
   | **[!UICONTROL Dataset]** | Nome del set di dati. |
   | **[!UICONTROL Preview]**: `<dataset name>` | Visualizza in anteprima il set di dati con le colonne data, ID e ID . |
   | **[!UICONTROL Remove]** | Rimuovi questo set di dati dalla connessione. |

   {style=&quot;table-layout:auto&quot;}

## Anteprima connessione {#preview}

Per visualizzare in anteprima la connessione creata, fare clic su **[!UICONTROL Connection preview]** nella finestra di dialogo Impostazioni connessione.

![Anteprima connessione](assets/create-conn4.png)

Questa anteprima contiene diverse colonne che elencano la configurazione della connessione. I tipi di colonna visualizzati dipendono dai singoli set di dati.

## Tipi di dati {#dataset-types}

per ogni set di dati aggiunto alla connessione, [!UICONTROL Customer Journey Analytics] imposta automaticamente il tipo di set di dati in base ai dati in arrivo.

>[!IMPORTANT]
>
>È necessario aggiungere almeno un set di dati evento come parte di una connessione.

Esistono 3 tipi diversi di set di dati: dati [!UICONTROL Event], dati [!UICONTROL Profile] e dati [!UICONTROL Lookup].

| Tipo di set di dati | Descrizione | Marca temporale | Schema | ID persona |
|---|---|---|---|---|
| **[!UICONTROL Event]** | Dati che rappresentano eventi nel tempo (ad esempio visite web, interazioni, transazioni, dati POS, dati dei sondaggi, dati ad impression, ecc.). Questi possono essere ad esempio tipici dati di click-stream, con un ID cliente o un ID cookie e un timestamp. Con i dati evento hai la flessibilità di scegliere quale ID usare come ID persona. | È impostato automaticamente sul campo marca temporale predefinito dagli schemi basati sull’evento in [!UICONTROL Experience Platform]. | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con il comportamento “Serie temporali”. Alcuni esempi includono “XDM Experience Event” o “XDM Decision Event”. | Puoi scegliere l’ID persona da includere. Ogni schema di set di dati definito in Experience Platform può avere un proprio set di una o più identità definite e associate a uno spazio dei nomi identità. Ognuno di questi può essere utilizzato come ID persona. Alcuni esempi includono Cookie ID (ID cookie), Stitched ID (ID di unione), User ID (ID utente), Tracking Code (Codice di tracciamento), ecc. |
| **[!UICONTROL Lookup]** | Questi dati vengono utilizzati per cercare i valori o le chiavi presenti nei dati evento o profilo. Ad esempio, puoi caricare dati ricerca che mappano ID numerici nei dati evento ai nomi dei prodotti. Consulta [questo caso d’uso](/help/use-cases/b2b.md) per un esempio. | N/D | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con comportamento “Record”, ad eccezione della classe “Profilo individuale XDM”. | N/D |
| **[!UICONTROL Profile]** | Dati applicati a visitatori, utenti o clienti nei dati [!UICONTROL Event]. Ad esempio, consente di caricare dati di gestione delle relazioni con i clienti riguardanti i tuoi clienti. | N/D | Qualsiasi schema predefinito o personalizzato basato sulla classe “Profilo individuale XDM”. | Puoi scegliere l’ID persona da includere. Ogni set di dati definito in [!DNL Experience Platform] presenta un proprio set di uno o più ID persona definiti, ad esempio Cookie ID (ID cookie), Stitched ID (ID di unione), User ID (ID utente), Tracking Code (Codice di tracciamento) e così via.<br>![ID persona ](assets/person-id.png)**Nota**: se crei una connessione che include set di dati con ID diversi, il reporting lo rifletterà. Per unire in modo efficace i set di dati è necessario utilizzare lo stesso ID persona. |

{style=&quot;table-layout:auto&quot;}

## Utilizzare Identity Map come ID persona {#id-map}

Customer Journey Analytics ora supporta la possibilità di utilizzare Identity Map per il proprio ID persona. Identity Map è una struttura di dati a mappa che consente a un utente di caricare coppie chiave -> valore. Le chiavi sono spazi dei nomi dell’identità e il valore è una struttura che contiene il valore dell’identità. Identity Map esiste su ogni riga/evento caricato e viene compilato di conseguenza per ogni riga.

Identity Map è disponibile per qualsiasi set di dati che utilizza uno schema basato sulla classe [ExperienceEvent XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it). Quando selezioni un set di dati da includere in una connessione CJA, puoi selezionare un campo come ID principale o Identity Map:

![](assets/idmap1.png)

Se selezioni Identity Map, ottieni due opzioni di configurazione aggiuntive:

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Use Primary ID Namespace]** | Questo indica a CJA, per riga, di trovare l’identità nella Identity Map contrassegnata con un attributo primary=true e utilizzarla come ID persona per quella riga. Questo significa che si tratta della chiave primaria che verrà utilizzata in Experience Platform per il partizionamento. È anche il candidato principale per l’utilizzo come ID visitatore di CJA (a seconda di come il set di dati è configurato in una connessione CJA). |
| **[!UICONTROL Namespace]** | (Questa opzione è disponibile solo se non si utilizza lo spazio dei nomi ID primario). Gli spazi dei nomi di identità sono un componente di [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=it) che fungono da indicatori del contesto a cui si riferisce un’identità. Se specifichi uno spazio dei nomi, CJA cercherà l’Identity Map di ogni riga per questa chiave dello spazio dei nomi e utilizzerà l’identità in tale spazio dei nomi come ID persona per tale riga. Poiché CJA non è in grado di eseguire una scansione completa del set di dati di tutte le righe per determinare quali spazi di nomi sono effettivamente presenti, nel menu a discesa vengono elencati tutti gli spazi di nomi possibili. È necessario sapere quali spazi di nomi sono specificati nei dati, non è possibile rilevare automaticamente questo valore. |

{style=&quot;table-layout:auto&quot;}

### Casi edge di Identity Map {#id-map-edge}

Questa tabella mostra le due opzioni di configurazione quando i casi edge sono presenti e come vengono gestiti:

| Opzione | Nessun ID presente in Identity Map | Nessun ID contrassegnato come primario | Gli ID multipli sono contrassegnati come primari | L’ID singolo è contrassegnato come primario | Spazio dei nomi non valido con un ID contrassegnato come primario |
|---|---|---|---|---|---|
| **[!UICONTROL Use Primary ID Namespace] controllato** | La riga viene rilasciata da CJA. | La riga viene rilasciata da CJA, in quanto non è specificato alcun ID primario. | Tutti gli ID contrassegnati come primari, sotto tutti gli spazi dei nomi, vengono estratti in un elenco. Sono quindi ordinati alfabeticamente. Con questo nuovo ordinamento, il primo spazio dei nomi con il primo ID viene utilizzato come ID persona. | Il singolo ID contrassegnato come primario viene utilizzato come ID persona. | Anche se lo spazio dei nomi può non essere valido (non presente in AEP), CJA utilizza l’ID primario nello spazio dei nomi come ID persona. |
| **[!UICONTROL Specific Identity Map namespace] selezionato** | La riga viene rilasciata da CJA. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio dei nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. (Al momento della creazione della connessione è possibile selezionare solo uno spazio dei nomi valido, pertanto non è possibile utilizzare uno spazio dei nomi/un ID non valido come ID persona). |

{style=&quot;table-layout:auto&quot;}

## Calcolare il numero medio di eventi giornalieri

Questo calcolo deve essere fatto per ogni set di dati della connessione.

1. Vai a [Servizi di query di Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=it) e crea una nuova query.

   La query si presenta così:

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   In questo esempio, “analytics_demo_data” è il nome del set di dati.

1. Esegui la query `Show Tables` per mostrare tutti i set di dati esistenti in AEP.
