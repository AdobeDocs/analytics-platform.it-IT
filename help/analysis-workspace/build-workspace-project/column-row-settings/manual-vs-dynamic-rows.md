---
title: Elementi dimensione dinamici e statici nelle tabelle a forma libera
description: Come interagire con gli elementi dimensionali dinamici e statici nelle tabelle.
translation-type: tm+mt
source-git-commit: cee89d021e9cd034246fe9367bc8910dac7ca7cf
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 9%

---


# Elementi dimensione dinamici e statici nelle tabelle a forma libera

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Nelle tabelle a forma libera, le righe e le colonne possono contenere diversi valori dei componenti. Questi valori possono essere dinamici (cambiare con il tempo) o statici (non cambiare con il tempo), a seconda dell&#39;analisi che si desidera generare.

## Elementi dimensione dinamici

Gli elementi dimensione dinamici cambiano con il tempo e dipendono dalla metrica ordinata dalla tabella a forma libera. Gli elementi dimensionali dinamici sono preferiti quando si desidera analizzare gli elementi principali per un determinato periodo di tempo.

Quando rilasci una dimensione in una tabella a forma libera, vengono restituite righe dinamiche. Rappresentano gli elementi principali che corrispondono alla dimensione per una metrica e un periodo di tempo specifici. È inoltre possibile rilasciare una dimensione nelle colonne di tabella a forma libera e la dimensione si espande automaticamente nei primi 5 elementi dimensionali.

Ad esempio, quando si trascina la dimensione Tipo browser nella tabella, gli elementi principali della dimensione Tipo browser (ad esempio, Microsoft, Apple, Google, ecc.) tornare alle righe della tabella in modo dinamico. Se viene rilasciata in una colonna, i primi cinque elementi dimensionali del tipo di browser torneranno in modo dinamico.

Gli elementi dimensione dinamica dispongono dell&#39;opzione filtro riga e **not** dispongono di icone di blocco e X.

![](assets/dynamic-items.png)

## Elementi dimensione statici

Gli elementi dimensionali statici non cambiano con il tempo; sono componenti fissi che vengono sempre restituiti in una tabella a forma libera. Gli elementi dimensione statica sono preferiti quando si desidera analizzare sempre lo stesso elemento, siano essi campagne specifiche o giorni specifici della settimana.

Ogni volta che si selezionano e si rilasciano manualmente valori di componenti specifici (dimensione, metrica, segmento, intervallo di date) in una tabella, il risultato è un elenco statico di righe o colonne. È inoltre possibile creare elementi dimensionali statici se si sceglie di:

* Da righe, fate clic con il pulsante destro del mouse > [!UICONTROL Display only selected rows]
* Da colonne, fare clic con il pulsante destro del mouse > [!UICONTROL Make item static]

Ad esempio, quando si trascina su specifici elementi del tipo di browser come Microsoft e Apple, questi due elementi specifici vengono sempre inseriti nella tabella.

Gli elementi dimensione statici **not** dispongono dell’opzione filtro righe. Al contrario, su ogni elemento sono presenti le icone Blocca e X. Fare clic sull&#39;icona X per rimuovere l&#39;elemento dimensione dalla tabella.

![](assets/static-items.png)

## Elementi dimensionali misti

È possibile aggiungere alla stessa tabella elementi Dimension di dimensioni diverse. In questi casi, l’intestazione della riga indica &quot;Dimension misti&quot;. Questi elementi dimensione sono statici. Ad esempio, aggiungere elementi dimensionali specifici dalla dimensione Tipo browser e altri elementi dimensionali dalla dimensione Browser.

![](assets/mixed-dimensions.png)

## Righe totali a forma libera

Le righe dinamiche e statiche si comportano in modo diverso nella riga totale a forma libera. Per impostazione predefinita:

* Le righe dinamiche vengono sommate con metriche lato server e deduplicate, come visite o visitatori
* Le righe statiche vengono sommate sul lato client e **not** deduplicare le metriche. Per calcolare la riga totale lato server, modificare l&#39;impostazione Riga in **Mostra totale complessivo**. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html)

