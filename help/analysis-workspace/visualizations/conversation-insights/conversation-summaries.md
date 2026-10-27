---
description: Utilizza la visualizzazione Riepiloghi conversazione per riepilogare le conversazioni.
title: Riepiloghi delle conversazioni
feature: Visualizations
role: User
hide: true
source-git-commit: 2cca5dfaec6be8f22308e09a023e9e57bec387b7
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 10%
---
# Riepiloghi delle conversazioni {#conversation-summaries}

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_button"
>title="Riepiloghi delle conversazioni"
>abstract="Crea una visualizzazione che riepiloga un gruppo filtrato di conversazioni."

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_panel"
>title="Riepiloghi delle conversazioni"
>abstract="Riepiloga un gruppo filtrato di conversazioni. Controlla la lunghezza del riepilogo. Consulta le offerte rappresentative dei clienti per convalidare l’accuratezza dei segnali estratti. Selezionare un preventivo per aprire la ripetizione completa della conversazione."


La visualizzazione ![Riepiloga](/help/assets/icons/Summarize.svg) **[!UICONTROL Riepiloghi conversazione]** consente di riepilogare un gruppo filtrato di conversazioni.

La visualizzazione mostra un riepilogo della metrica selezionata (ad esempio Conversazioni) e, dopo aver configurato la visualizzazione in modo da includere gli argomenti secondari, visualizza gli argomenti secondari o i commenti verbali.


## Creare e configurare {#conversation-summaries-create-configure}

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_usenondefaultattributionmodel"
>title="Usa modello di attribuzione non predefinito"
>abstract="Abilita un modello di attribuzione non predefinito per questa metrica."

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_usenondefaultattributionmodel_disabled"
>title="Usa modello di attribuzione non predefinito"
>abstract="Per questa metrica non sono disponibili modelli di attribuzione non predefiniti."

Per creare e configurare una visualizzazione **[!UICONTROL Riepiloghi conversazione]**:

1. Aggiungi una visualizzazione ![Riepiloga](/help/assets/icons/Summarize.svg) **[!UICONTROL Riepiloghi conversazione]**. Consulta [Aggiungere una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Nella configurazione della visualizzazione **[!UICONTROL Riepiloghi conversazione]**:

   1. Seleziona una **[!UICONTROL metrica]**. Ad esempio: **[!UICONTROL Conversazioni]**.
   1. Se si desidera utilizzare un modello [attribution](/help/analysis-workspace/attribution/models.md) non predefinito nella metrica, selezionare **[!UICONTROL Usa modello di attribuzione non predefinito]**, quindi selezionare **[!UICONTROL Modello]**, **[!UICONTROL Contenitore]** e **[!UICONTROL Intervallo di lookback]**.
   1. Facoltativamente, puoi applicare un segmento alla visualizzazione. Seleziona un segmento dal menu a discesa **[!UICONTROL Segmenti]**.

1. Seleziona **[!UICONTROL Build]** per generare la visualizzazione. Selezionare **[!UICONTROL Reimposta]** per ripristinare i valori predefiniti della configurazione. Seleziona **[!UICONTROL Annulla]** per annullare la configurazione.

Per riconfigurare la visualizzazione **[!UICONTROL Riepiloghi conversazione]**, seleziona ![Modifica](/help/assets/icons/Edit.svg) accanto a **[!UICONTROL Metrica: _Metrica_]**&#x200B;o **[!UICONTROL Metrica:_Metrica_]** | **[!UICONTROL Segmenti: _segmenti_]**.

## Utilizzo

Per utilizzare la visualizzazione:

>[!BEGINTABS]

>[!TAB Argomenti secondari]

![Argomenti secondari](assets/conversation-summaries-subtopics.png)

>[!TAB Commenti verbali]

![Commenti verbali](assets/conversation-summaries-verbatimcomments.png)

>[!ENDTABS]

* Se sono presenti [argomenti secondari inclusi](#settings), selezionare **[!UICONTROL Argomenti secondari]** per visualizzare gli argomenti secondari o **[!UICONTROL Commenti verbali]** per visualizzare i commenti verbali.
* Dopo aver selezionato **[!UICONTROL Commenti verbali]**, seleziona ![FileSearch](/help/assets/icons/FileSearch.svg) per aprire una nuova visualizzazione [**[!UICONTROL Revisione conversazione]**](./conversation-review.md) per la conversazione specifica di cui fa parte il commento verbale.

## Impostazioni

Sono disponibili le seguenti [impostazioni di visualizzazione specifiche](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings).

| Impostazione | Descrizione |
|---|---|
| **[!UICONTROL Lunghezza riepilogo]** | Specifica la lunghezza del riepilogo. Puoi scegliere tra **[!UICONTROL Short]** o **[!UICONTROL Long]**. |
| **[!UICONTROL Includi argomenti secondari]** | Selezionare **[!UICONTROL Includi argomenti secondari]** per visualizzare gli argomenti secondari nella visualizzazione. Utilizza **[!UICONTROL Numero massimo di argomenti secondari]** per configurare il numero massimo di argomenti secondari da visualizzare. |
