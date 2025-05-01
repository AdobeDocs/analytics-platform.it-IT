---
title: Impostazioni del componente gruppo di dati di riepilogo
description: Dettagli e modalità di configurazione delle dimensioni dai set di dati per fare in modo che tu possa creare rapporti in modo corretto sui dati di riepilogo.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 88%

---

# Impostazioni del componente [!UICONTROL Summary data group] {#summary-data-group-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup"
>title="Gruppo di dati di riepilogo"
>abstract="Un gruppo di dati di riepilogo crea un’associazione tra tutte le dimensioni del raggruppamento e viene utilizzato per combinare le dimensioni del set di dati di riepilogo e altri dimensioni per il reporting."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup_hideinreporting"
>title="Nascondere nel reporting"
>abstract="Selezionando questa opzione verrà abilitato **[!UICONTROL Hide component in reporting]** per tale dimensione e il componente non verrà mostrato in Analysis Workspace e in altri strumenti di reporting di Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->



Un gruppo di dati di riepilogo crea un’associazione tra tutte le dimensioni del raggruppamento e viene utilizzato per combinare le dimensioni del set di dati di riepilogo e altri dimensioni per il reporting.

![Impostazioni del componente gruppo di dati di riepilogo](/help/data-views/assets/summary-data-group.png)

Per creare un raggruppamento delle dimensioni:

1. Seleziona una dimensione.
1. Seleziona ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Summary data group]**.
1. Abilita **[!UICONTROL Create grouping]**.
1. Selezionare una dimensione dal menu a discesa **[!UICONTROL Dimension]** che si desidera raggruppare con la dimensione selezionata dal primo passaggio. Solo le dimensioni già aggiunte alla visualizzazione dati sono disponibili dal menu a discesa.
1. Facoltativamente, abilita **[!UICONTROL Hide in reporting]** per nascondere la dimensione raggruppata dal reporting. L’abilitazione di questa opzione è simile alla configurazione di **[!UICONTROL Hide in reporting]** nella dimensione raggruppata separatamente. Consulta [Impostazioni dei componenti](overview.md) per ulteriori informazioni.
1. Facoltativamente, per aggiungere ulteriori dimensioni al raggruppamento, seleziona ![Aggiungi](/help/assets/icons/Add.svg) **[!UICONTROL Add dimension to group]**.<br/>Puoi aggiungere fino a nove dimensioni, poiché in un gruppo di dati di riepilogo il limite è dieci.

## Impostazioni degli stessi componenti

Quando si raggruppano le dimensioni, è necessario assicurarsi che le impostazioni per [!UICONTROL Substring], [!UICONTROL Behavior (Lower case)] e [!UICONTROL Include exclude values], per ciascuna delle dimensioni che fanno parte del gruppo, siano uguali. In caso contrario, ogni dimensione del gruppo può potenzialmente restituire risultati diversi prima del raggruppamento.
Ad esempio:

1. È stato creato un gruppo di dati di riepilogo per `campaign_code` (parte dei dati di riepilogo) e `tracking_code` (parte dei dati dell’evento).
1. Hai applicato [!UICONTROL Behavior (Lower case)] alla dimensione `campaign_code` ma non alla dimensione `tracking_code`.

I valori in `tracking_code` possono essere potenzialmente visualizzati come diversi da `campaign_code`.

>[!IMPORTANT]
>
>Assicurati di eseguire il raggruppamento delle dimensioni da una sola dimensione e di non applicare il raggruppamento da più dimensioni. Ad esempio, se crei un raggruppamento aggiungendo la dimensione `campaign_name` alla dimensione `tracking_code`, non creare anche un raggruppamento per la dimensione `campaign_name`.
>
