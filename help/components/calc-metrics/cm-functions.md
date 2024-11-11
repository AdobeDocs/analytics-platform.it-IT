---
title: Funzioni di base
description: Il Generatore di metriche calcolate consente di applicare funzioni statistiche e matematiche per generare metriche calcolate avanzate.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 1a84fc71eb29ceabf3a3c5c3e333b78b882ea966
workflow-type: ht
source-wordcount: '1118'
ht-degree: 100%

---

# Funzioni di base


Il [Generatore di metriche calcolate](cm-workflow/cm-build-metrics.md) consente di applicare funzioni statistiche e matematiche. Questo articolo riporta un elenco alfabetico delle funzioni e delle relative definizioni.

>[!NOTE]
>
>Se [!DNL metric] è identificato come argomento in una funzione, sono consentite anche altre espressioni di metriche. Ad esempio, [COLUMN MAXIMUM(metrics)](#column-maximum) consente anche [COLUMN MAXIMUM(PageViews + Visits)](#column-maximum).



## Funzioni tabella e funzioni riga

Una funzione tabella è una funzione in cui l’output è lo stesso per ogni riga della tabella. Una funzione riga è una funzione in cui l’output è diverso per ogni riga della tabella.

Se applicabile e pertinente, una funzione viene annotata con il tipo di funzione: [!BADGE Tabella]{type="Neutral"}[!BADGE Riga]{type="Neutral"}

## Che cosa significa il parametro include-zeros?

Il parametro indica se includere gli zeri all’interno del calcolo. Talvolta lo zero *non* ha alcun significato, ma in determinate occasioni può risultare importante.

Ad esempio, se hai una metrica Revenue (Entrate) e ne aggiungi al report una del tipo Page Views (Visualizzazioni pagina), improvvisamente saranno presenti più righe per le entrate che sono pari a zero. Probabilmente non vorrai che questa metrica aggiuntiva influisca su **[MEAN](cm-functions.md#mean)**, **[ROW MINIMUM](cm-functions.md#row-min)**, **[QUARTILE](cm-functions.md#quartile)** e altri calcoli presenti nella colonna dei ricavi. In questo caso, dovrai controllare il parametro `include-zeros`.

In alternativa, puoi avere due metriche di interesse e una con una media o un minimo più elevati, perché alcune righe sono pari a zero.  In tal caso, puoi scegliere di non selezionare il parametro per includere degli zeri



## Valore assoluto

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ABSOLUTE VALUE(metric)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | La metrica della quale desideri calcolare il valore assoluto. |


## Massimo colonna

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MAXIMUM(metric, include_zeros)]**

Restituisce il valore più grande in un insieme di elementi dimensionali della colonna di una metrica. MAXV valuta verticalmente all’interno di una singola colonna (metrica) tra gli elementi dimensionali.

| Argomento | Descrizione |
|---|---|
| metrica | Richiede almeno una metrica, ma può accettare un numero qualsiasi di metriche come parametri. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |


## Minimo colonna

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MINIMUM(metric, include_zeros)]**

Restituisce il valore più piccolo in un insieme di elementi dimensionali della colonna di una metrica. MINV valuta verticalmente all’interno di una singola colonna (metrica) tra gli elementi dimensionali.

| Argomento | Descrizione |
|---|---|
| metrica | Richiede almeno una metrica, ma può accettare un numero qualsiasi di metriche come parametri. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |


## Somma colonna

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN SUM(metric)]**

Somma tutti i valori numerici di una metrica all’interno di una colonna (negli elementi di una dimensione).

| Argomento | Descrizione |
|---|---|
| metrica | Richiede almeno una metrica, ma può accettare un numero qualsiasi di metriche come parametri. |


## Conteggio

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(metric)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | La metrica da conteggiare. |


## Esponente

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(metric)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | L’esponente applicato alla base e. |


## Media

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | La metrica di cui desideri calcolare la media. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |


## Mediana

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | La metrica di cui desideri calcolare la mediana. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |


## Modulo

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X, metric_Y)]**

Restituisce il resto dopo aver diviso x per y utilizzando la divisione euclidea.

| Argomento | Descrizione |
|---|---|
| metric_X | La prima metrica che desideri dividere. |
| metric_Y | La seconda metrica che desideri dividere. |

### Esempi

Il valore restituito ha lo stesso segno dell’input (o è zero).

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

Per ottenere sempre un numero positivo, utilizza

```
MODULO(MODULO(x,y)+y,y)
```

## Percentile

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE(metric, k, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | Il valore percentile compreso tra 0 e 100 incluso. |
| k | La colonna della metrica che definisce la condizione relativa. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |



## Operatore di potenza

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER OPERATOR(metric_X, metrix_Y)]**

Restituisce x elevato alla potenza y.

| Argomento | Descrizione |
|---|---|
| metric_X | La metrica da elevare alla potenza metric_Y. |
| metric_Y | La potenza a cui desideri elevare metric_X. |


## Quartile

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric, quartile, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}[COLUMN MINIMUM](#column-minimum), [MEDIAN](#median) e [COLUMN MAXIMUM](#column-maximum) restituiscono lo stesso valore di [QUARTILE](#quartile) quando quartile è uguale rispettivamente a `0` (zero), `2` e `4`.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica di cui desideri calcolare il valore del quartile. |
| quartile | Indica quale valore del quartile restituire. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |


## Arrotondamento

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(metric, number)]**

L’arrotondamento senza un parametro *numerico* è uguale all’arrotondamento con un parametro *numero* pari a 0, vale a dire arrotondato al numero intero più vicino.  Con un parametro *numerico* ROUND restituisce il *numero* di cifre a destra del decimale.  Se il *numero* è negativo, restituisce gli 0 a sinistra del decimale.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica da arrotondare. |
| number | Quante cifre a destra del decimale restituire. Se la cifra è negativa, restituisce gli zero a sinistra del decimale. |

### Esempi

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```


## Conteggio righe

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ROW COUNT()]**

Restituisce il numero di righe di una colonna specificata (il numero di elementi univoci riportati all’interno di una dimensione). *Univoci superati* viene conteggiato come 1.


## Massimo riga

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MAX(metric, include_zeros)]**

La somma delle colonne di ogni riga.

| Argomento | Descrizione |
|---|---|
| metrica | Richiede almeno una metrica, ma può accettare un numero qualsiasi di metriche come parametri. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |

## Minimo riga

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MIN(metric, include_zeros)]**

Minimo di colonne di ogni riga.

| Argomento | Descrizione |
|---|---|
| metrica | Richiede almeno una metrica, ma può accettare un numero qualsiasi di metriche come parametri. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |



## Somma righe

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ROW SUM(metric, include_zeros)]**

Somma delle colonne di ogni riga.

| Argomento | Descrizione |
|---|---|
| metrica | Richiede almeno una metrica, ma può accettare un numero qualsiasi di metriche come parametri. |


## Radice quadrata

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT(metric, include_zeros)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | Metrica per la quale desideri calcolare la radice quadrata. |


## Deviazione standard

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL STANDARD DEVIATION(metric, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| | Metrica per la quale desideri calcolare la deviazione standard. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |


## Varianza

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | Metrica per la quale desideri calcolare la varianza. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |


L’equazione per VARIANCE è:

![](assets/variance_eq.png){width="100"}

Dove *x* è la media del campione, [MEAN(*metrica*)](#mean) e *n* è la dimensione del campione.


Per calcolare una varianza, considera un’intera colonna di numeri. Di tale elenco di numeri si calcola prima la media. Una volta ottenuta la media, si esamina ogni voce e si effettuano le seguenti operazioni:

1. Si sottrae la media dal numero.

1. Si eleva al quadrato il risultato.

1. Si aggiunge al totale.

Dopo aver ripetuto per l’intera colonna, si ottiene un singolo totale. Si divide quindi il totale per il numero di elementi nella colonna. Tale numero è la varianza della colonna. È un singolo numero. Viene tuttavia visualizzato come una colonna di numeri.

Nell’esempio della seguente colonna a tre elementi:

| colonna |
|:---:|
| 1 |
| 2 |
| 3 |

La media di questa colonna è 2. La varianza della colonna sarà ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.




<!--

## Absolute Value (Row)

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum 

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum 

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) 

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) 

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation 

Power Operator


pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)


## Mean (Table) 

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) 

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo 

The remainder of col1 / col2, using Euclidean division.

Returns the remainder after dividing x by y.

```
x = floor(x/y) + modulo(x,y)
```

The return value has the same sign as the input (or is zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

To always get a positive number, use 

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) 

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric column that defines relative standing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> The percentile value in the range 0 to 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) 

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric for which you want the quartile value. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indicates which *value to return. </td> 
  </tr> 
 </tbody> 
</table>

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round 

Returns the nearest integer for a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. A product reporting $569.51 will be round to the nearest dollar, or $570.

```
ROUND(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric you want to round.  |

Round without a digits parameter is the same as round with a digits parameter of 0, namely round to the nearest integer. With a digits parameter it returns that many digits to the right of the decimal. If digits is negative, it returns 0's to the left of the decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count 

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max 

The maximum of the columns in each row.

## Row Min 

The minimum of the columns in each row.

## Row Sum

The sum of the columns of each row.

## Square Root (Row) 

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric for which you want the square root.  |

## Standard Deviation (Table) 

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> The metric for which you want for standard deviation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) 

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the variance.  |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.

2. Square the result.

3. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In case of a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

-->