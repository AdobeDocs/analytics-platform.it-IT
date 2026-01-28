---
title: Includere più dimensioni in una tabella a forma libera
description: Scopri come includere più dimensioni in una tabella a forma libera
feature: Visualizations
role: User
source-git-commit: 696bd0db44949162307d8ce7d2debed351a76cd6
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 1%

---

# Includere più colonne di dimensione in una tabella a forma libera

{{release-limited-testing}}

Puoi includere fino a 5 colonne di dimensione in una tabella a forma libera, consentendoti di visualizzare più elementi dimensionali uno accanto all’altro. Ogni riga di elementi dimensionali si comporta come un singolo elemento dimensionale concatenato.

Puoi applicare filtri, ordinamento, raggruppamenti e altro ancora alle tabelle a forma libera con più colonne di dimensioni per creare un’analisi più approfondita e personalizzata.

## Elementi dimensionali concatenati

Quando [aggiungi più colonne di dimensione a una tabella a forma libera](#add-multiple-dimension-columns), ogni riga di elementi di dimensione si comporta come un singolo elemento di dimensione concatenato. Questa funzionalità consente di visualizzare i dati delle metriche per combinazioni specifiche di dimensioni.

Consideriamo ad esempio una tabella a forma libera in cui le colonne della dimensione sono _Città_, _Tipo di dispositivo_ e _Giorno del mese_ e la metrica è _Eventi_. I 3 elementi dimensionali nella prima riga della tabella diventano un singolo elemento dimensionale concatenato che mostra che il 30° giorno del mese si sono verificati a Mumbai 2.056 eventi da telefoni cellulari.

| Dimension: City | Dimension: tipo di dispositivo | Dimension: giorno del mese | Metrica: Eventi |
|---------|----------|---------|---------|
| Mumbai | Telefono cellulare | 30 | 2.056 |
| New York | Tablet | 31 | 1.761 |
| Bangalore | Desktop | 1 | 1.666 |
| Delhi | Telefono cellulare | 14 | 1.396 |

Di seguito è riportato l’aspetto di questa tabella in Analysis Workspace:

![Esempio con più dimensioni](assets/multi-dim-example.png)

## Aggiungere più colonne di dimensione

Puoi aggiungere più colonne di dimensione una alla volta o in blocco.

1. In Analysis Workspace, crea una tabella a forma libera.

   Per ulteriori informazioni, consulta [Aggiungere visualizzazioni a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) in [Panoramica delle visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Aggiungere dimensioni alla tabella a forma libera. È possibile aggiungere dimensioni una alla volta oppure più dimensioni contemporaneamente.

   * Trascina le dimensioni una alla volta nella tabella a forma libera. Posizionate colonne di quota aggiuntive a sinistra o a destra delle colonne di quota esistenti nella tabella. Una riga verticale blu **[!UICONTROL Aggiungi]** mostra dove verrà creata la nuova colonna.

     ![Trascina singole dimensioni](assets/dimensions-add-individually.png)

   * Selezionate fino a 5 dimensioni nel menu del componente e trascinatele nella tabella a forma libera. Le dimensioni vengono aggiunte alla tabella da sinistra a destra nell&#39;ordine in cui vengono selezionate.

     Per selezionare più dimensioni, tenere premuto il tasto ***Comando*** (in Mac) o il tasto ***Ctrl*** (in Windows).

     ![Trascina più dimensioni](assets/dimensions-add-multiple.png)

1. Visualizzare ogni riga della tabella come un singolo elemento dimensione. Per ulteriori informazioni, vedere [Elementi dimensione concatenati](#concatenated-dimension-items).

## Filtrare e ordinare tabelle

Puoi applicare filtri e ordinare alle colonne di una tabella a forma libera. Puoi ordinare i dati di una tabella a forma libera in base a qualsiasi colonna, che si tratti di dimensioni o metriche. È anche possibile ordinare in base a più colonne contemporaneamente.

Per informazioni, vedere [Filtrare e ordinare tabelle a forma libera](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Colonne e raggruppamenti di più dimensioni

Analysis Workspace fornisce i seguenti modi per aggiungere più dimensioni all’interno di una tabella a forma libera:

* Includi più colonne di dimensione (come descritto in questo articolo)

* [Aggiungere suddivisioni](/help/components/dimensions/t-breakdown-fa.md)

Entrambi questi metodi consentono di analizzare le quote rispetto ad altre quote. Tuttavia, esistono differenze importanti ed entrambi i metodi possono essere utilizzati nella stessa tabella per un’analisi ancora più approfondita.

### Differenze tra colonne di dimensione e raggruppamenti

Più colonne di dimensione consentono di:

* Concatenare elementi dimensionali in righe di dati distinte su più dimensioni.

* Includi elementi dimensionali nelle righe concatenate solo quando gli elementi dimensionali si applicano a ogni colonna della dimensione nella tabella. A questo scopo, utilizza il filtro colonne per deselezionare l&#39;impostazione **[!UICONTROL Includi &quot;Nessun valore&quot;]** in ogni colonna della dimensione.

  Per ulteriori informazioni, vedere [Ordinare le tabelle per più colonne (Ordinamento avanzato)](#sort-tables-by-multiple-columns-advanced-sorting).

* Ordina i dati per più colonne di dimensioni e metriche per visualizzare più dati personalizzati.

  Per ulteriori informazioni, vedere [Ordinare le tabelle per più colonne (Ordinamento avanzato)](#sort-tables-by-multiple-columns-advanced-sorting)

I raggruppamenti consentono di:

* Suddividere un elemento dimensione nella tabella a forma libera per una dimensione secondaria. Puoi visualizzare fino a 400 elementi dimensionali per la dimensione secondaria.

### Aggiungere suddivisioni a una tabella con più colonne di dimensione

Quando aggiungi un raggruppamento a una tabella con più colonne di dimensione, il raggruppamento si applica all’elemento dimensionale concatenato (in tutte le colonne di dimensione) nella riga in cui lo aggiungi.

![esempio di raggruppamento con più ordinamenti](assets/dimensions-multiple-sort-breakdown.png)

Inoltre, puoi aggiungere più colonne di dimensione all’interno di un raggruppamento. Anche ogni riga di elementi dimensionali all’interno del raggruppamento si comporta come un singolo elemento dimensionale concatenato.

<!-- Add a screenshot of a breakdown with multiple cllumns, then add this sentence: "For example, you can break down the first dimension item in this table by a new concatenated dimension item that shows..." -->

Per ulteriori informazioni su come aggiungere un raggruppamento, vedere [Suddividere dimensioni](/help/components/dimensions/t-breakdown-fa.md).

## Creare un segmento basato su un elemento dimensione che si estende su più colonne dimensione

Quando crei un segmento basato su un elemento dimensionale che si estende su più colonne di dimensione, ogni elemento dimensionale viene incluso nella definizione del segmento, con gli operatori And che li uniscono.

Per informazioni sulla creazione di un segmento, vedi [Creare segmenti](/help/components/segments/seg-create.md).

## Dimensioni non supportate {#unsupported}

Le seguenti combinazioni di dimensioni non sono supportate e Analysis Workspace ne impedisce l’aggiunta o visualizza un messaggio di errore dopo l’aggiunta:

* Più dimensioni provenienti da campi che fanno riferimento a [array di oggetti](/help/use-cases/object-arrays.md) diversi utilizzati insieme nella stessa tabella a forma libera.

  Più dimensioni sono consentite insieme nella stessa tabella a forma libera se fanno riferimento allo stesso array di oggetti.

