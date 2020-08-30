---
title: Pannello Attribution
description: Come utilizzare e interpretare il pannello Attribution in Analysis Workspace.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 84%

---


# Pannello Attribution

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Il pannello Attribution permette di strutturare facilmente un’analisi confrontando diversi modelli di attribuzione. È una funzione in [Attribution IQ](../attribution/overview.md) che offre un’area di lavoro dedicata per utilizzare e confrontare modelli di attribuzione.

## Creare un pannello di attribuzione

1. Fai clic sull’icona del pannello a sinistra.
1. Trascina il pannello Attribution nel progetto di Analysis Workspace.

   ![Nuovo pannello di attribuzione](assets/Attribution_Panel_1.png)

1. Aggiungi una metrica che desideri attribuire e aggiungi qualsiasi dimensione secondo cui effettuare l’attribuzione. Alcuni esempi includono Marketing Channels o dimensioni personalizzate, ad esempio promozioni interne.

   ![Seleziona dimensione e metrica](assets/attribution_panel2.png)

1. Seleziona i [modelli di attribuzione e l’intervallo di lookback](../attribution/models.md) che desideri confrontare.

1. Il pannello Attribution restituisce un set completo di dati e visualizzazioni che confrontano l’attribuzione per la dimensione e la metrica selezionate.

   ![Visualizzazioni di Attribution](assets/attr_panel_vizs.png)

## Visualizzazioni di Attribution

* **Metrica totale**: il numero totale di conversioni che si sono verificate nell’intervallo di tempo di reporting. Queste sono le conversioni attribuite nella dimensione selezionata.
* **Grafico a barre di confronto attribuzione metriche**: confronta visivamente le conversioni attribuite in ciascun elemento dimensionale dalla dimensione selezionata. Ogni colore della barra rappresenta un modello di attribuzione distinto.
* **Tabella a forma libera di attribuzione metriche**: mostra gli stessi dati del grafico a barre rappresentati in una tabella. Se si selezionano colonne o righe diverse in questa tabella, il grafico a barre e diverse altre visualizzazioni nel pannello vengono filtrate. Questa tabella funziona come qualsiasi altra tabella a forma libera in Workspace e consente di aggiungere componenti quali metriche, segmenti o suddivisioni.
* **Grafico di sovrapposizione Dimension**: Un diagramma di Venn che mostra i tre elementi principali e la frequenza con cui partecipano congiuntamente a una conversione. Ad esempio, la dimensione della sovrapposizione della bolla indica la frequenza con cui si sono verificate conversioni quando un visitatore era esposto a entrambi gli elementi dimensionali. Quando si selezionano altre righe nella tabella a forma libera adiacente, la visualizzazione si aggiorna in base alla selezione.
* **Marketing Touchpoints Per Journey**: un istogramma che indica il numero di punti di contatto di un visitatore nell’intervallo di lookback. Questa visualizzazione è utile per vedere l’impatto dell’attribuzione a più contatti per un set di dati. Se quasi tutti i visitatori dispongono di un solo punto di contatto, è probabile che i diversi modelli di attribuzione mostrino dati simili.
* **Dettagli delle prestazioni dei canali di marketing**: ti consente di confrontare visivamente fino a tre modelli di attribuzione mediante un grafico a dispersione.
* **Flusso dei canali di marketing**: ti consente di vedere con quali canali si verificano più comunemente interazioni e in quale ordine lungo il percorso di un visitatore.
