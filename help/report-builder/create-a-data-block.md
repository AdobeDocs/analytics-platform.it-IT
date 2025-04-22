---
title: Come creare un blocco di dati utilizzando Report Builder in Customer Journey Analytics
description: Descrive come creare un blocco di dati.
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
source-git-commit: 56ac1c5a6d13a972aed90cab79cbc5f794cedc9e
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%

---

# Creare un blocco di dati

Un *blocco di dati* è la tabella di dati creata da una singola richiesta di dati. Una cartella di lavoro di Report Builder può contenere più blocchi di dati. Quando crei un blocco di dati, configura prima il blocco di dati e quindi lo genera.

## Configurare il blocco di dati

Configura i parametri iniziali dei blocchi di dati per la posizione del blocco di dati, le visualizzazioni dati e un intervallo di date.

1. Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**.

   ![Schermata che mostra l&#39;opzione Crea blocco di dati.](./assets/create-datablock.png)

1. Imposta **[!UICONTROL Data block location]**.

   L&#39;opzione Posizione blocco dati definisce la posizione del foglio di lavoro in cui Report Builder aggiunge i dati al foglio di lavoro.

   Per specificare il percorso del blocco di dati, selezionare una singola cella nel foglio di lavoro oppure immettere un indirizzo di cella, ad esempio `a3`, `\\\$a3`, `a\\\$3` o `sheet1!a2`. La cella specificata sarà l’angolo superiore sinistro del blocco di dati quando i dati vengono recuperati.

   Utilizza ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) per scegliere una posizione del blocco di dati dalla cella selezionata corrente nel foglio.

1. Scegliere **[!UICONTROL Data views]**.

   L’opzione Visualizzazioni dati consente di scegliere una visualizzazione dati da un menu a discesa o di fare riferimento a una visualizzazione dati da una posizione cella.

   Selezionare ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) per creare una visualizzazione dati da una cella.

1. Imposta **[!UICONTROL Date range]**.

   L’opzione Intervallo date ti consente di scegliere un intervallo di date. Gli intervalli di date possono essere fissi o continui. Per informazioni sulle opzioni dell&#39;intervallo di date, vedere [Selezionare un intervallo di date](select-date-range.md).

   Selezionare **[!UICONTROL Calendar]** per scegliere un intervallo di dati utilizzando ![Calendario](/help/assets/icons/Calendar.svg) oppure immettere manualmente un intervallo di date. In alternativa, potete scegliere un predefinito dal menu a discesa Predefiniti di ricerca (Search Presets).

   Selezionare **[!UICONTROL From Cell]** per definire i dati iniziali e finali in base a una cella del foglio corrente.

1. Seleziona **Avanti**.

   ![Schermata che mostra l&#39;opzione Intervallo date e il pulsante Avanti attivo.](./assets/choose_date_data_view3.png)

   Dopo aver configurato il blocco di dati, puoi selezionare dimensioni, metriche e segmenti per crearlo. Le schede Dimensioni, Metriche e Segmenti vengono visualizzate sopra il riquadro Generatore tabella.

## Creare il blocco di dati

Per creare il blocco di dati, seleziona i componenti del rapporto, quindi personalizza il layout.

1. Aggiungi dimensioni, metriche e segmenti.

   Scorrere gli elenchi dei componenti o utilizzare il campo **ricerca** per individuare i componenti. Trascina i componenti nel riquadro Tabella oppure fai doppio clic sul nome di un componente nell’elenco per aggiungerlo automaticamente al riquadro Tabella.

   Fai doppio clic su un componente per aggiungerlo a una sezione predefinita della tabella.

   - I componenti Dimension vengono aggiunti alla sezione Riga o alla sezione Colonna se una dimensione è già presente nelle colonne.
   - I componenti data vengono aggiunti alla sezione Colonna.
   - I componenti del segmento vengono aggiunti alla sezione Segmenti.

### Data di inizio come Dimension

Imposta la data di inizio come dimensione per identificare chiaramente la data di inizio del blocco di dati. Questa funzione è utile se disponi di un rapporto pianificato regolarmente con un intervallo di date continuo o se disponi di un intervallo di date non convenzionale e devi essere libero dalla data di inizio.

![Schermata che mostra la data di inizio nell&#39;elenco delle dimensioni.](./assets/start-date-dimension.png)

1. Disporre gli elementi nel riquadro Tabella per personalizzare il layout del blocco di dati.

   Trascina i componenti nel riquadro Tabella per riordinarli oppure fai clic con il pulsante destro del mouse sul nome di un componente e scegli dal menu delle opzioni.

   Quando si aggiungono componenti alla tabella, nella posizione del blocco di dati nel foglio di lavoro viene visualizzata un&#39;anteprima del blocco di dati. Il layout dell’anteprima dei blocchi di dati viene aggiornato automaticamente quando aggiungi, sposti o rimuovi elementi nella tabella.

   ![Schermata che mostra i componenti aggiunti e il foglio di lavoro aggiornato.](./assets/image10.png)

### Visualizzare o nascondere le intestazioni di riga e di colonna

1. Selezionare l&#39;icona **[!UICONTROL Table]** ![Impostazioni](/help/assets/icons/Setting.svg).

   ![Schermata che mostra l&#39;opzione Impostazioni tabella.](./assets/table-settings.png)

1. Seleziona o deseleziona l’opzione per Visualizzare le intestazioni di riga e colonna. Le intestazioni vengono visualizzate per impostazione predefinita.

### Nascondere o mostrare etichette dimensione e intestazioni metriche

Per visualizzare le impostazioni, seleziona l’icona con i puntini di sospensione sulle dimensioni o sulle intestazioni di colonna.

![Icona puntini di sospensione nella sezione Riga.](./assets/row-heading.png)

1. Seleziona ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]** o ![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]** per attivare/disattivare le etichette di dimensione o le intestazioni di colonna. Tutte le etichette sono visualizzate per impostazione predefinita.

1. Seleziona **[!UICONTROL Finish]**.


Durante il recupero dei dati di analisi viene visualizzato un messaggio di elaborazione.

![Elaborazione del messaggio.](./assets/image11.png)

Report Builder recupera i dati e visualizza il blocco di dati completato nel foglio di lavoro.

![Blocco di dati completato.](./assets/image12.png)
