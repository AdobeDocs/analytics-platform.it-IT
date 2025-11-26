---
title: Acquisire e utilizzare i dati ad hoc
description: Spiegare come acquisire e utilizzare contenuti ad hoc in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: 17b5842f-dc81-481f-8b21-dc90a133adcf
source-git-commit: c9d7a4596a842ab7d949364e3469747d20ca15b4
workflow-type: tm+mt
source-wordcount: '1623'
ht-degree: 15%

---

# Acquisire e utilizzare i dati ad hoc

Questa guida rapida spiega come acquisire dati ad hoc in Experience Platform e quindi utilizzarli in Customer Journey Analytics.

A questo scopo, è necessario:

- **Crea un set di dati con un file CSV** in Experience Platform. Questo flusso di lavoro definisce il modello (schema) dei dati che desideri raccogliere e dove raccogliere i dati (set di dati).

- **Impostare una connessione** in Customer Journey Analytics. Questa connessione deve (almeno) includere il set di dati ad hoc di Experience Platform.

- **Configura una visualizzazione dati** in Customer Journey Analytics per definire metriche e dimensioni dai campi dei dati ad hoc che desideri utilizzare in Analysis Workspace.

- **Configurare un progetto** in Customer Journey Analytics per generare rapporti e visualizzazioni.



>[!NOTE]
>
>Questa guida rapida è una guida semplificata su come acquisire dati ad hoc in Experience Platform e utilizzarli in Customer Journey Analytics. Ti consigliamo vivamente di esaminare le informazioni aggiuntive quando vi fai riferimento.


## Creare un set di dati con un file CSV

Per questo avvio rapido, desideri utilizzare un file CSV che rappresenti i dati di ricerca e contenga informazioni simili a quelle mostrate di seguito.

| _id | tracking_code | ad_group | nome_campagna |
| ---: | :---          | :---        | :---          |
| 1 | abc123 | abc-adgroup | Campagna 123 |
| 2 | def123 | def-adgroup | Campagna 123 |
| 3 | ghi123 | ghi-adgroup | Campagna 123 |
| 4 | abc456 | abc-adgroup | Campagna 456 |
| 5 | def456 | def-adgroup | Campagna 456 |

>[!NOTE]
>
>Utilizza set di dati e schemi ad hoc per dati basati su record (ricerca, profilo). I set di dati e gli schemi ad hoc sono meno adatti e non devono essere considerati per i dati di serie temporali (evento, riepilogo).

Non è necessario creare uno schema XDM per dati ad hoc. Experience Platform supporta un flusso di lavoro che, in base ai dati contenuti nel file CSV:

1. Crea automaticamente uno schema ad hoc. Tale schema è conforme alle colonne del file CSV.
1. Crea un set di dati contenente i dati del file CSV.

Per avviare il flusso di lavoro:

1. Nell&#39;interfaccia di Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Flussi di lavoro]**.
1. Seleziona ![DataAdd](/help/assets/icons/DataAdd.svg) **[!UICONTROL Crea set di dati dal file CSV]**.
1. Seleziona **[!UICONTROL Lancio]** dal riquadro di destra.
1. Nella procedura guidata **[!UICONTROL Flussi di lavoro]** > **[!UICONTROL Crea set di dati dal file CSV]**:
   1. Nel passaggio **[!UICONTROL Configura set di dati]**:
      1. Immetti un **[!UICONTROL Nome]** per il set di dati. Ad esempio: `Sample Data From CSV`.
      1. Aggiungi una **[!UICONTROL Descrizione]** facoltativa. Ad esempio: `Sample data from a CSV file`.
      1. Aggiungi uno o più **[!UICONTROL Tag]** facoltativi oppure seleziona uno o più **[!UICONTROL Tag]** esistenti.

         ![Configura set di dati ad hoc configurato](assets/adhoc-dataset-configure.png)

      1. Seleziona **[!UICONTROL Avanti]**.
   1. Nel passaggio **[!UICONTROL Aggiungi dati]**:
      1. Seleziona **[!UICONTROL Scegli file]** per selezionare il file CSV dal computer o dalla rete. In alternativa, trascinare e rilasciare il file dal percorso del computer o della rete in **[!UICONTROL Trascinare i file]**. Il file è stato caricato e sono visualizzati **[!UICONTROL dati di esempio]**.
      1. Abilita o disabilita **[!UICONTROL Diagnostica errori]** e **[!UICONTROL Abilita acquisizione parziale]** in linea con le tue preferenze. Quando **[!UICONTROL Abilita acquisizione parziale]**, puoi definire una **[!UICONTROL soglia di errore %]**.

         ![Aggiungere dati a un set di dati ad hoc](assets/adhoc-dataset-adddata.png)

      1. Seleziona **[!UICONTROL Fine]**.

Una volta preparati e caricati correttamente i dati, verrai reindirizzato a **[!UICONTROL Set di dati]** nell&#39;interfaccia di Experience Platform.<br/> Viene visualizzata l&#39;**[!UICONTROL Attività set di dati]** per i tuoi **[!UICONTROL Dati di esempio dal set di dati CSV]** con stato ![StatoArancione](/help/assets/icons/StatusOrange.svg) **[!UICONTROL Elaborazione]**.

![Attività set di dati per dati ad hoc](assets/datasets-dataset-activity.png)

Per esaminare i dati ad hoc:

1. Nell&#39;interfaccia di Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Set di dati]**.
1. Selezionare la scheda **[!UICONTROL Sfoglia]** in **[!UICONTROL Set di dati]**. Dovresti visualizzare il set di dati elencato.
1. Selezionare il nome dello schema dalla colonna **[!UICONTROL Schema]**. Esempio: **[!UICONTROL Dati di esempio da CSV...]**

   ![Seleziona schema per set di dati ad hoc](assets/adhoc-schema-selection.png)

1. Nel popup, selezionare **[!UICONTROL Nome schema]**. Ad esempio: **[!UICONTROL Dati di esempio da CSV - Schema ad hoc - XXXXXXXXXXX]**. Sei stato reindirizzato agli **[!UICONTROL Schemi]** > **[!UICONTROL Dati di esempio da CSV - Schema ad hoc - interfaccia XXXXXXXXX]**.

Negli **[!UICONTROL Schemi]** > **[!UICONTROL Dati di esempio da CSV - Schema ad hoc - Interfaccia XXXXXXXXXXX]**:

- Seleziona l&#39;oggetto nome tenant più in alto sotto **[!UICONTROL Schemi]** > **[!UICONTROL Dati di esempio da CSV - schema ad hoc - XXXXXXXXXXX]** per visualizzare i campi all&#39;interno dell&#39;oggetto. I campi all’interno dell’oggetto rappresentano la struttura del file CSV. Lo schema viene creato automaticamente in base al caricamento dei dati ad hoc.

  ![Schema ad hoc](dataset/../assets/adhoc-schema.png)

  >[!NOTE]
  >
  >Il flusso di lavoro definisce tutti i campi dello schema come di tipo String. Non è possibile modificare questo tipo in una fase successiva. Se hai bisogno di maggiore flessibilità nella definizione di uno schema ad hoc, prendi in considerazione [l&#39;utilizzo dell&#39;API per creare uno schema ad hoc](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/tutorials/ad-hoc) e quindi utilizza il [Crea set di dati dallo schema](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide#schema) flusso di lavoro.
  > 




## Configurare una connessione

Per utilizzare il set di dati di Experience Platform in Customer Journey Analytics, crea una connessione che include il set di dati ad hoc risultante dal [flusso di lavoro](#create-a-dataset-with-a-csv-file)

Una connessione consente di integrare i set di dati da Experience Platform a Workspace. Per creare rapporti su questi set di dati, devi prima stabilire una connessione tra i set di dati in Experience Platform e Workspace.

Per creare la connessione:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, seleziona **[!UICONTROL Connessioni]**, facoltativamente da **[!UICONTROL Gestione dati]**, nel menu principale.

1. Selezionare **[!UICONTROL Crea nuova connessione]**.

1. Nella schermata **[!UICONTROL Connessione senza titolo]**:

   1. Denomina e descrivi la connessione in **[!UICONTROL Impostazioni connessione]**.

   1. Selezionare la sandbox corretta dall&#39;elenco **[!UICONTROL Sandbox]** in **[!UICONTROL Impostazioni dati]** e selezionare il numero di eventi giornalieri dall&#39;elenco **[!UICONTROL Numero medio di eventi giornalieri]**.

      ![Impostazioni della connessione](./assets/cja-connections-1.png)

   1. Seleziona **[!UICONTROL Aggiungi set di dati]**.

1. Nel passaggio **[!UICONTROL Seleziona set di dati]** in **[!UICONTROL Aggiungi set di dati]**:

   1. Seleziona il set di dati creato in precedenza, ad esempio **[!UICONTROL Dati di esempio da CSV]** e qualsiasi altro set di dati che desideri includere nella connessione. I set di dati ad hoc hanno il tipo **[!UICONTROL Adhoc]** [!UICONTROL Dataset].

      ![Aggiungere set di dati](./assets/cja-connections-adhoc-2.png)

   1. Seleziona **[!UICONTROL Avanti]**.

1. Nel passaggio **[!UICONTROL Impostazioni set di dati]** in **[!UICONTROL Aggiungi set di dati]**:

   Per il set di dati ad hoc:

   1. Seleziona il tipo di set di dati ad hoc. Esempio: **[!UICONTROL Ricerca]**.
   1. Seleziona una **[!UICONTROL Chiave]** dalle chiavi disponibili definite nello schema ad hoc.
   1. Seleziona una **[!UICONTROL Chiave corrispondente]** da un set di dati evento aggiunto come parte della connessione.
   1. Selezionare l&#39;origine dati corretta dall&#39;elenco **[!UICONTROL Tipo origine dati]**. Se si specifica **[!UICONTROL Altro]**, aggiungere una descrizione per l&#39;origine dati.

   1. Imposta **[!UICONTROL Importa tutti i nuovi dati]** e **[!UICONTROL Recupera i dati esistenti del set di dati]** in base alle tue preferenze.

      ![Configurare i set di dati](./assets/cja-connections-3-adhoc.png)

   1. Seleziona **[!UICONTROL Aggiungi set di dati]**.

   1. Seleziona **[!UICONTROL Salva]**.

Consulta [Impostazioni set di dati ad hoc](/help/connections/create-connection.md#adhoc-dataset) per ulteriori dettagli sulle impostazioni disponibili per i set di dati ad hoc.

>[!IMPORTANT]
>
>Oltre al consiglio generale di non utilizzare set di dati e schemi ad hoc per i dati delle serie temporali, non è possibile utilizzare **[!UICONTROL Crea set di dati dal flusso di lavoro CSV]** per i dati delle serie temporali. Questo flusso di lavoro definisce tutti i campi come di tipo String che non è possibile modificare successivamente. Quando si aggiunge un set di dati basato su serie temporali (evento o riepilogo) a una connessione, questo tipo di set di dati richiede la definizione di almeno un campo di tipo DateTime.<br/>Se è necessario utilizzare dati di serie temporali ad hoc, valutare l&#39;opportunità di [utilizzare l&#39;API per creare uno schema ad hoc](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/ad-hoc#token_type=bearer&expires_in=43197438) e quindi utilizzare il [Crea set di dati dal flusso di lavoro dello schema](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide#schema).


Dopo aver creato una [connessione](/help/connections/overview.md), è possibile eseguire varie attività di gestione, ad esempio [selezionare e combinare i set di dati](/help/connections/combined-dataset.md), [controllare lo stato dei set di dati di una connessione e lo stato dell&#39;acquisizione dei dati](/help/connections/manage-connections.md) e altro ancora.

## Configurare una visualizzazione dati

Una visualizzazione dati è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati da una connessione. Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace, e da quali colonne tali dimensioni e metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione alle attività di reporting in Analysis Workspace.

Per creare la visualizzazione dati:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, seleziona **[!UICONTROL Visualizzazioni dati]**, facoltativamente da **[!UICONTROL Gestione dati]**, nel menu principale.

1. Selezionare **[!UICONTROL Crea nuova visualizzazione dati]**.

1. Nel passaggio **[!UICONTROL Configura]**:

   1. Seleziona la [connessione](#set-up-a-connection) dall&#39;elenco **[!UICONTROL Connessione]**.

   1. Assegna un nome e (facoltativamente) una descrizione alla connessione.

      ![Configurare la visualizzazione dati](./assets/cja-dataview-1.png)

   1. Seleziona **[!UICONTROL Salva e continua]**.

1. Nel passaggio **[!UICONTROL Componenti]**:

   1. Aggiungi qualsiasi campo schema e/o componente standard da includere nelle caselle dei componenti **[!UICONTROL METRICS]** o **[!UICONTROL DIMENSIONS]**. Assicurati di aggiungere campi rilevanti dal set di dati che contiene i dati ad hoc. Per accedere a questi campi:

      1. Seleziona **[!UICONTROL Set di dati evento]**.
      1. Seleziona **[!UICONTROL Campi ad hoc e relazionali]**.

         ![Visualizzazione dati - componenti ad hoc](assets/cja-dataview-components-adhoc.png)

      1. Trascina i campi dagli schemi ad hoc in **[!UICONTROL METRICS]** o **[!UICONTROL DIMENSIONS]**.



   1. Facoltativamente, utilizzare [campi derivati](/help/data-views/derived-fields/derived-fields.md) per modificare qualsiasi campo ad hoc dal tipo e formato di stringa predefiniti a un altro tipo o formato.

   1. Seleziona **[!UICONTROL Salva e continua]**.

1. Nel passaggio **[!UICONTROL Impostazioni]**:

   Lasciare le impostazioni immutate e selezionare **[!UICONTROL Salva e termina]**.

Per ulteriori informazioni su come creare e modificare una visualizzazione dati, vedere [Panoramica delle visualizzazioni dati](../data-views/data-views.md). Quali componenti sono disponibili per l’utilizzo nella visualizzazione dati e come utilizzare le impostazioni di segmenti e sessioni.


## Configurare un progetto

Analysis Workspace è uno strumento di browser flessibile che consente di creare analisi rapidamente e condividere informazioni basate sui dati. Usa i progetti Workspace per combinare componenti dati, tabelle e visualizzazioni per sviluppare analisi da condividere con altri nella tua organizzazione.

Per creare il progetto:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, seleziona **[!UICONTROL Progetti]** nel menu principale.

1. Seleziona **[!UICONTROL Progetti]** nel menu di navigazione a sinistra.

1. Seleziona **[!UICONTROL Crea progetto]**.

1. Seleziona **[!UICONTROL Progetto vuoto]**.

1. Seleziona la [visualizzazione dati](#set-up-a-data-view) dall&#39;elenco.

1. Per creare il primo rapporto, inizia a trascinare dimensioni e metriche sulla [!UICONTROL tabella a forma libera] nel [!UICONTROL pannello]. Inclusione di metriche o dimensioni basate su dati ad hoc.

Per ulteriori informazioni su come creare progetti e generare analisi utilizzando componenti, visualizzazioni e pannelli, consulta la sezione [Panoramica di Analysis Workspace](../analysis-workspace/home.md).

>[!SUCCESS]
>
>Hai completato tutti i passaggi. Per iniziare, definisci quali dati ad hoc desideri raccogliere (file CSV). Hai utilizzato il flusso di lavoro per creare un set di dati e uno schema ad hoc da quel file CSV. Hai definito una connessione in Customer Journey Analytics per utilizzare i dati ad hoc acquisiti e altri dati. La definizione della visualizzazione dati ti consente di specificare la dimensione e le metriche da utilizzare e infine hai creato il tuo primo progetto per la visualizzazione e l’analisi dei dati.
