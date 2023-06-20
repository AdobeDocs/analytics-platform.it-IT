---
title: Dimension con cardinalità molto elevata nel Customer Journey Analytics
description: Descrive le best practice per gestire le dimensioni ad alta cardinalità nel Customer Journey Analytics
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 1%

---

# Dimensioni con cardinalità molto elevata

Il Customer Journey Analytics (Customer Journey Analytics) non pone limiti al numero di valori univoci o elementi dimensionali che possono essere segnalati all’interno di una singola dimensione. Tuttavia, in alcune circostanze, le dimensioni con un numero estremamente elevato di elementi univoci, note anche come dimensioni ad alta cardinalità, possono influire su ciò che può essere riportato.

## Limitazioni

A seconda del numero di eventi in una connessione di Customer Journey Analytics specifica, possono verificarsi le due limitazioni seguenti in combinazione con dimensioni ad alta cardinalità:

### 1. I conteggi delle righe potrebbero non essere segnalati con precisione

I conteggi delle righe per le dimensioni ad alta cardinalità potrebbero non essere segnalati con precisione. In questo caso, le tabelle a forma libera forniranno un’indicazione, come illustrato di seguito:

![](assets/high-cardinality.png)

### 2. Le metriche calcolate possono utilizzare stime per alcune funzioni e per l’ordinamento

Se utilizzate con dimensioni altamente cardinali, alcune funzioni della metrica calcolata possono restituire stime, tra cui: Massimo colonna, Minimo colonna, Conteggio righe, Media, Mediana, Percentile, Quartile, Deviazione standard, Varianza, Funzioni di regressione e Funzioni T e Z.

Inoltre, l’ordinamento di una colonna di tabella utilizzando una metrica calcolata può essere basato su una stima e non sempre riflettere l’esatto ordinamento. Verrà visualizzato un messaggio di avviso per avvisarti che potrebbero essere state utilizzate delle stime.

Tieni presente che anche se le metriche calcolate possono talvolta restituire stime, i totali delle colonne sono sempre accurati e non si basano mai su stime. Allo stesso modo, quando si utilizzano metriche standard, le stime non vengono mai utilizzate e riflettono sempre ordini esatti.

### Dove vengono considerati tutti i valori di dimensione

Anche se esistono limitazioni ad alcune metriche calcolate e ai conteggi delle righe delle dimensioni, tieni presente che le seguenti funzionalità considerano sempre tutti i valori univoci in qualsiasi dimensione, indipendentemente dal fatto che una dimensione sia altamente cardinale o meno:

* Attribuzione delle metriche e allocazione delle dimensioni
* Ricerche di voci applicate a una tabella a forma libera
* Filtri che utilizzano dimensioni o elementi dimensionali
* Funzione di conteggio distinto approssimativo nelle metriche calcolate
* Logica di inclusione/esclusione applicata a qualsiasi metrica o dimensione all’interno di una visualizzazione dati
* Ricercare set di dati aggiunti a una connessione

## Best practice per l’utilizzo di dimensioni ad alto numero di cardinali

Per eliminare le avvertenze o le stime che possono verificarsi quando si utilizzano dimensioni con cardinalità elevata, si consiglia di limitare il numero di righe considerate nel rapporto, utilizzando uno dei seguenti metodi:

* Aggiungi un filtro alla colonna o al pannello interessato.
* Applicare una ricerca alla tabella a forma libera.
* Applica un raggruppamento alle righe di interesse oppure utilizza la dimensione altamente cardinale come dimensione di raggruppamento.
* Aggiungi criteri di inclusione/esclusione alla configurazione della visualizzazione dati della dimensione per limitare il numero di valori univoci presenti nella dimensione.

L’utilizzo di queste tecniche spesso può eliminare qualsiasi stima o avviso indesiderato riscontrato durante l’utilizzo di dimensioni ad alta cardinalità.
