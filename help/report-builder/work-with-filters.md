---
title: Come utilizzare i filtri nel Report Builder nel Customer Journey Analytics
description: Descrive come utilizzare i filtri nel Report Builder per il Customer Journey Analytics
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# Utilizzare i filtri nel Report Builder

Puoi applicare i filtri quando crei un nuovo blocco di dati o quando selezioni il **Modifica blocco di dati** dal pannello COMANDI.

## Applicare filtri a un blocco di dati

Per applicare un filtro all’intero blocco di dati, fai doppio clic su un filtro o trascina i filtri dall’elenco dei componenti alla sezione Filtri della tabella.

## Applicare filtri alle singole metriche

Per applicare filtri a singole metriche, trascina e rilascia un filtro su una metrica nella tabella. Puoi anche fare clic sul pulsante **...** a destra di una metrica nel riquadro Tabella, quindi selezionare **Filtra metrica**. Per visualizzare i filtri applicati, passa il cursore del mouse su una metrica o selezionala nel riquadro Tabella. Le metriche con filtri applicati visualizzano un’icona di filtro.

<!-- ![](./assets/image24.png) -->

![](./assets/filter_by.png)

## Filtri di modifica rapida

Puoi utilizzare il pannello Modifica rapida per aggiungere, rimuovere o sostituire i filtri per i blocchi di dati esistenti.

Quando si seleziona un intervallo di celle nel foglio di calcolo, **Filtri** nel pannello Modifica rapida viene visualizzato un elenco riepilogativo dei filtri utilizzati dai blocchi di dati nella selezione.

Per modificare i filtri tramite il pannello Modifica rapida

1. Seleziona un intervallo di celle da uno o più blocchi di dati.

   ![](./assets/select_multiple_dbs.png)

1. Fai clic sul collegamento Filtri per avviare il pannello Modifica rapida - Filtri.

   ![](./assets/quick_edit_filters.png)

### Aggiungere o rimuovere un filtro

Puoi aggiungere o rimuovere filtri utilizzando le opzioni Aggiungi/Rimuovi.

1. Seleziona la **Aggiungi/Rimuovi** nel pannello Quick edit-filters (Modifica rapida filtri).

   Tutti i filtri applicati ai blocchi di dati selezionati sono elencati nel pannello Quick Edit-filters (Modifica rapida filtri). I filtri applicati a tutti i blocchi di dati nella selezione sono elencati nella sezione **Applicato a tutti i blocchi di dati selezionati** intestazione. I filtri applicati ad alcuni blocchi di dati, ma non a tutti, sono elencati in **Applicato a 1 o più blocchi di dati selezionati** intestazione.

   Quando nei blocchi di dati selezionati sono presenti più filtri, puoi cercare filtri specifici utilizzando **Aggiungi filtro** campo di ricerca.

   ![](./assets/add_filter.png)

1. Aggiungere filtri selezionando i filtri dalla **Aggiungi filtro** menu a discesa.

   L’elenco dei filtri ricercabili include tutti i filtri accessibili alle visualizzazioni dati presenti in uno o più blocchi di dati selezionati, nonché tutti i filtri disponibili a livello globale nell’organizzazione.

   L’aggiunta di un filtro applica il filtro a tutti i blocchi di dati della selezione.

1. Per rimuovere i filtri, fai clic sull’icona Elimina **x** a destra dei filtri nella sezione **Filtri applicati** elenco.

1. Clic **Applica** per salvare le modifiche e tornare al pannello hub.

   Nel Report Builder viene visualizzato un messaggio per confermare le modifiche apportate al filtro.

### Sostituire un filtro

È possibile sostituire un filtro esistente con un altro filtro per modificare la modalità di filtraggio dei dati.

1. Seleziona la **Sostituisci** nel pannello Quick edit-filters (Modifica rapida filtri).

   ![](./assets/replace_filter.png)

1. Utilizza il **Elenco di ricerca** campo di ricerca per individuare filtri specifici.

1. Scegli uno o più filtri da sostituire.

1. Cerca uno o più filtri nel campo Sostituisci con.

   Quando si seleziona un filtro, questo viene aggiunto al **Sostituisci con**... elenco.

   ![](./assets/replace_screen_new.png)

1. Fai clic su **Applica**.

   Il Report Builder aggiorna l’elenco dei filtri per riflettere la sostituzione.
