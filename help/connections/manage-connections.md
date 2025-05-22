---
title: Come gestire le connessioni in Customer Journey Analytics
description: Descrive come gestire le connessioni ai set di dati di Experience Platform in Customer Journey Analytics (CJA).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 836c793ae74185728af03636b0ba3e838f46f05d
workflow-type: tm+mt
source-wordcount: '3876'
ht-degree: 74%

---

# Gestire le connessioni

Dopo aver [creato o modificato una o più connessioni](/help/connections/create-connection.md), puoi gestirle in **[!UICONTROL Connections]**. L&#39;interfaccia [!UICONTROL Connections] consente di:

* Visualizzare immediatamente tutte le tue connessioni, inclusi il proprietario, la sandbox e quando sono state create e modificate.
* Modificare una connessione.
* Eliminare una connessione.
* Creare una visualizzazione dati a partire da una connessione.
* Visualizza tutti i set di dati in una connessione.
* Controllare lo stato dei set di dati della tua connessione e del processo di acquisizione. Ad esempio, la disponibilità dei dati in modo da poter iniziare con il reporting e l’analisi in Analysis Workspace.
* Identifica eventuali discrepanze di dati dovute a configurazione errata. Vi mancano delle righe? In caso affermativo, quali righe mancano e perché? Hai configurato in modo errato le connessioni e causato la mancanza di dati in Customer Journey Analytics?
* Ottieni informazioni sull’utilizzo delle righe acquisite e segnalabili in tutte le connessioni.

[!UICONTROL Connections] ha due interfacce: [[!UICONTROL List]](#list) e [[!UICONTROL Usage]](#usage).


## Elenco

L’interfaccia **[!UICONTROL List]** è l’interfaccia predefinita per Connessioni. Se non è selezionata, seleziona la scheda **[!UICONTROL List]** per accedere all’interfaccia.

![vista a elenco](assets/list-view.png)

L’interfaccia [!UICONTROL List] mostra una tabella di tutte le connessioni disponibili. Puoi cercare rapidamente una connessione utilizzando la casella ![Ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) della ricerca.

Nella tabella sono disponibili le colonne o le icone seguenti.

| Colonna o icona | Descrizione |
| --- | --- |
| **[!UICONTROL _Nome_]** | Il nome descrittivo della connessione. Selezionare il nome del collegamento ipertestuale per visualizzare i [dettagli della connessione](#connection-details). |
| ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Per visualizzare informazioni su [!UICONTROL Datasets included], [!UICONTROL Sandbox], [!UICONTROL Owner] e altro, seleziona ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) accanto al nome della connessione.<p>Una finestra a comparsa visualizza i dettagli sul set di dati. <p>![Popup info di connessione](assets/connection-info-popup.png) |
| ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) per aprire un menu di scelta rapida. È possibile selezionare: <p>![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** per [modificare](#edit-a-connection) una connessione.<p>![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** per [eliminare](#delete-a-connection) una connessione.<p>![Visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create new data view]** per [creare una nuova visualizzazione dati](#create-a-data-view) per la connessione.<p>![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Connection map]** per visualizzare una [mappa di connessione](#map-a-connection) per la connessione. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Connection type]** | Tipo di connessione: connessione basata su **[!UICONTROL Person]** o basata su **[!UICONTROL Account]**. |
| **[!UICONTROL Datasets]** | Uno o più collegamenti ai set di dati che fanno parte della connessione. Puoi selezionare il collegamento ipertestuale del set di dati per visualizzare il set di dati nella connessione. Se della connessione selezionata fanno parte più set di dati, seleziona **[!UICONTROL +*x *più]**&#x200B;per visualizzare un pannello **[!UICONTROL Datasets included]**. Questo pannello mostra i collegamenti a tutti i set di dati e un&#39;opzione per ![cercare](/help/assets/icons/Search.svg) set di dati specifici che fanno parte della connessione.<p>![Set di dati inclusi](assets/datasets-included.png)<p>Seleziona un nome per il set di dati per aprirlo nell’interfaccia di Experience Platform in una nuova scheda. |
| **[!UICONTROL Sandbox]** | La [sandbox di Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/sandbox/home) da cui questa connessione attinge i relativi set di dati. Seleziona questa sandbox al momento della creazione della connessione. Una volta salvata una connessione, non è possibile modificare la sandbox. |
| **[!UICONTROL Owner]** | Persona che ha creato la connessione. |
| **[!UICONTROL Import new data]** | Stato dell’importazione di nuovi dati per i set di dati: <p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Il]**&#x200B;per i set di dati configurati per l&#39;importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Disattivato_]** per i set di dati non configurati per l’importazione di nuovi dati. |
| **[!UICONTROL Date created]** | Marca temporale della prima creazione della connessione. |
| **[!UICONTROL Last modified]** | Marca temporale dell’ultimo aggiornamento della connessione. |
| **[!UICONTROL Backfill data]** | Stato dei dati di retrocompilazione tra set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _retrocompilazioni non riuscite]**&#x200B;per il numero di retrocompilazioni non riuscite tra set di dati,<p>![Stato arancione](assets/status-orange.svg)   **[!UICONTROL _x _retrocompilazioni in elaborazione]**&#x200B;per il numero di retrocompilazioni in elaborazione tra set di dati,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _retrocompilazioni completate]**&#x200B;per il numero di retrocompilazioni completate per i set di dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** nel caso in cui non siano definite retrocompilazioni per i set di dati nella connessione. |

Per configurare le colonne da visualizzare nella tabella, selezionare ![Impostazioni colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Nella finestra di dialogo Personalizza tabella, seleziona le colonne da visualizzare.

### Modificare una connessione

Per modificare una connessione:

1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione
1. Seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** dal menu di scelta rapida.

In alternativa, puoi:

1. Controllare l’URL della connessione.

1. Seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** dalla barra delle azioni blu.

Per ulteriori informazioni, consulta [Creare o modificare una connessione](create-connection.md).


### Eliminare una connessione {#connections-delete}

Per eliminare una connessione:

1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione.
1. Seleziona ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]**.

In alternativa, puoi:

1. Controllare l’URL della connessione.

1. Seleziona ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** dalla barra delle azioni blu.

Quando elimini una connessione, un pannello **[!UICONTROL Delete connection]** indica le visualizzazioni dati eliminate e i progetti dell’area di lavoro interessati.

* In ➊ **[!UICONTROL Info]** sono visualizzate le implicazioni dell&#39;eliminazione della connessione.

  ![Elimina connessione](assets/delete-connection.png)

  Selezionare **[!UICONTROL Continue]** per confermare l&#39;eliminazione.

* In ➋ **[!UICONTROL Confirmation]**, immettere il nome della connessione in **[!UICONTROL Type connection name]** e selezionare **[!UICONTROL Delete]** per eliminare la connessione. Seleziona **[!UICONTROL Cancel]** per annullare.

Per ulteriori informazioni sull’eliminazione di una connessione, consulta [Implicazioni dell’eliminazione](/help/technotes/deletion.md).


### Creare una visualizzazione dati per una connessione

Per creare una visualizzazione dati per una connessione:

1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione.
1. Seleziona ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create new data view]**.

In alternativa, puoi:

1. Controllare l’URL della connessione.

1. Seleziona ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** dalla barra delle azioni blu.

Per ulteriori informazioni, consulta [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md).


### Mappare una connessione

Per visualizzare una [mappa di connessione](/help/connections/create-connection.md#connection-map) che descrive le relazioni tra i set di dati che fanno parte di una connessione:

1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione.
1. Seleziona ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Connection map]**.

### Dettagli della connessione {#connection-detail}

Per visualizzare i dettagli di una connessione, selezionare un nome di connessione ipertestuale nella tabella connessioni.

![Finestra Tutti i set di dati con widget e impostazioni](assets/conn-details.png)

L’interfaccia Dettagli connessioni fornisce una visualizzazione molto dettagliata dello stato di una connessione. Puoi:

* Controllare lo stato dei set di dati della connessione e del processo di acquisizione.
* Identificare i problemi di configurazione che portano a record saltati o eliminati.
* Vedere quando i dati sono disponibili per il reporting.

| Interfaccia utente | Descrizione |
| --- | --- |
| ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit Connection]** | Per modificare i dettagli di una connessione, seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit Connection]**. Per ulteriori informazioni, consulta [Creare o modificare una connessione](create-connection.md). |
| **[!UICONTROL *Selettore di set di dati *]** | Seleziona uno o tutti i set di dati per i quali visualizzare i dettagli nella connessione. Non è possibile selezionare più set di dati. Predefinito su **[!UICONTROL All datasets]**. |
| **[!UICONTROL *Selettore di intervalli di date *]** | Seleziona un intervallo di dati per cui visualizzare i dettagli nella connessione. Modifica la data di inizio e di fine oppure seleziona ![Calendario](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) per aprire il selettore dell’intervallo di date. Nel selettore dell’intervallo di date seleziona un intervallo di date utilizzando uno dei periodi predefiniti (ad esempio **[!UICONTROL Last 6 months]**) oppure utilizzando il calendario per selezionare le date di inizio e di fine. Selezionare **[!UICONTROL Apply]** per applicare il nuovo intervallo di date ai dettagli della connessione. |
| **[!UICONTROL Records of event data available]** | Numero totale di righe del set di dati evento disponibili per il reporting, **per l’intera connessione**. Questo conteggio è indipendente da qualsiasi intervallo di date o selezione di set di dati. |
| [!UICONTROL **[!UICONTROL Metrics]**] | Riepiloga i record evento, ricerca, profilo e set di dati di riepilogo aggiunti, saltati ed eliminati e il numero di batch aggiunti. Queste metriche si basano sul **set di dati e intervallo di date selezionati**.<p>Seleziona **[!UICONTROL Check detail]** per visualizzare il pop-up **[!UICONTROL Check skipped detail]**. Il pop-up elenca il numero di record saltati e il motivo per tutti i set di dati evento o per i set di dati selezionati.<p>![Record ignorati](assets/skipped-records.png)<p>Seleziona il pop-up ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) con ulteriori informazioni. Per alcuni motivi ignorati, ad esempio [!UICONTROL Empty visitor ID], nel popup vengono visualizzati **[!UICONTROL Sample PSQL for EQS]** (Experience Platform for Query Service) che è possibile utilizzare in [Query Service](https://experienceleague.adobe.com/it/docs/experience-platform/query/home) per eseguire query per i record ignorati nel set di dati. Seleziona ![Copia](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copy sample PSQL for EQS]** per copiare SQL. |
| **[!UICONTROL Records added]** | Visualizzazione per indicare quante righe sono state aggiunte nel periodo di tempo selezionato, **per il set di dati e l&#39;intervallo di date selezionati**. Viene aggiornato ogni 10 minuti. |
| **[!UICONTROL Records skipped]** | Visualizzazione per indicare quante righe sono state ignorate nel periodo di tempo selezionato, **per il set di dati e l&#39;intervallo di date selezionati**. I motivi per cui i record vengono ignorati includono: marche temporali mancanti, ID persona o ID account [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} mancante o non valido e così via. Viene aggiornato ogni 10 minuti. <p>Gli ID persona non validi (ad esempio `undefined` o `00000000` o qualsiasi combinazione di numeri e lettere in un [!UICONTROL Person ID] che appaiono in un evento più di 1 milione di volte in un dato mese) non possono essere attribuiti a un utente o persona specifica. Queste righe di dati non possono essere acquisite nel sistema e causano acquisizioni e generazione di rapporti soggetti a errori. Per correggere gli ID persona o gli ID account [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} non validi, sono disponibili 3 opzioni:<ul><li>Utilizzare [Unione](/help/stitching/overview.md) per popolare gli ID utente non definiti o composti solo da zeri con ID utente validi.</li><li>Rimuovi gli ID utente, che vengono quindi ignorati durante l’acquisizione (da preferire agli ID utente non validi o agli ID composti solo da zeri).</li><li>Correggere eventuali ID utente non validi nel sistema prima di acquisire i dati.</li></ul> |
| **[!UICONTROL Records deleted]** | Visualizzazione per indicare quante righe sono state eliminate nel periodo di tempo selezionato, **per il set di dati e l&#39;intervallo di date selezionati**. Per esempio, qualcuno potrebbe aver eliminato un set di dati in [!DNL Experience Platform]. Viene aggiornato ogni 10 minuti.<p>In alcuni scenari, questo valore può includere anche i record sostituiti, ad esempio con l’unione, o alcuni aggiornamenti dei set di dati di ricerca. Studia questo esempio:</p><ul><li>Carichi un record in un set di dati Profilo individuale XDM, che in Customer Journey Analytics è configurato per essere acquisito come dati di ricerca profilo. Nei dettagli della connessione, questo set di dati visualizzerebbe 1 record aggiunto.</li><li>Carichi un duplicato del record originale nello stesso set di dati di AEP, che ora contiene due record. Customer Journey Analytics acquisisce il record aggiuntivo dal set di dati di ricerca del profilo o dell’account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}. Visto che un profilo o un record account è già stato acquisito nella connessione per l&#39;ID persona o l&#39;ID account [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, Customer Journey Analytics elimina la versione precedente e aggiunge i nuovi dati del profilo. Nei dettagli della connessione, questa azione rappresenterebbe 1 record aggiunto e 1 record eliminato, perché Customer Journey Analytics mantiene solo i dati di ricerca profilo più recenti per qualsiasi ID persona o ID account acquisito [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}.</li><li>In totale, il set di dati di AEP contiene due record che risultano identici. A parte, i dettagli della connessione a Customer Journey Analytics mostrano lo stato dei dati acquisiti: 2 record aggiunti e 1 record eliminato per questo set di dati profilo. </li></ul> |
| ![Ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Campo di ricerca di set di dati. Puoi cercare la tabella dei set di dati per nome o ID del set di dati. |
| [!UICONTROL Datasets table] | Set di dati che fanno parte della connessione. Per ulteriori spiegazioni, consulta la tabella seguente. Selezionare ![SelectBox](/help/assets/icons/SelectBox.svg) un singolo set di dati per visualizzare solo i dettagli di connessione per il set di dati selezionato. Equivale alla selezione di un set di dati dal selettore **[!UICONTROL _Set di dati_]**. |

La tabella dei set di dati visualizza le colonne seguenti per ogni set di dati:

| Colonna | Descrizione |
| --- | --- |
| **[!UICONTROL Datasets]** | Nome del set di dati. Puoi selezionare il collegamento ipertestuale per aprire il set di dati nell’interfaccia utente di Experience Platform in una nuova scheda. Puoi selezionare la riga o la casella di controllo per visualizzare i dettagli solo per il set di dati selezionato. |
| **[!UICONTROL Dataset ID]** | ID del set di dati generato da Experience Platform. |
| **[!UICONTROL Records added]** | Il numero di record di set di dati (righe) aggiunti a una connessione durante l’intervallo di date selezionato. |
| **[!UICONTROL Records skipped]** | Il numero di record di set di dati (righe) ignorati durante il trasferimento di dati per una connessione durante l’intervallo di date selezionato. |
| **[!UICONTROL Records deleted]** | Il numero di record di set di dati (righe) rimossi da una connessione durante l’intervallo di date selezionato. |
| **[!UICONTROL Batches added]** | Il numero di batch aggiunti a una connessione durante l’intervallo di date selezionato. |
| **[!UICONTROL Last added]** | La marca temporale dell’ultimo batch aggiunto a una connessione. |
| **[!UICONTROL Data source type]** | Tipo di origine. Puoi definire il tipo di origine quando aggiungi un set di dati a una connessione. |
| **[!UICONTROL Dataset type]** | Il tipo di [set di dati](create-connection.md#dataset-types). Il tipo può essere [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup] o [!UICONTROL Summary]. |
| **[!UICONTROL Schema]** | Schema Adobe Experience Platform su cui si basa il set di dati. |
| **[!UICONTROL Import new data]** | Stato dell’importazione di nuovi dati per il set di dati: <p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Attivo]**&#x200B;se il set di dati è configurato per l’importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Disattivato_]** se il set di dati non è configurato per l’importazione di nuovi dati. |
| **[!UICONTROL Transform data]** | Stato di trasformazione dei set di dati di ricerca B2B applicabili. Per ulteriori informazioni, consulta [Trasformare i set di dati per le ricerche B2B](transform-datasets-b2b-lookups.md).<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Attivo]**&#x200B;per i set di dati applicabili abilitati per la trasformazione, <p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Disattivato_]** per i set di dati applicabili non abilitati per la trasformazione e<p>**[!UICONTROL N/A]** per tutti gli altri set di dati, non applicabili per la trasformazione. |
| **[!UICONTROL Backfill data]** | Stato dei dati di retrocompilazione per il set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _retrocompilazioni non riuscite]**&#x200B;per il numero di retrocompilazioni non riuscite,<p>![Stato rosso](assets/status-orange.svg)   **[!UICONTROL _x _retrocompilazioni in elaborazione]**&#x200B;per il numero di retrocompilazioni in elaborazione,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _retrocompilazioni completate]**&#x200B;per il numero di retrocompilazioni completate e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** nel caso in cui le retrocompilazioni non siano configurate. |

>[!IMPORTANT]
>
>Eventuali dati acquisiti prima del 13 agosto 2021 non vengono riflessi nell’interfaccia [!UICONTROL Connections].
>

#### Pannello Connessione

Quando nella tabella dei set di dati non è selezionato alcun singolo set di dati, il pannello di destra mostra le opzioni e i dettagli di connessione.

| Opzioni | Descrizione |
| --- | --- |
| ![Aggiorna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Refresh]** | Per aggiornare la connessione e consentire la visualizzazione dei record aggiunti di recente, seleziona ![Aggiorna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Refresh]**. |
| ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** | [Elimina](#delete-a-connection) questa connessione. |
| ![Aggiungi una visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** | [Crea una visualizzazione dati](#create-a-data-view) in base a questa connessione. Per ulteriori informazioni, consulta [Visualizzazione dati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/data-views). |
| **[!UICONTROL Connection name]** | Nome descrittivo della connessione. |
| **[!UICONTROL Connection description]** | Descrizione della connessione. |
| **[!UICONTROL Sandbox]** | La [sandbox di Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/sandbox/home) da cui questa connessione attinge i relativi set di dati. Seleziona questa sandbox al momento della creazione della connessione. Una volta salvata una connessione, non è possibile modificare la sandbox. |
| **[!UICONTROL Connection ID]** | Identificatore generato per la connessione. Puoi utilizzare ![Copia](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) per copiare il valore. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Primary ID type]** | Tipo di ID primario per la connessione: **[!UICONTROL Person]** per una connessione basata su persona, **[!UICONTROL Account]** per una connessione basata su account. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Containers]** | I contenitori configurati per la connessione. |
| **[!UICONTROL Data views using connection]** | Visualizzazioni dati che utilizzano questa connessione. |
| **[!UICONTROL Import new data]** | Stato dell’importazione di nuovi dati per i set di dati: <p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Attivo]**&#x200B;per il numero di set di dati configurati per l’importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Disattivato_]** per il numero di set di dati per il quale viene disattivata l’importazione di nuovi dati. |
| **[!UICONTROL Backfill data]** | Stato dei dati di retrocompilazione per i set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _retrocompilazioni non riuscite]**&#x200B;per il numero di retrocompilazioni non riuscite tra set di dati,<p>![Stato rosso](assets/status-orange.svg)   **[!UICONTROL _x _retrocompilazioni in elaborazione]**&#x200B;per il numero di retrocompilazioni in elaborazione tra set di dati,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _retrocompilazioni completate]**&#x200B;per il numero di retrocompilazioni completate per i set di dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** nel caso in cui non siano definite retrocompilazioni per i set di dati nella connessione. |
| **[!UICONTROL Transform data]** | Stato di trasformazione dei set di dati di ricerca B2B applicabili. Per ulteriori informazioni, consulta [Trasformare i set di dati per le ricerche B2B](transform-datasets-b2b-lookups.md).<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Attivo]**&#x200B;per il numero di set di dati abilitati per la trasformazione. |
| **[!UICONTROL Created by]** | Nome della persona che ha creato la connessione. |
| **[!UICONTROL Last modified]** | Marca temporale dell’ultima modifica apportata alla connessione. |
| **[!UICONTROL Last modified by]** | Nome dell&#39;ultima persona che ha modificato la connessione. |

#### Pannello Set di dati

Quando una riga di set di dati viene selezionata nella tabella dei set di dati, in un pannello sul lato destro dell’interfaccia Connessioni vengono visualizzati i dettagli del set di dati selezionato.

| Dettagli | Descrizione |
| --- | --- |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Global Account ID]** | L’identità specificata come ID account globale per la connessione. Applicabile solo per una connessione basata su account per la quale è configurato un contenitore Account globale. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Account ID]** | L’identità specificata come ID account per la connessione. Applicabile solo per una connessione basata su account per la quale non è configurato alcun contenitore account globale. |
| **[!UICONTROL Person ID]** | L’identità specificata come ID persona per la connessione. |
| **[!UICONTROL Key]** | Chiave specificata per un set di dati di ricerca. |
| **[!UICONTROL Matching Key]** | Chiave corrispondente specificata per un set di dati di ricerca. |
| **[!UICONTROL Timestamp]** | Marca temporale definita per un set di dati evento. |
| **[!UICONTROL Records available]** | Numero totale di righe acquisite per questo set di dati, per il particolare periodo di tempo selezionato nel calendario. Non esiste alcuna latenza in termini di visualizzazione dei dati nel reporting, una volta aggiunti. Tuttavia, quando crei una nuova connessione, si verifica una [latenza](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-faq). |
| **[!UICONTROL Records added]** | Il numero di record di set di dati (righe) aggiunti a una connessione durante l’intervallo di date selezionato. |
| **[!UICONTROL Records skipped]** | Il numero di record di set di dati (righe) ignorati durante il trasferimento di dati per una connessione durante l’intervallo di date selezionato. |
| **[!UICONTROL Batches added]** | Il numero di batch aggiunti a una connessione. |
| **[!UICONTROL Records deleted]** | Il numero di record di set di dati (righe) rimossi da una connessione durante l’intervallo di date selezionato. |
| **[!UICONTROL Last added]** | La marca temporale dell’ultimo batch aggiunto a una connessione. |
| **[!UICONTROL Import new data]** | Stato dell’importazione di nuovi dati per il set di dati: <p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Attivo]**&#x200B;se il set di dati è configurato per l’importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Disattivato_]** se il set di dati è configurato per non importare nuovi dati. |
| **[!UICONTROL Backfill data]** | Stato dei dati di retrocompilazione per il set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _retrocompilazioni non riuscite]**&#x200B;per il numero di retrocompilazioni non riuscite,<p>![Stato rosso](assets/status-orange.svg)   **[!UICONTROL _x _retrocompilazioni in elaborazione]**&#x200B;per il numero di retrocompilazioni in elaborazione,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _retrocompilazioni completate]**&#x200B;per il numero di retrocompilazioni completate e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** se non è configurata alcuna retrocompilazione.<p>Per visualizzare una finestra di dialogo con una panoramica delle precedenti retrocompilazioni relative al set di dati, selezionare <img src="./assets/pastbackfill.svg" alt="Retrocompilazioni precedenti" width="15"/> **[!UICONTROL Past backfills]**. |
| **[!UICONTROL Data source type]** | Tipo di origine dati definito al momento dell’aggiunta del set di dati alla connessione. |
| **[!UICONTROL Dataset type]** | Il tipo di [set di dati](create-connection.md#dataset-types). |
| **[!UICONTROL Schema]** | Schema Adobe Experience Platform su cui si basa questo set di dati. |
| **[!UICONTROL Dataset ID]** | ID del set di dati generato in Experience Platform. |


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
>title="Righe di base per reporting"
>abstract="Il numero totale di righe disponibili negli ultimi 13 mesi. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="Righe storiche per reporting"
>abstract="Il numero totale di righe disponibili per il periodo antecedente agli ultimi 13 mesi. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale precedente a gennaio 2023."

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
>title="Righe di base per reporting"
>abstract="Il numero totale di righe disponibili negli ultimi 13 mesi. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Righe storiche per reporting"
>abstract="Il numero totale di righe disponibili per il periodo antecedente agli ultimi 13 mesi. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale precedente a gennaio 2023."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="Righe di base per reporting"
>abstract="Le righe di base per reporting sono istantanee di valori, non totali aggregati. Questi valori vengono aggiornati in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. Se si seleziona gennaio - marzo, i valori faranno riferimento all’istantanea dal mese di marzo."

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="Righe storiche per reporting"
>abstract="Le righe storiche per reporting sono istantanee di valori, non totali aggregati. Questi valori vengono aggiornati in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. Se si seleziona gennaio - marzo, i valori faranno riferimento all’istantanea dal mese di marzo."

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="Righe cumulative per reporting"
>abstract="Le righe cumulative per reporting sono istantanee di valori, non totali aggregati. Questi valori vengono aggiornati in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. Se si seleziona gennaio - marzo, i valori faranno riferimento all’istantanea dal mese di marzo."

<!-- markdownlint-enable MD034 -->



L’interfaccia [!UICONTROL Usage] mostra l’utilizzo delle righe acquisite e segnalabili in tutte le connessioni. Se non è selezionata, seleziona la scheda **[!UICONTROL Usage]** per accedere all’interfaccia.

Questa interfaccia consente di determinare se l’utilizzo di Customer Journey Analytics è conforme a quanto stabilito contrattualmente. Oltre a scopi di monitoraggio, è possibile utilizzare l’interfaccia Utilizzo per pianificare il rinnovo della licenza di Customer Journey Analytics.

L’interfaccia di utilizzo utilizza le metriche seguenti:

| Nome della metrica | Descrizione |
|---|---|
| Righe storiche per reporting | Numero di righe per il periodo antecedente a 13 mesi. |
| Righe di base per reporting | Numero di righe posteriori a 13 mesi. |
| Righe acquisite | Quante righe vengono acquisite per il periodo specifico. |
| Righe segnalabili | Quante righe di dati vengono presentate come parte della connessione per il periodo specifico. |
| Righe cumulative | Quante righe vengono acquisite fino al mese specifico. |

>[!NOTE]
>
>I dati vengono raccolti a partire da luglio 2024 per i record principali, storici e totali. Per informazioni sui dati storici precedenti, contatta il tuo account manager.
>



L’interfaccia Utilizzo è costituita da due pannelli:

* Pannello **[!UICONTROL Key usage metrics]**: fornisce righe di dati principali e storici segnalabili. Il pannello tiene traccia inoltre delle modifiche percentuali rispetto al mese precedente per entrambe le righe di dati principali e storici.

  Il pannello mostra una visualizzazione che contiene:

   * **[!UICONTROL Core data reportable rows]**.

     Quante righe segnalabili vengono presentate negli ultimi 13 mesi. Il numero di riepilogo è il numero di righe principali segnalabili (ad esempio, 741M) per l’ultimo mese (ad esempio, dicembre 2024).

   * **[!UICONTROL Historical data reportable rows]**.

     Quante righe segnalabili vengono presentate per il periodo antecedente a 13 mesi. Il numero di riepilogo è il numero di righe storiche segnalabili (ad esempio, 127M) per l’ultimo mese (ad esempio, dicembre 2024).

  Quando passi il puntatore su una barra sovrapposta nella visualizzazione, un pop-up mostra il numero di righe relativo a quella parte specifica della barra (ad esempio).


  ![Metriche di utilizzo chiave](assets/usage-key-usage-metrics.png)

* Un pannello combinato che mostra tre pannelli secondari per:

+++ Righe acquisite

  Il pannello secondario **[!UICONTROL Ingested rows]** misura il numero totale di record aggiunti al sistema ogni mese, per fornire informazioni approfondite sulla crescita dei dati e sui tassi di acquisizione. Il pannello secondario fornisce un riepilogo del totale delle righe acquisite di questo mese e della modifica rispetto al mese precedente.

  ![Righe acquisite](assets/usage-ingested-rows.png)

  Puoi passare il puntatore sui punti dati nella visualizzazione per visualizzare una finestra a comparsa con ulteriori dettagli.

+++

+++ Righe segnalabili

  La visualizzazione **[!UICONTROL Reportable rows]** tiene traccia del numero di righe disponibili per il reporting sottraendo le righe saltate ed eliminate dalle righe acquisite, fungendo da metrica chiave per la fatturazione e l&#39;utilizzo dei dati. Il pannello secondario fornisce due riepiloghi:

   * **[!UICONTROL Last month total]**: riepilogo delle righe segnalabili totali fino al mese corrente.
   * **[!UICONTROL This month]**: riepilogo delle righe totali del mese corrente e della modifica rispetto al mese precedente.

  ![Righe segnalabili](assets/usage-reportable-rows.png)

  Puoi passare il puntatore sui punti dati nelle visualizzazioni per visualizzare un pop-up con ulteriori dettagli.

+++

+++ Raggruppamento in dettaglio.

  È possibile utilizzare la tabella **[!UICONTROL Detail breakdown]** per visualizzare metriche dettagliate per connessione, set di dati, sandbox e tag. I set di dati vengono indicati utilizzando ID anziché nomi, in quanto i nomi dei set di dati possono essere modificati nel corso di un periodo di reporting. Le connessioni o i set di dati sconosciuti vengono indicati utilizzando i relativi ID.

  Per i mesi precedenti a settembre 2024, i dati sono stati raccolti a livello di set di dati e vengono visualizzati come [!UICONTROL Other datasets] per chiarezza. A partire da settembre 2024, i dati vengono raccolti a livello di set di dati granulari e [!UICONTROL Other datasets] non vengono più visualizzati.

   * Per modificare il raggruppamento, selezionare una combinazione di **[!UICONTROL View by]** e **[!UICONTROL Breakdown by]**.

     | Opzioni **[!UICONTROL View by]** | Opzioni **[!UICONTROL Breakdown by]** |
     |---|---|
     | **[!UICONTROL Connection]** | **[!UICONTROL -]** e **[!UICONTROL Dataset]** |
     | **[!UICONTROL Dataset]** | **[!UICONTROL -]** |
     | **[!UICONTROL Sandbox]** | **[!UICONTROL Connection]** |
     | **[!UICONTROL Tag]** | **[!UICONTROL Connection]** |

  ![Raggruppamento in dettaglio](assets/usage-detail-breakdown.png)

+++

  Puoi definire un **[!UICONTROL Time range]** in mesi per il quale generare il rapporto. Utilizza ![Calendario](/help/assets/icons/Calendar.svg) per selezionare l’intervallo di tempo.

>[!MORELIKETHIS]
>
>Tutorial: [Visualizzare, risolvere i problemi e modificare le impostazioni di connessione](https://experienceleague.adobe.com/it/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja).
>[Gestire l’utilizzo di Customer Journey Analytics](/help/technotes/estimate-usage.md)
>
