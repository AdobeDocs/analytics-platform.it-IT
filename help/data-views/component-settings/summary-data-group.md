---
title: Impostazioni dei componenti dei gruppi di dati di riepilogo
description: Dettagli e come configurare le dimensioni dai set di dati per garantire la possibilità di creare rapporti corretti sui dati di riepilogo.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: cba5904191b0602557903b5b9f32a2b793c8207d
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 1%

---

# Impostazioni del componente [!UICONTROL Summary data group]

Un gruppo di dati di riepilogo crea un’associazione tra tutte le dimensioni del raggruppamento e viene utilizzato per combinare dimensioni da set di dati di riepilogo con altre dimensioni per il reporting.

![Impostazioni del componente del gruppo di dati di riepilogo](/help/data-views/assets/summary-data-group.png)

Per creare un raggruppamento di dimensioni:

1. Selezionate una quota.
1. Selezionare ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Summary data group]**.
1. Abilita **[!UICONTROL Create grouping]**.
1. Selezionare una dimensione dall&#39;elenco a discesa **[!UICONTROL Dimension]** che si desidera raggruppare con la dimensione selezionata dal primo passaggio. Dall’elenco a discesa sono disponibili solo le dimensioni già aggiunte alla visualizzazione dati.
1. Facoltativamente, abilitare **[!UICONTROL Hide in reporting]** per nascondere la dimensione raggruppata dal reporting. L&#39;abilitazione di questa opzione è simile alla configurazione separata di **[!UICONTROL Hide in reporting]** nella dimensione raggruppata. Per ulteriori informazioni, vedere [Impostazioni dei componenti](overview.md).
1. Per aggiungere dimensioni aggiuntive al raggruppamento, selezionare ![Aggiungi](/help/assets/icons/Add.svg) **[!UICONTROL Add dimension to group]**.<br/>È possibile aggiungere fino a nove dimensioni, poiché un gruppo di dati di riepilogo ha un limite di dieci dimensioni.

## Impostazioni dello stesso componente

Quando si raggruppano le dimensioni, è necessario assicurarsi che le impostazioni per [!UICONTROL Substring], [!UICONTROL Behavior (Lower case)] e [!UICONTROL Include exclude values], per ciascuna delle dimensioni che fanno parte del gruppo, siano uguali. In caso contrario, ogni dimensione del gruppo può potenzialmente restituire risultati diversi prima del raggruppamento.
Ad esempio:

1. È stato creato un gruppo di dati di riepilogo per `campaign_code` (parte dei dati di riepilogo) e `tracking_code` (parte dei dati evento).
1. Hai applicato [!UICONTROL Behavior (Lower case)] alla dimensione `campaign_code` ma non alla dimensione `tracking_code`.

I valori in `tracking_code` potrebbero essere visualizzati come diversi da `campaign_code`.

>[!IMPORTANT]
>
>Assicuratevi di effettuare il raggruppamento di quote da una sola quota e di non applicare il raggruppamento da più quote. Ad esempio, se si crea un raggruppamento aggiungendo la dimensione `campaign_name` alla dimensione `tracking_code`, non creare un raggruppamento anche per la dimensione `campaign_name`.
>


