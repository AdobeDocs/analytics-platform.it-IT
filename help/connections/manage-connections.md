---
title: Come gestire le connessioni in Customer Journey Analytics
description: Descrive come gestire le connessioni ai set di dati Experienci Platform in Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 0b41cc80310c49bd1b0c73f1323f86c8b280e15f
workflow-type: tm+mt
source-wordcount: '2324'
ht-degree: 23%

---

# Gestire le connessioni

Una volta che [ha creato o modificato una o più connessioni](/help/connections/create-connection.md), puoi gestirli in **[!UICONTROL Connections]**. Le connessioni consentono di:

* Visualizza subito tutte le connessioni, inclusi il proprietario, la sandbox e quando sono state create e modificate.
* Modificare una connessione.
* Eliminare una connessione.
* Creare una visualizzazione dati a partire da una connessione.
* Visualizza tutti i set di dati in una connessione.
* Controlla lo stato dei set di dati della connessione e lo stato del processo di acquisizione. Ad esempio, quando sono disponibili i dati in modo da poter iniziare con il reporting e l’analisi in Analysis Workspace.
* Identifica eventuali discrepanze di dati dovute a configurazione errata. Vi mancano delle righe? In caso affermativo, quali righe mancano e perché? Hai configurato in modo errato le connessioni e causato la mancanza di dati nel Customer Journey Analytics?


Una tabella mostra tutte le connessioni disponibili. È possibile cercare rapidamente una connessione utilizzando il comando Cerca ![Ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) casella.

Nella tabella sono disponibili le seguenti colonne/icone.

| Colonna/Icona | Descrizione |
| --- | --- |
| [!UICONTROL Name] | Il nome descrittivo della connessione. Per visualizzare i dettagli della connessione, selezionare il nome del collegamento ipertestuale. Consulta [Dettagli di connessione](#connection-details). |
| ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Per visualizzare informazioni su [!UICONTROL Datasets included], [!UICONTROL Sandbox], [!UICONTROL Owner]e altro ancora, seleziona ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) accanto al nome della connessione.<p>Una finestra pop-up visualizza i dettagli. <p><img src="./assets/conn-info.png" alt="Visualizza informazioni di connessione" width="50%" /> |
| ![Visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | A [creare una visualizzazione dati](#create-a-data-view) per la connessione, seleziona ![Visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) . Questa icona viene visualizzata solo se alla connessione non è già associata alcuna visualizzazione dati. |
| ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) a: <p>![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Modifica](#edit-a-connection) una connessione.<p>![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Elimina](#delete-a-connection) una connessione.<p>![Visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Creare una nuova visualizzazione dati](#create-a-data-view). Utilizza questa opzione per creare visualizzazioni dati aggiuntive per la connessione. |
| [!UICONTROL Datasets] | Mostra uno o più collegamenti ai set di dati che fanno parte della connessione. Puoi selezionare il collegamento ipertestuale del set di dati per visualizzare il set di dati nella connessione. Se la connessione selezionata contiene più set di dati, seleziona **[!UICONTROL +*x *altro]**per visualizzare un **[!UICONTROL Datasets included]**pannello. Questo pannello mostra i collegamenti a tutti i set di dati e un’opzione per cercare un set di dati specifico che fa parte della connessione.<p><img src="./assets/datasets-included.png" alt="Risorse dati incluse" width="50%" /><p>Selezionando un nome per un set di dati si apre il set di dati nell’interfaccia utente di Experienci Platform in una nuova scheda. |
| [!UICONTROL Sandbox] | Mostra il [Sandbox di Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it) da cui questa connessione attinge i relativi set di dati. Questa sandbox è stata selezionata al momento della creazione della connessione. Non può essere modificato. |
| [!UICONTROL Owner] | Persona che ha creato la connessione. |
| [!UICONTROL Import new data] | Mostra lo stato dell’importazione di nuovi dati per i set di dati: <p><span style="color:green">●</span>   **[!UICONTROL _x _On]**per quanti set di dati sono configurati per l’importazione di nuovi dati, e&lt;/<p><span style="color:gray">●</span>   **[!UICONTROL _x disattivato_]** per quanti set di dati viene disattivata l’importazione di nuovi dati. |
| [!UICONTROL Date created] | Il timestamp in cui è stata creata la connessione. |
| [!UICONTROL Last modified] | Il timestamp dell’ultimo aggiornamento della connessione. |
| [!UICONTROL Backfill data] | Mostra lo stato dei dati di backfill tra set di dati.<p><span style="color:red">●</span>   **[!UICONTROL _x _backfill non riuscito]**per il numero di backfill non riusciti tra set di dati,<p><span style="color:orange">●</span>   **[!UICONTROL _x _elaborazione backfill]**per il numero di backfill di elaborazione tra set di dati,<p><span style="color:green">●</span>   **[!UICONTROL _x _backfill completati]**per il numero di backfill completati per i set di dati, e<p><span style="color:grey">●</span>   **[!UICONTROL _Disattivato_]** nel caso in cui non siano definiti backfill per i set di dati nella connessione. |

Puoi configurare le colonne da visualizzare utilizzando ![Impostazioni colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Questo mostra il **Personalizza tabella** consente di attivare/disattivare le colonne nella tabella.

## Modificare una connessione

Consente agli amministratori di modificare la connessione.

1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione
1. Seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** dal menu di scelta rapida.

In alternativa, è possibile:

1. Selezionare la riga di connessione.

1. Seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** dalla barra blu.

Durante la modifica di una connessione è possibile:

* Avviare e interrompere l&#39;importazione di nuovi dati.
* Rinominare una connessione.
* Aggiornare i set di dati.
* Rimuovere i set di dati dalle connessioni.

Consulta [Creare o modificare una connessione](create-connection.md) per ulteriori informazioni.


## Eliminare una connessione {#connections-delete}

Consente agli amministratori di eliminare la connessione.

1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione.
1. Seleziona ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]**.

In alternativa, è possibile:

1. Selezionare la riga di connessione.

1. Seleziona ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** dalla barra blu.

Quando si elimina una connessione, **[!UICONTROL Delete connection]** indica quali visualizzazioni dati vengono eliminate e quali progetti workspace sono interessati.

<img src="./assets/delete-connection.png" alt="Elimina connessione" width="50%" />

Seleziona **[!UICONTROL Continue]** per eliminare la connessione.

Consulta [Elimina implicazioni](/help/admin/cja-deletion.md) per ulteriori informazioni sulle implicazioni dell&#39;eliminazione di una connessione.


## Creare una visualizzazione dati

Consente agli amministratori di creare una visualizzazione dati per la connessione.

* Se alla connessione non è associata alcuna visualizzazione dati:

   1. Seleziona ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) accanto al nome della connessione.

* Se per la connessione sono già state create una o più visualizzazioni dati:

   1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione.
   1. Seleziona ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create new data view]**.

In alternativa, è possibile:

1. Selezionare la riga di connessione.

1. Seleziona ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** dalla barra dei pulsanti blu.

Consulta [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md) per ulteriori informazioni.

## Dettagli di connessione {#connection-detail}

Per visualizzare i dettagli di una connessione, selezionare un nome di connessione nella tabella connessioni.

![Finestra Tutti i set di dati con widget e impostazioni](assets/conn-details.png)

La schermata Dettagli connessioni fornisce una visualizzazione dettagliata dello stato di una connessione. È possibile:

* Controllare lo stato dei set di dati della connessione e del processo di acquisizione.
* Identificare i problemi di configurazione che possono causare record ignorati o eliminati.
* Vedere quando i dati sono disponibili per il reporting.

>[!IMPORTANT]
>
>Eventuali dati acquisiti prima del 13 agosto 2021 non vengono riflessi in questo [!UICONTROL Connections] .

### Dettagli di connessione

| Interfaccia utente | Descrizione |
| --- | --- |
| ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Edit Connection] | Per modificare i dettagli di una connessione, seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit Connection]** . Consulta [Creare o modificare una connessione](create-connection.md) per ulteriori informazioni. |
| Selettore set di dati | Consente di scegliere uno o tutti i set di dati della connessione. Non è possibile selezionare più set di dati. Predefinito su [!UICONTROL All datasets]. |
| Selettore Calendario/Intervallo date | L’intervallo di date indica quando hai aggiunto dati alla connessione. Sono inclusi tutti i predefiniti calendario standard. Puoi personalizzare l’intervallo di date, ma nell’elenco a discesa non viene visualizzato alcun intervallo di date personalizzato. |
| [!UICONTROL Records of event data available] | Rappresenta il numero totale di righe del set di dati evento disponibili per il reporting, **per l’intera connessione**. Questo conteggio è indipendente da qualsiasi impostazione del calendario. Il conteggio cambia se selezioni un set di dati dal selettore o selezionando un set di dati nella tabella. Una volta aggiunti i dati, vi è una latenza di 1-2 ore per far sì che vengano visualizzati nel reporting. |
| [!UICONTROL Metrics] | Riepiloga i record evento aggiunti/saltati/eliminati e il numero di batch aggiunti, **per il set di dati e l’intervallo di date selezionati**. |
| [!UICONTROL Records added] | Indica quante righe sono state aggiunte nel periodo di tempo selezionato, **per il set di dati e l’intervallo di date selezionati**. Aggiornato ogni 10 minuti. <p>**Nota**: dati per **[!UICONTROL Records added]** include solo i dati evento al momento, non i dati di profilo o di ricerca. |
| [!UICONTROL Records skipped] | Indica quante righe sono state saltate nel periodo di tempo selezionato, **per il set di dati e l’intervallo di date selezionati**. I motivi per cui i record vengono ignorati includono: marche temporali mancanti, ID persona mancante o non valido e così via. Aggiornato ogni 10 minuti.<p>ID persona non validi (ad esempio “non definito” o “00000000”, o qualsiasi combinazione di numeri e lettere in un [!UICONTROL Person ID] che appare in un evento più di 1 milione di volte in un dato mese) non possono essere attribuiti a un utente o persona specifica. Non possono essere acquisiti nel sistema e generano acquisizione e reporting soggetti a errori. Per correggere gli ID persona non validi, hai 3 possibilità:<ul><li>Utilizzare [Stitching](/help/stitching/overview.md) per popolare gli ID utente non definiti o composti solo da zeri con ID utente validi.</li><li>Rimuovi l’ID utente, che verrà quindi ignorato durante l’acquisizione (da preferire agli ID utente non validi o agli ID composti solo da zeri).</li><li>Correggi eventuali ID utente non validi nel sistema prima di acquisire i dati.</li></ul><p>**Nota**: dati per **[!UICONTROL Records skipped]** include solo i dati evento al momento, non i dati di profilo o di ricerca. |
| [!UICONTROL Records] eliminato | Indica quante righe sono state eliminate nel periodo di tempo selezionato, **per il set di dati e l’intervallo di date selezionati**. Per esempio, qualcuno potrebbe aver eliminato un set di dati in Experience Platform. Aggiornato ogni 10 minuti. <p>**Nota**: dati per **[!UICONTROL Records deleted]** include solo i dati evento al momento, non i dati di profilo o di ricerca. |
| ![Ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Cerca nome o ID set di dati_ | Campo di ricerca del set di dati. Puoi cercare la tabella dei set di dati per nome o [!UICONTROL Dataset ID]. |
| [!UICONTROL Datasets table] | Mostra i set di dati che fanno parte della connessione. |
| [!UICONTROL Datasets] | Mostra il nome del set di dati che fa parte della connessione. Puoi selezionare il collegamento ipertestuale per aprire il set di dati nell’interfaccia utente di Experienci Platform in una nuova scheda. Puoi selezionare la riga o la casella di controllo per visualizzare i dettagli solo per il set di dati selezionato. |
| [!UICONTROL Dataset ID] | Generato automaticamente da Experienci Platform. |
| [!UICONTROL Records added] | Il numero di record/righe del set di dati aggiunti a una connessione durante l’intervallo di tempo selezionato. |
| [!UICONTROL Records skipped] | Il numero di record/righe del set di dati ignorati durante il trasferimento di dati per una connessione durante l’intervallo di tempo selezionato. |
| [!UICONTROL Records deleted] | Numero di record/righe di set di dati rimossi da una connessione durante l’intervallo di tempo selezionato. |
| [!UICONTROL Batches added] | Numero di batch di set di dati aggiunti a una connessione. |
| [!UICONTROL Last added] | La marca temporale dell’ultimo batch del set di dati aggiunto a una connessione. |
| [!UICONTROL Data source type] | Tipo di origine del set di dati. Quando si crea una connessione, è possibile definire il tipo di origine. |
| [!UICONTROL Dataset type] | Tipo di set di dati per questo set di dati. Il tipo può essere [!UICONTROL Event], [!UICONTROL Lookup], o [!UICONTROL Profile]. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it#configure-dataset) |
| Schema | Schema di Experience Platform su cui si basa il set di dati. |
| [!UICONTROL Import new data] | Mostra lo stato dell’importazione di nuovi dati per il set di dati: <p><span style="color:green">●</span>   **[!UICONTROL _x _On]**se il set di dati è configurato per l’importazione di nuovi dati e<p><span style="color:gray">●</span>   **[!UICONTROL _x disattivato_]** se il set di dati è configurato per non importare nuove importazioni di dati. |
| [!UICONTROL Backfill data] | Mostra lo stato dei dati di backfill per il set di dati.<p><span style="color:red">●</span>   **[!UICONTROL _x _backfill non riuscito]**per il numero di backfill non riusciti,<p><span style="color:orange">●</span>   **[!UICONTROL _x _elaborazione backfill]**per il numero di backfill processing,<p><span style="color:green">●</span>   **[!UICONTROL _x _backfill completati]**per il numero di backfill completati e<p><span style="color:grey">●</span>   **[!UICONTROL _Disattivato_]** nel caso in cui non sia configurato alcun backfill. |

### Pannello Connessione

Quando nella tabella dei set di dati non è selezionato alcun set di dati, un pannello sul lato destro dell’interfaccia Connessioni mostra le opzioni e i dettagli di connessione.

| Opzioni / Dettagli | Descrizione |
| --- | --- |
| ![Aggiorna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Refresh] | Per aggiornare la connessione e consentire la visualizzazione dei record aggiunti di recente, selezionare ![Aggiorna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Refresh]**. |
| ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** | [Elimina](#delete-a-connection) questa connessione. |
| ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** | [Creare una visualizzazione dati](#create-a-data-view) in base a questa connessione. Consulta [Visualizzazioni dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=it) per ulteriori informazioni. |
| [!UICONTROL Connection name] | Mostra il nome descrittivo della connessione. |
| [!UICONTROL Connection description] | Mostra una descrizione più dettagliata che descrive lo scopo della connessione. |
| [!UICONTROL Sandbox] | Il [Sandbox di Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it) da cui questa connessione attinge i relativi set di dati. Questa sandbox è stata selezionata al momento della creazione della connessione. Non può essere modificato. |
| [!UICONTROL Connection ID] | Questo ID viene generato in Experienci Platform. È possibile utilizzare ![Copia](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) per copiare l&#39;ID. |
| [!UICONTROL Data views using connection] | Elenca tutte le visualizzazioni dati che utilizzano questa connessione. |
| [!UICONTROL Import new data] | Mostra lo stato dell’importazione di nuovi dati per i set di dati: <p><span style="color:green">●</span>   **[!UICONTROL _x _On]**per quanti set di dati sono configurati per l’importazione di nuovi dati e<p><span style="color:gray">●</span>   **[!UICONTROL _x disattivato_]** per quanti set di dati viene disattivata l’importazione di nuovi dati. |
| [!UICONTROL Backfill data] | Mostra lo stato dei dati di retrocompilazione per i set di dati.<p><span style="color:red">●</span>   **[!UICONTROL _x _backfill non riuscito]**per il numero di backfill non riusciti tra set di dati,<p><span style="color:orange">●</span>   **[!UICONTROL _x _elaborazione backfill]**per il numero di backfill di elaborazione tra set di dati,<p><span style="color:green">●</span>   **[!UICONTROL _x _backfill completati]**per il numero di backfill completati per i set di dati, e<p><span style="color:grey">●</span>   **[!UICONTROL _Disattivato_]** nel caso in cui non siano definiti backfill per i set di dati nella connessione. |
| [!UICONTROL Created by] | Mostra il nome della persona che ha creato la connessione. |
| [!UICONTROL Last modified] | Mostra la marca temporale dell’ultima modifica apportata alla connessione. |
| [!UICONTROL Last modified by] | Mostra l’ultimo utente che ha modificato la connessione. |

### Pannello Set di dati

Quando un set di dati viene selezionato nella tabella dei set di dati, in un pannello sul lato destro dell’interfaccia Connessioni vengono visualizzati i dettagli del set di dati selezionato.

| Dettagli | Descrizione |
| --- | --- |
| [!UICONTROL Person ID] | Mostra un’identità definita nello schema del set di dati in Experience Platform. Questo è l’ID persona selezionato durante la creazione della connessione. Se crei una connessione che include set di dati con ID diversi, il reporting lo riflette. Per unire i set di dati, è necessario utilizzare lo stesso ID persona in tutti i set di dati. |
| [!UICONTROL Key] | Mostra la chiave specificata per un set di dati di ricerca. |
| [!UICONTROL Matching Key] | Mostra la chiave corrispondente specificata per un set di dati di ricerca. |
| [!UICONTROL Timestamp] | Mostra la marca temporale definita per un set di dati evento. |
| [!UICONTROL Records available] | Rappresenta il numero totale di righe acquisite per questo set di dati, per il particolare periodo di tempo selezionato nel calendario. Non esiste alcuna latenza in termini di visualizzazione dei dati nel reporting, una volta aggiunti. Tuttavia, quando crei una connessione nuova, ci sarà [latenza](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=it#3.-getting-data-into-customer-journey-analytics). |
| [!UICONTROL Records added] | Indica quante righe sono state aggiunte nel periodo di tempo selezionato. <p>**Nota**: dati per **[!UICONTROL Records added]** include solo i dati evento al momento, non i dati di profilo o di ricerca. |
| [!UICONTROL Records deleted] | Indica quanti record sono stati eliminati durante il periodo di tempo selezionato. <p>**Nota**: dati per **[!UICONTROL Records deleted]** include solo i dati evento al momento, non i dati di profilo o di ricerca. |
| [!UICONTROL Batches added] | Indica quanti batch di dati sono stati aggiunti al set di dati. |
| [!UICONTROL Records skipped] | Indica quante righe sono state saltate durante l’acquisizione nel periodo di tempo selezionato.<p>I motivi per cui i record vengono ignorati includono: marche temporali mancanti, ID persona mancante o non valido e così via. Aggiornato ogni 10 minuti.<p>ID persona non validi (ad esempio “non definito” o “00000000”, o qualsiasi combinazione di numeri e lettere in un [!UICONTROL Person ID] che appare in un evento più di 1 milione di volte in un dato mese) non possono essere attribuiti a un utente o persona specifica. Non possono essere acquisiti nel sistema e generano acquisizione e reporting soggetti a errori. Per correggere gli ID persona non validi, hai 3 possibilità:<ul><li>Utilizzare [Stitching](/help/stitching/overview.md) per popolare gli ID utente non definiti o composti solo da zeri con ID utente validi.</li><li>Rimuovi l’ID utente, che viene quindi ignorato durante l’acquisizione (da preferire agli ID utente non validi o agli ID composti solo da zeri).</li><li>Correggi eventuali ID utente non validi nel sistema prima di acquisire i dati.</li></ul><p>**Nota**: dati per **[!UICONTROL Records skipped]** include solo i dati evento al momento, non i dati di profilo o di ricerca. |
| [!UICONTROL Last added] | Indica quando è stato aggiunto l’ultimo batch. |
| [!UICONTROL Import new data] | Mostra lo stato dell’importazione di nuovi dati per il set di dati: <p><span style="color:green">●</span>   **[!UICONTROL _x _On]**se il set di dati è configurato per l’importazione di nuovi dati e<p><span style="color:gray">●</span>   **[!UICONTROL _x disattivato_]** se il set di dati è configurato per non importare nuove importazioni di dati. |
| [!UICONTROL Backfill data] | Mostra lo stato dei dati di backfill per il set di dati.<p><span style="color:red">●</span>   **[!UICONTROL _x _backfill non riuscito]**per il numero di backfill non riusciti,<p><span style="color:orange">●</span>   **[!UICONTROL _x _elaborazione backfill]**per il numero di backfill processing,<p><span style="color:green">●</span>   **[!UICONTROL _x _backfill completati]**per il numero di backfill completati e<p><span style="color:grey">●</span>   **[!UICONTROL _Disattivato_]** nel caso in cui non sia configurato alcun backfill.<p>Per visualizzare una finestra di dialogo con una panoramica dei precedenti backfill per il set di dati, seleziona <img src="./assets/pastbackfill.svg" alt="Backfill passati" width="2%" /> **[!UICONTROL Past backfills]**. |
| [!UICONTROL Data source type] | Tipo di origine dati definito durante l’aggiunta di un set di dati alla connessione. |
| [!UICONTROL Dataset type] | [!UICONTROL Event], [!UICONTROL Lookup]oppure [!UICONTROL Profile]. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it#configure-dataset) |
| [!UICONTROL Schema] | Mostra lo schema di Experience Platform su cui si basa questo set di dati. |
| [!UICONTROL Dataset ID] | Questo ID del set di dati viene generato in Experienci Platform. |


>[!MORELIKETHIS]
>
>[Visualizzare, risolvere i problemi e modificare le impostazioni di connessione](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html?lang=en) esercitazione.
