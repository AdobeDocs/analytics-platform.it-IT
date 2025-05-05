---
description: Utilizza le visualizzazioni Numero di riepilogo e Variazione di riepilogo per visualizzare punti dati importanti in un progetto.
title: Numero riepilogo e Modifica riepilogo
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: ht
source-wordcount: '486'
ht-degree: 100%

---

# Numero riepilogo e Modifica riepilogo

>[!BEGINSHADEBOX]

_Questo articolo documenta le visualizzazioni Numero riepilogo e Modifica riepilogo in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Consulta [Numero riepilogo e Modifica riepilogo](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/visualizations/summary-number-change) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Per un video dimostrativo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualizzazione numero riepilogo e modifica riepilogo](https://video.tv.adobe.com/v/335564/?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]

## Numero di riepilogo {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Numero di riepilogo"
>abstract="Crea una visualizzazione che mostra i totali e i subtotali."

<!-- markdownlint-enable MD034 -->

Utilizza la visualizzazione ![Riepilogo](/help/assets/icons/123.svg) **[!UICONTROL Summary number]** per evidenziare un numero elevato importante in un progetto. Questa visualizzazione si comporta come segue, utilizzando l’origine dati associata:

* Se non è selezionata alcuna cella, viene selezionato il totale della colonna.
* Se è selezionata una cella, viene visualizzato il riepilogo per tale cella.
* Se sono selezionate più celle, viene visualizzata la prima cella selezionata.
* Se è selezionata la colonna, viene preso il valore della prima cella della colonna.

![Visualizzazione Numero di riepilogo](asses/../assets/summary-number.png)

Come parte delle impostazioni di visualizzazione, sono disponibili opzioni specifiche per il numero di Riepilogo.

| Opzione | Definizione |
|--- |--- |
| **[!UICONTROL Abbreviate value]** | Seleziona **[!UICONTROL Abbreviate value]** per abbreviare in modo intelligente il valore numerico. Se questa opzione è selezionata, immetti un numero per definire la quantità di abbreviazione. Ad esempio:<br/><table><tr><td>**Valore originale**</td><td>**Valore abbreviazione**</td><td>**Risultato**</td></tr><tr><td>12.011.141,25 $</td><td>Non selezionato</td><td  align="right">12.011.141,25 $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `0`</td><td align="right">12 milioni $</td></tr><tr><td>12.011.141,25 $</td><td> Selezionato, impostato su `1`</td><td  align="right">12,0 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `2`</td><td align="right">12,01 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `3`</td><td align="right">12,011 milioni $</td></tr></table> |
| **[!UICONTROL Summarize value by]** | Scegli di visualizzare il massimo, il minimo, la media, la mediana o la somma per una selezione di dati. |

## Variazione di riepilogo {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Variazione di riepilogo"
>abstract="Crea una visualizzazione che mostra il delta (variazione) tra due numeri"

<!-- markdownlint-enable MD034 -->


Utilizza la visualizzazione ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL Summary Change]** per visualizzare il delta (variazione) tra due numeri. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html?lang=it) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=it) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=it) option.
-->

Questa visualizzazione si comporta come segue:

* Se non è selezionata alcuna cella, vengono confrontati i valori delle prime due celle della colonna.
* Se è selezionata una cella, viene riportato 0 perché il valore della cella viene confrontato con se stesso e quindi non si verifica alcuna variazione nei valori.
* Se sono selezionate due celle, la prima cella selezionata funge da numeratore e la seconda da denominatore.
* Se sono selezionate più celle, per il confronto vengono considerate solo le prime due celle.
* Se è selezionato un intervallo di celle, vengono confrontate la prima e l’ultima cella selezionata nell’intervallo.
* Se è selezionata la colonna, il primo valore viene confrontato con se stesso, e la variazione risulta quindi pari a 0.


![Visualizzazione delle modifiche di riepilogo che mostra il delta tra due numeri.](assets/summary-change.png)


Come parte delle impostazioni di visualizzazione, sono disponibili **[!UICONTROL Summary change options]** specifiche.

| Opzione | Definizione |
|--- |--- |
| **[!UICONTROL Show percent change]** | Mostra la variazione percentuale tra i 2 numeri. |
| **[!UICONTROL Show raw difference]** | Mostra la differenza grezza tra i 2 numeri. Con questa opzione è inoltre possibile abbreviare i valori e visualizzare fino a 3 posizioni decimali. |
| **[!UICONTROL Abbreviate value]** | Seleziona **[!UICONTROL Abbreviate value]** per abbreviare in modo intelligente il valore modificato. Se questa opzione è selezionata, immetti un numero per definire la quantità di abbreviazione. Ad esempio:<br/><table><tr><td>**Valore originale**</td><td>**Valore abbreviazione**</td><td>**Risultato**</td></tr><tr><td>12.011.141,25 $</td><td>Non selezionato</td><td  align="right">12.011.141,25 $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `0`</td><td align="right">12 milioni $</td></tr><tr><td>12.011.141,25 $</td><td> Selezionato, impostato su `1`</td><td  align="right">12,0 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `2`</td><td align="right">12,01 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `3`</td><td align="right">12,011 milioni $</td></tr></table> |

>[!MORELIKETHIS]
>
>[Aggiungere una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Impostazioni di visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu di scelta rapida della visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
