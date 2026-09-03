---
description: Scopri come creare una metrica di partecipazione.
title: Metrica di partecipazione
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
TQID: https://experienceleague.adobe.com/no7rAZUl25LTEPqwRyC7vY4XcottzPGRq-DCAR5ez54
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 232
ht-degree: 6%

---

# Metriche di partecipazione.

Le metriche di partecipazione vengono utilizzate per quantificare il modo in cui i singoli valori di una dimensione (come Visualizzazioni di pagina) contribuiscono o partecipano a sessioni che contengono una metrica specifica (come Ordini).

>[!NOTE]
>
>Gli amministratori possono creare metriche con modelli di attribuzione non predefiniti, ad esempio Partecipazione, come parte di una [visualizzazione dati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/data-views). Per ulteriori dettagli, consulta [Impostazioni del componente di attribuzione](../../../data-views/component-settings/attribution.md).

I passaggi seguenti mostrano come qualsiasi utente con l&#39;autorizzazione [Crea metrica calcolata](/help/technotes//access-control.md#user-level-access) può creare una metrica di partecipazione.

1. [Creare una metrica calcolata](cm-workflow.md) e nel [Generatore di metriche calcolate](cm-build-metrics.md), denominare la metrica `Participation` o una metrica simile.
1. Trascinare una metrica contenente un evento di successo, ad esempio [!DNL Orders], nell&#39;area [!UICONTROL **[!UICONTROL Definizione]**].
1. Selezionare ![Ingranaggio](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) per la metrica.
1. Nel popup visualizzato, selezionare **[!UICONTROL Utilizza un modello di attribuzione non predefinito]** per definire il [modello di attribuzione](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) dell&#39;evento a **[!UICONTROL Partecipazione]** e selezionare **[!UICONTROL Sessione]** per [!UICONTROL Contenitore]. Seleziona **[!UICONTROL Applica]** per confermare.


   ![Menu a comparsa del modello di attribuzione colonna che mostra la partecipazione selezionata come modello e la sessione selezionata per l&#39;intervallo di lookback.](assets/participation-setup.png)

   **(Partizione|Sessione)** è stato aggiunto al nome del componente della metrica.



1. Seleziona [!UICONTROL **Salva**] per salvare la metrica.
1. Utilizza la metrica calcolata nel rapporto. Ad esempio, utilizza la metrica [!DNL Orders (Session Participation)] calcolata in un rapporto per mostrare quale livello cliente ha contribuito (o partecipato) alle sessioni che contenevano un ordine.

   ![Tabella a forma libera che mostra il livello cliente e gli ordini.](assets/participation-pages-customer-tier.png)
