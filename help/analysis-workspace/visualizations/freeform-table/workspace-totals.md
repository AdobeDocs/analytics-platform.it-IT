---
description: Informazioni su come vengono calcolati i totali di Workspace.
title: Totali in Workspace
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 75%

---

# Totali in Workspace

Nelle tabelle a forma libera viene visualizzata una riga del totale a ogni livello di suddivisione, la quale può mostrare due totali:

* **[!UICONTROL Grand Total]** (numero &quot;su&quot; grigio) - questo totale rappresenta tutti gli eventi che sono stati raccolti. Quando un filtro viene applicato a livello di pannello o all’interno della tabella a forma libera, questo totale si regola per riflettere tutti gli eventi che corrispondono ai criteri del filtro.
* **[!UICONTROL Table Total]** (Totale tabella), numero di colore nero: questo totale è in genere uguale o un sottoinsieme del [!UICONTROL Grand Total] (Totale complessivo). Riflette eventuali filtri applicati alla tabella a forma libera, inclusa l’opzione [!UICONTROL Include None] (Includi nessuna).

![Tabella a forma libera che evidenzia il totale complessivo e il totale della tabella.](assets/total-row.png)

## Impostazione di visualizzazione del totale

In **[!UICONTROL Column Settings]** (Impostazioni colonna) sono disponibili le opzioni **[!UICONTROL Show Totals]** (Mostra totali) e **[!UICONTROL Show Grand Total]** (Mostra totale complessivo). Se queste impostazioni non sono selezionate, i totali verranno rimossi dalla tabella. Ciò può essere utile nei casi in cui i totali siano privi di senso, ad esempio in alcuni [scenari di metriche calcolate](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html?lang=it).

![Opzioni delle impostazioni delle colonne che mostrano i segni di spunta per Mostra totali e Mostra totale sovvenzione.](assets/column-settings-total.png)

## Impostazioni Totale riga statica

I totali della [riga statica](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) si comportano in modo diverso e sono controllati in **[!UICONTROL Row Settings]** (Impostazioni riga).

* **[!UICONTROL Show sum of current rows as the total]** - mostra una somma lato client delle righe nella tabella, il che significa che il totale **non** deduplica metriche quali visite o persone.
* **[!UICONTROL Show Grand Total]**: mostra una somma lato server, il che significa che il totale deduplicherà le metriche quali visite o persone.

![Impostazioni riga che mostrano Mostra totale complessivo selezionato.](assets/static-rows.png)

## Domande frequenti

| Domande | Risposta |
|---|---|
| Su quale “totale” si basano le percentuali delle colonne grigie? | Questo dipende dall’impostazione **[!UICONTROL Percentages]** (Percentuale) selezionata in **[!UICONTROL Row Settings]** (Impostazioni riga):<ul><li>Calcola le percentuali per colonna: è l’impostazione predefinita. Le percentuali saranno basate sul totale della tabella.</li><li>Calcola le percentuali per riga: le percentuali saranno basate sul totale complessivo.</li></ul> |
| In che modo l’impostazione **[!UICONTROL Include Unspecified (None)]** (Includi non specificati (Nessuno)) influisce sui totali? | Se l’impostazione **[!UICONTROL Include Unspecified (None)]** (Includi non specificati (Nessuno)) non è selezionata, la riga None/Unspecified (Nessuno/Non specificato) verrà rimossa dalla tabella, ovvero dal totale della tabella, e passerà a tutte le metriche calcolate che utilizzano i [tipi di metrica “Totale”](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html?lang=it). |
| Quando si applicano filtri di tabella personalizzati a una tabella a forma libera, tutte le metriche calcolate e la formattazione condizionale vengono applicate al filtro? | Attualmente no. **[!UICONTROL Include Unspecified (None)]** (Includi non specificati (Nessuno)) verranno contabilizzati, ma i filtri di tabella personalizzati non avranno alcun impatto sui seguenti elementi:<ul><li>L’intervallo massimo/minimo delle colonne utilizzato per la formattazione condizionale sarà visualizzato in tutti i dati.</li><li>Metriche calcolate che sfruttano i tipi di metrica **[!UICONTROL Grand Total]** (Totale complessivo).</li><li>Metriche calcolate con funzioni che si calcolano considerando le righe di una tabella a forma libera, ad esempio Column Sum (Somma colonna), Column max (Massimo colonna), Column min (Minimo colonna), Count (Conteggio), Mean (Media), Median (Mediana), Percentile (Percentile), Quartile (Quartile), Row Count (Conteggio righe), Standard Deviation (Deviazione standard), Variance (Varianza), Cumulative (Cumulativa), Cumulative Average (Media cumulativa), Regression variants (Varianti di regressione), T-Score, T-Test, Z-Score, Z-Test.</li></ul> |
| In Metriche calcolate, cosa riflette il tipo di metrica **[!UICONTROL Grand Total]** (Totale complessivo)? | **[!UICONTROL Grand Total]** (Totale complessivo) continua a fare riferimento al **[!UICONTROL Grand Total]** (Totale complessivo) e non riflette i filtri applicati a una tabella o al **[!UICONTROL Table Total]** (Totale tabella). |
| Qual è il totale visualizzato quando i dati vengono copiati e incollati da una tabella a forma libera o scaricati tramite CSV? | La riga del totale riflette solo il **[!UICONTROL Table Total]** (Totale tabella) e rispetta l’impostazione della colonna **[!UICONTROL Show Totals]** (Mostra totali). |
