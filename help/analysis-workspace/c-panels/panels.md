---
description: I pannelli sono raccolte di tabelle e visualizzazioni.
title: Panoramica dei pannelli
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '2000'
ht-degree: 34%

---

# Panoramica dei pannelli

Un [!UICONTROL panel] è una raccolta di tabelle e visualizzazioni. Puoi accedere ai pannelli dall’icona in alto a sinistra in Workspace o da un [pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md). I pannelli sono utili per organizzare i progetti in base a specifici periodi di tempo, viste dati o casi di utilizzo di analisi.

## Tipi di pannello

In Analysis Workspace sono disponibili i seguenti tipi di pannello per [!UICONTROL Customer Journey Analytics]:

| Nome pannello | Descrizione |
| --- | --- |
| [Pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md) | Per iniziare a eseguire analisi, scegli tra i pannelli e le visualizzazioni disponibili. |
| [Attribuzione](attribution.md) | Confronta e visualizza rapidamente più modelli di attribuzione utilizzando qualsiasi dimensione e metrica di conversione. |
| [Sperimentazione](experimentation.md) | Confronta diverse esperienze utente, varianti di marketing o messaggistica per determinare quale sia meglio per determinare un risultato specifico. |
| [Forma libera](freeform-panel.md) | Esegui confronti illimitati e raggruppamenti, quindi aggiungi visualizzazioni per raccontare una storia ricca di dati. |
| [Pubblico medio per minuto](average-minute-audience-panel.md) | Analizza il pubblico medio per minuto di un contenuto specifico o in un periodo di tempo personalizzato. |
| [Visualizzatori simultanei contenuti multimediali](media-concurrent-viewers.md) | Analizza i visualizzatori simultanei nel tempo, con dettagli sui picchi di concorrenza e con la possibilità di suddividerli e confrontarli. |
| [Tempo di riproduzione trascorso](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | Analizza il tempo di riproduzione per capire dove si verificano picchi di convalute o abbandoni. |
| [Elemento successivo o precedente](next-previous.md) | Mostra le pagine successive o precedenti a cui si accede. |
| [Informazioni rapide](quickinsight.md) | Crea rapidamente una tabella a forma libera e una relativa visualizzazione per analizzare e individuare più rapidamente le informazioni. |


I pannelli [!UICONTROL Quick insights], [!UICONTROL Blank] e [!UICONTROL Freeform] sono ideali per iniziare con le attività di analisi, mentre [!UICONTROL Attribution] si presta ad analisi più avanzate. Nella parte inferiore dell&#39;area di lavoro è disponibile un ![AddCircle](/help/assets/icons/AddCircle.svg), che consente di aggiungere pannelli vuoti in qualsiasi momento.

Il pannello iniziale predefinito è [!UICONTROL Freeform], ma puoi impostare [pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md) o [Quick insights](/help/analysis-workspace/c-panels/quickinsight.md) come pannello predefinito. Consulta [Progetti e preferenze analisi](/help/analysis-workspace/user-preferences.md#projects--analyses-preferences).


## Creare un pannello

Per creare un pannello:

* Trascina un pannello dal pannello sinistro **[!UICONTROL Panels]** nell&#39;area di lavoro.
* Seleziona un pannello dal [pannello vuoto](blank-panel.md).
* Utilizza il menu **[!UICONTROL Insert]** in Workspace e seleziona il tuo pannello. In alternativa, è possibile utilizzare una delle [scelte rapide](../build-workspace-project/fa-shortcut-keys.md) per inserire un pannello.

  ![Crea un pannello](assets/create-panel.png)

È possibile:

* Seleziona ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) **entro** qualsiasi pannello per aggiungere un&#39;altra visualizzazione. Viene visualizzata una finestra a comparsa che consente di selezionare una visualizzazione.

  ![Popup con visualizzazioni possibili](assets/blank-panel.png)

  | Seleziona... | Per creare un... |
  |---|---|
  | ![Tabella](/help/assets/icons/Table.svg) | [Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) |
  | ![Linee](/help/assets/icons/GraphTrend.svg) | [Linee](/help/analysis-workspace/visualizations/line.md) |
  | ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barre](/help/analysis-workspace/visualizations/bar.md) |
  | ![123](/help/assets/icons/123.svg) | [Numero di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Testo](/help/assets/icons/Text.svg) | [Testo](/help/analysis-workspace/visualizations/text.md) |
  | ![FunnelConversione](/help/assets/icons/ConversionFunnel.svg) | [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) |
  | ![Flusso di lavoro](/help/assets/icons/GraphPathing.svg) | [Flusso](/help/analysis-workspace/visualizations/c-flow/flow.md) |
  | ![AreaGraficaSovrapposta](/help/assets/icons/GraphAreaStacked.svg) | [Superfici sovrapposte](/help/analysis-workspace/visualizations/area.md) |
  | ![NumeroTesto](/help/assets/icons/TextNumbered.svg) | [Tabella coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md) |
  | ![BulletGrafico](/help/assets/icons/GraphBullet.svg) | [Punto elenco](/help/analysis-workspace/visualizations/bullet-graph.md) |
  | ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [Anello](/help/analysis-workspace/visualizations/donut.md) |
  | ![SpostaSuGiù](/help/assets/icons/MoveUpDown.svg) | [Variazione di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Istogramma](/help/assets/icons/Histogram.svg) | [Istogramma](/help/analysis-workspace/visualizations/histogram.md) |
  | ![Dispersione grafico](/help/assets/icons/GraphScatter.svg) | [A dispersione](/help/analysis-workspace/visualizations/scatterplot.md) |
  | ![Tipo](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) |
  | ![GraphTree](/help/assets/icons/GraphTree.svg) | [Mappa ad albero](/help/analysis-workspace/visualizations/treemap.md) |

* Seleziona ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) **all&#39;esterno** dell&#39;ultimo pannello nell&#39;area di lavoro per aggiungere un altro [pannello vuoto](blank-panel.md).


## Visualizzazione dati

Ogni pannello è associato a una [visualizzazione dati](/help/data-views/data-views.md), identificata da ![Dati](/help/assets/icons/Data.svg) **[!UICONTROL *nome della visualizzazione dati *]**nel menu a discesa in alto a destra del pannello.

Quando crei un progetto Workspace vuoto, la visualizzazione dati predefinita per il pannello iniziale è l’ultima visualizzazione dati su cui hai lavorato in Customer Journey Analytics.

Quando crei un nuovo pannello, la visualizzazione dati predefinita si basa sulla visualizzazione dati dell’ultimo pannello su cui hai lavorato nel progetto Workspace.

>[!IMPORTANT]
>
>La visualizzazione dati selezionata determina le dimensioni, le metriche e i filtri disponibili per la creazione di visualizzazioni in un pannello.
>
>
>Quando passi da una visualizzazione dati a un pannello, alcuni componenti potrebbero non essere disponibili nella nuova visualizzazione dati. Questa modifica può impedire il corretto rendering della visualizzazione. Potresti visualizzare avvisi come:
>
>* Questo pannello contiene componenti non attivati nella visualizzazione dati selezionata. Modifica la visualizzazione dati o abilita i componenti richiesti nella visualizzazione dati.
>* Impossibile eseguire il rendering della visualizzazione: controlla le colonne e le righe per assicurarti che contengano componenti validi.
>

## Calendario

Il calendario del pannello controlla l’intervallo di date del reporting per tabelle e visualizzazioni all’interno di un pannello.

>[!NOTE]
>
>Se un componente ![Calendario](/help/assets/icons/Calendar.svg) intervallo di date viene utilizzato all&#39;interno di una visualizzazione o di un pannello (ad esempio, come filtro), il componente intervallo di date sostituisce il calendario del pannello.
>


![Finestra del calendario che mostra l’intervallo di date selezionato.](assets/panel-calendar.png)

1. Seleziona un intervallo di date selezionando prima la data di inizio e quindi la data di fine.
In alternativa, è possibile selezionare **[!UICONTROL Preset]** dal menu a discesa [!UICONTROL *Seleziona un predefinito*].

1. Facoltativamente, selezionare **[!UICONTROL Show advanced settings]** per:

   * Specificare **[!UICONTROL Start time]** e **[!UICONTROL End time]** diversi da `12:00 AM` (`0:00`) e `11:59 PM` (`23:59`) predefiniti. Gli orari di fine includono sempre 59 secondi. Per un intervallo di date che si estende su più giorni, l’ora di inizio si applica al primo giorno dell’intervallo di date e l’ora di fine si applica all’ultimo giorno dell’intervallo di date. Utilizzare **[!UICONTROL (Reset time values)]** per ripristinare le impostazioni predefinite dell&#39;ora di inizio e di fine.
   * **[!UICONTROL Make date range components relative to panel calendar]** (Autenticazione): Se disattivato, i componenti dell’intervallo di date utilizzati nel pannello sono relativi all’ora corrente. Se questa opzione è abilitata, i componenti dell’intervallo di date utilizzati nel pannello sono relativi al calendario del pannello.
   * **[!UICONTROL Use rolling dates]** (Autenticazione): Se abilitati, gli intervalli di date predefiniti come **[!UICONTROL Last 7 full days]** vengono aggiornati in modo dinamico in base all&#39;avanzamento della data e dell&#39;ora corrente. Se disattivate, tali predefiniti non vengono aggiornati una volta applicati.

     ![Date di rotazione](assets/calendar-rolling.png)

     È possibile selezionare il testo tra parentesi (ad esempio **[!UICONTROL fixed start - rolling daily]**) per estendere il pannello e specificare i dettagli per **[!UICONTROL Start]** e **[!UICONTROL End]**.

      1. Selezionare **[!UICONTROL Start of]**, **[!UICONTROL End of]** o **[!UICONTROL Fixed day]**.
      1. Dopo aver selezionato **[!UICONTROL Start of]** o **[!UICONTROL End of]**, è possibile creare un&#39;espressione completa. Ad esempio: **[!UICONTROL End of]** **[!UICONTROL current year]** **[!UICONTROL plus]** `1` **[!UICONTROL day]**. Selezionare il valore appropriato per ogni singola parte dell&#39;espressione.
         * Seleziona un valore per corrente. Ad esempio **[!UICONTROL current year]**.
         * Selezionare un valore per il calcolo aggiuntivo. Esempio: **[!UICONTROL plus]**.
         * Dopo aver specificato un calcolo aggiuntivo, specificare un valore. Ad esempio `1`.
         * Dopo aver specificato il calcolo aggiuntivo, selezionare il periodo di tempo da utilizzare per il calcolo. Ad esempio **[!UICONTROL day]**.

     Selezionare **[!UICONTROL Hide details]** per nascondere i dettagli del calcolo delle date di rotazione.

1. Selezionare **[!UICONTROL Apply]** per applicare l&#39;intervallo di date al pannello da cui è stato richiamato il calendario.
Seleziona **[!UICONTROL Apply to all panels]** per applicare l&#39;intervallo di date a tutti i pannelli nel progetto Workspace.


## Zona di rilascio {#dropzone}

La zona di rilascio del pannello consente di applicare filtri e filtri a discesa a tutte le tabelle e visualizzazioni di un pannello. Puoi applicare uno o più filtri a un pannello.

### Filtri

Per iniziare a filtrare il pannello, trascina i filtri dal pannello di sinistra fino alla zona di rilascio del pannello. Ripeti questa procedura per aggiungere altri filtri al pannello. I filtri vengono visualizzati uno accanto all’altro nella parte superiore del pannello.

![Il pannello a sinistra mostra le metriche disponibili e la metrica del cliente mobile trascinata nella zona di rilascio del pannello.](assets/segment-filter.png)

#### Filtri rapidi

Puoi anche trascinare componenti diversi da filtri direttamente nella zona di rilascio per creare filtri rapidi, risparmiando tempo e fatica quando accedi al [Generatore di filtri](/help/components/filters/filter-builder.md). I filtri creati in questo modo vengono automaticamente definiti come filtri a livello di evento. È possibile modificare rapidamente questa definizione selezionando ![Modifica](/help/assets/icons/Edit.svg) accanto al nome del filtro.


Per ulteriori informazioni, consulta [Filtri rapidi](/help/components/filters/quick-filters.md)

![Filtri ad hoc resi pubblici e rilasciati nella zona di rilascio.](assets/adhoc-segment-filter.png)

### Filtri a discesa

+++ Visualizza un video che illustra i filtri a discesa.

>[!VIDEO](https://video.tv.adobe.com/v/23877?format=jpeg)

{{videoaa}}

+++

#### Filtri a discesa statici

I filtri a discesa statici consentono di interagire con i dati in modo controllato. Ad esempio, puoi aggiungere un filtro a discesa per i tipi di dispositivi mobili, in modo da filtrare il pannello per tablet, telefono cellulare o desktop.

I filtri a discesa statici possono essere utilizzati anche per consolidare più progetti in un unico progetto. Ad esempio, se hai creato più versioni dello stesso progetto, assegnando a ciascuna un filtro Paese diverso, puoi consolidarle tutte in un unico progetto e aggiungere un filtro a discesa Paese.

![Filtri a discesa statici che mostrano il filtro del canale di mercato “Diretto” evidenziato. ](assets/dropdown-filter-intro.png)

##### Creare filtri a discesa statici

* Per i filtri a discesa che utilizzano elementi dimensionali, seleziona una singola dimensione dal pannello di sinistra e rilasciala nella zona di rilascio del pannello mantenendo ⇧ (*shift*). Questa azione crea un filtro a discesa con tutti gli elementi dimensionali associati a quella dimensione.

  Oppure, se desideri che il filtro a discesa includa solo elementi dimensionali specifici associati a una dimensione, seleziona l’icona a forma di freccia destra accanto alla dimensione desiderata nel pannello a sinistra. Questa azione espone tutti gli elementi dimensionali disponibili. Seleziona più elementi dimensionali da questo elenco utilizzando ⇧+![Seleziona](/help/assets/icons/Select.svg) (*turno* + *seleziona*) o ^+![Seleziona](/help/assets/icons/Select.svg) (*controllo* + *seleziona*), quindi rilasciali nella zona di rilascio del pannello **mantenendo** ⇧.

* Per i filtri a discesa che utilizzano un singolo tipo di componente (ad esempio, solo dimensioni, solo filtri o solo metriche), seleziona più elementi dello stesso tipo nel pannello a sinistra utilizzando ⇧+![Seleziona](/help/assets/icons/Select.svg) o ^+![Seleziona](/help/assets/icons/Select.svg). Quindi rilascia gli elementi nella zona di rilascio del pannello **tenendo premuto** ⇧.

  Viene creato un filtro a discesa singolo con i componenti selezionati.

* Per i filtri a discesa che utilizzano una combinazione di tipi di componenti (ad esempio 2 metriche e 3 filtri), seleziona più componenti utilizzando ⇧+![Seleziona](/help/assets/icons/Select.svg) o ^+![Seleziona](/help/assets/icons/Select.svg). Rilascia la selezione nella zona di rilascio del pannello **mentre tieni premuto** ⇧. In questo contesto, tutti i tipi di componenti vengono trattati come filtri a discesa separati. Ad esempio, se nella selezione includi sia metriche che elementi dimensionali, vengono creati due filtri a discesa separati: uno include gli elementi dimensionali e l’altro include le metriche.

Un filtro a discesa fornisce le seguenti opzioni del menu di scelta rapida:

* **[!UICONTROL Delete drop-down]**: rimuove il filtro a discesa dal pannello.
* **[!UICONTROL Delete label]**: rimuovere il testo visualizzato sopra un filtro a discesa. Per modificare l&#39;etichetta, passa il puntatore sull&#39;etichetta e seleziona ![Modifica etichetta del filtro a discesa](/help/assets/icons/Edit.svg).
* **[!UICONTROL Add label]**: quando aggiungi un filtro a discesa a un progetto, un’etichetta viene impostata automaticamente sul nome del componente. Se elimini l’etichetta, puoi aggiungerla nuovamente con questa opzione.
* **[!UICONTROL Require selection]**: richiede che nel pannello sia impostato un filtro.

##### Utilizzare filtri a discesa statici

Gli utenti possono utilizzare il menu a discesa dei filtri in uno dei seguenti modi per filtrare il pannello:

* Applica un singolo filtro al pannello selezionandolo dal filtro a discesa.

* Applica più filtri al pannello selezionandoli dal filtro a discesa. Il pannello viene filtrato per includere qualsiasi filtro selezionato.


#### Creare filtri a discesa dinamici

I filtri a discesa dinamici consentono di determinare i valori disponibili in base ai dati all’interno dell’intervallo di reporting del pannello e ai valori in altri filtri a discesa. Ad esempio, puoi creare due elenchi a discesa dinamici utilizzando una dimensione Paesi e una dimensione Città. Quando si seleziona un paese dall&#39;elenco a discesa **[!UICONTROL Countries]**, l&#39;elenco a discesa **[!UICONTROL Cities]** viene modificato in modo dinamico in modo da visualizzare solo le città del paese.

Lo stesso concetto si applica a tutte le dimensioni: sono visibili solo gli elementi dimensionali che compaiono nell’intervallo di date del pannello e i filtri selezionati. Gli elementi dimensionali selezionati nei filtri a discesa statici influiscono sui valori disponibili nei filtri a discesa dinamici. Tuttavia, ciò non vale per il contrario: gli elementi dimensionali selezionati nei filtri a discesa dinamici non influiscono sui valori disponibili nei filtri a discesa statici.

La selezione manuale degli elementi dimensionali è disponibile se prevedi che un certo elemento dimensionale verrà raccolto in futuro. È inoltre possibile cancellare un filtro a discesa dinamico in modo che non contenga un valore, consentendo ad altri filtri a discesa dinamici di contenere più valori. Seleziona **[!UICONTROL Reset all]** per cancellare la selezione da tutti i filtri a discesa per quel pannello.

Per creare un filtro a discesa dinamico:

* Trascina e rilascia una singola dimensione nella zona di rilascio del pannello **tenendo premuto** ⇧.

I filtri a discesa dinamici non sono disponibili per metriche, filtri o intervalli di date.

Un filtro a discesa dinamico fornisce le stesse opzioni del menu di scelta rapida dei filtri a discesa statici.


## Menu di scelta rapida

Ulteriori funzionalità per un pannello sono disponibili tramite un menu di scelta rapida (clic con il pulsante destro del mouse) nell’intestazione del pannello.

![Opzioni disponibili dal menu di scelta rapida per l’intestazione di un pannello.](assets/right-click-menu.png)

Sono disponibili le seguenti opzioni:

| Opzione | Descrizione |
| --- | --- |
| **[!UICONTROL Insert copied panel]** | Consentono di incollare un pannello copiato in un’altra posizione all’interno del progetto o in un progetto diverso. |
| **[!UICONTROL Insert copied visualization]** | Incolla una visualizzazione copiata in un’altra posizione all’interno del pannello, del progetto o di un altro progetto. |
| **[!UICONTROL Apply Data view to all panels]** | Applica la visualizzazione dati per questo pannello a tutti gli altri pannelli del progetto. |
| **[!UICONTROL Copy panel]** | Copiare un pannello in modo da poterlo inserire in un’altra posizione all’interno del progetto o in un progetto diverso. |
| **[!UICONTROL Duplicate panel]** | Crea un duplicato esatto del pannello corrente, che potrai quindi modificare. |
| **[!UICONTROL Collapse all panels]** | Comprimi tutti i pannelli del progetto. |
| **[!UICONTROL Expand all panels]** | Espandi tutti i pannelli del progetto. |
| **[!UICONTROL Collapse all visualizations in panel]** | Comprimi tutte le visualizzazioni nel pannello corrente. |
| **[!UICONTROL Expand all visualizations in panel]** | Espandi tutte le visualizzazioni nel pannello corrente. |
| **[!UICONTROL Edit Description]** | Aggiungi (o modifica) un testo descrittivo per il pannello. |
| **[!UICONTROL Get Panel Link]** | Indirizza un utente a un pannello specifico all’interno di un progetto. Quando il collegamento è selezionato, il destinatario deve effettuare l’accesso prima di essere indirizzato al pannello a cui è collegato. |

## Configurazione

Alcuni pannelli (come [!UICONTROL Attribution], [!UICONTROL Experimentation], [!UICONTROL Media average minute audience] e altri) dispongono di una finestra di dialogo per la configurazione che ti aiuta a creare la visualizzazione. Utilizza ![Modifica](/help/assets/icons/Edit.svg) nella parte superiore del pannello per accedere e modificare la configurazione.

![Configurare un pannello](/help/analysis-workspace/c-panels/assets/configure-panel.png)
