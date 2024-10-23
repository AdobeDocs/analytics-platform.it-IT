---
description: È possibile suddividere dimensioni ed elementi dimensionali in Analysis Workspace.
keywords: Analysis Workspace
title: Suddividere dimensioni
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
role: User
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 56%

---

# Suddividere dimensioni in Workspace

Puoi suddividere i dati in modalità illimitata in base alle tue esigenze specifiche; puoi creare query utilizzando metriche, dimensioni, filtri, linee temporali e altri valori rilevanti di analisi stratificata.

1. In una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) selezionare **[!UICONTROL Breakdown]** ![ChevronRight](/help/assets/icons/ChevronRight.svg) dal menu di scelta rapida di una o più righe selezionate.

   ![Risultato passaggio che mostra l&#39;avviso di creazione dalla selezione selezionata.](assets/breakdown.png)

1. Dal sottomenu selezionare **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]**, **[!UICONTROL Filters]** o **[!UICONTROL Date ranges]** e quindi selezionare un elemento.

Puoi analizzare metriche per elementi dimensionali o filtri di pubblico in diversi periodi di tempo selezionati. Puoi anche effettuare analisi molto più dettagliate.

>[!NOTE]
>
>È possibile mostrare nella tabella un massimo di 200 raggruppamenti. Questo limite aumenta per l’esportazione di raggruppamenti.

## Raggruppamento per posizione

Per impostazione predefinita, le suddivisioni sono fissate a elementi di riga statici. Ad esempio, immagina di suddividere i primi 3 elementi dimensionali di pagina (Home page, Risultati ricerca, Pagamento) per canale di marketing. Poi abbandoni il progetto per due settimane. Quando lo riapri, le prime 3 pagine sono cambiate e ora Home page, Risultati ricerca e Pagamento sono le prime 4-6 pagine. Per impostazione predefinita, i raggruppamenti per canale di marketing vengono ancora visualizzati in Home page, Risultati ricerca e Pagamento, anche se ora si trovano nelle righe 4-6.

Al contrario, **Raggruppamento per posizione**, raggruppa sempre i primi 3 elementi, indipendentemente da quali siano. Facendo riferimento all’esempio, quando riapri il progetto, i raggruppamenti per canale di marketing sono legati alle prime 3 pagine della tabella. E non alla homepage, ai risultati della ricerca e al checkout, che ora si trovano nelle righe 4-6. Consulta [Impostazioni riga](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md) per informazioni su come configurare questa impostazione.



## Applicare modelli di attribuzione ai raggruppamenti

A qualsiasi raggruppamento all’interno di una tabella può essere applicato anche qualsiasi modello di attribuzione. Tale modello di attribuzione può essere lo stesso o diverso dalla colonna principale. Ad esempio, puoi analizzare gli ordini lineari sulla dimensione canali di marketing, ma applicare ordini a forma di U agli specifici codici di tracciamento all’interno di un canale. Per modificare il modello di attribuzione applicato a un raggruppamento, passa il cursore sul modello di raggruppamento e seleziona **[!UICONTROL Edit]**.

![Confronto attributi ordine con le impostazioni di raggruppamento](assets/breakdown-attribution.png)

Questo è il comportamento previsto quando si applicano modelli di attribuzione ai raggruppamenti o quando questi vengono modificati:

* Se applichi un’attribuzione quando non esistono altre attribuzioni, questa si applica all’intera struttura ad albero della colonna.

* Se aggiungi un raggruppamento dopo aver applicato un’attribuzione, utilizzerà l’impostazione predefinita per il raggruppamento specificato che è stato aggiunto (se tale dimensione ha un valore predefinito). In caso contrario, utilizzerà il raggruppamento dalla colonna padre. Alcune dimensioni hanno un’allocazione predefinita. Ad esempio, le dimensioni di Tempo e Referrer utilizzano Same Touch (Stesso contatto). La dimensione Prodotto utilizza Last Touch (Ultimo contatto). Altre dimensioni non hanno un valore predefinito e utilizzeranno l’allocazione della colonna padre.

* Se la struttura ad albero della colonna contiene già delle attribuzioni, la modifica dell’attribuzione ha effetto solo su quella che si sta modificando.

+++ Video che illustrano le dimensioni e le suddivisioni delle dimensioni

Dimension in Analysis Workspace

>[!VIDEO](https://video.tv.adobe.com/v/23971)

Raggruppamenti per Dimension

>[!VIDEO](https://video.tv.adobe.com/v/23969)

Aggiungere dimensioni e metriche al progetto in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/30606)

Utilizzo delle dimensioni nelle tabelle a forma libera:

>[!VIDEO](https://video.tv.adobe.com/v/40179)

Raggruppamenti delle dimensioni per posizione:

>[!VIDEO](https://video.tv.adobe.com/v/24033)

{{videoaa}}

+++
