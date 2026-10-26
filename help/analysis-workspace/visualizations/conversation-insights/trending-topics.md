---
description: Utilizza la visualizzazione degli argomenti di tendenza per esplorare gli argomenti di tendenza nelle conversazioni.
title: Argomenti di tendenza
feature: Visualizations
role: User
hide: true
source-git-commit: 85311bf19368560ef54a3361edf2e7c13590929c
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 8%
---
# Argomenti di tendenza {#trending-topics}

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="Argomenti di tendenza"
>abstract="Crea una visualizzazione che mostri una suddivisione gerarchica degli argomenti di tendenza, con occorrenze e percentuali, abilitata per l’espansione, per identificare i temi significativi nelle conversazioni."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="Argomenti di tendenza"
>abstract="Analizza gli argomenti di tendenza in base alla metrica di classificazione selezionata. Selezionare gli argomenti per eseguire il drill-down fino a cinque livelli di profondità. Cerca argomenti specifici e confronta gli argomenti con altri intervalli di date."

La visualizzazione ![Feed](/help/assets/icons/Feed.svg) **[!UICONTROL Argomenti di tendenza]** consente di esplorare e analizzare gli argomenti di tendenza come parte degli approfondimenti sulla conversazione.

È possibile cercare argomenti specifici e confrontare il numero e la percentuale di ciascun argomento a ogni livello con altri intervalli di dati.

## Creare e configurare {#trendimg-topics-create-and-configure}

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_usenondefaultattributionmodel"
>title="Usa modello di attribuzione non predefinito"
>abstract="Abilita un modello di attribuzione non predefinito per questa metrica."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_usenondefaultattributionmodel_disabled"
>title="Usa modello di attribuzione non predefinito"
>abstract="Per questa metrica non sono disponibili modelli di attribuzione non predefiniti."

Per creare e configurare una visualizzazione **[!UICONTROL Argomenti di tendenza]**:

1. Aggiungi una visualizzazione ![Feed](/help/assets/icons/Feed.svg) **[!UICONTROL Argomenti di tendenza]**. Consulta [Aggiungere una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Nella configurazione della visualizzazione **[!UICONTROL Argomenti di tendenza]**:

   1. Selezionare una **[!UICONTROL metrica di classificazione]**. Ad esempio: **[!UICONTROL Conversazioni]**.
   1. Se si desidera utilizzare un modello [attribution](/help/analysis-workspace/attribution/models.md) non predefinito nella metrica, selezionare **[!UICONTROL Usa modello di attribuzione non predefinito]**, quindi selezionare **[!UICONTROL Modello]**, **[!UICONTROL Contenitore]** e **[!UICONTROL Intervallo di lookback]**.
1. Seleziona **[!UICONTROL Build]** per generare la visualizzazione. Selezionare **[!UICONTROL Reimposta]** per ripristinare i valori predefiniti della configurazione.

Per riconfigurare la visualizzazione degli argomenti di tendenza, seleziona ![Modifica](/help/assets/icons/Edit.svg) accanto a **[!UICONTROL Metrica di classificazione: _Metrica di classificazione_ | Livelli argomento: _x_]**.

## Utilizzo

Per utilizzare la visualizzazione:

![Utilizza la visualizzazione Argomenti di tendenza](assets/trending-topics.png)

* Passa il puntatore del mouse su un argomento per visualizzare una finestra a comparsa con ulteriori dettagli. ➊

* Per visualizzare gli argomenti secondari di tendenza per un argomento di livello inferiore, selezionare un argomento di livello specifico. Se non sono disponibili argomenti a un livello secondario, verrà visualizzato ![DataRemove](/help/assets/icons/DataRemove.svg) **[!UICONTROL Nessun argomento secondario trovato per _topic > sottoargomento > ...]**.

* Utilizza ![Cerca](/help/assets/icons/Search.svg) **[!UICONTROL _Cerca argomenti_]** per cercare rapidamente gli argomenti. ➋

* Per confrontare gli argomenti con un altro intervallo di date, selezionare un intervallo di date compreso tra **[!UICONTROL Confronta con]**. ➌

  Per utilizzare un intervallo di date personalizzato:

  * Seleziona **[!UICONTROL Intervallo date personalizzato]** dal menu a discesa e nella finestra di dialogo **[!UICONTROL Nuovo intervallo date]** definisci e salva un intervallo date personalizzato.
  * Seleziona l’intervallo di date personalizzato.

* Per visualizzare un grafico a linee per la selezione corrente di argomenti, rilascia una visualizzazione [Riga](/help/analysis-workspace/visualizations/line.md) nella visualizzazione **[!UICONTROL Argomenti di tendenza]**. La visualizzazione **[!UICONTROL Riga]** viene collegata automaticamente alla visualizzazione **[!UICONTROL Argomenti di tendenza]** e visualizza una riga per l&#39;argomento selezionato.

  ![Visualizzazione della linea dell&#39;argomento di tendenza](assets/trending-topics-line-viz.png)

## Impostazioni

Sono disponibili le seguenti [impostazioni di visualizzazione specifiche](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings).

| Impostazione | Descrizione |
|---|---|
| **[!UICONTROL Visualizza valore effettivo]** | Visualizza il valore effettivo di un argomento. |
| **[!UICONTROL Percentuale di visualizzazione]** | Visualizza la percentuale di un argomento. |
