---
title: Elemento dimensionale long tail
description: Spiega l’elemento dimensionale “Long Tail” e il motivo per cui viene visualizzato nel reporting.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: 5603eef365365cea941ba5b261aeb56e58a84236
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 39%

---

# Avviso troncamento

Quando utilizzi una dimensione che contiene un numero elevato di valori univoci, a volte visualizzi un avviso che riporta **[!UICONTROL Results Truncated]**.  Ciò significa che l’architettura di reporting utilizzata da CJA conteneva troppi valori univoci per consentirle di elaborare in modo efficiente e quindi ha rimosso gli elementi che riteneva fossero meno importanti.

## Architettura di elaborazione CJA e valori univoci

CJA elabora i rapporti al momento dell’esecuzione, distribuendo il set di dati combinato a diversi server. I dati per server di elaborazione sono raggruppati per ID persona, il che significa che un singolo server di elaborazione contiene tutti i dati per una determinata persona. Al termine dell’elaborazione, il sottoinsieme di dati elaborati viene consegnato a un server aggregatore. Tutti i sottoinsiemi di dati elaborati vengono combinati e restituiti sotto forma di un rapporto Workspace.

Se un singolo server aggrega un set di risultati che supera una soglia di dimensione, troncherà i risultati prima di inviarli nuovamente.  In questo modo il traffico di rete e l’aggregazione vengono mantenuti nei limiti per consentire la generazione di rapporti rapidi.  Poiché tronca i risultati solo con la visualizzazione dei propri dati, è possibile (per quanto improbabile) che gli elementi mostrati in Analysis Workspace abbiano valori di metrica errati.

Scegli gli elementi da scartare in base alla metrica utilizzata per l’ordinamento.  Se si tratta di una metrica calcolata, potrebbe non essere ovvio come ordinarla e quindi i risultati potrebbero essere meno precisi.  Ad esempio, quando si calcolano i ricavi per visitatore, la quantità totale di ricavi e il numero totale di visitatori vengono restituiti e aggregati prima di eseguire la divisione, e quindi ogni nodo sceglie di gran lunga gli elementi da rimuovere senza sapere realmente in che modo i loro risultati influenzeranno l’ordinamento complessivo.

## Differenze tra “Long Tail” e “Low-Traffic”

Nelle versioni precedenti di Analytics veniva utilizzata un’architettura di elaborazione diversa. I dati sono stati elaborati al momento della raccolta. Gli elementi di Dimension venivano inseriti in “Low-Traffic” dopo che una dimensione raggiungeva 500.000 valori univoci e applicavano un filtro più aggressivo ai valori univoci di 1M. Il conteggio dei valori univoci è stato reimpostato all’inizio di ogni mese di calendario. I dati trattati erano permanenti, non c’era modo di estrarre i dati esistenti da “Low-Traffic”.

In CJA, gli elementi dimensionali vengono troncati solo se i risultati di un rapporto sono troppo grandi. I dati elaborati non sono permanenti, il che significa che puoi ridurre o eliminare il troncamento modificando il rapporto.

## Ridurre l’elemento dimensionale “Long Tail”

Per ridurre il troncamento della coda lunga, l’Adobe consiglia una delle seguenti opzioni:

* Utilizza un [filtro](/help/components/filters/create-filters.md). I filtri si applicano al momento in cui ogni server elabora un sottoinsieme di dati. Limitando il numero di valori univoci restituiti si riduce il troncamento della coda lunga.
* Utilizza una ricerca.  Se viene utilizzata una ricerca, gli elementi che non corrispondono alla ricerca verranno troncati per primi, rendendo più probabile la visualizzazione degli elementi desiderati.
* Utilizza una dimensione del set di dati di ricerca. Le dimensioni del set di dati di ricerca combinano elementi dimensionali del set di dati evento, che limitano il numero di valori univoci restituiti.

Nel complesso, è difficile utilizzare un rapporto che contiene troppi elementi dimensionali univoci. Se applichi un filtro o una dimensione del set di dati di ricerca, puoi ridurre il troncamento &quot;Long Tail&quot; e allo stesso tempo semplificare l’utilizzo del rapporto.
