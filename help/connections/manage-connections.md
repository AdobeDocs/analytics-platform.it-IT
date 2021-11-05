---
title: Gestire le connessioni
description: Descrive come gestire le connessioni ai set di dati di Experience Platform in Customer Journey Analytics (CJA).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
source-git-commit: 6d1907d676ea01b3956d5ce2ce76d43d7a8f0f1d
workflow-type: tm+mt
source-wordcount: '1749'
ht-degree: 8%

---

# Gestire le connessioni

Una volta che gli utenti amministratori hanno [creazione di una o più connessioni](/help/connections/create-connection.md), possono gestirli nel [!UICONTROL Connections] Manager. L&#39;ultimo aggiornamento dell&#39;esperienza di connessione aggiunge due funzionalità importanti nella pagina Dettagli connessione, descritta più in basso in questa pagina:

* Ti consente di controllare la **stato dei set di dati della connessione e del processo di acquisizione**. Questo controllo di stato ti consente di sapere quando i dati sono disponibili in modo da poter accedere ad Analysis Workspace e avviare l’analisi.

* Ti permette di **identificare eventuali discrepanze di dati** a causa di configurazione errata. Vi mancano delle righe? In caso affermativo, quali righe mancano e perché? Hai configurato in modo errato le connessioni e causato la mancanza di dati in CJA?

>[!NOTE]
> Questa funzionalità sarà generalmente disponibile il 20 settembre 2021.

## Connections Manager {#connections-manager}

Gestione connessioni consente di:

* Visualizza immediatamente tutte le tue connessioni, inclusi il proprietario, la sandbox e quando sono state create e modificate.
* Visualizza tutti i set di dati in una connessione.
* Controllare lo stato di una connessione.
* Eliminare una connessione.
* Rinominare una connessione.
* Creare una visualizzazione dati a partire da una connessione.

![Gestione delle connessioni](assets/conn-manager.png)

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Name] | Il nome descrittivo della connessione. Quando fai clic sul nome del collegamento ipertestuale, accedi alla pagina dei dettagli della connessione descritta di seguito. |
| Informazioni di connessione | Fai clic sull’icona info accanto al nome della connessione per visualizzare le seguenti informazioni:![Visualizza informazioni sulla connessione](assets/conn-info.png) |
| Modificare una connessione | Fare clic sui puntini di sospensione (..) accanto al nome della connessione, quindi fare clic su [!UICONTROL Edit].![Modifica connessione](assets/conn-edit-delete.png) Per ulteriori informazioni, vedere &quot;Modifica connessione&quot; di seguito. |
| Eliminare una connessione | Fare clic sui puntini di sospensione (..) accanto al nome della connessione, quindi fare clic su [!UICONTROL Delete]. Ulteriori informazioni sono disponibili sotto l&#39;intestazione &quot;Elimina connessioni&quot;. |
| Creare una visualizzazione dati | Fare clic sui puntini di sospensione (..) accanto al nome della connessione, quindi fare clic su [!UICONTROL Create data view]. Questa azione crea una nuova visualizzazione dati basata su questa connessione. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Datasets] | Set di dati che fanno parte della connessione. È possibile fare clic sul collegamento ipertestuale per visualizzare tutti i set di dati presenti nella connessione. Facendo clic su un set di dati si apre tale set di dati in Adobe Experience Platform, in una nuova scheda. |
| [!UICONTROL Sandbox] | La [Sandbox Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) da cui questa connessione attinge i relativi set di dati. Questa sandbox è stata selezionata al momento della creazione della connessione. Non può essere cambiato. |
| [!UICONTROL Owner] | Persona che ha creato la connessione. |
| [!UICONTROL Import Data Sets] | Consente di abilitare o disabilitare ciò che veniva chiamato &quot;streaming dati&quot;. |
| [!UICONTROL Date Created] | Data della prima creazione della connessione. |
| [!UICONTROL Last Modified] | Data dell’ultimo aggiornamento della connessione. |

### Eliminare le connessioni {#connections-delete}

Solo gli amministratori dispongono dell’autorizzazione per eliminare una connessione. Questa azione non viene visualizzata per i non amministratori.

1. Fare clic sui puntini di sospensione (..) accanto al nome della connessione.
1. Fai clic su [!UICONTROL Delete].

Quando si elimina una connessione in [!UICONTROL Customer Journey Analytics], un messaggio di errore indica che:

* Tutte le visualizzazioni dati create in base alla connessione eliminata non funzionano più.
* Analogamente, tutti i progetti Workspace che dipendono dalle visualizzazioni dati nella connessione eliminata cesseranno di funzionare.

[Ulteriori informazioni](/help/getting-started/cja-deletion.md) sulle implicazioni relative all’eliminazione.

### Cercare una connessione o un set di dati

Puoi cercare le connessioni utilizzando la barra di ricerca nella parte superiore, sotto la [!UICONTROL Connections] titolo.

### Ordinare le connessioni

Puoi ordinare le connessioni facendo clic sull’intestazione di ogni colonna e ordinandole in alto o in basso.

## Pagina Dettagli connessione {#connection-detail}

La nuova pagina dei dettagli delle connessioni fornisce una visualizzazione molto dettagliata dello stato di una connessione.

Consente di:

* Controlla lo stato dei set di dati della connessione e del processo di acquisizione.
* Identifica i problemi di configurazione che portano a record saltati o eliminati.
* Vedi quando i dati sono disponibili per il reporting.

>[!IMPORTANT]
>Eventuali dati acquisiti prima del 13 agosto 2021 non vengono riflessi in questo [!UICONTROL Connections] finestra di dialogo.

Ecco i widget e le impostazioni spiegate:

![Visualizza dettagli connessione](assets/conn-details.png)

| Widget/Impostazione | Descrizione |
| --- | --- |
| Selettore set di dati | Consente di scegliere uno o tutti i set di dati della connessione. Non è possibile selezionare più set di dati. Predefinito su [!UICONTROL All datasets]. |
| Calendario/Intervalli di date | L’intervallo di date indica quando hai aggiunto dati alla connessione. Sono inclusi tutti i predefiniti calendario standard. Puoi personalizzare l’intervallo di date, ma nel menu a discesa non viene visualizzato alcun intervallo di date personalizzato. |
| [!UICONTROL Records of event data available] widget | Rappresenta il numero totale di righe del set di dati evento disponibili per il reporting, **per l&#39;intera connessione**. Questo conteggio è indipendente da qualsiasi impostazione del calendario. Cambia se selezioni un set di dati dal selettore o selezionando un set di dati nella tabella. (Tieni presente che, una volta aggiunto, i dati vengono visualizzati nel rapporto con una latenza di 1-2 ore.) |
| [!UICONTROL Metrics] widget | Riepiloga i record evento aggiunti/saltati/eliminati e il numero di batch aggiunti, **per il set di dati e l’intervallo di date selezionati**. |
| [!UICONTROL Records added] widget | Indica quante righe sono state aggiunte nel periodo di tempo selezionato, **per il set di dati e l’intervallo di date selezionati**. Aggiornato ogni 10 minuti. **Nota**: Dati per **[!UICONTROL Records added]** include solo i dati evento al momento, non i dati di profilo o di ricerca. |
| [!UICONTROL Records skipped] widget | Indica quante righe sono state saltate nel periodo di tempo selezionato, **per il set di dati e l’intervallo di date selezionati**. I motivi per cui i record vengono ignorati sono i seguenti: Marca temporale mancante, ID persona mancante o non valido, ecc. Aggiornato ogni 10 minuti.<p>Gli ID persona non validi (non definiti, tutti gli zeri) non possono essere attribuiti a un utente o a una persona specifici. Non possono essere acquisiti nel sistema e comportano processi di inserimento e reporting soggetti a errori. Per correggere gli ID persona non validi, sono disponibili 3 opzioni:<ul><li>Utilizzare l’unione per popolare gli ID utente non definiti o tutti gli ID utente con ID utente validi.</li><li>Rimuovi l’ID utente, che verrà ignorato anche durante l’acquisizione (da preferire agli ID utente non validi o tutti gli ID zero).</li><li>Correggi eventuali ID utente non validi nel sistema prima di acquisire i dati.</li></ul><p>**Nota**: Dati per **[!UICONTROL Records skipped]** include solo i dati evento al momento, non i dati di profilo o di ricerca. |
| [!UICONTROL Records deleted] widget | Indica quante righe sono state eliminate nel periodo di tempo selezionato, **per il set di dati e l’intervallo di date selezionati**. Ad Experience Platform, qualcuno potrebbe aver eliminato un set di dati. Aggiornato ogni 10 minuti. **Nota**: Dati per **[!UICONTROL Records deleted]** include solo i dati evento al momento, non i dati di profilo o di ricerca. |
| Casella di ricerca set di dati | Puoi eseguire ricerche per nome set di dati o [!UICONTROL Dataset ID]. |
| [!UICONTROL Datasets] | Mostra i set di dati che fanno parte della connessione. È possibile fare clic sul collegamento ipertestuale per visualizzare tutti i set di dati presenti nella connessione. |
| [!UICONTROL Dataset ID] | Questo ID viene generato automaticamente da Adobe Experience Platform. |
| [!UICONTROL Batches] | Indica quanti batch di dati sono stati aggiunti a questo set di dati. |
| [!UICONTROL Last added] | Mostra la marca temporale dell&#39;ultimo batch aggiunto a questo set di dati. |
| [!UICONTROL Dataset type] | Il tipo di set di dati per questo set di dati può essere [!UICONTROL Event], [!UICONTROL Lookup]oppure [!UICONTROL Profile]. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| Schema | Lo schema Adobe Experience Platform su cui si basano i set di dati in questa connessione. |
| **Barra a destra a livello di connessione** |  |
| [!UICONTROL Refresh] | Aggiorna la connessione per consentire la visualizzazione dei record aggiunti di recente. |
| [!UICONTROL Delete] | Elimina la connessione. |
| [!UICONTROL Create data view] | Crea una nuova visualizzazione dati basata su questa connessione. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Connection name] | Mostra il nome descrittivo della connessione. |
| [!UICONTROL Connection description] | Mostra una descrizione più dettagliata che descrive idealmente lo scopo di questa connessione. |
| [!UICONTROL Sandbox] | La [Sandbox Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) da cui questa connessione attinge i relativi set di dati. Questa sandbox è stata selezionata al momento della creazione della connessione. Non può essere cambiato. |
| [!UICONTROL Connection ID] | Questo ID è generato dal sistema in Adobe Experience Platform. |
| [!UICONTROL Data views using connection] | Elenca tutte le visualizzazioni dati che utilizzano questa connessione. |
| [!UICONTROL Import new data] | (On/Off) Indica se è necessario aggiungere o meno nuovi batch di dati ai dati storici (backfill). |
| [!UICONTROL Backfill data] | I dati di backfill (storici) vengono tracciati in 3 stati: [!UICONTROL In queue], [!UICONTROL In progress] (con percentuale di avanzamento indicata), e [!UICONTROL Complete]. |
| [!UICONTROL Created by] | Mostra il nome della persona che ha creato la connessione. |
| [!UICONTROL Last modified] | Mostra la data e l’ora dell’ultima modifica apportata alla connessione. |
| [!UICONTROL Last modified by] | Mostra l&#39;ultimo utente che ha modificato la connessione. |
| **Barra a destra a livello di set di dati** |  |
| [!UICONTROL Person ID] | Mostra un&#39;identità definita nello schema del set di dati nell&#39;Experience Platform. Questo è l’ID persona scelto durante la creazione della connessione. Se crei una connessione che include set di dati con ID diversi, il reporting lo rifletterà. Per unire in modo efficace i set di dati, è necessario utilizzare lo stesso ID persona nei set di dati. |
| [!UICONTROL Records available] | Rappresenta il numero totale di righe acquisite per questo set di dati, per il particolare periodo di tempo selezionato nel calendario. Non esiste alcuna latenza in termini di visualizzazione dei dati nel reporting, una volta aggiunti. (L’eccezione è che quando crei una connessione nuova, ci sarà [latenza](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=it#3.-introduzione di dati nell’analisi del percorso cliente). |
| [!UICONTROL Records added] | Indica quante righe sono state aggiunte nel periodo di tempo selezionato. **Nota**: Dati per **[!UICONTROL Records added]** include solo i dati evento al momento, non i dati di profilo o di ricerca. |
| [!UICONTROL Records deleted] | Indica quanti record sono stati eliminati durante il periodo di tempo selezionato. **Nota**: Dati per **[!UICONTROL Records deleted]** include solo i dati evento al momento, non i dati di profilo o di ricerca. |
| [!UICONTROL Batches added] | Indica quanti batch di dati sono stati aggiunti al set di dati. |
| [!UICONTROL Records skipped] | Indica quante righe sono state saltate durante l’acquisizione nel periodo di tempo selezionato.<p>Gli ID persona non validi (non definiti, tutti gli zeri) non possono essere attribuiti a un utente o a una persona specifici. Non possono essere acquisiti nel sistema e comportano processi di inserimento e reporting soggetti a errori. Per correggere gli ID persona non validi, sono disponibili 3 opzioni:<ul><li>Utilizzare l’unione per popolare gli ID utente non definiti o tutti gli ID utente con ID utente validi.</li><li>Rimuovi l’ID utente, che verrà ignorato anche durante l’acquisizione (da preferire agli ID utente non validi o tutti gli ID zero).</li><li>Correggi eventuali ID utente non validi nel sistema prima di acquisire i dati.</li></ul><p>**Nota**: Dati per **[!UICONTROL Records skipped]** include solo i dati evento al momento, non i dati di profilo o di ricerca. |
| [!UICONTROL Last added] | Indica quando è stato aggiunto l&#39;ultimo batch. |
| [!UICONTROL Dataset type] | O [!UICONTROL Event], [!UICONTROL Lookup]oppure [!UICONTROL Profile]. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| [!UICONTROL Schema] | Mostra lo schema Adobe Experience Platform su cui si basa il set di dati. |
| [!UICONTROL Dataset ID] | Questo ID è generato dal sistema in Adobe Experience Platform. |

### Modifica connessione

Consente agli amministratori di modificare la connessione. Seleziona una connessione, quindi fai clic su [!UICONTROL Edit Connection] per accedere a questa finestra di dialogo. Qui puoi effettuare le seguenti operazioni:

* Avviare e interrompere l&#39;importazione di nuovi dati. Questo processo era precedentemente noto come &quot;streaming di dati&quot;.
* Rinominare una connessione.
* Aggiorna i set di dati.
* Rimuovi i set di dati dalle connessioni.

## Imposta finestra di scorrimento per [!UICONTROL Connection] conservazione dei dati

>[!IMPORTANT]
>Contatta l’Assistenza clienti o il tuo responsabile commerciale Adobe per far sì che questa impostazione sia implementata. Non è ancora disponibile tramite l’interfaccia utente di CJA.

Questa impostazione ti consente di definire la conservazione dei dati CJA come una finestra continua in mesi (3 mesi, 6 mesi, ecc.), alla volta [!UICONTROL connection] (non a un livello [!UICONTROL dataset] livello). La conservazione dei dati si basa sulle marche temporali dei set di dati dell’evento e si applica solo ai set di dati dell’evento. Non esiste alcuna impostazione di conservazione dei dati per i set di dati di profilo o di ricerca, in quanto non sono disponibili marche temporali applicabili. Il vantaggio principale consiste nell’archiviare o generare rapporti solo sui dati applicabili e utili, nonché nell’eliminare i dati meno recenti che non sono più utili. Ti aiuta a rispettare i limiti del tuo contratto e riduce il rischio di sovraccosti.