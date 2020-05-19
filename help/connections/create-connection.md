---
title: Creare una connessione
description: Descrive come creare una connessione a un set di dati di Platform in Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 204eb143d513b9b73fad020efabe6891a1253608
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 87%

---


# Creare una connessione

Una connessione consente di integrare i set di dati da [!DNL Adobe Experience Platform] a [!UICONTROL Workspace]. Per creare rapporti sui set di dati [!DNL Experience Platform] bisogna prima stabilire una connessione tra i set di dati in [!DNL Experience Platform] e [!UICONTROL Workspace].

Fai clic [qui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) per una panoramica video.

>[!IMPORTANT] È possibile combinare più set di dati [!DNL Experience Platform] in una singola connessione.

1. Vai a [https://analytics.adobe.com](https://analytics.adobe.com).

1. Fai clic sulla scheda **[!UICONTROL Connections]**.

1. Fai clic su **[!UICONTROL Create new connection]** in alto a destra.

   ![Crea connessione](assets/create-connection.png)

1. Scegliete una sandbox in Experience Platform che contenga i set di dati a cui desiderate creare una connessione.

   Adobe Experience Platform fornisce [sandbox](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) che dividono una singola istanza della piattaforma in ambienti virtuali separati per sviluppare e sviluppare applicazioni per esperienze digitali. Potete considerare le sandbox come &quot;silos di dati&quot; contenenti set di dati. Le sandbox vengono utilizzate per controllare l&#39;accesso ai set di dati. Non potete accedere ai dati tra le sandbox. Dopo aver selezionato la sandbox, la barra a sinistra mostra tutti i set di dati nella sandbox da cui è possibile eseguire il pulling.

1. Seleziona uno o più set di dati da richiamare in [!UICONTROL Customer Journey Analytics] e fai clic su **[!UICONTROL Add]**.

   Se sono presenti molti set di dati tra cui scegliere, puoi cercare quelli giusti utilizzando la barra di ricerca sopra l’elenco dei set di dati.

1. Successivamente, per ogni set di dati aggiunto alla connessione, [!UICONTROL Customer Journey Analytics] imposta automaticamente il tipo di set di dati in base ai dati in arrivo.

   Esistono 3 tipi diversi di set di dati: dati [!UICONTROL Event], dati [!UICONTROL Profile] e dati [!UICONTROL Lookup].

   | Tipo di set di dati | Descrizione | Timestamp | Schema | ID persona |
   |---|---|---|---|---|
   | [!UICONTROL Event] | Dati che rappresentano eventi nel tempo (ad esempio visite web, interazioni, transazioni, dati POS, dati dei sondaggi, dati ad impression, ecc.). Questi possono essere ad esempio tipici dati di click-stream, con un ID cliente o un ID cookie e un timestamp. Con i dati evento hai la flessibilità di scegliere quale ID usare come ID persona. | È impostato automaticamente sul campo timestamp predefinito dagli schemi basati sull’evento in [UICONTROL Experience Platform]. | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con il comportamento “Serie temporali”. Alcuni esempi includono “XDM Experience Event” o “XDM Decision Event”. | Puoi scegliere l’ID persona da includere. Ogni schema di set di dati definito in Experience Platform può avere un proprio set di una o più identità definite e associate a uno spazio dei nomi identità. Ognuno di questi può essere utilizzato come ID persona. Alcuni esempi includono Cookie ID (ID cookie), Stitched ID (ID di unione), User ID (ID utente), Tracking Code (Codice di tracciamento), ecc. |
   | [!UICONTROL Lookup] | Analogo a un file classificazioni. Questi dati vengono utilizzati per cercare i valori o le chiavi presenti nei dati evento o profilo. Ad esempio, puoi caricare dati di ricerca che mappano gli ID numerici nei dati evento ai nomi dei prodotti. | N/D | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con comportamento “Record”, ad eccezione della classe “Profilo individuale XDM”. | N/D |
   | [!UICONTROL Profile] | Analogo a [!UICONTROL Customer Attributes] per attributi non modificabili e non temporali. Dati applicati a visitatori, utenti o clienti nei dati [!UICONTROL Event]. Ad esempio, consente di caricare dati di gestione delle relazioni con i clienti riguardanti i tuoi clienti. | N/D | Qualsiasi schema predefinito o personalizzato basato sulla classe “Profilo individuale XDM”. | Puoi scegliere l’ID persona da includere. Ogni set di dati definito in [!DNL Experience Platform] presenta un proprio set di uno o più ID persona definiti, ad esempio Cookie ID (ID cookie), Stitched ID (ID di unione), User ID (ID utente), Tracking Code (Codice di tracciamento) e così via.<br>![ID persona](assets/person-id.png)**Nota:** se crei una connessione che include set di dati con ID diversi, il reporting lo rifletterà. Per unire in modo efficace i set di dati è necessario utilizzare lo stesso ID persona. |

1. Fate clic **[!UICONTROL Next]** per passare alla [!UICONTROL Create Connection] finestra di dialogo.

   ![Crea connessione](assets/create-connection2.png)

1. Nella finestra di dialogo [!UICONTROL Create Connection], definisci le seguenti impostazioni:

   | Campo | Descrizione |
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
