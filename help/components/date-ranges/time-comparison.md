---
description: 'In Analysis Workspace, il confronto delle date ti consente di prendere una qualsiasi colonna contenente un intervallo di date e di creare un confronto tra date comune, come: anno su anno, trimestre su trimestre, mese su mese, ecc.'
title: Confronto delle date
feature: Calendar
exl-id: 08113536-658f-486b-ac56-6c531240c3c2
role: User
source-git-commit: b196b8c05ba05a3f46d71c10fdcaa2ad8ef0dcd6
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 70%

---

# Confronto delle date

In Analysis Workspace, il confronto delle date ti consente di prendere una qualsiasi colonna contenente un intervallo di date e di creare un confronto tra date comune, come: anno su anno, trimestre su trimestre, mese su mese, ecc.

## Confronto tra periodi temporali

L’analisi richiede contesto e spesso tale contesto viene fornito da un periodo di tempo precedente. Ad esempio, la domanda “Rispetto allo stesso periodo dello scorso anno, quanto stiamo andando meglio/peggio?” è fondamentale per comprendere la propria attività. Il confronto delle date include automaticamente una colonna “differenza” che mostra il cambiamento percentuale, confrontato a un periodo di tempo specificato.

1. Crea una tabella a forma libera, con qualsiasi dimensione e metrica desideri confrontare in un periodo di tempo.
1. Fai clic con il pulsante destro del mouse su una riga di tabella e seleziona **[!UICONTROL Compare time periods]** (Confronta periodi di tempo).

   ![Riga di tabella con periodi di tempo di confronto selezionati](assets/compare-time.png)

   >[!NOTE]
   >
   >Questa opzione accessibile tramite clic con il pulsante destro del mouse è disabilitata per le righe di metrica, di intervallo dati e di dimensione temporale.

1. A seconda di come hai impostato l’intervallo di date della tabella, hai a disposizione queste opzioni per il confronto:

   | Opzione | Descrizione |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Effettua il confronto con la settimana/il mese, ecc... subito precedente a questo intervallo di date. |
   | **[!UICONTROL This week/month/quarter/year last year to this date range]** | Effettua il confronto con il medesimo intervallo di date di un anno fa. |
   | **[!UICONTROL Custom date range to this date range]** | Ti consente di selezionare un intervallo di date personalizzato. |

   >[!NOTE]
   >
   >Quando selezioni un numero di giorni personalizzato, ad esempio 7 ottobre - 20 ottobre (un intervallo di 14 giorni) avrai a disposizione solo 2 opzioni: **[!UICONTROL Prior 14 days before this date range]** (14 giorni precedenti a questo intervallo di dati) e **[!UICONTROL Custom date range to this date range]** (Seleziona intervallo).

1. Il confronto risultante è simile a questo:

   ![Tabella a forma libera che mostra un confronto tra intervalli di date e variazioni percentuali.](assets/compare-time-result.png)

   Le righe nella colonna Modifica percentuale appaiono nere per i valori negativi e verdi per quelli positivi.

1. (Facoltativo) Così come in tutti gli altri progetti di Workspace, puoi creare visualizzazioni sulla base di questi confronti temporali. Ad esempio, questo è un grafico a barre:

   ![Grafico a barre dei progetti Workspace.](assets/compare-time-barchart.png)

   Tieni presente che, per mostrare la modifica della percentuale nel grafico a barre dovrai aver selezionato l’impostazione [!UICONTROL Percentages] (Percentuali) in [!UICONTROL Visualization Settings] (Impostazioni di visualizzazione).

## Aggiungere una colonna Periodo di tempo per il confronto

Ora puoi aggiungere a ciascuna colonna di una tabella un periodo di tempo diverso da quello impostato nel calendario corrente. Questa funzione offre un altro metodo per confrontare le date.

1. Fare clic con il pulsante destro del mouse su una colonna della tabella e selezionare **[!UICONTROL Add time period column]**.

   ![](assets/add-time-period-column.png)

1. A seconda di come hai impostato l’intervallo di date della tabella, hai a disposizione queste opzioni per il confronto:

   | Opzione | Descrizione |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Aggiunge una colonna con settimana/mese/ecc... subito precedente a questo intervallo di date. |
   | **[!UICONTROL This week/month/quarter/year last year to this date range]** | Aggiunge lo stesso intervallo di date, un anno fa. |
   | **[!UICONTROL Custom date range to this date range]** | Ti consente di selezionare un intervallo di date personalizzato. |

   >[!NOTE]
   >
   >Quando selezioni un numero di giorni personalizzato, ad esempio 7 ottobre - 20 ottobre (un intervallo di 14 giorni) avrai a disposizione solo 2 opzioni: **[!UICONTROL Prior 14 days before this date range]** (14 giorni precedenti a questo intervallo di dati) e **[!UICONTROL Custom date range to this date range]** (Seleziona intervallo).

1. Il periodo di tempo verrà inserito nella parte superiore della colonna selezionata:

   ![Tabella a forma libera che mostra le occorrenze per il periodo di calendario corrente e il mese di calendario precedente.](assets/add-time-period-column2.png)

1. Puoi aggiungere tutte le colonne di tempo che desideri, oltre ad abbinare intervalli di date diversi:

   ![Tabella a forma libera che mostra le occorrenze relative al mese corrente, al mese precedente, al mese precedente di un anno fa e a una settimana del mese precedente di un anno fa.](assets/add-time-period-column4.png)

1. Inoltre, puoi ordinare tutte le colonne, azione che modificherà l’ordine dei giorni a seconda della colonna che stai ordinando.

## Allineare le date della colonna affinché inizino sulla stessa riga {#section_5085E200082048CB899C3F355062A733}

Puoi allineare le date di ogni colonna affinché inizino tutte sulla stessa riga.

Ad esempio, quando scegli di allineare le date, se effettui un confronto mese-su-mese tra ottobre e settembre 2016, la colonna a sinistra inizierà con il 1 ottobre e la colonna a destra inizierà con il 1 settembre:

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>Quando utilizzi questa opzione, tieni presente quanto segue:
>
>* Questa impostazione è attivata per impostazione predefinita per tutti i nuovi progetti.
>
>* Questa impostazione si applica all&#39;intera tabella. Ad esempio, se modifichi questa impostazione per un raggruppamento all’interno della tabella, verrà modificata l’impostazione per l’intera tabella.
>

Per abilitare questa impostazione, se non è già abilitata:

1. Nella tabella in cui si desidera allineare le date delle colonne, selezionare l&#39;icona **Impostazioni** nell&#39;intestazione della tabella.

1. Nella scheda [!UICONTROL **Impostazioni**], selezionare **[!UICONTROL Align Dates from each column to all start on the same row (applies to entire table)]**.

![](assets/date-comparison-setting.png)
