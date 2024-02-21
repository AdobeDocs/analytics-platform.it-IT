---
title: Vista Timeline
description: Osserva gli eventi di sessione a livello di utente nel tempo per trovare modelli di esperienza.
feature: Guided Analysis
keywords: analisi dei prodotti
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 0%

---

# [!UICONTROL Timeline] visualizza

Il **[!UICONTROL Timeline]** La visualizzazione ti consente di osservare gli eventi delle sessioni a livello di utente nel tempo, trovare modelli di esperienza e raccontare storie di utenti migliori. La barra a sinistra ti consente di filtrare il flusso per valori di proprietà e segmenti. La barra a destra consente di selezionare da un elenco randomizzato di utenti che corrispondono ai criteri del filtro. L&#39;area centrale mostra il flusso per l&#39;utente selezionato per sessione, costituito da timestamp, valori delle proprietà e durata. La durata non è disponibile per l’ultimo evento di una determinata sessione.

![Schermata della timeline](../assets/timeline.png){style="border:1px solid gray"}

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
