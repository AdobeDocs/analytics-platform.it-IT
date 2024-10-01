---
description: Con il generatore di metriche calcolate, chiunque può creare una metrica di partecipazione.
title: Metrica di partecipazione
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 65eafd65358d9370b452338ce1036e59b3c69d1a
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Metriche di partecipazione

Le metriche di partecipazione vengono utilizzate per quantificare il modo in cui i singoli valori di una dimensione (come Visualizzazioni di pagina) contribuiscono o partecipano a sessioni che contengono una metrica specifica (come Ordini).

>[!NOTE]
>
>Gli amministratori possono creare metriche con modelli di attribuzione non predefiniti, ad esempio Partecipazione, come parte di una [visualizzazione dati](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views). Per ulteriori dettagli, consulta [Impostazioni del componente di attribuzione](../../../data-views/component-settings/attribution.md).

I passaggi seguenti mostrano come qualsiasi utente con l&#39;autorizzazione [Crea metrica calcolata](/help/technotes//access-control.md#user-level-access) può creare una metrica di partecipazione.

1. [Creare una metrica calcolata](cm-workflow.md) e nel [Generatore di metriche calcolate](cm-build-metrics.md), denominare la metrica `Participation` o una metrica simile.
1. Trascinare una metrica contenente un evento di successo, ad esempio [!DNL Orders], nell&#39;area [!UICONTROL **[!UICONTROL Definition]**].
1. Selezionare ![Ingranaggio](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) per la metrica.
1. Nel popup visualizzato, selezionare **[!UICONTROL Use a non-default attribution model]** per definire il [modello di attribuzione](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) dell&#39;evento a **[!UICONTROL Participation]** e selezionare **[!UICONTROL Session]** per [!UICONTROL Lookback window]. Selezionare **[!UICONTROL Apply]** per confermare.


   ![Menu a comparsa del modello di attribuzione colonna che mostra la partecipazione selezionata come modello e la sessione selezionata per l&#39;intervallo di lookback.](assets/participation-setup.png)

   **(Partizione|Sessione)** è stato aggiunto al nome del componente della metrica.



1. Seleziona [!UICONTROL **Salva**] per salvare la metrica.
1. Utilizza la metrica calcolata nel rapporto. Ad esempio, utilizza la metrica [!DNL Orders (Session Participation)] calcolata in un rapporto per mostrare quale livello cliente ha contribuito (o partecipato) alle sessioni che contenevano un ordine.

   ![Tabella a forma libera che mostra il livello cliente e gli ordini.](assets/participation-pages-customer-tier.png)
