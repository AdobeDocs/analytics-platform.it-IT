---
title: Funzioni avanzate
description: Per accedere a queste funzioni, seleziona Mostra avanzate nel menu a discesa Funzioni.
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '4964'
ht-degree: 89%

---

# Funzioni avanzate

Il [Generatore di metriche calcolate](cm-workflow/cm-build-metrics.md) consente di applicare funzioni statistiche e matematiche. Questo articolo riporta un elenco alfabetico delle funzioni avanzate e delle relative definizioni.

Accedi a queste funzioni selezionando **[!UICONTROL Show all]** sotto l’elenco ![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL Functions]** nel pannello Componenti. Scorri verso il basso per visualizzare l’elenco di **[!UICONTROL Advanced functions]**.

## Funzioni tabella e funzioni riga

Una funzione tabella è una funzione in cui l’output è lo stesso per ogni riga della tabella. Una funzione riga è una funzione in cui l’output è diverso per ogni riga della tabella.

Se applicabile e pertinente, una funzione viene annotata con il tipo di funzione: [!BADGE Tabella]{type="Neutral"} o [!BADGE Riga]{type="Neutral"}

## Che cosa significa il parametro include-zeros?

Il parametro indica se includere gli zeri all’interno del calcolo. Talvolta lo zero *non* ha alcun significato, ma in determinate occasioni può risultare importante.

Ad esempio, se hai una metrica Revenue (Entrate) e ne aggiungi al report una del tipo Page Views (Visualizzazioni pagina), improvvisamente saranno presenti più righe per le entrate che sono pari a zero. Probabilmente non vorrai che questa metrica aggiuntiva influisca su **[MEAN](cm-functions.md#mean)**, **[ROW MINIMUM](cm-functions.md#row-min)**, **[QUARTILE](cm-functions.md#quartile)** e altri calcoli presenti nella colonna dei ricavi. In questo caso, dovrai controllare il parametro `include-zeros`.

In alternativa, puoi avere due metriche di interesse e una con una media o un minimo più elevati, perché alcune righe sono pari a zero.  In tal caso, puoi scegliere di non selezionare il parametro per includere gli zeri


## E {#and}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-and"
>title="E"
>abstract="Congiunzione. Diverso da zero è considerato vero e uguale a zero è considerato falso. L’output è 0 (falso) o 1 (vero)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL AND(logical_test)]**

Congiunzione. Diverso da zero è considerato vero e uguale a zero è considerato falso. L’output è 0 (falso) o 1 (vero).

| Argomento | Descrizione |
|---|---|
| logical_test | Richiede almeno un parametro, ma può accettare un numero qualsiasi di parametri. Qualsiasi valore o espressione che può avere valore TRUE o FALSE. |


## Conteggio distinto approssimativo {#approximate_count_distinct}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-distinct-metric"
>title="Conteggio distinto approssimativo"
>abstract="Restituisce il conteggio distinto approssimativo degli elementi dimensionali per la dimensione selezionata."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL APPROXIMATE COUNT DISTINCT(dimension)]**


Restituisce il conteggio distinto approssimativo degli elementi dimensionali per la dimensione selezionata.


| Argomento | Descrizione |
|---|---|
| dimensione | La dimensione per la quale vuoi ottenere il conteggio distinto approssimativo degli elementi. |

### Esempio

Un caso d’uso comune per questa funzione si verifica quando desideri ottenere un numero approssimativo di clienti.



## Arcocoseno {#arc-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-acos"
>title="Arcocoseno"
>abstract="Restituisce l’arcocoseno di una metrica, detto anche inverso del coseno. L’arcocoseno è l’angolo di cui è numero il coseno. L’angolo restituito è espresso in radianti compresi nell’intervallo tra 0 (zero) e pi. Per convertire il risultato da radianti a gradi, moltiplicalo per 180/PI( )."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ARC COSINE(metric)]**


[!BADGE Riga]{type="Neutral"} Restituisce l&#39;arcocoseno, o inverso del coseno, di una metrica. L’arcocoseno è l’angolo di cui è numero il coseno. L’angolo restituito è espresso in radianti compresi nell’intervallo tra 0 (zero) e pi. Per convertire il risultato da radianti a gradi, moltiplicalo per 180/PI( ).


| Argomento | Descrizione |
|---|---|
| metrica | Il coseno dell’angolo desiderato da -1 a 1. |



## Arcoseno {#arc-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-asin"
>title="Arcoseno"
>abstract="Restituisce l’arcoseno, o seno inverso, di un numero. L’arcoseno è l’angolo di cui è numero il seno. L’angolo restituito è espresso in radianti compresi nell’intervallo tra -pi/2 e pi/2. Per esprimere l’arcoseno in gradi, moltiplica il risultato per 180/PI( )"

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ARC SINE(metric)]**


[!BADGE Riga]{type="Neutral"} Restituisce l&#39;arcoseno, o seno inverso, di un numero. L’arcoseno è l’angolo di cui è numero il seno. L’angolo restituito è espresso in radianti compresi nell’intervallo tra -pi/2 e pi/2. Per esprimere l&#39;arcoseno in gradi, moltiplicate il risultato per 180/PI().


| Argomento | Descrizione |
|---|---|
| metrica | Il seno dell’angolo desiderato da -1 a 1. |



## Arcotangente {#arc-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-atan"
>title="Arcotangente"
>abstract="Restituisce l’arcotangente, o tangente inversa, di un numero. L’arcotangente è l’angolo di cui è numero la tangente. L’angolo restituito è espresso in radianti compresi nell’intervallo tra -pi/2 e pi/2. Per esprimere l’arcotangente in gradi, moltiplica il risultato per 180/PI( )."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ARC TANGENT(metric)]**


[!BADGE Riga]{type="Neutral"} Restituisce l&#39;arcotangente, o tangente inversa, di un numero. L’arcotangente è l’angolo di cui è numero la tangente. L’angolo restituito è espresso in radianti compresi nell’intervallo tra -pi/2 e pi/2. Per esprimere l’arcotangente in gradi, moltiplica il risultato per 180/PI( ).


| Argomento | Descrizione |
|---|---|
| metrica | La tangente dell’angolo desiderato da -1 a 1. |



## Cdf-T {#cdf-t}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-t"
>title="Cdf-T"
>abstract="Restituisce la probabilità che una variabile casuale con distribuzione t di studente con n gradi di libertà abbia un punteggio z inferiore a col."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(metric, number)]**

Restituisce la probabilità che una variabile casuale con distribuzione t di studente con n gradi di libertà abbia un punteggio z inferiore a col.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica per la quale desideri la funzione Distribuzione cumulativa della distribuzione t di studente |
| numero | I gradi di libertà della funzione Distribuzione cumulativa della distribuzione t dello studente |

### Esempio

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z {#cdf-z}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-z"
>title="Cdf-Z"
>abstract="Restituisce la probabilità che una variabile casuale con una distribuzione normale abbia un punteggio z inferiore a col."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(metric, number)]**

Restituisce la probabilità che una variabile casuale con una distribuzione normale abbia un punteggio z inferiore a col.

| Argomento | Descrizione |
|---|---|
| metrica | Metrica per la quale si desidera la funzione di distribuzione cumulativa della distribuzione normale standard |

### Esempi

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## Ceiling {#ceiling}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ceil"
>title="Ceiling"
>abstract="Restituisce l’integer più piccolo, non inferiore a un valore specificato. 70 esempio, se vuoi evitare di riportare i decimali della valuta per le entrate e un prodotto è pari a 569,93 $, utilizza la formula CEILING (ricavi) per arrotondare i ricavi al dollaro più vicino, in questo caso 570 $."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CEILING(metric)]**

[!BADGE Riga]{type="Neutral"} Restituisce il numero intero più piccolo, non inferiore a un valore specificato. 70 esempio, se vuoi evitare di riportare i decimali della valuta per le entrate e un prodotto è pari a 569,93 $, utilizza la formula CEILING (ricavi) per arrotondare i ricavi al dollaro più vicino, in questo caso 570 $.

| Argomento | Descrizione |
|---|---|
| metrica | Metrica da arrotondare |


## Affidabilità {#confidence}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence"
>title="Affidabilità"
>abstract="Calcola il valore di affidabilità valido in ogni momento, utilizzando il metodo WASKR come descritto in [Teoria del limite centrale uniforme nel tempo e sequenze di affidabilità asintotiche](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Calcola il valore di affidabilità valido in ogni momento, utilizzando il metodo WASKR come descritto in [Teoria del limite centrale uniforme nel tempo e sequenze di affidabilità asintotiche](https://arxiv.org/pdf/2103.06476).

Affidabilità è una misura probabilistica della quantità di prove che dimostrano che una specifica variante è uguale alla variante di controllo. Una maggiore affidabilità indica meno prove dell’ipotesi che le varianti di controllo e non di controllo abbiano prestazioni uguali.

| Argomento | Descrizione |
| --- | --- |
| normalizing-container | La base (persone, sessioni o eventi) su cui verrà eseguito un test. |
| success-metric | La metrica o le metriche con cui un utente confronta le varianti. |
| controllo | La variante con cui vengono confrontate tutte le altre varianti dell’esperimento. Immetti il nome dell’elemento della dimensione della variante di controllo. |
| significance-threshold | La soglia in questa funzione è impostata su un valore predefinito di 95%. |


## Affidabilità (inferiore) {#confidence-lower}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence-interval-lower"
>title="Affidabilità (inferiore)"
>abstract="Calcola il valore **inferiore** di affidabilità valido in ogni momento, utilizzando il metodo WASKR come descritto in [Teoria del limite centrale uniforme nel tempo e sequenze di affidabilità asintotiche](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Calcola il valore **inferiore** di affidabilità valido in ogni momento, utilizzando il metodo WASKR come descritto in [Teoria del limite centrale uniforme nel tempo e sequenze di affidabilità asintotiche](https://arxiv.org/pdf/2103.06476).

Affidabilità è una misura probabilistica della quantità di prove che dimostrano che una specifica variante è uguale alla variante di controllo. Una maggiore affidabilità indica meno prove dell’ipotesi che le varianti di controllo e non di controllo abbiano prestazioni uguali.

| Argomento | Descrizione |
| --- | --- |
| normalizing-container | La base (persone, sessioni o eventi) su cui verrà eseguito un test. |
| success-metric | La metrica o le metriche con cui un utente confronta le varianti. |
| controllo | La variante con cui vengono confrontate tutte le altre varianti dell’esperimento. Immetti il nome dell’elemento della dimensione della variante di controllo. |
| significance-threshold | La soglia in questa funzione è impostata su un valore predefinito di 95%. |

## Affidabilità (superiore) {#confidence-upper}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence-interval-upper"
>title="Affidabilità (superiore)"
>abstract="Calcola il valore **superiore** di affidabilità valido in ogni momento, utilizzando il metodo WASKR come descritto in [Teoria del limite centrale uniforme nel tempo e sequenze di affidabilità asintotiche](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Calcola il valore **superiore** di affidabilità valido in ogni momento, utilizzando il metodo WASKR come descritto in [Teoria del limite centrale uniforme nel tempo e sequenze di affidabilità asintotiche](https://arxiv.org/pdf/2103.06476).

Affidabilità è una misura probabilistica della quantità di prove che dimostrano che una specifica variante è uguale alla variante di controllo. Una maggiore affidabilità indica meno prove dell’ipotesi che le varianti di controllo e non di controllo abbiano prestazioni uguali.

| Argomento | Descrizione |
| --- | --- |
| normalizing-container | La base (persone, sessioni o eventi) su cui verrà eseguito un test. |
| success-metric | La metrica o le metriche con cui un utente confronta le varianti. |
| controllo | La variante con cui vengono confrontate tutte le altre varianti dell’esperimento. Immetti il nome dell’elemento della dimensione della variante di controllo. |
| significance-threshold | La soglia in questa funzione è impostata su un valore predefinito di 95%. |


## Coseno {#cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cos"
>title="Coseno"
>abstract="Restituisce il coseno dell’angolo specificato. Se l’angolo è in gradi, moltiplicalo per PI( )/180."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL COSINE(metric)]**

[!BADGE Riga]{type="Neutral"} Restituisce il coseno dell&#39;angolo specificato. Se l’angolo è in gradi, moltiplicalo per PI( )/180.

| Argomento | Descrizione |
|---|---|
| metrica | L’angolo in radianti di cui vuoi ottenere il coseno. |


## Radice cubica {#cube-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cube-root"
>title="Radice cubica"
>abstract="Restituisce la radice cubica positiva di un numero. La radice cubica di un numero corrisponde al valore di quel numero elevato alla potenza di 1/3."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CUBE ROOT(metric)]**


Restituisce la radice cubica positiva di un numero. La radice cubica di un numero corrisponde al valore di quel numero elevato alla potenza di 1/3.


| Argomento | Descrizione |
|---|---|
| metrica | Metrica per la quale desideri calcolare la radice quadrata. |



## Cumulativa {#cumulative}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul"
>title="Cumulativa"
>abstract="Restituisce la somma degli ultimi n elementi della colonna x. Se n > 0, somma gli ultimi n elementi o x. Se n &lt; 0, somma gli elementi precedenti."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE(number, metric)]**

Restituisce la somma degli ultimi n elementi della colonna x. Se n > 0, somma gli ultimi n elementi o x. Se n &lt; 0, somma gli elementi precedenti.

| Argomento | Descrizione |
| --- | --- |
| numero | L’ultimo numero N di righe per cui restituire la somma. Se N &lt;= 0 usa tutte le righe precedenti. |
| metrica | La metrica di cui desideri la Somma cumulativa. |

### Esempi

| Data | Ricavi | CUMULATIVE(0, Revenue) | CUMULATIVE(2, Revenue) |
|------|------:|--------------:|--------------:|
| Maggio | $ 500 | $ 500 | $ 500 |
| Giugno | $ 200 | $ 700 | $ 700 |
| Luglio | $ 400 | $ 1100 | $ 600 |


## Media cumulativa {#cumulative-average}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul-avg"
>title="Media cumulativa"
>abstract="Restituisce la media degli ultimi n elementi della colonna x. Se n > 0, somma gli ultimi n elementi o x. Se n &lt; 0, somma gli elementi precedenti."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE AVERAGE(number, metric)]**

Restituisce la media degli ultimi n elementi della colonna x. Se n > 0, somma gli ultimi n elementi o x. Se n &lt; 0, somma gli elementi precedenti.

| Argomento | Descrizione |
| --- | --- |
| numero | L’ultimo numero N di righe per cui restituire la media. Se N &lt;= 0 usa tutte le righe precedenti. |
| metrica | La metrica di cui desideri la Media cumulativa. |

>[!NOTE]
>
>Questa funzione non funziona con metriche di percentuale come ricavi per persona. La funzione calcola la media delle percentuali anziché sommare le entrate rispetto all’ultima N, sommare le persone rispetto all’ultima N e infine dividerle. <br/>Utilizza invece [**[!UICONTROL CUMULATIVE(revenue)]**](#cumulative) ![Dividi](/help/assets/icons/Divide.svg) [**[!UICONTROL CUMULATIVE(person)]**](#cumulative).
>


## Uguale {#equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-eq"
>title="Uguale"
>abstract="Uguale. L’output è 0 (falso) o 1 (vero)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL EQUAL()]**

Uguale. L’output è 0 (falso) o 1 (vero).


| Argomento | Descrizione |
|---|---|
| metric_X | La metrica da utilizzare per il confronto. |
| metric_Y | La metrica da utilizzare per il confronto. |

### Esempio

`Metric 1 = Metric 2`


## Regressione esponenziale: coefficiente di correlazione {#exponential-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-exp"
>title="Regressione esponenziale: coefficiente di correlazione"
>abstract="Regressione esponenziale: Y = a exp(X) + b. Restituisce il coefficiente di correlazione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabella]{type="Neutral"} Regressione esponenziale: Y = a exp(X) + b. Restituisce il coefficiente di correlazione.


| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da correlare con metric_Y |
| metric_Y | Metrica da correlare con metric_X |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |

## Regressione esponenziale: Y previsto {#exponential-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-exp"
>title="Regressione esponenziale: Y previsto"
>abstract="Regressione esponenziale: Y = a exp(X) + b. Restituisce Y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Riga]{type="Neutral"} Regressione esponenziale: Y = a exp(X) + b. Restituisce Y.


| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati indipendenti. |
| metric_Y | Una metrica da designare come dati dipendenti. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |


## Regressione esponenziale: intercetta {#exponential-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-exp"
>title="Regressione esponenziale: intercetta"
>abstract="Regressione esponenziale: Y = a exp(X) + b. Restituisce b."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabella]{type="Neutral"} Regressione esponenziale: Y = a exp(X) + b. Restituisce b.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |


## Regressione esponenziale: pendenza {#exponential-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-exp"
>title="Regressione esponenziale: pendenza"
>abstract="Regressione esponenziale: Y = a exp(X) + b. Restituisce a."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabella]{type="Neutral"} Regressione esponenziale: Y = a exp(X) + b. Restituisce a.


| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |


## Floor {#floor}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-floor"
>title="Floor"
>abstract="Restituisce l’integer più grande, non superiore a un valore specificato. Ad esempio, se vuoi evitare di riportare i decimali della valuta per le entrate e un prodotto è pari a 569,34 $, utilizza la formula FLOOR (ricavi) per arrotondare i ricavi al dollaro più vicino, in questo caso 569 $."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR(metric_X, metric_Y, include_zeros)]**

[!BADGE Riga]{type="Neutral"} Restituisce l&#39;intero più grande non maggiore di un valore specificato. Ad esempio, se vuoi evitare di riportare i decimali della valuta per le entrate e un prodotto è pari a 569,34 $, utilizza la formula FLOOR (ricavi) per arrotondare i ricavi al dollaro più vicino, in questo caso 569 $.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica da arrotondare. |


## Maggiore di {#greather-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-gt"
>title="Maggiore di"
>abstract="L’output è 0 (falso) o 1 (vero)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN()]**

L’output è 0 (falso) o 1 (vero).

| Argomento | Descrizione |
|---|---|
| metric_X | La metrica di base da utilizzare per il confronto. |
| metric_Y | La metrica da utilizzare per il confronto. |

### Esempio

`Metric 1 > Metric 2`


## Maggiore di o uguale a {#greater-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ge"
>title="Maggiore di o uguale a"
>abstract="Maggiore di o uguale a. L’output è 0 (falso) o 1 (vero)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN OR EQUAL()]**

Maggiore di o uguale a. L’output è 0 (falso) o 1 (vero).

| Argomento | Descrizione |
|---|---|
| metric_X | La metrica di base da utilizzare per il confronto. |
| metric_Y | La metrica da utilizzare per il confronto. |

### Esempio

`Metric 1 >= Metric 2`



## Coseno iperbolico {#hyperbolic-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cosh"
>title="Coseno iperbolico"
>abstract="Restituisce il coseno iperbolico di un numero."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC COSINE(metric)]**


[!BADGE Riga]{type="Neutral"} Restituisce il coseno iperbolico di un numero.


| Argomento | Descrizione |
|---|---|
| metrica | L’angolo in radianti di cui vuoi ottenere il coseno iperbolico |



## Seno iperbolico {#hyperbolic-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sinh"
>title="Seno iperbolico"
>abstract="Restituisce il seno iperbolico di un numero."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC SINE(metric)]**

[!BADGE Riga]{type="Neutral"} Restituisce il seno iperbolico di un numero.

| Argomento | Descrizione |
|---|---|
| metrica | L’angolo in radianti di cui vuoi ottenere il seno iperbolico |


## Tangente iperbolica {#hyperbolic-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tanh"
>title="Tangente iperbolica"
>abstract="Restituisce la tangente iperbolica di un numero."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC TANGENT(metric)]**

[!BADGE Riga]{type="Neutral"} Restituisce la tangente iperbolica di un numero.

| Argomento | Descrizione |
|---|---|
| metrica | L’angolo in radianti di cui vuoi ottenere la tangente iperbolica |


## Se {#if}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-if"
>title="Se"
>abstract="Se il valore del parametro di condizione è diverso da zero (vero), il risultato è il valore del parametro value_if_true. In caso contrario, è il valore del parametro value_if_false."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL IF(logical_test, value_if_true, value_if_false)]**


[!BADGE Riga]{type="Neutral"} Se il valore del parametro di condizione è diverso da zero (true), il risultato sarà il valore del parametro value_if_true. In caso contrario, è il valore del parametro value_if_false.


| Argomento | Descrizione |
|---|---|
| logical_test | Obbligatorio. Qualsiasi valore o espressione che può avere valore TRUE o FALSE. |
| value_if_true | Valore che vuoi ottenere se l’argomento logical_test restituisce TRUE. (Se non è incluso, questo argomento sarà pari a 0 per impostazione predefinita.) |
| value_if_false | Valore che vuoi ottenere se l’argomento logical_test restituisce FALSE. (Se non è incluso, questo argomento sarà pari a 0 per impostazione predefinita.) |


## Minore di {#less-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-lt"
>title="Minore di"
>abstract="L’output è 0 (falso) o 1 (vero)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN()]**

L’output è 0 (falso) o 1 (vero).

| Argomento | Descrizione |
|---|---|
| metric_X | La metrica da utilizzare per il confronto. |
| metric_Y | La metrica da utilizzare per il confronto. |

### Esempio

`Metric 1 < Metric 2`


## Minore di o uguale a {#less-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-le"
>title="Minore di o uguale a"
>abstract="Minore di o uguale a. L’output è 0 (falso) o 1 (vero)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN OR EQUAL()]**

Minore di o uguale a. L’output è 0 (falso) o 1 (vero).

| Argomento | Descrizione |
|---|---|
| metric_X | La metrica da utilizzare per il confronto. |
| metric_Y | La metrica da utilizzare per il confronto. |

### Esempio

`Metric 1 <= Metric 2`



## Lift {#lift}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-lift"
>title="Lift"
>abstract="L’incremento del rapporto rispetto al valore di controllo."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LIFT(normalizing-container, success-metric, control)]**

L’incremento del rapporto rispetto al valore di controllo.

| Argomento | Descrizione |
| --- | --- |
| normalizing-container | La base (persone, sessioni o eventi) su cui verrà eseguito un test. |
| success-metric | La metrica o le metriche con cui un utente confronta le varianti. |
| controllo | La variante con cui vengono confrontate tutte le altre varianti dell’esperimento. Immetti il nome dell’elemento della dimensione della variante di controllo. |



## Regressione lineare: coefficiente di correlazione {#linear-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-linear"
>title="Regressione lineare: coefficiente di correlazione"
>abstract="Regressione lineare: Y = a X + b.  Restituisce il coefficiente di correlazione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabella]{type="Neutral"} Regressione lineare: Y = a X + b. Restituisce il coefficiente di correlazione.


| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da correlare con metric_Y |
| metric_Y | Metrica da correlare con metric_X |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |



## Regressione lineare: intercetta {#linear-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-linear"
>title="Regressione lineare: intercetta"
>abstract="Regressione lineare: Y = a X + b. Restituisce b."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabella]{type="Neutral"} Regressione lineare: Y = a X + b. Restituisce b.


| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |



## Regressione lineare: Y previsto {#linear-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-linear"
>title="Regressione lineare: Y previsto"
>abstract="Regressione lineare: Y = a X + b. Restituisce Y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Riga]{type="Neutral"} Regressione lineare: Y = a X + b. Restituisce Y.


| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |



## Regressione lineare: pendenza {#linear-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-linear"
>title="Regressione lineare: pendenza"
>abstract="Regressione lineare: Y = a X + b. Restituisce a."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Regressione lineare: Y = a X + b. Restituisce a.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |


## Log in base 10 {#log-base-ten}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log10"
>title="Log in base 10"
>abstract="Restituisce il logaritmo base 10 di un numero."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG BASE 10(metric)]**


[!BADGE Riga]{type="Neutral"} Restituisce il logaritmo base 10 di un numero.


| Argomento | Descrizione |
|---|---|
| metrica | Numero reale positivo di cui vuoi ottenere il logaritmo base 10 |


## Regressione logaritmica: coefficiente di correlazione {#log-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-log"
>title="Regressione logaritmica: coefficiente di correlazione"
>abstract="Regressione logaritmica: Y = a In(X) + b. Restituisce il coefficiente di correlazione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Regressione del registro: Y = a ln(X) + b. Restituisce il coefficiente di correlazione.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da correlare con metric_Y |
| metric_Y | Metrica da correlare con metric_X |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |


## Regressione logaritmica: intercetta {#log-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-log"
>title="Regressione logaritmica: intercetta"
>abstract="Regressione logaritmica: Y = a ln(X) + b. Restituisce b."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Regressione del registro: Y = a ln(X) + b. Restituisce b.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |



## Regressione logaritmica: Y previsto {#log-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-log"
>title="Regressione logaritmica: Y previsto"
>abstract="Regressione logaritmica: Y = a ln(X) + b. Restituisce Y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Riga]{type="Neutral"} Regressione del registro: Y = a ln(X) + b. Restituisce Y.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |



## Regressione logaritmica: pendenza {#log-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-log"
>title="Regressione logaritmica: pendenza"
>abstract="Regressione logaritmo: Y = a ln(X) + b. Restituisce a."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Regressione del registro: Y = a ln(X) + b. Restituisce a.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |



## Logaritmo naturale {#natural-log}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log"
>title="Logaritmo naturale"
>abstract="Restituisce il logaritmo naturale di un numero. I logaritmi naturali sono basati sulla costante e (2.71828182845904). LN è l’inverso della funzione EXP."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL NATURAL LOG(metric)]**

Restituisce il logaritmo naturale di un numero. I logaritmi naturali sono basati sulla costante e (2.71828182845904). LN è l’inverso della funzione EXP.

| Argomento | Descrizione |
|---|---|
| metrica | Numero reale positivo di cui vuoi ottenere il logaritmo naturale |



## Non {#not}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-not"
>title="Non"
>abstract="Negazione come booleano. L’output è 0 (falso) o 1 (vero)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL NOT(logical)]**

Negazione come booleano. L’output è 0 (falso) o 1 (vero).

| Argomento | Descrizione |
|---|---|
| logical | Obbligatorio. Valore o espressione che possono essere valutati come TRUE o FALSE. |



## Non uguale {#not-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ne"
>title="Non uguale"
>abstract="Non uguale. L’output è 0 (falso) o 1 (vero)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL NOT EQUAL()]**


Non uguale. L’output è 0 (falso) o 1 (vero).


| Argomento | Descrizione |
|---|---|
| metric_X | La metrica da utilizzare per il confronto. |
| metric_Y | La metrica da utilizzare per il confronto. |

### Esempio

`Metric 1 != Metric 2`


## Oppure {#or}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-or"
>title="Oppure"
>abstract="Disgiunzione. Diverso da zero è considerato vero e uguale a zero è considerato falso. L’output è 0 (falso) o 1 (vero)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL OR(logical_test)]**


Disgiunzione [!BADGE Riga]{type="Neutral"}. Diverso da zero è considerato vero e uguale a zero è considerato falso. L’output è 0 (falso) o 1 (vero).


| Argomento | Descrizione |
|---|---|
| logical_test | Richiede almeno un parametro, ma può accettare un numero qualsiasi di parametri. Qualsiasi valore o espressione che può avere valore TRUE o FALSE. |


>[!NOTE]
>
>0 (zero) significa False, mentre qualsiasi altro valore corrisponde a True.


## Pi {#pi}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pi"
>title="Pi"
>abstract="Restituisce Pi: 3,14159..."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

Restituisce Pi: 3,14159...


## Regressione di potenza: coefficiente di correlazione {#power-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-power"
>title="Regressione di potenza: coefficiente di correlazione"
>abstract="Regressione di potenza: Y = b X ^ a. Restituisce il coefficiente di correlazione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Regressione di potenza: Y = b X ^ a. Restituisce il coefficiente di correlazione.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da correlare con metric_Y |
| metric_Y | Metrica da correlare con metric_X |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |



## Regressione di potenza: intercetta {#power-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-power"
>title="Regressione di potenza: intercetta"
>abstract="Regressione di potenza: Y = b X ^ a. Restituisce b."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabella]{type="Neutral"} Regressione di potenza: Y = b X ^ a. Restituisce b.


| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |


## Regressione di potenza: Y previsto {#power-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-power"
>title="Regressione di potenza: Y previsto"
>abstract="Regressione di potenza: Y = b X ^ a. Restituisce Y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Riga]{type="Neutral"} Regressione di potenza: Y = b X ^ a. Restituisce Y.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |



## Regressione di potenza: pendenza {#power-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-power"
>title="Regressione di potenza: pendenza"
>abstract="Regressione di potenza: Y = b X ^ a. Restituisce a."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Regressione di potenza: Y = b X ^ a. Restituisce a.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |



## Regressione quadratica: coefficiente di correlazione {#quadratic-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-quadratic"
>title="Regressione quadratica: coefficiente di correlazione"
>abstract="Regressione quadratica: Y = (a + bX) ^ 2, Restituisce il coefficiente di correlazione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Regressione quadratica: Y = (a + bX) ^ 2, Restituisce il coefficiente di correlazione.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da correlare con metric_Y |
| metric_Y | Metrica da correlare con metric_X |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |

## Regressione quadratica: intercetta {#quadratic-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-quadratic"
>title="Regressione quadratica: intercetta"
>abstract="Regressione quadratica: Y = (a + bX) ^ 2, Restituisce a."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Regressione quadratica: Y = (a + bX) ^ 2, Restituisce a.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |


## Regressione quadratica: Y previsto {#quadratic-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-quadratic"
>title="Regressione quadratica: Y previsto"
>abstract="Regressione quadratica: Y = (a + bX) ^ 2, Restituisce Y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Riga]{type="Neutral"} Regressione quadratica: Y = (a + bX) ^ 2, Restituisce Y.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |


## Regressione quadratica: pendenza {#quadratic-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-quadratic"
>title="Regressione quadratica: pendenza"
>abstract="Regressione quadratica: Y = (a + bX) ^ 2, Restituisce b."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Regressione quadratica: Y = (a + bX) ^ 2, Restituisce b.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |



## Regressione reciproca: coefficiente di correlazione {#reciprocal-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-reciprocal"
>title="Regressione reciproca: coefficiente di correlazione"
>abstract="Regressione reciproca: Y = a + b X ^ -1. Restituisce il coefficiente di correlazione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Regressione reciproca: Y = a + b X ^ -1. Restituisce il coefficiente di correlazione.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da correlare con metric_Y |
| metric_Y | Metrica da correlare con metric_X |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |


## Regressione reciproca: intercetta {#reciprocal-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-reciprocal"
>title="Regressione reciproca: intercetta"
>abstract="Regressione reciproca: Y = a + b X ^ -1. Restituisce a."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Regressione reciproca: Y = a + b X ^ -1. Restituisce a.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |


## Regressione reciproca: Y previsto {#reciprocal-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-reciprocal"
>title="Regressione reciproca: Y previsto"
>abstract="Regressione reciproca: Y = a + b X ^ -1. Restituisce Y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Riga]{type="Neutral"} Regressione reciproca: Y = a + b X ^ -1. Restituisce Y.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |


## Regressione reciproca: pendenza {#reciprocal-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-reciprocal"
>title="Regressione reciproca: pendenza"
>abstract="Regressione reciproca: Y = a + b X ^ -1. Restituisce b."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Regressione reciproca: Y = a + b X ^ -1. Restituisce b.

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da designare come dati dipendenti |
| metric_Y | Metrica da designare come dati indipendenti |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |



## Varianza di esempio

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-variance-estimate"
>title="Varianza di esempio"
>abstract="Calcola una stima della varianza di esempio utilizzando la formula (somma(metrica^2) / (N - 1)) - (somma(metrica))^2/(N*(N-1)). dove N è il numero del contenitore di normalizzazione. <br/>Questa viene utilizzata nell’ambito dei calcoli di attendibilità *validi in ogni momento*. In genere, questa funzione non è utile da sola, ma può essere utilizzata per verificare i calcoli o per eseguire i calcoli di affidabilità *manualmente*."

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL SAMPLE VARIANCE(normalizing-container, success-metric)]**

Calcola una stima della varianza del campione.

| Argomento | Descrizione |
| --- | --- |
| normalizing-container | La base (persone, sessioni o eventi) su cui verrà eseguito un test. |
| success-metric | La metrica o le metriche con cui un utente confronta le varianti. |

<!-- markdownlint-enable MD034 -->



## Seno {#sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sin"
>title="Seno"
>abstract="Restituisce il seno dell’angolo specificato. Se l’angolo è in gradi, moltiplicalo per PI( )/180."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL SINE(metric)]**


[!BADGE Riga]{type="Neutral"} Restituisce il seno dell&#39;angolo specificato. Se l’angolo è in gradi, moltiplicalo per PI( )/180.


| Argomento | Descrizione |
|---|---|
| metrica | L’angolo in radianti di cui vuoi ottenere il seno |




## Punteggio T {#t-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-score"
>title="Punteggio T"
>abstract="La deviazione dalla [MEDIA](cm-functions.md#mean), divisa per la deviazione standard. Alias per [punteggio Z](#z-score)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE(metric, include_zeros)]**

La deviazione dalla [MEDIA](cm-functions.md#mean), divisa per la deviazione standard. Alias per [punteggio Z](#z-score).

| Argomento | Descrizione |
|---|---|
| metrica | Metrica per la quale desideri il punteggio T |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |


## Test T {#t-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-test"
>title="Test T"
>abstract="Esegue un test t con coda m con un punteggio t di x e n gradi di libertà."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL T-TEST(metric, degrees, tails)]**

Esegue un test t con coda m con un punteggio t di x e n gradi di libertà.

| Argomento | Descrizione |
|---|---|
| metrica | Metrica sulla quale desideri eseguire un test T |
| gradi | Gradi di libertà |
| code | Lunghezza della coda da utilizzare per eseguire il test T |

### Dettagli

La firma è T-TEST (metrica, gradi, code). Sotto, effettua semplicemente la chiamata a ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)**. Questa funzione è simile alla funzione **[TEST Z](#z-test)**, che esegue ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)**.

- ***m*** è il numero di code.
- ***n*** è il grado di libertà e deve essere un numero costante per l’intero rapporto, ovvero non deve cambiare riga per riga.
- ***x*** è la statistica del test T e spesso è una formula (ad esempio **[Z-SCORE](#z-score)**) basata su una metrica che sarà valutata su ogni riga.

Il valore restituito è la probabilità di visualizzare la statistica x del test in base ai gradi di libertà e al numero di code.

### Esempi

1. Utilizza questa funzione per individuare le anomalie:

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. Combinala con **[IF](#if)** per ignorare percentuali non recapitate molto elevate o basse e per contare le sessioni su tutto il resto:

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```



## Tangente {#tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tan"
>title="Tangente"
>abstract="Restituisce la tangente dell’angolo specificato. Se l’angolo è in gradi, moltiplicalo per PI( )/180."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENT(metric)]**

Restituisce la tangente dell’angolo specificato. Se l’angolo è in gradi, moltiplicalo per PI( )/180.

| Argomento | Descrizione |
|---|---|
| metrica | Angolo in radianti di cui vuoi ottenere la tangente |



## Punteggio Z {#z-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-score"
>title="Punteggio Z"
>abstract="La deviazione dalla media divisa per la deviazione standard."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL Z-SCORE(metric, include_zeros)]**

[!BADGE Riga]{type="Neutral"} la deviazione dalla media divisa per la deviazione standard.

| Argomento | Descrizione |
|---|---|
| metrica | Metrica per la quale desideri il punteggio Z |
| include_zeros | Specifica se includere o meno valori zero nei calcoli |

Un punteggio Z pari a 0 (zero) indica che il punteggio è uguale alla media. Un punteggio Z può essere positivo o negativo, il che significa se è superiore o inferiore alla media, oltre al numero di deviazioni standard.

L’equazione per il punteggio Z è:

![](assets/z_score.png)

dove ***[!DNL x]*** è il punteggio non elaborato, ***[!DNL μ]*** corrisponde alla media della popolazione e ***[!DNL σ]*** indica la deviazione standard della popolazione.

>[!NOTE]
>
>***[!DNL μ]*** (mu) e ***[!DNL σ]*** (sigma) vengono calcolati automaticamente dalla metrica.



## Test Z {#z-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-test"
>title="Test Z"
>abstract="Effettua un test z con coda n con punteggio z di x."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST(metric_tails)]**

Effettua un test z con coda n con punteggio z di x.

| Argomento | Descrizione |
|---|---|
| metrica | Metrica su cui desideri eseguire un test Z |
| code | Lunghezza della coda da utilizzare per eseguire il test Z |

>[!NOTE]
>
>Presuppone che i valori siano distribuiti normalmente.




<!--



## AND

Returns the value of its argument. Use NOT to make sure that a value is not equal to one particular value.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
AND(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Approximate Count Distinct (dimension)

Returns the approximated distinct count of dimension items for the selected dimension. The function uses the HyperLogLog (HLL) method of approximating distinct counts.&nbsp; It is configured to guarantee the value is within 5% of the actual value 95% of the time.

```
Approximate Count Distinct (dimension)
```

|  Argument  |  |
|---|---|
|  *dimension* | The dimension for which you want the approximate distinct item count.  |

### Example Use Case

Approximate Count Distinct (customer ID eVar) is a common use case for this function.

Definition for a new 'Approximate Customers' calculated metric:

![Approximate county distinct new dimension definition showing Customer ID (eVar1)](assets/approx-count-distinct.png)

This is how the "Approximate Customers" metric could be used in reporting:

![Freeform Table showing Unique Visitors and Approximate Customers ](assets/approx-customers.png)

### Comparing Count Functions

Approximate Count Distinct() is an improvement over Count() and RowCount() functions because the metric created can be used in any dimensional report to render an approximated count of items for a separate dimension. For example, a count of customer IDs used in a Mobile Device Type report.

This function will be marginally less accurate than Count() and RowCount() because it uses the HLL method, whereas Count() and RowCount() are exact counts.

## Arc Cosine (Row)

Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).

```
ACOS(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Sine (Row)

Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).

```
ASIN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Tangent (Row)

Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).

```
ATAN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Exponential Regression: Predicted Y (Row)

Calculates the predicted y-values (metric_Y), given the known x-values (metric_X) using the "least squares" method for calculating the line of best fit based on .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Cdf-T

Returns the percentage of values in a student's t-distribution with n degrees of freedom that have a z-score less than x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returns the percentage of values in a normal distribution that have a z-score less than x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499

```

## Exponential Regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Exponential Regression: Slope (Table)

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Floor (Row)

Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric you want to round.  |

## Greater Than

Returns items whose numeric count is greater than the value entered.

## Greater Than or Equal

Returns items whose numeric count is greater than or equal to the value entered.

## Hyperbolic Cosine (Row)

Returns the hyperbolic cosine of a number.

```
COSH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic cosine.  |

## Hyperbolic Sine (Row)

Returns the hyperbolic sine of a number.

```
SINH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic sine.  |

## Hyperbolic Tangent (Row)

Returns the hyperbolic tangent of a number.

```
TANH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic tanget.  |

## IF (Row)

The IF function returns one value if a condition you specify evaluates to TRUE, and another value if that condition evaluates to FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

|  Argument  | Description  |
|---|---|
|  *logical_test* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.)  |
|  *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.)  |

## Less Than

Returns items whose numeric count is less than the value entered.

## Less Than or Equal

Returns items whose numeric count is less than or equal to the value entered.

## Lift

Returns the Lift a particular variant had in conversions over a control variant. It is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage. 

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Description |
| --- | --- |
| Normalizing Container | The basis (People, Sessions, or Events) on which a test will be run. |
| Success Metric | The metric or metrics that a user is comparing variants with. |
| Control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |

{style="table-layout:auto"}

## Linear regression_ Correlation Coefficient

Y = a X + b. Returns the correlation coefficient

## Linear regression_ Intercept

Y = a X + b. Returns b.

## Linear regression_ Predicted Y

Y = a X + b. Returns Y.

## Linear regression_ Slope

Y = a X + b. Returns a.

## Log Base 10 (Row)

Returns the base-10 logarithm of a number.

```
LOG10(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the base-10 logarithm.  |

## Log regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the CORREL equation.

```
CORREL.LOG(metric_X,metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Log regression: Intercept (Table)

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the INTERCEPT equation.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log Regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. It is calculated using the ESTIMATE equation.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. The [!DNL a] values correspond to each x value, and [!DNL b] is a constant value.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the SLOPE equation.

```
SLOPE.LOG(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the independent data.  |

## Natural Log

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the natural logarithm.  |

## NOT

Returns 1 if the number is 0 or returns 0 if another number.

```
NOT(logical)
```

|  Argument  | Description  |
|---|---|
|  *logical* | Required. A value or expression that can be evaluated to TRUE or FALSE.  |

Using NOT requires knowing if the expressions (<, >, =, <> , etc.) return 0 or 1 values.

## Not equal

Returns all items that do not contain the exact match of the value entered.

## Or (Row)

Returns TRUE if any argument is TRUE, or returns FALSE if all arguments are FALSE.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
OR(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Pi

Returns the constant PI, 3.14159265358979, accurate to 15 digits.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Power regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Quadratic regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Reciprocal regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Sine (Row)

Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
SIN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the sine.  |

## T-Score

Alias for Z-Score, namely the deviation from the mean divided by the standard deviation

## T-Test

Performs an m-tailed t-test with t-score of col and n degrees of freedom.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent

Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
TAN (metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the tangent.  |

## Z-Score (Row)

Returns the Z-score, or normal score, based upon a normal distribution. The Z-score is the number of standard deviations an observation is from the mean. A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.

Z-score(metric)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Returns the value of its first non-zero argument. </p> </td>
  </tr>
 </tbody>
</table>

## Z-Test

Performs an n-tailed Z-test with Z-score of A.

Returns the probability that the current row could be seen by chance in the column.

>[!NOTE]
>
>Assumes that the values are normally distributed.

-->