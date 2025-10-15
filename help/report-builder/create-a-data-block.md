---
title: Come creare un blocco di dati utilizzando Report Builder in Customer Journey Analytics
description: Descrive come creare un blocco di dati.
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
source-git-commit: 7d3300336a955facc230f335d1452096700ea98b
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 1%

---

# Creare un blocco di dati

Un *blocco di dati* è la tabella di dati creata da una singola richiesta di dati. Una cartella di lavoro di Report Builder può contenere più blocchi di dati. Quando crei un blocco di dati, configura prima il blocco di dati e quindi lo genera.

## Configurare il blocco di dati

Configura i parametri iniziali dei blocchi di dati per la posizione del blocco di dati, le visualizzazioni dati e un intervallo di date.

1. Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**.

   ![Schermata che mostra l&#39;opzione Crea blocco di dati](./assets/create-data-block.png){zoomable="yes"}


1. Imposta **[!UICONTROL Data block location]**.

   L&#39;opzione Posizione blocco dati definisce la posizione del foglio di lavoro in cui Report Builder aggiunge i dati al foglio di lavoro.

   Per specificare il percorso del blocco di dati, selezionare una singola cella nel foglio di lavoro o immettere un indirizzo di cella, ad esempio `a3`, `\\\$a3`, `a\\\$3` o `sheet1!a2`. La cella specificata diventa l&#39;angolo superiore sinistro del blocco di dati quando i dati vengono recuperati.

   Utilizza ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) per scegliere una posizione di blocco di dati dalla cella selezionata corrente nel foglio.

1. Scegliere **[!UICONTROL Data views]**.

   L’opzione Visualizzazioni dati consente di scegliere una visualizzazione dati da un menu a discesa o di fare riferimento a una visualizzazione dati da una posizione cella.

   Selezionare ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) per creare una visualizzazione dati da una cella.

1. Imposta **[!UICONTROL Date range]**.

   L&#39;opzione **[!UICONTROL Date range]** consente di scegliere un intervallo di date. Gli intervalli di date possono essere fissi o continui.

   Selezionare **[!UICONTROL Calendar]** per scegliere un intervallo di dati utilizzando ![Calendario](/help/assets/icons/Calendar.svg) oppure immettere manualmente un intervallo di date. È possibile scegliere un predefinito dal menu a discesa **[!UICONTROL _Predefiniti di ricerca_]**.

   Selezionare **[!UICONTROL From cell]** per definire i dati iniziali e finali in base a una cella del foglio corrente.

   Per informazioni sulle opzioni dell&#39;intervallo di date, vedere [Selezionare un intervallo di date](select-date-range.md).

1. Seleziona **[!UICONTROL Next]**.

   ![Schermata che mostra l&#39;opzione Intervallo date e il pulsante Avanti attivo.](./assets/choose_date_data_view3.png)

   Dopo aver configurato il blocco di dati, puoi selezionare dimensioni, metriche e segmenti per crearlo. Le schede **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]** e **[!UICONTROL Segments]** sono visualizzate sopra il riquadro **[!UICONTROL Table]**.

## Creare il blocco di dati

Per creare il blocco di dati, seleziona i componenti del rapporto, quindi personalizza il layout.

1. Aggiungere **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]** e **[!UICONTROL Segments]** componenti.

   Scorrere gli elenchi dei componenti o utilizzare il campo ![Cerca](/help/assets/icons/Search.svg) **[!UICONTROL _Cerca componenti_]** per individuare i componenti. Trascinare i componenti nel riquadro [!UICONTROL Table] oppure selezionare due volte il nome di un componente nell&#39;elenco per aggiungerlo al riquadro [!UICONTROL Table].

   Selezionate due volte un componente per aggiungerlo a una sezione di default della tabella.

   - I componenti Dimension vengono aggiunti alla sezione ![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]** o alla sezione ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]** se è già presente una dimensione nelle colonne.
   - Componenti data aggiunti alla sezione ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]**.
   - I componenti del segmento vengono aggiunti alla sezione ![Segmentazione](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]**.
   - I componenti delle metriche vengono aggiunti alla sezione ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Values]**.

1. Disporre gli elementi nel riquadro Tabella per personalizzare il layout del blocco di dati.

   Trascina e rilascia i componenti all&#39;interno di ogni elenco nel riquadro Tabella per riordinare i componenti o seleziona ![AltroPiccolo](/help/assets/icons/MoreSmall.svg) e seleziona ![FrecciaSu](/help/assets/icons/ArrowUp.svg) Sposta su, ![FrecciaGiù](/help/assets/icons/ArrowDown.svg) Sposta giù e altro per spostare i componenti all&#39;interno di un elenco.

   Quando si aggiungono componenti alla tabella, nella posizione del blocco di dati nel foglio di lavoro viene visualizzata un&#39;anteprima del blocco di dati. Il layout dell’anteprima dei blocchi di dati viene aggiornato automaticamente quando aggiungi, sposti o rimuovi elementi nella tabella.

   ![Schermata che mostra i componenti aggiunti e il foglio di lavoro aggiornato.](./assets/image10.png)


1. È possibile impostare **[!UICONTROL Start date]** come dimensione per identificare la data di inizio del blocco di dati. L’aggiunta di dati di inizio come dimensione è utile se disponi di un rapporto pianificato regolarmente con un intervallo di date continuo. Oppure, se hai un intervallo di date non convenzionale e devi essere esplicito sulla data di inizio.

   ![Schermata che mostra la data di inizio nell&#39;elenco delle dimensioni.](./assets/start-date-dimension.png)

1. È possibile visualizzare o nascondere le intestazioni di riga e di colonna. A tale scopo, effettua le seguenti operazioni:

   1. Selezionare l&#39;icona **[!UICONTROL Table]** ![Impostazioni](/help/assets/icons/Setting.svg).

      ![Schermata che mostra l&#39;opzione Impostazioni tabella.](./assets/table-settings.png)

   1. Selezionare o deselezionare l&#39;opzione per **[!UICONTROL Display row and column headers]**. Le intestazioni vengono visualizzate per impostazione predefinita.

1. Facoltativamente, puoi anche nascondere o mostrare le etichette delle dimensioni e le intestazioni delle metriche. A tale scopo, effettua le seguenti operazioni:

   1. Seleziona ![AltroPiccolo](/help/assets/icons/MoreSmall.svg) nell&#39;etichetta della dimensione o nell&#39;intestazione della colonna per visualizzare il menu di scelta rapida.

      ![Icona puntini di sospensione nella sezione Riga.](./assets/row-heading.png)

   1. Seleziona ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]** o ![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]** per attivare/disattivare l&#39;etichetta della dimensione o l&#39;intestazione della colonna. Tutte le etichette sono visualizzate per impostazione predefinita.

1. Seleziona **[!UICONTROL Finish]** per completare la configurazione del blocco di dati.

1. Durante il recupero dei dati di analisi viene visualizzato un messaggio di elaborazione **[!UICONTROL #BUSY]**.

   ![Elaborazione del messaggio.](./assets/image11.png)

1. Report Builder recupera i dati e visualizza il blocco di dati completato nel foglio di lavoro.

   ![Blocco di dati completato.](./assets/image12.png)


>[!MORELIKETHIS]
>
>[Selezionare una visualizzazione dati](select-data-view.md)
>&#x200B;>[Seleziona un intervallo di date](select-date-range.md)
>&#x200B;>[Filtra dimensioni](filter-dimensions.md)
>&#x200B;>[Operazioni con i segmenti](work-with-filters.md)
>
