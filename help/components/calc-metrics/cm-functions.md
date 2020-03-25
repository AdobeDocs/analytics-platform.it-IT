---
title: Riferimento - Funzioni di base
description: 'Il Generatore di metriche calcolate consente di applicare funzioni statistiche e matematiche per creare metriche calcolate avanzate. '
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Riferimento - Funzioni di base

Il Generatore di metriche calcolate consente di applicare funzioni statistiche e matematiche per creare metriche calcolate avanzate.

Elenco alfabetico delle funzioni e delle relative definizioni.

> [!NOTE] Se [!DNL metric] è identificato come argomento in una funzione, sono consentite anche altre espressioni di metriche. Ad esempio, [!DNL MAXV(metrics)] consente [!DNL MAXV(PageViews + Visits).]

## Funzioni tabella e funzioni riga

Una funzione di tabella è una in cui l&#39;output è lo stesso per ogni riga della tabella. Una funzione di riga è una in cui l&#39;output è diverso per ogni riga della tabella.

## Valore assoluto (riga)

Restituisce il valore assoluto di un numero. Il valore assoluto di un numero è il numero con un valore positivo.

```
ABS(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale si desidera il valore assoluto. |

## Massimo colonna

Restituisce il valore più grande in un insieme di elementi dimensionali per una colonna metrica. MAXV valuta verticalmente all&#39;interno di una singola colonna (metrica) tra gli elementi dimensionali.

```
MAXV(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Una metrica da valutare. |

## Minima colonna

Restituisce il valore più piccolo in un insieme di elementi dimensionali per una colonna metrica. MINV valuta verticalmente all’interno di una singola colonna (metrica) tra gli elementi di dimensione.

```
MINV(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Una metrica da valutare. |

## Somma colonna

Aggiunge tutti i valori numerici di una metrica all’interno di una colonna (attraverso gli elementi di una dimensione).

```
SUM(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale si desidera il valore totale o la somma. |

## Count (Tabella)

Restituisce il numero o il conteggio di valori diversi da zero per una metrica all&#39;interno di una colonna (il numero di elementi univoci segnalati all&#39;interno di una dimensione).

```
COUNT(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica da contare. |

## Esponente (riga)

Restituisce *e* elevato alla potenza di un numero specificato. La costante *e* è uguale a 2,71828182845904, la base del logaritmo naturale. EXP è l&#39;inverso di LN, il logaritmo naturale di un numero.

```
EXP(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | L&#39;esponente applicato all&#39; *e* di base. |

## Esponenziazione

Operatore di alimentazione

<pre>
pow(x,y) =<sup>xy</sup> = x*x*x*... (y volte)
</pre>

## Media (tabella)

Restituisce la media aritmetica, o media, di una metrica in una colonna.

```
MEAN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale si desidera la media. |

## Mediano (tabella)

Restituisce la mediana di una metrica in una colonna. La mediana è il numero al centro di un insieme di numeri, ovvero la metà dei numeri ha valori che sono maggiori o uguali alla mediana, e la metà sono minori o uguali alla mediana.

```
MEDIAN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale si desidera la media. |

## Modulo

Il resto di col1 / col2, utilizzando la divisione euclidea.

Restituisce il resto dopo la divisione x per y.

```
x = floor(x/y) + modulo(x,y)
```

Il valore restituito ha lo stesso segno dell&#39;input (o è zero).

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

Restituisce il k-esimo percentile di valori per una metrica. È possibile utilizzare questa funzione per stabilire una soglia di accettazione. Ad esempio, puoi decidere di esaminare gli elementi dimensionali con un punteggio superiore al 90 percentile.

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
   <td colname="col2"> Colonna della metrica che definisce lo stato relativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> Il valore percentile compreso tra 0 e 100, incluso. </td> 
  </tr> 
 </tbody> 
</table>

## Quarile (Tabella)

Restituisce il quartile dei valori per una metrica. Ad esempio, i quartili possono essere utilizzati per trovare il 25% dei prodotti più venduti. I valori MINV, MEDIAN e MAXV restituiscono lo stesso valore di QUARTILE quando il grafico a torta è uguale rispettivamente a 0 (zero), 2 e 4.

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
   <td colname="col2"> La metrica per la quale si desidera il valore del quartile. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indica il valore *da restituire. </td> 
  </tr> 
 </tbody> 
</table>

*Se *quart* = 0, QUARTILE restituisce il valore minimo. Se *quart* = 1, QUARTILE restituisce il primo quartile (25 percentile). Se *quart* = 2, QUARTILE restituisce il primo quartile (50 percentile). Se *quart* = 3, QUARTILE restituisce il primo quartile (75 percentile). Se *quart* = 4, QUARTILE restituisce il valore massimo.

## Round

Restituisce il numero intero più vicino per un valore specificato. Ad esempio, se si desidera evitare di riportare i decimali della valuta per le entrate e un prodotto ha $569,34, utilizzare la formula Round( *Revenue*) per arrotondare le entrate al dollaro più vicino, oppure $569. Un prodotto che riporta $569,51 sarà arrotondato al dollaro più vicino, o $570.

```
ROUND(metric)
```

| Argomento | Descrizione |
|---|---|
| *number* | La metrica da arrotondare. |

Il arrotondamento senza un parametro di cifre è uguale al round con un parametro di cifre pari a 0, vale a dire arrotondato al numero intero più vicino. Con un parametro di cifre restituisce un numero di cifre pari a destra del decimale. Se le cifre sono negative, restituisce 0 s a sinistra del decimale.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Conteggio righe

Restituisce il numero di righe per una colonna specificata (il numero di elementi univoci segnalati all&#39;interno di una dimensione). &quot;Superato il numero di errori&quot; viene conteggiato come 1.

## Riga max

Il massimo delle colonne in ogni riga.

## Riga min

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
| *number* | La metrica per la quale si desidera la radice quadrata. |

## Deviazione standard (tabella)

Restituisce la deviazione standard, o radice quadrata della varianza, in base a una popolazione di dati di esempio.

L&#39;equazione per STDEV è:

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
   <td> <b> <i> metrica</i></b> </td> 
   <td> <p> La metrica per la quale si desidera una deviazione standard. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Varianza (tabella)

Restituisce la varianza in base a una popolazione di dati di esempio.

L&#39;equazione per VARIANCE è:

![](assets/variance_eq.png)

dove x è la media del campione, MEAN(*metrica*) e *n* è la dimensione del campione.

```
VARIANCE(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale si desidera la varianza. |

Per calcolare una varianza si osserva un&#39;intera colonna di numeri. Da tale elenco di numeri si calcola prima la media. Una volta ottenuta la media, si passa attraverso ogni voce ed è possibile effettuare le seguenti operazioni:

1. Sottrai la media dal numero.

2. Quadrato il risultato.

3. Aggiungetelo al totale.

Dopo aver ripetuto l&#39;intera colonna, si ottiene un singolo totale. Dividi quindi il totale per il numero di elementi nella colonna. Tale numero è la varianza della colonna. È un singolo numero. Viene tuttavia visualizzata come una colonna di numeri.

Ad esempio, supponiamo che sia presente una colonna a tre elementi:

1

2

3

La media di questa colonna è 2. La varianza per la colonna sarà ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3. In Analisi ad hoc l&#39;aspetto sarà:

1 2/3

2 2/3

3 2/3
