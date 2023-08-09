---
title: Dimensioni ad alta cardinalità
description: Spiega come il Customer Journey Analytics gestisce le dimensioni con molti valori univoci
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
source-git-commit: 8f64e0a31ed3bca7185674490fc36b78598f5b1c
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 7%

---

# Dimensioni ad alta cardinalità

Quando si utilizza una dimensione contenente molti valori univoci, il rapporto risultante può contenere troppi elementi dimensionali univoci da visualizzare o calcolare. I risultati vengono troncati rimuovendo gli elementi dimensionali ritenuti meno importanti. Queste ottimizzazioni vengono eseguite per mantenere le prestazioni di progetto e prodotto.

Quando richiedi un rapporto con troppi valori univoci, Analysis Workspace mostra un indicatore nell’intestazione della dimensione che indica che non tutti gli elementi dimensionali sono inclusi. Ad esempio, &quot;Righe: da 1 a 50 su oltre 22.343.156&quot;. La parola chiave &quot;più di&quot; indica che è stata applicata una certa ottimizzazione al rapporto per restituire gli elementi dimensionali più importanti.

![Anteprima area di lavoro](assets/high-cardinality.png)

## Determinazione degli elementi dimensionali da visualizzare

Il Customer Journey Analytics elabora i rapporti al momento dell’esecuzione, distribuendo il set di dati combinato a più server. I dati per server di elaborazione sono raggruppati per ID persona, il che significa che un singolo server di elaborazione contiene tutti i dati per una determinata persona. Al termine dell’elaborazione, il server consegna il sottoinsieme di dati elaborati a un server aggregatore. Tutti i sottoinsiemi di dati elaborati vengono combinati e restituiti sotto forma di un rapporto Workspace.

Se un singolo server elabora dati che superano una soglia univoca, i risultati vengono troncati prima di restituire il sottoinsieme di dati elaborato. Gli elementi dimensionali troncati vengono determinati in base alla metrica utilizzata per l’ordinamento.

Se la metrica di ordinamento è una metrica calcolata, il server utilizza le metriche all’interno della metrica calcolata per determinare quali elementi dimensionali troncare. Poiché le metriche calcolate possono contenere diverse metriche di diversa importanza, i risultati possono essere meno precisi. Ad esempio, quando si calcola &quot;Ricavo per persona&quot;, l’importo totale delle entrate e il numero totale di persone vengono restituiti e aggregati prima di effettuare la divisione. Di conseguenza, ogni singolo server di elaborazione sceglie gli elementi da rimuovere senza sapere in che modo i risultati influiscono sull’ordinamento complessivo.

Anche se alcuni singoli elementi dimensionali potrebbero mancare nei rapporti con cardinalità elevata, i totali delle colonne sono accurati e non basati su dati troncati. Anche la funzione &quot;Count Distinct&quot; nelle metriche calcolate non è interessata dagli elementi dimensionali troncati.

## Best practice per dimensioni ad alta cardinalità

Il modo migliore per adattarsi a dimensioni ad alta cardinalità consiste nel limitare il numero di elementi dimensionali elaborati da un rapporto. Poiché tutti i rapporti vengono elaborati al momento della richiesta, è possibile modificare i parametri per i risultati immediati. L’Adobe consiglia una delle seguenti ottimizzazioni per le dimensioni ad alta cardinalità:

* Utilizza un [Filtro](/help/components/filters/create-filters.md). I filtri si applicano al momento in cui ogni server elabora un sottoinsieme di dati.
* Utilizza una ricerca. Gli elementi di Dimension esclusi dal termine di ricerca vengono rimossi dai risultati del rapporto, rendendo più probabile la visualizzazione degli elementi dimensionali desiderati.
* Utilizza una dimensione del set di dati di ricerca. Le dimensioni del set di dati di ricerca combinano elementi dimensionali del set di dati evento, che limitano il numero di valori univoci restituiti.
* Utilizza il [Includi/escludi](/help/data-views/component-settings/include-exclude-values.md) impostazione del componente in gestione visualizzazione dati.
* Abbreviare l’intervallo di date della richiesta. Se molti valori univoci si accumulano nel tempo, la riduzione dell’intervallo di date del rapporto Workspace può limitare il numero di valori univoci da elaborare per i server.
