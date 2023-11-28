---
description: Scopri
title: Tipo di metrica e attribuzione
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 9%

---

# Tipo di metrica e attribuzione

Selezionando l’icona a forma di ingranaggio accanto a una metrica puoi specificare il tipo di metrica e il modello di attribuzione.

## Tipi di metriche

Per specificare il tipo di metrica durante la creazione di una metrica calcolata:

1. Seleziona l’icona a forma di ingranaggio accanto alla metrica di cui desideri selezionare il tipo.

   ![Icona dell’ingranaggio con finestra a comparsa che mostra il tipo di metrica uguale a Standard.](assets/cm_type_alloc.png)

1. Scegli tra le seguenti opzioni:

   | Tipi di metriche | Definizione |
   |---|---|
   | Standard | Queste metriche sono le stesse utilizzate in Standard [!DNL Analytics] reportistica. Se una formula è costituita da una singola metrica standard, visualizza dati identici alla sua controparte metrica non calcolata. Le metriche standard sono utili per creare metriche calcolate specifiche per ogni singola riga. Ad esempio: [Ordini] / [Sessioni] prende gli ordini per quella voce specifica e li divide per il numero di sessioni per quella voce specifica. |
   | Totale complessivo | Utilizza il totale complessivo per il periodo di reporting in ogni voce di riga. Se una formula è costituita da una singola metrica Totale complessivo, per ogni riga viene visualizzato lo stesso numero Totale complessivo. Le metriche del totale complessivo sono utili per creare metriche calcolate che si confrontano con i dati totali. Ad esempio: [Ordini] / [Sessioni totali] mostra la proporzione di ordini rispetto a TUTTE le sessioni su un canale, non solo le sessioni rispetto alla riga specifica. |

## Attribuzione

Per informazioni sull’attribuzione nel Customer Journey Analytics, consulta [Impostazioni dei componenti di attribuzione](/help/data-views/component-settings/attribution.md).
