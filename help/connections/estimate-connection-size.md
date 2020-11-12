---
title: Stima dimensione connessione
description: Report sull'utilizzo corrente del Customer Journey Analytics (a scopo di fatturazione)
translation-type: tm+mt
source-git-commit: 27b3b1d9e6042f4c61cd1d5bb9d574cc268c3460
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 0%

---


# Stima dimensione connessione

Potrebbe essere necessario sapere quante righe di dati si hanno attualmente in [!UICONTROL Customer Journey Analytics]. Lo scopo di questo argomento è di mostrare come eseguire un rapporto sull&#39;utilizzo corrente di [!UICONTROL Customer Journey Analytics].

1. In [!UICONTROL Customer Journey Analytics], fare clic sulla scheda **[!UICONTROL Connections]**.
1. Nella schermata [!UICONTROL Edit connection], selezionate una connessione per la quale desiderate determinare le dimensioni di utilizzo/connessione.

   ![Modifica connessione](assets/edit-connection.png)

1. Selezionate un set di dati che fa parte della connessione dalla barra a sinistra. In questo caso, si tratta del dataset &quot;B2B Impression&quot;.

   ![dataset](assets/dataset.png)

1. Fate clic sull’icona blu (i) (info) accanto al nome. Noterai che il DataSet ha 3,8 k righe/eventi. Inoltre, per il numero esatto di righe, fate clic su **[!UICONTROL Edit in Experience Platform]** sotto la tabella di anteprima. Questo reindirizzerà l&#39;utente ai set di dati in [!UICONTROL Adobe Experience Platform].

   ![Informazioni sui set di dati AEP](assets/data-size.png)

1. Notate che **[!UICONTROL Total records]** per questo set di dati equivale a 3,83k record, con la dimensione dei dati pari a 388,59 KB.

1. Ripetere i passaggi da 1 a 5 per altri set di dati nella connessione e aggiungere il numero di record/righe. Il numero finale aggregato sarà la metrica di utilizzo della connessione, ossia il numero di righe dei set di dati della connessione che si desidera acquisire da [!UICONTROL Adobe Experience Platform].

## Determinare il numero di righe ingerite

Il numero di eventi effettivamente ingeriti in CJA dipende dalle impostazioni di configurazione della connessione. Inoltre, se hai selezionato l&#39;ID persona errato o se questo ID non è disponibile per alcune righe nei set di dati, [!UICONTROL Customer Journey Analytics] ignorerà tali righe. Per determinare le righe effettive degli eventi ingeriti, effettuate le seguenti operazioni:

1. Una volta salvata la connessione, create una visualizzazione dati della stessa connessione senza filtri.
1. Crea un progetto Workspace e seleziona la visualizzazione dati corretta. Crea una tabella a forma libera e trascina e rilascia la metrica **[!UICONTROL Events]** con una dimensione **[!UICONTROL Year]**. Scegli un intervallo di date sufficientemente ampio dal calendario di selezione delle date per racchiudere tutti i dati nella connessione. Questo ti consentirà di vedere il numero di eventi in corso di assimilazione in [!UICONTROL Customer Journey Analytics].

   ![Progetto Workspace](assets/event-number.png)

   >[!NOTE]
   >
   >Questo consente di visualizzare il numero di eventi che vengono acquisiti dal set di dati degli eventi. Non include i set di dati di profilo e tipo di ricerca. Seguire i passaggi da 1 a 3 per i set di dati di profilo e di ricerca e aggiungere i numeri per ottenere il numero totale di righe per la connessione.

## Differenze di diagnostica

In alcuni casi, si può notare che il numero totale di eventi ingeriti dalla connessione è diverso dal numero di righe nel set di dati in AEP. In questo caso il set di dati &quot;Impression B2B&quot; ha 7650 righe, ma il set di dati contiene 3830 righe in AEP. Ci sono diversi motivi per cui possono verificarsi discrepanze, e i seguenti passi possono essere fatti per diagnosticare:

1. Suddividere questa dimensione per **[!UICONTROL Platform Dataset ID]** e si noteranno due set di dati con la stessa dimensione ma diversa **[!UICONTROL Platform Dataset IDs]**. Ogni set di dati ha 3825 record. Ciò significa che [!UICONTROL Customer Journey Analytics] 5 record ignorati a causa di ID di persona mancanti o marche temporali mancanti:

   ![guasto](assets/data-size2.png)

1. Inoltre, se archiviiamo [!UICONTROL Adobe Experience Platform], non esiste alcun dataset con ID &quot;5f21c12b732044194bffc1d0&quot;, quindi qualcuno ha eliminato questo particolare set di dati da [!UICONTROL Adobe Experience Platform] al momento della creazione della connessione iniziale. Successivamente è stato aggiunto di nuovo a [!UICONTROL Customer Journey Analytics], ma un [!UICONTROL Platform Dataset ID] diverso è stato generato da [!UICONTROL Adobe Experience Platform].

   Ulteriori informazioni sulle [implicazioni del dataset e l&#39;eliminazione della connessione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components) in [!UICONTROL Customer Journey Analytics] e [!UICONTROL Adobe Experience Platform].
