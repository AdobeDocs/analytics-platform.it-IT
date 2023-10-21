---
title: Elementi dimensionali dinamici e statici nelle tabelle a forma libera
description: Interagire con elementi dimensionali dinamici e statici nelle tabelle
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
source-git-commit: ab30cd4e884dbf92d4148e8f81a638a8ea0b63f3
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 81%

---

# Elementi dimensionali dinamici e statici nelle tabelle a forma libera

Le righe e le colonne nelle tabelle a forma libera possono contenere diversi valori dei componenti. Questi valori possono essere dinamici (ovvero cambiare con il tempo) o statici (non cambiare con il tempo), a seconda dell’analisi che desideri generare.

## Elementi dimensionali dinamici

Gli elementi dimensionali dinamici cambiano con il tempo e dipendono dalla metrica per cui si effettua l’ordinamento nella tabella a forma libera. Gli elementi dimensionali dinamici sono consigliati quando si desidera analizzare gli elementi principali per un determinato periodo di tempo.

Quando rilasci una dimensione in una tabella a forma libera, vengono restituite righe dinamiche. Esse rappresentano gli elementi principali che corrispondono alla dimensione per una metrica e un periodo di tempo specifici. È inoltre possibile rilasciare una dimensione nelle colonne di una tabella a forma libera. Così facendo la dimensione si espande automaticamente nei primi 5 elementi dimensionali.

Ad esempio, quando si trascina la dimensione Tipo di browser nella tabella, gli elementi principali della dimensione (ad esempio Microsoft, Apple, Google, ecc.) sono restituiti nelle righe della tabella in modo dinamico. Se viene rilasciata in una colonna, sono restituiti in modo dinamico i primi cinque elementi della dimensione Tipo di browser.

Gli elementi dimensionali dinamici dispongono dell’opzione filtro righe e delle icone X, quindi eseguono le operazioni seguenti: **non** l&#39;icona del lucchetto è presente. <!--do they have the lock icon? --> Quando fai clic sulla x accanto a un elemento di dimensione dinamico, viene applicato automaticamente un filtro. Per ulteriori informazioni sull&#39;applicazione di filtri alle tabelle, vedere [Filtrare e ordinare le tabelle](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![Tabella a forma libera che evidenzia l’icona del filtro.](assets/dynamic-items.png)

## Elementi dimensionali statici

Gli elementi dimensionali statici non cambiano con il tempo, sono componenti fissi che vengono sempre restituiti in una tabella a forma libera. Gli elementi dimensionali statici sono consigliati quando si desidera analizzare sempre gli stessi elementi, siano essi campagne o giorni della settimana specifici.

Ogni volta che selezioni e rilasci manualmente valori di componenti specifici (dimensione, metrica, filtro, intervallo di date) in una tabella, il risultato è un elenco statico di righe o colonne. Puoi inoltre creare elementi dimensionali statici se lo desideri:

* Dalle righe, fai clic con il pulsante destro del mouse > [!UICONTROL Display only selected rows]
* Dalle colonne, fai clic con il pulsante destro del mouse > [!UICONTROL Make item static]

Ad esempio, quando trascini su specifici elementi della dimensione Tipo di browser, come Microsoft e Apple, questi due elementi specifici vengono sempre inseriti nella tabella.

Gli elementi dimensionali statici **non** dispongono dell’opzione filtro righe. Su ogni elemento sono invece presenti le icone lucchetto e X. Fai clic sull’icona X per rimuovere l’elemento dimensionale dalla tabella.

![Una tabella a forma libera che mostra il Tipo di browser e la riga Microsoft con un’icona di blocco. Nota: questo elemento dimensionale è statico e non cambierà con il tempo.](assets/static-items.png)

## Elementi dimensionali misti

È possibile aggiungere alla stessa tabella elementi dimensionali di dimensioni diverse. In questi casi, l’intestazione della riga indica “dimensioni miste”. Questi elementi dimensionali sono statici. Ad esempio, è possibile aggiungere elementi dimensionali specifici dalla dimensione Tipo di browser e altri elementi dimensionali dalla dimensione Browser.

![Una tabella a forma libera che evidenzia la colonna Dimension misti.](assets/mixed-dimensions.png)

## Righe del totale a forma libera

Le righe dinamiche e statiche si comportano in modo diverso nella riga del totale a forma libera. Per impostazione predefinita:

* Le righe dinamiche vengono sommate lato server e deduplicano metriche quali visite o persone
* Le righe statiche vengono sommate lato client e **non** duplicano le metriche. Per calcolare la riga del totale lato server, modifica l’impostazione della riga in **Mostra totale**. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=it)
