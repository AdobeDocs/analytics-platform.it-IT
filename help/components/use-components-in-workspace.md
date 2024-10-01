---
description: Scopri come aggiungere componenti a un progetto in Analysis Workspace
title: Utilizzare i componenti in Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 3%

---

# Utilizzare i componenti in Analysis Workspace

I componenti costituiscono i dati effettivi di qualsiasi progetto in Analysis Workspace. I componenti sono costituiti da dimensioni, metriche, filtri e intervalli di date. Puoi aggiungere componenti a un progetto trascinandoli in visualizzazioni o pannelli.

Per ulteriori informazioni sui tipi di componenti che è possibile aggiungere, vedere [Panoramica dei componenti](/help/components/overview.md).

>[!TIP]
>
>Per informazioni su ciascun componente, seleziona l&#39;icona ![InfoOutline](/help/assets/icons/InfoOutline.svg) accanto al nome del componente.

## Aggiungere componenti a un progetto

1. [Crea un progetto in Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md).

1. [Aggiungi un pannello](/help/analysis-workspace/c-panels/panels.md#create-a-panel) o [aggiungi una visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) al progetto in Analysis Workspace. Se aggiungi un componente a un progetto vuoto, viene già creata una visualizzazione a forma libera della tabella.

1. Seleziona ![Cura](/help/assets/icons/Curate.svg) **[!UICONTROL Components]** dal pannello del pulsante. Tutti i componenti disponibili sono visualizzati nel pannello a sinistra. Per ulteriori dettagli, vedere [Interfaccia](/help/analysis-workspace/home.md#interface).

1. Scorri fino al componente da aggiungere o cerca il componente che desideri aggiungere, quindi trascinalo su un pannello o una visualizzazione all’interno del progetto.

1. Facoltativamente, puoi trascinare un componente nella zona di rilascio del filtro nell’intestazione di un pannello. Questo trascinamento definisce il componente come un filtro e applica il filtro a tutto il contenuto del pannello.
Per informazioni su come utilizzare la zona di rilascio dei filtri in un pannello per filtrare il pannello, vedi [Zona di rilascio](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Panoramica dei pannelli](/help/analysis-workspace/c-panels/panels.md).

1. Per informazioni più dettagliate, vedere le sezioni seguenti:

   * [Aggiungere dimensioni a un progetto](#add-dimensions-to-a-project)

   * [Aggiungere metriche a un progetto](#add-metrics-to-a-project)

   * [Aggiungere filtri a un progetto](#add-filters-to-a-project)

   * [Aggiungere intervalli di date a un progetto](#add-date-ranges-to-a-project)

### Aggiungere dimensioni a un progetto

[Dimension](/help/components/dimensions/overview.md) sono variabili in Customer Journey Analytics che in genere contengono valori stringa. Al contrario, le [metriche](/help/components/calc-metrics/calc-metr-overview.md) contengono valori numerici che si legano a una dimensione. Un rapporto di base mostra righe di valori stringa (dimensione) rispetto a una colonna di valori numerici (metrica).

1. Inizia ad aggiungere una dimensione al progetto in Analysis Workspace, come descritto in [Aggiungere componenti a un progetto](#add-components-to-a-project).

1. Scegliere uno dei metodi seguenti per aggiungere dimensioni e determinare il tipo di dati da analizzare:

   ![Aggiungi una dimensione](/help/components/assets/add-dimension.gif)

   * Trascina una dimensione in una visualizzazione (ad esempio una tabella a forma libera) in Analysis Workspace.

   * Trascina una o più dimensioni dal pannello di sinistra nella zona di rilascio del filtro per creare un filtro rapido, come descritto in [Aggiungere filtri a un progetto](#add-filters-to-a-project).

1. Facoltativamente, puoi suddividere dimensioni ed elementi dimensionali in Analysis Workspace con altri componenti. Per ulteriori informazioni, vedere [Suddividere dimensioni in Workspace](/help/components/dimensions/t-breakdown-fa.md).

Per ulteriori informazioni sull&#39;utilizzo delle dimensioni in Analysis Workspace, vedere [Anteprima dimensioni](/help/components/dimensions/view-dimensions.md), [Suddivisione dimensioni](/help/components/dimensions/t-breakdown-fa.md) e [Dimensioni suddivise in base al tempo](/help/components/dimensions/time-parting-dimensions.md).

### Aggiungere metriche a un progetto

Le metriche consentono di quantificare i punti dati in Analysis Workspace. Sono più comunemente utilizzate come colonne in una visualizzazione e legate alle dimensioni.

Per aggiungere una metrica a un progetto in Analysis Workspace:

1. Inizia ad aggiungere una metrica al progetto in Analysis Workspace, come descritto in [Aggiungere componenti a un progetto](#add-components-to-a-project).



1. Per aggiungere una metrica in Analysis Workspace, scegli uno dei seguenti metodi:

   ![Aggiunta di una metrica](/help/components/assets/add-metric.gif)

   * Trascina una metrica nella zona di rilascio della metrica in una tabella a forma libera vuota per visualizzare la tendenza della metrica nel periodo di date del progetto.

   * Trascina una metrica quando è presente una dimensione per visualizzarla per ogni elemento dimensione.

   * Trascina una metrica sopra un’intestazione di metrica esistente per sostituirla.

   * Trascina una metrica a sinistra o a destra di un’intestazione di metrica esistente per aggiungere la nuova metrica.

   * Trascina una metrica sopra o sotto l’intestazione di una metrica esistente per creare una sovrapposizione di metrica.


Per ulteriori informazioni sulle metriche, vedere [Metriche](/help/components/apply-create-metrics.md).

### Aggiungere filtri a un progetto

[I filtri](/help/components/filters/filters-overview.md) ti consentono di identificare sottoinsiemi di persone, sessioni o eventi in base a caratteristiche o interazioni specifiche.

In Analysis Workspace puoi utilizzare i filtri in uno dei seguenti modi:

* Aggiungere filtri a un pannello
Quando aggiungi filtri a un pannello, i filtri si applicano a tutto il contenuto al suo interno.
Per informazioni su come utilizzare la zona di rilascio dei filtri in un pannello per filtrare il pannello, vedi [Zona di rilascio](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Panoramica dei pannelli](/help/analysis-workspace/c-panels/panels.md).

* Aggiungere filtri a una visualizzazione
Quando si aggiungono filtri a una colonna di una tabella a forma libera, i filtri vengono applicati a tutto il contenuto della colonna della tabella. Puoi anche aggiungere filtri come parte di una visualizzazione di abbandono.

* Utilizzare i filtri nei componenti
Quando definisci componenti come [metriche calcolate](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md), [annotazioni](/help/components/annotations/create-annotations.md#annotation-builder) o anche [filtri](/help/components/filters/filter-builder.md) puoi utilizzare i filtri come parte della definizione.


### Aggiungere intervalli di date a un progetto

[Gli intervalli di date](/help/components/date-ranges/overview.md) determinano l&#39;intervallo di tempo di reporting in Analysis Workspace e possono essere applicati a uno o più pannelli all&#39;interno di un progetto e anche ad alcune visualizzazioni (come la tabella a forma libera).

Per impostazione predefinita, ogni pannello include un intervallo di date. Esistono diversi modi per aggiornare un intervallo di date per un pannello. Un modo per aggiornare un intervallo di date per un pannello in Analysis Workspace consiste nel trascinare un componente intervallo di date dal pannello a sinistra:

1. Facoltativamente, aggiungi un intervallo di date al progetto in Analysis Workspace, come descritto in [Aggiungi componenti a un progetto](#add-components-to-a-project).

1. Trascina e rilascia un intervallo di date dal pannello a sinistra in:

   * L’intervallo di date corrente, per modificare l’intervallo di date del pannello.

     ![Rilascia un intervallo di date](assets/add-date-range.gif)

   * Una metrica o dimensione in una visualizzazione a forma libera. Per ulteriori informazioni, vedere [Utilizzare intervalli di dati](/help/components/date-ranges/overview.md#use-date-ranges).

Per ulteriori informazioni su come utilizzare e gestire gli intervalli di date in Analysis Workspace, consulta [Panoramica sugli intervalli di date](/help/components/date-ranges/overview.md).

## Informazioni sul componente

Puoi passare il cursore sopra un componente per visualizzare ![Ulteriori informazioni](/help/assets/icons/InfoOutline.svg). Se questa opzione è selezionata, viene visualizzata una finestra a comparsa con informazioni aggiuntive sul componente.

![Informazioni sul componente](assets/component-info.png)

In base al controllo degli accessi, puoi:

* Accedi alla definizione ![Segnalibro](/help/assets/icons/Bookmark.svg) [!UICONTROL Data dictionary] per il componente.
* Accedi al generatore di componenti ![Modifica](/help/assets/icons/Edit.svg) o alla visualizzazione dati in cui è definito il componente.
