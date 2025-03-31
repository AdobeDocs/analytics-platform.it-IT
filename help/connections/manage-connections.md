---
title: Come gestire le connessioni in Customer Journey Analytics
description: Descrive come gestire le connessioni ai set di dati di Experience Platform in Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 7f2f2fc92c188c4cdfba7d87b7b64458daf2f0a6
workflow-type: tm+mt
source-wordcount: '3913'
ht-degree: 23%

---

# Gestire le connessioni

Dopo aver creato o modificato [ una o più connessioni](/help/connections/create-connection.md), puoi gestirle in **[!UICONTROL Connections]**. Le connessioni consentono di:

* Visualizza subito tutte le connessioni, inclusi il proprietario, la sandbox e quando sono state create e modificate.
* Modificare una connessione.
* Eliminare una connessione.
* Creare una visualizzazione dati a partire da una connessione.
* Visualizza tutti i set di dati in una connessione.
* Controlla lo stato dei set di dati della connessione e lo stato del processo di acquisizione. Ad esempio, quando sono disponibili i dati in modo da poter iniziare con il reporting e l’analisi in Analysis Workspace.
* Identifica eventuali discrepanze di dati dovute a configurazione errata. Vi mancano delle righe? In caso affermativo, quali righe mancano e perché? Hai configurato in modo errato le connessioni e causato la mancanza di dati in Customer Journey Analytics?
* Ottieni informazioni sull’utilizzo delle righe acquisite e segnalabili in tutte le connessioni.

[!UICONTROL Connections] ha due interfacce: [[!UICONTROL List]](#list) e [[!UICONTROL Usage]](#usage).


## Elenco

L&#39;interfaccia [!UICONTROL List] è l&#39;interfaccia predefinita per Connessioni. Se non è selezionata, selezionare la scheda **[!UICONTROL List]** per accedere all&#39;interfaccia.

![visualizzazione elenco](assets/list-view.png)

L&#39;interfaccia [!UICONTROL List] mostra una tabella di tutte le connessioni disponibili. Puoi cercare rapidamente una connessione utilizzando la casella Cerca ![Ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

Nella tabella sono disponibili le colonne o le icone seguenti.

| Colonna o icona | Descrizione |
| --- | --- |
| [!UICONTROL Name] | Il nome descrittivo della connessione. Per visualizzare i dettagli della connessione, selezionare il nome del collegamento ipertestuale. Vedi [Dettagli connessione](#connection-details). |
| ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Per visualizzare informazioni su [!UICONTROL Datasets included], [!UICONTROL Sandbox], [!UICONTROL Owner] e altro, seleziona ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) accanto al nome della connessione.<p>Una finestra pop-up visualizza i dettagli. <p><img src="./assets/conn-info.png" alt="Visualizza informazioni di connessione" width="400"/> |
| ![Visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Per [creare una visualizzazione dati](#create-a-data-view) per la connessione, selezionare ![Visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). Questa icona viene visualizzata solo se alla connessione non è già associata alcuna visualizzazione dati. |
| ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) per: <p>![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Modifica](#edit-a-connection) una connessione.<p>![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Elimina](#delete-a-connection) una connessione.<p>![Visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Crea nuova visualizzazione dati](#create-a-data-view). Per creare visualizzazioni dati aggiuntive per la connessione. |
| [!UICONTROL Datasets] | Uno o più collegamenti ai set di dati che fanno parte della connessione. Puoi selezionare il collegamento ipertestuale del set di dati per visualizzare il set di dati nella connessione. Se la connessione selezionata contiene altri set di dati, selezionare **[!UICONTROL +*x *ulteriori]**per visualizzare un pannello **[!UICONTROL Datasets included]**. Questo pannello mostra i collegamenti a tutti i set di dati e un’opzione per cercare un set di dati specifico che fa parte della connessione.<p><img src="./assets/datasets-included.png" alt="Risorse dati incluse" width="400"/><p>Selezionando un nome per un set di dati si apre il set di dati nell’interfaccia utente di Experience Platform in una nuova scheda. |
| [!UICONTROL Sandbox] | La sandbox [Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/sandbox/home) da cui questa connessione attinge i relativi set di dati. Questa sandbox è stata selezionata al momento della creazione della connessione. Non può essere modificato. |
| [!UICONTROL Owner] | Persona che ha creato la connessione. |
| [!UICONTROL Import new data] | Stato dell’importazione di nuovi dati per i set di dati: <p>![Stato verde](assets/status-green.svg))    **[!UICONTROL _x _Il]**per i set di dati configurati per l&#39;importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x disattivato_]** per i set di dati non configurati per l&#39;importazione di nuovi dati. |
| [!UICONTROL Date created] | Il timestamp in cui è stata creata la connessione. |
| [!UICONTROL Last modified] | Il timestamp dell’ultimo aggiornamento della connessione. |
| [!UICONTROL Backfill data] | Lo stato dei dati di backfill tra set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _backfill non riusciti]**per il numero di backfill non riusciti tra set di dati,<p>![Stato arancione](assets/status-orange.svg)   **[!UICONTROL _x _backfill in elaborazione]**per il numero di backfill in elaborazione tra set di dati,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _backfill completati]**per il numero di backfill completati per i set di dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** nel caso in cui non siano definiti backfill per i set di dati nella connessione. |

Per configurare le colonne da visualizzare, selezionare ![Impostazioni colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Viene visualizzata la finestra di dialogo **Personalizza tabella** che consente di attivare o disattivare le colonne nella tabella.

### Modificare una connessione

1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione
1. Selezionare ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** dal menu di scelta rapida.

In alternativa, è possibile:

1. Selezionare la riga di connessione.

1. Seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** dalla barra blu.

Durante la modifica di una connessione è possibile:

* Avviare e interrompere l&#39;importazione di nuovi dati.
* Rinominare una connessione.
* Aggiornare i set di dati.
* Rimuovere i set di dati dalle connessioni.

Per ulteriori informazioni, vedere [Creare o modificare una connessione](create-connection.md).


### Eliminare una connessione {#connections-delete}

1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione.
1. Selezionare ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]**.

In alternativa, è possibile:

1. Selezionare la riga di connessione.

1. Seleziona ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** dalla barra blu.

Quando si elimina una connessione, un pannello **[!UICONTROL Delete connection]** indica le visualizzazioni dati eliminate e i progetti dell&#39;area di lavoro interessati.

![Elimina connessione](assets/delete-connection.png)

Selezionare **[!UICONTROL Continue]** per eliminare la connessione.

Per ulteriori informazioni sull&#39;eliminazione di una connessione, vedere [Implicazioni dell&#39;eliminazione](/help/technotes/deletion.md).


### Creare una visualizzazione dati per una connessione

* Se alla connessione non è associata alcuna visualizzazione dati:

   1. Seleziona ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) accanto al nome della connessione.

* Se per la connessione sono già state create una o più visualizzazioni dati:

   1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione.
   1. Selezionare ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create new data view]**.

In alternativa, è possibile:

1. Selezionare la riga di connessione.

1. Seleziona ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** dalla barra dei pulsanti blu.

Per ulteriori informazioni, consulta [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md).

### Dettagli di connessione {#connection-detail}

Per visualizzare i dettagli di una connessione, selezionare un nome di connessione nella tabella connessioni.

![Finestra Tutti i set di dati con widget e impostazioni](assets/conn-details.png)

L&#39;interfaccia dei dettagli Connessioni fornisce una visualizzazione dettagliata dello stato di una connessione. Puoi:

* Controllare lo stato dei set di dati della connessione e del processo di acquisizione.
* Identificare i problemi di configurazione che possono causare record ignorati o eliminati.
* Vedere quando i dati sono disponibili per il reporting.

| Interfaccia utente | Descrizione |
| --- | --- |
| ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Edit Connection] | Per modificare i dettagli di una connessione, selezionare ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit Connection]**. Per ulteriori informazioni, vedere [Creare o modificare una connessione](create-connection.md). |
| Selettore set di dati | Consente di scegliere uno o tutti i set di dati della connessione. Non è possibile selezionare più set di dati. Predefinito su [!UICONTROL All datasets]. |
| Selettore intervallo di date | Modifica la data di inizio e di fine oppure seleziona ![Calendario](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) per aprire il selettore dell&#39;intervallo di date. Nel selettore intervallo di date selezionare un intervallo di date utilizzando uno dei periodi predefiniti, ad esempio **[!UICONTROL Last 6 months]**, oppure utilizzare il calendario per selezionare le date di inizio e di fine. Selezionare **[!UICONTROL Apply]** per applicare il nuovo intervallo di date. |
| [!UICONTROL Records of event data available] | Numero totale di righe del set di dati evento disponibili per il reporting, **per l&#39;intera connessione**. Questo conteggio è indipendente da qualsiasi impostazione del calendario. Il conteggio cambia se selezioni un set di dati dal selettore o selezionando un set di dati nella tabella. Una volta aggiunti i dati, vi è una latenza di 1-2 ore per far sì che vengano visualizzati nel reporting. |
| [!UICONTROL Metrics] | Riepiloga i record evento, ricerca, profilo e set di dati di riepilogo aggiunti, saltati ed eliminati e il numero di batch aggiunti. Queste metriche si basano sul **set di dati e intervallo di date selezionati**.<p>Selezionare **[!UICONTROL Check detail]** per visualizzare la finestra a comparsa **[!UICONTROL Check skipped detail]**. Il pop-up elenca il numero di record saltati e il motivo di tutti i set di dati evento o di tutti i set di dati selezionati.<p><img src="./assets/skipped-records.png" width="500"/><p>Selezionare il popup ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) con ulteriori informazioni. Per alcuni motivi ignorati, ad esempio [!UICONTROL Empty visitor ID], nel popup viene visualizzato PSQL di esempio per EQS (Experience Platform for Query Service) che è possibile utilizzare in [Query Service](https://experienceleague.adobe.com/it/docs/experience-platform/query/home) per eseguire query per i record ignorati nel set di dati. Selezionare ![Copia](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copy sample PSQL for EQS]** per copiare SQL. |
| [!UICONTROL Records added] | Indica quante righe sono state aggiunte nel periodo di tempo selezionato, **per il set di dati e l’intervallo di date selezionati**. Aggiornato ogni 10 minuti. |
| [!UICONTROL Records skipped] | Indica quante righe sono state saltate nel periodo di tempo selezionato, **per il set di dati e l’intervallo di date selezionati**. I motivi per cui i record vengono ignorati includono: marche temporali mancanti, ID persona mancante o non valido e così via. Aggiornato ogni 10 minuti. <p>Gli ID persona non validi (ad esempio `undefined` o `00000000` o qualsiasi combinazione di numeri e lettere in un [!UICONTROL Person ID] che compaiono in un evento più di 1 milione di volte in un dato mese) sono ID che non possono essere attribuiti a un utente o persona specifica. Queste righe non possono essere acquisite nel sistema e generano acquisizione e reporting soggetti a errori. Per correggere gli ID persona non validi, hai 3 possibilità:<ul><li>Utilizza [Stitching](/help/stitching/overview.md) per popolare gli ID utente non definiti o composti solo da zeri con ID utente validi.</li><li>Rimuovi l’ID utente, che viene quindi ignorato durante l’acquisizione (da preferire agli ID utente non validi o agli ID composti solo da zeri).</li><li>Correggi eventuali ID utente non validi nel sistema prima di acquisire i dati.</li></ul> |
| Eliminazione di [!UICONTROL Records] completata | Indica quante righe sono state eliminate nel periodo di tempo selezionato, **per il set di dati e l’intervallo di date selezionati**. Qualcuno potrebbe aver eliminato un set di dati in [!DNL Experience Platform], ad esempio. Aggiornato ogni 10 minuti.<p>In alcuni scenari, questo valore può includere anche i record sostituiti, ad esempio con l’unione o alcuni aggiornamenti dei set di dati di ricerca. Prendi in considerazione questo esempio:</p><ul><li>Carichi un record in un set di dati Profilo individuale XDM, che Customer Journey Analytics è configurato per acquisire come dati di ricerca profilo. Nei dettagli della connessione, questo set di dati visualizzerebbe 1 record aggiunto.</li><li>Carichi un duplicato del record originale nello stesso set di dati di AEP, che ora contiene due record. Customer Journey Analytics acquisisce il record aggiuntivo dal set di dati di ricerca del profilo. Vedendo che ha già acquisito un record di profilo nella connessione per quell’ID persona, Customer Journey Analytics elimina la versione precedente e aggiunge i nuovi dati del profilo. Nei dettagli della connessione, questa azione rappresenterebbe 1 record aggiunto e 1 record eliminato, perché Customer Journey Analytics mantiene solo i dati di ricerca profilo più recenti per qualsiasi ID persona acquisito.</li><li>In totale, il set di dati di AEP contiene due record che risultano identici. I dettagli della connessione a Customer Journey Analytics visualizzano separatamente lo stato dei dati acquisiti: 2 record aggiunti e 1 record eliminato per questo set di dati profilo. </li></ul> |
| ![Cerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Cerca nome o ID set di dati_ | Campo di ricerca del set di dati. È possibile eseguire ricerche nella tabella dei set di dati in base al nome o a [!UICONTROL Dataset ID]. |
| [!UICONTROL Datasets table] | I set di dati che fanno parte della connessione. |
| [!UICONTROL Datasets] | Nome del set di dati che fa parte della connessione. Puoi selezionare il collegamento ipertestuale per aprire il set di dati nell’interfaccia utente di Experience Platform in una nuova scheda. Puoi selezionare la riga o la casella di controllo per visualizzare i dettagli solo per il set di dati selezionato. |
| [!UICONTROL Dataset ID] | Generato automaticamente da Experience Platform. |
| [!UICONTROL Records added] | Il numero di record del set di dati (righe) aggiunti a una connessione durante l’intervallo di tempo selezionato. |
| [!UICONTROL Records skipped] | Il numero di record del set di dati (righe) ignorati durante il trasferimento di dati per una connessione durante l’intervallo di tempo selezionato. |
| [!UICONTROL Records deleted] | Numero di record di set di dati (righe) rimossi da una connessione durante l’intervallo di tempo selezionato. |
| [!UICONTROL Batches added] | Il numero di batch di set di dati è stato aggiunto a una connessione. |
| [!UICONTROL Last added] | La marca temporale dell’ultimo batch del set di dati aggiunto a una connessione. |
| [!UICONTROL Data source type] | Tipo di origine del set di dati. Quando si crea una connessione, è possibile definire il tipo di origine. |
| [!UICONTROL Dataset type] | Tipo di set di dati per questo set di dati. Il tipo può essere [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup] o [!UICONTROL Summary]. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| Schema | Lo schema Experience Platform su cui si basa il set di dati. |
| [!UICONTROL Import new data] | Stato dell’importazione di nuovi dati per il set di dati: <p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Il]**se il set di dati è configurato per l&#39;importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Off_]** se il set di dati non è configurato per l&#39;importazione di nuovi dati. |
| [!UICONTROL Transform data] | Stato di trasformazione dei set di dati di ricerca B2B applicabili. Per ulteriori informazioni, consulta [Trasformare i set di dati per le ricerche B2B](transform-datasets-b2b-lookups.md).<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _il]**per i set di dati applicabili abilitati per la trasformazione, <p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x disattivato_]** per i set di dati applicabili non abilitato per la trasformazione e<p>**[!UICONTROL N/A]** per tutti gli altri set di dati, non applicabile per la trasformazione. |
| [!UICONTROL Backfill data] | Stato dei dati di backfill per il set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _backfill non riusciti]**per il numero di backfill non riusciti,<p>![Stato rosso](assets/status-orange.svg)   **[!UICONTROL _x _backfill in elaborazione]**per il numero di backfill in elaborazione,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _backfill completati]**per il numero di backfill completati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** nel caso in cui i backfill non siano configurati. |
| [!UICONTROL Import new data] | Stato dell’importazione di nuovi dati per il set di dati: <p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Il]**se il set di dati è configurato per l&#39;importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Off_]** se il set di dati non è configurato per l&#39;importazione di nuovi dati. |
| [!UICONTROL Backfill data] | Stato dei dati di backfill per il set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _backfill non riusciti]**per il numero di backfill non riusciti,<p>![Stato rosso](assets/status-orange.svg)   **[!UICONTROL _x _backfill in elaborazione]**per il numero di backfill in elaborazione,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _backfill completati]**per il numero di backfill completati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** se non è configurato alcun backfill. |

>[!IMPORTANT]
>
>Eventuali dati acquisiti prima del 13 agosto 2021 non vengono riflessi nell&#39;interfaccia [!UICONTROL Connections].

#### Pannello Connessione

Quando nella tabella dei set di dati non è selezionato alcun set di dati, un pannello sul lato destro dell’interfaccia Connessioni mostra le opzioni e i dettagli di connessione.

| Opzioni | Descrizione |
| --- | --- |
| ![Aggiorna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Refresh] | Per aggiornare la connessione e consentire la visualizzazione dei record aggiunti di recente, selezionare ![Aggiorna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Refresh]**. |
| ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** | [Elimina](#delete-a-connection) questa connessione. |
| ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** | [Crea una visualizzazione dati](#create-a-data-view) basata su questa connessione. Per ulteriori informazioni, vedi [Visualizzazioni dati](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views). |
| [!UICONTROL Connection name] | Il nome descrittivo della connessione. |
| [!UICONTROL Connection description] | Descrizione più dettagliata dello scopo della connessione. |
| [!UICONTROL Sandbox] | La sandbox [Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/sandbox/home) da cui questa connessione attinge i relativi set di dati. Questa sandbox è stata selezionata al momento della creazione della connessione. Non può essere modificato. |
| [!UICONTROL Connection ID] | Questo ID viene generato in Experience Platform. Puoi usare ![Copia](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) per copiare l&#39;ID. |
| [!UICONTROL Data views using connection] | Elenca tutte le visualizzazioni dati che utilizzano questa connessione. |
| [!UICONTROL Import new data] | Stato dell’importazione di nuovi dati per i set di dati: <p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Il]**per il numero di set di dati configurati per l&#39;importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Disattivato_]** per quanti set di dati viene disattivata l&#39;importazione di nuovi dati. |
| [!UICONTROL Backfill data] | Stato dei dati di backfill per i set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _backfill non riusciti]**per il numero di backfill non riusciti tra set di dati,<p>![Stato rosso](assets/status-orange.svg)   **[!UICONTROL _x _backfill in elaborazione]**per il numero di backfill in elaborazione tra set di dati,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _backfill completati]**per il numero di backfill completati per i set di dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** nel caso in cui non siano definiti backfill per i set di dati nella connessione. |
| Trasformare i dati | Stato di trasformazione dei set di dati di ricerca B2B applicabili. Per ulteriori informazioni, consulta [Trasformare i set di dati per le ricerche B2B](transform-datasets-b2b-lookups.md).<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _On]**per il numero di set di dati abilitati per la trasformazione. |
| [!UICONTROL Created by] | Nome della persona che ha creato la connessione. |
| [!UICONTROL Last modified] | Il timestamp dell’ultima modifica apportata alla connessione. |
| [!UICONTROL Last modified by] | Persona che ha modificato per ultima la connessione. |

#### Pannello Set di dati

Quando un set di dati viene selezionato nella tabella dei set di dati, in un pannello sul lato destro dell’interfaccia Connessioni vengono visualizzati i dettagli del set di dati selezionato.

| Dettagli | Descrizione |
| --- | --- |
| [!UICONTROL Person ID] | Un’identità definita nello schema del set di dati in Experience Platform. Questa identità è l’ID persona selezionato durante la creazione della connessione. Se crei una connessione che include set di dati con ID diversi, il reporting lo riflette. Per unire i set di dati, devi utilizzare lo stesso ID persona in tutti i set di dati. |
| [!UICONTROL Key] | Chiave specificata per un set di dati di ricerca. |
| [!UICONTROL Matching Key] | Chiave corrispondente specificata per un set di dati di ricerca. |
| [!UICONTROL Timestamp] | La marca temporale definita per un set di dati evento. |
| [!UICONTROL Records available] | Numero totale di righe acquisite per questo set di dati, per il particolare periodo di tempo selezionato nel calendario. Non esiste alcuna latenza in termini di visualizzazione dei dati nel reporting, una volta aggiunti. Tuttavia, quando crei una nuova connessione, esiste [latenza](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq). |
| [!UICONTROL Records added] | Numero di righe aggiunte nel periodo di tempo selezionato. |
| [!UICONTROL Records deleted] | Quanti record sono stati eliminati durante il periodo di tempo selezionato. |
| [!UICONTROL Batches added] | Quanti batch di dati sono stati aggiunti a questo set di dati. |
| [!UICONTROL Records skipped] | Quante righe sono state saltate durante l’acquisizione nel periodo di tempo selezionato.<p>I motivi per cui i record vengono ignorati includono: marche temporali mancanti, ID persona mancante o non valido e così via. Aggiornato ogni 10 minuti.<p>Gli ID persona non validi (ad esempio `undefined` o `00000000` o qualsiasi combinazione di numeri e lettere in un [!UICONTROL Person ID] che appare in un evento più di 1 milione di volte in un dato mese) sono ID che non possono essere attribuiti a un utente o persona specifica. Queste righe non possono essere acquisite nel sistema e generano acquisizione e reporting soggetti a errori. Per correggere gli ID persona non validi, hai 3 possibilità:<ul><li>Utilizza [Stitching](/help/stitching/overview.md) per popolare gli ID utente non definiti o composti solo da zeri con ID utente validi.</li><li>Rimuovi l’ID utente, che viene quindi ignorato durante l’acquisizione (da preferire agli ID utente non validi o agli ID composti solo da zeri).</li><li>Correggi eventuali ID utente non validi nel sistema prima di acquisire i dati.</li></ul> |
| [!UICONTROL Last added] | La marca temporale in cui è stato aggiunto l’ultimo batch. |
| [!UICONTROL Import new data] | Stato dell’importazione di nuovi dati per il set di dati: <p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Il]**se il set di dati è configurato per l&#39;importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Off_]** se il set di dati non è configurato per l&#39;importazione di nuovi dati. |
| [!UICONTROL Backfill data] | Stato dei dati di backfill per il set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _backfill non riusciti]**per il numero di backfill non riusciti,<p>![Stato rosso](assets/status-orange.svg)   **[!UICONTROL _x _backfill in elaborazione]**per il numero di backfill in elaborazione,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _backfill completati]**per il numero di backfill completati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** se non è configurato alcun backfill.<p>Per visualizzare una finestra di dialogo con una panoramica dei precedenti backfill per il set di dati, seleziona <img src="./assets/pastbackfill.svg" alt="Retrocompilazioni precedenti" width="15"/> **[!UICONTROL Past backfills]**. |
| [!UICONTROL Data source type] | Tipo di origine dati definito durante l’aggiunta del set di dati alla connessione. |
| [!UICONTROL Dataset type] | [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup] o [!UICONTROL Summary]. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| [!UICONTROL Schema] | Lo schema Experience Platform su cui si basa questo set di dati. |
| [!UICONTROL Dataset ID] | Questo ID del set di dati viene generato in Experience Platform. |


## Utilizzo {#connections-usage}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_keyusagemetrics"
>title="Metriche di utilizzo chiave"
>abstract="Fornisce dati mensili e totali per le righe principali e storiche da riportare."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyingestedrows"
>title="Righe acquisite mensilmente"
>abstract="Misura il numero totale di record aggiunti al sistema ogni mese per fornire informazioni approfondite sulla crescita dei dati e sui tassi di acquisizione."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyreportablerows"
>title="Righe mensili da riportare"
>abstract="Traccia il numero di righe disponibili per il reporting. Le righe da riportare sono le righe acquisite meno quelle ignorate ed eliminate durante l’acquisizione. Le righe da riportare fungono da metrica chiave per la fatturazione e l’utilizzo dei dati."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_detailbreakdown"
>title="Raggruppamento in dettaglio."
>abstract="Puoi visualizzare metriche dettagliate per connessione, set di dati, sandbox e tag, con l’opzione di scaricare un file CSV dei dati."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_otherdatasets"
>title="Altri set di dati"
>abstract="Per i mesi precedenti a settembre 2024, i dati sono stati raccolti a livello di set di dati e vengono visualizzati come *Altri set di dati* per maggiore chiarezza. A partire da settembre 2024, i dati vengono raccolti a livello di set di dati granulari e *Altri set di dati* non verranno più visualizzati."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_unknowndatasetsorconnections"
>title="Connessioni o set di dati sconosciuti"
>abstract="Le connessioni o i set di dati sconosciuti vengono visualizzati utilizzando i relativi ID."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_datanotavailable"
>title="Dati non disponibili"
>abstract="I dati storici precedenti a settembre 2024 non sono disponibili a causa di limitazioni del sistema. Le metriche vengono raccolte e visualizzate a partire da settembre 2024. Il grafico mostra gli ultimi 18 mesi sulla timeline. I dati futuri verranno visualizzati non appena saranno disponibili."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="Righe principali da riportare"
>abstract="Visualizza il numero totale di righe disponibili negli ultimi 13 mesi. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="Righe storiche da riportare"
>abstract="Visualizza il numero totale di righe disponibili per il periodo antecedente agli ultimi 13 mesi. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale precedente a gennaio 2023."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="Metriche di utilizzo chiave"
>abstract="Fornisce dati mensili e totali per le righe principali e storiche da riportare."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="Righe acquisite mensilmente"
>abstract="Misura il numero totale di record aggiunti al sistema ogni mese per fornire informazioni approfondite sulla crescita dei dati e sui tassi di acquisizione."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="Righe mensili da riportare"
>abstract="Traccia il numero di righe disponibili per il reporting. Le righe da riportare sono le righe acquisite meno quelle ignorate ed eliminate durante l’acquisizione. Le righe da riportare fungono da metrica chiave per la fatturazione e l’utilizzo dei dati."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="Raggruppamento in dettaglio."
>abstract="Puoi visualizzare metriche dettagliate per connessione, set di dati, sandbox e tag, con l’opzione di scaricare un file CSV dei dati."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="Altri set di dati"
>abstract="Per i mesi precedenti a settembre 2024, i dati sono stati raccolti a livello di set di dati e vengono visualizzati come *Altri set di dati* per maggiore chiarezza. A partire da settembre 2024, i dati vengono raccolti a livello di set di dati granulari e *Altri set di dati* non verranno più visualizzati."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="Connessioni o set di dati sconosciuti"
>abstract="Le connessioni o i set di dati sconosciuti vengono visualizzati utilizzando i relativi ID."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="Dati non disponibili"
>abstract="I dati storici precedenti a settembre 2024 non sono disponibili a causa di limitazioni del sistema. Le metriche vengono raccolte e visualizzate a partire da settembre 2024. Il grafico mostra gli ultimi 18 mesi sulla timeline. I dati futuri verranno visualizzati non appena saranno disponibili."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="Righe principali da riportare"
>abstract="Visualizza il numero totale di righe disponibili negli ultimi 13 mesi. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Righe storiche da riportare"
>abstract="Visualizza il numero totale di righe disponibili per il periodo antecedente agli ultimi 13 mesi. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale precedente a gennaio 2023."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="Righe principali da riportare"
>abstract="Le righe principali da segnalare sono valori di snapshot, non totali aggregati. Questi valori vengono aggiornati in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. Se un cliente seleziona gennaio - marzo, i valori rifletteranno l’istantanea da marzo."

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="Righe storiche da riportare"
>abstract="Le righe cronologiche da segnalare sono valori di snapshot, non totali aggregati. Questi valori vengono aggiornati in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. Se un cliente seleziona gennaio - marzo, i valori rifletteranno l’istantanea da marzo."

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="Righe cumulative per reporting"
>abstract="Le righe cumulative da segnalare sono valori di snapshot, non totali aggregati. Questi valori vengono aggiornati in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. Se un cliente seleziona gennaio - marzo, i valori rifletteranno l’istantanea da marzo."

<!-- markdownlint-enable MD034 -->



L&#39;interfaccia [!UICONTROL Usage] mostra l&#39;utilizzo delle righe acquisite e segnalabili in tutte le connessioni. Se non è selezionata, selezionare la scheda **[!UICONTROL Usage]** per accedere all&#39;interfaccia.

Questa interfaccia consente di determinare se l&#39;utilizzo del Customer Journey Analytics è conforme a quanto stabilito contrattualmente. Oltre a scopi di monitoraggio, è possibile utilizzare l&#39;interfaccia di utilizzo per pianificare il rinnovo della licenza Customer Journey Analytics.

L’interfaccia di utilizzo utilizza le metriche seguenti

| Nome della metrica | Descrizione |
|---|---|
| Righe storiche da riportare | Numero di righe per il periodo più vecchio di 13 mesi. |
| Righe principali da riportare | Numero di righe negli ultimi 13 mesi. |
| Righe acquisite | Quante righe vengono acquisite per il periodo specifico. |
| Righe per reporting | Quante righe di dati hai come parte della connessione per il periodo specifico. |
| Righe cumulative | Quante righe vengono acquisite fino al mese specifico. |

>[!NOTE]
>
>I dati vengono raccolti a partire da luglio 2024 per i record principali, storici e totali. Per informazioni sui dati storici precedenti, contatta il tuo account manager.
>



L’interfaccia di utilizzo è costituita da due pannelli:

* Pannello **[!UICONTROL Key usage metrics]**: fornisce righe di dati di base e cronologici da segnalare. Il pannello tiene inoltre traccia delle modifiche percentuali rispetto al mese precedente per entrambe le righe di dati principali e storici.

  Il pannello viene visualizzato in una visualizzazione:

   * **[!UICONTROL Core data reportable rows]**.

     Quante righe da segnalare hai negli ultimi 13 mesi. Il numero di riepilogo è il numero di righe principali da segnalare (ad esempio, 741M) per l’ultimo mese (ad esempio, dicembre 2024).

   * **[!UICONTROL Historical data reportable rows]**.

     Quante righe da segnalare si hanno per il periodo più vecchio di 13 mesi. Il numero di riepilogo è il numero di righe segnalabili cronologiche (ad esempio, 127M) per l’ultimo mese (ad esempio, dicembre 2024).

  Quando passi il cursore su una barra sovrapposta nella visualizzazione, viene visualizzato il numero di righe per quella parte specifica della barra (ad esempio).


  ![Metriche di utilizzo chiave](assets/usage-key-usage-metrics.png)

* Un pannello combinato che mostra tre pannelli secondari per:

+++ Righe acquisite

  Il pannello secondario **[!UICONTROL Ingested rows]** misura il numero totale di record aggiunti al sistema ogni mese, fornendo informazioni sulla crescita dei dati e sui tassi di acquisizione. Il pannello secondario fornisce un riepilogo del totale delle righe acquisite di questo mese e della modifica rispetto al mese precedente.

  ![Righe acquisite](assets/usage-ingested-rows.png)

  Puoi passare il cursore del mouse sui punti dati nella visualizzazione per visualizzare una finestra a comparsa con ulteriori dettagli.

+++

+++ Righe per reporting

  La visualizzazione **[!UICONTROL Reportable rows]** tiene traccia del numero di righe disponibili per il reporting sottraendo le righe saltate ed eliminate dalle righe acquisite, fungendo da metrica chiave per la fatturazione e l&#39;utilizzo dei dati. Il pannello secondario fornisce due riepiloghi:

   * **[!UICONTROL Last month total]**: riepilogo delle righe segnalabili totali fino al mese corrente.
   * **[!UICONTROL This month]**: riepilogo delle righe totali del mese corrente e della modifica rispetto al mese precedente.

  ![Righe segnalabili](assets/usage-reportable-rows.png)

  Puoi passare il cursore del mouse sui punti dati nelle visualizzazioni per visualizzare un pop-up con ulteriori dettagli.

+++

+++ Raggruppamento dettagliato

  È possibile utilizzare la tabella **[!UICONTROL Detail breakdown]** per visualizzare metriche dettagliate per connessione, set di dati, sandbox e tag. I set di dati vengono segnalati utilizzando ID anziché nomi, in quanto i nomi dei set di dati possono essere modificati durante un periodo di reporting. I set di dati o le connessioni sconosciuti vengono segnalati utilizzando gli ID.

  Per i mesi precedenti a settembre 2024, i dati sono stati raccolti a livello di set di dati e vengono visualizzati come [!UICONTROL Other datasets] per maggiore chiarezza. A partire da settembre 2024, i dati vengono raccolti a livello di set di dati granulari e [!UICONTROL Other datasets] non viene più visualizzato.

   * Per modificare il raggruppamento, selezionare una combinazione per **[!UICONTROL View by]** e **[!UICONTROL Breakdown by]**.

     | **[!UICONTROL View by]** opzioni | **[!UICONTROL Breakdown by]** opzioni |
     |---|---|
     | **[!UICONTROL Connection]** | **[!UICONTROL -]** e **[!UICONTROL Dataset]** |
     | **[!UICONTROL Dataset]** | **[!UICONTROL -]** |
     | **[!UICONTROL Sandbox]** | **[!UICONTROL Connection]** |
     | **[!UICONTROL Tag]** | **[!UICONTROL Connection]** |

  ![Dettaglio raggruppamento](assets/usage-detail-breakdown.png)

+++

  Puoi definire un **[!UICONTROL Time range]** in mesi per il quale generare il rapporto. Utilizza ![Calendario](/help/assets/icons/Calendar.svg) per selezionare l&#39;intervallo di tempo.

>[!MORELIKETHIS]
>
>Esercitazione su [Visualizzare, risolvere e modificare le impostazioni di connessione](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja).
