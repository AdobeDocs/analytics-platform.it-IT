---
title: Includere più dimensioni in una tabella a forma libera
description: Scopri come includere più dimensioni in una tabella a forma libera
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: bff352181392c19b6c4fe70893a016179fb77f06
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 2%

---

# Includere più dimensioni in una tabella a forma libera

{{release-limited-testing}}

Puoi includere fino a 5 colonne di dimensione in una tabella a forma libera, consentendoti di visualizzare più elementi dimensionali uno accanto all’altro. Ogni riga di elementi dimensionali agisce come un singolo elemento concatenato.

Puoi ordinare le colonne di dimensione (insieme alle colonne di metrica) per un’analisi più completa e personalizzata.

## Colonne e raggruppamenti di più dimensioni

Analysis Workspace fornisce i seguenti modi per aggiungere più dimensioni all’interno di una tabella a forma libera:

* Includi più colonne di dimensione (come descritto in questo articolo)

* [Aggiungere suddivisioni](/help/components/dimensions/t-breakdown-fa.md)

Entrambi questi metodi consentono di analizzare le quote rispetto ad altre quote. Tuttavia, esistono differenze importanti ed entrambi i metodi possono essere utilizzati nella stessa tabella per un’analisi ancora più approfondita.

Più colonne di dimensione consentono di:

* Correlare le righe di dati tra più dimensioni e metriche.

* Mostra i dati solo quando si applica a ogni colonna della dimensione nella tabella. A tale scopo, utilizzare il filtro colonne per deselezionare l&#39;impostazione **[!UICONTROL Include "No value"]** in ogni colonna dimensione.

  Per ulteriori informazioni, vedere [Filtrare e ordinare le tabelle](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

* Ordinare i dati per più colonne di dimensioni e metriche.

  Per ulteriori informazioni, vedere [Filtrare e ordinare le tabelle](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

I raggruppamenti consentono di:

* Mostra elementi dimensionali per un solo elemento

* Mostra gli elementi dimensionali principali per un singolo

## Aggiungere colonne di dimensione

Puoi aggiungere colonne di dimensione una alla volta o in blocco.

1. In Analysis Workspace, crea una tabella a forma libera.

   Per ulteriori informazioni, consulta [Aggiungere visualizzazioni a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) in [Panoramica delle visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Aggiungere dimensioni alla tabella a forma libera. È possibile aggiungere dimensioni una alla volta oppure più dimensioni contemporaneamente.

   * Trascina le dimensioni una alla volta nella tabella a forma libera. Posizionate colonne di quota aggiuntive a sinistra o a destra delle colonne di quota esistenti nella tabella. Una riga **[!UICONTROL Add]** verticale blu mostra dove verrà creata la nuova colonna.

     ![Trascina singole dimensioni](assets/dimensions-add-individually.png)

   * Selezionate fino a 5 dimensioni nel menu del componente e trascinatele nella tabella a forma libera. Le dimensioni vengono aggiunte alla tabella da sinistra a destra nell&#39;ordine in cui vengono selezionate.

     Per selezionare più dimensioni, tenere premuto il tasto ***Comando*** (in Mac) o il tasto ***Ctrl*** (in Windows).

     ![Trascina più dimensioni](assets/dimensions-add-multiple.png)

## Filtrare le tabelle

Per informazioni sul filtraggio delle tabelle, vedere [Filtrare le tabelle](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#filter-tables) in [Filtrare e ordinare le tabelle](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Ordinare le tabelle {#sort-tables}

<!--At GA, move this section into the "Filter and sort tables" article and replace the current "Sort tables" section. Change the "Filter tables" section above to "Filter and sort tables" and link to the other article. Also add row to Guardrails article. -->

Puoi ordinare i dati di una tabella a forma libera in base a qualsiasi colonna in Analysis Workspace che sia una dimensione o una metrica.

Per impostazione predefinita, le dimensioni sono ordinate in ordine crescente e le metriche in ordine decrescente.

### Ordinare le tabelle in base a una singola colonna

Quando si ordinano i dati per una singola colonna come descritto in questa sezione, qualsiasi [ordinamento avanzato](#sort-tables-by-multiple-columns-advanced-sorting) applicato alla tabella viene rimosso.

Per ordinare i dati nelle tabelle in base a una singola colonna:

1. Passa il puntatore del mouse sull&#39;intestazione della colonna che desideri ordinare, quindi seleziona l&#39;icona **Ordina** ![Ordina](/help/assets/icons/SortOrderDown.svg) quando viene visualizzata.

   ![Menu a discesa Ordina](assets/sort-dropdown-menu.png)

1. Seleziona **[!UICONTROL Ascending]** (Mostra origine dati) o **[!UICONTROL Descending]** (Blocca selezione).

   L’icona di ordinamento rimane visibile quando l’ordinamento viene applicato alla colonna. Una freccia indica l&#39;ordinamento dei dati (![Ordinamento](/help/assets/icons/SortOrderUp.svg) per crescente o ![Ordinamento](/help/assets/icons/SortOrderDown.svg) per decrescente).

### Ordinare le tabelle in base a più colonne (ordinamento avanzato)

{{release-limited-testing-section}}

#### Applica ordinamento a più colonne

Per ordinare i dati nelle tabelle in base a più colonne:

1. Passa il puntatore del mouse sull&#39;intestazione di una colonna che desideri ordinare, quindi seleziona l&#39;icona **Ordina** ![Ordina](/help/assets/icons/SortOrderDown.svg) quando viene visualizzata.

   ![Menu a discesa Ordina](assets/sort-dropdown-menu.png)

1. Seleziona **[!UICONTROL Advanced sorting]**.

   ![Finestra di dialogo Ordinamento avanzato](assets/sort-advanced-dialog.png)

1. Nella finestra di dialogo Ordinamento avanzato, eseguire una delle operazioni seguenti:

   * Aggiungere le colonne che non sono ancora ordinate selezionando il pulsante **[!UICONTROL Add sort column]**.

   * Rimuovere le colonne che non si desidera più ordinare selezionando l&#39;icona **Rimuovi** ![Rimuovi](/help/assets/icons/Close.svg).

   * Trascina le colonne più in alto o più in basso nell’elenco per regolare la priorità di ordinamento.

     Per ulteriori informazioni, vedere [Priorità ordinamento](#sort-priority).

   * Modificare il valore di ordinamento selezionando **[!UICONTROL Ascending]** o **[!UICONTROL Descending]** nel menu a discesa.

   * Seleziona una colonna diversa selezionando il menu a discesa nome colonna.

1. Seleziona **[!UICONTROL Apply]**.

L’icona di ordinamento rimane visibile quando l’ordinamento viene applicato a una colonna. Una freccia indica l&#39;ordinamento dei dati (![Ordinamento](/help/assets/icons/SortOrderUp.svg) per crescente o ![Ordinamento](/help/assets/icons/SortOrderDown.svg) per decrescente).

![esempio di ordinamento multiplo](assets/dimensions-multiple-sort.png)

#### Priorità di ordinamento

Quando si ordinano dati per più colonne, i dati vengono ordinati in base alla priorità assegnata a ciascuna colonna. La numerazione delle priorità viene visualizzata accanto all&#39;icona di ordinamento ![icona priorità ordinamento](assets/sort-priority-icon.png).

La colonna con priorità primaria determina l&#39;ordine principale, la colonna con priorità secondaria determina l&#39;ordine quando le righe hanno lo stesso valore nella colonna principale, la colonna con priorità terziaria determina l&#39;ordine quando le righe hanno lo stesso valore nelle colonne principale e secondaria e così via.

Consideriamo ad esempio una tabella con le seguenti colonne:

* Giorno del mese (dimensione)

* Ora del giorno (dimensione)

* Eventi (metrica)

È possibile assegnare una priorità di ordinamento a ciascuna colonna nel modo seguente:

| Nome colonna (componente) | Tipo di componente | Priorità di ordinamento |
|---------|----------|---------|
| Giorno del mese | Dimensione | 1 |
| Ora del giorno | Dimensione | 2 |
| Eventi | Metrica | 3 |

Assegnando una priorità di ordinamento a ciascuna colonna, è possibile controllare esattamente la modalità di visualizzazione dei dati nella tabella. In questo esempio, le informazioni vengono ordinate prima per Giorno del mese, quindi per Ora del giorno e infine per Eventi.

![esempio di ordinamento multiplo](assets/dimensions-multiple-sort.png)

## Aggiungere suddivisioni a una tabella con più colonne di dimensione

Quando aggiungi un raggruppamento a una tabella con più colonne di dimensione, il raggruppamento si estende su tutti gli elementi dimensionali della riga in cui viene aggiunto.

È possibile aggiungere un raggruppamento come descritto in [Suddividere dimensioni](/help/components/dimensions/t-breakdown-fa.md).

## Dimensioni non supportate {#unsupported}

Le seguenti combinazioni di dimensioni non sono supportate e Analysis Workspace ne impedisce l’aggiunta o visualizza un messaggio di errore dopo l’aggiunta:

* Più dimensioni provenienti da campi che fanno riferimento a [array di oggetti](/help/use-cases/object-arrays.md) diversi utilizzati insieme nella stessa tabella a forma libera.

  Più dimensioni sono consentite insieme nella stessa tabella a forma libera se fanno riferimento allo stesso array di oggetti.