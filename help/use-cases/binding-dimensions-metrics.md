---
title: Utilizzare dimensioni e metriche di binding in CJA
description: Attribuisci dimensioni agli array di oggetti per analisi di persistenza complessa.
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
source-git-commit: 28a6acd3f850e94a1f0d72477c22a5b30ab3fc2a
workflow-type: tm+mt
source-wordcount: '1330'
ht-degree: 1%

---


# Utilizzare dimensioni e metriche di binding in CJA

Il Customer Journey Analytics offre diversi modi per mantenere i valori di dimensione oltre l’hit su cui sono impostati. Uno dei metodi di persistenza offerti da Adobe è noto come Binding. Nelle versioni precedenti di Adobe Analytics, questo concetto era noto come merchandising.

Anche se è possibile utilizzare dimensioni di binding con dati evento di livello principale, è meglio utilizzarlo quando si lavora con [Array di oggetti](object-arrays.md). È possibile attribuire una dimensione a una parte di una matrice di oggetti senza applicarla a tutti gli attributi di un dato evento. Ad esempio, è possibile attribuire un termine di ricerca a un prodotto nell’array di oggetti del carrello senza associare tale termine all’intero evento.

## Esempio 1: Utilizzare le dimensioni di binding per attribuire attributi di prodotto aggiuntivi a un acquisto

È possibile eseguire il binding degli elementi dimensionali all’interno di una matrice di oggetti a un’altra dimensione. Quando viene visualizzato l’elemento di dimensione associato, CJA richiama la dimensione associata e lo include nell’evento per te. Considera il seguente percorso di clienti:

1. Un visitatore visualizza una pagina di prodotto su una lavatrice.

   ```json
   {
       "PersonID": "1",
       "product": [
           {
               "name": "Washing Machine 2000",
               "color": "white",
               "type": "front loader",
           },
       ],
       "timestamp": 1534219229
   }
   ```

1. Il visitatore visualizza quindi una pagina di prodotto su un’asciugatrice.

   ```json
   {
       "PersonID": "1",
       "product": [
           {
               "name": "Dryer 2000",
               "color": "neon orange",
           },
       ],
       "timestamp": 1534219502
   }
   ```

1. Alla fine fanno un acquisto. Il colore di ciascun prodotto non è stato incluso nell’evento di acquisto.

   ```json
   {
       "PersonID": "1",
       "orders": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "price": 1600,
           },
           {
               "name": "Dryer 2000",
               "price": 499
           }
       ],
       "timestamp": 1534219768
   }
   ```

Se desideri esaminare i ricavi per colore senza una dimensione di binding, la dimensione `product.color` persiste e attribuisce in modo errato il credito al colore dell&#39;asciugatrice:

| product.color | ricavi |
| --- | --- |
| neon arancione | 2099 |

È possibile accedere a Data View Manager e associare il colore del prodotto al nome del prodotto:

![Dimensione di binding](assets/binding-dimension.png)

Quando imposti questo modello di persistenza, CJA prende nota del nome del prodotto ogni volta che viene impostato il colore del prodotto. Quando riconosce lo stesso nome di prodotto in un evento successivo per questo visitatore, viene portato anche il colore del prodotto. Gli stessi dati quando si associa il colore del prodotto al nome del prodotto saranno simili ai seguenti:

| product.color | ricavi |
| --- | --- |
| bianco | 1600 |
| neon arancione | 499 |

## Esempio 2: Utilizzare metriche di binding per legare i termini di ricerca a un acquisto di prodotto

Uno dei metodi più comuni di merchandising in Adobe Analytics è stato quello di associare un termine di ricerca a un prodotto in modo che ogni termine di ricerca riceva credito per il prodotto appropriato. Considera il seguente percorso di clienti:

1. Un visitatore arriva al tuo sito e cerca &quot;guanti da boxe&quot;. La metrica delle ricerche viene incrementata di uno, e vengono visualizzati i primi tre risultati di ricerca.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
           },
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Professional gloves",
           }
       ]
   }
   ```

2. Trovano un paio di guanti che gli piacciono, e lo aggiungono al carrello.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           }
       ]
   }
   ```

3. Il visitatore cerca poi &quot;racchetta da tennis&quot;. La metrica delle ricerche viene incrementata di uno, e vengono visualizzati i primi tre risultati di ricerca.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
           },
           {
               "name": "Women's open racket",
           },
           {
               "name": "Extreme racket",
           }
       ]
   }
   ```

4. Trovano una racchetta che gli piace, e la aggiungono al carrello.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Shock absorb racket",
           }
       ]
   }
   ```

5. Il visitatore cerca una terza volta &quot;scarpe&quot;. La metrica delle ricerche viene incrementata di uno, e vengono visualizzati i primi tre risultati di ricerca.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
           },
           {
               "name": "Tennis shoes",
           },
           {
               "name": "Skate shoes",
           }
       ]
   }
   ```

6. Trovano un paio di scarpe che gli piacciono e le aggiungono al carrello.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Shock absorb racket",
           },
           {
               "name": "Skate shoes",
           }
       ]
   }
   ```

7. Il visitatore passa attraverso il processo di pagamento e acquista questi tre elementi.

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "price": "79.99"
           }
       ]
   }
   ```

Se si utilizza un modello di allocazione che non include una dimensione di binding con un termine di ricerca, tutti e tre i prodotti attribuiscono i ricavi a un solo termine di ricerca. Ad esempio, se hai utilizzato Allocazione originale con la dimensione del termine di ricerca:

| search_term | ricavi |
| --- | --- |
| guanti da pugilato | $ 204,97 |

Se hai utilizzato l’allocazione più recente con la dimensione del termine di ricerca, tutti e tre i prodotti attribuiscono ancora i ricavi a un singolo termine di ricerca:

| search_term | ricavi |
| --- | --- |
| scarpe | $ 204,97 |

Anche se questo esempio include un solo visitatore, molti visitatori che cercano cose diverse possono attribuire erroneamente i termini di ricerca a prodotti diversi, rendendo difficile determinare quali siano effettivamente i migliori risultati di ricerca.

È possibile associare i termini di ricerca al nome del prodotto ogni volta che la metrica Ricerche è presente per attribuire correttamente il termine di ricerca ai ricavi.

![Metrica di binding](assets/binding-metric.png)

In Analysis Workspace, il rapporto risultante sarà simile al seguente:

| search_term | ricavi |
| --- | --- |
| guanti da pugilato | $ 89,99 |
| racchetta da tennis | $ 34,99 |
| scarpe | $ 79,99 |

CJA rileva automaticamente la relazione tra la dimensione selezionata e la dimensione di binding. Se la dimensione di binding si trova in una matrice di oggetti mentre la dimensione selezionata si trova a un livello superiore, è necessaria una metrica di binding. Una metrica di binding funge da trigger per una dimensione di binding, quindi si vincola solo agli eventi in cui è presente la metrica di binding. Nell’esempio precedente, la pagina dei risultati della ricerca include sempre una dimensione del termine di ricerca e una metrica di ricerca.

L’impostazione della dimensione del termine di ricerca su questo modello di persistenza esegue la logica seguente:

* Quando la dimensione del termine di ricerca è impostata, controlla la presenza del nome del prodotto.
* Se il nome del prodotto non è presente, non eseguire alcuna operazione.
* Se il nome del prodotto è presente, controlla la presenza della metrica Ricerche.
* Se la metrica Ricerche non è presente, non eseguire alcuna operazione.
* Se la metrica Ricerche è presente, associa il termine di ricerca a tutti i nomi di prodotto in tale evento. Si copia fino allo stesso livello del nome del prodotto per quell&#39;evento. In questo esempio viene trattato come product.search_term.
* Se lo stesso nome di prodotto viene visualizzato in un evento successivo, anche il termine di ricerca associato viene riportato a tale evento.

## Esempio 3: Associare il termine di ricerca video al profilo utente

Puoi eseguire un binding di un termine di ricerca con un profilo utente in modo che la persistenza tra i profili rimanga completamente separata. Ad esempio, la tua organizzazione esegue un servizio di streaming in cui un account di overarching può avere più profili. Il visitatore ha un profilo figlio e un profilo per adulti.

1. L&#39;account accede sotto il profilo bambino e cerca un programma televisivo per bambini. Tieni presente che `"ProfileID"` è `2` per rappresentare il profilo figlio.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "2",
       "Searches": "1",
       "search_term": "kids show"
   }
   ```

1. Trovano lo show &quot;Orangey&quot; e lo suonano così che il loro bambino possa guardarlo.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "2",
       "ShowName": "Orangey",
       "VideoStarts": "1"
   }
   ```

1. Più tardi quella sera, il genitore passa al loro profilo e cerca il contenuto per adulti da guardare. Tieni presente che `"ProfileID"` è `1` per rappresentare il profilo adulto. Entrambi i profili appartengono allo stesso account, rappresentato dallo stesso `"PersonID"`.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "1",
       "Searches": "1",
       "search_term": "grownup movie"
   }
   ```

1. Troverete lo show &quot;Analytics After Hours&quot; e godetevi la loro serata guardando.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "1",
       "ShowName": "Analytics After Hours",
       "VideoStarts": "1"
   }
   ```

1. Il giorno dopo, continuano lo spettacolo &quot;Orangey&quot; per il loro bambino. Non è necessario effettuare ricerche perché ora sono già a conoscenza dello spettacolo.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "2",
       "ShowName": "Orangey",
       "VideoStarts": "1"
   }
   ```

Se utilizzi l&#39;allocazione più recente con scadenza Persona, la `"grownup movie"` il termine di ricerca è attribuito all&#39;ultima vista dello spettacolo del bambino.

| Termine di ricerca | Avvio del video |
| --- | --- |
| film di grownup | 2 |
| show per bambini | 1 |

Tuttavia, se hai effettuato un binding `search_term` a `ProfileID`, le ricerche di ciascun profilo vengono isolate nel proprio profilo, attribuite alle serie corrette che cercano.

![Associazione dei visitatori](assets/binding-visitor.png)

Analysis Workspace attribuirà correttamente il secondo episodio di Orangey al termine di ricerca `"kids show"` senza tenere conto delle ricerche di altri profili.

| Termine di ricerca | Avvio del video |
| --- | --- |
| show per bambini | 2 |
| film di grownup | 1 |

## Esempio 4: Valutare il comportamento di ricerca rispetto a quello di ricerca in un&#39;impostazione retail

È possibile eseguire il binding dei valori alle dimensioni impostate sugli eventi precedenti. Quando imposti una variabile con una dimensione di binding, CJA tiene conto del valore persistente. Se questo comportamento non è desiderato, è possibile regolare le impostazioni di persistenza della dimensione di binding. Prendi in considerazione l’esempio seguente in cui `product_finding_method` è impostato su un evento, quindi associato alla metrica Aggiungi carrello sull’evento seguente.

1. Un visitatore esegue una ricerca per `"camera"`. Nessun prodotto impostato in questa pagina.

   ```json
   {
       "search_term": "camera",
       "product_finding_method": "search"
   }
   ```

1. Cliccano su una telecamera che gli piace e la aggiungono al carrello.

   ```json
   {
       "Product": [
           {
               "name": "DSLR Camera"
           }
       ],
       "CartAdd": "1"
   }
   ```

1. Il visitatore passa quindi alla categoria cinture senza eseguire alcuna ricerca. Nessun prodotto impostato in questa pagina.

   ```json
   {
       "category": "Men's belts",
       "product_finding_method": "browse"
   }
   ```

1. Cliccano su una cintura che gli piace e la aggiungono al carrello.

   ```json
   {
       "Product": [
           {
               "name": "Ratchet belt"
           }
       ],
       "CartAdd": "1"
   }
   ```

1. Seguono il processo di pagamento e acquistano questi due articoli.

   ```json
   {
       "Product": [
           {
               "name": "DSLR Camera",
               "price": "399.99"
           },
           {
               "name": "Ratchet belt",
               "price": "19.99"
           }
       ],
       "Purchase": "1"
   }
   ```

Se la persistenza è impostata sull’allocazione più recente senza una dimensione vincolante, tutti i $419,98 dei ricavi sono attribuiti al `browse` metodo di ricerca.

| Metodo di ricerca del prodotto | Ricavi |
| --- | --- |
| navigare | 419,98 |

Se la persistenza viene impostata utilizzando l’allocazione originale senza una dimensione vincolante, tutti i $419,98 dei ricavi vengono attribuiti al `search` metodo di ricerca.

| Metodo di ricerca del prodotto | Ricavi |
| --- | --- |
| ricerca | 419,98 |

Tuttavia, se si esegue un binding `product_finding_method` al carrello Aggiunge una metrica, il rapporto risultante attribuisce ogni prodotto al metodo di ricerca corretto.

| Metodo di ricerca del prodotto | Ricavi |
| --- | --- |
| ricerca | 399,99 |
| navigare | 19,99 |
