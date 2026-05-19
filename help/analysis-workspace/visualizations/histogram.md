---
description: Scopri come utilizzare un istogramma, simile a un grafico a barre, ma che raggruppa i numeri in intervalli.
title: Istogramma
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
autotag-review: '2026-05-19T08:31:33.712Z'
TQID: 'https://experienceleague.adobe.com/X9T4RpAiJ8uL0clPhyjffdl02kwd-k2Jv3O5t6iHfss'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 486
ht-degree: 62%

---

# Istogramma {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Istogramma"
>abstract="Crea una visualizzazione a istogramma per rappresentare la distribuzione dei dati numerici in gruppi di intervalli."


>[!BEGINSHADEBOX]

_In questo articolo viene documentata la visualizzazione Istogramma in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Vedere [Istogramma](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/visualizations/histogram) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]


La visualizzazione ![Istogramma](/help/assets/icons/Histogram.svg) **[!UICONTROL Istogramma]** è simile a una visualizzazione [!UICONTROL Barra], ma raggruppa i numeri in intervalli (bucket). Analytics automatizza la creazione di intervalli di numeri, ma puoi comunque cambiare le impostazioni in [Impostazioni avanzate](#advanced-settings).

## Utilizzo

Per creare un istogramma:

1. Aggiungi una visualizzazione ![Istogramma](/help/assets/icons/Histogram.svg) **[!UICONTROL Istogramma]**. Consulta [Aggiungere una visualizzazione a un pannello](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Trascinare una metrica dall&#39;elenco dei componenti **[!UICONTROL Metriche]** oppure selezionare una metrica dal menu a discesa [!UICONTROL *Aggiungi una metrica*].
1. (facoltativo) Selezionare **[!UICONTROL Mostra impostazioni avanzate]**. Consulta [Impostazioni avanzate](#advanced-settings).
1. Seleziona **[!UICONTROL Genera]**.

>[!NOTE]
>
>Gli istogrammi supportano solo metriche standard; le metriche calcolate non sono supportate.

Nell’esempio seguente, viene utilizzato un istogramma per le sessioni di bucket relative al numero di persone. L’istogramma mostra che la maggior parte delle persone ha tra 16 e 21 sessioni per l’intervallo di date selezionato.

![Istogramma](assets/histogram.png)

## Impostazioni avanzate

Come parte della visualizzazione, sono disponibili impostazioni specifiche dell’istogramma.

| Impostazioni istogramma | Descrizione |
|---|---|
| **[!UICONTROL Avvio bucket]** | Determina con quale bucket inizia l’istogramma. &quot;1&quot; è il valore predefinito. È possibile impostare i numeri iniziali da 0 a infinito (nessun numero negativo). |
| **[!UICONTROL Bucket di metrica]** | Consente di aumentare/diminuire il numero di intervalli di dati (bucket). Il numero massimo consentito è 50. |
| **[!UICONTROL Dimensione bucket metrica]** | Consente di impostare la dimensione di ciascun bucket. Ad esempio, puoi modificare la dimensione del bucket dalla visualizzazione a 1 pagina a 2 visualizzazioni di pagina. |
| **[!UICONTROL Metodo di conteggio]** | Seleziona da **[!UICONTROL Account globale]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Gruppo acquisti]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Opportunità]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Persona]**, **[!UICONTROL Sessione]** o **[!UICONTROL Evento]**. Ad esempio, visualizzazioni di pagina per account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, per sessione, per persona o per evento. |

<!--Russ or Meike - Check Hit Type link above. -->

**Esempi**:

| Bucket iniziale | Bucket metrica | Dimensione bucket di metrica | Risultato |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Istogramma, bucket iniziale 1, bucket metrica 5, dimensione bucket metrica 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Istogramma, bucket iniziale 0, bucket metrica 3, dimensione bucket metrica 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Aggiungi una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Impostazioni di visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu di scelta rapida visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>[Utilizzo di istogrammi per identificare valori di dati imprevisti](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168?profile.language=it)

