---
description: Con il generatore di metriche calcolate, chiunque può creare una metrica di partecipazione.
title: Metrica di partecipazione
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 6a9cae93011447fff0f74ca4ae15178e0a1f36aa
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 2%

---

# Creare una metrica di partecipazione

Questo articolo spiega come creare una metrica di partecipazione. Una metrica di partecipazione mostra il modo in cui i singoli valori di una dimensione (come Visualizzazioni di pagina, Canale di marketing) contribuiscono o partecipano a sessioni che contengono una metrica specifica (ad esempio Ordini).

Questo tipo di informazioni potrebbe essere utile per qualsiasi proprietario di contenuto.

>[!NOTE]
>
>Le metriche con altri modelli di attribuzione, ad esempio Partecipazione, possono essere create dagli amministratori come parte di un [visualizzazione dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=it). L’esempio seguente mostra come possono essere create da qualsiasi utente con accesso al generatore di metriche calcolate in Workspace.


1. Inizia a creare una metrica, come descritto in [Creare metriche](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Nel generatore di metriche calcolate, denomina la metrica &quot;Partecipazione&quot; o qualcosa di simile.
1. Trascina una metrica contenente un evento di successo, ad esempio &quot;Ordini&quot;, nell’area di lavoro Definizione.
1. Seleziona ![Ingranaggio](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) per la metrica.
1. Nella finestra a comparsa visualizzata, seleziona **[!UICONTROL Use a non-default attribution model]** per definire [modello di attribuzione](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) di tale evento a **[!UICONTROL Participation]** e seleziona **[!UICONTROL Session]** per [!UICONTROL Lookback window]. Seleziona **[!UICONTROL Apply]** per confermare.

   Nella casella Definizione, la metrica selezionata viene aggiornata aggiungendo  **(Partizione|Sessione)** al suo nome.

   ![](assets/participation-setup.png)



1. Seleziona [!UICONTROL **Salva**] per salvare la metrica.
1. Utilizza la metrica calcolata nel rapporto. Ad esempio, utilizza il [!DNL Orders (Session Participation)] metrica (come definita nel passaggio 5) in un rapporto per mostrare quale livello cliente ha contribuito (o partecipato) alle sessioni che contenevano un ordine.

   ![](assets/participation-pages-customer-tier.png)

1. (Facoltativo) Condividi la metrica con altri utenti dell’organizzazione, come descritto in [Condividere le metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
