---
title: Elemento dimensionale long tail
description: Spiega l’elemento dimensionale “Long Tail” e il motivo per cui viene visualizzato nel reporting.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 26%

---

# Elemento dimensione coda lunga

Quando utilizzi una dimensione che contiene un numero elevato di valori univoci, a volte viene visualizzato un avviso che indica **[!UICONTROL Results Truncated]**.  Ciò significa che il Customer Journey Analytics dell’architettura di reporting utilizza troppi valori univoci affinché possa essere elaborato in modo efficiente. Di conseguenza. ha rimosso gli elementi ritenuti meno importanti.

## Architettura di elaborazione del Customer Journey Analytics e valori univoci

Il Customer Journey Analytics elabora i rapporti al momento dell’esecuzione, distribuendo il set di dati combinato a diversi server. I dati per server di elaborazione sono raggruppati per ID persona, il che significa che un singolo server di elaborazione contiene tutti i dati per una determinata persona. Al termine dell’elaborazione, il server consegna il sottoinsieme di dati elaborati a un server aggregatore. Tutti i sottoinsiemi di dati elaborati vengono combinati e restituiti sotto forma di un rapporto Workspace.

Se un singolo server aggrega un set di risultati che supera una soglia di dimensione, i risultati verranno troncati prima di essere inviati nuovamente. In questo modo il traffico di rete e l’aggregazione vengono mantenuti entro limiti che consentono di creare rapporti rapidi.  Poiché i risultati vengono troncati solo con la visualizzazione dei propri dati, è possibile (anche se improbabile) che gli elementi visualizzati in Analysis Workspace presentino valori di metrica errati.

Il server sceglie gli elementi da eliminare in base alla metrica utilizzata per l&#39;ordinamento.  Se si tratta di una metrica calcolata, potrebbe non essere ovvio come ordinarla, pertanto i risultati potrebbero essere meno precisi.  Ad esempio, quando si calcola &quot;Ricavo per persona&quot;, l’importo totale delle entrate e il numero totale di persone vengono restituiti e aggregati prima di effettuare la divisione. Di conseguenza, ogni nodo sceglie spesso gli elementi da rimuovere, senza sapere realmente in che modo i loro risultati influenzeranno l’ordinamento complessivo.

## Differenze tra “Long Tail” e “Low-Traffic”

Nelle versioni precedenti di Adobe Analytics veniva utilizzata un’architettura di elaborazione diversa. I dati sono stati elaborati al momento della raccolta. Gli elementi di Dimension venivano inseriti in “Low-Traffic” dopo che una dimensione raggiungeva 500.000 valori univoci e applicavano un filtro più aggressivo ai valori univoci di 1M. Il conteggio &quot;Valore univoco&quot; è stato reimpostato all’inizio di ogni mese di calendario. I dati trattati erano permanenti, non c’era modo di estrarre i dati esistenti da “Low-Traffic”.

In Customer Journey Analytics, gli elementi dimensionali vengono troncati solo se i risultati di un rapporto sono troppo grandi. I dati elaborati non sono permanenti, il che significa che puoi ridurre o eliminare il troncamento modificando il rapporto.

## Ridurre l’elemento dimensionale “Long Tail”

Se desideri ridurre il troncamento &quot;Long Tail&quot;, Adobe consiglia una delle seguenti opzioni:

* Utilizza un [filtro](/help/components/filters/create-filters.md). I filtri si applicano al momento in cui ogni server elabora un sottoinsieme di dati. Limitando il numero di valori univoci restituiti, si riduce il troncamento della &quot;Long Tail&quot;.
* Utilizza una ricerca. Se si utilizza una ricerca, gli elementi che non corrispondono alla ricerca vengono troncati per primi, rendendo più probabile la visualizzazione degli elementi desiderati.
* Utilizza una dimensione del set di dati di ricerca. Le dimensioni del set di dati di ricerca combinano elementi dimensionali del set di dati evento, che limitano il numero di valori univoci restituiti.

Nel complesso, è difficile utilizzare un rapporto che contiene troppi elementi dimensionali univoci. Se applichi un filtro o una dimensione del set di dati di ricerca, puoi ridurre il troncamento &quot;Long Tail&quot; e allo stesso tempo semplificare l’utilizzo del rapporto.
