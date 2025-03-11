---
title: Creare uno schema per Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 22d3e7b8-4a4d-48a8-a98d-5172a9876286
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1510'
ht-degree: 93%

---

# Creare e configurare una connessione da utilizzare con Customer Journey Analytics {#upgrade-create-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-connection"
>title="Creare una connessione in Customer Journey Analytics"
>abstract="Una connessione consente di tradurre i dati di Adobe Experience Platform in un formato ottimizzato per il reporting di Customer Journey Analytics. La creazione di una connessione in Customer Journey Analytics è semplice e richiede solo pochi minuti per essere completata."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/connections/create-connection.md -->

Le informazioni seguenti spiegano come creare e configurare una connessione e come aggiungere set di dati di Experience Platform alla connessione creata. Per ulteriori informazioni sulla creazione e la configurazione di una connessione, vedere [Creare o modificare una connessione](/help/connections/create-connection.md).

## Creare e configurare la connessione {#create-connection}

1. In Customer Journey Analytics, seleziona la scheda **[!UICONTROL Connections]**.
1. Seleziona **[!UICONTROL Create new connection]**.

   ![Impostazioni di connessione senza titolo](assets/create-conn1.png)

1. Configura le impostazioni della connessione.

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Connection name]** | Assegna un nome univoco alla connessione. |
   | **[!UICONTROL Connection description]** | Descrivi lo scopo della connessione. |
   | **[!UICONTROL Sandbox]** | Scegli una sandbox in Experience Platform che contiene i set di dati per cui desideri creare una connessione.<p>Adobe Experience Platform fornisce [sandbox](https://experienceleague.adobe.com/it/docs/experience-platform/sandbox/home) che permettono di suddividere una singola istanza Platform in ambienti virtuali separati, utili per le attività di sviluppo e aggiornamento delle applicazioni di esperienza digitale. Puoi considerare le sandbox come “silos di dati” che contengono set di dati. Le sandbox vengono utilizzate per controllare l’accesso ai set di dati.<p>Dopo aver selezionato la sandbox, la barra a sinistra mostra tutti i set di dati nella sandbox da cui puoi richiamarli. |
   | **[!UICONTROL Enable rolling data window]** | La casella di controllo, se selezionata, consente di definire un’impostazione di conservazione dei dati di Customer Journey Analytics come finestra continua in mesi (1 mese, 3 mesi, 6 mesi, ecc.), a livello di connessione.<p>La conservazione dei dati si basa sulle marche temporali dei set di dati dell’evento e si applica solo ai set di dati dell’evento. Non esiste alcuna impostazione di finestra continua per i set di dati di profilo o di ricerca, in quanto non sono disponibili marche temporali applicabili. Tuttavia, se la connessione include un profilo o set di dati di ricerca (oltre a uno o più set di dati evento), tali dati verranno conservati per lo stesso periodo di tempo.<p> Il vantaggio principale consiste nell’archiviare o generare rapporti solo sui dati applicabili e utili, nonché nell’eliminare i dati meno recenti che non sono più utili. Ti aiuta a rispettare i limiti del tuo contratto e riduce il rischio di sovraccosti.<p>Se lasci l’impostazione predefinita (non selezionata), il periodo di conservazione viene sostituito dall’impostazione di conservazione dei dati di Adobe Experience Platform. Se disponi di un valore di 25 mesi di dati in Experience Platform, Customer Journey Analytics può ottenere 25 mesi di dati tramite retrocompilazione. Eliminando10 di questi mesi in Platform, Customer Journey Analytics mantiene i restanti 15 mesi. |
   | **[!UICONTROL Add datasets]** (vedi di seguito) | Aggiungi i set di dati se nell’elenco dei set di dati non sono presenti set di dati. |
   | **[!UICONTROL Dataset name]** | Seleziona uno o più set di dati da richiamare in Customer Journey Analytics e seleziona **[!UICONTROL Add]**.<p>Se sono presenti molti set di dati tra cui scegliere, puoi cercare quelli giusti utilizzando la barra di ricerca apposita sopra l’elenco dei set di dati. |
   | **[!UICONTROL Last updated]** | Solo per i set di dati evento, questa impostazione viene impostata automaticamente sul campo marca temporale predefinito dagli schemi basati su eventi in Experience Platform. “N/A” significa che il set di dati non contiene dati. |
   | **[!UICONTROL Number of records]** | Totale dei record del mese precedente per il set di dati in Experience Platform. |
   | **[!UICONTROL Schema]** | [Schema](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/schema/composition) in base al quale è stato creato il set di dati in Adobe Experience Platform. |
   | **[!UICONTROL Dataset type]** | Per ogni set di dati aggiunto alla connessione, Customer Journey Analytics imposta automaticamente il tipo di set di dati in base ai dati in arrivo. Esistono 3 tipi diversi di set di dati: dati evento, dati profilo e dati di ricerca. Nella tabella seguente puoi trovare una spiegazione dei tipi di set di dati. |
   | **[!UICONTROL Granularity]** | La granularità dei dati nel set di dati; applicabile solo per i set di dati di riepilogo. |
   | **[!UICONTROL Data source type]** | Il tipo di origine dati del set di dati. Non applicabile per i set di dati di riepilogo. |
   | **[!UICONTROL Person ID]** | Seleziona un ID persona dall’elenco a discesa delle identità disponibili. Queste identità sono state definite nello schema del set di dati in Experience Platform. Vedi di seguito per informazioni su come utilizzare Identity Map come ID persona.<p>IMPORTANTE: se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Guarda [questo video](https://www.youtube.com/watch?v=G_ttmGl_LRU) su come definire un’identità in Experience Platform. |
   | **[!UICONTROL Key]** | Solo per i set di dati di ricerca (ad esempio _id). |
   | **[!UICONTROL Matching Key]** | Solo per i set di dati di ricerca (ad esempio _id). |
   | **[!UICONTROL Import new data]** | Imposta su On o Off. |
   | **[!UICONTROL Backfill data]** | Puoi richiedere di eseguire la retrocompilazione dei dati in un set di dati. Ad esempio, puoi richiedere di eseguire la retrocompilazione degli ultimi 7 giorni di dati. Configura il set di dati correttamente e verifica la connessione. Se tutto sembra a posto, puoi eseguire facilmente il backfill di tutti i dati rimanenti.<p>Inoltre, puoi abilitare l’importazione di nuovi dati per set di dati. |
   | **[!UICONTROL Backfill status]** | Questo stato indica se vengono elaborati dati di retrocompilazione. |

   {style="table-layout:auto"}

## Aggiungere e configurare i set di dati {#add-dataset}

Puoi aggiungere un set di dati di Experience Platform quando crei una connessione.

1. Nella finestra di dialogo Impostazioni della connessione, seleziona **[!UICONTROL Add datasets]**.

1. Nel passaggio [!UICONTROL Select datasets] viene visualizzato un elenco dei set di dati di Experience Platform.

   ![Selezionare un set di dati](assets/select-datasets.png)

   Per ogni set di dati, l’elenco mostra:

   | Colonna | Descrizione |
   |---|---|
   | Set di dati | Nome del se di dati. Seleziona il nome per indirizzarti al set di dati in Experience Platform. Seleziona ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) per visualizzare un pop-up con ulteriori dettagli per il set di dati. Puoi selezionare **[!UICONTROL Edit in Platform]** per modificare il set di dati direttamente in Experience Platform. |
   | Tipo di set di dati | Tipo di set di dati: evento, profilo, ricerca e riepilogo. |
   | Numero di record | Totale dei record del mese precedente per il set di dati in Experience Platform. |
   | Schema | Lo schema per il set di dati. Seleziona il nome per indirizzarti allo schema in Experience Platform. |
   | Ultimo batch | Stato dell’ultimo batch acquisito in Experience Platform. Per ulteriori informazioni, consulta [Stati batch](https://experienceleague.adobe.com/it/docs/experience-platform/ingestion/batch/troubleshooting#batch-states). |
   | ID set di dati | ID del set di dati. |
   | Ultimo aggiornamento | Marca temporale dell’ultimo aggiornamento del set di dati. |


1. Seleziona uno o più set di dati e seleziona **[!UICONTROL Next]**. Deve far parte della connessione almeno un set di dati evento.
   * Per modificare le colonne visualizzate per l’elenco dei set di dati, seleziona ![Impostazioni colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) e seleziona le colonne da visualizzare nella finestra di dialogo [!UICONTROL Customize table].
   * Per cercare un set di dati specifico, utilizza il campo di ricerca ![Cerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).
   * Per scegliere tra visualizzare o nascondere i set di dati selezionati, utilizza ![Seleziona](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg) **[!UICONTROL Hide selected]** o **[!UICONTROL Show selected]**.
   * Per rimuovere un set di dati dall’elenco dei set di dati selezionati, utilizza ![Chiudi](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg). Per rimuovere tutti i set di dati selezionati, seleziona **[!UICONTROL Clear all]**.




1. Ora configura singolarmente ciascun set di dati.

   ![Configurare i set di dati](assets/add-dataset.png)

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Person ID]** | Disponibile solo per i set di dati evento e profilo. Seleziona un ID persona dall’elenco a discesa delle identità disponibili. Queste identità sono state definite nello schema del set di dati in Experience Platform. Vedi di seguito per informazioni su come utilizzare Identity Map come ID persona.<p>Se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Consulta [Definire i campi di identità nell’interfaccia utente](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/identity) per ulteriori informazioni. <p>Il valore per l’ID persona selezionato è considerato sensibile a maiuscole e minuscole. Ad esempio: `abc123` e `ABC123` sono due valori diversi. |
   | **[!UICONTROL Timestamp]** | Solo per i set di dati evento e riepilogo, questa impostazione viene settata automaticamente sul campo marca temporale predefinito dagli schemi basati su eventi in Experience Platform. |
   | **[!UICONTROL Key]** | Disponibile solo per i set di dati di ricerca. Chiave da utilizzare per un set di dati di ricerca. |
   | **[!UICONTROL Matching key]** | Disponibile solo per i set di dati di ricerca. Chiave corrispondente per partecipare a uno dei set di dati dell’evento. Se questo elenco è vuoto, probabilmente non hai aggiunto o configurato un set di dati evento. |
   | **[!UICONTROL Timezone]** | Disponibile solo per i dati di riepilogo. Seleziona il fuso orario appropriato per i dati di riepilogo delle serie temporali. |
   | **[!UICONTROL Data source type]** | Seleziona un tipo di origine dati. <br/>I tipi di origini dati includono: <ul><li>[!UICONTROL Web data]</li><li>[!UICONTROL Mobile App data]</li><li>[!UICONTROL POS data]</li><li>[!UICONTROL CRM data]</li><li>[!UICONTROL Survey data]</li><li>[!UICONTROL Call Center data]</li><li>[!UICONTROL Product data]</li><li> [!UICONTROL Accounts data]</li><li> [!UICONTROL Transaction data]</li><li>[!UICONTROL Customer Feedback data]</li><li> [!UICONTROL Other]</li></ul>Questo campo viene utilizzato per esaminare i tipi di origini dati in uso. |
   | **[!UICONTROL Import new data]** | Attiva questa opzione se desideri stabilire una connessione continua. Con una connessione continua, i nuovi batch di dati aggiunti ai set di dati sono disponibili automaticamente in Workspace. |
   | **[!UICONTROL Dataset backfill]** | Abilita **[!UICONTROL Backfill all existing data]** per garantire la retrocompilazione di tutti i dati esistenti.<br/><br/>Seleziona **[!UICONTROL Request backfill]** per eseguire la retrocompilazione dei dati storici per un periodo specifico. Puoi definire fino a 10 periodi di retrocompilazione dei set di dati.<ol><li>Definisci il periodo immettendo i dati di inizio e fine o selezionando le date utilizzando il ![Calendario](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).</li><li>Seleziona **[!UICONTROL Queue backfill]** per aggiungere la retrocompilazione all’elenco, oppure **[!UICONTROL Cancel]** per annullare.</li></ol>Per ogni voce, seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) per modificare il periodo oppure ![Elimina](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) per eliminare la voce.<br/><br/>Informazioni sulle retrocompilazioni:<ul><li>È possibile eseguire la retrocompilazione di ogni set di dati singolarmente.</li><li>Dai priorità ai nuovi dati aggiunti a un set di dati nella connessione in modo che questi dati abbiano la latenza più bassa.</li><li>Eventuali dati di retrocompilazione (storici) vengono importati a una velocità più bassa. La quantità di dati storici influenza la latenza.</li><li>Il connettore origine di Analytics importa fino a 13 mesi di dati (indipendentemente dalle dimensioni) per le sandbox di produzione. La retrocompilazione nelle sandbox non di produzione è limitata a 3 mesi.</li></ul> |
   | **[!UICONTROL Transform dataset]** | Per set di dati di ricerca B2B specifici, puoi abilitare la trasformazione di un set di dati per scenari di reporting appropriati basati su persone B2B. |
   | **[!UICONTROL Backfill status]** | Gli indicatori di stato possibili sono:<ul><li>Success (Operazione riuscita)</li><li>X backfill(s) processing (Elaborazione di X retrocompilazioni)</li><li>Off</li></ul> |
   | **[!UICONTROL Dataset ID]** | Questo ID viene generato automaticamente. |
   | **[!UICONTROL Description]** | Descrizione specificata quando è stato creato il set di dati. |
   | **[!UICONTROL Dataset size]** | Dimensione del set di dati. |
   | **[!UICONTROL Schema]** | Schema sulla cui base è stato creato il set di dati in Adobe Experience Platform. |
   | **[!UICONTROL Dataset]** | Nome del set di dati. |
   | **[!UICONTROL Preview: *nome del set di dati *]** | Visualizza in anteprima il set di dati con le colonne Data, ID personale e Identificatore. |
   | **[!UICONTROL Remove]** | Puoi eliminare o rimuovere il set di dati e modificare l’ID persona senza eliminare l’intera connessione. L’eliminazione o la rimozione riduce i costi associati all’acquisizione dei dati e il complicato processo di ricreazione dell’intera connessione e delle visualizzazioni dati associate. |

   {style="table-layout:auto"}

{{upgrade-final-step}}
