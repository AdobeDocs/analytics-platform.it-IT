---
description: 'null'
title: Numero di riepilogo e Variazione di riepilogo
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 92%

---


# Numero di riepilogo e Variazione di riepilogo

>[!NOTE] Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

## Visualizzazione Numero di riepilogo

* Se non è selezionata alcuna cella, viene selezionato il totale della colonna.
* Se è selezionata una cella, viene visualizzato il riepilogo per tale cella.
* Se sono selezionate più celle, viene visualizzata la prima cella selezionata.
* Se è selezionata la colonna, viene preso il valore della prima cella della colonna.

![](assets/summary-number.png)

## Visualizzazione Variazione di riepilogo

* Se non è selezionata alcuna cella, vengono confrontati i valori delle prime due celle della colonna.
* Se è selezionata una cella, viene riportato 0 perché il valore della cella viene confrontato con se stesso e quindi non si verifica alcuna variazione nei valori.
* Se sono selezionate due celle, la prima cella selezionata funge da numeratore e la seconda da denominatore.
* Se sono selezionate più celle, per il confronto vengono considerate solo le prime due celle.
* Se è selezionato un intervallo di celle, vengono confrontate la prima e l’ultima cella selezionata nell’intervallo.
* Se è selezionata la colonna, il primo valore viene confrontato con se stesso, e la variazione risulta quindi pari a 0.
* È possibile controllare il colore verde e rosso della variazione di riepilogo tramite:
   * [Polarità di un evento personalizzato](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-tools/success-events/success-event.html).
   * Opzione [Show Upward Trend As](https://docs.adobe.com/content/help/it-IT/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) (Mostra tendenza ascendente come) per una metrica calcolata.

## Impostazioni di Variazione di riepilogo {#section_2581AC0107634FB4990AB8347E5897AA}

Fai clic sull’icona dell’ingranaggio accanto alla visualizzazione per configurare le impostazioni Riepilogo:

| Impostazione | Definizione |
|--- |--- |
| Percentuali | Usa le percentuali invece dei numeri. |
| Visualizzazione legenda | Mostra le metriche utilizzate. |
| Opzioni di Numero di riepilogo: Abbrevia valore | Puoi scegliere da 0 a 3 cifre decimali per i valori abbreviati. |
| Opzioni Variazione di riepilogo: Mostra variazione percentuale | Mostra la variazione tra 2 numeri, espressa in percentuale. |
| Opzioni Variazione di riepilogo: Mostra differenza raw | Mostra la differenza grezza tra 2 numeri. |
