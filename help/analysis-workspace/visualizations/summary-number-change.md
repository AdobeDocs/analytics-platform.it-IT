---
description: Utilizzate le visualizzazioni Summary Number (Numero riepilogo) e Change (Modifica) per visualizzare punti dati importanti in un progetto.
title: Numero di riepilogo e Variazione di riepilogo
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: 158c9da54f7d5dcdd0cca6223b5d4833df53abb7
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 49%

---


# Numero di riepilogo e Variazione di riepilogo

## Visualizzazione Numero di riepilogo {#summary-number}

Utilizzate la visualizzazione Summary Number (Numero riepilogo) per evidenziare un numero elevato che è importante in un progetto. Questa visualizzazione si comporta come segue:

* Se non è selezionata alcuna cella, viene selezionato il totale della colonna.
* Se è selezionata una cella, viene visualizzato il riepilogo per tale cella.
* Se sono selezionate più celle, viene visualizzata la prima cella selezionata.
* Se è selezionata la colonna, viene preso il valore della prima cella della colonna.

Fai clic sul pulsante **Impostazioni di visualizzazione** ingranaggio in alto a destra per configurare le impostazioni Summary Number (Numero riepilogo):

| Impostazione | Definizione |
|--- |--- |
| Percentuali | Visualizza le percentuali invece dei numeri non elaborati. |
| Legenda visibile | Visualizza informazioni sulla metrica visualizzata. |
| Abbreviazione del valore | Scegliere di ridurre i valori e visualizzare fino a 3 posizioni decimali. |
| Riepiloga valore per | Scegliere di visualizzare il massimo, il minimo, la media, la media o la somma per una selezione di dati. |

## Visualizzazione Variazione di riepilogo {#summary-change}

Utilizzate la visualizzazione Modifica riepilogo per visualizzare il delta (modifica) tra due numeri. Il colore verde e rosso della Modifica di riepilogo può essere controllato attraverso [polarità evento personalizzata](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-tools/success-events/success-event.html) o di una metrica calcolata [Mostra tendenza verso l&#39;alto come](https://docs.adobe.com/content/help/it-IT/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) opzione.

Questa visualizzazione si comporta come segue:

* Se non è selezionata alcuna cella, vengono confrontati i valori delle prime due celle della colonna.
* Se è selezionata una cella, viene riportato 0 perché il valore della cella viene confrontato con se stesso e quindi non si verifica alcuna variazione nei valori.
* Se sono selezionate due celle, la prima cella selezionata funge da numeratore e la seconda da denominatore.
* Se sono selezionate più celle, per il confronto vengono considerate solo le prime due celle.
* Se è selezionato un intervallo di celle, vengono confrontate la prima e l’ultima cella selezionata nell’intervallo.
* Se è selezionata la colonna, il primo valore viene confrontato con se stesso, e la variazione risulta quindi pari a 0.

Fai clic sul pulsante **Impostazioni di visualizzazione** ingrandisci in alto a destra per configurare le impostazioni Summary Change (Modifica riepilogo):

| Impostazione | Definizione |
|--- |--- |
| Percentuali | Visualizza le percentuali invece dei numeri non elaborati. |
| Legenda visibile | Visualizza informazioni sulla metrica visualizzata. |
| Mostra variazione percentuale | Mostra la variazione percentuale tra i 2 numeri. |
| Mostra differenza raw | Mostra la differenza grezza tra 2 numeri. Con questa opzione è inoltre possibile abbreviare i valori e visualizzare fino a 3 posizioni decimali. |
