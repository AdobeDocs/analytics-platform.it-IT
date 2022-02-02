---
title: 'Riferimento: funzioni di base'
description: Il Generatore di metriche calcolate consente di applicare funzioni statistiche e matematiche per generare metriche calcolate avanzate.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 100%

---

# Riferimento: funzioni di base

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Il Generatore di metriche calcolate consente di applicare funzioni statistiche e matematiche per generare metriche calcolate avanzate.

Di seguito è riportato un elenco alfabetico delle funzioni e delle relative definizioni.

>[!NOTE]
>
>Se [!DNL metric] è identificato come argomento in una funzione, sono consentite anche altre espressioni di metriche. Ad esempio, [!DNL MAXV(metrics)] consente anche [!DNL MAXV(PageViews + Visits).]

## Funzioni tabella e funzioni riga

Una funzione tabella è una funzione in cui l’output è lo stesso per ogni riga della tabella. Una funzione riga è una funzione in cui l’output è diverso per ogni riga della tabella.

## Valore assoluto (riga)

Restituisce il valore assoluto di un numero. Il valore assoluto di un numero è il numero con un valore positivo.

```
ABS(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica della quale desideri il valore assoluto. |

## Massimo colonna

Restituisce il valore più grande in un insieme di elementi dimensionali della colonna di una metrica. MAXV valuta verticalmente all’interno di una singola colonna (metrica) tra gli elementi dimensionali.

```
MAXV(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Una metrica che desideri valutare. |

## Minimo colonna

Restituisce il valore più piccolo in un insieme di elementi dimensionali della colonna di una metrica. MINV valuta verticalmente all’interno di una singola colonna (metrica) tra gli elementi dimensionali.

```
MINV(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Una metrica che desideri valutare. |

## Somma colonna

Somma tutti i valori numerici di una metrica all’interno di una colonna (negli elementi di una dimensione).

```
SUM(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica della quale desideri il valore totale o la somma. |

## Conteggio (tabella)

Restituisce il numero, o conteggio, di valori diversi da zero di una metrica all’interno di una colonna (il numero di elementi univoci riportati all’interno di una dimensione).

```
COUNT(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica che desideri conteggiare. |

## Esponente (riga)

Restituisce *e* elevato alla potenza di un numero specificato. La costante *e* è uguale a 2,71828182845904, la base del logaritmo naturale. EXP è l’inverso di LN, il logaritmo naturale di un numero.

```
EXP(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | L’esponente applicato alla base *e*. |

## Esponenziazione

Operatore di potenza

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*… (y volte)
</pre>

## Media (tabella)

Restituisce la media aritmetica, o media, di una metrica in una colonna.

```
MEAN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica di cui desideri la media. |

## Mediana (tabella)

Restituisce la mediana di una metrica in una colonna. La mediana è il numero nel mezzo di un insieme di numeri, ovvero metà dei numeri ha valori che sono maggiori o uguali alla mediana, e metà sono minori o uguali alla mediana.

```
MEDIAN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica di cui desideri la mediana. |

## Modulo

Il resto di col1 / col2, utilizzando la divisione euclidea.

Restituisce il resto dopo aver diviso x per y.

```
x = floor(x/y) + modulo(x,y)
```

Il valore restituito ha lo stesso segno dell’input (o è zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Per ottenere sempre un numero positivo, utilizza

```
modulo(modulo(x,y)+y,y)
```

## Percentile (tabella)

Restituisce il k-esimo percentile dei valori di una metrica. Puoi utilizzare questa funzione per stabilire una soglia di accettazione. Ad esempio, puoi decidere di esaminare gli elementi dimensionali con un punteggio superiore al 90 percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argomento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metrica</i> </td> 
   <td colname="col2"> La colonna della metrica che definisce la condizione relativa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> Il valore percentile compreso tra 0 e 100 incluso. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (tabella)

Restituisce il quartile dei valori di una metrica. Ad esempio, i quartili possono essere utilizzati per trovare il 25% dei prodotti che generano maggiori ricavi. MINV, MEDIAN e MAXV restituiscono lo stesso valore di QUARTILE quando il quarto è uguale rispettivamente a 0 (zero), 2 e 4.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argomento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metrica</i> </td> 
   <td colname="col2"> La metrica di cui desideri il valore del quartile. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quarto </p> </td> 
   <td colname="col2"> Indica il valore* da restituire. </td> 
  </tr> 
 </tbody> 
</table>

*Se *quarto* = 0, QUARTILE restituisce il valore minimo. Se *quarto* = 1, QUARTILE restituisce il primo quartile (25 percentile). Se *quarto* = 2, QUARTILE restituisce il primo quartile (50 percentile). Se *quarto* = 3, QUARTILE restituisce il primo quartile (75 percentile). Se *quarto* = 4, QUARTILE restituisce il valore massimo.

## Arrotondamento

Restituisce il numero intero più vicino a un determinato valore. Ad esempio, se desideri evitare di riportare i decimali della valuta per le entrate e un prodotto ha 569,34 $, utilizza la formula Round(*Entrate*) per arrotondare le entrate al dollaro più vicino, cioè 569 $. Un prodotto che riporta 569,51 $ sarà arrotondato al dollaro più vicino, cioè 570 $.

```
ROUND(metric)
```

| Argomento | Descrizione |
|---|---|
| *numero* | La metrica che desideri arrotondare. |

L’arrotondamento senza un parametro di cifre è uguale all’arrotondamento con un parametro di cifre pari a 0, vale a dire arrotondato al numero intero più vicino. Con un parametro di cifre restituisce quel numero di cifre a destra del decimale. Se la cifra è negativa, restituisce quel numero di 0 a sinistra del decimale.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Conteggio righe

Restituisce il numero di righe di una colonna specificata (il numero di elementi univoci riportati all’interno di una dimensione). “Univoci superati” viene conteggiato come 1.

## Massimo riga

Il massimo delle colonne in ogni riga.

## Minimo riga

Il minimo delle colonne in ogni riga.

## Somma righe

La somma delle colonne di ogni riga.

## Radice quadrata (riga)

Restituisce la radice quadrata positiva di un numero. La radice quadrata di un numero è il valore di quel numero elevato alla potenza di 1/2.

```
SQRT(metric)
```

| Argomento | Descrizione |
|---|---|
| *numero* | La metrica della quale desideri la radice quadrata. |

## Deviazione standard (tabella)

Restituisce la deviazione standard, o radice quadrata della varianza, in base a una popolazione di dati campione.

L’equazione per STDEV è:

![](assets/std_dev.png)

dove x è la media del campione (*metrica*) e *n* è la dimensione del campione.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argomento</b> </td> 
   <td> <b> Descrizione</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metrica</i> </b> </td> 
   <td> <p> La metrica di cui desideri la deviazione standard. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Varianza (tabella)

Restituisce la varianza in base a una popolazione di dati campione.

L’equazione per VARIANCE è:

![](assets/variance_eq.png)

dove x è la media del campione, MEAN(*metrica*) e *n* è la dimensione del campione.

```
VARIANCE(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica di cui desideri la varianza. |

Per calcolare una varianza, si considera un’intera colonna di numeri. Di tale elenco di numeri si calcola prima la media. Una volta ottenuta la media, si esamina ogni voce e si effettuano le seguenti operazioni:

1. Si sottrae la media dal numero.

2. Si eleva al quadrato il risultato.

3. Si aggiunge al totale.

Dopo aver ripetuto per l’intera colonna, si ottiene un singolo totale. Si divide quindi il totale per il numero di elementi nella colonna. Tale numero è la varianza della colonna. È un singolo numero. Viene tuttavia visualizzato come una colonna di numeri.

Ad esempio, supponiamo che sia presente una colonna con tre elementi:

1

2

3

La media di questa colonna è 2. La varianza della colonna sarà ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3.
