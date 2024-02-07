---
title: Vista Timeline
description: Esplora i pattern nell’attività della sessione.
feature: Guided Analysis
keywords: analisi dei prodotti
role: User
source-git-commit: 5cd54973b08285badbedce273ac28371158f194c
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 1%

---

# [!UICONTROL Timeline] visualizza

Il **[!UICONTROL Timeline]** La vista consente di analizzare singole sessioni per determinare i pattern di comportamento. La barra a destra consente di selezionare un ID persona da analizzare. L’area centrale mostra l’ora, il valore della proprietà e la durata della persona.

Questa analisi richiede l’aggiunta di **[!UICONTROL Person ID]** componente standard per [visualizzazione dati](/help/data-views/component-reference.md#optional). Se non si dispone di [!UICONTROL Person ID] componente aggiunto alla visualizzazione dati, viene visualizzato il seguente messaggio:

> La proprietà PersonID è obbligatoria per questa analisi. Aggiungi PersonID alla visualizzazione dati.

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Esplorazione dell’attrito**: se trovi una goccia profonda nella [Attrito](friction.md) , è possibile analizzare le possibili cause di tale calo utilizzando questa visualizzazione.
* **Comportamento di errore**: se gli utenti rilevano un errore nel prodotto, puoi scoprire cosa fanno gli utenti prima o dopo aver visualizzato tale errore.
* **Convalida della raccolta dati**: gli amministratori dei dati possono filtrare questa vista per isolarsi. Questa vista offre un modo efficace per garantire che l’implementazione dell’organizzazione funzioni come previsto.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Property]**: proprietà per la quale visualizzare i valori. L’analisi della sessione al centro mostra i valori per la proprietà selezionata qui. Puoi anche filtrare i dati in base alla proprietà selezionata. Gli operatori validi per il filtro includono [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Starts with], [!UICONTROL Ends with], [!UICONTROL Contains], [!UICONTROL Does not contain], [!UICONTROL Exists], e [!UICONTROL Does not exist].
* **[!UICONTROL Segments]**: il segmento che desideri misurare. Il segmento selezionato filtra i dati in modo da concentrarti solo sui singoli utenti che corrispondono ai criteri del segmento. Per questa visualizzazione è supportato un segmento.

## Impostazioni grafico

Il [!UICONTROL Timeline] visualizza offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Show as]**: mostra i valori di proprietà desiderati.
   * [!UICONTROL Show all]
   * [!UICONTROL Highlight]
   * [!UICONTROL View only]

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati sulle tendenze. Questa impostazione non influisce sulle visualizzazioni senza tendenze, ad esempio Frequenza.
* **[!UICONTROL Date]**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.
