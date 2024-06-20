---
description: Scopri come aggiungere componenti a un progetto in Analysis Workspace
title: Utilizzare i componenti in Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 697503bba56f44159df7a2f6a0e60a0a4178266d
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 7%

---

# Utilizzare i componenti in Analysis Workspace

I componenti costituiscono i dati effettivi di qualsiasi progetto in Analysis Workspace. I componenti sono costituiti da dimensioni, metriche, filtri e intervalli di date. Puoi aggiungere componenti a un progetto trascinandoli in visualizzazioni o pannelli.

Per informazioni generali sui tipi di componenti che è possibile aggiungere, vedere [Panoramica dei componenti](/help/components/overview.md).

>[!TIP]
>
>Per informazioni su ciascun componente, seleziona l’icona Informazioni accanto al nome di un componente nella barra a sinistra di Analysis Workspace.

## Inizia ad aggiungere componenti a un progetto

1. [Creare un progetto in Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md) se non lo hai già fatto.

1. [Aggiungi un pannello](/help/analysis-workspace/c-panels/panels.md) o [aggiungere una visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) al progetto in Analysis Workspace.

   Se aggiungi un componente a un progetto vuoto, viene automaticamente creata una visualizzazione a forma libera.

1. Seleziona l’icona **[!UICONTROL Components]** nella barra a sinistra.

   ![](assets/build-components.png)

1. Scorri fino al componente da aggiungere oppure cercalo, quindi trascinalo su un pannello o su una visualizzazione all’interno del progetto.

1. (Facoltativo) Trascina un componente nella zona di rilascio del filtro nell’intestazione di un pannello.

   I filtri si applicano a tutto il contenuto del pannello.

   Per informazioni su come utilizzare la zona di rilascio dei filtri in un pannello per filtrare il pannello, consulta [Zona di rilascio](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Panoramica dei pannelli](/help/analysis-workspace/c-panels/panels.md).

   ![rilascia un filtro nella zona di rilascio](assets/filter-dropzone.png)

1. Per informazioni più dettagliate, continua con una delle sezioni seguenti, a seconda del tipo di componente che stai aggiungendo:

   * [Aggiungere dimensioni a un progetto](#add-dimensions-to-a-project)

   * [Aggiungere metriche a un progetto](#add-metrics-to-a-project)

   * [Aggiungere filtri a un progetto](#add-filters-to-a-project)

   * [Aggiungere intervalli di date a un progetto](#add-date-ranges-to-a-project)

## Aggiungere dimensioni a un progetto

[Dimension](/help/components/dimensions/overview.md) sono variabili in Adobe Analytics che in genere contengono valori stringa. Al contrario, le [metriche](/help/components/calc-metrics/calc-metr-overview.md) contengono valori numerici che si legano a una dimensione. Un rapporto di base mostra righe di valori stringa (dimensione) rispetto a una colonna di valori numerici (metrica).

1. Inizia ad aggiungere una dimensione al progetto in Analysis Workspace, come descritto in [Inizia ad aggiungere componenti a un progetto](#begin-adding-components-to-a-project).

1. Scegliere uno dei metodi seguenti per aggiungere dimensioni e determinare il tipo di dati da analizzare:

   * Trascina una dimensione in una visualizzazione (ad esempio una tabella a forma libera) in Analysis Workspace.

     ![Aggiungere dimensioni a un progetto](assets/add-dimensions.png)

   * Trascina una o più dimensioni dalla barra a sinistra alla zona di rilascio del filtro per creare un filtro ad hoc, come descritto in [Aggiungere filtri a un progetto](#add-filters-to-a-project).

1. (Facoltativo) Puoi suddividere dimensioni ed elementi dimensionali in Analysis Workspace con altri componenti.

   Per ulteriori informazioni, consulta [Suddividere dimensioni in Workspace](/help/components/dimensions/t-breakdown-fa.md).

Per ulteriori informazioni sull’utilizzo delle dimensioni in Analysis Workspace, consulta [Anteprima dimensioni](/help/components/dimensions/view-dimensions.md), [Suddividere dimensioni](/help/components/dimensions/t-breakdown-fa.md), e [Dimensioni suddivise in base al tempo](/help/components/dimensions/time-parting-dimensions.md).

## Aggiungere metriche a un progetto

Le metriche consentono di quantificare i punti dati in Analysis Workspace. Sono più comunemente utilizzate come colonne in una visualizzazione e legate alle dimensioni.

Per aggiungere una metrica a un progetto in Analysis Workspace:

1. Inizia ad aggiungere una metrica al progetto in Analysis Workspace, come descritto in [Inizia ad aggiungere componenti a un progetto](#begin-adding-components-to-a-project).

1. Per aggiungere una metrica in Analysis Workspace, scegli uno dei seguenti metodi:

   * Trascina una metrica nella zona di rilascio della metrica in una tabella a forma libera vuota per visualizzare la tendenza della metrica nel periodo di date del progetto.

     ![Aggiungere una metrica a un progetto](assets/add-metrics.png)

   * Trascina una metrica quando è presente una dimensione per visualizzarla rispetto a ciascun elemento dimensione.

   * Trascina una metrica sopra un’intestazione di metrica esistente per sostituirla.

   * Trascina una metrica accanto a un’intestazione per vedere entrambe le metriche una accanto all’altra.

Per ulteriori informazioni sulle metriche, consulta [Panoramica delle metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md).

## Aggiungere filtri a un progetto

[Filtri](/help/components/filters/filters-overview.md) consente di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni specifiche.

In Analysis Workspace puoi utilizzare i filtri in uno dei seguenti modi:

### Aggiungere filtri a un pannello

Quando aggiungi filtri a un pannello, i filtri si applicano a tutto il contenuto al suo interno.

Per informazioni su come utilizzare la zona di rilascio dei filtri in un pannello per filtrare il pannello, consulta [Zona di rilascio](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Panoramica dei pannelli](/help/analysis-workspace/c-panels/panels.md).

### Aggiungere filtri a una colonna di una tabella a forma libera

Quando si aggiungono filtri a una colonna di una tabella a forma libera, i filtri vengono applicati a tutto il contenuto della colonna della tabella.

### Utilizzare i filtri per creare metriche calcolate

Nel generatore di metriche calcolate, puoi applicare filtri all’interno della definizione della metrica.

Per ulteriori informazioni, consulta [Metriche filtrate](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md).

## Aggiungere intervalli di date a un progetto

[Intervalli di date](/help/components/date-ranges/custom-date-ranges.md) determina l’intervallo di tempo di reporting in Analysis Workspace e può essere applicato a uno o più pannelli all’interno di un progetto.

Per impostazione predefinita, ogni pannello include un intervallo di date. Esistono diversi modi per aggiornare un intervallo di date per un pannello. Un modo per aggiornare un intervallo di date per un pannello in Analysis Workspace consiste nel trascinare un componente intervallo di date dalla barra a sinistra:

1. Inizia ad aggiungere un intervallo di date al progetto in Analysis Workspace, come descritto in [Inizia ad aggiungere componenti a un progetto](#begin-adding-components-to-a-project).

1. Trascina un intervallo di date dalla barra a sinistra all’intervallo di date corrente nella parte superiore destra del pannello.

   ![rilascia un intervallo di date](assets/daterange-drop.png)

Per ulteriori informazioni sull’utilizzo di calendari e intervalli di date in Analysis Workspace, consulta [Panoramica del calendario e degli intervalli di date](/help/components/date-ranges/custom-date-ranges.md).
