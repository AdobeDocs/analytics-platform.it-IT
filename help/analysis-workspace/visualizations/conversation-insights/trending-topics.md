---
description: Utilizza la visualizzazione degli argomenti di tendenza per esplorare gli argomenti di tendenza nelle conversazioni.
title: Argomenti di tendenza
feature: Visualizations
role: User
hide: true
source-git-commit: 137dba69c8827f3b67d5656760d7715437c58b73
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%
---

# Argomenti di tendenza

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="Argomenti di tendenza"
>abstract="Crea una visualizzazione che mostri una suddivisione gerarchica degli argomenti di tendenza, con occorrenze e percentuali, abilitata per l’espansione, per identificare i temi importanti nelle conversazioni."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="Argomenti di tendenza"
>abstract="Analizza gli argomenti di tendenza in base alla metrica di classificazione selezionata. Selezionare gli argomenti per eseguire il drill-down fino a cinque livelli di profondità. Cerca argomenti specifici e confronta gli argomenti con altri intervalli di date."

La visualizzazione ![Feed](/help/assets/icons/Feed.svg) **[!UICONTROL Argomenti di tendenza]** consente di esplorare e analizzare gli argomenti di tendenza come parte degli approfondimenti sulla conversazione.

È possibile cercare argomenti specifici e confrontare il numero e la percentuale di ciascun argomento a ogni livello con altri intervalli di dati.

## Creare e configurare

Per creare e configurare una visualizzazione degli argomenti di tendenza:

1. Aggiungi una visualizzazione ![Feed](/help/assets/icons/Feed.svg) **[!UICONTROL Argomenti di tendenza]**. Consulta [Aggiungere una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Nella configurazione della visualizzazione **[!UICONTROL Argomenti di tendenza]**:

   1. Selezionare una **[!UICONTROL metrica di classificazione]**. Ad esempio: **[!UICONTROL Conversazioni]**.
   1. Facoltativamente, selezionare **[!UICONTROL Imposta attribuzione]** e selezionare **[!UICONTROL Modello]**, **[!UICONTROL Contenitore]** e **[!UICONTROL Intervallo di lookback]**.
   1. Selezionare un livello per **[!UICONTROL Limita livelli argomenti secondari]**. Il valore predefinito è **[!UICONTROL Livello 5]**.

      >[!NOTE]
      >
      >Il livello di argomento secondario **[!UICONTROL Limit]** definisce il numero massimo di livelli da espandere per gli argomenti della visualizzazione. Se non sono disponibili altri argomenti a un livello compreso nel numero massimo definito, verrà visualizzato ![DataUnavailable](/help/assets/icons/DataUnavailable.svg) **[!UICONTROL Nessun argomento trovato]**.

1. Seleziona **[!UICONTROL Build]** per generare la visualizzazione. Selezionare **[!UICONTROL Reimposta]** per ripristinare i valori predefiniti della configurazione.

Per riconfigurare la visualizzazione degli argomenti di tendenza, seleziona ![Modifica](/help/assets/icons/Edit.svg) accanto a **[!UICONTROL Metrica di classificazione: _Metrica di classificazione_ | Livelli argomento: _x_]**.

## Utilizzo

Per utilizzare la visualizzazione:

* Per eseguire il drilling e visualizzare gli argomenti secondari di tendenza per un argomento di livello inferiore, selezionare un argomento di livello specifico.

* Per confrontare gli argomenti con un altro intervallo di date, selezionare un intervallo di date da Confronta con. Per utilizzare un intervallo di date personalizzato:
  * Seleziona Intervallo date personalizzato dal menu a discesa e nella finestra di dialogo Nuovo intervallo di date definisci e salva un intervallo di date personalizzato.
  * Seleziona l’intervallo di date personalizzato.

* Per visualizzare un grafico a linee per la selezione corrente di argomenti, rilascia una visualizzazione [Riga](/help/analysis-workspace/visualizations/line.md) nella visualizzazione **[!UICONTROL Argomenti di tendenza]**. La visualizzazione **[!UICONTROL Riga]** è collegata automaticamente alla visualizzazione **[!UICONTROL Argomenti di tendenza]**.

## Impostazioni

Sono disponibili le seguenti [impostazioni di visualizzazione specifiche](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings).

| Impostazione | Descrizione |
|---|---|
| **[!UICONTROL Visualizza valore effettivo]** | Visualizza il valore effettivo di un argomento. |
| **[!UICONTROL Percentuale di visualizzazione]** | Visualizza la percentuale per un argomento. |



