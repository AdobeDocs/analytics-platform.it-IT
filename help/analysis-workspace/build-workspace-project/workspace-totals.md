---
description: Modalità di calcolo dei totali in Workspace.
title: Totali in Workspace
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 95%

---


# Totali in Workspace

>[!NOTE]
>
>Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Nelle tabelle a forma libera viene visualizzata una riga del totale a ogni livello di suddivisione, la quale può mostrare due totali:

* **[!UICONTROL Grand Total]** (Totale complessivo), numero “su” grigio: questo totale rappresenta tutti gli hit che sono stati raccolti, talvolta denominati “totale suite di rapporti”. Quando un segmento viene applicato a livello di pannello o all’interno della tabella a forma libera, questo totale si regola per riflettere tutti gli hit che corrispondono ai criteri del segmento.
* **[!UICONTROL Table Total]** (Totale tabella), numero di colore nero: questo totale è in genere uguale o un sottoinsieme del [!UICONTROL Grand Total] (Totale complessivo). Riflette eventuali filtri applicati alla tabella a forma libera, inclusa l’opzione [!UICONTROL Include None] (Includi nessuna).

![](assets/total-row.png)

## Impostazione di visualizzazione del totale

In **[!UICONTROL Column Settings]** (Impostazioni colonna) sono disponibili le opzioni **[!UICONTROL Show Totals]** (Mostra totali) e **[!UICONTROL Show Grand Total]** (Mostra totale complessivo). Se queste impostazioni non sono selezionate, i totali verranno rimossi dalla tabella. Ciò può essere utile nei casi in cui i totali siano privi di senso, ad esempio in alcuni [scenari di metriche calcolate](https://docs.adobe.com/content/help/it-IT/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html).

![](assets/column-settings-total.png)

## Impostazioni Totale riga statica

I totali della [riga statica](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) si comportano in modo diverso e sono controllati in **[!UICONTROL Row Settings]** (Impostazioni riga).

* **[!UICONTROL Show sum of current rows as the total]** (Mostra somma delle righe selezionate come totale): mostra una somma lato client delle righe nella tabella, il che significa che il totale **non** deduplica metriche quali visite o visitatori.
* **[!UICONTROL Show Grand Total]** (Mostra totale complessivo): mostra una somma lato server, il che significa che il totale deduplicherà le metriche quali visite o visitatori.

![](assets/static-rows.png)

## Domande frequenti

| Domande | Risposta |
|---|---|
| Su quale “totale” si basano le percentuali delle colonne grigie? | Questo dipende dall’impostazione **[!UICONTROL Percentages]** (Percentuale) selezionata in **[!UICONTROL Row Settings]** (Impostazioni riga):<ul><li>Calcola le percentuali per colonna: è l’impostazione predefinita. Le percentuali saranno basate sul totale della tabella.</li><li>Calcola le percentuali per riga: le percentuali saranno basate sul totale complessivo.</li></ul> |
| In che modo l’impostazione **[!UICONTROL Include Unspecified (None)]** (Includi non specificati (Nessuno)) influisce sui totali? | Se l’impostazione **[!UICONTROL Include Unspecified (None)]** (Includi non specificati (Nessuno)) non è selezionata, la riga None/Unspecified (Nessuno/Non specificato) verrà rimossa dalla tabella, ovvero dal totale della tabella, e passerà a tutte le metriche calcolate che utilizzano i [tipi di metrica “Totale”](https://docs.adobe.com/content/help/it-IT/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html). |
| Quando si applicano filtri di tabella personalizzati a una tabella a forma libera, tutte le metriche calcolate e la formattazione condizionale vengono applicate al filtro? | Attualmente no. **[!UICONTROL Include Unspecified (None)]** (Includi non specificati (Nessuno)) verranno contabilizzati, ma i filtri di tabella personalizzati non avranno alcun impatto sui seguenti elementi:<ul><li>L’intervallo massimo/minimo delle colonne utilizzato per la formattazione condizionale sarà visualizzato in tutti i dati.</li><li>Metriche calcolate che sfruttano i tipi di metrica **[!UICONTROL Grand Total]** (Totale complessivo).</li><li>Metriche calcolate con funzioni che si calcolano considerando le righe di una tabella a forma libera, ad esempio Column Sum (Somma colonna), Column max (Massimo colonna), Column min (Minimo colonna), Count (Conteggio), Mean (Media), Median (Mediana), Percentile (Percentile), Quartile (Quartile), Row Count (Conteggio righe), Standard Deviation (Deviazione standard), Variance (Varianza), Cumulative (Cumulativa), Cumulative Average (Media cumulativa), Regression variants (Varianti di regressione), T-Score, T-Test, Z-Score, Z-Test.</li></ul> |
| In Metriche calcolate, cosa riflette il tipo di metrica **[!UICONTROL Grand Total]** (Totale complessivo)? | **[!UICONTROL Grand Total]** (Totale complessivo) continua a fare riferimento al **[!UICONTROL Grand Total]** (Totale complessivo) e non riflette i filtri applicati a una tabella o al **[!UICONTROL Table Total]** (Totale tabella). |
| Qual è il totale visualizzato quando i dati vengono copiati e incollati da una tabella a forma libera o scaricati tramite CSV? | La riga del totale riflette solo il **[!UICONTROL Table Total]** (Totale tabella) e rispetta l’impostazione della colonna **[!UICONTROL Show Totals]** (Mostra totali). |

