---
title: Risultati Elemento dimensione troncato
description: Spiega l’elemento dimensionale "Risultati troncati" e il motivo per cui viene visualizzato nel reporting.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: cf3c451cbefa7d6f9d5ea326c69fc2e5944881ff
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 13%

---

# Risultati Elemento dimensione troncato

Quando si utilizza una dimensione contenente molti valori univoci, un rapporto può restituire un elemento dimensione etichettato **[!UICONTROL Results Truncated]**. Questo elemento dimensione indica che il rapporto richiesto conteneva troppi valori univoci affinché potesse essere elaborato in modo efficiente. Di conseguenza, rimuove gli elementi ritenuti meno importanti.

## Architettura di elaborazione del Customer Journey Analytics e valori univoci

Il Customer Journey Analytics elabora i rapporti al momento dell’esecuzione, distribuendo il set di dati combinato a più server. I dati per server di elaborazione sono raggruppati per ID persona, il che significa che un singolo server di elaborazione contiene tutti i dati per una determinata persona. Al termine dell’elaborazione, il server consegna il sottoinsieme di dati elaborati a un server aggregatore. Tutti i sottoinsiemi di dati elaborati vengono combinati e restituiti sotto forma di un rapporto Workspace.

Se un singolo server aggrega un set di risultati che supera una soglia di dimensione, i risultati vengono troncati prima di essere inviati nuovamente. Questa ottimizzazione mantiene il traffico di rete e l’aggregazione entro i limiti consentiti da un reporting rapido. Poiché ogni server di elaborazione tronca i risultati con la sola visualizzazione dei propri dati, è possibile che gli elementi visualizzati in Analysis Workspace presentino valori di metrica leggermente diversi.

Il server sceglie gli elementi dimensionali da eliminare in base alla metrica utilizzata per l’ordinamento. Se la metrica di ordinamento è una metrica calcolata, il server utilizza le metriche all’interno della metrica calcolata per determinare quali elementi dimensionali troncare. Poiché le metriche calcolate possono contenere diverse metriche di diversa importanza, i risultati possono essere meno precisi. Ad esempio, quando si calcola &quot;Ricavo per persona&quot;, l’importo totale delle entrate e il numero totale di persone vengono restituiti e aggregati prima di effettuare la divisione. Di conseguenza, ogni nodo sceglie gli elementi da rimuovere senza sapere in che modo i risultati influiscono sull’ordinamento complessivo.

## Differenze tra &quot;Risultati troncati&quot; e &quot;Traffico ridotto&quot;

Nelle versioni precedenti di Adobe Analytics veniva utilizzata un’architettura di elaborazione diversa. I dati sono stati elaborati al momento della raccolta. Gli elementi di Dimension venivano inseriti in &quot;Low-Traffic&quot; dopo che una dimensione raggiungeva 500.000 valori univoci e applicavano un filtro più aggressivo a un milione di valori univoci. Il conteggio &quot;Valore univoco&quot; è stato reimpostato all’inizio di ogni mese di calendario. I dati trattati erano permanenti, non c’era modo di estrarre i dati esistenti da “Low-Traffic”.

In Customer Journey Analytics, gli elementi dimensionali vengono troncati solo se i risultati di un rapporto sono troppo grandi. I dati elaborati non sono permanenti, il che significa che puoi ridurre o eliminare il troncamento modificando il rapporto.

## Ridurre l’elemento dimensione &quot;Risultati troncati&quot;

Se desideri ridurre il numero di eventi nell’elemento dimensione &quot;Risultati troncati&quot;, l’Adobe consiglia una delle seguenti opzioni:

* Utilizza un [Filtro](/help/components/filters/create-filters.md). I filtri si applicano al momento in cui ogni server elabora un sottoinsieme di dati. Limitando il numero di valori univoci restituiti, si riduce l’elemento dimensione &quot;Risultati troncati&quot;.
* Utilizza una ricerca. Se si utilizza una ricerca, gli elementi che non corrispondono alla ricerca vengono rimossi dai risultati del rapporto, rendendo più probabile la visualizzazione degli elementi desiderati.
* Utilizza una dimensione del set di dati di ricerca. Le dimensioni del set di dati di ricerca combinano elementi dimensionali del set di dati evento, che limitano il numero di valori univoci restituiti.
