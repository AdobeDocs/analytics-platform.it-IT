---
title: Utilizzo di dimensioni e metriche di binding in CJA
description: Attribuisci dimensioni agli array di oggetti per analisi di persistenza complessa.
source-git-commit: b93809c9af02227295c9dd66565f04675236c393
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---


# Utilizzo di dimensioni e metriche di binding in CJA

Il Customer Journey Analytics offre diversi modi per mantenere i valori di dimensione oltre l’hit su cui sono impostati. Uno dei metodi di persistenza offerti da Adobe è noto come Binding. Nelle versioni precedenti di Adobe Analytics, questo concetto era noto come merchandising.

Anche se è possibile utilizzare dimensioni di binding con dati evento di livello principale, è meglio utilizzarlo quando si lavora con [Array di oggetti](object-arrays.md). È possibile attribuire una dimensione a una parte di una matrice di oggetti senza applicarla a tutti gli attributi di un dato evento. Ad esempio, è possibile attribuire un termine di ricerca a un prodotto nell’array di oggetti del carrello senza associare tale termine all’intero evento.

## Esempio 2: Utilizzo di metriche di binding per legare i termini di ricerca a un acquisto di prodotto

Uno dei metodi più comuni di merchandising in Adobe Analytics è stato quello di associare un termine di ricerca a un prodotto in modo che ogni termine di ricerca riceva credito per il prodotto appropriato. Considera il seguente percorso di clienti:

1. Un visitatore arriva al tuo sito e cerca &quot;guanti da boxe&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
               "color": "Red",
               "price": "25.69"
           },
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Professional gloves",
               "color": "Blue",
               "price": "224.99"
           }
       ]
   }
   ```

1. Trovano un paio di guanti che gli piacciono, e lo aggiungono al carrello.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           }
       ]
   }
   ```

1. Il visitatore cerca poi &quot;racchetta da tennis&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Women's open racket",
               "price": "49.99"
           },
           {
               "name": "Extreme racket",
               "price": "134.99"
           }
       ]
   }
   ```

1. Trovano una racchetta che gli piace, e la aggiungono al carrello.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           }
       ]
   }
   ```

1. Il visitatore cerca una terza volta &quot;scarpe&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
               "color": "Grey",
               "price": "54.95"
           },
           {
               "name": "Tennis shoes",
               "color": "White",
               "price": "42.59"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. Trovano un paio di scarpe che gli piacciono e le aggiungono al carrello.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. Il visitatore passa attraverso il processo di pagamento e acquista questi tre elementi.

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

Se utilizzi un modello di allocazione tradizionale con termine di ricerca, tutti e tre i prodotti attribuiscono i ricavi a un solo termine di ricerca. Ad esempio, se hai utilizzato la prima allocazione con la dimensione del termine di ricerca:

| search_term | ricavi |
| --- | --- |
| guanti da pugilato | $ 204,97 |

Se hai utilizzato l’ultima allocazione con la dimensione del termine di ricerca, tutti e tre i prodotti attribuiscono ancora i ricavi a un singolo termine di ricerca:

| search_term | ricavi |
| --- | --- |
| scarpe | $ 204,97 |

Anche se questo esempio include un solo visitatore, molti visitatori che cercano cose diverse possono attribuire erroneamente i termini di ricerca a prodotti diversi, rendendo difficile determinare quali siano effettivamente i migliori risultati di ricerca.

Con una dimensione di binding, Adobe prende nota dell’elemento dimensionale a cui è associato. Quando lo stesso valore di binding viene visualizzato in un evento successivo, questo porta sopra l’elemento dimensione in modo da poter attribuire la metrica desiderata. In questo esempio, possiamo impostare la dimensione di binding per search_term su nome prodotto:

![Dimensione di binding](assets/binding-dimension.png)

Quando si imposta questa dimensione in Gestione visualizzazione dati, è necessario impostare anche una metrica di binding perché la dimensione di binding si trova in una matrice di oggetti. Una metrica di binding funge da trigger per una dimensione di binding, quindi si vincola solo agli eventi in cui è presente la metrica di binding. In questa implementazione di esempio, la pagina dei risultati della ricerca include sempre una dimensione del termine di ricerca e una metrica di ricerca. È possibile associare i termini di ricerca al nome del prodotto ogni volta che la metrica Ricerche è presente.

![Metrica di binding](assets/binding-metric.png)

L’impostazione della dimensione del termine di ricerca su questo modello di persistenza esegue la logica seguente:

* Quando search_term si trova in un evento, controlla la presenza del nome del prodotto.
* Se il nome del prodotto non è presente, non eseguire alcuna operazione.
* Se il nome del prodotto è presente, controlla la presenza della metrica Ricerche.
* Se la metrica Ricerche non è presente, non eseguire alcuna operazione.
* Se la metrica Ricerche è presente, associa il termine di ricerca a tutti i nomi di prodotto. Funziona come se fosse allo stesso livello del nome del prodotto per quell’evento. In questo esempio viene trattato come product.search_term.
* Se lo stesso nome di prodotto viene visualizzato in un evento successivo, esiste anche il termine di ricerca associato.

In Analysis Workspace, il rapporto risultante sarà simile al seguente:

| search_term | ricavi |
| --- | --- |
| guanti da pugilato | $ 89,99 |
| racchetta da tennis | $ 34,99 |
| scarpe | $ 79,99 |
