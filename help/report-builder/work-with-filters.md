---
title: Utilizzare I Segmenti In Report Builder
description: Scopri come utilizzare i segmenti in Report Builder.
role: User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
source-git-commit: 31d3b40ad7a081aefa4297d7f4a3b986711ead03
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 2%

---

# Utilizzare i segmenti

Puoi applicare segmenti quando crei un nuovo blocco di dati o quando selezioni **[!UICONTROL Modifica blocco di dati]** dal pannello **[!UICONTROL Comandi]**.

## Applicare segmenti a un blocco di dati

Per applicare un segmento all’intero blocco di dati, seleziona due volte un segmento o trascina i segmenti dall’elenco dei componenti nella sezione dei segmenti della tabella.

## Applicare filtri alle singole metriche

Per applicare filtri che utilizzano i segmenti a singole metriche:

* Trascina uno o più segmenti da **[!UICONTROL Segmenti]** in una metrica della tabella.

* In alternativa:

   1. Selezionare ![AltroPiccolo](/help/assets/icons/MoreSmall.svg) per una metrica specifica nel riquadro **[!UICONTROL Tabella]**, quindi selezionare **[!UICONTROL Filtra metrica]**.

      Scheda ![segmenti con metriche.](./assets/filter-metric.png){zoomable="yes"}

   1. Seleziona uno o più segmenti dal menu a discesa **[!UICONTROL Segmenti]**. I segmenti vengono aggiunti all&#39;elenco **[!UICONTROL Segmenti applicati]**.

      ![Segmenti applicati](assets/segments-applied.png)
   1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un segmento dall&#39;elenco **[!UICONTROL Segmento applicato]**. In alternativa, selezionare **[!UICONTROL Cancella tutto]** per rimuovere tutti i segmenti dall&#39;elenco **[!UICONTROL Segmento applicato]**.
   1. Seleziona **[!UICONTROL Applica]**.

Per visualizzare i filtri applicati, passa il cursore del mouse su una metrica o selezionala nel riquadro Tabella. Le metriche con segmenti applicati visualizzano un’icona di segmento.


## Modifica rapida segmenti

Puoi utilizzare il pannello **[!UICONTROL Modifica rapida]** per aggiungere, rimuovere o sostituire segmenti per blocchi di dati esistenti.

Quando selezioni un intervallo di celle nel foglio di calcolo, il collegamento **[!UICONTROL Segmenti]** nel pannello **[!UICONTROL Modifica rapida]** visualizza un elenco di riepilogo dei segmenti utilizzati dai blocchi di dati nella selezione.

Per modificare i segmenti utilizzando il pannello **[!UICONTROL Modifica rapida]**:

1. Seleziona un intervallo di celle da uno o più blocchi di dati.

1. Seleziona il collegamento **[!UICONTROL Segmenti]** per avviare il pannello **[!UICONTROL Modifica rapida]** **[!UICONTROL Segmenti]**.


### Aggiungere o rimuovere segmenti

Puoi aggiungere o rimuovere segmenti utilizzando le opzioni Aggiungi/Rimuovi.

1. Seleziona la scheda **[!UICONTROL Aggiungi/Rimuovi]** nel pannello **[!UICONTROL Modifica rapida]** **[!UICONTROL Segmenti]**.


   1. Seleziona uno o più segmenti dal menu a discesa **[!UICONTROL Segmenti]**. I segmenti vengono aggiunti all&#39;elenco **[!UICONTROL Segmenti applicati]**.
   1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un segmento dall&#39;elenco **[!UICONTROL Segmento applicato]**.
   1. Seleziona **[!UICONTROL Applica]**.

In Report Builder viene visualizzato un messaggio per confermare le modifiche al segmento applicato.

### Sostituire i segmenti

Puoi sostituire un segmento esistente con un altro segmento per modificare la modalità di segmentazione dei dati.

1. Seleziona la scheda **[!UICONTROL Sostituisci]** nel pannello **[!UICONTROL Modifica rapida]** **[!UICONTROL Segmenti]**.

1. Utilizza il campo di ricerca **Elenco di ricerca** per individuare segmenti specifici.

1. Seleziona uno o più segmenti da sostituire.

1. Cerca uno o più segmenti dal menu a discesa Sostituisci con per aggiungere il segmento all&#39;elenco **[!UICONTROL Sostituisci con]**.

1. Seleziona **[!UICONTROL Applica]**.

Report Builder aggiorna l’elenco dei segmenti in base alla sostituzione.

## Definire i segmenti dei blocchi di dati dalla cella

I blocchi di dati possono fare riferimento a segmenti da una cella. Più blocchi di dati possono fare riferimento alla stessa cella per i segmenti, consentendo di cambiare facilmente i segmenti per più blocchi di dati alla volta.

Per applicare segmenti da una cella:

1. [Creare un nuovo blocco di dati](create-a-data-block.md#create-a-data-block) o modificare un blocco di dati esistente.
1. Seleziona la scheda **[!UICONTROL Segmenti]** per definire i segmenti.
1. Selezionare ![DataViewSelector](/help/assets/icons/DataViewSelector.svg).

   ![Seleziona segmento dalla cella](assets/select-segment-from-cell.png){zoomable="yes"}

1. Seleziona la cella da cui desideri che i blocchi di dati facciano riferimento a un segmento.

1. Fai doppio clic su per aggiungere un segmento alla cella. In alternativa, trascina uno o più segmenti nella sezione **[!UICONTROL Segmenti inclusi]**.

1. Selezionare **[!UICONTROL Applica]** per creare la cella di riferimento.

1. Dalla scheda **Segmenti**, aggiungi il segmento della cella di riferimento appena creato al blocco di dati.

   Scheda ![segmenti che mostra il segmento Sheet1!J1(All Data) aggiunto alla tabella.](assets/segment-from-cell-applied.png){zoomable="yes"}

1. Seleziona **[!UICONTROL Fine]**.

Per applicare la cella di riferimento come segmento ad altri blocchi di dati, utilizzare il riferimento di cella come uno dei segmenti nell&#39;elenco **[!UICONTROL Segmenti]** nella scheda **[!UICONTROL Tabella]**.

### Utilizzare una cella di riferimento per modificare i segmenti dei blocchi di dati

1. Selezionare la cella di riferimento nel foglio di calcolo.

1. Selezionare il collegamento in **[!UICONTROL Segmenti dalla cella]** nel menu **[!UICONTROL Modifica rapida]**.

   ![segmenti dal collegamento di cella che mostra Sheet1!J1 (Tutti i dati)](assets/select-segment-from-cell-in-sheet.png){zoomable="yes"}

1. Seleziona il segmento dal menu a discesa.

1. Seleziona **[!UICONTROL Applica]**.
