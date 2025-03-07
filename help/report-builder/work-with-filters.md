---
title: Come utilizzare i segmenti in Report Builder in Customer Journey Analytics
description: Descrive come utilizzare i segmenti in Report Builder for Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
source-git-commit: 0d87f28aa4f8c1b16f46227abad7d374800dcb66
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# Utilizzare i segmenti in Report Builder

Puoi applicare i segmenti quando crei un nuovo blocco di dati o quando selezioni l&#39;opzione **Modifica blocco di dati** dal pannello COMANDI.

## Applicare filtri a un blocco di dati

Per applicare un filtro all’intero blocco di dati, fai doppio clic su un filtro o trascina i filtri dall’elenco dei componenti alla sezione Filtri della tabella.

## Applicare filtri alle singole metriche

Per applicare filtri a singole metriche, trascina e rilascia un filtro su una metrica nella tabella. È inoltre possibile fare clic sull&#39;icona **...** a destra di una metrica nel riquadro Tabella, quindi selezionare **Filtra metrica**. Per visualizzare i filtri applicati, passa il cursore del mouse su una metrica o selezionala nel riquadro Tabella. Le metriche con filtri applicati visualizzano un’icona di filtro.

![Scheda Filtri che visualizza le metriche.](./assets/filter_by.png)

## Filtri di modifica rapida

Puoi utilizzare il pannello Modifica rapida per aggiungere, rimuovere o sostituire i filtri per i blocchi di dati esistenti.

Quando selezioni un intervallo di celle nel foglio di calcolo, il collegamento **Filtri** nel pannello di modifica rapida visualizza un elenco di riepilogo dei filtri utilizzati dai blocchi di dati nella selezione.

Per modificare i filtri tramite il pannello Modifica rapida

1. Seleziona un intervallo di celle da uno o più blocchi di dati.

   ![Pannello di filtro Modifica rapida che mostra le opzioni di filtro per le visualizzazioni dati, l&#39;intervallo di date e i filtri.](./assets/select_multiple_dbs.png)

1. Fai clic sul collegamento Filtri per avviare il pannello Modifica rapida - Filtri.

   ![il pannello Filtri che mostra il campo Aggiungi filtro e gli elenchi Filtri applicati.](./assets/quick_edit_filters.png)

### Aggiungere o rimuovere un filtro

Puoi aggiungere o rimuovere filtri utilizzando le opzioni Aggiungi/Rimuovi.

1. Selezionare la scheda **Aggiungi/Rimuovi** nel pannello Quick edit-filters (Modifica rapida filtri).

   Tutti i filtri applicati ai blocchi di dati selezionati sono elencati nel pannello Quick Edit-filters (Modifica rapida filtri). I filtri applicati a tutti i blocchi di dati nella selezione sono elencati nell&#39;intestazione **Applicati a tutti i blocchi di dati selezionati**. I filtri applicati ad alcuni blocchi di dati, ma non a tutti, sono elencati nell&#39;intestazione **Applicati a uno o più blocchi di dati selezionati**.

   Quando nei blocchi di dati selezionati sono presenti più filtri, è possibile cercare filtri specifici utilizzando il campo di ricerca **Aggiungi filtro**.

   ![Campo Aggiungi filtro.](./assets/add_filter.png)

1. Aggiungere filtri selezionando i filtri dal menu a discesa **Aggiungi filtro**.

   L’elenco dei filtri ricercabili include tutti i filtri accessibili alle visualizzazioni dati presenti in uno o più blocchi di dati selezionati, nonché tutti i filtri disponibili a livello globale nell’organizzazione.

   L’aggiunta di un filtro applica il filtro a tutti i blocchi di dati della selezione.

1. Per rimuovere i filtri, fare clic sull&#39;icona Elimina **x** a destra dei filtri nell&#39;elenco **Filtri applicati**.

1. Fai clic su **Applica** per salvare le modifiche e tornare al pannello hub.

   In Report Builder viene visualizzato un messaggio per confermare le modifiche apportate al filtro.

### Sostituire un filtro

È possibile sostituire un filtro esistente con un altro filtro per modificare la modalità di filtraggio dei dati.

1. Selezionare la scheda **Sostituisci** nel pannello Quick edit-filters.

   ![Selezionare la scheda Sostituisci.](./assets/replace_filter.png)

1. Utilizza il campo di ricerca **Elenco di ricerca** per individuare filtri specifici.

1. Scegli uno o più filtri da sostituire.

1. Cerca uno o più filtri nel campo Sostituisci con.

   Selezionando un filtro, viene aggiunto all&#39;elenco **Sostituisci con**....

   ![La scheda Sostituisci con il blocco di dati Persone nell&#39;app selezionato e l&#39;elenco Sostituisci con aggiornato mostrano Persone nell&#39;app rivista.](./assets/replace_screen_new.png)

1. Fai clic su **Applica**.

   Report Builder aggiorna l’elenco dei filtri in base alla sostituzione.

### Definire i filtri dei blocchi di dati dalla cella

I blocchi di dati possono fare riferimento a filtri provenienti da una cella. Più blocchi di dati possono fare riferimento alla stessa cella per i filtri, consentendo di cambiare facilmente i filtri per più blocchi di dati alla volta.

Per applicare filtri da una cella

1. Passa al passaggio 2 nel processo di creazione o modifica dei blocchi di dati. Vedi [Creare un blocco di dati](./create-a-data-block.md).
1. Fai clic sulla scheda **Filtri** per definire i filtri.
1. Fare clic su **Crea filtro dalla cella**.

   ![Crea filtro da icona cella.](./assets/create-filter-from-cell.png)

1. Seleziona la cella dalla quale desideri che i blocchi di dati facciano riferimento a un filtro.

1. Aggiungi alla cella la scelta di filtri che desideri aggiungere facendo doppio clic sul filtro o trascinandolo nella sezione Filtri inclusi.

   Nota: è possibile selezionare una sola scelta per la cella specificata alla volta.

   ![La finestra Aggiungi filtro da cella mostra i filtri inclusi.](./assets/select-filters.png)

1. Fare clic su **Applica** per creare la cella di riferimento.

1. Dalla scheda **Filtri**, aggiungi il filtro della cella di riferimento appena creato al blocco di dati.

   ![Scheda Filtri che mostra il filtro Sheet1!J1(All Data) aggiunto alla tabella.](./assets/reference-cell-filter.png)

1. Fai clic su **Fine**.

   Ora puoi fare riferimento a questa cella da altri blocchi di dati nei loro filtri. Per applicare la cella di riferimento come filtro ad altri blocchi di dati, è sufficiente aggiungere il riferimento di cella ai relativi filtri dalla scheda Filtri.

#### Utilizza la cella di riferimento per modificare i filtri dei blocchi di dati

1. Selezionare la cella di riferimento nel foglio di calcolo.

1. Fare clic sul collegamento in **Filtri da cella** nel menu Modifica rapida.

   ![Filtri dal collegamento di cella che mostra Sheet1!J1 (Tutti i dati)](./assets/filters-from-cell-link.png)

1. Seleziona il filtro dal menu a discesa.

   ![Menu a discesa Filtro](./assets/filter-drop-down.png)

1. Fai clic su **Applica**.
