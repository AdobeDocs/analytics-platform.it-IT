---
description: Con il generatore di metriche calcolate, chiunque può creare una metrica di partecipazione.
title: Metrica di partecipazione
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: d95d324350a2f8aa77032e7cac1c924d161d47ce
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 10%

---

# Creare una metrica “Partecipazione”

Questo articolo spiega come creare una metrica che mostra come i singoli valori per una dimensione selezionata (come Visualizzazioni pagina, Canale di marketing, Versione app) hanno contribuito (o partecipato) alle sessioni che contenevano un ordine.

Questo tipo di informazioni potrebbe essere utile per qualsiasi proprietario di contenuto.

>[!NOTE]
>
>Le metriche con altri modelli di attribuzione, ad esempio Partecipazione, possono essere create dagli amministratori come parte di un [visualizzazione dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=it). L’esempio seguente mostra come possono essere create da qualsiasi utente con accesso al generatore di metriche calcolate in Workspace.

1. Inizia a creare una metrica, come descritto in [Creare metriche](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Nel generatore di metriche calcolate, denomina la metrica &quot;Partecipazione&quot; o qualcosa di simile.
1. Trascina l’evento di successo &quot;Ordini&quot; nell’area di lavoro Definizione.
1. Seleziona ![Ingranaggio](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) per [!DNL Orders] metriche.
1. Nella finestra a comparsa visualizzata, seleziona **[!UICONTROL Use a non-default attribution model]** per definire [modello di attribuzione](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) di tale evento a **[!UICONTROL Participation]** e seleziona **[!UICONTROL Session]** per [!UICONTROL Lookback window]. Seleziona **[!UICONTROL Apply]** per confermare.

   Nella casella Definizione (Definition) ![Evento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **Ordini** è aggiornato a ![Evento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **Ordini (partizione|sessione)**.

   ![](assets/participation-setup.png)



1. Seleziona [!UICONTROL **Salva**] per salvare la metrica.
1. Utilizza la metrica calcolata nel rapporto. Sotto la metrica calcolata viene utilizzato in un rapporto per mostrare quale livello cliente ha contribuito (o partecipato) alle sessioni che contenevano un ordine.

   ![](assets/participation-pages-customer-tier.png)

1. (Facoltativo) Condividi la metrica con altri utenti dell’organizzazione, come descritto in [Condividere le metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
