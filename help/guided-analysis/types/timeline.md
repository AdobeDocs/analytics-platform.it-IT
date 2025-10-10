---
title: Analisi della timeline
description: Osserva gli eventi di sessione a livello di utente nel tempo per trovare pattern di esperienza.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 100%

---

# [!UICONTROL Timeline] analisi {#timeline}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_timeline_button"
>title="Timeline"
>abstract="Osserva gli eventi della sessione a livello di utente nel tempo."

<!-- markdownlint-enable MD034 -->

L’analisi della ![Timeline](/help/assets/icons/Timeline.svg) **[!UICONTROL Timeline]** ti consente di osservare gli eventi della sessione a livello di utente nel tempo per trovare pattern di esperienza e creare presentazioni di utenti migliori. La barra a sinistra ti consente di filtrare il flusso per valori di proprietà e segmenti. La barra a destra ti consente di selezionare da un elenco randomizzato di utenti che corrispondono ai criteri di filtro. L’area centrale mostra il flusso dell’utente selezionato per sessione, costituito da marca temporale, valori di proprietà e durata. La durata non è disponibile per l’ultimo evento di una determinata sessione.


>[!NOTE]
>
>L’analisi [!UICONTROL Timeline] richiede che il componente standard **[!UICONTROL Person ID]** sia disponibile nella [visualizzazione dati](/help/data-views/component-reference.md#optional). L’inclusione dell’ID persona in una visualizzazione dati viene gestita dall’amministratore di Customer Journey Analytics, consentendo all’organizzazione di controllare completamente la privacy degli utenti che possono accedere a tali dati.
>><br/>Se a una visualizzazione dati non è stato aggiunto il componente [!UICONTROL Person ID], viene visualizzato il seguente messaggio:
>
>* **Amministratori**: *per questa analisi è necessaria la proprietà PersonID. Aggiungi l’ID persona alla visualizzazione dati.*
>* **Non amministratori**: *per questa analisi è necessaria la proprietà PersonID. Collabora con l’amministratore di Customer Journey Analytics per aggiungere l’ID persona alla visualizzazione dati.*

>[!VIDEO](https://video.tv.adobe.com/v/3435775/?quality=12&learn=on&captions=ita)



## Casi d’uso

I casi d’uso per questa analisi includono:

* **Esplorazione attrito**: se nell’analisi [Analisi funnel](funnel.md) riscontri un calo significativo, puoi creare un segmento di tali utenti e applicarlo in questa analisi per indagare le possibili cause.
* **Comportamento errore**: se gli utenti riscontrano un errore di prodotto, puoi esplorare le operazioni eseguite dagli utenti prima o dopo la visualizzazione dell’errore.
* **Convalida raccolta dati**: gli amministratori dei dati possono filtrare questa analisi sul proprio ID persona per verificare che l’implementazione della propria organizzazione funzioni come previsto.

## Interfaccia

Per una panoramica dell’interfaccia dell’analisi guidata, consulta [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Dimension]**: dimensione per la quale visualizzare i valori in streaming. Il flusso al centro mostra i valori per la dimensione selezionata. Puoi anche applicare filtri per restringere il flusso a dati più pertinenti. Gli operatori validi per il filtro includono [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Starts with], [!UICONTROL Ends with], [!UICONTROL Contains], [!UICONTROL Does not contain], [!UICONTROL Exists] e [!UICONTROL Does not exist].
* **[!UICONTROL Segments]**: i segmenti che desideri analizzare. Il segmento selezionato filtra i dati in modo da concentrarti solo sui singoli utenti che corrispondono ai criteri del segmento. Se desideri limitare l’analisi a un ID persona specifico, puoi filtrarla per questo ID persona nel pannello a destra. Per questa analisi è supportato un segmento.

### Impostazioni del grafico

L’analisi della [!UICONTROL Timeline] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu posizionato sopra di esso:

* **[!UICONTROL Show as]**: mostra i valori di proprietà desiderati.
   * [!UICONTROL Show all]: mostra tutti i valori di proprietà in una sessione.
   * [!UICONTROL Highlight]: evidenzia visivamente i valori di proprietà in una sessione che corrispondono ai filtri della query.
   * [!UICONTROL View only]: mostra solo i valori di proprietà in una sessione che corrispondono ai filtri della query.

### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è costituita da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati sulle tendenze. Questa impostazione non influisce sull’analisi senza tendenze, ad esempio Timeline.
* **[!UICONTROL Date]**: la data di inizio e di fine. Per comodità, sono disponibili intervalli di date continui predefiniti e intervalli personalizzati salvati in precedenza; in alternativa, puoi utilizzare il selettore del calendario per scegliere un intervallo di date fisso.


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
