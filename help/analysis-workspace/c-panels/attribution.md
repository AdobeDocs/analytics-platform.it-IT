---
title: Pannello Attribution
description: Scopri come utilizzare e interpretare il pannello Attribuzione in Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 94%

---

# Pannello Attribuzione {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_attribution_button"
>title="Attribution"
>abstract="Confronta e visualizza rapidamente un numero qualsiasi di modelli di attribuzione utilizzando una metrica di successo, un canale e un intervallo di lookback."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Pannello Attribution IQ"

>[!CONTEXTUALHELP]
>id="workspace_attribution_panel"
>title="Pannello Attribuzione"
>abstract="Confronta e visualizza rapidamente un numero qualsiasi di modelli di attribuzione per una metrica di successo. Seleziona il canale (dimensione), i modelli da includere e l’intervallo di lookback."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Pannello Attribution IQ"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Questo articolo descrive il pannello Attribuzione in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_.<br/>_Consulta il [pannello Attribuzione](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/panels/attribution) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]

Il pannello **[!UICONTROL Attribution]** permette di strutturare facilmente un’analisi confrontando diversi modelli di attribuzione. Il pannello offre un’area di lavoro dedicata per utilizzare e confrontare modelli di attribuzione.

Customer Journey Analytics migliora l’attribuzione consentendo di:

* Definisci l’attribuzione oltre ai paid media: è possibile applicare ai modelli qualsiasi dimensione, metrica, canale o evento (ad esempio, ricerca interna), non solo le campagne di marketing.
* Utilizza il confronto illimitato tra modelli di attribuzione: è possibile confrontare in modo dinamico tanti modelli quanti se ne desiderano.
* Evita le modifiche di implementazione: con l’elaborazione al momento del rapporto e le sessioni in base al contesto, è possibile integrare e applicare il contesto di Costumer Journey in fase di esecuzione.
* Costruire la sessione che si adatta al meglio allo scenario di attribuzione.
* Suddividere l’attribuzione in base ai segmenti: è possibile confrontare facilmente le prestazioni dei canali di marketing in qualsiasi segmento importante (ad es. clienti nuovi rispetto a clienti di ritorno, prodotto X rispetto a prodotto Y, livello di fedeltà rispetto a Customer Lifetime Value).
* Ispezionare l’analisi incrociata e a più contatti dei canali: è possibile utilizzare diagrammi di Venn, istogrammi e risultati di attribuzione di tendenze.
* Analizzare visivamente sequenze di marketing principali: è possibile esplorare in modo visivo i percorsi che hanno condotto alla conversione, con visualizzazioni di abbandono e di flusso a più nodi.
* Costruire metriche calcolate: è possibile utilizzare un qualsiasi numero di metodi di allocazione di attribuzione.

## Utilizzo

Per usare un pannello **[!UICONTROL Attribution]**:

1. Crea un pannello **[!UICONTROL Attribution]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.

### Input del pannello

Puoi configurare il pannello Attribuzione utilizzando le seguenti impostazioni di input:

1. Aggiungi **[!UICONTROL Success metric]** e una dimensione da **[!UICONTROL Channel]** per l’attribuzione. Alcuni esempi includono Marketing Channels o dimensioni personalizzate, ad esempio promozioni interne.

   ![La finestra del pannello Attribuzione mostra diverse dimensioni e metriche selezionate.](assets/attribution-panel.png)

1. Selezionare uno o più [modelli di attribuzione](#attribution-models) da **[!UICONTROL Included models]**, il [contenitore](#container) da **[!UICONTROL Container]** e un [intervallo di lookback](#lookback-window) da **[!UICONTROL Lookback window]** che si desidera utilizzare per il confronto.

1. Seleziona **[!UICONTROL Build]** per creare le visualizzazioni nel pannello.

### Output del pannello

Il pannello **[!UICONTROL Attribution]** restituisce un set completo di dati e visualizzazioni che confrontano l’attribuzione per la dimensione e la metrica selezionate.

![Visualizzazioni del pannello Attribuzione che confrontano le metriche e le dimensioni selezionate.](assets/attr_panel_vizs.png)

### Visualizzazioni di Attribution

La visualizzazione seguente fa parte dell’output del pannello.

* **Metrica totale**: numero totale di conversioni che si sono verificate nell&#39;intervallo di tempo di reporting e sono attribuite alla dimensione selezionata.
* **Barra di confronto attribuzione**: confronta visivamente le conversioni attribuite per ciascun elemento dimensionale dalla dimensione selezionata. Ogni colore della barra rappresenta un modello di attribuzione distinto.
* **Tabella di confronto attribuzione**: mostra gli stessi dati del grafico a barre, rappresentandoli sotto forma di tabella. La selezione di colonne o righe diverse in questa tabella segmenta il grafico a barre e diverse altre visualizzazioni nel pannello. Questa tabella funziona come qualsiasi altra tabella a forma libera in Workspace e consente di aggiungere componenti quali metriche, segmenti o raggruppamenti.
* **Diagramma di sovrapposizione**: una visualizzazione di Venn che mostra i principali tre elementi dimensionali e la frequenza con cui partecipano congiuntamente a una conversione. Ad esempio, le dimensioni della sovrapposizione a bolla indicano quanto spesso si è verificata una conversione quando una persona è stata esposta a entrambi gli elementi dimensionali. Quando si selezionano altre righe nella tabella a forma libera adiacente, la visualizzazione viene aggiornata per riflettere la selezione.
* **Dettagli delle prestazioni**: una visualizzazione a dispersione per confrontare visivamente fino a tre modelli di attribuzione.
* **Prestazioni con tendenze**: mostra la tendenza delle conversioni attribuite per l’elemento della dimensione superiore. Quando si selezionano altre righe nella tabella a forma libera adiacente, la visualizzazione viene aggiornata per riflettere la selezione.
* **Flusso**: consente di visualizzare con quali canali si interagisce più comunemente e in quale ordine nel percorso di una persona.

## Modello di attribuzione

{{attribution-models-details}}

## Contenitore

{{attribution-container}}

## Intervallo di lookback

{{attribution-lookback-window}}

## Esempio

{{attribution-example}}

>[!MORELIKETHIS]
>
> [Creare un pannello](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
