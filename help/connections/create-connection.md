---
title: Creazione di una connessione
description: Descrive come creare una connessione a un set di dati della piattaforma in Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 41029fb428308a247df65072af4e419a90098a15

---


# Creazione di una connessione

Una connessione consente di integrare i set di dati di Adobe Experience Platform in Workspace. Per generare rapporti sui set di dati della piattaforma, è innanzitutto necessario stabilire una connessione tra i set di dati in Piattaforma e Workspace.

Fate clic [qui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) per una panoramica video.

>[!IMPORTANT] È possibile combinare più set di dati della piattaforma in una singola connessione.

1. Andate a [https://analytics.adobe.com](https://analytics.adobe.com).

1. Fate clic sulla **[!UICONTROL Connections]** scheda.

1. Fate clic **[!UICONTROL Create new connection]** in alto a destra.

![Crea connessione](assets/create-connection.png)

1. Nella barra a sinistra sono visualizzati tutti i set di dati della piattaforma da cui è possibile eseguire il pulling. Selezionate uno o più set di dati da inserire in Analisi percorso cliente e fate clic su **[!UICONTROL Add]**. Se si dispone di molti set di dati tra cui scegliere, è possibile cercare quelli giusti utilizzando la barra di ricerca sopra l&#39;elenco dei set di dati.

1. Successivamente, per ogni set di dati aggiunto alla connessione, Analisi percorso cliente imposta automaticamente il tipo di set di dati in base ai dati in arrivo. Esistono 3 tipi di set di dati diversi: Dati evento, dati profilo e dati di ricerca.

   | Tipo set di dati | Descrizione | Timestamp | Schema | ID persona |
   |---|---|---|---|---|
   | Evento | Dati che rappresentano eventi nel tempo (ad esempio visite Web, interazioni, transazioni, dati POS, dati sondaggio, dati ad impression, ecc.). Si tratta di dati tipici del clickstream, con un ID cliente o un ID cookie e una marca temporale. Con i dati dell’evento, vi consentiamo di utilizzare l’ID desiderato. | Sarà impostato su Timestamp. | Schema piattaforma su cui si basa questo tipo di set di dati. | N/D |
   | Ricerca | Analogo a un file Classificazioni. Questi dati vengono utilizzati per cercare i valori o le chiavi presenti nei dati dell&#39;evento o del profilo. Ad esempio, potete caricare dati di ricerca che mappano ID numerici nei dati dell&#39;evento ai nomi di prodotto. | N/D | Schema piattaforma su cui si basa questo tipo di set di dati. | N/D |
   | Profilo | Analogo agli attributi del cliente - per attributi non modificabili e non temporali. Dati applicati ai visitatori, utenti o clienti nei dati dell’evento. Ad esempio, consente di caricare dati CRM sui clienti. | N/D | Schema piattaforma su cui si basa questo tipo di set di dati. | Puoi scegliere l’ID persona da includere. Per ogni set di dati definito in Adobe Experience Platform è definito un proprio set di uno o più ID persona, ad esempio Cookie ID, Stitched ID, User ID, Tracking Code e così via.<br>![Persona](assets/person-id.png)**IDNote **: Se crei una connessione che include set di dati con ID diversi, il reporting lo rifletterà. Per unire realmente i set di dati, è necessario utilizzare lo stesso ID persona. |

1. Fai clic su **[!UICONTROL Next]**.

1. Nella finestra di dialogo Crea connessione, definite le seguenti impostazioni:

   | Campo | Descrizione |
   |---|---|
   | Nome | Assegnare alla connessione un nome descrittivo. Impossibile salvare la connessione senza un nome. |
   | Descrizione | Aggiungete ulteriori dettagli per distinguere questa connessione dagli altri. |
   | Dimensione | La dimensione collettiva dei set di dati nella connessione dati. |
   | Set di dati | Set di dati inclusi in questa connessione. |
   | Streaming dei dati | Per iniziare lo streaming dei dati per questa connessione, abilita lo streaming dei dati. Quando lo streaming di dati è abilitato per questa connessione, l&#39;account viene addebitato per la quantità di dati in streaming della connessione. (È inoltre possibile abilitare lo streaming di dati in Gestione connessioni.) |

1. Fai clic su **[!UICONTROL Save]**. Quando si salva questa connessione, si verificano due cose:

   * È possibile estrarre tutti i dati storici da Piattaforma per tutti i set di dati in questa connessione.
   * Se hai attivato lo streaming, stabilisci una connessione continua, in modo che tutti i nuovi dati che vengono aggiunti ai set di dati in questa connessione vengano automaticamente inseriti in Workspace.

Il passaggio successivo nel flusso di lavoro consiste nel [creare una visualizzazione](/help/data-views/create-dataview.md)dati.
