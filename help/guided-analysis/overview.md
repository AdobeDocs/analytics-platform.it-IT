---
title: Panoramica dell’analisi guidata
description: Metodo di analisi dei dati in Customer Journey Analytics che consente ai team di prodotto di ottenere rapidamente informazioni approfondite di alta qualità.
keywords: Product Analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '1719'
ht-degree: 100%

---

# Panoramica dell’analisi guidata

L’analisi guidata consente agli utenti, dagli addetti marketing e prodotti fino agli analisti, di gestire in autonomia dati e approfondimenti di alta qualità sul percorso del cliente tramite flussi di lavoro guidati, basati sui dati cross-channel di Customer Journey Analytics. Analogamente alle scorecard per Analysis Workspace e dispositivi mobili, l’analisi guidata utilizza dati provenienti da una [Visualizzazione dati](/help/data-views/data-views.md), che fa riferimento ai dati in Adobe Experience Platform tramite un [Connessione](../connections/overview.md). Molti rapporti creati nell’analisi guidata possono essere trasferiti facilmente in Analysis Workspace per ulteriori ricerche.

Sono disponibili le seguenti analisi guidate:

| Icona | Analisi | Descrizione |
| :----:|--- | --- |
| ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) | [Crescita attiva](types/active-growth.md) | Identifica gli utenti nuovi, mantenuti, che ritornano o inattivi. |
| ![ConversionTrens](/help/assets/icons/ConversionTrends.svg) | [Tendenze di conversione](types/conversion-trends.md) | Tieni traccia delle modifiche nei tassi di conversione nel tempo. |
| ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) | [Coinvolgimento](types/engagement.md) | Comprendi l’ampiezza e la profondità del coinvolgimento delle funzioni. |
| ![FirstUse](/help/assets/icons/FirstUse.svg) | [Analisi dell’impatto del primo utilizzo](types/first-use-impact.md) | Misura l’impatto del primo utilizzo delle funzioni sugli indicatori chiave. |
| ![Istogramma](/help/assets/icons/Histogram.svg) | [Frequenza](types/frequency.md) | Misura il coinvolgimento in base alla frequenza d’uso. |
| ![Funnel di conversione](/help/assets/icons/ConversionFunnel.svg) | [Funnel](types/funnel.md) | Confronta i tassi di conversione tra passaggi. |
| ![NetGrowth](/help/assets/icons/NetGrowth.svg) | [Crescita netta](types/net-growth.md) | Stai guadagnando o perdendo utenti? |
| ![Rilascio](/help/assets/icons/Release.svg) | [Impatto sulla versione](types/release-impact.md) | Confronta le prestazioni in periodi uguali prima e dopo il rilascio. |
| ![Mantenimento](/help/assets/icons/Retention.svg) | [Mantenimento](types/retention.md) | Misura le abitudini attuali riguardo il ritorno degli utenti. |
| ![Timeline](/help/assets/icons/Timeline.svg) | [Timeline](types/timeline.md) | Esplora i pattern nell’attività della sessione. |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Tendenze](types/trends.md) | Misura il coinvolgimento degli utenti nel tempo. |



## Accesso

Puoi accedere all’Analisi guidata dalla pagina Home di Customer Journey Analytics.

1. Dalla pagina Home, seleziona **[!UICONTROL Guided analysis]**, che ti indirizza direttamente ad [Analisi delle tendenze](types/trends.md).

   ![Riquadro della pagina di destinazione](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Seleziona **[!UICONTROL Create new]** per vedere le diverse opzioni di visualizzazione e scegliere un punto di partenza diverso per l’analisi.

   ![Creare un nuovo modale](assets/create-new-modal.png){style="border:1px solid gray"}

Puoi accedere all’analisi guidata anche dall’interno di un progetto Analysis Workspace.

1. Seleziona **[!UICONTROL Blank project]** dalla pagina Home per creare un progetto Workspace vuoto.

   ![Creare un progetto vuoto](assets/blank-project.png){style="border:1px solid gray"}

1. Seleziona ![Analisi guidata](/help/assets/icons/GuidedAnalysis.svg) **[!UICONTROL Guided Analysis]** nella barra a sinistra.

   ![Barra a sinistra di Workspace](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. Trascina una nuova analisi nell’area di lavoro di Workspace, quindi seleziona **[!UICONTROL Create]** per generare l’analisi desiderata, ad esempio **[!UICONTROL Create Trends]**. Puoi anche trascinare un’analisi esistente nell’area di lavoro di Workspace dalla sezione **[!UICONTROL Saved]**.

   ![Creare un pannello](assets/create-guided-analysis-panel.gif)

## Interfaccia

L’interfaccia per l’analisi guidata segue un formato di domanda e risposta. Crea una domanda nella barra delle query, quindi ottieni una risposta con un approfondimento scritto, un grafico e una tabella. A questo punto potrai rispondere alla domanda successiva con le impostazioni di visualizzazione e analisi.

L’analisi guidata utilizza i seguenti elementi dell’interfaccia utente:

| Anteprima interfaccia | Elemento nell’interfaccia utente | Descrizione |
| --- | --- | --- |
| ![Barra delle query](assets/query-rail.png){style="border:1px solid gray"} | **[!UICONTROL Query rail]** | Configura la *domanda* selezionando i componenti desiderati (eventi, proprietà e segmenti) che compongono un’analisi. Le seguenti opzioni sono disponibili per tutte le analisi, con impostazioni aggiuntive disponibili per singole visualizzazioni. <ul><li>**Visualizzazione**: seleziona una delle opzioni per passare a una nuova analisi. Le selezioni delle query vengono mantenute entro i limiti consentiti per il nuovo tipo di analisi.</li><li>**Eventi**: gli eventi che desideri misurare. Ogni analisi applica limiti diversi al numero di eventi che è possibile configurare.  Gli eventi a volte sono etichettati come **[!UICONTROL Start and return events]**, **[!UICONTROL Steps]** o **[!UICONTROL Key indicators]**. Nell’analisi gli eventi sono identificati utilizzando 1, 2, ...<br/>Seleziona ![Aggiungi](/help/assets/icons/Add.svg) **[!UICONTROL Add an event]** per aggiungere nuovi eventi.</li><li>**[!UICONTROL Factors]**: se disponibile, consente di specificare fattori quali data da e primo evento.</li><li>**Conteggiato come**: metodo di conteggio che desideri applicare agli eventi selezionati. Seleziona dal menu a discesa.</li><li>**Segmenti**: i segmenti che desideri misurare. Ogni analisi applica limiti diversi al numero di segmenti che è possibile configurare. Nell’analisi i segmenti sono identificati utilizzando A, B, ...<br/>Seleziona ![Aggiungi](/help/assets/icons/Add.svg) **[!UICONTROL Add a segment]** per aggiungere nuovi segmenti.</li><li>**[!UICONTROL Breakdown]**: se disponibile, il raggruppamento da applicare all&#39;analisi.</li></ul>In alcune impostazioni sono disponibili configurazioni aggiuntive.<ul><li>**Filtri**: utilizza ![Filtro](assets/filter.png) per limitare gli eventi o i segmenti in base a dimensioni specifiche. Quando viene selezionata una dimensione, vengono utilizzati entrambi i criteri di filtro standard (ad esempio **[!UICONTROL Equals]**, **[!UICONTROL Contains]** o **[!UICONTROL Ends with]**) e sono disponibili i primi 1000 valori della dimensione.<br/>Seleziona ![Filtro](/help/assets/icons/Filter.svg) per aggiungere altri filtri.<br/>Seleziona ![Rimuovi](/help/assets/icons/Remove.svg) per rimuovere un filtro.</li><li>**Altre azioni**: utilizza ![Altre](/help/assets/icons/More.svg) per selezionare azioni come<ul><li>![Rinomina](/help/assets/icons/Rename.svg) **[!UICONTROL Rename]**: per rinominare un evento o un segmento.</li><li>![Duplica](/help/assets/icons/Duplicate.svg) **[!UICONTROL Duplicate]**: per duplicare un evento o un segmento.</li><li>![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Remove]**: per rimuovere un evento, segmento o raggruppamento.</li><li>![Modifica segmento](/help/assets/icons/Edit.svg) **[!UICONTROL Edit segment]**: per modificare un segmento nel [Generatore di segmenti](/help/components/segments/seg-builder.md).</li><li>![Stella](/help/assets/icons/Star.svg) **[!UICONTROL Add to favorites]**: per aggiungere il segmento all’elenco dei segmenti preferiti nel [Gestore segmenti](/help/components/segments/seg-manage.md).</li><li>![SaveAsFloppy](/help/assets/icons/SaveAsFloppy.svg) **[!UICONTROL Save as]**: per salvare il segmento come nuovo componente. Nella finestra di dialogo **[!UICONTROL Save segments to components]**, puoi specificare un nome di segmento e una descrizione. Puoi selezionare ![StarOutline](/help/assets/icons/StarOutline.svg) per contrassegnare il nuovo segmento come preferito. Seleziona **[!UICONTROL Save]** per salvare il segmento come nuovo segmento.</li><li>![Collega](/help/assets/icons/Link.svg) **[!UICONTROL Link start and return events]**.: per collegare eventi di inizio e ritorno in un’analisi [Mantenimento](types/retention.md).</li><li>![Scollega](/help/assets/icons/Unlink.svg) **[!UICONTROL Unlink start and return events]**: per scollegare gli eventi di inizio e di ritorno in un’analisi [Mantenimento](types/retention.md).</li></ul></li></ul> |
| ![Grafico](assets/chart.png){style="border:1px solid gray"} | **[!UICONTROL Chart]** | Una visualizzazione dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. La visualizzazione che vedi dipende dalla vista e dalle impostazioni sopra il grafico. Il grafico include anche: <ul><li>**Descrizioni**: passa il puntatore su un punto dati del grafico per visualizzare una descrizione comando con ulteriori informazioni.</li><li>**Legenda**: passa il puntatore sulla serie di legende del grafico per visualizzare le definizioni, se disponibili, per concentrarti su tale serie e nasconderne temporaneamente altre. Seleziona una serie nella legenda per nasconderla.</li><li>**Annotazioni**: le [annotazioni](../components/annotations/overview.md) applicabili sono visibili tra la visualizzazione e la legenda. Vengono visualizzate come ![icona Annotazione](assets/annotation.png) nel colore configurato dell’annotazione. Le analisi che mostrano i dati nel tempo inseriscono l’![icona Annotazione](assets/annotation.png) sotto la data o l’intervallo di date configurato. Le analisi che non mostrano dati nel tempo mostrano l’![Icona Annotazione](assets/annotation.png) nell’angolo inferiore a destra del grafico.</li><li>**Seleziona azioni**: per esporre le azioni successive disponibili selezionando un qualsiasi punto dati. Le opzioni includono **Salva segmento**.</li></ul> |
| ![Tabella](assets/table.png){style="border:1px solid gray"} | **[!UICONTROL Table]** | Una rappresentazione in tabella dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. Righe della tabella che utilizzano come riferimento gli identificatori evento (1, 2, ...) e segmento (A, B, ...). Le colonne della tabella dipendono dall’analisi sopra il grafico. Per ogni riga la tabella include anche: <ul><li>**Seleziona azioni**: attiva o disattiva ![Mostra nascondi icona](assets/hide-in-chart.png) per nascondere o esporre una serie di grafici per una riga. Seleziona ![Altro](/help/assets/icons/More.svg) per ulteriori azioni. Le opzioni includono **Salva segmento**.</li></ul> |
| ![Impostazioni di visualizzazione](assets/visualization-settings.png){style="border:1px solid gray"} | **[!UICONTROL Visualization settings]** | Opzioni sopra il grafico che consentono di porre la domanda successiva e personalizzare la modalità di restituzione dei dati del grafico e della tabella. Le seguenti opzioni sono disponibili per tutte le analisi, con impostazioni aggiuntive disponibili per singole analisi. <ul><li>![GraphTrend](/help/assets/icons/GraphTrend.svg) **Impostazioni grafico**: regola con precisione la visualizzazione del grafico e della tabella. Le opzioni disponibili dipendono dall’analisi selezionata.</li><li>![Livello](/help/assets/icons/Layer.svg) **Impostazioni sovrapposizione**: aggiungi una sovrapposizione. Le opzioni disponibili dipendono dall’analisi selezionata.</li><li>![Bucket](/help/assets/icons/Bucket.svg) **[!UICONTROL Bucket settings]**: impostazione bucket automatico o applicazione di bucket personalizzati ai dati. Le opzioni disponibili dipendono dall’analisi selezionata.<li>![DataCorrelated](/help/assets/icons/DataCorrelated.svg) **[!UICONTROL Compare settings]**: confronta i dati con un intervallo di date specifico. Le opzioni disponibili dipendono dall’analisi selezionata.</li><li>![Passi](/help/assets/icons/Footsteps.svg) **[!UICONTROL Display settings]**: per selezionare come mostrare i dati. Le opzioni disponibili dipendono dall’analisi selezionata.<li>![Calendario](/help/assets/icons/Calendar.svg) **Intervallo di date**: selettore calendario che consente di determinare l’intervallo di date dell’analisi. È inoltre possibile selezionare un intervallo per le analisi con tendenze, ad esempio giornaliere, settimanali o mensili.</li><li>![Lampadina](/help/assets/icons/LightBulb.svg) **Insight**: approfondimenti contestuali a seconda dell’analisi visualizzata. Queste informazioni approfondite forniscono osservazioni per l’analisi corrente. Se sono disponibili più informazioni, puoi visualizzarle utilizzando le frecce a destra. È possibile attivare o disattivare la visibilità di questa casella utilizzando l&#39;icona della lampadina in alto a destra.</li></ul> |
| ![Icona Menu](assets/menu.png){style="border:1px solid gray"} | **[!UICONTROL Menu]**<br/>Disponibile in un progetto di analisi guidata | Comandi in alto a destra del progetto di analisi guidata che forniscono azioni globali per l’analisi.<ul><li>![Icona Dati](/help/assets/icons/Data.svg) ***Nome della visualizzazione dati***: per modificare la visualizzazione dati utilizzata dall’analisi. Quando modifichi la visualizzazione dati, cambiano anche i componenti disponibili nella barra delle query.</li><li>![Icona Collegamento](/help/assets/icons/Link.svg) **Copia collegamento**: copia negli Appunti un collegamento all’analisi. Ti verrà richiesto di salvare prima della condivisione.</li><li>**Condividi**: apre la finestra modale di condivisione, con ulteriori opzioni per la condivisione a singoli utenti o gruppi. Puoi condividere un’analisi con altri utenti o generare un collegamento da condividere con chiunque.</li><li>**Salva**: salva l’analisi. Se stai salvando una nuova analisi, viene visualizzata la finestra di dialogo **[!UICONTROL Save analysis]** che richiede un nome e una descrizione. Una volta salvata, una finestra di dialogo **[!UICONTROL Analysis saved]** consente di condividere l’analisi.</li><li>![Icona Aggiungi a Workspace](/help/assets/icons/MultipleAdd.svg) **[!UICONTROL Add to Workspace]**: mostra i progetti disponibili in Workspace a cui puoi aggiungere questa analisi. Quando selezioni un progetto Workspace, questo viene aperto in una nuova scheda e nella parte inferiore del progetto viene aggiunta l’analisi.</li></ul>Seleziona l’![icona Altro](/help/assets/icons/More.svg) per altre azioni, ad esempio:<ul><li>**[!UICONTROL Save as]**: salva l’analisi separatamente da quella corrente, creando una copia. Viene visualizzata una finestra di dialogo che richiede un nuovo nome e una nuova descrizione.</li><li>**[!UICONTROL Export to Workspace]**: ricrea la query dell’analisi guidata corrente in Analysis Workspace. Il progetto Workspace viene creato in una nuova scheda, evitando interruzioni durante l’analisi guidata. È una copia dell’analisi e non rimane sincronizzata con l’analisi guidata originale una volta aperta. Utilizza questo comando per trasmetterla al team di analisti o per approfondire i dati oltre ai limiti consentiti dall’analisi.</li><li>**[!UICONTROL Copy chart to clipboard]**: copia l’elemento grafico negli Appunti per incollarlo in altre applicazioni. La barra delle query e la tabella non sono incluse nel grafico.</li><li>**[!UICONTROL Download PNG]**: scarica l’elemento grafico come `.png`. La barra delle query e la tabella non sono incluse nel grafico.</li><li>**[!UICONTROL Download CSV]**: scarica i dati della tabella come `.csv`. La barra delle query e il grafico non sono inclusi nel file.</li></ul> |
| ![Visualizzazione menu](assets/menu-visualization.png){style="border:1px solid gray"} | **Menu**<br/> Disponibile in una visualizzazione di analisi guidata in Analysis Workspace. | Comandi in una visualizzazione di analisi guidata in Analysis Workspace.<ul><li>![GraphScatter](/help/assets/icons/GraphScatter.svg) **[!UICONTROL Chart]**: per visualizzare solo il grafico dell’analisi.</li><li>![Tabella](/help/assets/icons/Table.svg) **[!UICONTROL Table]**: per visualizzare solo la tabella dell’analisi.</li><li>![TabellaEGrafico](/help/assets/icons/TableAndChart.svg) **[!UICONTROL All]**: per visualizzare il grafico e la tabella dell’analisi.</li><li>![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**: per modificare la configurazione dell’analisi</li><li>![Calendario](/help/assets/icons/Calendar.svg) **[!UICONTROL *Intervallo date *]**: per configurare l’intervallo di date per l’analisi.</li></ul> |


## Provisioning

Le analisi guidate sono incluse nei pacchetti di Customer Journey Analytics nel modo seguente:

| Pacchetto | Analisi disponibili |
| --- | --- |
| [!UICONTROL Customer Journey Analytics add-ons] | Crescita attiva, tendenze di conversione, frequenza, funnel, crescita netta, conservazione, tendenze |
| [!UICONTROL Customer Journey Analytics Foundation] | Tendenze |
| [!UICONTROL Customer Journey Analytics Select] | Visualizzazioni Foundation + crescita attiva, tendenze di conversione, frequenza, funnel, crescita netta, conservazione |
| [!UICONTROL Customer Journey Analytics Prime] | Seleziona visualizzazioni + Coinvolgimento, Impatto primo utilizzo, Impatto rilascio, Timeline |
| [!UICONTROL Customer Journey Analytics Ultimate] | Visualizzazioni Prime |

{style="table-layout:auto"}

Gli amministratori dei profili di prodotto possono aggiungere o rimuovere l’accesso all’analisi guidata in Adobe Admin Console.

1. Accedi ad [Adobe Admin Console](https://adminconsole.adobe.com).
1. Seleziona **[!UICONTROL Customer Journey Analytics]** nell’elenco dei prodotti.
1. Seleziona il profilo di prodotto desiderato per le autorizzazioni da modificare.
1. Seleziona la scheda **[!UICONTROL Permissions]**, quindi fai clic su **[!UICONTROL Edit]** in [!UICONTROL Reporting Tools].
1. Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg)  accanto a **[!UICONTROL Guided Analysis Access]** nell’elenco di [!UICONTROL Available Permission Items], che lo aggiunge all’elenco degli [!UICONTROL Included Permission Items].
1. Seleziona **[!UICONTROL Save]**.

Per ulteriori informazioni, consulta [Accesso a livello utente](/help/technotes/access-control.md#user-level-access).

>[!TIP]
>
>Alcuni amministratori preferiscono abilitare l’analisi guidata e disabilitare Analysis Workspace per i nuovi utenti di Customer Journey Analytics. Una volta che questi utenti avranno una maggiore conoscenza del prodotto e dei tuoi dati organizzativi, potrai abilitare l’accesso ad Analysis Workspace.
