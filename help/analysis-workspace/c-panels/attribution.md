---
title: Pannello Attribution
description: Come utilizzare e interpretare il pannello Attribution in Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 45%

---

# Pannello Attribution {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_attribution_button"
>title="Attribuzione"
>abstract="Confronta e visualizza rapidamente un numero qualsiasi di modelli di attribuzione utilizzando qualsiasi dimensione e metrica di conversione."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Pannello Attribution IQ"

>[!CONTEXTUALHELP]
>id="cja_workspace_attribution_panel"
>title="Pannello Attribution"
>abstract="Confronta e visualizza rapidamente più modelli di attribuzione utilizzando qualsiasi dimensione e metrica di conversione.<br/><br/>**Parametri **<br/>**Canale**<br/> La dimensione a cui attribuire. Questa dimensione può essere un canale di marketing, una campagna o qualsiasi altra dimensione.<br/>**Modelli**<br/> Il modello determina come viene assegnato il credito ai punti di contatto.<br/>**Intervallo di lookback**<br/> Questa impostazione determina la finestra di attribuzione dei dati che viene applicata a ogni conversione."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Pannello Attribution IQ"

<!-- markdownlint-enable MD034 -->


Il pannello **[!UICONTROL Attribution]** permette di strutturare facilmente un’analisi confrontando diversi modelli di attribuzione. Il pannello offre un’area di lavoro dedicata per utilizzare e confrontare modelli di attribuzione.

Customer Journey Analytics migliora l’attribuzione consentendo di:

* Definire l’attribuzione oltre i paid media: è possibile applicare ai modelli qualsiasi dimensione, metrica, canale o evento (ad esempio, ricerca interna), non solo le campagne di marketing.
* Utilizza confronto illimitato tra modelli di attribuzione: confronta dinamicamente tutti i modelli che desideri.
* Evitare le modifiche di implementazione: con l’elaborazione al momento del reporting e le sessioni in base al contesto, è possibile integrare e applicare il contesto di percorso del cliente in fase di esecuzione.
* Costruire la sessione che si adatta al meglio allo scenario di attribuzione.
* Suddividere l’attribuzione in base ai filtri: è possibile confrontare facilmente le prestazioni dei canali di marketing in qualsiasi filtro importante (ad esempio, clienti nuovi rispetto a clienti di ritorno, prodotto X rispetto a prodotto Y, livello di fedeltà rispetto a Customer Lifetime Value).
* Ispezionare l’analisi incrociata e a più contatti dei canali: è possibile utilizzare diagrammi di Venn, istogrammi e risultati di attribuzione di tendenze.
* Analizzare visivamente sequenze di marketing principali: è possibile esplorare in modo visivo i percorsi che hanno condotto alla conversione, con visualizzazioni di abbandono e di flusso a più nodi.
* Costruire metriche calcolate: è possibile utilizzare un qualsiasi numero di metodi di allocazione di attribuzione.

## Seleziona

Per utilizzare un pannello **[!UICONTROL Attribution]**:

1. Crea un pannello **[!UICONTROL Attribution]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Specifica [input](#panel-input) per il pannello.

1. Osserva [output](#panel-output) per il pannello.

### Input del pannello

Puoi configurare il pannello Attribuzione utilizzando le seguenti impostazioni di input:

1. Aggiungere **[!UICONTROL Success metric]** e una dimensione da **[!UICONTROL Channel]** a cui si desidera attribuire l&#39;attributo. Alcuni esempi includono Marketing Channels o dimensioni personalizzate, ad esempio promozioni interne.

   ![La finestra del pannello Attribuzione mostra diverse dimensioni e metriche selezionate.](assets/attribution-panel.png)

1. Selezionare uno o più [modelli di attribuzione](#attribution-models) da **[!UICONTROL Included models]** e un [intervallo di lookback](#lookback-window) da **[!UICONTROL Lookback window]** che si desidera utilizzare per il confronto.

1. Seleziona **[!UICONTROL Build]** per creare le visualizzazioni nel pannello.

### Output del pannello

Il pannello **[!UICONTROL Attribution]** restituisce un set completo di dati e visualizzazioni che confrontano l&#39;attribuzione per la dimensione e la metrica selezionate.

![Visualizzazioni del pannello Attribuzione che confrontano le metriche e le dimensioni selezionate.](assets/attr_panel_vizs.png)

### Visualizzazioni di Attribution

La visualizzazione seguente fa parte dell’output del pannello.

* **Metrica totale**: il numero totale di conversioni che si sono verificate nell&#39;intervallo di tempo di reporting e sono attribuite alla dimensione selezionata.
* **Barra di confronto attribuzione**: confronta visivamente le conversioni attribuite per ciascun elemento dimensionale dalla dimensione selezionata. Ogni colore della barra rappresenta un modello di attribuzione distinto.
* **Tabella di confronto attribuzione**: mostra gli stessi dati del grafico a barre, rappresentandoli sotto forma di tabella. Se si selezionano colonne o righe diverse in questa tabella, il grafico a barre e diverse altre visualizzazioni nel pannello vengono filtrate. Questa tabella funziona come qualsiasi altra tabella a forma libera in Workspace e consente di aggiungere componenti quali metriche, filtri o raggruppamenti.
* **Diagramma di sovrapposizione**: una visualizzazione di Venn che mostra i primi tre elementi dimensionali e la frequenza con cui partecipano congiuntamente a una conversione. Ad esempio, le dimensioni della sovrapposizione a bolla indicano quanto spesso si è verificata una conversione quando una persona è stata esposta a entrambi gli elementi dimensionali. Quando si selezionano altre righe nella tabella a forma libera adiacente, la visualizzazione si aggiorna in base alla selezione.
* **Dettagli delle prestazioni**: una visualizzazione a dispersione per confrontare visivamente fino a tre modelli di attribuzione.
* **Prestazioni con tendenze**: mostra la tendenza delle conversioni attribuite per l’elemento della dimensione superiore. Quando si selezionano altre righe nella tabella a forma libera adiacente, la visualizzazione si aggiorna in base alla selezione.
* **Flusso**: consente di vedere con quali canali si interagisce più comunemente e in quale ordine nel percorso di una persona.

## Modelli di attribuzione

{{attribution-models-details}}

## Intervallo di lookback

{{attribution-lookback-window}}

>[!MORELIKETHIS]
>
> [Crea un pannello](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
