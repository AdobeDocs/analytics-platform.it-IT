---
title: Inserire e usare i dati dalla versione tradizionale di Adobe Analytics
description: Spiegare come inserire dati provenienti dalla versione tradizionale di Adobe Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: 5cbfa922-6d6e-453a-9558-abfcfb80449d
role: Admin
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 82%

---

# Acquisire e utilizzare dati da Adobe Analytics

Questa guida introduttiva spiega come utilizzare in Customer Journey Analytics i dati raccolti da Adobe Analytics.

>[!PREREQUISITES]
>
>Adobe Analytics è concesso in licenza e implementato su uno o più siti Web, utilizzando uno dei metodi di implementazione documentati:
>
>- [Implementare Analytics tramite Experience Platform Edge](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/overview.html)
>
>- [Implementare Analytics tramite l’estensione Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=it)
>
>- [Implementare Analytics tramite JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=it)

A questo scopo, è necessario:

- **Configurare un connettore di origine di Adobe Analytics** in Adobe Experience Platform. Il connettore di origine si occupa di acquisire i dati Adobe Analytics correnti in un set di dati in Adobe Experience Platform.

- **Impostare una connessione** in Customer Journey Analytics. La connessione deve (almeno) includere il set di dati di Adobe Experience Platform.

- **Configurare una visualizzazione dati** in Customer Journey Analytics per definire le metriche e le dimensioni da utilizzare in Analysis Workspace.

- **Configurare un progetto** in Customer Journey Analytics per generare rapporti e visualizzazioni.


>[!NOTE]
>
>Questa guida rapida è una guida semplificata su come acquisire i dati utilizzando il connettore di origine di Adobe Analytics e utilizzarli in Customer Journey Analytics. Ti consigliamo vivamente di esaminare le informazioni aggiuntive quando vi fai riferimento.


## Configurare un connettore di origine di Adobe Analytics

Il connettore di origine di Adobe Analytics consente di inserire i dati della suite di rapporti di Adobe Analytics in Adobe Experience Platform.

Per creare un connettore di origine di Adobe Analytics:

1. Nell’interfaccia utente di Platform, seleziona **[!UICONTROL Sources]** (Origini), dalla barra a sinistra.

2. Seleziona **[!UICONTROL Adobe applications]** (Applicazioni Adobe) dall’elenco [!UICONTROL CATEGORIES] (CATEGORIE).

3. Seleziona **[!UICONTROL Set up]** (Configura) o **[!UICONTROL Add data]** (Aggiungi dati) nel riquadro Adobe Analytics.

   ![Finestra di Adobe Experience Platform con Origini selezionate insieme alle applicazioni Adobe e Aggiungi dati evidenziati.](./assets/sources-overview.png)

4. Seleziona **[!UICONTROL Report suite]** (Suite di rapporti). Dall’elenco delle suite di rapporti, seleziona quella da utilizzare.

   ![Finestra di Adobe Experience Platform con l’elenco delle suite di rapporti](./assets/report-suites.png)

   Seleziona **[!UICONTROL Next]** (Avanti).

5. Seleziona **[!UICONTROL Default schema]** (Schema predefinito) come [!UICONTROL Target schema] (Schema di destinazione). Adobe Experience Platform crea automaticamente lo schema e il set di dati corrispondenti per mappare tutti i campi standard dalla suite di rapporti Adobe Analytics selezionata.

   ![Finestra di Adobe Experience Platform con lo schema predefinito selezionato](./assets/default-schema.png)

   Seleziona **[!UICONTROL Next]** (Avanti).

6. Assegna un nome al flusso di dati e (facoltativamente) fornisci una descrizione.

   ![Finestra di Adobe Experience Platform che evidenzia la sezione dei dettagli del flusso di dati](./assets/dataflow-detail.png)

   Seleziona **[!UICONTROL Next]** (Avanti).

7. Controlla la connessione e seleziona **[!UICONTROL Finish]** (Fine).

   ![Finestra di Adobe Experience Platform che evidenzia le sezioni Connetti e Tipo di dati per la revisione](./assets/review.png)


Una volta creata la connessione, il flusso di dati viene creato automaticamente per popolare un set di dati con i dati di Adobe Analytics dalla suite di rapporti. Il flusso di dati acquisisce fino a 13 mesi di dati storici per le sandbox di produzione. La retrocompilazione nelle sandbox non di produzione è limitata a 3 mesi.

Al termine dell’inserimento iniziale, i dati della suite di rapporti Adobe Analytics sono pronti per essere utilizzati da Customer Journey Analytics.

Consulta la sezione [Creare una connessione sorgente di Adobe Analytics nell’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) per un tutorial molto più completo.


## Configurare una connessione

Per utilizzare i dati di Adobe Experience Platform in Customer Journey Analytics, crea una connessione che include i dati risultanti dalla configurazione dello schema, del set di dati e del flusso di lavoro.

Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti su questi set di dati, devi prima stabilire una connessione tra i set di dati in Adobe Experience Platform e Workspace.

Per creare la connessione:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, selezionare **[!UICONTROL Connections]**, facoltativamente da **[!UICONTROL Data management]**, nel menu principale.

2. Seleziona **[!UICONTROL Create new connection]** (Crea uova connessione).

3. Nella schermata [!UICONTROL Untitled connection] (Connessione senza titolo):

   Assegna un nome e una descrizione alla connessione in [!UICONTROL Connection Settings] (Impostazioni della connessione).

   Seleziona la sandbox corretta dall’elenco [!UICONTROL Sandbox] in [!UICONTROL Data settings] (Impostazioni dati) e seleziona il numero di eventi giornalieri dall’elenco [!UICONTROL Average number of daily events] (Numero medio di eventi giornalieri).

   ![Impostazioni della connessione](./assets/cja-connections-1.png)

   Seleziona **[!UICONTROL Add datasets]** (Aggiungi set di dati).

   Nel passaggio [!UICONTROL Select datasets] (Seleziona set di dati) in [!UICONTROL Add datasets] (Aggiungi set di dati):

   - Seleziona il set di dati creato automaticamente dal connettore di origine di Adobe Analytics e qualsiasi altro set di dati da includere nella connessione.

     ![Finestra Aggiungi set di dati](./assets/cja-connections-2a.png)

   - Seleziona **[!UICONTROL Next]** (Aggiungi set di dati).

   Nel passaggio [!UICONTROL Datasets settings] (Impostazioni set di dati) in [!UICONTROL Add datasets] (Aggiungi set di dati):

   - Per ogni set di dati:

      - Seleziona un [!UICONTROL Person ID] (ID persona) tra le identità disponibili definite negli schemi di set di dati in Adobe Experience Platform.

      - Seleziona l’origine dati corretta dall’elenco [!UICONTROL Data source type] (Tipo di origine dati). Se specifichi **[!UICONTROL Other]** (Altro), aggiungi una descrizione per l’origine dati.

      - Imposta **[!UICONTROL Import all new data]** (Importa tutti i nuovi dati) e **[!UICONTROL Dataset backfill existing data]** (Dati esistenti di backfill del set di dati) secondo le tue preferenze.

     ![Configurare i set di dati](./assets/cja-connections-3a.png)

   - Seleziona **[!UICONTROL Add datasets]** (Aggiungi set di dati).

   Seleziona **[!UICONTROL Save]** (Salva).

Per ulteriori informazioni su come creare e gestire una connessione e come selezionare e combinare i set di dati, consulta la sezione [Panoramica delle connessioni](../connections/overview.md).

## Configurare una visualizzazione dati

Una visualizzazione dati è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati da una connessione. Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace, e da quali colonne tali dimensioni e metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione alle attività di reporting in Analysis Workspace.

Per creare la visualizzazione dati:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, selezionare **[!UICONTROL Data views]**, facoltativamente da **[!UICONTROL Data management]**, nel menu principale.

2. Seleziona **[!UICONTROL Create new data view]** (Crea nuova visualizzazione dati).

3. Nel passaggio [!UICONTROL Configure] (Configura):

   Seleziona la connessione dall’elenco [!UICONTROL Connection] (Connessioni).

   Assegna un nome e (facoltativamente) una descrizione alla connessione.

   ![Configurare la visualizzazione dati](./assets/cja-dataview-1.png)

   Seleziona **[!UICONTROL Save and continue]** (Salva e continua).

4. Nel passaggio [!UICONTROL Components] (Componenti):

   Aggiungi qualsiasi campo dello schema e/o componente standard che desideri includere nelle caselle dei componenti [!UICONTROL METRICS] (METRICHE) o [!UICONTROL DIMENSIONS] (DIMENSIONI).

   ![Componenti della visualizzazione dati](./assets/cja-dataview-2.png)

   Seleziona **[!UICONTROL Save and continue]** (Salva e continua).

5. Nel passaggio [!UICONTROL Settings] (Impostazioni):

   ![Impostazioni della visualizzazione dati](./assets/cja-dataview-3.png)

   Lascia le impostazioni così come sono e seleziona **[!UICONTROL Save and finish]** (Salva e fine).

Per ulteriori informazioni su come creare e modificare una visualizzazione dati, quali componenti sono disponibili per la visualizzazione dati e come utilizzare le impostazioni di filtro e sessioni, consulta la sezione [Panoramica delle visualizzazioni dati](../data-views/data-views.md).


## Configurare un progetto

Analysis Workspace è uno strumento basato su browser flessibile che consente di creare rapidamente le analisi e condividere i dati rilevati sulla base dei tuoi dati. Usa i progetti Workspace per combinare componenti dati, tabelle e visualizzazioni per sviluppare analisi da condividere con altri nella tua organizzazione.

Per creare il progetto:

1. Nell&#39;interfaccia utente di Customer Journey Analytics, seleziona **[!UICONTROL Projects]** nel menu principale.

2. Seleziona **[!UICONTROL Projects]** (Progetti) nel pannello di navigazione a sinistra.

3. Seleziona **[!UICONTROL Create project]** (Crea progetto).

   ![Progetto Workspace](./assets/cja-projects-1.png)

   Seleziona **[!UICONTROL Blank project]** (Progetto vuoto).

   ![Workspace - Progetto vuoto](./assets/cja-projects-2.png)

4. Seleziona la visualizzazione dati dall’elenco.

   ![Visualizzazione Select Data (Seleziona dati) di Workspace](./assets/cja-projects-3.png).

5. Per creare il primo rapporto, inizia a trascinare dimensioni e metriche su [!UICONTROL Freeform table] in [!UICONTROL Panel]. Ad esempio, trascina `Program Points Balance` e `Page View` come metriche e `email` come dimensione per ottenere una panoramica rapida dei profili che hanno visitato il tuo sito Web e che fanno parte del programma di fidelizzazione per la raccolta di punti di fidelizzazione.

   ![Workspace - Primo rapporto](./assets/cja-projects-5.png)

Per ulteriori informazioni su come creare progetti e generare analisi utilizzando componenti, visualizzazioni e pannelli, consulta la sezione [Panoramica di Analysis Workspace](../analysis-workspace/home.md).


>[!SUCCESS]
>
>Hai completato tutti i passaggi. Partendo dalla configurazione del connettore dell’origine dati di Adobe Analytics e del connettore per la suite di rapporti, i dati di Adobe Analytics vengono caricati automaticamente in Adobe Experience Platform. Hai definito una connessione in Customer Journey Analytics per utilizzare i dati di Adobe Analytics acquisiti e altri dati. La definizione della visualizzazione dati ti consente di specificare la dimensione e le metriche da utilizzare e infine hai creato il tuo primo progetto per la visualizzazione e l’analisi dei dati.

