---
title: Come utilizzare i filtri nel Report Builder del Customer Journey Analytics
description: Descrive come utilizzare i filtri in Report Builder per CJA
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: b655813816b2a8e0d47b035eefa11926f106ee0e
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---


# Utilizzare i filtri nel Report Builder

È possibile applicare i filtri quando si crea un nuovo blocco di dati o quando si seleziona l&#39;opzione **Modifica blocco di dati** dal pannello COMANDI.

## Applicazione di filtri a un blocco di dati

Per applicare un filtro all’intero blocco di dati, fai doppio clic su un filtro o trascina e rilascia i filtri dall’elenco dei componenti nella sezione Filtri della tabella.

## Applicazione di filtri alle singole metriche

Per applicare filtri a singole metriche, trascina e rilascia un filtro su una metrica nella tabella. Puoi anche fare clic su **...Icona** a destra di una metrica nel riquadro Tabella , quindi seleziona **Filtra metrica**. Per visualizzare i filtri applicati, passa il puntatore del mouse su una metrica nel riquadro Tabella o selezionala. Le metriche con filtri applicati presentano un’icona di filtro.

<!-- ![](./assets/image24.png) -->

![](./assets/filter_by.png)

## Filtri di modifica rapida

Puoi usare il pannello Modifica rapida per aggiungere, rimuovere o sostituire i filtri per i blocchi di dati esistenti.

Quando selezioni un intervallo di celle nel foglio di calcolo, il collegamento **Filtri** nel pannello Modifica rapida visualizza un elenco di riepilogo dei filtri utilizzati dai blocchi di dati in tale selezione.

Per modificare i filtri utilizzando il pannello di modifica rapida

1. Seleziona un intervallo di celle da uno o più blocchi di dati.

   ![](./assets/select_multiple_dbs.png)

1. Fai clic sul collegamento Filtri per avviare il pannello Modifica rapida - Filtri .

   ![](./assets/quick_edit_filters.png)

### Aggiungere o rimuovere un filtro

È possibile aggiungere o rimuovere filtri utilizzando le opzioni Aggiungi/Rimuovi.

1. Seleziona la scheda **Aggiungi/Rimuovi** nel pannello Filtri di modifica rapida .

   Tutti i filtri applicati ai blocchi di dati selezionati sono elencati nel pannello Filtri di modifica rapida . I filtri applicati a tutti i blocchi di dati nella selezione sono elencati sotto l&#39;intestazione **Applicato a tutti i blocchi di dati selezionati**. I filtri applicati ad alcuni blocchi di dati ma non a tutti sono elencati sotto l&#39;intestazione **Applicato a uno o più blocchi di dati selezionati** .

   Quando nei blocchi di dati selezionati sono presenti più filtri, puoi cercare filtri specifici utilizzando il campo di ricerca **Aggiungi filtro** .

   ![](./assets/add_filter.png)

1. Aggiungi i filtri selezionando i filtri dal menu a discesa **Aggiungi filtro** .

   L’elenco dei filtri ricercabili include tutti i filtri accessibili alle visualizzazioni dati presenti in uno o più blocchi di dati selezionati, nonché tutti i filtri disponibili a livello globale nell’organizzazione.

   L’aggiunta di un filtro applica il filtro a tutti i blocchi di dati nella selezione.

1. Per rimuovere i filtri, fai clic sull&#39;icona Elimina **x** a destra dei filtri nell&#39;elenco **Filtri applicati**.

1. Fai clic su **Applica** per salvare le modifiche e tornare al pannello hub.

   In Report Builder viene visualizzato un messaggio per confermare le modifiche al filtro applicato.

### Sostituire un filtro

Puoi sostituire un filtro esistente con un altro filtro per modificare il modo in cui i dati vengono filtrati.

1. Seleziona la scheda **Sostituisci** nel pannello Filtri di modifica rapida .

   ![](./assets/replace_filter.png)

1. Utilizza il campo di ricerca **Elenco di ricerca** per individuare filtri specifici.

1. Scegli uno o più filtri da sostituire.

1. Cerca uno o più filtri nel campo Sostituisci con .

   Selezionando un filtro, questo viene aggiunto all&#39;elenco **Sostituisci con**...

   ![](./assets/replace_screen_new.png)

1. Fai clic su **Applica**.

   Il Report Builder aggiorna l’elenco dei filtri per riflettere la sostituzione.
