---
description: Informazioni su come vengono calcolati i totali di Workspace.
title: Totali in Workspace
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: 770320a0b16d26e0755203a3524b000db30cac82
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 20%

---

# Totali in Workspace {#workspace-totals}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="Totale complessivo"
>abstract="Il totale complessivo non è supportato per tabelle o raggruppamenti con righe statiche."

<!-- markdownlint-enable MD034 -->


Nelle tabelle a forma libera viene visualizzata una riga del totale a ogni livello di raggruppamento, la quale può mostrare due totali:

![Tabella a forma libera che evidenzia il totale complessivo e il totale della tabella.](assets/total-row.png)

* **[!UICONTROL Table total]** - Questo totale è in genere uguale o un sottoinsieme di [!UICONTROL Grand total]. Il totale riflette tutti i segmenti di tabella applicati nella tabella a forma libera, inclusa l&#39;opzione [!UICONTROL Include None].
* **[!UICONTROL Grand total]** (**[!UICONTROL out of]** *numero*) - Questo totale rappresenta tutti gli eventi raccolti. Quando un segmento viene applicato a livello di pannello o all’interno della tabella a forma libera, questo totale si regola per riflettere tutti gli eventi che corrispondono ai criteri del segmento.




## Visualizza totali

In ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Column settings]** sono disponibili opzioni per **[!UICONTROL Show totals]** e **[!UICONTROL Show grand total]**. Se queste impostazioni non sono selezionate, i totali vengono rimossi dalla tabella, il che può essere utile nei casi in cui i totali non abbiano senso.


[I totali della riga statica](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) si comportano in modo diverso e sono controllati tramite ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Row Settings]**.

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Show sum of current rows as the total]** | Mostra una somma lato client delle righe nella tabella. Questo totale **non** deduplica metriche quali sessioni o persone. |
| **[!UICONTROL Show grand total]** | Mostra una somma lato server. Questo totale deduplica metriche quali sessioni o persone. |

Vedi [Elementi dimensionali dinamici e statici nelle tabelle a forma libera](column-row-settings/manual-vs-dynamic-rows.md).


## Domande frequenti

| Domande | Risposta |
|---|---|
| Su quali *totali* si basano le percentuali delle colonne grigie? | Questo *totale* dipende dalla selezione dell&#39;impostazione **[!UICONTROL Percentages]** in **[!UICONTROL Row Settings]**:<ul><li>Calcola le percentuali per colonna: questa impostazione è quella predefinita. Le percentuali sono basate sul totale della tabella.</li><li>Calcola le percentuali per riga: le percentuali sono basate sul totale complessivo.</li></ul> |
| In che modo l’impostazione **[!UICONTROL Include "No value"]** (Includi non specificati (Nessuno)) influisce sui totali? | Se l&#39;impostazione **[!UICONTROL Include "No value"]** non è selezionata, la riga **[!UICONTROL No value]** viene rimossa dalla tabella, ovvero dal totale della tabella, e passa a qualsiasi metrica calcolata che utilizza i tipi di metrica [*Total*](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md). |
| Quando si applicano segmenti di tabella personalizzati a una tabella a forma libera, tutte le metriche calcolate e la formattazione condizionale vengono prese in considerazione per il segmento? | Attualmente no. **[!UICONTROL Include "No value"]** è un account per, ma i segmenti di tabella personalizzati non influiscono sui seguenti elementi:<ul><li>L’intervallo massimo/minimo delle colonne utilizzato per la formattazione condizionale viene visualizzato in tutti i dati.</li><li>Metriche calcolate che sfruttano i tipi di metrica **[!UICONTROL Grand total]** (Totale complessivo).</li><li>Metriche calcolate con funzioni che calcolano tra le righe di una tabella a forma libera: Somma colonna, Massimo colonna, Minimo colonna, Conteggio, Media, Mediana, Percentile, Quartile, Conteggio righe, Deviazione standard, Varianza, Cumulativo, Media cumulativa, Varianti di regressione, Punteggio T, Test T, Punteggio Z e Test Z.</li></ul> |
| In Metriche calcolate, cosa riflette il tipo di metrica **[!UICONTROL Grand total]** (Totale complessivo)? | **[!UICONTROL Grand total]** continua a fare riferimento a **[!UICONTROL Grand total]** e non riflette i segmenti applicati a una tabella o a **[!UICONTROL Table total]**. |
| Qual è il totale visualizzato quando i dati vengono copiati e incollati da una tabella a forma libera o scaricati tramite CSV? | La riga del totale riflette solo **[!UICONTROL Table total]** e rispetta l&#39;impostazione della colonna **[!UICONTROL Show totals]**. |
