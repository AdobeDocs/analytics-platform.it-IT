---
description: Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella.
title: Impostazioni riga
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 88%

---


# Impostazioni riga

>[!NOTE]
>
>Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella.

In una tabella, puoi utilizzare anche le [azioni pulsante destro](/help/analysis-workspace/visualizations/freeform-table.md) per gestire le righe selezionate.

Per accedere alle impostazioni di riga, fai clic sull’icona Impostazioni accanto a una dimensione, a un segmento, a una metrica, a un periodo di tempo o a un’interruzione in ognuna di queste:

![](assets/row-settings.png)

| Impostazione delle righe | Descrizione |
|--- |--- |
| Confronto date | Allinea le date di ogni colonna affinché inizino tutte sulla stessa riga.   Quando scegli di allineare le date, ad esempio in un confronto mese-su-mese tra ottobre e settembre 2016, la colonna a sinistra inizierà con il 1 ottobre e la colonna a destra inizierà con il 1 settembre.<br>Disabilitata per impostazione predefinita. |
| Percentuali | Calcola percentuali per riga Nelle tabelle a forma libera forza il calcolo delle percentuali delle celle di una riga, anziché di una colonna. Questo è utile in particolare per le percentuali di tendenza.<br>È attivata per impostazione predefinita quando si usa l’icona Visualizza. |
| Totali colonna | Queste impostazioni vengono visualizzate solamente con [static rows](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) (when you have selected a finite set of items), not with dynamic rows (i.e., when you drop in a dimension that shows all items).<ul><li>**[!UICONTROL Show sum of current rows as the total]** (Mostra somma delle righe selezionate come totale): mostra una somma lato client delle righe nella tabella, il che significa che il totale **non** deduplica metriche quali visite o visitatori.</li><li>**[!UICONTROL Show Grand Total]** (Mostra totale complessivo): mostra una somma lato server, il che significa che il totale deduplicherà le metriche quali visite o visitatori.</li></ul> |
| Suddivisioni | **[!UICONTROL Breakdown by position]** (Suddivisione per posizione): È possibile mostrare le suddivisioni in base a una posizione fissa in una tabella a forma libera. Ad esempio, puoi specificare di suddividere sempre le prime sette righe.<br>(In precedenza, i valori elencati nella suddivisione erano “bloccati”. Ciò portava a una situazione in cui, ad esempio, se eseguivi una suddivisione di Data per Pagina, ottenevi un elenco delle prime 50 pagine per l’intervallo date selezionato. Se avessi salvato questo rapporto e lo avessi eseguito di nuovo un mese più tardi, le prime 50 pagine sarebbero probabilmente cambiate. Analysis Workspace utilizzava comunque i risultati della suddivisione originale e restituiva le stesse pagine, ma con il mese corrente come intervallo di date.)<br>Per eseguire suddivisioni sulla base di una posizione fissa: 1. Suddividi alcune righe nella tua tabella. 2. Fai clic sull’icona Impostazioni (ingranaggio) accanto alla riga della tabella che desideri mettere in posizione fissa. 3. Spunta la casella di controllo accanto a Suddivisione per posizione. 4. Modifica l’ordinamento o l’intervallo di date e osserva come ora le suddivisioni sono correlate alla posizione della riga e non alle righe a codifica fissa.<br>Disabilitata per impostazione predefinita. |