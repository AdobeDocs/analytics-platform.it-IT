---
title: Valori di dimensione dinamici e statici
description: Come interagire con i valori di dimensione dinamici e statici nelle tabelle.
translation-type: tm+mt
source-git-commit: 0477302df92ccab30d9f3a45cc7b22f2112a0c70
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 9%

---


# Valori di dimensione dinamici e statici nelle tabelle a forma libera

>[!NOTE] Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Nelle tabelle a forma libera, le righe e le colonne possono contenere diversi valori dei componenti. Questi valori possono essere dinamici (cambiare con il tempo) o statici (non cambiare con il tempo), a seconda dell&#39;analisi che si desidera generare.

## Valori di dimensione dinamici

I valori delle dimensioni dinamiche cambiano con il tempo e dipendono dalla metrica ordinata dalla tabella a forma libera. I valori di dimensione dinamica sono preferiti quando si desidera analizzare gli elementi principali per un determinato periodo di tempo.

Quando rilasci una dimensione in una tabella a forma libera, vengono restituite righe dinamiche. Rappresentano gli elementi principali che corrispondono alla dimensione per una metrica e un periodo di tempo specifici. È inoltre possibile rilasciare una dimensione nelle colonne di tabella a forma libera e la dimensione si espande automaticamente nei primi 5 valori di dimensione.

Ad esempio, quando si trascina la dimensione Tipo browser nella tabella, i primi valori della dimensione Tipo browser (ad esempio, Microsoft, Apple, Google, ecc.) tornare alle righe della tabella in modo dinamico. Se rilasciata in una colonna, i primi cinque valori della dimensione Tipo browser restituiranno dinamicamente.

I valori di dimensione dinamica dispongono dell&#39;opzione filtro riga e **non** sono presenti icone blocco e X.

## Valori di dimensione statici

I valori di dimensione statici non cambiano con il tempo; sono componenti fissi che vengono sempre restituiti in una tabella a forma libera. I valori delle dimensioni statiche sono preferiti quando si desidera analizzare sempre lo stesso elemento, siano esse campagne specifiche o giorni specifici della settimana.

Ogni volta che si selezionano e si rilasciano manualmente valori di componenti specifici (dimensione, metrica, segmento, intervallo di date) in una tabella, il risultato è un elenco statico di righe o colonne. I valori di dimensione statici possono essere creati anche se si sceglie di:

* Da righe, fate clic con il pulsante destro del mouse > [!UICONTROL Display only selected rows]
* Da colonne, fare clic con il pulsante destro del mouse > [!UICONTROL Make item static]

Ad esempio, quando si trascina su specifici elementi del tipo di browser come Microsoft e Apple, questi due elementi specifici vengono sempre inseriti nella tabella.

I valori delle dimensioni statiche **non** dispongono dell&#39;opzione filtro righe. Al contrario, su ogni elemento sono presenti le icone Blocca e X. Fare clic sull&#39;icona X per rimuovere il valore della dimensione dalla tabella.

## Valori di dimensione misti

È possibile aggiungere alla stessa tabella valori di dimensione di dimensioni diverse. In questi casi, l’intestazione della riga indica &quot;Dimensioni miste&quot;. Questi valori di dimensione sono statici. Ad esempio, l&#39;aggiunta di valori di dimensione specifici dalla dimensione Tipo browser e di altri valori di dimensione dalla dimensione Browser.

## Righe totali a forma libera

Le righe dinamiche e statiche si comportano in modo diverso nella riga totale a forma libera. Per impostazione predefinita:

* Le righe dinamiche vengono sommate con metriche lato server e deduplicate, come visite o visitatori
* Le righe statiche sono sommate sul lato client e **non** duplicano le metriche.

[Ulteriori informazioni sulle opzioni totali](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html) di Workspace per le righe dinamiche e statiche.
