---
title: Come utilizzare i segmenti in Report Builder in Customer Journey Analytics
description: Descrive come utilizzare i segmenti in Report Builder for Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
source-git-commit: bd2d45b9fc1380e36fc482ee75e1a9bbb26f6cf7
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 0%

---

# Utilizzare i segmenti in Report Builder

Puoi applicare i segmenti quando crei un nuovo blocco di dati o quando selezioni l&#39;opzione **Modifica blocco di dati** dal pannello COMANDI.

## Applicare segmenti a un blocco di dati

Per applicare un segmento all’intero blocco di dati, fai doppio clic su un segmento o trascina i segmenti dall’elenco dei componenti nella sezione dei segmenti della tabella.

## Applicare segmenti a singole metriche

Per applicare segmenti a singole metriche, trascina un segmento su una metrica nella tabella. È inoltre possibile fare clic sull&#39;icona **...** a destra di una metrica nel riquadro Tabella, quindi selezionare **Metrica segmento**. Per visualizzare i segmenti applicati, passa il cursore del mouse su una metrica o selezionala nel riquadro Tabella. Le metriche con segmenti applicati visualizzano un’icona di segmento.

Scheda ![segmenti con metriche.](./assets/filter_by.png)

## Modifica rapida segmenti

Puoi utilizzare il pannello Modifica rapida per aggiungere, rimuovere o sostituire segmenti per i blocchi di dati esistenti.

Quando selezioni un intervallo di celle nel foglio di calcolo, il collegamento **Segmenti** nel pannello di modifica rapida visualizza un elenco di riepilogo dei segmenti utilizzati dai blocchi di dati nella selezione.

Per modificare i segmenti mediante il pannello Modifica rapida

1. Seleziona un intervallo di celle da uno o più blocchi di dati.

   ![Pannello Quick Edit segment (Modifica rapida segmento) che mostra le opzioni dei segmenti per le visualizzazioni dati, l&#39;intervallo di date e i segmenti.](./assets/select_multiple_dbs.png)

1. Fai clic sul collegamento Segmenti per aprire il pannello Modifica rapida - Segmenti.

   ![il pannello dei segmenti che mostra il campo Aggiungi segmento e gli elenchi Segmenti applicati.](./assets/quick_edit_filters.png)

### Aggiungere o rimuovere un segmento

Puoi aggiungere o rimuovere segmenti utilizzando le opzioni Aggiungi/Rimuovi.

1. Seleziona la scheda **Aggiungi/Rimuovi** nel pannello Quick edit-segments.

   Tutti i segmenti applicati ai blocchi di dati selezionati sono elencati nel pannello Quick Edit-segments (Modifica rapida segmenti). I segmenti applicati a tutti i blocchi di dati nella selezione sono elencati nell&#39;intestazione **Applicato a tutti i blocchi di dati selezionati**. I segmenti applicati ad alcuni blocchi di dati, ma non a tutti, sono elencati nell&#39;intestazione **Applicato a uno o più blocchi di dati selezionati**.

   Quando nei blocchi di dati selezionati sono presenti più segmenti, è possibile cercare segmenti specifici utilizzando il campo di ricerca **Aggiungi segmento**.

   ![Campo Aggiungi segmento.](./assets/add_filter.png)

1. Aggiungi segmenti selezionando i segmenti dal menu a discesa **Aggiungi segmento**.

   L’elenco dei segmenti ricercabili include tutti i segmenti accessibili alle visualizzazioni dati presenti in uno o più dei blocchi di dati selezionati, nonché tutti i segmenti disponibili a livello globale nell’organizzazione.

   L’aggiunta di un segmento applica il segmento a tutti i blocchi di dati della selezione.

1. Per rimuovere i segmenti, fare clic sull&#39;icona Elimina **x** a destra dei segmenti nell&#39;elenco **Segmenti applicati**.

1. Fai clic su **Applica** per salvare le modifiche e tornare al pannello hub.

   In Report Builder viene visualizzato un messaggio per confermare le modifiche al segmento applicato.

### Sostituire un segmento

Puoi sostituire un segmento esistente con un altro segmento per modificare la modalità di segmentazione dei dati.

1. Seleziona la scheda **Sostituisci** nel pannello Quick edit-segments.

   ![Selezionare la scheda Sostituisci.](./assets/replace_filter.png)

1. Utilizza il campo di ricerca **Elenco di ricerca** per individuare segmenti specifici.

1. Scegli uno o più segmenti da sostituire.

1. Cerca uno o più segmenti nel campo Sostituisci con.

   Quando si seleziona un segmento, questo viene aggiunto all&#39;elenco **Sostituisci con**....

   ![La scheda Sostituisci con il blocco di dati Persone nell&#39;app selezionato e l&#39;elenco Sostituisci con aggiornato mostrano Persone nell&#39;app rivista.](./assets/replace_screen_new.png)

1. Fai clic su **Applica**.

   Report Builder aggiorna l’elenco dei segmenti in base alla sostituzione.

### Definire i segmenti dei blocchi di dati dalla cella

I blocchi di dati possono fare riferimento a segmenti da una cella. Più blocchi di dati possono fare riferimento alla stessa cella per i segmenti, consentendo di cambiare facilmente segmenti per più blocchi di dati alla volta.

Per applicare segmenti da una cella

1. Passa al passaggio 2 nel processo di creazione o modifica dei blocchi di dati. Vedi [Creare un blocco di dati](./create-a-data-block.md).
1. Fai clic sulla scheda **Segmenti** per definire i segmenti.
1. Fare clic su **Crea segmento dalla cella**.

   ![Crea segmento dall&#39;icona cella.](./assets/create-filter-from-cell.png)

1. Seleziona la cella da cui desideri che i blocchi di dati facciano riferimento a un segmento.

1. Aggiungi il segmento da aggiungere alla cella facendo doppio clic sul segmento o trascinandolo nella sezione Segmenti inclusi.

   Nota: è possibile selezionare una sola scelta per la cella specificata alla volta.

   ![La finestra Aggiungi segmento da cella mostra i segmenti inclusi.](./assets/select-filters.png)

1. Fare clic su **Applica** per creare la cella di riferimento.

1. Dalla scheda **Segmenti**, aggiungi il segmento della cella di riferimento appena creato al blocco di dati.

   Scheda ![segmenti che mostra il segmento Sheet1!J1(All Data) aggiunto alla tabella.](./assets/reference-cell-filter.png)

1. Fai clic su **Fine**.

   Ora è possibile fare riferimento a questa cella da altri blocchi di dati nei loro segmenti. Per applicare la cella di riferimento come segmento ad altri blocchi di dati, è sufficiente aggiungere il riferimento di cella ai relativi segmenti dalla scheda Segmenti.

#### Utilizza la cella di riferimento per modificare i segmenti dei blocchi di dati

1. Selezionare la cella di riferimento nel foglio di calcolo.

1. Fare clic sul collegamento in **Segmenti dalla cella** nel menu Modifica rapida.

   ![segmenti dal collegamento di cella che mostra Sheet1!J1 (Tutti i dati)](./assets/filters-from-cell-link.png)

1. Seleziona il segmento dal menu a discesa.

   ![menu a discesa dei segmenti](./assets/filter-drop-down.png)

1. Fai clic su **Applica**.
