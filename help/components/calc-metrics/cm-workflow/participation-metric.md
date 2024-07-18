---
description: Con il generatore di metriche calcolate, chiunque può creare una metrica di partecipazione.
title: Metrica di partecipazione
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 1%

---

# Creare una metrica di partecipazione

Questo articolo spiega come creare una metrica di partecipazione. Una metrica di partecipazione mostra il modo in cui i singoli valori di una dimensione (come Visualizzazioni di pagina, Canale di marketing) contribuiscono o partecipano a sessioni che contengono una metrica specifica (ad esempio Ordini).

Questo tipo di informazioni potrebbe essere utile per qualsiasi proprietario di contenuto.

>[!NOTE]
>
>Le metriche con altri modelli di attribuzione, ad esempio Partecipazione, possono essere create anche dagli amministratori come parte di una [visualizzazione dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=it). Per ulteriori dettagli, consulta [Impostazioni del componente di attribuzione](../../../data-views/component-settings/attribution.md).<br/>Nell&#39;esempio seguente viene illustrato come è possibile creare una metrica di partecipazione da qualsiasi utente con accesso al generatore di metriche calcolate in Workspace.


1. Inizia a creare una metrica, come descritto in [Metriche di compilazione](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Nel generatore di metriche calcolate, assegnare un nome alla metrica `Participation` o a un nome simile.
1. Trascinare una metrica contenente un evento di successo, ad esempio [!DNL Orders], nell&#39;area di lavoro [!UICONTROL Definition].
1. Selezionare ![Ingranaggio](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) per la metrica.
1. Nel popup visualizzato, selezionare **[!UICONTROL Use a non-default attribution model]** per definire il [modello di attribuzione](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) dell&#39;evento a **[!UICONTROL Participation]** e selezionare **[!UICONTROL Session]** per [!UICONTROL Lookback window]. Selezionare **[!UICONTROL Apply]** per confermare.

   Nella casella Definizione, la metrica selezionata viene aggiornata aggiungendo **(Partizione|Sessione)** al nome.

   ![Menu a comparsa del modello di attribuzione colonna che mostra la partecipazione selezionata come modello e la sessione selezionata per l&#39;intervallo di lookback.](assets/participation-setup.png)



1. Seleziona [!UICONTROL **Salva**] per salvare la metrica.
1. Utilizza la metrica calcolata nel rapporto. Ad esempio, utilizza la metrica [!DNL Orders (Session Participation)] calcolata (come definita nel passaggio 5) in un rapporto per mostrare quale livello cliente ha contribuito (o partecipato) alle sessioni che contenevano un ordine.

   ![Tabella a forma libera che mostra il livello cliente e gli ordini.](assets/participation-pages-customer-tier.png)

1. (Facoltativo) Condividi la metrica con altri utenti dell&#39;organizzazione, come descritto in [Condividi metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
