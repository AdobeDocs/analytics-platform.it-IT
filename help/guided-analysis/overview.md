---
title: Panoramica dell’analisi guidata
description: Un metodo di analisi dei dati in Customer Journey Analytics che consente ai team di prodotto di ottenere rapidamente informazioni di alta qualità.
keywords: Product Analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 1e7d61f05a8351a1bd9e4d289c9d31906676f909
workflow-type: tm+mt
source-wordcount: '1692'
ht-degree: 34%

---

# Panoramica dell’analisi guidata

L’analisi guidata consente agli utenti, dal marketing ai prodotti agli analisti, di gestire in autonomia dati e informazioni di alta qualità sul percorso del cliente tramite flussi di lavoro guidati, basati sui dati multicanale del Customer Journey Analytics. Analogamente alle scorecard per Analysis Workspace e dispositivi mobili, l’analisi guidata utilizza dati provenienti da una [Visualizzazione dati](/help/data-views/data-views.md), che fa riferimento ai dati in Adobe Experience Platform tramite un [Connessione](../connections/overview.md). Molti rapporti creati nell’analisi guidata possono essere trasferiti facilmente in Analysis Workspace per ulteriori ricerche.

Sono disponibili le seguenti analisi guidate:

| Icona | Analisi | Descrizione |
| :----:|--- | --- |
| ![GruppoPersone](/help/assets/icons/PeopleGroup.svg) | [Crescita attiva](types/active-growth.md) | Identifica gli utenti nuovi, mantenuti, che ritornano o inattivi. |
| ![ConversionTrens](/help/assets/icons/ConversionTrends.svg) | [Tendenze di conversione](types/conversion-trends.md) | Tieni traccia delle modifiche nei tassi di conversione nel tempo. |
| ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) | [Coinvolgimento](types/engagement.md) | Comprendi l’ampiezza e la profondità del coinvolgimento delle funzioni. |
| ![Primo utilizzo](/help/assets/icons/FirstUse.svg) | [Impatto primo utilizzo](types/first-use-impact.md) | Misura l’impatto del primo utilizzo delle funzioni sugli indicatori chiave. |
| ![Istogramma](/help/assets/icons/Histogram.svg) | [Frequenza](types/frequency.md) | Misura il coinvolgimento in base alla frequenza d’uso. |
| ![FunnelConversione](/help/assets/icons/ConversionFunnel.svg) | [Funnel](types/funnel.md) | Confronta i tassi di conversione tra passaggi. |
| ![Crescita netta](/help/assets/icons/NetGrowth.svg) | [Crescita netta](types/net-growth.md) | Stai guadagnando o perdendo utenti? |
| ![Versione](/help/assets/icons/Release.svg) | [Impatto sulla versione](types/release-impact.md) | Confronta le prestazioni in periodi uguali prima e dopo il rilascio. |
| ![Mantenimento](/help/assets/icons/Retention.svg) | [Mantenimento](types/retention.md) | Misura le abitudini attuali riguardo il ritorno degli utenti. |
| ![Timeline](/help/assets/icons/Timeline.svg) | [Timeline](types/timeline.md) | Esplora i pattern nell’attività della sessione. |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Tendenze](types/trends.md) | Misura il coinvolgimento utenti nel tempo. |



## Accesso

Puoi accedere all’analisi guidata dalla home page del Customer Journey Analytics.

1. Selezionare **[!UICONTROL Guided analysis]** dalla home page, per passare direttamente all&#39;analisi delle tendenze [](types/trends.md).

   ![Riquadro della pagina di destinazione](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Selezionare **[!UICONTROL Create new]** per visualizzare le diverse opzioni di visualizzazione e scegliere un punto di partenza diverso per l&#39;analisi.

   ![Creare un nuovo modale](assets/create-new-modal.png){style="border:1px solid gray"}

Puoi accedere all’analisi guidata anche dall’interno di un progetto Analysis Workspace.

1. Selezionare **[!UICONTROL Blank project]** dalla home page per creare un progetto Workspace vuoto.

   ![Crea progetto vuoto](assets/blank-project.png){style="border:1px solid gray"}

1. Seleziona ![Analisi guidata](/help/assets/icons/GuidedAnalysis.svg) **[!UICONTROL Guided Analysis]** nella barra a sinistra.

   ![Barra a sinistra di Workspace](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. Trascinare una nuova analisi nell&#39;area di lavoro di Workspace, quindi selezionare **[!UICONTROL Create]** per generare l&#39;analisi desiderata, ad esempio **[!UICONTROL Create Trends]**. È inoltre possibile trascinare un&#39;analisi esistente nell&#39;area di lavoro di Workspace dalla sezione **[!UICONTROL Saved]**.

   ![Crea pannello](assets/create-guided-analysis-panel.gif)

## Interfaccia

L&#39;interfaccia per l&#39;analisi guidata segue il formato di domanda e risposta. Crea una domanda nella barra delle query, quindi ottieni una risposta con un approfondimento scritto, un grafico e una tabella. Puoi quindi porre la domanda successiva con le impostazioni di analisi e visualizzazione.

L’analisi guidata utilizza i seguenti elementi dell’interfaccia utente:

| Anteprima interfaccia | Elemento nell’interfaccia utente | Descrizione |
| --- | --- | --- |
| ![Barra delle query](assets/query-rail.png){style="border:1px solid gray"} | **[!UICONTROL Query rail]** | Configura la *domanda* selezionando i componenti desiderati (eventi, proprietà e segmenti) che compongono un&#39;analisi. Le seguenti opzioni sono disponibili per tutte le analisi, con impostazioni aggiuntive disponibili in base alla singola visualizzazione. <ul><li>**Visualizzazione**: selezionare una delle opzioni per passare a una nuova analisi. Le selezioni delle query vengono mantenute entro i limiti consentiti per la nuova analisi.</li><li>**Eventi**: gli eventi che desideri misurare. Ogni analisi applica limiti diversi al numero di eventi che è possibile configurare.  Gli eventi a volte sono etichettati come **[!UICONTROL Start and return events]**, **[!UICONTROL Steps]** o **[!UICONTROL Key indicators]**. Gli eventi sono identificati nell&#39;analisi utilizzando 1, 2, ...<br/>Seleziona ![Aggiungi](/help/assets/icons/Add.svg) **[!UICONTROL Add an event]** per aggiungere nuovi eventi.</li><li>**[!UICONTROL Factors]**: se disponibile, consente di specificare fattori quali data da e primo evento.</li><li>**Conteggiato come**: metodo di conteggio da applicare agli eventi selezionati. Seleziona dal menu a discesa.</li><li>**Segmenti**: i segmenti che desideri misurare. Ogni analisi applica limiti diversi al numero di segmenti che puoi configurare. I segmenti sono identificati nell&#39;analisi utilizzando A, B, ...<br/>Seleziona ![Aggiungi](/help/assets/icons/Add.svg) **[!UICONTROL Add a segment]** per aggiungere nuovi segmenti.</li><li>**[!UICONTROL Breakdown]**: se disponibile, il raggruppamento da applicare all&#39;analisi.</li></ul>In alcune impostazioni sono disponibili configurazioni aggiuntive.<ul><li>**Filtri**: utilizza ![Filtro](assets/filter.png) per limitare gli eventi o i segmenti in base a dimensioni specifiche. Quando è selezionata una dimensione, sono disponibili sia i criteri di filtro standard (ad esempio **[!UICONTROL Equals]**, **[!UICONTROL Contains]** o **[!UICONTROL Ends with]**) che i primi 1000 valori di dimensione.<br/>Selezionare ![Filtro](/help/assets/icons/Filter.svg) per aggiungere altri filtri.<br/>Selezionare ![Rimuovi](/help/assets/icons/Remove.svg) per rimuovere un filtro.</li><li>**Altre azioni**: utilizza ![Altre](/help/assets/icons/More.svg) per selezionare azioni, come<ul><li>![Rinomina](/help/assets/icons/Rename.svg) **[!UICONTROL Rename]**: per rinominare un evento o un segmento.</li><li>![Duplicato](/help/assets/icons/Duplicate.svg) **[!UICONTROL Duplicate]**: per duplicare un evento o un segmento.</li><li>![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Remove]**: per rimuovere un evento, segmento o raggruppamento.</li><li>![Modifica segmento](/help/assets/icons/Edit.svg) **[!UICONTROL Edit segment]**: per modificare un segmento nel [Generatore di filtri](/help/components/filters/filter-builder.md).</li><li>![Stella](/help/assets/icons/Star.svg) **[!UICONTROL Add to favorites]**: per aggiungere il segmento all&#39;elenco dei filtri preferiti nel [Gestore filtri](/help/components/filters/manage-filters.md).</li><li>![SaveAsFloppy](/help/assets/icons/SaveAsFloppy.svg) **[!UICONTROL Save as]**: per salvare il segmento come nuovo componente. Nella finestra di dialogo **[!UICONTROL Save segments to components]**, puoi specificare un nome di segmento e una descrizione. È possibile selezionare ![StarOutline](/help/assets/icons/StarOutline.svg) per contrassegnare il nuovo segmento come preferito. Selezionare **[!UICONTROL Save]** per salvare il segmento come nuovo filtro.</li><li>![Collegamento](/help/assets/icons/Link.svg) **[!UICONTROL Link start and return events]**.: per collegare eventi di inizio e ritorno in un&#39;analisi [Mantenimento](types/retention.md).</li><li>![Scollega](/help/assets/icons/Unlink.svg) **[!UICONTROL Unlink start and return events]**: per scollegare gli eventi di inizio e di ritorno in un&#39;analisi [Mantenimento](types/retention.md).</li></ul></li></ul> |
| ![Grafico](assets/chart.png){style="border:1px solid gray"} | **[!UICONTROL Chart]** | Una visualizzazione dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. La visualizzazione che vedi dipende dalla vista e dalle impostazioni sopra il grafico. Il grafico include anche: <ul><li>**Descrizioni**: passa il puntatore del mouse su un punto dati del grafico per visualizzare una descrizione comando con ulteriori informazioni.</li><li>**Legenda**: passa il puntatore del mouse sulla serie di legende del grafico per visualizzare le definizioni, se disponibili, per concentrarti su tale serie e nasconderne temporaneamente altre. Selezionate una serie nella legenda per nasconderla.</li><li>**Annotazioni**: le [annotazioni](../components/annotations/overview.md) applicabili sono visibili tra la visualizzazione e la legenda. Vengono visualizzate come ![icona Annotazione](assets/annotation.png) nel colore configurato dell’annotazione. Le analisi che mostrano i dati nel tempo posizionano l&#39;icona ![Annotation](assets/annotation.png) sotto la data o l&#39;intervallo di date configurato. Le analisi che non mostrano dati nel tempo mostrano l&#39;icona ![Annotation](assets/annotation.png) nell&#39;angolo inferiore destro del grafico.</li><li>**Seleziona azioni**: espone le successive azioni disponibili selezionando qualsiasi punto dati. Le opzioni includono **Salva segmento**.</li></ul> |
| ![Tabella](assets/table.png){style="border:1px solid gray"} | **[!UICONTROL Table]** | Una rappresentazione in tabella dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. Righe della tabella che utilizzano come riferimento l’evento (1, 2, ...) e gli identificatori del segmento (A, B, ...). Le colonne della tabella dipendono dall’analisi eseguita sopra il grafico. La tabella include anche per ogni riga: <ul><li>**Seleziona azioni**: attiva ![Mostra icona nascondi](assets/hide-in-chart.png) per nascondere o esporre una serie di grafici per una riga. Seleziona ![Altro](/help/assets/icons/More.svg) per ulteriori azioni. Le opzioni includono **Salva segmento**.</li></ul> |
| ![Impostazioni di visualizzazione](assets/visualization-settings.png){style="border:1px solid gray"} | **[!UICONTROL Visualization settings]** | Opzioni sopra il grafico che consentono di porre la domanda successiva e personalizzare la modalità di restituzione dei dati del grafico e della tabella. Le seguenti opzioni sono disponibili per tutte le analisi, con impostazioni aggiuntive disponibili per singole analisi. <ul><li>![GraphTrend](/help/assets/icons/GraphTrend.svg) **Impostazioni grafico**: ottimizzare la visualizzazione del grafico e della tabella. Le opzioni disponibili dipendono dall’analisi selezionata.</li><li>![Livello](/help/assets/icons/Layer.svg) **Impostazioni sovrapposizione**: aggiungi una sovrapposizione. Le opzioni disponibili dipendono dall’analisi selezionata.</li><li>![Bucket](/help/assets/icons/Bucket.svg) **[!UICONTROL Bucket settings]**: impostazione bucket automatico o applicazione di bucket personalizzati ai dati. Le opzioni disponibili dipendono dall’analisi selezionata.<li>![DataCorrelated](/help/assets/icons/DataCorrelated.svg) **[!UICONTROL Compare settings]**: confronta i dati con un intervallo di date specifico. Le opzioni disponibili dipendono dall’analisi selezionata.</li><li>![Passaggi](/help/assets/icons/Footsteps.svg) **[!UICONTROL Display settings]**: selezionare come visualizzare i dati. Le opzioni disponibili dipendono dall’analisi selezionata.<li>![Calendario](/help/assets/icons/Calendar.svg) **Intervallo date**: selettore di calendari che consente di determinare l&#39;intervallo di date dell&#39;analisi. Puoi anche selezionare un intervallo per le analisi con tendenze, ad esempio giornaliere, settimanali o mensili.</li><li>![LightBulb](/help/assets/icons/LightBulb.svg) **Approfondimenti**: approfondimenti contestuali a seconda dell&#39;analisi visualizzata. Queste informazioni approfondite forniscono osservazioni per l’analisi corrente. Se sono disponibili più informazioni, puoi visualizzarle utilizzando le frecce a destra. È possibile attivare o disattivare la visibilità di questa casella utilizzando l&#39;icona della lampadina in alto a destra.</li></ul> |
| ![Menu](assets/menu.png){style="border:1px solid gray"} | **[!UICONTROL Menu]**<br/>Disponibile in un progetto di analisi guidata | Comandi in alto a destra di un progetto di analisi guidata che forniscono azioni generali per l’analisi.<ul><li>![Dati](/help/assets/icons/Data.svg) ***nome della visualizzazione dati***: modificare la visualizzazione dati utilizzata dall&#39;analisi. Quando modifichi la visualizzazione dati, cambiano anche i componenti disponibili nella barra delle query.</li><li>![Collegamento](/help/assets/icons/Link.svg) **Copia collegamento**: copia un collegamento all&#39;analisi negli Appunti. Ti verrà richiesto di salvare prima della condivisione.</li><li>**Condividi**: apre la finestra modale di condivisione, con ulteriori opzioni per la condivisione a singoli utenti o gruppi. Puoi condividere un’analisi con altri utenti o generare un collegamento da condividere con chiunque.</li><li>**Salva**: salva l’analisi. Se si salva una nuova analisi, viene visualizzata la finestra di dialogo **[!UICONTROL Save analysis]** che richiede un nome e una descrizione. Una volta salvata, una finestra di dialogo **[!UICONTROL Analysis saved]** ti consente di condividere l&#39;analisi.</li></ul>Seleziona ![Altro](/help/assets/icons/More.svg) per altre azioni, ad esempio:<ul><li>**Salva con nome**: salva l’analisi separatamente da quella corrente, creando una copia. Viene visualizzata una finestra di dialogo che richiede un nuovo nome e una nuova descrizione.</li><li>**Esporta in Workspace**: ricrea la query di analisi guidata corrente in Analysis Workspace. Il progetto Workspace viene creato in una nuova scheda, evitando interruzioni durante l’analisi guidata. È una copia dell&#39;analisi e non rimane sincronizzata con l&#39;analisi originale una volta aperta. Utilizza questo comando per passare al team di analisti o per approfondire i dati rispetto a quanto consente l’analisi.</li><li>**Copia grafico negli Appunti**: copia l&#39;elemento grafico negli Appunti per incollarlo in altre applicazioni. La barra delle query e la tabella non sono incluse nel grafico.</li><li>**Scarica PNG**: scarica l’elemento grafico come `.png`. La barra delle query e la tabella non sono incluse nel grafico.</li><li>**Scarica CSV**: scarica i dati della tabella come `.csv`. La barra delle query e il grafico non sono inclusi nel file.</li></ul> |
| ![Visualizzazione menu](assets/menu-visualization.png){style="border:1px solid gray"} | **Menu**<br/> Disponibile in una visualizzazione di analisi guidata in Analysis Workspace. | Comandi in una visualizzazione di analisi guidata in Analysis Workspace.<ul><li>![GraphScatter](/help/assets/icons/GraphScatter.svg) **[!UICONTROL Chart]**: per visualizzare solo il grafico dell&#39;analisi.</li><li>![Tabella](/help/assets/icons/Table.svg) **[!UICONTROL Table]**: per visualizzare solo la tabella dell&#39;analisi.</li><li>![TabellaEGrafico](/help/assets/icons/TableAndChart.svg) **[!UICONTROL All]**: per visualizzare il grafico e la tabella dell&#39;analisi.</li><li>![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**: per modificare la configurazione dell&#39;analisi</li><li>![Calendario](/help/assets/icons/Calendar.svg) **[!UICONTROL *Intervallo date *]**: per configurare l&#39;intervallo di date per l&#39;analisi.</li></ul> |


## Provisioning

Le analisi guidate sono incluse nei pacchetti di Customer Journey Analytics nel modo seguente:

| Pacchetto | Analisi disponibili |
| --- | --- |
| [!UICONTROL Customer Journey Analytics add-ons] | Crescita attiva, Tendenze di conversione, Frequenza, Funnel, Crescita netta, Mantenimento, Tendenze |
| [!UICONTROL Customer Journey Analytics Foundation] | Tendenze |
| [!UICONTROL Customer Journey Analytics Select] | Viste di base + Crescita attiva, Tendenze di conversione, Frequenza, Funnel, Crescita netta, Mantenimento |
| [!UICONTROL Customer Journey Analytics Prime] | Seleziona viste + Coinvolgimento, Impatto primo utilizzo, Impatto rilascio, Timeline |
| [!UICONTROL Customer Journey Analytics Ultimate] | Visualizzazioni Prime |

{style="table-layout:auto"}

Gli amministratori dei profili di prodotto possono aggiungere o rimuovere l’accesso all’analisi guidata in Adobe Admin Console.

1. Accedi ad [Adobe Admin Console](https://adminconsole.adobe.com).
1. Seleziona **[!UICONTROL Customer Journey Analytics]** nell’elenco dei prodotti.
1. Seleziona il profilo di prodotto desiderato per le autorizzazioni da modificare.
1. Selezionare la scheda **[!UICONTROL Permissions]**, quindi fare clic su **[!UICONTROL Edit]** in [!UICONTROL Reporting Tools].
1. Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) accanto a **[!UICONTROL Guided Analysis Access]** nell&#39;elenco di [!UICONTROL Available Permission Items], che lo aggiunge all&#39;elenco di [!UICONTROL Included Permission Items].
1. Seleziona **[!UICONTROL Save]**.

Per ulteriori informazioni, consulta [Accesso a livello utente](/help/technotes/access-control.md#user-level-access).

>[!TIP]
>
>Alcuni amministratori preferiscono abilitare l’analisi guidata e disabilitare Analysis Workspace per i nuovi utenti di Customer Journey Analytics. Una volta che questi utenti avranno una maggiore conoscenza del prodotto e dei tuoi dati organizzativi, potrai abilitare l’accesso ad Analysis Workspace.
