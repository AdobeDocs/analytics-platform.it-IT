---
title: Utilizzare i campi derivati per creare rapporti sugli obiettivi
description: Scopri come utilizzare i campi derivati per creare rapporti sugli obiettivi (target) nei progetti Workspace.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: 53cf026531ac5690a3e5a31acaa5654a52747b69
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 2%

---


# Utilizzare i campi derivati per creare rapporti sugli obiettivi

Questo caso d’uso descrive come utilizzare la potenza dei campi derivati per impostare gli obiettivi per una dimensione specifica e quindi utilizzarli nel progetto Workspace.

Se non conosci i campi derivati, consulta la sezione [esercitazione](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html?lang=en) e [documentazione](../data-views/derived-fields/derived-fields.md) per un’introduzione.


## Definire gli obiettivi

Per definire gli obiettivi, crea un nuovo campo derivato in cui impostare esplicitamente i valori numerici personalizzati direttamente o indirettamente utilizzando i valori risultanti dalle regole precedenti nella definizione del campo derivato.


### Obiettivi degli ordini di buoni mensili

Desideri impostare esplicitamente gli obiettivi per gli ordini di certificati regalo per quattro mesi, da luglio 2023 a ottobre 2023. Per eseguire questa operazione:

1. Crea un nuovo campo derivato con il nome `Monthly Gift Certificate Orders Goal (Incremental)`.

1. Impostare valori statici, utilizzando una REGOLA CASE WHEN, per ogni mese impostando un **[!UICONTROL Custom numeric value]**. Consulta la regola Obiettivi di prodotto mensili di seguito.

   ![Obiettivi del prodotto](assets/goals-derived-field-product-goals-1.png)


### Obiettivi di ricavo del canale di marketing

Desideri impostare un obiettivo di ricavi mensile per ciascuno dei tuoi canali di marketing. Per eseguire questa operazione:

1. Creare un nuovo campo derivato utilizzando [Modello di funzione Canali di marketing](/help/data-views/derived-fields/derived-fields.md#marketing-channels) con il nome `Monthly Marketing Channel Revenue Goal (Incremental)`.

1. Definisci tutte le regole per identificare correttamente ciascuno dei canali di marketing in base a una combinazione di regole URL PARSE e CASE WHEN. Ad esempio:

   ![Definizione delle regole per il campo derivato dal canale di marketing](assets/goals-derived-field-marketing-channel-1.png)

1. Impostare in modo esplicito valori statici, che rappresentano gli obiettivi di ricavi mensili, per canali di marketing specifici in una regola CASE WHEN finale, impostando un **[!UICONTROL Custom numeric value]**. Consulta la [!DNL Monthly Goal] regola di seguito.

   ![Obiettivi mensili](assets/goals-derived-field-marketing-channel-2.png)



## Usa obiettivi

Per utilizzare gli obiettivi nel progetto Workspace, utilizza la funzionalità delle metriche calcolate per &quot;normalizzare&quot; il campo derivato al suo valore statico originale.

### Obiettivi degli ordini di buoni mensili

1. Creare un campo metrico calcolato denominato `Monthly Gift Certificate Orders Goal`, definito come:

   ![Obiettivo ordini](assets/calculated-metric-ordersgoals.png)

1. Puoi creare campi calcolati aggiuntivi, ad esempio `% of Monthly Gift Certificate Orders Goal`, per mostrare i progressi effettivi rispetto agli obiettivi, ad esempio:

   ![Percentuale obiettivo ordini](assets/calculated-metric-ordersgoalspercent.png)

Puoi utilizzare queste metriche calcolate per generare rapporti sull’avanzamento nelle tabelle e nelle visualizzazioni a forma libera. Ad esempio:

![Tabella a forma libera che mostra gli obiettivi di marketing](assets/freeform-table-product-order-goals.png)


### Obiettivi di ricavo del canale di marketing

1. Creare un campo metrico calcolato denominato `Marketing Channel Revenue Goal`, definito come:

   ![Revenue Goal](assets/calculated-metric-revenuegoals.png)

1. Puoi creare campi calcolati aggiuntivi, ad esempio `% of Marketing Channel Revenue Goal`, per mostrare i progressi effettivi rispetto agli obiettivi, ad esempio:

   ![Percentuale obiettivo ricavi](assets/calculated-metric-revenuegoalspercent.png)

Puoi utilizzare queste metriche calcolate per generare rapporti sull’avanzamento nelle tabelle e nelle visualizzazioni a forma libera. Ad esempio:

![Tabella a forma libera che mostra gli obiettivi di marketing](assets/freeform-table-marketing-channel-revenue-goals.png)
