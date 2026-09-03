---
title: Impostazioni del componente gruppo di dati di riepilogo
description: Dettagli e modalità di configurazione delle dimensioni dai set di dati per fare in modo che tu possa creare rapporti in modo corretto sui dati di riepilogo.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
autotag-review: '2026-05-19T09:00:37.763Z'
TQID: 'https://experienceleague.adobe.com/t1TH-tkHBNCfmC8hgk-IntYmYdRrS0enf2YEyRExCo4'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 378
ht-degree: 64%

---

# Impostazioni del componente [!UICONTROL Gruppo di dati di riepilogo] {#summary-data-group-component-settings}

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
>abstract="Selezionando questa opzione verrà abilitato **[!UICONTROL Nascondi componente nel reporting]** per tale dimensione e il componente non verrà mostrato in Analysis Workspace e in altri strumenti di reporting di Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->



Un gruppo di dati di riepilogo crea un’associazione tra tutte le dimensioni del raggruppamento e viene utilizzato per combinare le dimensioni del set di dati di riepilogo e altri dimensioni per il reporting.

![Impostazioni del componente gruppo di dati di riepilogo](/help/data-views/assets/summary-data-group.png)

Per creare un raggruppamento delle dimensioni:

1. Seleziona una dimensione.
1. Selezionare ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Gruppo di dati di riepilogo]**.
1. Abilita **[!UICONTROL Crea raggruppamento]**.
1. Selezionare una dimensione dal menu a discesa **[!UICONTROL Dimension]** che si desidera raggruppare con la dimensione selezionata dal primo passaggio. Solo le dimensioni già aggiunte alla visualizzazione dati sono disponibili dal menu a discesa.
1. Facoltativamente, abilita **[!UICONTROL Nascondi nel reporting]** per nascondere la dimensione raggruppata dal reporting. L&#39;abilitazione di questa opzione è simile alla configurazione di **[!UICONTROL Nascondi nel reporting]** nella dimensione raggruppata separatamente. Consulta [Impostazioni dei componenti](overview.md) per ulteriori informazioni.
1. Per aggiungere dimensioni aggiuntive al raggruppamento, selezionare ![Aggiungi](/help/assets/icons/Add.svg) **[!UICONTROL Aggiungi dimensione al gruppo]**.<br/>Puoi aggiungere fino a nove dimensioni, poiché in un gruppo di dati di riepilogo il limite è dieci.

## Impostazioni degli stessi componenti

Quando si raggruppano le dimensioni, è necessario assicurarsi che le impostazioni per [!UICONTROL Substring], [!UICONTROL Behavior (Lower case)] e [!UICONTROL Include exclude values], per ciascuna delle dimensioni che fanno parte del gruppo, siano uguali. In caso contrario, ogni dimensione del gruppo può potenzialmente restituire risultati diversi prima del raggruppamento.
Ad esempio:

1. È stato creato un gruppo di dati di riepilogo per `campaign_code` (parte dei dati di riepilogo) e `tracking_code` (parte dei dati dell’evento).
1. Hai applicato [!UICONTROL Comportamento (lettere minuscole)] a `campaign_code` ma non alla dimensione `tracking_code`.

I valori in `tracking_code` possono essere potenzialmente visualizzati come diversi da `campaign_code`.

>[!IMPORTANT]
>
>Assicurati di eseguire il raggruppamento delle dimensioni da una sola dimensione e di non applicare il raggruppamento da più dimensioni. Ad esempio, se crei un raggruppamento aggiungendo la dimensione `campaign_name` alla dimensione `tracking_code`, non creare anche un raggruppamento per la dimensione `campaign_name`.
>
