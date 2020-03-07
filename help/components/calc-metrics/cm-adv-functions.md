---
title: Riferimento - Funzioni avanzate
description: Per accedere a queste funzioni, selezionare Mostra avanzate dall'elenco a discesa Funzioni.
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Riferimento - Funzioni avanzate

Accedere a queste funzioni selezionando **[!UICONTROL Show Advanced]** l&#39;elenco a **[!UICONTROL Functions]** discesa.

## Funzioni tabella e funzioni riga

Una funzione di tabella è una in cui l&#39;output è lo stesso per ogni riga della tabella. Una funzione di riga è una in cui l&#39;output è diverso per ogni riga della tabella.

## Che cosa significa il parametro Include-Zeros?

Indica se includere zeri nel calcolo. A volte zero significa &quot;niente&quot;, ma a volte è importante.

Ad esempio, se hai una metrica Revenue (Entrate) e aggiungi una metrica Page Views (Visualizzazioni pagina) al report, improvvisamente ci sono più righe per le tue entrate che sono tutte pari a zero. Probabilmente non volete che questo influenzi i MEAN, MIN, QUARTILE, ecc. calcoli disponibili nella colonna Entrate. In questo caso, controllate il parametro include-zeros.

D&#39;altra parte, se hai due metriche che ti interessano, potrebbe non essere giusto dire che una ha una media o un minimo più alti perché alcune delle sue righe erano zeri, quindi non controllereste il parametro per includere gli zeri.

## AND

Restituisce il valore del relativo argomento. Utilizzare NOT per assicurarsi che un valore non sia uguale a un particolare valore.

> [!NOTE] 0 (zero) significa False e qualsiasi altro valore è True.

```
AND(logical_test1,[logical_test2],...)
```

| Argomento | Descrizione |
|---|---|
| *logical_test1* | Obbligatorio. Qualsiasi valore o espressione che può essere valutata su TRUE o FALSE. |
| *logical_test2* | Facoltativo. Condizioni aggiuntive da valutare come TRUE o FALSE |

## Numero approssimativo distinto (dimensione)

Restituisce il conteggio distinto approssimativo degli elementi dimensione per la dimensione selezionata. La funzione utilizza il metodo HyperLogLog (HLL) per approssimare i conteggi distinti.  È configurato per garantire che il valore sia compreso entro il 5% del valore effettivo 95% del tempo.

```
Approximate Count Distinct (dimension)
```

| Argomento |  |
|---|---|
| *size* | La dimensione per la quale si desidera il conteggio approssimativo degli elementi distinti. |

## Esempio di caso di utilizzo

L&#39;eVar per l&#39;ID cliente approssimativo (Approximate Count Distinct) è un caso d&#39;uso comune per questa funzione.

Definizione per una nuova metrica calcolata &#39;clienti prossimi&#39;:

![](assets/approx-count-distinct.png)

Questo è il modo in cui la metrica &quot;Approximate Customers&quot; (Clienti approssimati) può essere utilizzata nei report:

![](assets/approx-customers.png)

## Superato il numero di errori

Analogamente a Count() e RowCount(), Approximate Count Distinct() è soggetto ai limiti [di](https://marketing.adobe.com/resources/help/en_US/reference/metrics_uniques_high_numbers.html)&quot;univesità superate&quot;. Se per una dimensione viene raggiunto il limite di &quot;univoci superate&quot; entro un mese specifico, il valore viene conteggiato come 1 elemento dimensione.

## Confronto delle funzioni di conteggio

Approximate Count Distinct() è un miglioramento rispetto alle funzioni Count() e RowCount(), perché la metrica creata può essere utilizzata in qualsiasi report dimensionale per rappresentare un conteggio approssimativo di elementi per una dimensione separata. Ad esempio, un numero totale di ID cliente utilizzati in un rapporto Tipo dispositivo mobile.

Questa funzione sarà leggermente meno accurata di Count() e RowCount() perché utilizza il metodo HLL, mentre Count() e RowCount() sono conteggi esatti.

## Arco coseno (riga)

Restituisce l&#39;arccosina, o l&#39;inverso del coseno, di una metrica. L&#39;arcoseno è l&#39;angolo il cui coseno è numero. L&#39;angolo restituito è espresso in radianti compresi tra 0 (zero) e pi. Per convertire il risultato dai radianti in gradi, moltiplicatelo per 180/PI( ).

```
ACOS(metric)
```

| Argomento |  |
|---|---|
| *metrica* | Coseno dell&#39;angolo desiderato da -1 a 1. |

## Arco sinusoidale (riga)

Restituisce l&#39;arcoseno, o seno inverso, di un numero. L&#39;arcsina è l&#39;angolo il cui seno è numero. L’angolo restituito è espresso in radianti nell’intervallo da -pi/2 a pi/2. Per esprimere l&#39;arcsina in gradi, moltiplicate il risultato per 180/PI( ).

```
ASIN(metric) 
```

| Argomento |  |
|---|---|
| *metrica* | Coseno dell&#39;angolo desiderato da -1 a 1. |

## Tangente arco (riga)

Restituisce l&#39;arcotangente, o tangente inversa, di un numero. L&#39;arctangent è l&#39;angolo la cui tangente è un numero. L’angolo restituito è espresso in radianti nell’intervallo da -pi/2 a pi/2. Per esprimere l’angolo di inclinazione in gradi, moltiplicate il risultato per 180/PI( ).

```
ATAN(metric)
```

| Argomento |  |
|---|---|
| *metrica* | Coseno dell&#39;angolo desiderato da -1 a 1. |

## Regressione esponenziale: Predicato Y (riga)

Calcola i valori y previsti (metrica_Y), in base ai valori x noti (metrica_X) utilizzando il metodo dei &quot;minimi quadrati&quot; per calcolare la riga di adattamento ottimale in base a .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## Cdf-T

Restituisce la percentuale di valori nella distribuzione t di uno studente con n gradi di libertà con un punteggio z inferiore a x.

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Restituisce la percentuale di valori in una distribuzione normale con un punteggio z inferiore a x.

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## Soffitto (riga)

Restituisce il numero intero più piccolo, non minore di un valore specificato. Ad esempio, se si desidera evitare di riportare i decimali della valuta per i ricavi e un prodotto ha $569,34, utilizzare la formula CEILING( *Revenue*) per arrotondare i ricavi al dollaro più vicino, o $570.

```
CEILING(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica da arrotondare. |

## Coseno (riga)

Restituisce il coseno dell&#39;angolo specificato. Se l&#39;angolo è in gradi, moltiplicate l&#39;angolo per PI( )/180.

```
COS(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Angolo in radianti per il quale si desidera il coseno. |

## Radice cubo

Restituisce la radice cubica positiva di un numero. La radice del cubo di un numero è il valore di quel numero elevato alla potenza di 1/3.

```
CBRT(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale si desidera la radice del cubo. |

## Cumulativo

Restituisce la somma di x per le ultime righe N (come ordinato dalla dimensione, utilizzando valori hash per i campi basati su stringhe).

Se N &lt;= 0 utilizza tutte le righe precedenti. Poiché è ordinato dalla dimensione, è utile solo per le dimensioni che hanno un ordine naturale come data o lunghezza del percorso.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## Media cumulativa

Restituisce la media delle ultime righe N.

Se N &lt;= 0 utilizza tutte le righe precedenti. Poiché è ordinato dalla dimensione, è utile solo per le dimensioni che hanno un ordine naturale come data o lunghezza del percorso.

> [!NOTE] Questo non funziona come previsto con metriche di tasso come entrate/visitatore: essa calcola la media dei tassi invece di sommare le entrate rispetto all&#39;ultima N e sommare i visitatori rispetto all&#39;ultima N e quindi dividendoli. Utilizzate

```
cumul(revenue)/cumul(visitor)
```

## Uguale

Restituisce elementi che corrispondono esattamente a un valore numerico o a una stringa.

## Coefficiente di correlazione esponenziale (tabella)

Restituisce il coefficiente di correlazione, *r*, tra due colonne metriche ( *metriche_A* e *metriche_B*) per l&#39;equazione di regressione.

```
CORREL.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Metrica che si desidera correlare con *metriche_Y*. |
| *metriche_Y* | Metrica che si desidera correlare con *metriche_X*. |

## Regressione esponenziale: Intercept (tabella)

Restituisce l&#39;intercetta, *b*, tra due colonne metriche ( *metriche_X* e *metriche_Y*) per

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## Regressione esponenziale: Pendenza (tabella)

Restituisce la pendenza, *a*, tra due colonne metriche ( *metriche_X* e *metriche_Y*) per .

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## Floor (riga)

Restituisce il numero intero più grande non maggiore di un valore specificato. Ad esempio, se si desidera evitare di riportare i decimali della valuta per le entrate e un prodotto ha $569,34, utilizzare la formula FLOOR( *Revenue*) per arrotondare le entrate al dollaro più vicino, o $569.

```
FLOOR(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica da arrotondare. |

## Maggiore di

Restituisce elementi il cui conteggio numerico è maggiore del valore immesso.

## Maggiore o uguale a

Restituisce elementi il cui conteggio numerico è maggiore o uguale al valore immesso.

## Coseno iperbolico (riga)

Restituisce il coseno iperbolico di un numero.

```
COSH(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Angolo in radianti per il quale si desidera trovare il coseno iperbolico. |

## Sine iperbolico (riga)

Restituisce il seno iperbolico di un numero.

```
SINH(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Angolo in radianti per il quale si desidera trovare il seno iperbolico. |

## Tangente iperbolico (riga)

Restituisce la tangente iperbolica di un numero.

```
TANH(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Angolo in radianti per il quale si desidera trovare il tanget iperbolico. |

## IF (riga)

La funzione IF restituisce un valore se una condizione specificata restituisce TRUE e un altro valore se tale condizione restituisce FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argomento | Descrizione |
|---|---|
| *logical_test* | Obbligatorio. Qualsiasi valore o espressione che può essere valutata su TRUE o FALSE. |
| *[value_if_true]* | Il valore che si desidera restituire se l&#39;argomento *logical_test* restituisce TRUE. (Questo argomento per impostazione predefinita è 0 se non è incluso.) |
| *[value_if_false]* | Il valore che si desidera restituire se l&#39;argomento *logical_test* restituisce FALSE. (Questo argomento per impostazione predefinita è 0 se non è incluso.) |

## Minore di

Restituisce elementi il cui conteggio numerico è inferiore al valore immesso.

## Minore o uguale a

Restituisce elementi il cui conteggio numerico è minore o uguale al valore immesso.

## regressione lineare_ Coefficiente di correlazione

Y = a X + b. Restituisce il coefficiente di correlazione

## regressione lineare_ Intercept

Y = a X + b. Restituisce b.

## regressione lineare_Predicato Y

Y = a X + b. Restituisce Y.

## regressione lineare_ Slope

Y = a X + b. Restituisce un valore.

## Log Base 10 (riga)

Restituisce il logaritmo base-10 di un numero.

```
LOG10(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Numero reale positivo per il quale si desidera il logaritmo base 10. |

## regressione del registro: Coefficiente di correlazione (tabella)

Restituisce il coefficiente di correlazione, *r*, tra due colonne metriche (*metriche_X* e *metriche_Y*) per l&#39;equazione di regressione [!DNL Y = a ln(X) + b]. Viene calcolata utilizzando l&#39;equazione CORREL.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Metrica che si desidera correlare con *metriche_Y*. |
| *metriche_Y* | Metrica che si desidera correlare con *metriche_X*. |

## regressione del registro: Intercept (tabella)

Restituisce l&#39;intercetta *b* come regressione dei minimi quadrati tra due colonne metriche (*metriche_X* e *metriche_Y*) per l&#39;equazione di regressione [!DNL Y = a ln(X) + b]. Viene calcolata utilizzando l&#39;equazione INTERCEPT.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## Regressione registro: Predicato Y (riga)

Calcola i [!DNL y] valori previsti (metrica_Y), in base ai [!DNL x] valori noti (metrica_X) utilizzando il metodo &quot;minimi quadrati&quot; per calcolare la riga di adattamento ottimale in base a [!DNL Y = a ln(X) + b]. Viene calcolata utilizzando l&#39;equazione STIMATE.

Nell&#39;analisi di regressione, questa funzione calcola i [!DNL y] valori previsti (*metriche_Y*), dati i [!DNL x] valori noti (*metriche_X*) utilizzando il logaritmo per calcolare la linea più adatta all&#39;equazione di regressione [!DNL Y = a ln(X) + b]. I [!DNL a] valori corrispondono a ciascun valore x ed [!DNL b] è un valore costante.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## regressione del registro: Pendenza (tabella)

Restituisce la pendenza, *a*, tra due colonne metriche (*metriche_X* e *metriche_Y*) per l&#39;equazione di regressione [!DNL Y = a ln(X) + b]. Viene calcolata utilizzando l&#39;equazione SLOPE.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argomento | Descrizione |
|---|---|
| *metriche_A* | Una metrica da designare come dati dipendenti. |
| *metriche_B* | Una metrica da designare come dati indipendenti. |

## Registro naturale

Restituisce il logaritmo naturale di un numero. I logaritmi naturali si basano sulla costante *e* (2.71828182845904). LN è l&#39;inverso della funzione EXP.

```
LN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Il numero reale positivo per cui si desidera il logaritmo naturale. |

## NOT

Restituisce 1 se il numero è 0 o restituisce 0 se è presente un altro numero.

```
NOT(logical)
```

| Argomento | Descrizione |
|---|---|
| *logico* | Obbligatorio. Un valore o un&#39;espressione che può essere valutata su TRUE o FALSE. |

Per utilizzare NOT è necessario verificare se le espressioni (&lt;, >, =, &lt;>, ecc.) restituisce 0 o 1 valori.

## Non uguale

Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore immesso.

## O (Riga)

Restituisce TRUE se un qualsiasi argomento è TRUE o FALSE se tutti gli argomenti sono FALSE.

> [!NOTE] 0 (zero) significa False e qualsiasi altro valore è True.

```
OR(logical_test1,[logical_test2],...)
```

| Argomento | Descrizione |
|---|---|
| *logical_test1* | Obbligatorio. Qualsiasi valore o espressione che può essere valutata su TRUE o FALSE. |
| *logical_test2* | Facoltativo. Condizioni aggiuntive da valutare come TRUE o FALSE |

## Pi

Restituisce la costante PI, 3,14159265358979, con precisione di 15 cifre.

```
PI()
```

La [!DNL PI]funzione non ha argomenti.

## Regolazione di potenza: Coefficiente di correlazione (tabella)

Restituisce il coefficiente di correlazione, *r*, tra due colonne metriche (*metriche_X* e *metriche_Y*) per [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Metrica che si desidera correlare con *metriche_Y*. |
| *metriche_Y* | Metrica che si desidera correlare con *metriche_X*. |

## Regolazione di potenza: Intercept (tabella)

Restituisce l&#39;intercetta, *b*, tra due colonne metriche (*metriche_X* e *metriche_Y*) per [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## Regolazione di potenza: Predicato Y (riga)

Calcola i [!DNL y] valori previsti ( [!DNL metric_Y]), in base ai [!DNL x] valori noti ( [!DNL metric_X]) utilizzando il metodo dei &quot;minimi quadrati&quot; per calcolare la riga di migliore adattamento [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## Regolazione di potenza: Pendenza (tabella)

Restituisce la pendenza, *a*, tra due colonne metriche (*metriche_X* e *metriche_Y*) per [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## Regolazione quadratica: Coefficiente di correlazione (tabella)

Restituisce il coefficiente di correlazione, *r*, tra due colonne metriche (*metriche_X* e *metriche_Y*) per [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Metrica che si desidera correlare con *metriche_Y*. |
| *metriche_Y* | Metrica che si desidera correlare con *metriche_X*. |

## Regolazione quadratica: Intercept (tabella)

Restituisce l&#39;intercetta, *b*, tra due colonne metriche (*metriche_X* e *metriche_Y*) per [!DNL Y=(a*X+b)]***.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## Regolazione quadratica: Predicato Y (riga)

Calcola i [!DNL y] valori previsti (metrica_Y), in base ai [!DNL x] valori noti (metrica_X) utilizzando il metodo dei minimi quadrati per calcolare la riga di adattamento ottimale utilizzando [!DNL Y=(a*X+b)]****.

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argomento | Descrizione |
|---|---|
| *metriche_A* | Una metrica da designare come dati dipendenti. |
| *metriche_B* | Una metrica da designare come dati dipendenti. |

## Regolazione quadratica: Pendenza (tabella)

Restituisce la pendenza, *a*, tra due colonne metriche (*metriche_X* e metriche_Y) per [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## Regolazione reciproca: Coefficiente di correlazione (tabella)

Restituisce il coefficiente di correlazione, *r*, tra due colonne metriche (*metriche_X)* e *metriche_Y*) per [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Metrica che si desidera correlare con *metriche_Y*. |
| *metriche_Y* | Metrica che si desidera correlare con *metriche_X*. |

## Regolazione reciproca: Intercept (tabella)

Restituisce l&#39;intercetta, *b*, tra due colonne metriche (*metriche_X* e *metriche_Y*) per [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## Regolazione reciproca: Predicato Y (riga)

Calcola i [!DNL y] valori previsti (metrica_Y), in base ai [!DNL x] valori noti (metrica_X) utilizzando il metodo dei minimi quadrati per calcolare la riga di adattamento ottimale utilizzando [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## Regolazione reciproca: Pendenza (tabella)

Restituisce la pendenza, *a*, tra due colonne metriche (*metriche_X* e *metriche_Y*) per [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metriche_X* | Una metrica da designare come dati dipendenti. |
| *metriche_Y* | Una metrica da designare come dati indipendenti. |

## Sinusoidale (riga)

Restituisce il seno dell&#39;angolo specificato. Se l&#39;angolo è in gradi, moltiplicate l&#39;angolo per PI( )/180.

```
SIN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Angolo in radianti per il quale si desidera il seno. |

## Punteggio T

Alias per Z-Score, vale a dire la deviazione dalla media divisa per la deviazione standard

## Test T

Esegue un test t-taglia m con un punteggio t di colonna e un grado di libertà.

La firma è `t_test( x, n, m )`. Sotto, chiama semplicemente `m*cdf_t(-abs(x),n)`. È simile alla funzione z-test in esecuzione `m*cdf_z(-abs(x))`.

Qui `m` è il numero di code, e `n` i gradi di libertà. Devono essere numeri (costanti per l’intero rapporto, ovvero non modificati per riga).

`X` è la statistica del test t, e spesso è una formula (ad es., zscore) basata su una metrica e sarà valutata su ogni riga.

Il valore restituito è la probabilità di visualizzare la statistica x del test in base ai gradi di libertà e al numero di code.

**Esempi:**

1. Utilizzatelo per individuare i contorni:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combinatelo `if` per ignorare tassi di rimbalzo molto alti o bassi e contare le visite su tutto il resto:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangente

Restituisce la tangente dell&#39;angolo specificato. Se l&#39;angolo è in gradi, moltiplicate l&#39;angolo per PI( )/180.

```
TAN (metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Angolo in radianti per il quale si desidera la tangente. |

## Punteggio Z (riga)

Restituisce il punteggio Z, o il punteggio normale, in base a una distribuzione normale. Il punteggio Z è il numero di deviazioni standard che un&#39;osservazione è dalla media. Un punteggio Z pari a 0 (zero) indica che il punteggio è uguale alla media. Un punteggio Z può essere positivo o negativo, indicando se è superiore o inferiore alla media e il numero di deviazioni standard.

L&#39;equazione per il punteggio Z è:

![](assets/z_score.png)

dove [!DNL x] è il punteggio grezzo, [!DNL μ] è la media della popolazione, ed [!DNL σ] è la deviazione standard della popolazione.

> [!NOTE] [!DNL μ] (mu) e (sigma) vengono calcolati automaticamente dalla metrica[!DNL σ] .

Z-score(metrica)

<table id="table_AEA3622A58F54EA495468A9402651E1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argomento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metrica</i> </td> 
   <td colname="col2"> <p> Restituisce il valore del primo argomento diverso da zero. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Z-Test

Effettua un test Z con Z-code con Z-score di A.

Restituisce la probabilità che la riga corrente possa essere vista per caso nella colonna.

> [!NOTE] Presuppone che i valori siano normalmente distribuiti.

