---
title: Panoramica delle tabelle a forma libera
description: Scopri come utilizzare le tabelle a forma libera, che sono la base per l’analisi dei dati in Analysis Workspace.
feature: Visualizations
exl-id: e5ba9089-c575-47b3-af85-b8b2179396ac
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 97%

---

# Panoramica della tabella a forma libera {#freeform-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="Tabella a forma libera"
>abstract="Crea una visualizzazione vuota delle tabelle a forma libera che puoi realizzare utilizzando dimensioni, segmenti, metriche e intervalli di date. Puoi utilizzare la tabella a forma libera come base per altre visualizzazioni."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo descrive la visualizzazione della tabella a forma libera in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Consulta [Tabella a forma libera](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]


In Analysis Workspace, la visualizzazione di una ![Table](/help/assets/icons/Table.svg) **[!UICONTROL Freeform table]** è la base per l’analisi dei dati interattivi. Puoi trascinare una combinazione di [componenti](/help/components/overview.md) nelle righe e nelle colonne per creare una tabella personalizzata per l’analisi. Man mano che ciascun componente viene rilasciato, la tabella viene aggiornata immediatamente e puoi subito analizzarla e approfondire i dati.

![Tabella a forma libera che mostra i componenti nelle righe e nelle colonne, inclusi le Visite e gli Ordini online per più pagine web.](assets/opening-section.png)

Per creare e configurare una [!UICONTROL Freeform table]:

* Aggiungi una visualizzazione ![Table](/help/assets/icons/Table.svg) **[!UICONTROL Freeform table]**. Consulta [Aggiungere una visualizzazione a un pannello](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

## Tabelle automatizzate

Il modo più rapido per creare una tabella consiste nel trascinare i componenti direttamente in un progetto o pannello vuoto o in una tabella a forma libera. Una tabella a forma libera viene creata per te in un formato consigliato. [Guarda il tutorial](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace).

![Un nuovo pannello con il componente Visite è stato rilasciato nell’area di lavoro.](assets/automated-table.png)

## Generatore di tabelle a forma libera

Se prima preferisci aggiungere diversi componenti alla tabella e quindi eseguire il rendering dei dati, puoi selezionare **[!UICONTROL Enable table builder]**. Con il generatore abilitato, puoi trascinare dimensioni, raggruppamenti, metriche e segmenti per creare tabelle che rispondano a domande più complesse. I dati vengono aggiornati dopo la selezione di **[!UICONTROL Build]**.

![Un generatore di tabelle a forma libera mostra ](assets/table-builder.png)

## Interazioni

Puoi interagire con una tabella a forma libera e personalizzarla in diversi modi:

### Filtrare e ordinare

* Puoi [segmentare e ordinare](filter-and-sort.md) i dati in una tabella.

### Righe

* Puoi rapidamente [creare una nuova visualizzazione](../freeform-analysis-visualizations.md#visualize) da una o più righe utilizzando ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg).
* È possibile inserire più righe in una singola schermata regolando la [densità di visualizzazione](/help/analysis-workspace/build-workspace-project/view-density.md) del progetto.
* Prima dell’impaginazione ogni riga delle dimensioni può visualizzare fino a 400 righe. Seleziona il numero accanto a **[!UICONTROL Rows]** nell’intestazione della prima colonna per visualizzare più righe in una pagina. Passa a una pagina diversa utilizzando ![ChevronRight](/help/assets/icons/ChevronRight.svg) nell’intestazione della prima colonna.
* Puoi suddividere le righe per componenti aggiuntivi. Per suddividere più righe alla volta, seleziona più righe e quindi trascina il componente successivo sopra le righe selezionate. Scopri di più sui [raggruppamenti](/help/components/dimensions/t-breakdown-fa.md).
* Le righe possono essere [segmentate](/help/components/segments/seg-overview.md) per visualizzare un set ridotto di elementi. Impostazioni aggiuntive sono disponibili in [Impostazioni riga](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md).

### Colonne

* I componenti possono essere impilati all’interno di colonne per creare metriche segmentate, analisi incrociate e altro ancora.
* La visualizzazione di ogni colonna può essere regolata nelle [impostazioni della colonna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).
* Sono disponibili diverse azioni tramite il [menu di scelta rapida](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu). A seconda dell’elemento selezionato (intestazione, righe o colonne della tabella), il menu fornisce azioni diverse.


## Impostazioni

Seleziona ![Setting](/help/assets/icons/Setting.svg) per visualizzare **[!UICONTROL Table settings]**. Sono disponibili le seguenti [impostazioni](../freeform-analysis-visualizations.md#settings) di visualizzazione specifiche:

### Origine dati

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Linked visualizations]**. | Elenca tutte le visualizzazioni collegate. |
| **[!UICONTROL Show data source]** | Se è deselezionata, la tabella a forma libera che funge da origine dati per la visualizzazione è nascosta in Workspace. |

### Impostazioni

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Align dates from each columns to all start on the same row]** | Per allineare o non allineare le date di ogni colonna affinché inizino tutte sulla stessa riga. |


## Menu di scelta rapida

Le seguenti opzioni del [menu di scelta rapida](../freeform-analysis-visualizations.md#context-menu) sono disponibili nell’intestazione della visualizzazione:

| Opzione | Descrizione |
| --- | --- |
| **[!UICONTROL Insert copied visualization]**n | Incolla (inserisci) una visualizzazione copiata altrove nello stesso progetto o in un altro progetto. |
| **[!UICONTROL Copy data to clipboard]** | Copia i dati dalla visualizzazione negli appunti. |
| **[!UICONTROL Copy selection to clipboard]** | Copia la selezione dalla visualizzazione negli appunti. |
| **[!UICONTROL Download items as CSV (*nome dimensione *)]** | Scarica immediatamente gli elementi dimensionali (fino a un massimo di 50.000) della visualizzazione sul dispositivo locale. Un massimo di 50.000 elementi dimensionali per la dimensione selezionata. |
| **[!UICONTROL Copy visualization]** | Copia la visualizzazione, in modo da poterla inserire in un’altra posizione all’interno del progetto o in un progetto diverso. |
| **[!UICONTROL Download data CSV]** | Scarica immediatamente i dati visualizzati della visualizzazione sul dispositivo locale. |
| **[!UICONTROL Export full table...]** | Esporta la tabella completa in posizioni cloud designate. Consulta [Esporta i rapporti di Customer Journey Analytics nel cloud](../../export/export-cloud.md) |
| **[!UICONTROL Duplicate visualization]** | Crea un duplicato esatto della visualizzazione. |
| **[!UICONTROL Edit description]** | Aggiungi (o modifica) una descrizione di testo per la visualizzazione. Consulta [Testo](../text.md). |
| **[!UICONTROL Get visualization link]** | Copia e condividi un collegamento direttamente alla visualizzazione. La finestra di dialogo Condividi collegamento consente di visualizzare il collegamento. Seleziona Copia per copiare il collegamento negli appunti. |
| **[!UICONTROL Start over]** | Elimina la configurazione della visualizzazione corrente in modo da poterla riconfigurare da zero. |


>[!MORELIKETHIS]
>
>[Aggiungere una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[Impostazioni di visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[Menu di scelta rapida della visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
