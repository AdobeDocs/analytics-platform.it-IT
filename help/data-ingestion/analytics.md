---
title: Acquisizione e utilizzo di dati dal tradizionale Adobe Analytics
description: Spiegare come acquisire dati dal tradizionale Adobe Analytics
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: f910f8e810c5c5d6f4d43aff2b609d8bf6c131ca
workflow-type: tm+mt
source-wordcount: '1051'
ht-degree: 11%

---


# Acquisizione e utilizzo di dati dal tradizionale Adobe Analytics

Questa guida rapida spiega come utilizzare in Customer Journey Analytics i dati raccolti da Adobe Analytics.

>[!PREREQUISITES]
>
>Adobe Analytics è concesso in licenza e distribuito su uno o più siti web, utilizzando uno dei metodi di implementazione documentati:
>
>- [Implementazione di Analytics tramite Experience Platform Edge](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/overview.html?lang=it)
>
>- [Implementazione di Analytics tramite l’estensione Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=it)
>
>- [Implementare Analytics utilizzando Javascript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=en)


A questo scopo, devi:

- **Configurare un connettore sorgente Adobe Analytics** in Adobe Experience Platform. In questo modo puoi acquisire i dati Adobe Analytics correnti in un set di dati in Adobe Experience Platform.

- **Impostare una connessione** in Customer Journey Analytics. Questa connessione deve includere almeno il set di dati Adobe Experience Platform.

- **Configurare una visualizzazione dati** in Customer Journey Analytics per definire le metriche e le dimensioni da utilizzare in Analysis Workspace.

- **Configurare un progetto** in Customer Journey Analytics per generare rapporti e visualizzazioni.


>[!NOTE]
>
>Questa è una guida semplificata su come acquisire i dati, utilizzando il connettore di origine Adobe Analytics, e utilizzarli in Customer Journey Analytics.  Si raccomanda vivamente di studiare le informazioni aggiuntive quando si fa riferimento a tali informazioni.


## Configurare un connettore sorgente Adobe Analytics

Il connettore di origine Adobe Analytics consente di inserire i dati della suite di rapporti Adobe Analytics in Adobe Experience Platform.

Per creare un connettore sorgente Adobe Analytics:

1. Nell’interfaccia utente di Platform, seleziona **[!UICONTROL Sources]** dalla barra a sinistra.

2. Seleziona **[!UICONTROL Adobe applications]** dall&#39;elenco di [!UICONTROL CATEGORIES].

3. Seleziona **[!UICONTROL Set up]** o **[!UICONTROL Add data]** nel riquadro Adobe Analytics.

   ![Origini](./assets/sources-overview.png)

4. Seleziona **[!UICONTROL Report suite]**. Dall’elenco delle suite di rapporti, seleziona quella da utilizzare.

   ![Suite di rapporti](./assets/report-suites.png)

   Seleziona **[!UICONTROL Next]**.

5. Seleziona **[!UICONTROL Default schema]** come [!UICONTROL Target schema]. Adobe Experience Platform creerà automaticamente lo schema e il set di dati corrispondenti per mappare tutti i campi standard dalla suite di rapporti Adobe Analytics selezionata.

   ![Schema predefinito](./assets/default-schema.png)

   Seleziona **[!UICONTROL Next]**.

6. Denomina il flusso di dati e (facoltativamente) fornisci una descrizione.

   ![Dettagli del flusso di dati](./assets/dataflow-detail.png)

   Seleziona **[!UICONTROL Next]**.

7. Controlla la connessione e seleziona **[!UICONTROL Finish]**.

   ![Rivedete](./assets/review.png)


Una volta creata la connessione, il flusso di dati viene creato automaticamente per popolare un set di dati con i dati Adobe Analytics dalla suite di rapporti, compresa l’acquisizione di fino a 13 mesi di dati storici.

Al termine dell’acquisizione iniziale, i dati della suite di rapporti Adobe Analytics sono pronti per essere utilizzati dal Customer Journey Analytics.

Vedi [Creare una connessione sorgente Adobe Analytics nell’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) per un tutorial molto più completo.


## Configurazione di una connessione

Per utilizzare i dati Adobe Experience Platform nel Customer Journey Analytics, è necessario creare una connessione che includa i dati risultanti dalla configurazione dello schema, del set di dati e del flusso di lavoro.

Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti su questi set di dati, è innanzitutto necessario stabilire una connessione tra i set di dati in Adobe Experience Platform e Workspace.

Per creare la connessione:

1. Nell’interfaccia utente del Customer Journey Analytics, seleziona **[!UICONTROL Connections]** nella navigazione superiore.

2. Seleziona **[!UICONTROL Create new connection]**.

3. In [!UICONTROL Untitled connection] schermo:

   Assegnare un nome e descrivere la connessione in [!UICONTROL Connection Settings].

   Seleziona la sandbox corretta dal [!UICONTROL Sandbox] elenco in [!UICONTROL Data settings] e seleziona il numero di eventi giornalieri dal [!UICONTROL Avergage number of daily events] elenco.

   ![Impostazioni connessione](./assets/cja-connections-1.png)

   Seleziona **[!UICONTROL Add datsets]**.

   In [!UICONTROL Select datasets] passo [!UICONTROL Add datasets]:

   - Seleziona il set di dati creato automaticamente dal connettore di origine Adobe Analytics e qualsiasi altro set di dati da includere nella connessione.

      ![Aggiungi set di dati](./assets/cja-connections-2a.png)

   - Seleziona **[!UICONTROL Next]**.
   In [!UICONTROL Datasets settings] passo [!UICONTROL Add datasets]:

   - Per ogni set di dati:

      - Seleziona una [!UICONTROL Person ID] dalle identità disponibili definite negli schemi di set di dati in Adobe Experience Platform.

      - Seleziona l’origine dati corretta dal [!UICONTROL Data source type] elenco. Se si specifica **[!UICONTROL Other]** quindi aggiungi una descrizione per l’origine dati.

      - Imposta **[!UICONTROL Import all new data]** e **[!UICONTROL Dataset backfill existing data]** secondo le tue preferenze.

      ![Configurare i set di dati](./assets/cja-connections-3.png)

   - Seleziona **[!UICONTROL Add datasets]**.
   Seleziona **[!UICONTROL Save]**.

Vedi [Panoramica delle connessioni](../connections/overview.md) per ulteriori informazioni su come creare e gestire una connessione e come selezionare e combinare i set di dati.

## Configurare una visualizzazione dati

Una visualizzazione dati è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati da una connessione. Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace, e da quali colonne tali dimensioni e metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione alle attività di reporting in Analysis Workspace.

Per creare la visualizzazione dati:

1. Nell’interfaccia utente del Customer Journey Analytics, seleziona **[!UICONTROL Data views]** nella navigazione superiore.

2. Seleziona **[!UICONTROL Create new data view]**.

3. In [!UICONTROL Configure] passo:

   Seleziona la connessione dal [!UICONTROL Connection] elenco.

   Nome e (facoltativamente) descrizione della connessione.

   ![Configurazione della visualizzazione dati](./assets/cja-dataview-1.png)

   Seleziona **[!UICONTROL Save and continue]**.

4. In [!UICONTROL Components] passo:

   Aggiungi qualsiasi campo dello schema e/o componente standard da includere nel [!UICONTROL METRICS] o [!UICONTROL DIMENSIONS] caselle dei componenti.

   ![Componenti della visualizzazione dati](./assets/cja-dataview-2.png)

   Seleziona **[!UICONTROL Save and continue]**.

5. In [!UICONTROL Settings] passo:

   Impostazioni della ![visualizzazione dati](./assets/cja-dataview-3.png)

   Lascia le impostazioni così come sono e seleziona **[!UICONTROL Save and finish]**.

Vedi [Panoramica delle visualizzazioni dati](../data-views/data-views.md) per ulteriori informazioni su come creare e modificare una visualizzazione dati, quali componenti sono disponibili per la visualizzazione dati e come utilizzare le impostazioni di filtro e sessioni.


## Configurare un progetto

Analysis Workspace è uno strumento browser flessibile che ti consente di creare rapidamente analisi e condividere informazioni basate sui tuoi dati. Puoi utilizzare i progetti Workspace per combinare componenti dati, tabelle e visualizzazioni per creare le tue analisi e condividerle con chiunque all’interno della tua organizzazione.

Per creare il progetto:

1. Nell’interfaccia utente del Customer Journey Analytics, seleziona **[!UICONTROL Projects]** nella navigazione superiore.

2. Seleziona **[!UICONTROL Projects]** nella navigazione a sinistra.

3. Seleziona **[!UICONTROL Create project]**.

   ![Progetto Workspace](./assets/cja-projects-1.png)

   Seleziona **[!UICONTROL Blank project]**.

   ![Workspace - Progetto vuoto](./assets/cja-projects-2.png)

4. Seleziona la visualizzazione dati dall’elenco.

   ![Visualizzazione dati Seleziona area di lavoro](./assets/cja-projects-3.png).

5. Inizia a trascinare dimensioni e metriche sul [!UICONTROL Freeform table] in [!UICONTROL Panel] per creare il primo rapporto. Ad esempio, trascina `Program Points Balance` e `Page View` come metriche e `email` come dimensione per ottenere una rapida panoramica dei profili che hanno visitato il tuo sito web e che fanno anche parte del programma fedeltà che raccoglie punti fedeltà.

   ![Area di lavoro - Primo rapporto](./assets/cja-projects-5.png)

Vedi [Panoramica di Analysis Workspace](../analysis-workspace/home.md) per ulteriori informazioni su come creare progetti e generare analisi utilizzando componenti, visualizzazioni e pannelli.


>[!SUCCESS]
>
>Hai completato tutti i passaggi. A partire dalla configurazione del connettore dell’origine dati Adobe Analytics e del connettore per la suite di rapporti, i dati Adobe Analytics vengono caricati automaticamente in Adobe Experience Platform. Hai definito una connessione in Customer Journey Analytics per utilizzare i dati Adobe Analytics acquisiti e altri dati. La definizione della visualizzazione dati ti consente di specificare la dimensione e le metriche da utilizzare e infine hai creato il tuo primo progetto per la visualizzazione e l’analisi dei dati.







