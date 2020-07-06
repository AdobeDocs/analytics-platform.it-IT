---
description: 'In Analysis Workspace, il confronto delle date ti consente di prendere una qualsiasi colonna contenente un intervallo di date e di creare un confronto tra date comune, come: anno su anno, trimestre su trimestre, mese su mese, ecc.'
title: Confronto delle date
uuid: ef18f9d9-b6ad-4859-b7c9-9750ca0df519
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 95%

---


# Confronto delle date

>[!NOTE]
>
>Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

In Analysis Workspace, il confronto delle date ti consente di prendere una qualsiasi colonna contenente un intervallo di date e di creare un confronto tra date comune, come: anno su anno, trimestre su trimestre, mese su mese, ecc.

## Confronto tra periodi temporali

L’analisi richiede contesto e spesso tale contesto viene fornito da un periodo di tempo precedente. Ad esempio, la domanda “Rispetto allo stesso periodo dello scorso anno, quanto stiamo andando meglio/peggio?” è fondamentale per comprendere la propria attività. Il confronto delle date include automaticamente una colonna “differenza” che mostra il cambiamento percentuale, confrontato a un periodo di tempo specificato.

1. Crea una tabella a forma libera, con qualsiasi dimensione e metrica desideri confrontare in un periodo di tempo.
1. Fai clic con il pulsante destro del mouse su una riga di tabella e seleziona **[!UICONTROL Compare Time Periods]** (Confronta periodi di tempo).

   ![](assets/compare-time.png)

   >[!IMPORTANT]
   >
   >Questa opzione accessibile tramite clic con il pulsante destro del mouse è disabilitata per le righe di metrica, di intervallo dati e di dimensione temporale.

1. A seconda di come hai impostato l’intervallo di date della tabella, hai a disposizione queste opzioni per il confronto:

   | Opzione | Descrizione |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Effettua il confronto con la settimana/il mese, ecc... subito precedente a questo intervallo di date. |
   | **[!UICONTROL This week/month/quarter/year last year]** | Effettua il confronto con il medesimo intervallo di date di un anno fa. |
   | **[!UICONTROL Select range]** | Ti consente di selezionare un intervallo di date personalizzato. |

   >[!NOTE]
   >
   >Quando selezioni un numero di giorni personalizzato, ad esempio 7 ottobre - 20 ottobre (un intervallo di 14 giorni) avrai a disposizione solo 2 opzioni: **[!UICONTROL Prior 14 days before this date range]** (14 giorni precedenti a questo intervallo di dati) e **[!UICONTROL Select range]** (Seleziona intervallo).

1. Il confronto risultante è simile a questo:

   ![](assets/compare-time-result.png)

   Le righe nella colonna Modifica percentuale appaiono nere per i valori negativi e verdi per quelli positivi.

1. (Facoltativo) Così come in tutti gli altri progetti di Workspace, puoi creare visualizzazioni sulla base di questi confronti temporali. Ad esempio, questo è un grafico a barre:

   ![](assets/compare-time-barchart.png)

   Tieni presente che, per mostrare la modifica della percentuale nel grafico a barre dovrai aver selezionato l’impostazione [!UICONTROL Percentages] (Percentuali) in [!UICONTROL Visualization Settings] (Impostazioni di visualizzazione).

## Aggiungere una colonna Periodo di tempo per il confronto

Ora puoi aggiungere a ciascuna colonna di una tabella un periodo di tempo diverso da quello impostato nel calendario corrente. Questa funzione offre un altro metodo per confrontare le date.

1. Fai clic con il pulsante destro del mouse su una colonna della tabella e seleziona **[!UICONTROL Add Time Period Column]**![](assets/add-time-period-column.png) (Aggiungi una colonna periodo di tempo)

1. A seconda di come hai impostato l’intervallo di date della tabella, hai a disposizione queste opzioni per il confronto:

   | Opzione | Descrizione |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Aggiunge una colonna con settimana/mese/ecc... subito precedente a questo intervallo di date. |
   | **[!UICONTROL This week/month/quarter/year last year]** | Aggiunge lo stesso intervallo di date, un anno fa. |
   | **[!UICONTROL Select range]** | Ti consente di selezionare un intervallo di date personalizzato. |

   >[!NOTE]
   >
   >Quando selezioni un numero di giorni personalizzato, ad esempio 7 ottobre - 20 ottobre (un intervallo di 14 giorni) avrai a disposizione solo 2 opzioni: **[!UICONTROL Prior 14 days before this date range]** (14 giorni precedenti a questo intervallo di dati) e **[!UICONTROL Select range]** (Seleziona intervallo).

1. Il periodo di tempo verrà inserito nella parte superiore della colonna selezionata:

   ![](assets/add-time-period-column2.png)

1. Puoi aggiungere tutte le colonne di tempo che desideri, oltre ad abbinare intervalli di date diversi:

   ![](assets/add-time-period-column4.png)

1. Inoltre, puoi ordinare tutte le colonne, azione che modificherà l’ordine dei giorni a seconda della colonna che stai ordinando.

## Allineare le date della colonna affinché inizino sulla stessa riga {#section_5085E200082048CB899C3F355062A733}

Una nuova impostazione per tutte le tabelle consente di **[!UICONTROL Align Dates from each column to all start on the same row (applies to entire table)]** (Allineare le date della colonna affinché inizino sulla stessa riga; si applica all’intera tabella). “Si applica all’intera tabella” significa che se effettui, ad esempio, una suddivisione nella tabella, e se cambi questa impostazione per la suddivisione, questa modificherà l’impostazione per tutta la tabella.

![](assets/date-comparison-setting.png)

>[!IMPORTANT]
>
>Questa impostazione è **disabilitata** (non selezionata) per tutti i progetti esistenti ed **abilitata** (selezionata) per tutti i nuovi progetti.

Ad esempio: Quando scegli di allineare le date, se effettui un confronto mese-su-mese tra ottobre e settembre 2016, la colonna a sinistra inizierà con il 1 ottobre e la colonna a destra inizierà con il 1 settembre:

![](assets/add-time-period-column3.png)

<!-- 

<p>See Jonny Moon's email from November 3. </p>

 -->

