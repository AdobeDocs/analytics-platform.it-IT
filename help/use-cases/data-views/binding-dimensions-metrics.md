---
title: Utilizzare dimensioni e metriche di binding nel Customer Journey Analytics
description: Scopri come attribuire dimensioni ad array di oggetti per complesse analisi di persistenza.
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1337'
ht-degree: 83%

---


# Utilizzare dimensioni e metriche di binding nel Customer Journey Analytics

Customer Journey Analytics offre diversi modi per mantenere i valori delle dimensioni oltre l’hit su cui sono impostati. Uno dei metodi di persistenza offerti da Adobe è noto come “binding”. Nelle versioni precedenti di Adobe Analytics, questo concetto era noto come “merchandising”.

Anche se è possibile utilizzare dimensioni di binding con dati evento di livello principale, questo concetto è più indicato per l’utilizzo con [array di oggetti](/help/use-cases/object-arrays.md). È possibile attribuire una dimensione a una parte di un array di oggetti senza applicarla a tutti gli attributi di un dato evento. Ad esempio, puoi attribuire un termine di ricerca a un prodotto nell’array dell’oggetto carrello senza associare tale termine all’intero evento.

## Esempio 1: utilizzare dimensioni di binding per attribuire altri attributi di prodotto a un acquisto

Puoi associare elementi dimensione all’interno di un array oggetto a un’altra dimensione. Quando viene visualizzato l’elemento dimensione associato, Customer Journey Analytics richiama la dimensione associata e la include nell’evento. Considera il seguente percorso del cliente:

1. Un visitatore visualizza una pagina di prodotto relativa a una lavatrice.

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

1. Successivamente, visualizza una pagina di prodotto relativa a un’asciugatrice.

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

1. Infine conclude un acquisto. Il colore di ciascun prodotto non è stato incluso nell’evento di acquisto.

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

Se desideri esaminare i ricavi per colore senza una dimensione di binding, la dimensione `product.color` persiste e attribuisce erroneamente il merito al colore dell’asciugatrice:

| product.color | ricavi |
| --- | --- |
| arancione fluo | 2099 |

Vai a **[!UICONTROL Data views]** e associare il [!DNL Product Color] dimensione a [!DNL Product Name]:

![Dimensione di binding](../assets/binding-dimension.png)

Quando imposti questo modello di persistenza, il Customer Journey Analytics prende nota del nome del prodotto ogni volta che viene impostato il colore del prodotto. Quando riconosce lo stesso nome di prodotto in un evento successivo per questa persona, viene riportato anche il colore del prodotto. Ecco come si presentano gli stessi dati quando si associa il colore del prodotto al nome del prodotto:

| product.color | ricavi |
| --- | --- |
| bianco | 1600 |
| arancione fluo | 499 |

## Esempio 2: utilizzare metriche di binding per associare termini di ricerca all’acquisto di un prodotto

Uno dei metodi di merchandising più comuni in Adobe Analytics prevede l’associazione di un termine di ricerca a un prodotto, in modo che a ogni termine di ricerca venga attribuito il merito per il prodotto appropriato. Considera il seguente percorso del cliente:

1. Un visitatore arriva al tuo sito e cerca “guantoni da boxe”. La metrica delle ricerche viene incrementata di uno, e vengono visualizzati i primi tre risultati di ricerca.

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

2. Trova un paio di guantoni che gli piacciono, e lo aggiunge al carrello.

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

3. Poi il visitatore cerca “racchetta da tennis”. La metrica delle ricerche viene incrementata di uno, e vengono visualizzati i primi tre risultati di ricerca.

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

4. Trova una racchetta che gli piace, e la aggiunge al carrello.

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

5. Il visitatore esegue quindi una terza ricerca, questa volta per “scarpe”. La metrica delle ricerche viene incrementata di uno, e vengono visualizzati i primi tre risultati di ricerca.

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

6. Trova un paio di scarpe che gli piacciono, e lo aggiunge al carrello.

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

7. Il visitatore procede al pagamento e acquista questi tre articoli.

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

Con un modello di allocazione che non include una dimensione di binding con un termine di ricerca, per tutti e tre i prodotti i ricavi vengono attribuiti a un singolo termine di ricerca. Ad esempio, se hai usato [!UICONTROL Original] allocazione con la dimensione termine di ricerca:

| search_term | ricavi |
| --- | --- |
| guantoni da pugilato | $ 204,97 |

Se ha usato [!UICONTROL Most Recent] allocazione con la dimensione termine di ricerca, tutti e tre i prodotti attribuiscono ancora i ricavi a un singolo termine di ricerca:

| search_term | ricavi |
| --- | --- |
| scarpe | $ 204,97 |

Anche se questo esempio include una sola persona, molte persone che cercano cose diverse possono attribuire erroneamente i termini di ricerca a prodotti diversi, rendendo difficile determinare quali siano effettivamente i migliori risultati di ricerca.

Ora puoi eseguire il binding [!DNL Search Term] a [!DNL Product Name] quando [!DNL Searches] La metrica è presente per attribuire correttamente il termine di ricerca ai ricavi.

![Metrica di binding](../assets/binding-metric.png)

In Analysis Workspace, il rapporto risultante sarà simile al seguente:

| search_term | ricavi |
| --- | --- |
| guantoni da pugilato | $ 89,99 |
| racchetta da tennis | $ 34,99 |
| scarpe | $ 79,99 |

Il Customer Journey Analytics rileva automaticamente la relazione tra la dimensione selezionata e la dimensione di binding. Se la dimensione di binding si trova in un array di oggetti mentre la dimensione selezionata si trova a un livello superiore, è necessaria una metrica di binding. Una metrica di binding funge da trigger per una dimensione di binding: si associa solo agli eventi in cui è presente la metrica di binding. Nell’esempio precedente, la pagina dei risultati della ricerca include sempre una dimensione Termine di ricerca e una metrica Ricerche.

L’impostazione della dimensione Termine di ricerca su questo modello di persistenza esegue la logica seguente:

* Quando è impostata la dimensione Termine di ricerca, controlla la presenza del nome del prodotto.
* Se il nome del prodotto non è presente, non viene eseguita alcuna operazione.
* Se il nome del prodotto è presente, viene controllato se è presente la metrica Ricerche.
* Se la metrica Ricerche non è presente, non viene eseguita alcuna operazione.
* Se la metrica Ricerche è presente, il termine di ricerca viene associato a tutti i nomi di prodotto in tale evento. Viene quindi copiato fino allo stesso livello del nome del prodotto per l’evento in questione. In questo esempio, si tratta di product.search_term.
* Se lo stesso nome di prodotto è presente in un evento successivo, il termine di ricerca viene associato anche a tale evento.

## Esempio 3: associare il termine di ricerca video al profilo utente

Puoi associare un termine di ricerca a un profilo utente in modo da mantenere completamente separata la persistenza tra profili diversi. Ad esempio, la tua organizzazione offre un servizio di streaming in cui un account può avere più profili. Il visitatore ha un profilo Bambini e un profilo Adulti.

1. L’account accede al profilo Bambini e cerca un programma TV per bambini. In questo caso `"ProfileID"` è `2` per rappresentare il profilo Bambini.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "2",
       "Searches": "1",
       "search_term": "kids show"
   }
   ```

1. Viene trovato il programma “Orangey”, che viene avviato affinché il bambino possa guardarlo.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "2",
       "ShowName": "Orangey",
       "VideoStarts": "1"
   }
   ```

1. Più tardi, la sera, un genitore passa al proprio profilo e cerca tra i contenuti per adulti. In questo caso `"ProfileID"` è `1` per rappresentare il profilo Adulti. Entrambi i profili appartengono allo stesso account, rappresentato dallo stesso `"PersonID"`.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "1",
       "Searches": "1",
       "search_term": "grownup movie"
   }
   ```

1. Il genitore trova e guarda il programma “Analytics After Hours”.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "1",
       "ShowName": "Analytics After Hours",
       "VideoStarts": "1"
   }
   ```

1. Il giorno dopo, il bambino continua a guardare “Orangey”. Non serve cercare nulla perché ora conoscono già questo programma.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "2",
       "ShowName": "Orangey",
       "VideoStarts": "1"
   }
   ```

Con l’allocazione Più recente e scadenza Persona, il termine di ricerca `"grownup movie"` viene attribuito all’ultima visualizzazione del programma per bambini.

| Termine di ricerca | Avvio del video |
| --- | --- |
| programma per adulti | 2 |
| programma per bambini | 1 |

Tuttavia, se hai associato `search_term` a `ProfileID`, le ricerche di ciascun profilo vengono isolate nel rispettivo profilo, e attribuite al programma giusto.

![Associazione dei visitatori](../assets/binding-profileid.png)

Analysis Workspace attribuirà correttamente il secondo episodio di Orangey al termine di ricerca `"kids show"`, senza tenere conto delle ricerche effettuate per altri profili.

| Termine di ricerca | Avvio del video |
| --- | --- |
| programma per bambini | 2 |
| programma per adulti | 1 |

## Esempio 4: valutare il comportamento di navigazione e di ricerca in ambito retail

È possibile associare valori alle dimensioni impostate negli eventi precedenti. Quando imposti una variabile con una dimensione di binding, il Customer Journey Analytics tiene conto del valore persistente. Se questo comportamento non è desiderato, è possibile regolare le impostazioni di persistenza della dimensione di binding. Considera l’esempio seguente in cui `product_finding_method` è impostato su un evento, quindi associato alla metrica Aggiunte al carrello nell’evento seguente.

1. Un visitatore cerca il termine `"camera"`. Su questa pagina non è impostato alcun prodotto.

   ```json
   {
       "search_term": "camera",
       "product_finding_method": "search"
   }
   ```

1. Fa clic su una fotocamera e la aggiunge al carrello.

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

1. Il visitatore passa quindi alla categoria Cinture da uomo, senza eseguire alcuna ricerca. Su questa pagina non è impostato alcun prodotto.

   ```json
   {
       "category": "Men's belts",
       "product_finding_method": "browse"
   }
   ```

1. Fa clic su una cintura e la aggiunge al carrello.

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

1. Procede al pagamento e acquista questi due articoli.

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

Se la persistenza è impostata sull’allocazione Più recente senza una dimensione di binding, l’intera somma di $ 419,98 viene attribuita al metodo di ricerca `browse`.

| Metodo di ricerca dei prodotti | Ricavi |
| --- | --- |
| navigazione | 419,98 |

Se la persistenza è impostata sull’allocazione Originale senza una dimensione di binding, l’intera somma di $ 419,98 viene attribuita al metodo di ricerca `search`.

| Metodo di ricerca dei prodotti | Ricavi |
| --- | --- |
| ricerca | 419,98 |

Se invece si associa `product_finding_method` alla metrica Aggiunte al carrello, nel rapporto risultante ogni prodotto viene attribuito al rispettivo metodo di ricerca.

| Metodo di ricerca dei prodotti | Ricavi |
| --- | --- |
| ricerca | 399,99 |
| navigazione | 19,99 |


>[!MORELIKETHIS]
>
>[Dimension di binding nelle visualizzazioni dati](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/binding-dimensions-in-data-views.html?lang=it) esercitazione.
