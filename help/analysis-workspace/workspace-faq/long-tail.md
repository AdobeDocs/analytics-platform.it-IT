---
title: Elemento dimensionale long tail
description: Spiega l’elemento dimensionale “Long Tail” e il motivo per cui viene visualizzato nel reporting.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: 8618690187a0cc35fd59cc8bef9ad1147cadf8b0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Elemento dimensione a coda lunga

Quando utilizzi una dimensione che contiene un numero elevato di valori univoci, a volte visualizzi un avviso che riporta **[!UICONTROL Results Truncated]**.  Ciò significa che l’architettura di reporting utilizzata da CJA conteneva troppi valori univoci affinché possa essere elaborata in modo efficiente. Di conseguenza. ha rimosso gli elementi ritenuti meno importanti.

## Architettura di elaborazione CJA e valori univoci

CJA elabora i rapporti al momento dell’esecuzione, distribuendo il set di dati combinato a diversi server. I dati per server di elaborazione sono raggruppati per ID persona, il che significa che un singolo server di elaborazione contiene tutti i dati per una determinata persona. Al termine dell’elaborazione, il server distribuisce il sottoinsieme di dati elaborati a un server aggregatore. Tutti i sottoinsiemi di dati elaborati vengono combinati e restituiti sotto forma di un rapporto Workspace.

Se un singolo server aggrega un set di risultati che supera una soglia di dimensione, troncherà i risultati prima di inviarli nuovamente. In questo modo il traffico e l’aggregazione di rete vengono mantenuti entro i limiti consentiti per consentire la generazione di rapporti rapidi.  Poiché tronca i risultati solo con la visualizzazione dei propri dati, è possibile (anche se improbabile) che gli elementi mostrati in Analysis Workspace abbiano valori di metrica errati.

Il server sceglie gli elementi da eliminare in base alla metrica utilizzata per l’ordinamento.  Se si tratta di una metrica calcolata, potrebbe non essere ovvio come ordinarla e quindi i risultati potrebbero essere meno precisi.  Ad esempio, nel calcolo di &quot;Ricavo per visitatore&quot;, prima di eseguire la divisione, l’importo totale dei ricavi e il numero totale di visitatori vengono restituiti e aggregati. Di conseguenza, ogni nodo sceglie molto gli elementi da rimuovere, senza realmente sapere come i loro risultati influenzeranno l&#39;ordinamento generale.

## Differenze tra “Long Tail” e “Low-Traffic”

Nelle versioni precedenti di Adobe Analytics, veniva utilizzata un’architettura di elaborazione diversa. I dati sono stati elaborati al momento della raccolta. Gli elementi di Dimension venivano inseriti in “Low-Traffic” dopo che una dimensione raggiungeva 500.000 valori univoci e applicavano un filtro più aggressivo ai valori univoci di 1M. Il conteggio del &quot;valore univoco&quot; è stato reimpostato all&#39;inizio di ogni mese di calendario. I dati trattati erano permanenti, non c’era modo di estrarre i dati esistenti da “Low-Traffic”.

In CJA, gli elementi dimensionali vengono troncati solo se i risultati di un rapporto sono troppo grandi. I dati elaborati non sono permanenti, il che significa che puoi ridurre o eliminare il troncamento modificando il rapporto.

## Ridurre l’elemento dimensionale “Long Tail”

Per ridurre il troncamento della coda lunga, l’Adobe consiglia una delle seguenti opzioni:

* Utilizza un [filtro](/help/components/filters/create-filters.md). I filtri si applicano al momento in cui ogni server elabora un sottoinsieme di dati. Limitando il numero di valori univoci restituiti si riduce il troncamento della coda lunga.
* Utilizza una ricerca. Se viene utilizzata una ricerca, gli elementi che non corrispondono alla ricerca vengono troncati per primi, rendendo più probabile la visualizzazione degli elementi desiderati.
* Utilizza una dimensione del set di dati di ricerca. Le dimensioni del set di dati di ricerca combinano elementi dimensionali del set di dati evento, che limitano il numero di valori univoci restituiti.

Nel complesso, è difficile utilizzare un rapporto che contiene troppi elementi dimensionali univoci. Se applichi un filtro o una dimensione del set di dati di ricerca, puoi ridurre il troncamento &quot;Long Tail&quot; e allo stesso tempo semplificare l’utilizzo del rapporto.
