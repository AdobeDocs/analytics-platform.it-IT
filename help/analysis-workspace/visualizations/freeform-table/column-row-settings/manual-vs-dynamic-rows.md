---
title: Elementi dimensionali dinamici e statici nelle tabelle a forma libera
description: Interagire con elementi dimensionali dinamici e statici nelle tabelle
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
role: User
source-git-commit: 6a279ac39e6b94200ff93ac1a3796d202e6349c7
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 51%

---

# Elementi dimensionali dinamici e statici nelle tabelle a forma libera

Le righe e le colonne nelle tabelle a forma libera possono contenere diversi valori dei componenti. Questi valori possono essere dinamici (cambiare nel tempo) o statici (non cambiare nel tempo), a seconda dell’analisi che desideri generare.

## Elementi dimensionali dinamici

Gli elementi dimensionali dinamici cambiano nel tempo e dipendono dalla metrica in base alla quale viene ordinato nella tabella a forma libera. Gli elementi dimensionali dinamici sono consigliati quando si desidera analizzare gli elementi principali per un determinato periodo di tempo.

Quando rilasci una dimensione in una tabella a forma libera, vengono restituite righe dinamiche. Le righe dinamiche rappresentano gli elementi principali che corrispondono alla dimensione per una metrica e un periodo di tempo specifici. È inoltre possibile rilasciare una dimensione nelle colonne di una tabella a forma libera. Così facendo la dimensione si espande automaticamente nei primi 5 elementi dimensionali.

Ad esempio, quando si trascina la dimensione Tipo di browser nella tabella, gli elementi principali della dimensione (ad esempio Microsoft, Apple, Google, ecc.) sono restituiti nelle righe della tabella in modo dinamico. Se viene rilasciata in una colonna, sono restituiti in modo dinamico i primi cinque elementi della dimensione Tipo di browser.

Gli elementi dimensionali dinamici dispongono dell&#39;opzione filtro righe ![Filtro](/help/assets/icons/Filter.svg) e di una ![Chiusura](/help/assets/icons/Close.svg) e **non** dispongono di un blocco ![BloccoChiuso](/help/assets/icons/LockClosed.svg). <!--do they have the lock icon? --> Quando fai clic su ![Chiudi](/help/assets/icons/Close.svg) accanto a un elemento di dimensione dinamica, viene applicato automaticamente un filtro. Per ulteriori informazioni sull&#39;applicazione di filtri alle tabelle, vedere [Filtrare e ordinare le tabelle](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![Tabella a forma libera che evidenzia l&#39;icona del filtro.](assets/dynamic-items.png)

## Elementi dimensionali statici

Gli elementi dimensionali statici non cambiano con il tempo, sono componenti fissi che vengono sempre restituiti in una tabella a forma libera. Gli elementi dimensionali statici sono consigliati quando si desidera analizzare sempre gli stessi elementi, siano essi campagne o giorni della settimana specifici.

Ogni volta che selezioni e rilasci manualmente valori di componenti specifici (dimensione, metrica, filtro, intervallo di date) in una tabella, il risultato è un elenco statico di righe o colonne.

Ad esempio, quando trascini su specifici elementi della dimensione Tipo di browser, come Microsoft e Apple, questi due elementi specifici vengono sempre inseriti nella tabella.

È inoltre possibile creare elementi dimensionali statici se si sceglie di selezionare **[!UICONTROL Display only selected rows]** dal menu di scelta rapida per le righe selezionate.

Gli elementi dimensionali statici **non** dispongono dell’opzione filtro righe. Su ogni elemento sono invece presenti ![LockClosed](/help/assets/icons/LockClosed.svg) e ![Close](/help/assets/icons/Close.svg). Seleziona ![Chiudi](/help/assets/icons/Close.svg) per rimuovere l&#39;elemento dimensione dalla tabella.

![Tabella a forma libera che mostra il tipo di browser e la riga Microsoft con un&#39;icona di blocco. Nota: questo elemento dimensione è statico e non cambierà con il tempo.](assets/static-items.png)

## Elementi dimensionali misti

È possibile aggiungere alla stessa tabella elementi dimensionali di dimensioni diverse. In questi casi, l&#39;intestazione di riga indica **[!UICONTROL Mixed Dimensions]**. Questi elementi dimensionali sono statici. Ad esempio, è possibile aggiungere elementi dimensionali specifici dalla dimensione Gruppo di browser e altri elementi dimensionali dalla dimensione Nome browser.

![Tabella a forma libera che evidenzia la colonna Dimension misti.](assets/mixed-dimensions.png)

## Righe del totale a forma libera

Le righe dinamiche e statiche si comportano in modo diverso nella riga del totale a forma libera. Per impostazione predefinita:

* Le righe dinamiche vengono sommate lato server e deduplicano metriche quali sessioni o persone.
* Le righe statiche vengono sommate lato client e **non** duplicano le metriche. Per calcolare la riga del totale lato server, modifica l’impostazione della riga in **Mostra totale**. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=it)
