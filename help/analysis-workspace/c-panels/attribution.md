---
title: Pannello Attribuzione
description: Come utilizzare e interpretare il pannello di attribuzione in  Analysis Workspace.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 20%

---


# Pannello Attribuzione

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Il pannello Attribuzione permette di strutturare facilmente un’analisi confrontando diversi modelli di attribuzione. È una funzione in [Attribution IQ](../attribution/overview.md) che offre un’area di lavoro dedicata per utilizzare e confrontare i modelli di attribuzione.

## Creare un pannello di attribuzione

1. Fate clic sull’icona del pannello a sinistra.
1. Trascina il pannello Attribuzione nel progetto di Analysis Workspace.

   ![Nuovo pannello di attribuzione](assets/Attribution_Panel_1.png)

1. Aggiungi una metrica da attribuire e aggiungi qualsiasi dimensione da attribuire. Alcuni esempi includono Marketing Channels (Canali di marketing) o dimensioni personalizzate, ad esempio promozioni interne.

   ![Seleziona dimensione e metrica](assets/attribution_panel2.png)

1. Selezionate i modelli di [attribuzione e la finestra](../attribution/models.md) di lookback da confrontare.

1. Il pannello Attribuzione restituisce un set completo di dati e visualizzazioni che confrontano l’attribuzione per la dimensione e la metrica selezionata.

   ![Visualizzazioni di attribuzione](assets/attr_panel_vizs.png)

## Visualizzazioni di attribuzione

* **Metrica** totale: Il numero totale di conversioni che si sono verificate durante la finestra del tempo di reporting. Queste sono le conversioni attribuite lungo la dimensione selezionata.
* **Grafico** a barre Confronto Attribuzione metrica: Confronta visivamente le conversioni attribuite tra ciascun elemento della dimensione dalla dimensione selezionata. Ogni colore della barra rappresenta un modello di attribuzione distinto.
* **Tabella** a forma libera attribuzione metrica: Mostra gli stessi dati del grafico a barre, rappresentato come tabella. Se si selezionano colonne o righe diverse in questa tabella, il grafico a barre e diverse altre visualizzazioni nel pannello vengono filtrate. Questa tabella funziona come qualsiasi altra tabella a forma libera in Workspace e consente di aggiungere componenti quali metriche, segmenti o suddivisioni.
* **Grafico** di sovrapposizione dimensioni: Un diagramma di Venn che mostra i tre elementi principali e la frequenza con cui partecipano congiuntamente a una conversione. Ad esempio, la dimensione della sovrapposizione della bolla indica la frequenza con cui si sono verificate conversioni quando un visitatore era esposto a entrambi gli elementi dimensionali. Selezionando altre righe nella tabella a forma libera adiacente, la visualizzazione viene aggiornata per riflettere la selezione.
* **Punti di contatto marketing per viaggio**: Un istogramma che indica il numero di punti di contatto di un visitatore nella finestra di lookback. Questa visualizzazione è utile per vedere l’impatto dell’attribuzione a più contatti per un set di dati. Se quasi tutti i visitatori dispongono di un solo punto di contatto, è probabile che i diversi modelli di attribuzione mostrino dati simili.
* **Dettagli** sulle prestazioni del canale di marketing: Consente di confrontare visivamente fino a tre modelli di attribuzione utilizzando un grafico a dispersione.
* **Flusso** canale marketing: Consente di vedere con quali canali si interagisce più comunemente, e in quale ordine nel percorso di un visitatore.
