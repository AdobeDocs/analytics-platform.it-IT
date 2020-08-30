---
title: Elemento dimensione lunga
description: Spiega l’elemento dimensione "Coda lunga" e il motivo per cui viene visualizzato nel reporting.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---


# Elemento dimensione lunga

Se utilizzate una dimensione che contiene un numero elevato di valori univoci, talvolta potete visualizzare un valore nel rapporto con l&#39;etichetta &quot;Long Tail&quot;. Questo elemento dimensione indica che l&#39;architettura di reporting utilizzata da CJA conteneva troppi valori univoci per l&#39;elaborazione.

## Architettura di elaborazione CJA e valori univoci

CJA elabora i rapporti al momento della loro esecuzione, distribuendo il set di dati combinato a diversi server. I dati per server di elaborazione sono raggruppati per ID persona, il che significa che un singolo server di elaborazione contiene tutti i dati per una determinata persona. Al termine dell&#39;elaborazione, il sottoinsieme dei dati elaborati viene distribuito a un server di aggregazione. Tutti i sottoinsiemi di dati elaborati vengono combinati e restituiti sotto forma di rapporto Workspace.

Se un singolo server che elabora un sottoinsieme di dati rileva più di 500.000 elementi di dimensione univoci, restituisce i primi 500.000 elementi di dimensione del proprio sottoinsieme, quindi restituisce il resto in &#39;Long Tail&#39;. L&#39;elemento dimensione &#39;Coda lunga&#39; visualizzato in un rapporto Workspace è il totale aggregato dei valori di ciascun singolo server di elaborazione che supera i valori univoci di 500.000.

## Differenze tra &#39;coda lunga&#39; e &#39;traffico basso&#39;

Nelle versioni precedenti di  Adobe Analytics, veniva utilizzata un&#39;architettura di elaborazione diversa. I dati sono stati elaborati al momento della raccolta. Gli elementi Dimension sono stati inseriti in &#39;Basso traffico&#39; dopo che una dimensione ha raggiunto valori univoci di 500 K e applicato un filtraggio più aggressivo ai valori univoci di 1M. Il conteggio dei valori univoci è stato reimpostato all&#39;inizio di ogni mese di calendario. I dati trattati erano permanenti; non c&#39;era modo di estrarre i dati esistenti da &#39;Basso Traffico&#39;.

In CJA, gli elementi dimensionali vengono inseriti solo in &#39;Long Tail&#39; se un singolo server di elaborazione contiene più di 500K valori univoci. I dati elaborati non sono permanenti, il che significa che è possibile ridurre l&#39;elemento dimensione &#39;Coda lunga&#39; modificando il rapporto.

## Ridurre l&#39;elemento dimensione &#39;Coda lunga&#39;

Per ridurre l’elemento dimensione &#39;Coda lunga&#39;,  Adobe consiglia una delle seguenti opzioni:

* Utilizza un segmento. I segmenti si applicano al momento in cui ogni server elabora un sottoinsieme di dati. Limitando il numero di valori univoci restituiti, si riduce l’elemento dimensione &#39;Coda lunga&#39;.
* Utilizzare una dimensione dataset di ricerca. Le dimensioni del set di dati di ricerca combinano gli elementi della dimensione del set di dati dell&#39;evento, che limitano il numero di valori univoci restituiti.

Nel complesso, è difficile utilizzare un rapporto che contiene più di 500.000 elementi di dimensione univoci. Se si applica un segmento o una dimensione di set di dati di ricerca, è possibile ridurre la presenza di &#39;Coda lunga&#39; e semplificare l&#39;utilizzo del rapporto.  Adobe intende migliorare tale esperienza man mano che la CGUE viene ulteriormente sviluppata.
