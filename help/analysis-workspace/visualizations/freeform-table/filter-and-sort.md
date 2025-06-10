---
description: Documentazione che descrive come filtrare e ordinare le tabelle in Analysis Workspace.
title: Filtrare e ordinare tabelle
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 99%

---

# Filtra e ordina tabelle a forma libera

Le tabelle a forma libera in Analysis Workspace sono la base dell’analisi interattiva dei dati. In quanto tali, possono contenere migliaia di righe di informazioni. Filtrare e ordinare i dati può essere fondamentale per far emergere in modo efficace le informazioni più importanti.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Filtrare le tabelle

I filtri in Analysis Workspace ti aiutano a far emergere le informazioni più importanti.

>[!NOTE]
>
> Solo gli elementi dimensionali dinamici possono essere filtrati come descritto in questa sezione, non gli elementi dimensionali statici. Per ulteriori informazioni, consulta [Elementi dimensionali dinamici e statici nelle tabelle a forma libera](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

Sono disponibili vari metodi per filtrare le righe da una tabella a forma libera.

- Escludere righe specifiche da una tabella
- Applicare filtri a una tabella
- Utilizzare segmenti di pubblico

Assicurati di leggere in che misura ogni metodo influisce sui [totali delle tabelle a forma libera](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### Escludere righe specifiche da una tabella

Puoi escludere rapidamente righe specifiche dalla tabella senza dover utilizzare l’opzione ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]**.

>[!NOTE]
>
>Quando si escludono alcune righe come descritto in questa sezione, viene automaticamente aggiunta una regola [!UICONTROL Always exclude items] nella finestra di dialogo del filtro [!UICONTROL Advanced]. Puoi visualizzare la regola applicata selezionando l’icona Filtro ![Filtro](/help/assets/icons/Filter.svg), quindi [**[!UICONTROL Show advanced]**](#apply-a-simple-or-advanced-filter-to-a-table).

Per escludere righe specifiche da una tabella a forma libera:

1. Passa il puntatore sulla riga da escludere, quindi seleziona ![Chiudi](/help/assets/icons/Close.svg).

   Tieni premuto il tasto ***Maiusc*** per selezionare un intervallo di righe oppure il tasto ***Cmd*** (in Mac) o il tasto ***Ctrl*** (in Windows) per selezionare più righe.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### Applicare un filtro semplice o avanzato a una tabella

Per filtrare i dati nelle tabelle a forma libera:

1. Passa il puntatore sulla colonna contenente i dati da filtrare. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Seleziona l’icona ![Filtro](/help/assets/icons/Filter.svg) **Filtro** quando viene visualizzata.

   ![Tabella a forma libera con l’icona Filtro evidenziata.](assets/table-filter-icon.png)

   Nella finestra di dialogo **[!UICONTROL Search]** sono disponibili le seguenti opzioni:

   ![Filtro semplice](assets/filter-simple.png){width="500"}

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Includi “Nessun valore”**] | Seleziona questa opzione per visualizzare nella tabella una riga **[!UICONTROL No value]** con i dati che non hanno alcun valore per la dimensione selezionata. Deseleziona questa opzione per nascondere la riga **[!UICONTROL No value]**. |
   | [!UICONTROL **Cerca parola o frase**] | Specifica una parola o una frase in base a cui applicare il filtro. Vengono visualizzate solo le righe contenenti la parola o la frase esatta specificata. |


1. (Facoltativo) Per filtrare in base a criteri diversi o a più criteri, seleziona [!UICONTROL **Mostra avanzate**].

   Sono disponibili le seguenti opzioni di filtro avanzato:

   ![Filtro semplice](assets/filter-advanced.png){width=500}

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Includi “Nessun valore”**] | Seleziona questa opzione per visualizzare nella tabella una riga **[!UICONTROL No value]** con i dati che non hanno alcun valore per la dimensione selezionata. Deseleziona questa opzione per nascondere la riga **[!UICONTROL No value]**. |
   | [!UICONTROL **Corrispondenza**] | Scegli [!UICONTROL **Se sono soddisfatti tutti i criteri**] per mostrare solo i dati che soddisfano tutti i criteri specificati. In genere, questa opzione genera dati più precisi.<br/><br/>Scegli [!UICONTROL **Se sono soddisfatti i criteri**] per mostrare i dati che soddisfano tutti i criteri di filtro specificati. Di solito, questa opzione genera dati meno precisi. |
   | [!UICONTROL **Criteri**] | Seleziona tra le opzioni filtro seguenti:<br/><ul><li>[!UICONTROL **Contiene la frase**] (impostazione predefinita): nei risultati filtrati vengono inclusi solo i dati che contengono la frase esatta specificata. Le parole devono essere nell’ordine specificato nel [!UICONTROL **campo Cerca parola o frase**].</li><li>[!UICONTROL **Contiene qualsiasi termine**]: nei risultati filtrati sono inclusi solo i dati contenenti una o più parole della frase specificata. </li><li>[!UICONTROL **Contiene tutti i termini**]: nei risultati filtrati sono inclusi solo i dati che contengono tutte le parole della frase specificata. Le parole non devono necessariamente essere nell&#39;ordine specificato nel [!UICONTROL **campo Cerca parola o frase**].</li><li>[!UICONTROL **Non contiene alcun termine**]: nei risultati filtrati sono inclusi solo i dati che non contengono le parole della frase specificata. </li><li>[!UICONTROL **Non contiene la frase**]: nei risultati filtrati sono inclusi solo i dati che non contengono la frase esatta specificata. Le parole devono essere nell’ordine specificato nel [!UICONTROL **campo Cerca parola o frase**].</li><li>[!UICONTROL **È uguale a**]: nei risultati filtrati vengono inclusi solo i dati che corrispondono esattamente alla frase specificata. </li><li>[!UICONTROL **Non è uguale a**]: nei risultati filtrati vengono inclusi solo i dati che non corrispondono esattamente alla frase specificata. </li><li>[!UICONTROL **Inizia con**]: nei risultati filtrati sono inclusi solo i dati che iniziano con la parola o la frase esatta specificata. </li><li>[!UICONTROL **Termina con**]: nei risultati filtrati sono inclusi solo i dati che terminano con la parola o la frase esatta specificata. </li></ul>Seleziona ![Aggiungi](/help/assets/icons/Add.svg) [!UICONTROL **Aggiungi riga**] per aggiungere più criteri di filtro. L’opzione selezionata per [!UICONTROL **Corrispondenza**] determina **[!UICONTROL If all criteria are met]** o **[!UICONTROL If any criteria are met]**. |
   | [!UICONTROL **Escludi sempre gli elementi**] | Specifica il nome degli elementi da escludere dai dati filtrati. |

1. Seleziona **[!UICONTROL Apply]** per filtrare i dati. Seleziona **[!UICONTROL Clear]** per cancellare l’intero input. Seleziona **[!UICONTROL Cancel]** per annullare e chiudere la finestra di dialogo. <br/>Un’icona ![Filtro](/help/assets/icons/FilterColored.svg) **Filtro** colorata indica e visualizza i dettagli quando viene applicato un filtro alla tabella.

### Utilizzare segmenti di pubblico

Per ulteriori dettagli, consulta [Panoramica sulla segmentazione](/help/components/segments/seg-overview.md).

## Ordinare le tabelle

Puoi ordinare i dati di una tabella a forma libera in base a qualsiasi colonna di Analysis Workspace che può essere una dimensione oppure una metrica. Una freccia indica l’ordinamento dei dati (**↓** se decrescente o **↑** se crescente).

![Ordinamento](assets/sorting.gif)
