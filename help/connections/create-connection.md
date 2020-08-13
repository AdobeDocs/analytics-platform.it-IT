---
title: Creare una connessione
description: Descrive come creare una connessione a un set di dati di Platform in Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: bbe86f2d6e052262f0e8a84bca0996f4e2589433
workflow-type: tm+mt
source-wordcount: '1590'
ht-degree: 43%

---


# Creare una connessione

Una connessione consente di integrare i set di dati da [!DNL Adobe Experience Platform] a [!UICONTROL Workspace]. Per creare rapporti sui set di dati [!DNL Experience Platform] bisogna prima stabilire una connessione tra i set di dati in [!DNL Experience Platform] e [!UICONTROL Workspace].

Fai clic [qui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) per una panoramica video.

>[!IMPORTANT]
>
>È possibile combinare più set di dati [!DNL Experience Platform] in una singola connessione.

## Seleziona sandbox e set di dati

1. Vai a [https://analytics.adobe.com](https://analytics.adobe.com).

1. Fai clic sulla scheda **[!UICONTROL Connections]**.

1. Fai clic su **[!UICONTROL Create new connection]** in alto a destra.

   ![Crea connessione](assets/create-connection0.png)

1. Scegliete una sandbox in  Experience Platform che contenga il/i set di dati a cui desiderate creare una connessione.

   Adobe Experience Platform fornisce [sandbox](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) quale partizione di una singola istanza della piattaforma in ambienti virtuali separati per sviluppare e sviluppare applicazioni per esperienze digitali. Potete considerare le sandbox come &quot;silos di dati&quot; contenenti set di dati. Le sandbox vengono utilizzate per controllare l&#39;accesso ai set di dati.  Dopo aver selezionato la sandbox, la barra a sinistra mostra tutti i set di dati nella sandbox da cui è possibile eseguire il pulling.

   >[!IMPORTANT]
   >
   >Non potete accedere ai dati tra più sandbox, ad esempio potete combinare solo set di dati all’interno di una sandbox.

1. Seleziona uno o più set di dati da richiamare in [!UICONTROL Customer Journey Analytics] e fai clic su **[!UICONTROL Add]**.

   (Se avete molti set di dati tra cui scegliere, potete cercare quelli giusti utilizzando la variabile **[!UICONTROL Search datasets]** barra di ricerca sopra l&#39;elenco dei set di dati.

## Configura set di dati

Sul lato destro è ora possibile configurare i set di dati aggiunti.

![Configura set di dati](assets/create-connection.png)

1. **[!UICONTROL Dataset type]**: Per ogni set di dati aggiunto alla connessione, [!UICONTROL Customer Journey Analytics] imposta automaticamente il tipo di dataset in base ai dati in arrivo.

   Esistono 3 tipi diversi di set di dati: dati [!UICONTROL Event], dati [!UICONTROL Profile] e dati [!UICONTROL Lookup].

   | Tipo di set di dati | Descrizione | Timestamp | Schema | ID persona |
   |---|---|---|---|---|
   | [!UICONTROL Event] | Dati che rappresentano eventi nel tempo (ad esempio visite web, interazioni, transazioni, dati POS, dati dei sondaggi, dati ad impression, ecc.). Questi possono essere ad esempio tipici dati di click-stream, con un ID cliente o un ID cookie e un timestamp. Con i dati evento hai la flessibilità di scegliere quale ID usare come ID persona. | È impostato automaticamente sul campo timestamp predefinito dagli schemi basati sull’evento in [UICONTROL Experience Platform]. | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con il comportamento “Serie temporali”. Alcuni esempi includono “XDM Experience Event” o “XDM Decision Event”. | Puoi scegliere l’ID persona da includere. Ogni schema di set di dati definito in Experience Platform può avere un proprio set di una o più identità definite e associate a uno spazio dei nomi identità. Ognuno di questi può essere utilizzato come ID persona. Alcuni esempi includono Cookie ID (ID cookie), Stitched ID (ID di unione), User ID (ID utente), Tracking Code (Codice di tracciamento), ecc. |
   | [!UICONTROL Lookup] | (analogo a un file Classifications in Adobe Analytics  tradizionale). Questi dati vengono utilizzati per cercare i valori o le chiavi presenti nei dati evento o profilo. Ad esempio, puoi caricare dati ricerca che mappano ID numerici nei dati evento ai nomi dei prodotti. Vedere [questo caso d&#39;uso](/help/use-cases/b2b.md) ad esempio. | N/D | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con comportamento “Record”, ad eccezione della classe “Profilo individuale XDM”. | N/D |
   | [!UICONTROL Profile] | Analogo a [!UICONTROL Customer Attributes] per attributi non modificabili e non temporali. Dati applicati a visitatori, utenti o clienti nei dati [!UICONTROL Event]. Ad esempio, consente di caricare dati di gestione delle relazioni con i clienti riguardanti i tuoi clienti. | N/D | Qualsiasi schema predefinito o personalizzato basato sulla classe “Profilo individuale XDM”. | Puoi scegliere l’ID persona da includere. Ogni set di dati definito in [!DNL Experience Platform] presenta un proprio set di uno o più ID persona definiti, ad esempio Cookie ID (ID cookie), Stitched ID (ID di unione), User ID (ID utente), Tracking Code (Codice di tracciamento) e così via.<br>![ID persona ](assets/person-id.png)**Nota:** se crei una connessione che include set di dati con ID diversi, il reporting lo rifletterà. Per unire in modo efficace i set di dati è necessario utilizzare lo stesso ID persona. |

1. **[!UICONTROL Dataset ID]**: Questo ID viene generato automaticamente.

1. **[!UICONTROL Time stamp]**: aggiungi il contenuto qui

1. **[!UICONTROL Schema]**: Questa è la [schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) in base al quale il set di dati è stato creato in Adobe Experience Platform.

1. **[!UICONTROL Person ID]**: Selezionate un ID persona dall&#39;elenco a discesa delle identità disponibili. Tali identità sono state definite nello schema del set di dati nel Experience Platform . Consulta di seguito per informazioni su come utilizzare la mappa identità come ID persona.

   >[!IMPORTANT]
   >
   >Se non sono disponibili ID di persona, uno o più ID di persona non sono stati definiti nello schema. Visualizza [questo video](https://youtu.be/G_ttmGl_LRU) su come definire un&#39;identità in  Experience Platform.

1. Click **[!UICONTROL Next]** per passare al [!UICONTROL Enable Connection] finestra di dialogo.

### Usa mappa identità come ID persona

Il Customer Journey Analytics ora supporta la possibilità di utilizzare la mappa identità per il relativo ID persona. Mappa identità è una struttura di dati mappa che consente a un utente di caricare coppie chiave -> valore. Le chiavi sono spazi dei nomi dell’identità e il valore è una struttura che contiene il valore dell’identità. La mappa identità esiste su ogni riga/evento caricato e viene compilata di conseguenza per ogni riga.

La mappa identità è disponibile per qualsiasi set di dati che utilizza uno schema basato su [ExperienceEvent XDM](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) class. Quando si seleziona un set di dati da includere in una connessione CJA, è possibile selezionare un campo come ID principale o Mappa identità:

![](assets/idmap1.png)

Se selezionate Mappa identità, vengono visualizzate due opzioni di configurazione aggiuntive:

| Opzione | Descrizione |
|---|---|
| [!UICONTROL Use Primary ID Namespace] | Questo indica a CJA, per riga, di trovare l&#39;identità nella Mappa identità contrassegnata con un attributo primario=true e utilizzarla come ID persona per quella riga. Questo significa che si tratta della chiave primaria che verrà utilizzata nel Experience Platform  partizionamento. È anche il candidato principale per l’utilizzo come ID visitatore di CJA (a seconda di come il set di dati è configurato in una connessione CJA). |
| [!UICONTROL Namespace] | Questa opzione è disponibile solo se non si utilizza lo spazio dei nomi ID principale. Gli spazi dei nomi delle identità sono un componente di [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html) che fungono da indicatori del contesto a cui si riferisce un&#39;identità. Se si specifica uno spazio dei nomi, CJA cercherà la mappa identità di ogni riga per questa chiave dello spazio dei nomi e utilizzerà l&#39;identità nello spazio dei nomi come ID persona per quella riga. Notate che, poiché CJA non è in grado di eseguire una scansione completa del set di dati di tutte le righe per determinare quali spazi di nomi sono effettivamente presenti, tutti i possibili spazi di nomi sono elencati nel menu a discesa. È necessario sapere quali spazi dei nomi sono specificati nei dati; non può essere rilevato automaticamente. |

### Casi periferici della mappa identità

Questa tabella mostra le due opzioni di configurazione per i casi periferici presenti e per la relativa gestione:

| Opzione | Nessun ID presente nella mappa identità | Nessun ID contrassegnato come primario | Più ID contrassegnati come principali | ID singolo contrassegnato come principale | Spazio dei nomi non valido con ID contrassegnato come principale |
|---|---|---|---|---|---|
| **Opzione &quot;Usa spazio nomi ID principale&quot; selezionata** | La riga viene eliminata da CJA. | La riga viene eliminata da CJA, in quanto non è specificato alcun ID primario. | Tutti gli ID contrassegnati come principali, sotto tutti gli spazi dei nomi, vengono estratti in un elenco. Sono quindi ordinati alfabeticamente; con questo nuovo ordinamento, il primo spazio nomi con il primo ID viene utilizzato come ID persona. | L’ID singolo contrassegnato come primario viene utilizzato come ID persona. | Anche se lo spazio dei nomi potrebbe non essere valido (non presente in AEP), CJA utilizzerà l&#39;ID primario nello spazio dei nomi come ID persona. |
| **Spazio dei nomi della mappa identità specifico selezionato** | La riga viene eliminata da CJA. | Tutti gli ID nello spazio nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. | Tutti gli ID nello spazio nomi selezionato vengono estratti in un elenco e il primo viene utilizzato come ID persona. Al momento della creazione della connessione è possibile selezionare solo uno spazio nomi valido, pertanto non è possibile utilizzare uno spazio nomi/ID non valido come ID persona. |

## Abilita connessione

![Abilita connessione](assets/create-connection2.png)

1. Per abilitare una connessione, definire le seguenti impostazioni:

   | Opzione | Descrizione |
   |---|---|
   | [!UICONTROL Name Connection] | Assegna alla connessione un nome descrittivo. Impossibile salvare la connessione senza un nome. |
   | [!UICONTROL Description] | Aggiungi ulteriori dettagli per distinguere questa connessione dalle altre. |
   | [!UICONTROL Datasets] | Set di dati inclusi in questa connessione. |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | Seleziona questa opzione se desideri stabilire una connessione continua in modo che tutti i nuovi batch di dati aggiunti ai set di dati in questa connessione passino automaticamente in [!UICONTROL Workspace]. |
   | [!UICONTROL Import all existing data] | Quando selezioni questa opzione e salvi la connessione verranno importati tutti i dati esistenti (storici) da [!DNL Experience Platform] per tutti i set di dati presenti in questa connessione. In futuro verranno importati automaticamente anche tutti i dati storici esistenti per eventuali nuovi set di dati aggiunti a questa connessione salvata. <br>**Ricorda che una volta salvata la connessione questa impostazione non può essere modificata.** |

   **Nota bene:**

   * Se la dimensione cumulativa dei dati storici per tutti i set di dati della connessione supera 1,5 miliardi di righe un messaggio di errore indicherà che non è possibile importare questa quantità di dati storici. Tuttavia, se aggiungessi un set di dati con 1 miliardo di righe di dati storici e importassi tali dati e una settimana dopo aggiungessi un altro set di dati della stessa dimensione e importassi i dati storici, ciò funzionerebbe.
   * Diamo priorità ai nuovi dati aggiunti a un set di dati nella connessione in modo che questi dati abbiano la latenza più bassa.
   * Eventuali dati di backfill (storici) vengono importati a una velocità più bassa.

1. Fai clic su **[!UICONTROL Save]**.

Il passaggio successivo nel flusso di lavoro consiste nel [creare una visualizzazione dati](/help/data-views/create-dataview.md).
