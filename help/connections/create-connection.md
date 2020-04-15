---
title: Creazione di una connessione
description: Descrive come creare una connessione a un set di dati della piattaforma in Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: f17994c7d6812480102b9dc5fdbfc4609d2d1012

---


# Creazione di una connessione

Una connessione consente di integrare i set di dati [!DNL Adobe Experience Platform] in [!UICONTROL Workspace]. Per creare rapporti sui [!DNL Experience Platform] set di dati, è innanzitutto necessario stabilire una connessione tra i set di dati in [!DNL Experience Platform] e [!UICONTROL Workspace].

Fate clic [qui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) per una panoramica video.

>[!IMPORTANT] È possibile combinare più [!DNL Experience Platform] set di dati in una singola connessione.

1. Andate a [https://analytics.adobe.com](https://analytics.adobe.com).

1. Fate clic sulla **[!UICONTROL Connections]** scheda.

1. Fate clic **[!UICONTROL Create new connection]** in alto a destra.

![Crea connessione](assets/create-connection.png)

1. Nella barra a sinistra sono visualizzati tutti i set di dati [!DNL Experience Platform] da cui è possibile eseguire il pulling. Selezionare uno o più set di dati in cui si desidera eseguire il pulling [!UICONTROL Customer Journey Analytics] e fare clic su **[!UICONTROL Add]**. Se si dispone di molti set di dati tra cui scegliere, è possibile cercare quelli giusti utilizzando la barra di ricerca sopra l&#39;elenco dei set di dati.

1. Successivamente, per ogni set di dati aggiunto alla connessione, imposta [!UICONTROL Customer Journey Analytics] automaticamente il tipo di set di dati in base ai dati in arrivo. Esistono 3 tipi di set di dati diversi: [!UICONTROL Event] dati, [!UICONTROL Profile] dati e [!UICONTROL Lookup] dati.

   | Tipo set di dati | Descrizione | Timestamp | Schema | ID persona |
   |---|---|---|---|---|
   | [!UICONTROL Event] | Dati che rappresentano eventi nel tempo (ad esempio visite Web, interazioni, transazioni, dati POS, dati sondaggio, dati ad impression, ecc.). Ad esempio, questi possono essere dati clickstream tipici, con un ID cliente o un ID cookie e una marca temporale. Con i dati Evento, hai la flessibilità di utilizzare l’ID come ID persona. | È impostato automaticamente sul campo di marca temporale predefinito dagli schemi basati sull&#39;evento in [UICONTROL Experience Platform]. | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con il comportamento &quot;Serie temporali&quot;. Alcuni esempi includono &quot;XDM Experience Event&quot; o &quot;XDM Decision Event&quot;. | Puoi scegliere l’ID persona da includere. Ogni schema di set di dati definito in Experience Platform può avere un proprio set di una o più identità definite e associate a uno Spazio dei nomi identità. Ognuno di questi può essere utilizzato come ID persona. Alcuni esempi includono ID cookie, ID uniti, ID utente, codice di tracciamento, ecc. |
   | [!UICONTROL Lookup] | Analogo a un file Classificazioni. Questi dati vengono utilizzati per cercare i valori o le chiavi presenti nei dati dell&#39;evento o del profilo. Ad esempio, potete caricare dati di ricerca che mappano ID numerici nei dati dell&#39;evento ai nomi dei prodotti. | N/D | Qualsiasi schema predefinito o personalizzato basato su una classe XDM con comportamento &quot;Record&quot;, ad eccezione della classe &quot;Profilo singolo XDM&quot;. | N/D |
   | [!UICONTROL Profile] | Analogo a [!UICONTROL Customer Attributes] - per attributi non modificabili e non temporali. Dati applicati ai visitatori, utenti o clienti nei [!UICONTROL Event] dati. Ad esempio, consente di caricare dati CRM sui clienti. | N/D | Qualsiasi schema predefinito o personalizzato basato sulla classe &quot;Profilo singolo XDM&quot;. | Puoi scegliere l’ID persona da includere. Ogni set di dati definito in [!DNL Experience Platform] presenta un proprio set di uno o più ID persona, ad esempio ID cookie, ID uniti, ID utente, codice di tracciamento e così via.<br>![Persona](assets/person-id.png)**IDNote **: Se crei una connessione che include set di dati con ID diversi, il reporting lo rifletterà. Per unire realmente i set di dati, è necessario utilizzare lo stesso ID persona. |

1. Facendo clic **[!UICONTROL Next]** si passa alla [!UICONTROL Create Connection] finestra di dialogo.

   ![Crea connessione](assets/create-connection2.png)

1. Nella [!UICONTROL Create Connection] finestra di dialogo, definite le seguenti impostazioni:

   | Field | Descrizione |
   |---|---|
   | [!UICONTROL Name Connection] | Assegnare alla connessione un nome descrittivo. Impossibile salvare la connessione senza un nome. |
   | [!UICONTROL Description] | Aggiungete ulteriori dettagli per distinguere questa connessione dagli altri. |
   | [!UICONTROL Datasets] | Set di dati inclusi in questa connessione. |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | Selezionare questa opzione se si desidera stabilire una connessione continua, in modo che tutti i nuovi batch di dati che vengono aggiunti ai set di dati in questa connessione possano scorrere automaticamente in [!UICONTROL Workspace]. |
   | [!UICONTROL Import all existing data] | Quando si seleziona questa opzione e si salva la connessione, verranno importati tutti i dati esistenti (storici) di [!DNL Experience Platform] per tutti i set di dati che si trovano in questa connessione. In futuro, verranno importati automaticamente anche tutti i dati storici esistenti per eventuali nuovi dataset aggiunti a questa connessione salvata. <br>**Una volta salvata la connessione, questa impostazione non può essere modificata.** |

   **Nota bene:**

   * Se la dimensione cumulativa dei dati storici per tutti i set di dati della connessione supera 1,5 miliardi di righe, un messaggio di errore indica che non è possibile importare la quantità di dati storici. Tuttavia, se si aggiungesse un dataset con 1 Miliardo di righe di dati storici e si importassero tali dati, e una settimana dopo, si aggiungesse un altro dataset della stessa dimensione e si importassero i dati storici, ciò funzionerebbe.
   * Assegniamo priorità ai nuovi dati aggiunti a un dataset nella connessione, in modo che questi dati abbiano la latenza più bassa.
   * Eventuali dati di backfill (storico) vengono importati a una velocità più bassa.

1. Fai clic su **[!UICONTROL Save]**.

Il passaggio successivo nel flusso di lavoro consiste nel [creare una visualizzazione](/help/data-views/create-dataview.md)dati.
