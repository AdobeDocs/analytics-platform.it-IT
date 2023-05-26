---
description: Scopri
title: Tipo di metrica e attribuzione
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 5fbffb01c08b5f8069b2670742f7ae3836ad8357
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 10%

---

# Tipo di metrica e attribuzione

Selezionando l’icona a forma di ingranaggio accanto a una metrica puoi specificare il tipo di metrica e il modello di attribuzione.

## Tipi di metriche

Per specificare il tipo di metrica durante la creazione di una metrica calcolata:

1. Seleziona l’icona a forma di ingranaggio accanto alla metrica di cui desideri selezionare il tipo.

   ![](assets/cm_type_alloc.png)

1. Scegli tra le seguenti opzioni:

   | Tipi di metriche | Definizione |
   |---|---|
   | Standard | Queste metriche sono le stesse utilizzate in Standard [!DNL Analytics] reportistica. Se una formula è costituita da una singola metrica standard, visualizza dati identici alla sua controparte metrica non calcolata. Le metriche standard sono utili per creare metriche calcolate specifiche per ogni singola riga. Ad esempio: [Ordini] / [Visite] prende ordini per quella voce specifica e lo divide per il numero di visite per quella voce specifica. |
   | Totale complessivo | Utilizza il totale complessivo per il periodo di reporting in ogni voce di riga. Se una formula è costituita da una singola metrica Totale complessivo, per ogni riga viene visualizzato lo stesso numero Totale complessivo. Le metriche del totale complessivo sono utili per creare metriche calcolate che si confrontano con i dati totali del sito. Ad esempio: [Ordini] / [Visite totali] mostra la proporzione di ordini rispetto a TUTTE le visite al sito, non solo le visite alla voce specifica. |

## Attribution

Per informazioni sull’attribuzione in CJA, consulta [Impostazioni dei componenti di attribuzione](/help/data-views/component-settings/attribution.md).
