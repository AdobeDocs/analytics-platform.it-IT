---
description: Utilizza le visualizzazioni Numero di riepilogo e Variazione di riepilogo per visualizzare punti dati importanti in un progetto.
title: Numero Di Riepilogo E Variazione Di Riepilogo
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
autotag-review: '2026-05-19T08:30:25.509Z'
TQID: 'https://experienceleague.adobe.com/S9PlaFSE-szemwSU8Cehhfxc9r0bem1qyxfI9S8ohXg'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 543
ht-degree: 47%

---

# Numero e variazione di riepilogo

>[!BEGINSHADEBOX]

_In questo articolo vengono documentate le visualizzazioni Numero riepilogo e Modifica riepilogo in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Vedere [Numero riepilogo e Modifica riepilogo](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/visualizations/summary-number-change) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Per un video dimostrativo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualizzazione numero riepilogo e modifica riepilogo](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/analysis-workspace/visualizations/use-summary-visualizations){target="_blank"}.

>[!ENDSHADEBOX]

## Numero di riepilogo {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Numero di riepilogo"
>abstract="Crea una visualizzazione che mostra i totali e i subtotali."

<!-- markdownlint-enable MD034 -->

Utilizza la visualizzazione ![Riepiloga](/help/assets/icons/123.svg) **[!UICONTROL Numero riepilogo]** per evidenziare un numero elevato importante in un progetto. Questa visualizzazione si comporta come segue, utilizzando l’origine dati associata:

* Seleziona il totale della colonna se non è selezionata alcuna cella.
* Se è selezionata una singola cella, viene visualizzato il relativo riepilogo.
* Se sono selezionate più celle, viene visualizzata la prima cella selezionata.
* Se la colonna è selezionata, viene selezionato il primo valore di cella della colonna.

![Visualizzazione Numero di riepilogo](asses/../assets/summary-number.png)

Come parte delle impostazioni di visualizzazione, sono disponibili opzioni specifiche per il numero di Riepilogo.

| Opzione | Definizione |
|--- |--- |
| **[!UICONTROL Abbrevia valore]** | Seleziona **[!UICONTROL Abbrevia valore]** per abbreviare in modo intelligente il valore numerico. Se questa opzione è selezionata, immetti un numero per definire la quantità di abbreviazione. Ad esempio:<br/><table><tr><td>**Valore originale**</td><td>**Valore abbreviazione**</td><td>**Risultato**</td></tr><tr><td>12.011.141,25 $</td><td>Non selezionato</td><td  align="right">12.011.141,25 $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `0`</td><td align="right">12 milioni $</td></tr><tr><td>12.011.141,25 $</td><td> Selezionato, impostato su `1`</td><td  align="right">12,0 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `2`</td><td align="right">12,01 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `3`</td><td align="right">12,011 milioni $</td></tr></table> |
| **[!UICONTROL Riepiloga valore per]** | Scegli di visualizzare il massimo, il minimo, la media, la mediana o la somma per una selezione di dati. |

## Variazione di riepilogo {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Variazione di riepilogo"
>abstract="Crea una visualizzazione che mostra il delta (variazione) tra due numeri"

<!-- markdownlint-enable MD034 -->


Utilizza la visualizzazione ![SpostaSuGiù](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL Variazione di riepilogo]** per mostrare il delta (variazione) tra due numeri. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

Questa visualizzazione si comporta come segue:

* Se non è selezionata alcuna cella, vengono confrontati i primi due valori di cella della colonna.
* Se è selezionata una cella, viene visualizzato 0 in quanto confronta il valore della cella con se stessa.
* Se sono selezionate due celle, la prima cella selezionata viene considerata come numeratore e la seconda come denominatore.
* Se sono selezionate più di due celle, vengono considerate solo le prime due per il confronto.
* Se è selezionato un intervallo di celle, la prima viene confrontata con le ultime celle selezionate nell&#39;intervallo.
* Se la colonna è selezionata, il primo valore viene confrontato con se stesso, il che mostra una modifica di 0.


![Visualizzazione delle modifiche di riepilogo che mostra il delta tra due numeri.](assets/summary-change.png)


Come parte delle impostazioni di visualizzazione, sono disponibili **[!UICONTROL opzioni di modifica di riepilogo]** specifiche.

| Opzione | Definizione |
|--- |--- |
| **[!UICONTROL Mostra variazione percentuale]** | Mostra la variazione percentuale tra i 2 numeri. |
| **[!UICONTROL Mostra differenza raw]** | Mostra la differenza grezza tra i 2 numeri. Con questa opzione è inoltre possibile abbreviare i valori e visualizzare fino a 3 posizioni decimali. |
| **[!UICONTROL Abbrevia valore]** | Selezionare **[!UICONTROL Abbrevia valore]** per abbreviare in modo intelligente il valore modificato. Se questa opzione è selezionata, immetti un numero per definire la quantità di abbreviazione. Ad esempio:<br/><table><tr><td>**Valore originale**</td><td>**Valore abbreviazione**</td><td>**Risultato**</td></tr><tr><td>12.011.141,25 $</td><td>Non selezionato</td><td  align="right">12.011.141,25 $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `0`</td><td align="right">12 milioni $</td></tr><tr><td>12.011.141,25 $</td><td> Selezionato, impostato su `1`</td><td  align="right">12,0 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `2`</td><td align="right">12,01 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `3`</td><td align="right">12,011 milioni $</td></tr></table> |

>[!MORELIKETHIS]
>
>[Aggiungi una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Impostazioni di visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu di scelta rapida della visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
