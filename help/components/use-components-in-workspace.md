---
description: Scopri come utilizzare i componenti di un progetto in Analysis Workspace
title: Utilizzare I Componenti In Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 97%

---

# Utilizzare componenti in un progetto

I componenti costituiscono i dati effettivi di ogni progetto in Analysis Workspace. I componenti sono costituiti da dimensioni, metriche, segmenti e intervalli di date. Puoi aggiungere componenti a un progetto trascinandoli nelle visualizzazioni o nei pannelli.

Per informazioni sui tipi di componenti che è possibile aggiungere, consulta [Panoramica dei componenti](/help/components/overview.md).

>[!TIP]
>
>Per informazioni su ciascun componente, utilizza ![InfoOutline](/help/assets/icons/InfoOutline.svg). Per ulteriori informazioni, consulta [Informazioni sui componenti](#component-info).

## Aggiungere componenti a un progetto

1. [Creare un progetto in Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md).

1. [Aggiungi un pannello](/help/analysis-workspace/c-panels/panels.md#create-a-panel) o [aggiungi una visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) al progetto in Analysis Workspace. Se aggiungi un componente a un progetto vuoto, viene già creata una visualizzazione con tabella a forma libera.

1. Seleziona ![Cura](/help/assets/icons/Curate.svg) **[!UICONTROL Components]** dal pannello dei pulsanti. Tutti i componenti disponibili sono visualizzati nel pannello a sinistra. Per ulteriori dettagli, consulta [Interfaccia](/help/analysis-workspace/home.md#interface).

1. Scorri fino al componente che desideri aggiungere oppure cercalo, quindi trascinalo su un pannello o su una visualizzazione all’interno del progetto.

1. Facoltativamente, puoi trascinare un componente nella zona di rilascio nell’intestazione di un pannello. Questo trascinamento definisce il componente come un segmento e lo applica a tutto il contenuto all’interno del pannello.
Per informazioni su come utilizzare la zona di rilascio dei segmenti in un pannello al fine di segmentarlo, consulta [Zona di rilascio](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Panoramica dei pannelli](/help/analysis-workspace/c-panels/panels.md).

1. Per informazioni dettagliate, consulta le sezioni seguenti:

   * [Aggiungere dimensioni a un progetto](#add-dimensions-to-a-project)

   * [Aggiungere metriche a un progetto](#add-metrics-to-a-project)

   * [Aggiungere segmenti a un progetto](#add-segments-to-a-project)

   * [Aggiungere intervalli di date a un progetto](#add-date-ranges-to-a-project)

### Aggiungere dimensioni a un progetto

Le [dimensioni](/help/components/dimensions/overview.md) sono delle variabili in Customer Journey Analytics che in genere contengono valori stringa. Al contrario, le [metriche](/help/components/calc-metrics/calc-metr-overview.md) contengono valori numerici che si legano a una dimensione. Un rapporto di base mostra righe di valori stringa (dimensioni) rispetto a una colonna di valori numerici (metriche).

1. Inizia aggiungendo una dimensione al progetto in Analysis Workspace, come descritto in [Aggiungere componenti in un progetto](#add-components-to-a-project).

1. Scegli uno dei metodi seguenti per aggiungere dimensioni e determinare il tipo di dati che desideri analizzare:

   ![Aggiungere una dimensione](/help/components/assets/add-dimension.gif)

   * Trascina una dimensione in una visualizzazione (ad esempio una tabella a forma libera) in Analysis Workspace.

   * Dal pannello a sinistra, trascina una o più dimensioni nella zona di rilascio dei segmenti per creare un segmento rapido, come descritto in [Aggiungere segmenti a un progetto](#add-filters-to-a-project).

1. Facoltativamente, puoi suddividere dimensioni ed elementi dimensionali in Analysis Workspace con altri componenti. Per ulteriori informazioni, consulta [Suddividere dimensioni in Workspace](/help/components/dimensions/t-breakdown-fa.md).

Per ulteriori informazioni sull’utilizzo delle dimensioni in Analysis Workspace, consulta [Anteprima delle dimensioni](/help/components/dimensions/view-dimensions.md), [Suddividere le dimensioni](/help/components/dimensions/t-breakdown-fa.md) e [Dimensioni suddivise in base al tempo](/help/components/dimensions/time-parting-dimensions.md).

### Aggiungere metriche a un progetto

Le metriche consentono di quantificare i punti di dati in Analysis Workspace. Sono solitamente utilizzate come colonne in una visualizzazione e associate alle dimensioni.

Per aggiungere una metrica a un progetto in Analysis Workspace:

1. Inizia aggiungendo una metrica al progetto in Analysis Workspace, come descritto in [Aggiungere componenti a un progetto](#add-components-to-a-project).



1. Per aggiungere una metrica in Analysis Workspace, scegli uno dei seguenti metodi:

   ![Aggiunta di una metrica](/help/components/assets/add-metric.gif)

   * Per visualizzare la tendenza di una metrica nel periodo di date del progetto, trascinala nella zona di rilascio delle metriche in una tabella a forma libera vuota.

   * Per visualizzare una metrica per ciascun elemento di dimensione, trascinala quando è presente una dimensione.

   * Per sostituire una metrica esistente, trascina una metrica sopra l’intestazione della metrica da sostituire.

   * Per aggiungerne una nuova, trascinala vicino al lato destro o sinistro dell’intestazione di una metrica esistente.

   * Per creare una sovrapposizione di metrica, trascina una metrica sopra o sotto l’intestazione di una metrica esistente.


Per ulteriori informazioni sulle metriche, consulta la sezione [Metriche](/help/components/apply-create-metrics.md).

### Aggiungere segmenti a un progetto

I [segmenti](/help/components/segments/seg-overview.md) ti consentono di identificare sottoinsiemi di persone, sessioni o eventi in base a caratteristiche o interazioni specifiche.

Puoi utilizzare i segmenti in Analysis Workspace in uno dei seguenti modi:

* Aggiungere segmenti a un pannello
Quando aggiungi segmenti a un pannello, questi vengono applicati a tutto il contenuto al suo interno.
Per informazioni su come utilizzare la zona di rilascio dei segmenti in un pannello per segmentare il pannello, consulta [Zona di rilascio](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Panoramica dei pannelli](/help/analysis-workspace/c-panels/panels.md).

* Aggiungere segmenti a una visualizzazione
Quando aggiungi segmenti a una colonna in una tabella a forma libera, i segmenti si applicano a tutto il contenuto della colonna. Puoi anche aggiungere segmenti come parte di una visualizzazione del fallout.

* Utilizzare i segmenti nei componenti
Quando definisci componenti come [metriche calcolate](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md), [annotazioni](/help/components/annotations/create-annotations.md#annotation-builder) o anche [segmenti](/help/components/segments/seg-builder.md) puoi utilizzare i segmenti come parte della definizione.


### Aggiungere intervalli di date a un progetto

Gli [intervalli di date](/help/components/date-ranges/overview.md) determinano l’intervallo temporale del reporting in Analysis Workspace e possono essere applicati a uno o più pannelli all’interno di un progetto e anche ad alcune visualizzazioni (come la tabella a forma libera).

Per impostazione predefinita, ogni pannello include un intervallo di date. Esistono diversi modi per aggiornare un intervallo di date per un pannello. Un modo per aggiornare l’intervallo di date di un pannello in Analysis Workspace consiste nel trascinare un componente intervallo di date dal pannello a sinistra:

1. Facoltativamente, aggiungi un intervallo di date al progetto in Analysis Workspace, come descritto in [Aggiungere componenti al progetto](#add-components-to-a-project).

1. Trascina un intervallo di date dal pannello a sinistra su:

   * l’intervallo di date corrente, per modificare quello del pannello.

     ![Rilasciare un intervallo di date](assets/add-date-range.gif)

   * Una metrica o dimensione in una visualizzazione Tabella a forma libera. Per ulteriori informazioni, consulta [Utilizzare intervalli di date](/help/components/date-ranges/overview.md#use-date-ranges).

Per ulteriori informazioni su come utilizzare e gestire gli intervalli di date in Analysis Workspace, consulta [Panoramica sugli intervalli di date](/help/components/date-ranges/overview.md).

## Informazioni componente

Puoi passare il puntatore su qualunque componente per visualizzare ![Ulteriori informazioni](/help/assets/icons/InfoOutline.svg). Se questa opzione è selezionata, le informazioni aggiuntive sul componente vengono visualizzate in un pop-up.

![Informazioni componente](assets/component-info.png)

In base al controllo degli accessi, puoi:

* Accedere alla definizione ![Segnalibro](/help/assets/icons/Bookmark.svg) [!UICONTROL Data dictionary] per il componente.
* Accedere al generatore di componenti ![Modifica](/help/assets/icons/Edit.svg) o alla visualizzazione dati in cui è definito il componente.
