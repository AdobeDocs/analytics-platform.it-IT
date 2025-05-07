---
description: Informazioni su come vengono calcolati i totali di Workspace.
title: Totali in Workspace
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: 770320a0b16d26e0755203a3524b000db30cac82
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 78%

---

# Totali in Workspace {#workspace-totals}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="Totale complessivo"
>abstract="Il totale complessivo non è supportato per tabelle o raggruppamenti con righe statiche"

<!-- markdownlint-enable MD034 -->


Nelle tabelle a forma libera viene visualizzata una riga del totale a ogni livello di raggruppamento, la quale può mostrare due totali:

![Tabella a forma libera che evidenzia il totale complessivo e il totale della tabella.](assets/total-row.png)

* **[!UICONTROL Table total]** ➊ - Questo totale è in genere uguale o un sottoinsieme del [!UICONTROL Grand total]. Il totale riflette tutti i segmenti di tabella applicati nella tabella a forma libera, inclusa l&#39;opzione [!UICONTROL Include None].
* **[!UICONTROL Grand total]** (**[!UICONTROL out of]** *numero*) ➋ - Questo totale rappresenta tutti gli eventi raccolti. Quando un segmento viene applicato a livello di pannello o all’interno della tabella a forma libera, questo totale si regola per riflettere tutti gli eventi che corrispondono ai criteri del segmento.




## Visualizzare i totali

In ![Impostazioni](/help/assets/icons/Setting.svg) **[!UICONTROL Column settings]** sono disponibili le opzioni **[!UICONTROL Show totals]** and **[!UICONTROL Show grand total]**. Se queste impostazioni non sono selezionate, i totali vengono rimossi dalla tabella, il che può essere utile nei casi in cui i totali non abbiano senso.


I totali della [riga statica](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) si comportano in modo diverso e sono controllati in ![Impostazioni](/help/assets/icons/Setting.svg) **[!UICONTROL Row Settings]**.

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Show sum of current rows as the total]** | Mostra una somma lato client delle righe nella tabella. Questo totale **non** deduplica metriche quali sessioni o persone. |
| **[!UICONTROL Show grand total]** | Mostra una somma lato server. Questo totale deduplica metriche quali sessioni o persone. |

Consulta [Elementi dimensionali dinamici e statici nelle tabelle a forma libera](column-row-settings/manual-vs-dynamic-rows.md).


## Domande frequenti

| Domande | Risposta |
|---|---|
| Su quale *totale* si basano le percentuali delle colonne grigie? | Il *totale* dipende dall’impostazione **[!UICONTROL Percentages]** selezionata in **[!UICONTROL Row Settings]**:<ul><li>Calcola le percentuali per colonna: questa impostazione è quella predefinita. Le percentuali saranno basate sul totale della tabella.</li><li>Calcola le percentuali per riga: le percentuali saranno basate sul totale complessivo.</li></ul> |
| In che modo l’impostazione **[!UICONTROL Include "No value"]** (Includi non specificati (Nessuno)) influisce sui totali? | Se l’impostazione **[!UICONTROL Include "No value"]** non è selezionata, la riga **[!UICONTROL No value]** verrà rimossa dalla tabella, ovvero dal totale della tabella, e passerà a tutte le metriche calcolate che utilizzano i tipi di metrica [*Totale*](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md). |
| Quando si applicano segmenti di tabella personalizzati a una tabella a forma libera, tutte le metriche calcolate e la formattazione condizionale vengono prese in considerazione per il segmento? | Attualmente no. **[!UICONTROL Include "No value"]** è un account per, ma i segmenti di tabella personalizzati non influiscono sui seguenti elementi:<ul><li>Intervallo max/min delle colonne utilizzato per la formattazione condizionale considera tutti i dati.</li><li>Metriche calcolate che sfruttano i tipi di metrica **[!UICONTROL Grand total]** (Totale complessivo).</li><li>Metriche calcolate con funzioni che si calcolano considerando le righe di una tabella a forma libera, ad esempio Column Sum (Somma colonna), Column max (Massimo colonna), Column min (Minimo colonna), Count (Conteggio), Mean (Media), Median (Mediana), Percentile (Percentile), Quartile (Quartile), Row Count (Conteggio righe), Standard Deviation (Deviazione standard), Variance (Varianza), Cumulative (Cumulativa), Cumulative Average (Media cumulativa), Regression variants (Varianti di regressione), T-Score, T-Test, Z-Score e Z-Test.</li></ul> |
| In Metriche calcolate, cosa riflette il tipo di metrica **[!UICONTROL Grand total]** (Totale complessivo)? | **[!UICONTROL Grand total]** continua a fare riferimento a **[!UICONTROL Grand total]** e non riflette i segmenti applicati a una tabella o a **[!UICONTROL Table total]**. |
| Qual è il totale visualizzato quando i dati vengono copiati e incollati da una tabella a forma libera o scaricati tramite CSV? | La riga del totale riflette solo il **[!UICONTROL Table total]** e rispetta l’impostazione della colonna **[!UICONTROL Show totals]**. |
