---
title: Riferimento - Funzioni avanzate
description: Per accedere a queste funzioni, seleziona Show Advanced (Mostra avanzate) dall’elenco a discesa Functions (Funzioni).
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: ht
source-wordcount: '2939'
ht-degree: 100%

---

# Riferimento - Funzioni avanzate

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Accedi a queste funzioni selezionando **[!UICONTROL Show Advanced]** nell’elenco a discesa **[!UICONTROL Functions]**.

## Funzioni tabella e Funzioni riga

Una funzione tabella è una funzione in cui l’output è lo stesso per ogni riga della tabella. Una funzione riga contiene un output diverso per ogni riga della tabella.

## Che cosa significa il parametro Include-Zeros?

Il parametro indica se includere gli zeri all’interno del calcolo. Talvolta lo zero non ha alcun significato, ma in determinate occasioni può risultare importante.

Ad esempio, se hai una metrica Revenue (Entrate) e ne aggiungi al report una del tipo Page Views (Visualizzazioni pagina), improvvisamente saranno presenti più righe per le entrate che sono pari a zero. È probabile che non vorrai estendere questo risultato ai calcoli MEAN, MIN, QUARTILE e così via, che sono presenti nella colonna Revenue (Entrate). In questo caso, dovrai controllare il parametro include-zeros.

D’altra parte, se disponi di due metriche di tuo interesse, potrebbe non essere giusto affermare che una presenti una media o un minimo più alto in virtù di alcune righe pari a zero, quindi non controlleresti il parametro in modo da includere gli zeri.

## AND

Restituisce il valore del relativo argomento. Per assicurarti che un valore non sia uguale a un valore particolare, utilizza la funzione NOT.

>[!NOTE]
>
>0 (zero) significa False, mentre qualsiasi altro valore corrisponde a True.

```
AND(logical_test1,[logical_test2],...)
```

| Argomento | Descrizione |
|---|---|
| *logical_test1* | Obbligatorio. Qualsiasi valore o espressione che può essere valutato come TRUE o FALSE. |
| *logical_test2* | Facoltativo. Condizioni aggiuntive da valutare come TRUE o FALSE. |

## Approximate Count Distinct (dimension) (Conteggio valori univoci approssimativo (dimensione))

Restituisce il conteggio valori univoci approssimativo degli elementi dimensione per la dimensione selezionata. La funzione sfrutta il metodo HyperLogLog (HLL) per approssimare i conteggi valori univoci ed è configurata per garantire che il valore sia compreso entro il 5% del valore effettivo per il 95% del tempo.

```
Approximate Count Distinct (dimension)
```

| Argomento |  |
|---|---|
| *dimension* | La dimensione per la quale vuoi ottenere il conteggio dei valori univoci approssimativo degli elementi. |

## Caso d’uso di esempio

Approximate Count Distinct (customer ID eVar) (Conteggio valori univoci approssimativo (eVar ID cliente)) rappresenta un caso d’uso comune per questa funzione.

Definizione di una nuova metrica calcolata “Approximate Customers” (Clienti approssimativi):

![](assets/approx-count-distinct.png)

Questo è il modo in cui la metrica “Approximate Customers” (Clienti approssimativi) potrebbe essere utilizzata nel reporting:

![](assets/approx-customers.png)

## Uniques Exceeded (Univoci superati)

Analogamente a Count() e RowCount(), Approximate Count Distinct() è soggetto ai [limiti di “uniques exceeded” (univoci superati)](https://experienceleague.adobe.com/docs/analytics/technotes/low-traffic.html?lang=it). Se in un determinato mese si raggiunge il limite “uniques exceeded” per una dimensione, il valore viene conteggiato come 1 elemento dimensione.

## Confronto delle funzioni di conteggio

Approximate Count Distinct() rappresenta un miglioramento rispetto alle funzioni Count() e RowCount(), perché la metrica creata può essere utilizzata in qualsiasi report dimensionale per rappresentare un conteggio approssimativo di elementi per una dimensione separata. Ad esempio, un conteggio degli ID cliente utilizzati all’interno di un report Mobile Device Type (Tipo dispositivo mobile).

Questa funzione risulterà leggermente meno precisa rispetto a Count() e RowCount() perché sfrutta il metodo HLL, mentre Count() e RowCount() rappresentano conteggi esatti.

## Arcocoseno (riga)

Restituisce l’arcocoseno di una metrica, detto anche inverso del coseno. L’arcocoseno è l’angolo di cui è numero il coseno. L’angolo restituito è espresso in radianti compresi nell’intervallo tra 0 (zero) e pi. Per convertire il risultato dai radianti ai gradi, moltiplicalo per 180/PI( ).

```
ACOS(metric)
```

| Argomento |  |
|---|---|
| *metric* | Il coseno dell’angolo desiderato da -1 a 1. |

## Arcoseno (riga)

Restituisce l’arcoseno, o seno inverso, di un numero. L’arcoseno è l’angolo di cui è numero il seno. L’angolo restituito è espresso in radianti compresi nell’intervallo tra -pi/2 e pi/2. Per esprimere l’arcoseno in gradi, moltiplica il risultato per 180/PI( ).

```
ASIN(metric)
```

| Argomento |  |
|---|---|
| *metric* | Il coseno dell’angolo desiderato da -1 a 1. |

## Arcotangente (riga)

Restituisce l’arcotangente, o tangente inversa, di un numero. L’arcotangente è l’angolo di cui è numero la tangente. L’angolo restituito è espresso in radianti compresi nell’intervallo tra -pi/2 e pi/2. Per esprimere l’arcotangente in gradi, moltiplica il risultato per 180/PI( ).

```
ATAN(metric)
```

| Argomento |  |
|---|---|
| *metric* | Il coseno dell’angolo desiderato da -1 a 1. |

## Regressione esponenziale: valore Y previsto (riga)

Calcola i valori y previsti (metric_Y), in base ai valori x noti (metric_X) utilizzando il metodo dei minimi quadrati per calcolare la riga di adattamento ottimale in base a.

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Cdf-T

Restituisce la percentuale di valori nella distribuzione t di uno studente con n gradi di libertà che presenta un punteggio z inferiore a x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Restituisce la percentuale di valori in una distribuzione normale che presenta un punteggio z inferiore a x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499
```

## Eccesso (riga)

Restituisce l’integer più piccolo, non inferiore a un valore specificato. Ad esempio, se vuoi evitare di riportare i decimali della valuta per le entrate e il prezzo di un prodotto è pari a 569,34 $, utilizza la formula CEILING(*Revenue*) per arrotondare le entrate al dollaro più vicino o 570 $.

```
CEILING(metric)
```

| Argomento | Descrizione |
|---|---|
| *metric* | La metrica da arrotondare. |

## Coseno (riga)

Restituisce il coseno dell’angolo specificato. Se l’angolo è in gradi, moltiplicalo per PI( )/180.

```
COS(metric)
```

| Argomento | Descrizione |
|---|---|
| *metric* | L’angolo in radianti di cui vuoi ottenere il coseno. |

## Radice cubica

Restituisce la radice cubica positiva di un numero. La radice cubica di un numero corrisponde al valore di quel numero elevato alla potenza di 1/3.

```
CBRT(metric)
```

| Argomento | Descrizione |
|---|---|
| *metric* | La metrica per la quale vuoi ottenere la radice cubica. |

## Cumulativo

Restituisce la somma di x per le ultime N righe secondo quanto ordinato dalla dimensione, utilizzando valori hash per i campi basati su stringhe.

Se N &lt;= 0 vengono usate tutte le righe precedenti. Poiché questa funzione è ordinata dalla dimensione, risulta utile solo per le dimensioni con ordine naturale, come data o lunghezza del percorso.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) |
|------+------+--------------+--------------|
| May  | $500 | $500         | $500         |
| June | $200 | $700         | $700         |
| July | $400 | $1100        | $600         |
```

## Media cumulativa

Restituisce la media delle ultime N righe.

Se N &lt;= 0 vengono usate tutte le righe precedenti. Poiché questa funzione è ordinata dalla dimensione, risulta utile solo per le dimensioni con ordine naturale, come data o lunghezza del percorso.

>[!NOTE]
>
>Questa funzione non opera come previsto con metriche di tasso come entrate/visitatore: calcola la media dei tassi, anziché sommare i ricavi rispetto all’ultima N, quindi sommare i visitatori rispetto all’ultima N e infine dividere i due valori ottenuti. Invece, utilizza

```
cumul(revenue)/cumul(visitor)
```

## Uguale

Restituisce elementi che corrispondono esattamente a un valore numerico o stringa.

## Regressione esponenziale: coefficiente di correlazione (tabella)

Restituisce il coefficiente di correlazione, *r*, tra due colonne di metrica ( *metric_A* e *metric_B*) per l’equazione di regressione.

```
CORREL.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Metrica da correlare con *metric_Y*. |
| *metric_Y* | Metrica da correlare con *metric_X*. |

## Regressione esponenziale: intersezione (tabella)

Restituisce l’intersezione, *b*, tra due colonne di metrica ( *metric_X* e *metric_Y*) per

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Regressione esponenziale: pendenza (tabella)

Restituisce la pendenza, *a*, tra due colonne di metrica ( *metric_X* e *metric_Y*) per

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Base (riga)

Restituisce l’integer più grande, non superiore a un valore specificato. Ad esempio, se vuoi evitare di riportare i decimali della valuta per le entrate e il prezzo di un prodotto è pari a 569,34 $, utilizza la formula FLOOR(*Revenue*) per arrotondare le entrate al dollaro più vicino o 569$.

```
FLOOR(metric)
```

| Argomento | Descrizione |
|---|---|
| *metric* | La metrica da arrotondare. |

## Maggiore di

Restituisce elementi il cui conteggio numerico è maggiore del valore immesso.

## Maggiore di o uguale a

Restituisce elementi il cui conteggio numerico è maggiore di o uguale al valore immesso.

## Coseno iperbolico (riga)

Restituisce il coseno iperbolico di un numero.

```
COSH(metric)
```

| Argomento | Descrizione |
|---|---|
| *metric* | L’angolo in radianti di cui vuoi ottenere il coseno iperbolico. |

## Seno iperbolico (riga)

Restituisce il seno iperbolico di un numero.

```
SINH(metric)
```

| Argomento | Descrizione |
|---|---|
| *metric* | L’angolo in radianti di cui vuoi ottenere il seno iperbolico. |

## Tangente iperbolica (riga)

Restituisce la tangente iperbolica di un numero.

```
TANH(metric)
```

| Argomento | Descrizione |
|---|---|
| *metric* | L’angolo in radianti di cui vuoi ottenere la tangente iperbolica. |

## IF (riga)

La funzione IF restituisce un valore se una condizione specificata restituisce TRUE, mentre consente di ottenere un altro valore se tale condizione restituisce FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argomento | Descrizione |
|---|---|
| *logical_test* | Obbligatorio. Qualsiasi valore o espressione che può essere valutato come TRUE o FALSE. |
| *[value_if_true]* | Il valore che vuoi ottenere se l’argomento *logical_test* restituisce TRUE. Se non è incluso, questo argomento sarà pari a 0 per impostazione predefinita. |
| *[value_if_false]* | Il valore che vuoi ottenere se l’argomento *logical_test* restituisce FALSE. Se non è incluso, questo argomento sarà pari a 0 per impostazione predefinita. |

## Minore di

Restituisce elementi il cui conteggio numerico è inferiore al valore immesso.

## Minore o uguale a

Restituisce elementi il cui conteggio numerico è minore o uguale al valore immesso.

## Regressione lineare: coefficiente di correlazione

Y = a X + b. Restituisce il coefficiente di correlazione.

## Regressione lineare: intersezione

Y = a X + b. Restituisce b.

## Regressione lineare: valore Y previsto

Y = a X + b. Restituisce Y.

## Regressione lineare: pendenza

Y = a X + b. Restituisce a.

## Base logaritmo 10 (riga)

Restituisce il logaritmo base 10 di un numero.

```
LOG10(metric)
```

| Argomento | Descrizione |
|---|---|
| *metric* | Numero reale positivo di cui vuoi ottenere il logaritmo base 10. |

## Regressione logaritmo: coefficiente di correlazione (tabella)

Restituisce il coefficiente di correlazione, *r*, tra due colonne di metrica (*metric_X* e *metric_Y*) per l’equazione di regressione [!DNL Y = a ln(X) + b]. Viene calcolato utilizzando l’equazione CORREL.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Metrica da correlare con *metric_Y*. |
| *metric_Y* | Metrica da correlare con *metric_X*. |

## Regressione logaritmo: intersezione (tabella)

Restituisce l’intersezione *b* come regressione dei minimi quadrati tra due colonne di metrica (*metric_X* e *metric_Y*) per l’equazione di regressione [!DNL Y = a ln(X) + b]. Viene calcolata utilizzando l’equazione INTERCEPT.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Regressione logaritmo: valore Y previsto (riga)

Calcola i [!DNL y] valori previsti (metric_Y), in base ai [!DNL x] valori noti (metric_X) utilizzando il metodo dei minimi quadrati per calcolare la riga di adattamento ottimale in base a [!DNL Y = a ln(X) + b]. Viene calcolata utilizzando l’equazione ESTIMATE.

Nell’analisi di regressione, questa funzione calcola i [!DNL y] valori previsti (*metric_Y*), dati i [!DNL x] valori noti (*metric_X*) utilizzando il logaritmo per calcolare la linea più adatta all’equazione di regressione [!DNL Y = a ln(X) + b]. I [!DNL a] valori corrispondono a ciascun valore x e [!DNL b] è un valore costante.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Regressione logaritmo: pendenza (tabella)

Restituisce la pendenza, *a*, tra due colonne di metrica (*metric_X* e *metric_Y*) per l’equazione di regressione [!DNL Y = a ln(X) + b]. Viene calcolata utilizzando l’equazione SLOPE.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argomento | Descrizione |
|---|---|
| *metric_A* | Una metrica da designare come dati dipendenti. |
| *metric_B* | Una metrica da designare come dati indipendenti. |

## Logaritmo naturale

Restituisce il logaritmo naturale di un numero. I logaritmi naturali si basano sulla costante *e* (2,71828182845904). LN è l’inverso della funzione EXP.

```
LN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metric* | Numero reale positivo di cui vuoi ottenere il logaritmo naturale. |

## NOT

Restituisce 1 se il numero è 0 o restituisce 0 se è presente un altro numero.

```
NOT(logical)
```

| Argomento | Descrizione |
|---|---|
| *logical* | Obbligatorio. Un valore o espressione che può essere valutato come TRUE o FALSE. |

Per utilizzare NOT è necessario verificare se le espressioni (&lt;, >, =, &lt;>, ecc.) restituiscono i valori 0 o 1.

## Non uguale

Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore immesso.

## O (riga)

Restituisce TRUE se un qualsiasi argomento è TRUE oppure FALSE se tutti gli argomenti sono FALSE.

>[!NOTE]
>
>0 (zero) significa False, mentre qualsiasi altro valore corrisponde a True.

```
OR(logical_test1,[logical_test2],...)
```

| Argomento | Descrizione |
|---|---|
| *logical_test1* | Obbligatorio. Qualsiasi valore o espressione che può essere valutato come TRUE o FALSE. |
| *logical_test2* | Facoltativo. Condizioni aggiuntive da valutare come TRUE o FALSE. |

## Pi

Restituisce la costante PI, 3,14159265358979, con una precisione di 15 cifre.

```
PI()
```

La funzione [!DNL PI]non ha argomenti.

## Regressione di potenza: coefficiente di correlazione (tabella)

Restituisce il coefficiente di correlazione, *r*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Metrica da correlare con *metric_Y*. |
| *metric_Y* | Metrica da correlare con *metric_X*. |

## Regressione di potenza: intersezione (tabella)

Restituisce l’intersezione, *b*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Regressione di potenza: valore Y previsto (riga)

Calcola i [!DNL y] valori previsti ( [!DNL metric_Y]), in base ai [!DNL x] valori noti ( [!DNL metric_X]) utilizzando il metodo dei minimi quadrati per calcolare la riga di adattamento ottimale per [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Regressione di potenza: pendenza (tabella)

Restituisce la pendenza, *a*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Regressione quadratica: coefficiente di correlazione (tabella)

Restituisce il coefficiente di correlazione, *r*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Metrica da correlare con *metric_Y*. |
| *metric_Y* | Metrica da correlare con *metric_X*. |

## Regressione quadratica: intersezione (tabella)

Restituisce l’intersezione, *b*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Regressione quadratica: valore Y previsto (riga)

Calcola i [!DNL y] valori previsti (metric_Y), in base ai [!DNL x] valori noti (metric_X) utilizzando il metodo dei minimi quadrati per calcolare la riga di adattamento ottimale tramite [!DNL Y=(a*X+b)]****.

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argomento | Descrizione |
|---|---|
| *metric_A* | Una metrica da designare come dati dipendenti. |
| *metric_B* | Una metrica da designare come dati dipendenti. |

## Regressione quadratica: pendenza (tabella)

Restituisce la pendenza, *a*, tra due colonne di metrica (*metric_X* e metric_Y) per [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Regressione reciproca: coefficiente di correlazione (tabella)

Restituisce il coefficiente di correlazione, *r*, tra due colonne di metrica (*metric_X)* e *metric_Y*) per [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Metrica da correlare con *metric_Y*. |
| *metric_Y* | Metrica da correlare con *metric_X*. |

## Regressione reciproca: intersezione (tabella)

Restituisce l’intersezione, *b*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Regressione reciproca: valore Y previsto (riga)

Calcola i [!DNL y] valori previsti (metric_Y), in base ai [!DNL x] valori noti (metric_X) utilizzando il metodo dei minimi quadrati per calcolare la riga di adattamento ottimale tramite [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Regressione reciproca: pendenza (tabella)

Restituisce la pendenza, *a*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati dipendenti. |
| *metric_Y* | Una metrica da designare come dati indipendenti. |

## Seno (riga)

Restituisce il seno dell’angolo specificato. Se l’angolo è in gradi, moltiplicalo per PI( )/180.

```
SIN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metric* | L’angolo in radianti di cui vuoi ottenere il seno. |

## Punteggio T

Alias per punteggio Z, vale a dire la deviazione dalla media divisa per la deviazione standard.

## Test T

Esegue un test t a coda m con un punteggio t di col e n gradi di libertà.

La firma è `t_test( x, n, m )`. Sotto, effettua semplicemente la chiamata `m*cdf_t(-abs(x),n)`. È simile alla funzione di test z che esegue `m*cdf_z(-abs(x))`.

Qui `m` indica il numero di code e `n` corrisponde ai gradi di libertà. Devono essere numeri costanti per l’intero report, ovvero senza subire modifiche per riga.

`X` è la statistica del test t e spesso è una formula (ad es., zscore) basata su una metrica, che sarà valutata su ogni riga.

Il valore restituito è la probabilità di visualizzare la statistica x del test in base ai gradi di libertà e al numero di code.

**Esempi:**

1. Utilizza questo valore per individuare gli outlier:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combinalo con `if` per ignorare tassi non raggiunti molto elevati o bassi e per contare le visite degli altri elementi:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangente

Restituisce la tangente dell’angolo specificato. Se l’angolo è in gradi, moltiplicalo per PI( )/180.

```
TAN (metric)
```

| Argomento | Descrizione |
|---|---|
| *metric* | L’angolo in radianti di cui vuoi ottenere la tangente. |

## Punteggio Z (riga)

Restituisce il punteggio Z, o punteggio normale, in base a una distribuzione normale. Il punteggio Z è il numero di deviazioni standard di un’osservazione dalla media. Un punteggio Z pari a 0 (zero) indica che il punteggio è uguale alla media. Un punteggio Z può essere positivo o negativo, il che significa se è superiore o inferiore alla media, oltre al numero di deviazioni standard.

L’equazione per il punteggio Z è:

![](assets/z_score.png)

dove [!DNL x] è il punteggio non elaborato, [!DNL μ] corrisponde alla media della popolazione e [!DNL σ] indica la deviazione standard della popolazione.

>[!NOTE]
>
>[!DNL μ] (mu) e[!DNL σ] (sigma) vengono calcolati automaticamente dalla metrica.

Punteggio Z (metrica)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argomento </th>
   <th colname="col2" class="entry"> Descrizione </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Restituisce il valore del primo argomento diverso da zero. </p> </td>
  </tr>
 </tbody>
</table>

## Test Z

Effettua un test Z con coda n con punteggio Z di A.

Restituisce la probabilità che la riga corrente possa essere vista casualmente nella colonna.

>[!NOTE]
>
>Presuppone che i valori siano distribuiti normalmente.
