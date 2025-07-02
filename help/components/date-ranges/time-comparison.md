---
description: Scopri come utilizzare il confronto delle date in Analysis Workspace, che consente di prendere una qualsiasi colonna contenente un intervallo di date e creare un confronto tra date comune.
title: Confronto delle date
feature: Calendar
exl-id: 08113536-658f-486b-ac56-6c531240c3c2
role: User
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 23%

---

# Confronto delle date

Il confronto delle date in Analysis Workspace consente di prendere una qualsiasi colonna contenente un intervallo di date e di creare un confronto tra date comune, ad esempio: anno su anno, trimestre su trimestre, mese su mese, ecc.

## Confronto tra periodi temporali

L’analisi richiede contesto e spesso tale contesto viene fornito da un periodo di tempo precedente. Ad esempio, la domanda *Quanto stai facendo meglio o peggio rispetto a questo periodo dell&#39;anno scorso?* è fondamentale per comprendere la tua attività. Il confronto delle date include automaticamente una colonna *differenza* che mostra la variazione percentuale rispetto a un periodo di tempo specificato.

1. Crea una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), con tutte le dimensioni e le metriche che desideri confrontare in un periodo di tempo.
1. Aprire il menu di scelta rapida per una riga di tabella e selezionare **[!UICONTROL Compare time periods]**.

   ![Riga di tabella con periodi di tempo di confronto selezionati](assets/compare-time.png)

   >[!NOTE]
   >
   >Questa opzione del menu di scelta rapida è disabilitata per le righe di metrica, di intervallo di date e di dimensione temporale.

1. A seconda di come hai impostato l’intervallo di date della tabella, hai a disposizione queste opzioni per il confronto:

   | Opzione | Descrizione |
   |---|---|
   | **[!UICONTROL Prior *x *settimane/mesi/trimestri/anni a questo intervallo di date]** | Confronta con l’intervallo di date selezionato immediatamente prima di questo intervallo di date. |
   | **[!UICONTROL These x weeks / months / quarters / years last year to this date range]** | Confronta con lo stesso intervallo di date di un anno fa. |
   | **[!UICONTROL Custom date range to this date range]** | Consente di definire un intervallo di date personalizzato. |

   >[!NOTE]
   >
   >Quando selezioni un numero di giorni personalizzato, ad esempio 7 ottobre - 20 ottobre (un intervallo di 14 giorni) avrai a disposizione solo 2 opzioni: **[!UICONTROL Prior 14 days before this date range]** (14 giorni precedenti a questo intervallo di dati) e **[!UICONTROL Custom date range to this date range]** (Seleziona intervallo).

1. Il confronto risultante è simile a questo:

   ![Tabella a forma libera che mostra un confronto tra intervalli di date e variazioni percentuali.](assets/compare-time-result.png)

   Le righe della colonna Variazione percentuale vengono visualizzate in rosso per i valori negativi e in verde per i valori positivi.

## Aggiungere una colonna Periodo di tempo per il confronto

È ora possibile aggiungere a ogni colonna di una tabella un periodo di tempo diverso da quello impostato nel calendario.

1. Fare clic con il pulsante destro del mouse su una colonna della tabella e selezionare **[!UICONTROL Add time period column]**.

   ![](assets/add-time-period-column.png)

1. A seconda di come hai impostato l’intervallo di date della tabella, hai a disposizione queste opzioni per il confronto:

   | Opzione | Descrizione |
   |---|---|
   | **[!UICONTROL Prior *x *settimane/mesi/trimestri/anni a questo intervallo di date]** | Aggiungi una colonna con settimana/mese/ecc. subito precedente a questo intervallo di date. |
   | **[!UICONTROL These *x *settimane/mesi/trimestri/anni ultimo anno a questo intervallo di date]** | Aggiungi lo stesso intervallo di date un anno fa. |
   | **[!UICONTROL Custom date range to this date range]** | Consentono di creare un intervallo di date personalizzato. |

   >[!NOTE]
   >
   >Quando selezioni un numero di giorni personalizzato, ad esempio 7 ottobre - 20 ottobre (un intervallo di 14 giorni) avrai a disposizione solo 2 opzioni: **[!UICONTROL Prior 14 days before this date range]** (14 giorni precedenti a questo intervallo di dati) e **[!UICONTROL Custom date range to this date range]** (Seleziona intervallo).

1. Il periodo di tempo viene inserito sopra la colonna selezionata:

   ![Tabella a forma libera che mostra le occorrenze per il periodo di calendario corrente e il mese di calendario precedente.](assets/add-time-period-column2.png)

1. Puoi aggiungere tutte le colonne di tempo che desideri, oltre ad abbinare intervalli di date diversi:

1. Inoltre, è possibile ordinare in base a ciascuna colonna, cambiando l&#39;ordine dei giorni a seconda della colonna in cui si esegue l&#39;ordinamento.

## Allineare le date della colonna affinché inizino sulla stessa riga

Puoi allineare le date di ogni colonna affinché inizino tutte sulla stessa riga.

Ad esempio, effettui un confronto giorno dopo giorno per l’ultima settimana (che termina il 5 ottobre 2024) e la settimana precedente. Per impostazione predefinita, la colonna a sinistra inizia il 22 settembre e la colonna a destra il 29 settembre.

![Date non allineate](assets/not-align-dates.png)

È possibile abilitare **[!UICONTROL Align dates from each column to all start on the same row]** in [Impostazioni](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1) affinché la visualizzazione a forma libera allinei le date delle colonne affinché inizino sulla stessa riga.

![](assets/align-dates.png)

Quando utilizzi questa opzione, tieni presente quanto segue:

* Questa impostazione è attivata per impostazione predefinita per tutti i nuovi progetti.

* Questa impostazione si applica all&#39;intera tabella. Ad esempio, se modifichi questa impostazione per un raggruppamento all’interno della tabella, l’impostazione viene applicata all’intera tabella.

