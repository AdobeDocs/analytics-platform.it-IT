---
title: Gestire Le Connessioni In Customer Journey Analytics
description: Scopri come gestire le connessioni ai set di dati di Experience Platform in Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
autotag-review: '2026-05-19T08:50:02.853Z'
TQID: 'https://experienceleague.adobe.com/iJ5jp3wtWSrJzCnJqIceIHwwLideF-U2puXvit5GFac'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 88ff7c4124d4612a3411b315a605aec29bc9a218
workflow-type: tm+mt
source-wordcount: 7300
ht-degree: 87%

---

# Gestire le connessioni {#manage-connections}

>[!CONTEXTUALHELP]
>id="connections_use_ajo"
>title="Utilizzare la connessione di Journey Optimizer"
>abstract="Sfrutta le funzionalità avanzate di reporting di Customer Journey Analytics con Journey Optimizer."

>[!CONTEXTUALHELP]
>id="connections_cancel_ajo"
>title="Annullare la connessione di Journey Optimizer"
>abstract="Annulla le funzionalità avanzate di reporting di Customer Journey Analytics con Journey Optimizer."


Dopo aver [creato o modificato una o più connessioni](/help/connections/create-connection.md), puoi gestirle in **[!UICONTROL Connessioni]**. L&#39;interfaccia [!UICONTROL Connections] consente di:

* Visualizza tutte le connessioni, inclusi il proprietario, la sandbox e quando sono state create e modificate.
* Modificare una connessione.
* Eliminare una connessione.
* Creare una visualizzazione dati a partire da una connessione.
* Visualizza tutti i set di dati in una connessione.
* Controllare lo stato dei set di dati della tua connessione e del processo di acquisizione. Ad esempio, la disponibilità dei dati in modo da poter iniziare con il reporting e l’analisi in Analysis Workspace.
* Identifica eventuali discrepanze di dati dovute a configurazione errata. Vi mancano delle righe? In caso affermativo, quali righe mancano e perché? Hai configurato in modo errato le connessioni e causato la mancanza di dati in Customer Journey Analytics?
* Ottieni informazioni sull’utilizzo delle righe acquisite e segnalabili in tutte le connessioni.

[!UICONTROL Le connessioni] dispongono di due interfacce: [[!UICONTROL Elenco]](#list) e [[!UICONTROL Utilizzo]](#usage).


## Elenco

L’interfaccia **[!UICONTROL Elenco]** è l’interfaccia predefinita per Connessioni. Se non è selezionata, seleziona la scheda **[!UICONTROL Elenco]** per accedere all’interfaccia.

L&#39;interfaccia **[!UICONTROL List]** mostra una tabella di tutte le connessioni disponibili.
△
![visualizzazione elenco](assets/list-view.png)

Nella tabella sono disponibili le colonne o le icone seguenti.

| Colonna o icona | Descrizione |
| --- | --- |
| **[!UICONTROL _Nome_]** | Il nome descrittivo della connessione. Seleziona il nome con collegamento ipertestuale per visualizzare i [dettagli della connessione](#connection-details). |
| ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Per visualizzare le informazioni su [!UICONTROL Set di dati inclusi], [!UICONTROL Sandbox], [!UICONTROL Proprietario] e altro ancora, seleziona ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) accanto al nome della connessione.<p>Una finestra a comparsa mostra i dettagli sul set di dati. <p>![Finestra a comparsa con informazioni sulla connessione](assets/connection-info-popup.png) |
| ![Visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Per [creare una visualizzazione dati](#create-a-data-view) per la connessione, seleziona ![Visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). Questa icona viene visualizzata solo se alla connessione non è già associata alcuna visualizzazione dati. |
| ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) per aprire un menu di scelta rapida. Puoi selezionare: <p>![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifica]** per [modificare](#edit-a-connection) una connessione.<p>![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Elimina]** per [eliminare](#delete-a-connection) una connessione.<p>![Visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Crea nuova visualizzazione dati]** per [creare una nuova visualizzazione dati](#create-a-data-view) per la connessione.<p>![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Mappa connessione]** per visualizzare una [mappa della connessione](#map-a-connection) per la connessione. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Tipo di connessione &#x200B;]** | Il tipo di connessione: **[!UICONTROL Connessione basata su Persona]** o **[!UICONTROL Connessione basata su Account]**. |
| **[!UICONTROL Set di dati]** | Uno o più collegamenti ai set di dati che fanno parte della connessione. Puoi selezionare il collegamento ipertestuale del set di dati per visualizzare il set di dati nella connessione. Se della connessione selezionata fanno parte più set di dati, seleziona **[!UICONTROL +*x* più]** per visualizzare un pannello **[!UICONTROL Set di dati inclusi]**. Questo pannello mostra i collegamenti a tutti i set di dati e l’opzione ![Ricerca](/help/assets/icons/Search.svg), che consente di cercare un set di dati specifico che fa parte della connessione.<p>![Set di dati inclusi](assets/datasets-included.png)<p>Seleziona un nome per un set di dati per aprire il set di dati nell’interfaccia utente di Experience Platform in una nuova scheda. |
| **[!UICONTROL Sandbox]** | La [sandbox di Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/sandbox/home) da cui questa connessione estrae i relativi set di dati. Selezioni questa sandbox al momento della creazione della connessione. Una volta salvata una connessione, non è possibile modificare la sandbox. |
| **[!UICONTROL Proprietario]** | La persona che ha creato la connessione. |
| **[!UICONTROL Importa nuovi dati]** | Stato dell’importazione di nuovi dati per i set di dati: <p>![Stato attivo](assets/status-green.svg)   **[!UICONTROL _x _Attivo]**&#x200B;per i set di dati configurati per l’importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Disattivato_]** per i set di dati non configurati per l’importazione di nuovi dati. |
| **[!UICONTROL Data creazione]** | La marca temporale della creazione della connessione. |
| **[!UICONTROL Ultima modifica]** | La marca temporale dell’ultimo aggiornamento della connessione. |
| **[!UICONTROL Retrocompilazione dei dati]** | Stato dei dati di retrocompilazione tra set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _retrocompilazioni non riuscite]**&#x200B;per il numero di retrocompilazioni non riuscite tra set di dati,<p>![Stato arancione](assets/status-orange.svg)   **[!UICONTROL _x _retrocompilazioni in elaborazione]**&#x200B;per il numero di retrocompilazioni in elaborazione tra set di dati,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _retrocompilazioni completate]**&#x200B;per il numero di retrocompilazioni completate per i set di dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** nel caso in cui non siano definite retrocompilazioni per i set di dati nella connessione. |
| **[!UICONTROL Integrazioni]** | Mostra tutte le applicazioni Experience Platform abilitate con la connessione. |
| **[!UICONTROL Utilizza in CJA]** | Mostra se la connessione è stata abilitata per l’utilizzo con Customer Journey Analytics. |

Per configurare le colonne da visualizzare nella tabella, seleziona ![Impostazioni colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Nella finestra di dialogo **[!UICONTROL Personalizza tabella]**, seleziona le colonne da visualizzare. Quindi selezionare **[!UICONTROL Applica]**.

### Cerca connessioni

Puoi cercare rapidamente le connessioni utilizzando la casella ![Cerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

### Filtra connessioni

Per applicare un filtro all&#39;elenco delle connessioni, selezionare ![Filtro](/help/assets/icons/Filter.svg). Quindi seleziona una delle seguenti opzioni di filtro:

| Opzione filtro | Descrizione |
|---------|----------|
| **[!UICONTROL Set di dati]** | Vengono visualizzate solo le connessioni associate ai set di dati selezionati. |
| **[!UICONTROL Proprietario]** | Vengono visualizzate solo le connessioni di proprietà delle persone selezionate. |
| **[!UICONTROL Sandbox]** | Vengono visualizzate solo le connessioni disponibili nelle sandbox selezionate. |
| **[!UICONTROL Tipo connessione]** | Filtra le connessioni [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} basate su **[!UICONTROL persona]** o **[!UICONTROL account]**. |
| **[!UICONTROL Utilizza in CJA]** | Seleziona **[!UICONTROL Attive]** per visualizzare solo le connessioni abilitate per l’utilizzo con Customer Journey Analytics. Seleziona **[!UICONTROL Non attive]** per visualizzare solo le connessioni non ancora abilitate per l’utilizzo con Customer Journey Analytics. |
| **[!UICONTROL Integrazioni]** | Vengono visualizzate solo le connessioni con le integrazioni selezionate. |

Seleziona ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Nascondi filtri]** per nascondere il riquadro dei filtri.

### Modificare una connessione

Per modificare una connessione:

1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione
1. Seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifica]** dal menu di scelta rapida.

In alternativa, puoi:

1. Controllare l’URL della connessione.

1. Seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifica]** dalla barra delle azioni blu.

Per ulteriori informazioni, consulta [Creare o modificare una connessione](create-connection.md).


### Eliminare una connessione {#connections-delete}

Per eliminare una connessione:

1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione.
1. Seleziona ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Elimina]**.

In alternativa, puoi:

1. Controllare l’URL della connessione.

1. Seleziona ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Elimina]** dalla barra delle azioni blu.

Quando elimini una connessione, un pannello **[!UICONTROL Elimina connessione]** indica le visualizzazioni dati eliminate e i progetti dell’area di lavoro interessati.

* In ➊ **[!UICONTROL Informazioni]** sono mostrate le implicazioni dell’eliminazione della connessione.

  ![Elimina connessione](assets/delete-connection.png)

  Seleziona **[!UICONTROL Continua]** per confermare l’eliminazione.

* In ➋ **[!UICONTROL Conferma]**, inserisci il nome della connessione in **[!UICONTROL Digita il nome della connessione]** e seleziona **[!UICONTROL Elimina]** per eliminare la connessione. Seleziona **[!UICONTROL Annulla]** per annullare.

Per ulteriori informazioni sull’eliminazione di una connessione, consulta [Implicazioni dell’eliminazione](/help/technotes/deletion.md).


### Creare una visualizzazione dati per una connessione

Per creare una visualizzazione dati per una connessione:

1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione.
1. Seleziona ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Crea nuova visualizzazione dati]**.

In alternativa, puoi:

1. Controllare l’URL della connessione.

1. Seleziona ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Crea visualizzazione dati]** dalla barra delle azioni blu.

Per ulteriori informazioni, consulta [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md).

### Connessioni Journey Optimizer

È possibile utilizzare una connessione Journey Optimizer in Customer Journey Analytics per fornire il seguente valore aggiuntivo alla connessione:

* Esegui analisi approfondite dei dati Journey Optimizer in Customer Journey Analytics, utilizzando il pulsante **[!UICONTROL Analizza in CJA]** in Journey Optimizer.

  Per ulteriori informazioni, vedere [Analizzare in Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/reporting/channel-report/report-cja-manage#cja-template).

* Modificare la connessione Journey Optimizer e le visualizzazioni dati associate.

  Per ulteriori informazioni sulle opzioni di modifica, consulta [Modificare una connessione](#edit-a-connection).


>[!IMPORTANT]
>
>Quando abiliti una connessione Journey Optimizer per Customer Journey Analytics, ogni riga conta per le righe con licenza mensile e viene visualizzata nell’interfaccia utente di utilizzo delle connessioni. Seleziona l’opzione **[!UICONTROL Utilizza in CJA]** sulla connessione solo se sei certo dell’ulteriore utilizzo di righe di dati in Customer Journey Analytics.
>
>**Se disponevi dei diritti per Customer Journey Analytics e Journey Optimizer tra ottobre 2024 e ottobre 2025, consulta il seguente documento sulle [Connessioni abilitate per AJO](https://view.adobe.com/viewer/1ed94fc35c7860b260766c620889e7a0#1)**.

Per abilitare questa funzionalità, la tua organizzazione deve accedere a Customer Journey Analytics. Se non disponi dell’accesso, contatta il tuo rappresentante commerciale Adobe.

#### Utilizzare la connessione Journey Optimizer {#use-connection-in-cja}

Per utilizzare una connessione Journey Optimizer in Customer Journey Analytics:

1. Individua la connessione Journey Optimizer che desideri utilizzare con Customer Journey Analytics.

   1. Seleziona ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]** nella scheda **[!UICONTROL Connessioni]**.

   1. Nella sezione **[!UICONTROL Utilizza in CJA]**, seleziona **[!UICONTROL Disattiva]**.

      Vengono visualizzate tutte le connessioni Journey Optimizer attualmente non configurate per l&#39;utilizzo in Customer Journey Analytics.

      ![Filtra per mostrare le connessioni non abilitate per AJO](assets/remove-ajo-connection.png)

1. Seleziona il nome della connessione Journey Optimizer.

1. Seleziona ![UsersShare](/help/assets/icons/UseInCJA.svg) **[!UICONTROL Utilizza in CJA]**.

   ![Pulsante Utilizza in CJA](assets/connection-use-in-cja.png)

   Viene visualizzata la finestra di dialogo **[!UICONTROL Utilizza questa connessione in Customer Journey Analytics]**.

1. Abilita il pulsante di attivazione, **[!UICONTROL Utilizza la connessione in CJA]**.

1. Seleziona **[!UICONTROL Utilizza la connessione]**. <!-- double-check these dialog button names -->

#### Rimuovere una connessione Journey Optimizer {#remove-connection-in-cja}

Puoi rimuovere una connessione Journey Optimizer da Customer Journey Analytics in qualsiasi momento. Tuttavia, la rimozione della connessione da Customer Journey Analytics dopo il suo utilizzo comporta quanto segue:

* La connessione Journey Optimizer ed eventuali visualizzazioni dati associate vengono ripristinate allo stato predefinito e non possono più essere modificate

* Tutti i campi derivati personalizzati associati alla connessione vengono eliminati.

* Non puoi più eseguire un’analisi approfondita dei dati di Journey Optimizer all’interno di Customer Journey Analytics.

  Ciò significa che il pulsante **[!UICONTROL Analizza in CJA]** all&#39;interno di Journey Optimizer viene disabilitato.

>[!IMPORTANT]
>
>La fatturazione per questa connessione in Customer Journey Analytics include l’intero mese durante il quale la connessione viene rimossa.


Per rimuovere questa connessione da Customer Journey Analytics:

1. Individua la connessione Journey Optimizer che intendi rimuovere da Customer Journey Analytics.

   1. Seleziona ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]** nella scheda **[!UICONTROL Connessioni]**.

   1. Nella sezione **[!UICONTROL Utilizza in CJA]**, seleziona **[!UICONTROL Attive]**.

      Vengono visualizzate tutte le connessioni Journey Optimizer attualmente configurate per l&#39;utilizzo in Customer Journey Analytics.

      ![Filtra per visualizzare le connessioni abilitate per AJO](assets/enabled-ajo-connection.png)

1. Per visualizzare la connessione, seleziona il nome della connessione Journey Optimizer che intendi rimuovere da Customer Journey Analytics.

1. Quando si visualizza la connessione Journey Optimizer, seleziona **[!UICONTROL Rimuovi da CJA]**.

   Viene visualizzata la finestra di dialogo **[!UICONTROL Rimuovi questa connessione da Customer Journey Analytics]**:

   ![Pulsante Rimuovi da CJA](assets/connection-remove-from-cja.png)

1. Disabilita l&#39;opzione **[!UICONTROL Rimuovi la connessione da CJA]**.

1. Seleziona **[!UICONTROL Rimuovi connessione]**.

### Mappare una connessione

Per visualizzare una [mappa di connessione](/help/connections/create-connection.md#connection-map) che descrive le relazioni tra i set di dati che fanno parte di una connessione:

1. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) accanto al nome della connessione.
1. Seleziona ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Mappa di connessione]**.

### Dettagli della connessione {#connection-detail}

Per passare ai dettagli di una connessione, seleziona il nome connessione del collegamento ipertestuale nella tabella connessioni.

![Finestra Tutti i set di dati con widget e impostazioni](assets/conn-details.png)

L’interfaccia Dettagli connessioni fornisce una visualizzazione molto dettagliata dello stato di una connessione. Puoi:

* Controllare lo stato dei set di dati della connessione e del processo di acquisizione.
* Identificare i problemi di configurazione che portano a record saltati o eliminati.
* Vedere quando i dati sono disponibili per il reporting.

| Interfaccia utente | Descrizione |
| --- | --- |
| ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifica connessione]** | Per modificare i dettagli di una connessione, seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifica connessione]**. Per ulteriori informazioni, consulta [Creare o modificare una connessione](create-connection.md). |
| **[!UICONTROL *Selettore di set di dati *]** | Seleziona uno o tutti i set di dati per i quali mstrare i dettagli nella connessione. Non è possibile selezionare più set di dati. L’impostazione predefinita è **[!UICONTROL Tutti i set di dati]**. |
| **[!UICONTROL *Selettore di intervalli di date *]** | Seleziona un intervallo di dati per cui mostrare i dettagli nella connessione. Modifica la data di inizio e di fine oppure seleziona ![Calendario](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) per aprire il selettore dell’intervallo di date. Nel selettore, seleziona un intervallo di date utilizzando uno dei periodi predefiniti, ad esempio **[!UICONTROL Ultimi 6 mesi]**, oppure utilizzando il calendario per selezionare le date di inizio e di fine. Seleziona **[!UICONTROL Applica]** per applicare il nuovo intervallo di date ai dettagli della connessione. |
| **[!UICONTROL Record di dati evento disponibili]** | Numero totale di righe del set di dati evento disponibili per il reporting, **per l’intera connessione**. Il conteggio è indipendente da qualsiasi intervallo di date o selezione di set di dati. |
| [!UICONTROL **[!UICONTROL Metriche]**] | Riepiloga record di set di dati di evento, ricerca, profilo e di riepilogo aggiunti, saltati ed eliminati e il numero di batch aggiunti. Queste metriche si basano sul **set di dati e intervallo di date selezionati**.<p>Seleziona **[!UICONTROL Controlla i dettagli]** per mostrare la finestra a comparsa **[!UICONTROL Controlla i dettagli ignorati]**. La finestra a comparsa elenca il numero di record saltati e il motivo per tutti i set di dati evento o per i set di dati selezionati.<p>![Record ignorati](assets/skipped-records.png)<p>Seleziona il pop-up ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) con ulteriori informazioni. Per alcuni motivi per cui vengono ignorati, come [!UICONTROL ID visitatore vuoto], nella finestra a comparsa viene visualizzato **[!UICONTROL Esempio di PSQL per EQS]** (Experience Platform per servizio query) che puoi utilizzare nel [Servizio query](https://experienceleague.adobe.com/it/docs/experience-platform/query/home) per eseguire query per i record ignorati nel set di dati. Seleziona ![Copia](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copia esempio PSQL per EQS]** per copiare SQL. |
| **[!UICONTROL Record aggiunti]** | Una visualizzazione che indica quante righe sono state aggiunte nel periodo di tempo selezionato **per il set di dati e l’intervallo di date selezionati**. Viene aggiornata ogni 10 minuti. |
| **[!UICONTROL Record ignorati]** | Una visualizzazione che indica quante righe sono state ignorate nel periodo di tempo selezionato **per il set di dati e l’intervallo di date selezionati**. I motivi per cui i record vengono ignorati comprendono: marche temporali mancanti, ID persona o ID account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} mancante o non valido, e così via. Viene aggiornata ogni 10 minuti. <p>Gli ID non validi, ad esempio `undefined`, `00000000` o qualsiasi combinazione di numeri e lettere in un [!UICONTROL ID persona] che appaiono in un evento più di 1 milione di volte in un determinato mese, non possono essere attribuiti a un utente o persona specifica. Queste righe di dati non possono essere acquisite nel sistema e causano errori nell’acquisizione e nel reporting. Per correggere gli ID persona o gli ID account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} non validi, sono disponibili 3 opzioni:<ul><li>Utilizza [Unione delle identità](/help/stitching/overview.md) per popolare gli ID utente non definiti o composti da soli zeri con ID utente validi.</li><li>Rimuovi gli ID utente, che verranno ignorati anche durante l’acquisizione, da preferire agli ID utente non validi o composti solo da zeri.</li><li>Correggi eventuali ID utente non validi nel sistema prima di acquisire i dati.</li></ul> |
| **[!UICONTROL Record eliminati]** | Una visualizzazione che indica quante righe sono state eliminate nel periodo di tempo selezionato **per il set di dati e l’intervallo di date selezionati**. Ad esempio, qualcuno potrebbe aver eliminato un set di dati in [!DNL Experience Platform]. Viene aggiornata ogni 10 minuti.<p>In alcuni scenari, questo valore può includere anche i record sostituiti, ad esempio con l’unione, o alcuni aggiornamenti dei set di dati di ricerca. Studia questo esempio:</p><ul><li>Carichi un record in un set di dati Profilo individuale XDM, che in Customer Journey Analytics è configurato per essere acquisito come dati di ricerca profilo. Nei dettagli della connessione, questo set di dati visualizzerebbe 1 record aggiunto.</li><li>Carichi un duplicato del record originale nello stesso set di dati di AEP, che ora contiene due record. Customer Journey Analytics acquisisce il record aggiuntivo dal set di dati di ricerca del profilo o dell’account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}. Considerando che il record profilo o account è già stato acquisito nella connessione per l’ID persona o l’ID account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, Customer Journey Analytics elimina la versione precedente e aggiunge i nuovi dati del profilo. Nei dettagli della connessione, questa azione rappresenterebbe 1 record aggiunto e 1 record eliminato, perché Customer Journey Analytics mantiene solo i dati di ricerca del profilo più recenti per qualsiasi ID persona o ID account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} acquisito.</li><li>In totale, il set di dati di AEP contiene due record che risultano identici. A parte, i dettagli della connessione a Customer Journey Analytics mostrano lo stato dei dati acquisiti: 2 record aggiunti e 1 record eliminato per questo set di dati profilo. </li></ul> |
| ![Ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Campo di ricerca del set di dati. Nella tabella dei set di dati, puoi eseguire ricerche per nome o ID set di dati. |
| [!UICONTROL Tabella set di dati] | Set di dati che fanno parte della connessione. Per ulteriori spiegazioni, consulta la tabella seguente. Seleziona ![SelectBox](/help/assets/icons/SelectBox.svg) un singolo set di dati per mostrare solo i dettagli della connessione per il set di dati selezionato. Equivale alla selezione di un set di dati dal **[!UICONTROL _Selettore di set di dati_]**. |

Per ciascun set di dati, la tabella visualizza le colonne riportate di seguito:

| Colonna | Descrizione |
| --- | --- |
| **[!UICONTROL Set di dati]** | Il nome del set di dati. Puoi selezionare il collegamento ipertestuale per aprire il set di dati nell’interfaccia utente di Experience Platform in una nuova scheda. Puoi selezionare la riga o la casella di controllo per visualizzare i dettagli solo per il set di dati selezionato. |
| **[!UICONTROL ID set di dati]** | L’ID set di dati generato da Experience Platform. |
| **[!UICONTROL Record aggiunti]** | Il numero di record set di dati (righe) aggiunti a una connessione durante l’intervallo di date selezionato. |
| **[!UICONTROL Record ignorati]** | Il numero di record set di dati (righe) ignorati durante il trasferimento di dati per una connessione nell’intervallo di date selezionato. |
| **[!UICONTROL Record eliminati]** | Il numero di record set di dati (righe) rimossi da una connessione durante l’intervallo di date selezionato. |
| **[!UICONTROL Batch aggiunti]** | Il numero di batch aggiunti a una connessione durante l’intervallo di date selezionato. |
| **[!UICONTROL Ultima aggiunta]** | La marca temporale dell’ultimo batch aggiunto a una connessione. |
| **[!UICONTROL Tipo di origine dati]** | Il tipo di origine. Quando aggiungi un set di dati a una connessione, puoi definire il tipo di origine. |
| **[!UICONTROL Tipo di set di dati]** | Il [tipo di set di dati](create-connection.md#dataset-types). Il tipo può essere **[!UICONTROL Evento]**, **[!UICONTROL Profilo]**, **[!UICONTROL Ricerca]**, **[!UICONTROL Riepilogo]**. Un set di dati ad hoc o relazionale è identificato da **[!UICONTROL (Ad hoc)]** o **[!UICONTROL (Relazionale)]**. Ad esempio, **[!UICONTROL Evento (Ad hoc)]** o **[!UICONTROL Ricerca (Relazionale)]**. |
| **[!UICONTROL Uniti]** | Se un set di dati è [abilitato per l&#39;unione nell&#39;interfaccia utente della connessione](/help/stitching/use-stitching-ui.md), il valore è **[!UICONTROL true]**. In caso contrario, il valore è **[!UICONTROL false]**. I set di dati uniti che sono il risultato della [richiesta di unione](/help/stitching//use-stitching.md) non sono identificati come uniti in questa tabella e per impostazione predefinita hanno un valore di **[!UICONTROL false]**. |
| **[!UICONTROL Schema]** | Lo schema di Adobe Experience Platform su cui si basa il set di dati. |
| **[!UICONTROL Importa nuovi dati]** | Stato dell’importazione di nuovi dati per il set di dati: <p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Attivo]**&#x200B;se il set di dati è configurato per l’importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Disattivato_]** se il set di dati non è configurato per l’importazione di nuovi dati. |
| **[!UICONTROL Trasforma dati]** | Stato di trasformazione dei set di dati di ricerca B2B applicabili. Per ulteriori informazioni, consulta [Trasformare i set di dati per le ricerche B2B](transform-datasets-b2b-lookups.md).<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Attivo]**&#x200B;per i set di dati applicabili abilitati per la trasformazione, <p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Disattivato_]** per i set di dati applicabili non abilitati per la trasformazione e<p>**[!UICONTROL N/D]** per tutti gli altri set di dati, non applicabili per la trasformazione. |
| **[!UICONTROL Retrocompilazione dei dati]** | Stato dei dati di retrocompilazione per il set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _retrocompilazioni non riuscite]**&#x200B;per il numero di retrocompilazioni non riuscite,<p>![Stato rosso](assets/status-orange.svg)   **[!UICONTROL _x _retrocompilazioni in elaborazione]**&#x200B;per il numero di retrocompilazioni in elaborazione,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _retrocompilazioni completate]**&#x200B;per il numero di retrocompilazioni completate e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** nel caso in cui le retrocompilazioni non siano configurate. |

>[!IMPORTANT]
>
>Eventuali dati acquisiti prima del 13 agosto 2021 non vengono riflessi nell’interfaccia [!UICONTROL Connessioni].
>

#### Pannello connessione

Quando nella tabella dei set di dati non è selezionato alcun singolo set di dati, il pannello di destra mostra le opzioni e i dettagli di connessione.

| Opzioni | Descrizione |
| --- | --- |
| ![Aggiorna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Aggiorna]** | Per aggiornare la connessione e consentire la visualizzazione dei record aggiunti di recente, seleziona ![Aggiorna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Aggiorna]**. |
| ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Elimina]** | [Elimina](#delete-a-connection) questa connessione. |
| ![Aggiungi visualizzazione dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Crea visualizzazione dati]** | [Crea una visualizzazione dati](#create-a-data-view) in base a questa connessione. Per ulteriori informazioni, consulta [Visualizzazione dati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/data-views). |
| **[!UICONTROL Utilizza in CJA]** | Utilizza una connessione Journey Optimizer in Customer Journey Analytics per aggiungere valore alla connessione Journey Optimizer. Per ulteriori informazioni, consulta [Utilizza una connessione Journey Optimizer in Customer Journey Analytics](#use-a-journey-optimizer-connection-in-customer-journey-analytics). |
| **[!UICONTROL Nome connessione]** | Il nome descrittivo della connessione. |
| **[!UICONTROL Descrizione connessione]** | Una descrizione più dettagliata che illustra lo scopo di questa connessione. |
| **[!UICONTROL Sandbox]** | La [sandbox di Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/sandbox/home) da cui questa connessione estrae i relativi set di dati. Selezioni questa sandbox al momento della creazione della connessione. Una volta salvata una connessione, non è possibile modificare la sandbox. |
| **[!UICONTROL ID connessione]** | Un identificatore generato per la connessione. Puoi usare ![Copia](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) per copiare il valore. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Tipo di ID primario &#x200B;]** | Il tipo di ID primario per la connessione: **[!UICONTROL Persona]** per una connessione basata su persona, **[!UICONTROL Account]** per una connessione basata su account. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Contenitori &#x200B;]** | I contenitori configurati per la connessione. |
| **[!UICONTROL Visualizzazioni dati che usano questa connessione]** | Le visualizzazioni dati che utilizzano questa connessione. |
| **[!UICONTROL Importa nuovi dati]** | Stato dell’importazione di nuovi dati per i set di dati: <p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Attivo]**&#x200B;per il numero di set di dati configurati per l’importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Disattivato_]** per il numero di set di dati per il quale viene disattivata l’importazione di nuovi dati. |
| **[!UICONTROL Retrocompilazione dei dati]** | Stato dei dati di retrocompilazione per i set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _retrocompilazioni non riuscite]**&#x200B;per il numero di retrocompilazioni non riuscite tra set di dati,<p>![Stato rosso](assets/status-orange.svg)   **[!UICONTROL _x _retrocompilazioni in elaborazione]**&#x200B;per il numero di retrocompilazioni in elaborazione tra set di dati,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _retrocompilazioni completate]**&#x200B;per il numero di retrocompilazioni completate per i set di dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** nel caso in cui non siano definite retrocompilazioni per i set di dati nella connessione. |
| **[!UICONTROL Trasforma dati]** | Stato di trasformazione dei set di dati di ricerca B2B applicabili. Per ulteriori informazioni, consulta [Trasformare i set di dati per le ricerche B2B](transform-datasets-b2b-lookups.md).<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Attivo]**&#x200B;per il numero di set di dati abilitati per la trasformazione. |
| **[!UICONTROL Creata da]** | Il nome della persona che ha creato la connessione. |
| **[!UICONTROL Ultima modifica]** | La marca temporale dell’ultima modifica apportata alla connessione. |
| **[!UICONTROL Ultima modifica di]** | Il nome della persona che ha modificato la connessione. |

#### Pannello set di dati

Quando una riga di set di dati viene selezionata nella tabella dei set di dati, in un pannello sul lato destro dell’interfaccia Connessioni vengono visualizzati i dettagli del set di dati selezionato.

| Dettagli | Descrizione |
| --- | --- |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL ID account globale &#x200B;]** | L’identità specificata come ID account globale per la connessione. Applicabile solo per una connessione basata su account per la quale hai configurato un contenitore account globale. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL ID account &#x200B;]** | L’identità specificata come ID account per la connessione. Applicabile solo per una connessione basata su account per la quale non hai configurato alcun contenitore account globale. |
| **[!UICONTROL ID persona]** | L’identità specificata come ID persona per la connessione. |
| **[!UICONTROL Chiave]** | La chiave specificata per un set di dati di ricerca. |
| **[!UICONTROL Chiave corrispondente]** | La chiave corrispondente specificata per un set di dati di ricerca. |
| **[!UICONTROL Marca temporale]** | La marca temporale definita per un set di dati evento. |
| **[!UICONTROL Record disponibili]** | Numero totale di righe acquisite per questo set di dati, per il particolare periodo di tempo selezionato nel calendario. Non esiste alcuna latenza in termini di visualizzazione dei dati nel reporting, una volta aggiunti. Tuttavia, quando crei una nuova connessione, si verifica una [latenza](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-faq). |
| **[!UICONTROL Record aggiunti]** | Il numero di record set di dati (righe) aggiunti a una connessione durante l’intervallo di date selezionato. |
| **[!UICONTROL Record ignorati]** | Il numero di record set di dati (righe) ignorati durante il trasferimento di dati per una connessione nell’intervallo di date selezionato. |
| **[!UICONTROL Batch aggiunti]** | Il numero di batch aggiunti a una connessione. |
| **[!UICONTROL Record eliminati]** | Il numero di record set di dati (righe) rimossi da una connessione durante l’intervallo di date selezionato. |
| **[!UICONTROL Ultima aggiunta]** | La marca temporale dell’ultimo batch aggiunto a una connessione. |
| **[!UICONTROL Importa nuovi dati]** | Stato dell’importazione di nuovi dati per il set di dati: <p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _Attivo]**&#x200B;se il set di dati è configurato per l’importazione di nuovi dati e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _x Disattivato_]** se il set di dati è configurato per non importare nuovi dati. |
| **[!UICONTROL Retrocompilazione dei dati]** | Stato dei dati di retrocompilazione per il set di dati.<p>![Stato rosso](assets/status-red.svg)   **[!UICONTROL _x _retrocompilazioni non riuscite]**&#x200B;per il numero di retrocompilazioni non riuscite,<p>![Stato rosso](assets/status-orange.svg)   **[!UICONTROL _x _retrocompilazioni in elaborazione]**&#x200B;per il numero di retrocompilazioni in elaborazione,<p>![Stato verde](assets/status-green.svg)   **[!UICONTROL _x _retrocompilazioni completate]**&#x200B;per il numero di retrocompilazioni completate e<p>![Stato grigio](assets/status-gray.svg)   **[!UICONTROL _Disattivato_]** se non è configurata alcuna retrocompilazione.<p>Per visualizzare una finestra di dialogo con una panoramica delle precedenti retrocompilazioni relative al set di dati, selezionare <img src="./assets/pastbackfill.svg" alt="Retrocompilazioni precedenti" width="15"/> **[!UICONTROL Retrocompilazioni precedenti]**. |
| **[!UICONTROL Tipo di origine dati]** | Il tipo di origine dati definito durante l’aggiunta del set di dati alla connessione. |
| **[!UICONTROL Tipo di set di dati]** | Il [tipo di set di dati](create-connection.md#dataset-types). Il tipo può essere **[!UICONTROL Evento]**, **[!UICONTROL Profilo]**, **[!UICONTROL Ricerca]**, **[!UICONTROL Riepilogo]**. Un set di dati ad hoc o relazionale è identificato da **[!UICONTROL (Ad hoc)]** o **[!UICONTROL (Relazionale)]**. Ad esempio, **[!UICONTROL Evento (Ad hoc)]** o **[!UICONTROL Ricerca (Relazionale)]**. |
| **[!UICONTROL Schema]** | Lo schema di Adobe Experience Platform su cui si basa questo set di dati. |
| **[!UICONTROL ID set di dati]** | L&#39;ID del set di dati, così come viene generato in Experience Platform. |


## Utilizzo {#connections-usage}

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="Metriche di utilizzo chiave"
>abstract="Fornisce dati mensili e totali per le righe principali e storiche da riportare."

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="Righe acquisite mensilmente"
>abstract="Misura il numero totale di record aggiunti al sistema ogni mese per fornire informazioni approfondite sulla crescita dei dati e sui tassi di acquisizione."

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="Righe mensili da riportare"
>abstract="Traccia il numero di righe disponibili per il reporting. Le righe da riportare sono le righe acquisite meno quelle ignorate ed eliminate durante l’acquisizione. Le righe da riportare fungono da metrica chiave per la fatturazione e l’utilizzo dei dati."

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="Raggruppamento in dettaglio."
>abstract="Puoi visualizzare metriche dettagliate per connessione, set di dati, sandbox e tag, con l’opzione di scaricare un file CSV dei dati."

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="Altri set di dati"
>abstract="Per i mesi precedenti a settembre 2024, i dati sono stati raccolti a livello di set di dati e vengono visualizzati come *Altri set di dati* per maggiore chiarezza. A partire da settembre 2024, i dati vengono raccolti a livello di set di dati granulari e *Altri set di dati* non verranno più visualizzati."

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="Connessioni o set di dati sconosciuti"
>abstract="Le connessioni o i set di dati sconosciuti vengono visualizzati utilizzando i relativi ID."

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="Dati non disponibili"
>abstract="I dati storici precedenti a settembre 2024 non sono disponibili a causa di limitazioni del sistema. Le metriche vengono raccolte e visualizzate a partire da settembre 2024. Il grafico mostra gli ultimi 18 mesi sulla timeline. I dati futuri verranno visualizzati non appena saranno disponibili."

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="Righe di base per reporting"
>abstract="Il numero totale di righe disponibili negli ultimi 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente.  Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024."

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Righe storiche per reporting"
>abstract="Il numero totale di righe disponibili in un periodo antecedente ai 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale precedente a gennaio 2023."


>[!CONTEXTUALHELP]
>id="connections_averagerowsize"
>title="Dimensione riga media"
>abstract="La quantità media di spazio di archiviazione utilizzato da ogni riga di dati acquisiti e memorizzati per il mese corrente (in KB), con una variazione percentuale rispetto al mese precedente."


>[!CONTEXTUALHELP]
>id="connections_coredatavolume"
>title="Volume dati di base"
>abstract="La quantità totale di dati memorizzati su disco con marca temporale per il mese corrente (in TB), con una variazione percentuale rispetto al mese precedente."


>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="Righe di base per reporting"
>abstract="Le righe di base per reporting sono istantanee di valori, non totali aggregati. Questi valori si aggiornano in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. I valori riflettono l’istantanea per il mese selezionato."

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="Righe storiche per reporting"
>abstract="Le righe storiche per reporting sono istantanee di valori, non totali aggregati. Questi valori si aggiornano in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. I valori riflettono l’istantanea per il mese selezionato."

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="Righe cumulative per reporting"
>abstract="Le righe cumulative per reporting sono istantanee di valori, non totali aggregati. Questi valori si aggiornano in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. I valori riflettono l’istantanea per il mese selezionato."


>[!CONTEXTUALHELP]
>id="connections_extendeddatacapacityrows"
>title="Righe di capacità di dati estesa"
>abstract="Il numero totale di righe disponibili in un periodo antecedente ai 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale precedente a gennaio 2023."

>[!CONTEXTUALHELP]
>id="connections_breakdown_extendeddatacapacityrows"
>title="Righe di capacità di dati estesa"
>abstract="Le righe di capacità di dati estesa presentano valori istantanei, non totali aggregati. Questi valori si aggiornano in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. I valori riflettono l’istantanea per il mese selezionato."

>[!CONTEXTUALHELP]
>id="connections_aca_corereportablerows"
>title="Righe di base per il reporting di Content Analytics"
>abstract="Il numero totale di righe specifiche di Content Analytics disponibili negli ultimi 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente.  Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024."

>[!CONTEXTUALHELP]
>id="connections_usage_aca_monthlyreportablerows"
>title="Righe mensili di Content Analytics"
>abstract="Traccia il numero di righe di Content Analytics disponibili per il reporting. Le righe da riportare sono le righe acquisite meno quelle ignorate ed eliminate durante l’acquisizione. Le righe da riportare fungono da metrica chiave per la fatturazione e l’utilizzo dei dati."

>[!CONTEXTUALHELP]
>id="connections_breakdown_aca_corereportablerows"
>title="Righe di base per il reporting di Content Analytics"
>abstract="Le righe di base per il reporting di Content Analytics presentano valori istantanei non totali aggregati. Questi valori si aggiornano in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. I valori riflettono l’istantanea per il mese selezionato."


>[!CONTEXTUALHELP]
>id="connections_b2b_coreportablebpp"
>title="Righe di base per il reporting di persone aziendali"
>abstract="Il numero totale di righe per il reporting del profilo aziendale disponibili negli ultimi 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente.  Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024."

>[!CONTEXTUALHELP]
>id="connections_b2b_historicalreportablebpp"
>title="Righe storiche per il reporting del profilo aziendale"
>abstract="Il numero totale di righe per il reporting del profilo aziendale disponibili in un periodo antecedente ai 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale precedente a gennaio 2023."

>[!CONTEXTUALHELP]
>id="connections_breakdown_b2b_corereportablebpp"
>title="Righe di base per il reporting del profilo aziendale"
>abstract="Le righe di base per il reporting del profilo aziendale presentano valori istantanei, non totali aggregati. Questi valori si aggiornano in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. I valori riflettono l’istantanea per il mese selezionato."

>[!CONTEXTUALHELP]
>id="connections_breakdown_b2b_historicalreportablebpp"
>title="Righe storiche per il reporting del profilo aziendale"
>abstract="Le righe storiche per il reporting del profilo aziendale presentano valori ottenuti istantanei, non totali aggregati. Questi valori si aggiornano in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. I valori riflettono l’istantanea per il mese selezionato."

>[!CONTEXTUALHELP]
>id="connections_monthlymediastarts"
>title="Avvii mensili dei file multimediali"
>abstract="Il numero totale di avvii mensili dei file multimediali disponibili negli ultimi 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente.  Ad esempio, il 1° febbraio 2024 viene mostrato il totale di avvii dei file multimediali disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024."

>[!CONTEXTUALHELP]
>id="connections_breakdown_monthlymediastarts"
>title="Avvii mensili dei file multimediali"
>abstract="Gli avvii mensili dei file multimediali presentano valori istantanei, non totali aggregati. Questi valori si aggiornano in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. I valori riflettono l’istantanea per il mese selezionato."


>[!CONTEXTUALHELP]
>id="connections_breakdown_aca_monthlyreportablerows"
>title="Righe mensili di Content Analytics"
>abstract="Le righe mensili di Content Analytics presentano valori istantanei, non totali aggregati. Questi valori si aggiornano in modo dinamico in base all’ultimo mese nell’intervallo di date selezionato. I valori riflettono l’istantanea per il mese selezionato."



L’interfaccia [!UICONTROL Utilizzo] mostra l’utilizzo delle righe acquisite e per reporting in tutte le connessioni. Se non è selezionata, seleziona la scheda **[!UICONTROL Utilizzo]** per accedere all’interfaccia.

Questa interfaccia consente di determinare se l&#39;utilizzo di Customer Journey Analytics è conforme a quanto stabilito contrattualmente. Oltre a scopi di monitoraggio, è possibile utilizzare l’interfaccia Utilizzo per pianificare il rinnovo della licenza di Customer Journey Analytics.

Per ogni modulo a cui hai diritto, è disponibile una sezione comprimibile con i dettagli di utilizzo.

### Utilizzo di CJA

L&#39;interfaccia **[!UICONTROL Utilizzo di CJA]** utilizza le metriche seguenti:

| Nome della metrica | Descrizione |
|---|---|
| **Righe storiche per reporting** | Il conteggio delle righe per il periodo antecedente a 13 mesi. |
| **Righe di base per reporting** | Il conteggio delle righe degli ultimi 13 mesi. |
| **Volume dati di base** | Quantità totale di dati memorizzati su disco. |
| **Dimensione riga media** | Quantità media di spazio di archiviazione utilizzato per ogni riga di dati acquisiti e memorizzati. |
| **Righe acquisite** | La quantità di righe acquisite per il periodo specifico. |
| **Righe segnalabili** | La quantità di righe di dati presenti nella connessione per il periodo specifico. |
| **Righe cumulative** | Quante righe vengono acquisite fino al mese specifico. |

>[!NOTE]
>
>I dati vengono raccolti a partire da luglio 2024 per i record principali, storici e totali. Per informazioni sui dati storici precedenti, contatta il tuo account manager.
>

L&#39;interfaccia **[!UICONTROL Utilizzo di CJA]** è costituita da due pannelli:

* Il pannello **[!UICONTROL Metriche chiave di utilizzo]** che visualizza:

  * Quattro visualizzazioni di riepilogo che visualizzano le modifiche totali e percentuali rispetto al mese precedente per:

    * **[!UICONTROL Righe di dati di base per reporting]** Il numero totale di righe disponibili negli ultimi 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024.
    * **[!UICONTROL Righe capacità dati estesa]**. Il numero totale di righe disponibili in un periodo antecedente ai 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale precedente a gennaio 2023.
    * **[!UICONTROL Righe acquisite mensilmente]**. Righe acquisite durante il mese di fatturazione, con una variazione percentuale rispetto al mese precedente
    * **[!UICONTROL Volume dati di base]** La quantità totale di dati memorizzati su disco con marca temporale per il mese corrente (in TB), con una variazione percentuale rispetto al mese precedente.
    * **[!UICONTROL Dimensione riga media]**. Memoria media consumata da ogni riga acquisita per il mese corrente (in kB), con variazione percentuale rispetto al mese precedente.

  * Visualizzazione a due barre verticali che visualizza le **[!UICONTROL righe dei dati core segnalabili]** e **[!UICONTROL righe della capacità dati estesa]** per gli ultimi 13 mesi.

    Quando passi il puntatore su una barra sovrapposta nella visualizzazione, una finestra a comparsa mostra il numero di righe relativo a quella parte specifica della barra.

* Un pannello combinato che mostra tre pannelli secondari per:

  +++ Righe acquisite

  Il pannello secondario **[!UICONTROL Righe acquisite]** misura il numero totale di record aggiunti al sistema ogni mese, per fornire insight sulla crescita dei dati e sui tassi di acquisizione. Il pannello secondario fornisce un riepilogo del totale delle righe acquisite di questo mese e della modifica rispetto al mese precedente.

  Puoi passare il puntatore sui punti dati nelle visualizzazioni per visualizzare un pop-up con ulteriori dettagli. È possibile selezionare un **[!UICONTROL intervallo di tempo]** che si applica sia alle **[!UICONTROL righe acquisite]** che alle **[!UICONTROL righe segnalabili]**. Utilizza ![Calendario](/help/assets/icons/Calendar.svg) per selezionare l’intervallo di tempo.

  +++

  +++ Righe segnalabili

  La visualizzazione **[!UICONTROL Righe per reporting]** tiene traccia del numero di righe disponibili per il reporting sottraendo le righe ignorate ed eliminate dalle righe acquisite, fungendo da metrica chiave per la fatturazione e l’utilizzo dei dati. Il pannello secondario fornisce due riepiloghi:

  * **[!UICONTROL Totale righe segnalabili]**: riepilogo del totale delle righe segnalabili fino al mese corrente.
  * **[!UICONTROL Mese da segnalare]**: riepilogo del totale delle righe da segnalare di questo mese e della modifica rispetto al mese precedente.

  Puoi passare il puntatore sui punti dati nelle visualizzazioni per visualizzare un pop-up con ulteriori dettagli. È possibile selezionare un **[!UICONTROL intervallo di tempo]** che si applica sia alle **[!UICONTROL righe acquisite]** che alle **[!UICONTROL righe segnalabili]**. Utilizza ![Calendario](/help/assets/icons/Calendar.svg) per selezionare l’intervallo di tempo.

  +++

  +++ Raggruppamento in dettaglio.

  Puoi utilizzare la tabella **[!UICONTROL Raggruppamento dettagliato]** per visualizzare metriche dettagliate per connessione, set di dati, sandbox e tag. I set di dati vengono indicati utilizzando ID anziché nomi, in quanto i nomi dei set di dati possono essere modificati nel corso di un periodo di reporting. Le connessioni o i set di dati sconosciuti vengono indicati utilizzando i relativi ID.

  Per i mesi precedenti a settembre 2024, i dati sono stati raccolti a livello di set di dati e vengono visualizzati come [!UICONTROL Altri set di dati] per maggiore chiarezza. A partire da settembre 2024, i dati vengono raccolti a livello di set di dati granulari e [!UICONTROL Altri set di dati] non vengono più visualizzati.

  * Per modificare il raggruppamento, seleziona una combinazione per **[!UICONTROL Visualizza per]** e **[!UICONTROL Raggruppa per]**.

    | Opzioni relative a **[!UICONTROL Visualizza per]** | Opzioni relative a **[!UICONTROL Raggruppa per]** |
    |---|---|
    | **[!UICONTROL Connessione]** | **[!UICONTROL -]** e **[!UICONTROL Set di dati]** |
    | **[!UICONTROL Set di dati]** | **[!UICONTROL -]** |
    | **[!UICONTROL Sandbox]** | **[!UICONTROL Connessione]** |
    | **[!UICONTROL Tag]** | **[!UICONTROL Connessione]** |

  È possibile selezionare un mese per il quale si desidera ottenere il raggruppamento. Seleziona un mese da **[!UICONTROL Mese raggruppamento]**.


  +++

### Utilizzo di Content Analytics

L&#39;interfaccia **[!UICONTROL Utilizzo di Content Analytics]** utilizza le metriche seguenti:

| Nome della metrica | Descrizione |
|---|---|
| **Righe reportabili principali di Content Analytics** | Il numero totale di righe specifiche di Content Analytics disponibili negli ultimi 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente.  Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024. |
| **Righe Content Analytics mensili** | Traccia il numero di righe di Content Analytics disponibili per il reporting. Le righe da riportare sono le righe acquisite meno quelle ignorate ed eliminate durante l’acquisizione. Le righe da riportare fungono da metrica chiave per la fatturazione e l’utilizzo dei dati. |

>[!NOTE]
>
>I dati vengono raccolti a partire da luglio 2024 per i record principali, storici e totali. Per informazioni sui dati storici precedenti, contatta il tuo account manager.
>

L&#39;interfaccia **[!UICONTROL Utilizzo di Content Analytics]** è costituita da due pannelli:

* Il pannello **[!UICONTROL Metriche chiave di utilizzo]** che visualizza:

  * Due visualizzazioni di riepilogo che visualizzano le modifiche totali e percentuali rispetto al mese precedente per:

    * **[!UICONTROL Righe principali di Analytics da segnalare]**. Il numero totale di righe specifiche di Content Analytics disponibili negli ultimi 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente.  Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024.
    * **Righe Content Analytics mensili**. Traccia il numero di righe di Content Analytics disponibili per il reporting. Le righe da riportare sono le righe acquisite meno quelle ignorate ed eliminate durante l’acquisizione. Le righe da riportare fungono da metrica chiave per la fatturazione e l’utilizzo dei dati.

  * Visualizzazione a barre verticali sovrapposte che visualizza le **[!UICONTROL righe principali di Content Analytics da segnalare]** per gli ultimi 13 mesi.

    Quando passi il puntatore su una barra sovrapposta nella visualizzazione, una finestra a comparsa mostra il numero di righe relativo a quella parte specifica della barra.

* Un pannello combinato che mostra due pannelli secondari per:

  +++ Righe mensili di Content Analytics

  Il pannello secondario **[!UICONTROL Righe mensili di Content Analytics]** misura il numero totale di record mensili di Content Analytics aggiunti al sistema ogni mese, fornendo ad insight la crescita dei dati e i tassi di acquisizione. Il pannello secondario fornisce un riepilogo del totale delle righe acquisite di questo mese e della modifica rispetto al mese precedente.

  Puoi passare il puntatore sui punti dati nella visualizzazione per visualizzare una finestra a comparsa con ulteriori dettagli. È possibile selezionare un **[!UICONTROL intervallo di tempo]** o utilizzare ![Calendario](/help/assets/icons/Calendar.svg) per selezionare l&#39;intervallo di tempo.

  +++

  +++ Raggruppamento in dettaglio.

  Puoi utilizzare la tabella **[!UICONTROL Raggruppamento dettagliato]** per visualizzare metriche dettagliate per connessione, set di dati, sandbox e tag. I set di dati vengono indicati utilizzando ID anziché nomi, in quanto i nomi dei set di dati possono essere modificati nel corso di un periodo di reporting. Le connessioni o i set di dati sconosciuti vengono indicati utilizzando i relativi ID.

  Per i mesi precedenti a settembre 2024, i dati sono stati raccolti a livello di set di dati e vengono visualizzati come [!UICONTROL Altri set di dati] per maggiore chiarezza. A partire da settembre 2024, i dati vengono raccolti a livello di set di dati granulari e [!UICONTROL Altri set di dati] non vengono più visualizzati.

  * Per modificare il raggruppamento, seleziona una combinazione per **[!UICONTROL Visualizza per]** e **[!UICONTROL Raggruppa per]**.

    | Opzioni relative a **[!UICONTROL Visualizza per]** | Opzioni relative a **[!UICONTROL Raggruppa per]** |
    |---|---|
    | **[!UICONTROL Connessione]** | **[!UICONTROL -]** e **[!UICONTROL Set di dati]** |
    | **[!UICONTROL Set di dati]** | **[!UICONTROL -]** |
    | **[!UICONTROL Sandbox]** | **[!UICONTROL Connessione]** |
    | **[!UICONTROL Tag]** | **[!UICONTROL Connessione]** |

  È possibile selezionare un mese per il quale si desidera ottenere il raggruppamento. Seleziona un mese da **[!UICONTROL Mese raggruppamento]**.

  +++


### Utilizzo della B2B Edition di CJA

L&#39;interfaccia **[!UICONTROL Utilizzo di CJA B2B edition]** utilizza le metriche seguenti:

| Nome della metrica | Descrizione |
|---|---|
| **BPP Core da segnalare** | Numero totale di righe segnalabili del profilo aziendale disponibili negli ultimi 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente.  Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024. |
| **BPP cronologico da segnalare** | Il numero totale di righe segnalabili del profilo aziendale disponibili in un periodo più vecchio di 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente. Ad esempio, il 1° febbraio 2024 viene mostrato il totale delle righe disponibili per eventi con marca temporale precedente a gennaio 2023. |

>[!NOTE]
>
>I dati vengono raccolti a partire da luglio 2024 per i record principali, storici e totali. Per informazioni sui dati storici precedenti, contatta il tuo account manager.
>

L&#39;interfaccia **[!UICONTROL Utilizzo di CJA B2B edition]** è costituita da un pannello che visualizza i pannelli secondari per:

+++ BPP Core da segnalare.

Il pannello secondario **[!UICONTROL Core BPP]** segnalabile misura il numero totale di record mensili del profilo aziendale segnalabile principali aggiunti al sistema ogni mese, fornendo ad insight tassi di crescita e di acquisizione dei dati. Il pannello secondario fornisce un riepilogo del totale delle righe acquisite di questo mese e della modifica rispetto al mese precedente.

Puoi passare il cursore del mouse sui punti dati nella visualizzazione per visualizzare un popup con ulteriori dettagli applicabili sia a **[!UICONTROL BPP Core segnalabile]** che a **[!UICONTROL BPP storico segnalabile]**. Utilizza ![Calendario](/help/assets/icons/Calendar.svg) per selezionare l’intervallo di tempo.

+++

+++ BPP da segnalare cronologico.

Il pannello secondario **[!UICONTROL Historical Reportable BPP]** misura il numero totale di record mensili del profilo Business Reporting cronologico aggiunti al sistema ogni mese, fornendo ad insight la crescita dei dati e i tassi di acquisizione. Il pannello secondario fornisce un riepilogo del totale delle righe acquisite di questo mese e della modifica rispetto al mese precedente.

Puoi passare il cursore del mouse sui punti dati nella visualizzazione per visualizzare un popup con ulteriori dettagli applicabili sia a **[!UICONTROL BPP Core segnalabile]** che a **[!UICONTROL BPP storico segnalabile]**. Utilizza ![Calendario](/help/assets/icons/Calendar.svg) per selezionare l’intervallo di tempo.

+++

+++ Raggruppamento in dettaglio.

Puoi utilizzare la tabella **[!UICONTROL Raggruppamento dettagliato]** per visualizzare metriche dettagliate per connessione, set di dati, sandbox e tag. I set di dati vengono indicati utilizzando ID anziché nomi, in quanto i nomi dei set di dati possono essere modificati nel corso di un periodo di reporting. Le connessioni o i set di dati sconosciuti vengono indicati utilizzando i relativi ID.

Per i mesi precedenti a settembre 2024, i dati sono stati raccolti a livello di set di dati e vengono visualizzati come [!UICONTROL Altri set di dati] per maggiore chiarezza. A partire da settembre 2024, i dati vengono raccolti a livello di set di dati granulari e [!UICONTROL Altri set di dati] non verranno più visualizzati.

* Per modificare il raggruppamento, seleziona una combinazione per **[!UICONTROL Visualizza per]** e **[!UICONTROL Raggruppa per]**.

  | Opzioni relative a **[!UICONTROL Visualizza per]** | Opzioni relative a **[!UICONTROL Raggruppa per]** |
  |---|---|
  | **[!UICONTROL Connessione]** | **[!UICONTROL -]** e **[!UICONTROL Set di dati]** |
  | **[!UICONTROL Set di dati]** | **[!UICONTROL -]** |
  | **[!UICONTROL Sandbox]** | **[!UICONTROL Connessione]** |
  | **[!UICONTROL Tag]** | **[!UICONTROL Connessione]** |

È possibile selezionare un mese per il quale si desidera ottenere il raggruppamento. Seleziona un mese da **[!UICONTROL Mese raggruppamento]**.

+++


### Utilizzo di file multimediali in streaming

L&#39;interfaccia **[!UICONTROL Utilizzo di contenuti multimediali in streaming]** utilizza le metriche seguenti:

| Nome della metrica | Descrizione |
|---|---|
| **Avvio mensile file multimediali** | Il numero totale di avvii mensili dei file multimediali disponibili negli ultimi 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente.  Ad esempio, il 1° febbraio 2024 viene mostrato il totale di avvii dei file multimediali disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024. |

>[!NOTE]
>
>I dati vengono raccolti a partire da luglio 2024 per i record principali, storici e totali. Per informazioni sui dati storici precedenti, contatta il tuo account manager.
>


L&#39;interfaccia **[!UICONTROL Utilizzo contenuti multimediali in streaming]** è costituita da due pannelli:

* Il pannello **[!UICONTROL Metriche chiave di utilizzo]** che visualizza:

  * Visualizzazione di riepilogo che visualizza le modifiche totali e percentuali rispetto al mese precedente per **[!UICONTROL Avvio mensile file multimediali]**.

    Il numero totale di avvii mensili dei file multimediali disponibili negli ultimi 13 mesi per il mese corrente, con una variazione percentuale rispetto al mese precedente.  Ad esempio, il 1° febbraio 2024 viene mostrato il totale di avvii dei file multimediali disponibili per eventi con marca temporale compresa tra gennaio 2023 e gennaio 2024.

  * Visualizzazione a barre verticali sovrapposte che visualizza **[!UICONTROL Avvio elemento multimediale mensile]** negli ultimi 13 mesi.

    Quando passi il puntatore su una barra sovrapposta nella visualizzazione, una finestra a comparsa mostra il numero di righe relativo a quella parte specifica della barra.

* Un pannello combinato che mostra due pannelli secondari per:

  +++ Avvii mensili di file multimediali

  Il pannello secondario **[!UICONTROL Avvio file multimediale mensile]** misura il numero totale di record mensili di avvio del file multimediale aggiunti al sistema ogni mese, fornendo ad insight la crescita dei dati e i tassi di acquisizione. Il pannello secondario fornisce un riepilogo del totale delle righe acquisite di questo mese e della modifica rispetto al mese precedente.

  Puoi passare il puntatore sui punti dati nella visualizzazione per visualizzare una finestra a comparsa con ulteriori dettagli. È possibile selezionare un **[!UICONTROL intervallo di tempo]** o utilizzare ![Calendario](/help/assets/icons/Calendar.svg) per selezionare l&#39;intervallo di tempo.

  +++

  +++ Raggruppamento in dettaglio.

  Puoi utilizzare la tabella **[!UICONTROL Raggruppamento dettagliato]** per visualizzare metriche dettagliate per connessione, set di dati, sandbox e tag. I set di dati vengono indicati utilizzando ID anziché nomi, in quanto i nomi dei set di dati possono essere modificati nel corso di un periodo di reporting. Le connessioni o i set di dati sconosciuti vengono indicati utilizzando i relativi ID.

  Per i mesi precedenti a settembre 2024, i dati sono stati raccolti a livello di set di dati e vengono visualizzati come [!UICONTROL Altri set di dati] per maggiore chiarezza. A partire da settembre 2024, i dati vengono raccolti a livello di set di dati granulari e [!UICONTROL Altri set di dati] non verranno più visualizzati.

  * Per modificare il raggruppamento, seleziona una combinazione per **[!UICONTROL Visualizza per]** e **[!UICONTROL Raggruppa per]**.

    | Opzioni relative a **[!UICONTROL Visualizza per]** | Opzioni relative a **[!UICONTROL Raggruppa per]** |
    |---|---|
    | **[!UICONTROL Connessione]** | **[!UICONTROL -]** e **[!UICONTROL Set di dati]** |
    | **[!UICONTROL Set di dati]** | **[!UICONTROL -]** |
    | **[!UICONTROL Sandbox]** | **[!UICONTROL Connessione]** |
    | **[!UICONTROL Tag]** | **[!UICONTROL Connessione]** |

  È possibile selezionare un mese per il quale si desidera ottenere il raggruppamento. Seleziona un mese da **[!UICONTROL Mese raggruppamento]**.

  +++


>[!MORELIKETHIS]
>
>Esercitazione su [Visualizzare, risolvere e modificare le impostazioni di connessione](https://experienceleague.adobe.com/it/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja).
>[Gestione dell&#39;utilizzo di Customer Journey Analytics](/help/technotes/estimate-usage.md)
>
