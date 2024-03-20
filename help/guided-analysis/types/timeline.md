---
title: Vista Timeline
description: Osserva gli eventi di sessione a livello di utente nel tempo per trovare modelli di esperienza.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: e9721eaf993175dd46e9d8edf9176d7c00308e8c
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 1%

---

# [!UICONTROL Timeline] visualizza

Il **[!UICONTROL Timeline]** La visualizzazione ti consente di osservare gli eventi delle sessioni a livello di utente nel tempo, trovare modelli di esperienza e raccontare storie di utenti migliori. La barra a sinistra ti consente di filtrare il flusso per valori di proprietà e segmenti. La barra a destra consente di selezionare da un elenco randomizzato di utenti che corrispondono ai criteri del filtro. L&#39;area centrale mostra il flusso per l&#39;utente selezionato per sessione, costituito da timestamp, valori delle proprietà e durata. La durata non è disponibile per l’ultimo evento di una determinata sessione.

>[!VIDEO](https://video.tv.adobe.com/v/3427810/?learn=on)

>[!NOTE]
>
>La vista Timeline richiede che il **[!UICONTROL Person ID]** il componente standard sarà disponibile nel [visualizzazione dati](/help/data-views/component-reference.md#optional). L’inclusione dell’ID persona in una visualizzazione dati viene gestita dall’amministratore di Customer Journey Analytics, consentendo all’organizzazione di controllare completamente la privacy degli utenti che possono accedere a tali dati.

Se una visualizzazione dati non dispone del [!UICONTROL Person ID] è stato aggiunto un componente, viene visualizzato il seguente messaggio:

* **Amministratori**: *La proprietà PersonID è obbligatoria per questa analisi. Aggiungi l&#39;ID persona alla visualizzazione dati.*
* **Non amministratori**: *La proprietà PersonID è obbligatoria per questa analisi. Rivolgiti al tuo amministratore di Customer Journey Analytics per aggiungere l’ID persona alla visualizzazione dati.*

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Esplorazione dell’attrito**: se trovi una goccia profonda nella [Attrito](friction.md) , è possibile creare un segmento di tali utenti e applicarlo in questa visualizzazione per indagare le possibili cause.
* **Comportamento di errore**: se gli utenti rilevano un errore di prodotto, puoi scoprire cosa stavano facendo gli utenti prima o dopo aver visualizzato tale errore.
* **Convalida della raccolta dati**: gli amministratori dei dati possono filtrare questa vista in base al proprio ID persona per verificare che l’implementazione della loro organizzazione funzioni come previsto.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Property]**: proprietà per la quale visualizzare i valori in streaming. Il flusso al centro mostra i valori per la proprietà selezionata. Puoi anche applicare filtri per restringere il flusso a dati più rilevanti. Gli operatori validi per il filtro includono [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Starts with], [!UICONTROL Ends with], [!UICONTROL Contains], [!UICONTROL Does not contain], [!UICONTROL Exists], e [!UICONTROL Does not exist].
* **[!UICONTROL Segments]**: il segmento che desideri analizzare. Il segmento selezionato filtra i dati in modo da concentrarti solo sui singoli utenti che corrispondono ai criteri del segmento. Se desideri limitare la visualizzazione a un ID persona specifico, puoi filtrare tale ID qui. Per questa visualizzazione è supportato un segmento.

## Impostazioni grafico

Il [!UICONTROL Timeline] visualizza offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Show as]**: mostra i valori della proprietà desiderati.
   * [!UICONTROL Show all]: mostra tutti i valori delle proprietà in una sessione.
   * [!UICONTROL Highlight]: evidenzia visivamente i valori delle proprietà in una sessione che corrispondono ai filtri della query.
   * [!UICONTROL View only]: mostra solo i valori delle proprietà in una sessione che corrispondono ai filtri della query.

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati sulle tendenze. Questa impostazione non influisce sulle viste non di tendenza, come la Timeline.
* **[!UICONTROL Date]**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.
