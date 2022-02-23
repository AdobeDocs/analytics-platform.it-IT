---
title: Elemento dimensionale long tail
description: Spiega l’elemento dimensionale “Long Tail” e il motivo per cui viene visualizzato nel reporting.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '431'
ht-degree: 100%

---

# Elemento dimensionale long tail

Se utilizzi una dimensione che contiene un numero elevato di valori univoci, a volte puoi visualizzare un valore nel reporting etichettato **[!UICONTROL Long Tail]**. Questo elemento dimensionale indica che l’architettura di reporting utilizzata da CJA conteneva troppi valori univoci affinché possa essere elaborata.

## Architettura di elaborazione CJA e valori univoci

CJA elabora i rapporti al momento dell’esecuzione, distribuendo il set di dati combinato a diversi server. I dati per server di elaborazione sono raggruppati per ID persona, il che significa che un singolo server di elaborazione contiene tutti i dati per una determinata persona. Al termine dell’elaborazione, il sottoinsieme di dati elaborati viene consegnato a un server aggregatore. Tutti i sottoinsiemi di dati elaborati vengono combinati e restituiti sotto forma di un rapporto Workspace.

Se un singolo server che elabora un sottoinsieme di dati rileva più di 500.000 elementi dimensionali univoci, restituisce i primi 500.000 elementi dimensionali del proprio sottoinsieme, quindi restituisce il resto sotto “[!UICONTROL Long Tail]”. L’elemento dimensionale “[!UICONTROL Long Tail]” visualizzato in un rapporto Workspace è il totale aggregato dei valori di ogni singolo server di elaborazione che ha superato 500.000 valori univoci.

## Differenze tra “Long Tail” e “Low-Traffic”

Nelle versioni precedenti di Analytics veniva utilizzata un’architettura di elaborazione diversa. I dati sono stati elaborati al momento della raccolta. Gli elementi di Dimension venivano inseriti in “Low-Traffic” dopo che una dimensione raggiungeva 500.000 valori univoci e applicavano un filtro più aggressivo ai valori univoci di 1M. Il conteggio dei valori univoci è stato reimpostato all’inizio di ogni mese di calendario. I dati trattati erano permanenti, non c’era modo di estrarre i dati esistenti da “Low-Traffic”.

In CJA, gli elementi dimensionali vengono inseriti solo in “Long Tail” se un singolo server di elaborazione contiene più di 500.000 valori univoci. I dati elaborati non sono permanenti, il che significa che puoi ridurre l’elemento dimensionale “Long Tail” modificando il rapporto.

## Ridurre l’elemento dimensionale “Long Tail”

Se desideri ridurre l’elemento dimensione “Long Tail”, Adobe consiglia una delle seguenti opzioni:

* Utilizza un [filtro](/help/components/filters/create-filters.md). I filtri si applicano al momento in cui ogni server elabora un sottoinsieme di dati. Limitando il numero di valori univoci restituiti, si riduce l’elemento dimensionale “Long Tail”.
* Utilizza una dimensione del set di dati di ricerca. Le dimensioni del set di dati di ricerca combinano elementi dimensionali del set di dati evento, che limitano il numero di valori univoci restituiti.

Nel complesso, è difficile utilizzare un rapporto che contiene più di 500.000 elementi dimensionali univoci. Se applichi un filtro o una dimensione del set di dati di ricerca, puoi ridurre la presenza di “Long Tail” e allo stesso tempo semplificare l’utilizzo del rapporto. Adobe prevede di migliorare questa esperienza man mano che CJA viene ulteriormente sviluppato.
