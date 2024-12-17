---
title: Funzioni avanzate
description: Per accedere a queste funzioni, seleziona Show Advanced (Mostra avanzate) dall’elenco a discesa Functions (Funzioni).
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: 1804f3dc4126007c1ff553f844d691c80623bb90
workflow-type: tm+mt
source-wordcount: '4163'
ht-degree: 28%

---

# Funzioni avanzate

Il [Generatore di metriche calcolate](cm-workflow/cm-build-metrics.md) consente di applicare funzioni statistiche e matematiche. Questo articolo documenta l’elenco alfabetico delle funzioni avanzate e delle relative definizioni.

Accedi a queste funzioni selezionando **[!UICONTROL Show all]** sotto l&#39;elenco ![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL Functions]** nel pannello Componenti. Scorrere verso il basso per visualizzare l&#39;elenco di **[!UICONTROL Advanced functions]**.

## Funzioni tabella e funzioni riga

Una funzione tabella è una funzione in cui l’output è lo stesso per ogni riga della tabella. Una funzione riga è una funzione in cui l’output è diverso per ogni riga della tabella.

Se applicabile e pertinente, una funzione viene annotata con il tipo di funzione: [!BADGE Tabella]{type="Neutral"}[!BADGE Riga]{type="Neutral"}

## Che cosa significa il parametro include-zeros?

Il parametro indica se includere gli zeri all’interno del calcolo. Talvolta lo zero *non* ha alcun significato, ma in determinate occasioni può risultare importante.

Ad esempio, se hai una metrica Revenue (Entrate) e ne aggiungi al report una del tipo Page Views (Visualizzazioni pagina), improvvisamente saranno presenti più righe per le entrate che sono pari a zero. Probabilmente non vorrai che questa metrica aggiuntiva influisca su **[MEAN](cm-functions.md#mean)**, **[ROW MINIMUM](cm-functions.md#row-min)**, **[QUARTILE](cm-functions.md#quartile)** e altri calcoli presenti nella colonna dei ricavi. In questo caso, dovrai controllare il parametro `include-zeros`.

In alternativa, puoi avere due metriche di interesse e una con una media o un minimo più elevati, perché alcune righe sono pari a zero.  In tal caso, puoi scegliere di non selezionare il parametro per includervi degli zeri.


## E {#and}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_and"
>title="E"
>abstract="Congiunzione. Diverso da zero è considerato vero e uguale a zero è considerato falso. L’output è 0 (false) o 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL AND(logical_test)]**

Congiunzione. Diverso da zero è considerato vero e uguale a zero è considerato falso. L’output è 0 (false) o 1 (true).

| Argomento | Descrizione |
|---|---|
| logical_test | Richiede almeno un parametro, ma può richiedere un numero qualsiasi di parametri. Qualsiasi valore o espressione che può essere valutato come TRUE o FALSE |


## Approximate Count Distinct {#approximate_count_distinct}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_approximate_count_distinct"
>title="Approximate Count Distinct"
>abstract="Restituisce il conteggio distinto approssimativo degli elementi dimensione per la dimensione selezionata."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL APPROXIMATE COUNT DISTINCT(dimension)]**


Restituisce il conteggio distinto approssimativo degli elementi dimensione per la dimensione selezionata.


| Argomento | Descrizione |
|---|---|
| dimensione | Dimensione per la quale si desidera calcolare il conteggio degli elementi distinti approssimato |

### Esempio

Un caso d’uso comune per questa funzione si verifica quando si desidera ottenere un numero approssimativo di clienti.



## Arco coseno {#arc-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_arc_cosine"
>title="Arco coseno"
>abstract="Restituisce l’arcocoseno di una metrica, detto anche inverso del coseno. L’arcocoseno è l’angolo di cui è numero il coseno. L’angolo restituito è espresso in radianti compresi nell’intervallo tra 0 (zero) e pi. Per convertire il risultato da radianti a gradi, moltiplicalo per 180/PI()."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ARC COSINE(metric)]**


[!BADGE Riga]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metrica | Il coseno dell’angolo desiderato da -1 a 1 |



## Arcoseno {#arc-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_arc_sine"
>title="Arcoseno"
>abstract="Restituisce l’arcoseno, o seno inverso, di un numero. L&#39;arcoseno è l&#39;angolo il cui seno è un numero. L’angolo restituito è espresso in radianti compresi nell’intervallo tra -pi/2 e pi/2. Per esprimere l&#39;arcoseno in gradi, moltiplicate il risultato per 180/PI()"

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ARC SINE(metric)]**


[!BADGE Riga]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metrica | Seno dell&#39;angolo desiderato da -1 a 1 |



## Arco tangente {#arc-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_arc_tangent"
>title="Arco tangente"
>abstract="Restituisce l’arcotangente, o tangente inversa, di un numero. L&#39;arcotangente è l&#39;angolo la cui tangente è un numero. L’angolo restituito è espresso in radianti compresi nell’intervallo tra -pi/2 e pi/2. Per esprimere l&#39;arcotangente in gradi, moltiplicate il risultato per 180/PI()."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ARC TANGENT(metric)]**


[!BADGE Riga]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metrica | Tangente dell&#39;angolo desiderato da -1 a 1 |



## Cdf-T {#cdf-t}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_cdf_t"
>title="Cdf-T"
>abstract="Restituisce la probabilità che una variabile casuale con distribuzione di t-studente con n gradi di libertà abbia un punteggio z inferiore a col."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(metric, number)]**

Restituisce la probabilità che una variabile casuale con distribuzione di t-studente con n gradi di libertà abbia un punteggio z inferiore a col.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica per la quale desideri la funzione di distribuzione cumulativa della distribuzione t di Student |
| number | I gradi di libertà per la funzione di distribuzione cumulativa della distribuzione t dello studente |

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
>id="calcmetrics_function_cdf_z"
>title="Cdf-Z"
>abstract="Restituisce la probabilità che una variabile casuale con una distribuzione normale abbia un punteggio z inferiore a col."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(metric, number)]**

Restituisce la probabilità che una variabile casuale con una distribuzione normale abbia un punteggio z inferiore a col.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica per la quale si desidera la funzione di distribuzione cumulativa della distribuzione normale standard |

### Esempi

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## Soffitto {#ceiling}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_ceiling"
>title="Soffitto"
>abstract="Restituisce l’integer più piccolo, non inferiore a un valore specificato. Ad esempio, se desideri evitare di riportare i decimali della valuta per le entrate e il prezzo di un prodotto è pari a 569,34 $, utilizza la formula CEILING(Revenue) per arrotondare le entrate al dollaro più vicino o 570 $."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CEILING(metric)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | La metrica da arrotondare |


## Confidence {#confidence}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_confidence"
>title="Confidence"
>abstract="Calcolare l&#39;affidabilità valida in qualsiasi momento utilizzando il metodo WASKR come descritto in [Teoria del limite centrale uniforme nel tempo e sequenze di affidabilità asintotiche](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Calcolare l&#39;affidabilità valida in qualsiasi momento utilizzando il metodo WASKR come descritto in [Teoria del limite centrale uniforme nel tempo e sequenze di affidabilità asintotiche](https://arxiv.org/pdf/2103.06476).

L’affidabilità è una misura probabilistica della quantità di prove che dimostrano che una determinata variante è uguale alla variante di controllo. Una maggiore affidabilità indica meno prove dell’ipotesi che le varianti di controllo e non di controllo abbiano prestazioni uguali.

| Argomento | Descrizione |
| --- | --- |
| normalizing-container | La base (Persone, Sessioni o Eventi) su cui viene eseguito un test. |
| success-metric | La metrica o le metriche con cui un utente confronta le varianti. |
| controllo | La variante con cui vengono confrontate tutte le altre varianti dell’esperimento. Immetti il nome dell’elemento della dimensione della variante di controllo. |
| soglia di significatività | La soglia in questa funzione è impostata su un valore predefinito di 95%. |


## Affidabilità (inferiore) {#confidence-lower}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_confidence_lower"
>title="Affidabilità (inferiore)"
>abstract="Calcolare l&#39;affidabilità valida per qualsiasi tempo **lower** utilizzando il metodo WASKR come descritto in [Teoria dei limiti centrali uniformi per tempo e sequenze di affidabilità asintotiche](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Calcolare l&#39;affidabilità valida per qualsiasi tempo **lower** utilizzando il metodo WASKR come descritto in [Teoria dei limiti centrali uniformi per tempo e sequenze di affidabilità asintotiche](https://arxiv.org/pdf/2103.06476).

L’affidabilità è una misura probabilistica della quantità di prove che dimostrano che una determinata variante è uguale alla variante di controllo. Una maggiore affidabilità indica meno prove dell’ipotesi che le varianti di controllo e non di controllo abbiano prestazioni uguali.

| Argomento | Descrizione |
| --- | --- |
| normalizing-container | La base (Persone, Sessioni o Eventi) su cui viene eseguito un test. |
| success-metric | La metrica o le metriche con cui un utente confronta le varianti. |
| controllo | La variante con cui vengono confrontate tutte le altre varianti dell’esperimento. Immetti il nome dell’elemento della dimensione della variante di controllo. |
| soglia di significatività | La soglia in questa funzione è impostata su un valore predefinito di 95%. |

## Affidabilità (superiore) {#confidence-upper}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_confidence_upper"
>title="Affidabilità (superiore)"
>abstract="Calcolare l&#39;intervallo di confidenza valido per qualsiasi tempo **upper** utilizzando il metodo WASKR come descritto in [Teoria dei limiti centrali uniforme per il tempo e sequenze di confidenza asintotiche](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Calcolare l&#39;intervallo di confidenza valido per qualsiasi tempo **upper** utilizzando il metodo WASKR come descritto in [Teoria dei limiti centrali uniforme per il tempo e sequenze di confidenza asintotiche](https://arxiv.org/pdf/2103.06476).

L’affidabilità è una misura probabilistica della quantità di prove che dimostrano che una determinata variante è uguale alla variante di controllo. Una maggiore affidabilità indica meno prove dell’ipotesi che le varianti di controllo e non di controllo abbiano prestazioni uguali.

| Argomento | Descrizione |
| --- | --- |
| normalizing-container | La base (Persone, Sessioni o Eventi) su cui viene eseguito un test. |
| success-metric | La metrica o le metriche con cui un utente confronta le varianti. |
| controllo | La variante con cui vengono confrontate tutte le altre varianti dell’esperimento. Immetti il nome dell’elemento della dimensione della variante di controllo. |
| soglia di significatività | La soglia in questa funzione è impostata su un valore predefinito di 95%. |


## Coseno {#cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_cosine"
>title="Coseno"
>abstract="Restituisce il coseno dell’angolo specificato. Se l&#39;angolo è espresso in gradi, moltiplicatelo per PI()/180."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL COSINE(metric)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | L’angolo in radianti di cui vuoi ottenere il coseno |


## Radice cubica {#cube-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_cube_root"
>title="Radice cubica"
>abstract="Restituisce la radice cubica positiva di un numero. La radice cubica di un numero corrisponde al valore di quel numero elevato alla potenza di 1/3."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CUBE ROOT(metric)]**


Restituisce la radice cubica positiva di un numero. La radice cubica di un numero corrisponde al valore di quel numero elevato alla potenza di 1/3.


| Argomento | Descrizione |
|---|---|
| metrica | La metrica per la quale si desidera calcolare la radice cubica |



## Cumulativo {#cumulative}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_cumulative"
>title="Cumulativo"
>abstract="Restituisce la somma degli ultimi n elementi della colonna x. Se n > 0, somma gli ultimi n elementi o x. Se n &lt; 0, sommare gli elementi precedenti."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE(number, metric)]**

Restituisce la somma degli ultimi n elementi della colonna x. Se n > 0, somma gli ultimi n elementi o x. Se n &lt; 0, sommare gli elementi precedenti.

| Argomento | Descrizione |
| --- | --- |
| number | L’ultimo numero N di righe per cui restituire la somma. Se N &lt;= 0 utilizzare tutte le righe precedenti. |
| metrica | La metrica di cui desideri la Somma cumulativa. |

### Esempi

| Data | Ricavi | CUMULATIVE(0, Revenue) | CUMULATIVE(2, Revenue) |
|------|------:|--------------:|--------------:|
| Maggio | $ 500 | $ 500 | $ 500 |
| Giugno | $ 200 | $ 700 | $ 700 |
| Luglio | $ 400 | $ 1100 | $ 600 |


## Cumulativo (media) {#cumulative-average}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_cumulative_average"
>title="Cumulativo (media)"
>abstract="Restituisce la media degli ultimi n elementi della colonna x. Se n > 0, somma gli ultimi n elementi o x. Se n &lt; 0, sommare gli elementi precedenti."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE AVERAGE(number, metric)]**

Restituisce la media degli ultimi n elementi della colonna x. Se n > 0, somma gli ultimi n elementi o x. Se n &lt; 0, sommare gli elementi precedenti.

| Argomento | Descrizione |
| --- | --- |
| number | L’ultimo numero N di righe per cui restituire la media. Se N &lt;= 0 utilizzare tutte le righe precedenti. |
| metrica | La metrica di cui desideri la Media cumulativa. |

>[!NOTE]
>
>Questa funzione non funziona con metriche di tasso come ricavi per persona. La funzione calcola la media dei tassi, anziché sommare le entrate rispetto all’ultima N, quindi sommare le persone rispetto all’ultima N e infine dividerle. <br/>Utilizzare invece [**[!UICONTROL CUMULATIVE(revenue)]**](#cumulative) ![Dividi](/help/assets/icons/Divide.svg) [**[!UICONTROL CUMULATIVE(person)]**](#cumulative).
>


## Uguale {#equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_equal"
>title="Uguale"
>abstract="Uguale. L’output è 0 (false) o 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL EQUAL()]**

Uguale. L’output è 0 (false) o 1 (true).


| Argomento | Descrizione |
|---|---|
| metric_X | |
| metric_Y | |

### Esempio

`Metric 1 = Metric 2`


## Regressione esponenziale: coefficiente di correlazione {#exponential-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_exponential_regression_correlation_coefficient"
>title="Regressione esponenziale: coefficiente di correlazione"
>abstract="Regressione esponenziale: Y = a exp(X) + b. Restituisce il coefficiente di correlazione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabella]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da correlare con metric_Y |
| metric_Y | Metrica da correlare con metric_X |
| include_zeros | Se includere o meno i valori zero nei calcoli |

## Regressione esponenziale: valore Y previsto {#exponential-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_exponential_regression_predicted_y"
>title="Regressione esponenziale: valore Y previsto"
>abstract="Regressione esponenziale: Y = a exp(X) + b. Restituisce Y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Riga]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati indipendenti. |
| metric_Y | Una metrica da designare come dati dipendenti. |
| include_zeros | Se includere o meno i valori zero nei calcoli |


## Regressione esponenziale: intersezione {#exponential-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_exponential_regression_intercept"
>title="Regressione esponenziale: intersezione"
>abstract="Regressione esponenziale: Y = a exp(X) + b. Restituisce b."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |


## Regressione esponenziale: pendenza {#exponential-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_exponential_regression_slope"
>title="Regressione esponenziale: pendenza"
>abstract="Regressione esponenziale: Y = a exp(X) + b. Restituisce a."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabella]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |


## Floor {#floor}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_floor"
>title="Floor"
>abstract="Restituisce l’integer più grande, non superiore a un valore specificato. Ad esempio, se desideri evitare di riportare i decimali della valuta per le entrate e il prezzo di un prodotto è pari a 569,34 $, utilizza la formula FLOOR(Revenue) per arrotondare le entrate al dollaro più vicino o 569 $."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR(metric_X, metric_Y, include_zeros)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | La metrica da arrotondare. |


## Maggiore di {#greather-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_greater_than"
>title="Maggiore di"
>abstract="L’output è 0 (false) o 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN()]**

L’output è 0 (false) o 1 (true).

| Argomento | Descrizione |
|---|---|
| metric_X | |
| metric_Y | |

### Esempio

`Metric 1 > Metric 2`


## Maggiore di o uguale a {#greater-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_greater_than_or_equal"
>title="Maggiore di o uguale a"
>abstract="Maggiore o uguale a. L’output è 0 (false) o 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN OR EQUAL()]**

Maggiore o uguale a. L’output è 0 (false) o 1 (true).

| Argomento | Descrizione |
|---|---|
| metric_X |  |
| metric_Y |  |

### Esempio

`Metric 1 >= Metric 2`



## Coseno iperbolico {#hyperbolic-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_hyperbolic_cosine"
>title="Coseno iperbolico"
>abstract="Restituisce il coseno iperbolico di un numero."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC COSINE(metric)]**


[!BADGE Riga]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metrica | L’angolo in radianti di cui vuoi ottenere il coseno iperbolico |



## Seno iperbolico {#hyperbolic-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_hyperbolic_sine"
>title="Seno iperbolico"
>abstract="Restituisce il seno iperbolico di un numero."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC SINE(metric)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | L’angolo in radianti di cui vuoi ottenere il seno iperbolico |


## Tangente iperbolica {#hyperbolic-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_hyperbolic_tangent"
>title="Tangente iperbolica"
>abstract="Restituisce la tangente iperbolica di un numero."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC TANGENT(metric)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | Angolo in radianti di cui trovare la tangente iperbolica |


## Se  {#if}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_if"
>title="Se "
>abstract="Se il valore del parametro condition è diverso da zero (true), il risultato sarà il valore del parametro value_if_true. In caso contrario, è il valore del parametro value_if_false."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL IF(logical_test, value_if_true, value_if_false)]**


[!BADGE Riga]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| logical_test | Obbligatorio. Qualsiasi valore o espressione che può essere valutato come TRUE o FALSE |
| value_if_true | Il valore che vuoi ottenere se l’argomento logical_test restituisce TRUE. Se non è incluso, questo argomento sarà pari a 0 per impostazione predefinita. |
| value_if_false | Il valore che vuoi ottenere se l’argomento logical_test restituisce FALSE. Se non è incluso, questo argomento sarà pari a 0 per impostazione predefinita. |


## Minore di {#less-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_less_than"
>title="Minore di"
>abstract="L’output è 0 (false) o 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN()]**

L’output è 0 (false) o 1 (true).

| Argomento | Descrizione |
|---|---|
| metric_X | |
| metric_Y | |

### Esempio

`Metric 1 < Metric 2`


## Minore o uguale a {#less-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_less_than_or_equal"
>title="Minore o uguale a"
>abstract="Minore o uguale a. L’output è 0 (false) o 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN OR EQUAL()]**

Minore o uguale a. L’output è 0 (false) o 1 (true).

| Argomento | Descrizione |
|---|---|
| metric_X | |
| metric_Y | |

### Esempio

`Metric 1 <= Metric 2`



## Lift (#lift)

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_lift"
>title="Lift"
>abstract="L’incremento del rapporto rispetto al valore di controllo."

<!-- markdownlint-enable MD034 -->

| Argomento | Descrizione |
| --- | --- |
| normalizing-container | La base (Persone, Sessioni o Eventi) su cui viene eseguito un test. |
| success-metric | La metrica o le metriche con cui un utente confronta le varianti. |
| controllo | La variante con cui vengono confrontate tutte le altre varianti dell’esperimento. Immetti il nome dell’elemento della dimensione della variante di controllo. |



## Regressione lineare: coefficiente di correlazione {#linear-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_linear_regression_correlation_coefficient"
>title="Regressione lineare: coefficiente di correlazione"
>abstract="Regressione lineare: Y = a X + b. Restituisce il coefficiente di correlazione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabella]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da correlare con metric_Y |
| metric_Y | Metrica da correlare con metric_X |
| include_zeros | Se includere o meno i valori zero nei calcoli |



## Regressione lineare: intersezione {#linear-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_linear_regression_intercept"
>title="Regressione lineare: intersezione"
>abstract="Regressione lineare: Y = a X + b. Restituisce b."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabella]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |



## Regressione lineare: valore Y previsto {#linear-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_linear_regression_predicted_y"
>title="Regressione lineare: valore Y previsto"
>abstract="Regressione lineare: Y = a X + b. Restituisce Y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Riga]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |



## Regressione lineare: pendenza {#linear-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_linear_regression_slope"
>title="Regressione lineare: pendenza"
>abstract="Regressione lineare: Y = a X + b. Restituisce a."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |


## Base logaritmo 10 {#log-base-ten}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_log_base_ten"
>title="Base logaritmo 10"
>abstract="Restituisce il logaritmo base 10 di un numero."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG BASE 10(metric)]**


[!BADGE Riga]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metrica | Numero reale positivo di cui vuoi ottenere il logaritmo base 10 |


## Regressione logaritmo: coefficiente di correlazione {#log-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_log_regression_coefficient"
>title="Regressione logaritmo: coefficiente di correlazione"
>abstract="Regressione logaritmo: Y = a ln(X) + b. Restituisce il coefficiente di correlazione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da correlare con metric_Y |
| metric_Y | Metrica da correlare con metric_X |
| include_zeros | Se includere o meno i valori zero nei calcoli |


## Regressione registro: intersezione {#log-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_log_regression_intercept"
>title="Regressione registro: intersezione"
>abstract="Regressione logaritmo: Y = a ln(X) + b. Restituisce b."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |



## Regressione registro: valore Y previsto {#log-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_log_regression_predicted_y"
>title="Regressione registro: valore Y previsto"
>abstract="Regressione logaritmo: Y = a ln(X) + b. Restituisce Y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |



## Regressione registro: pendenza {#log-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_log_regression_slope"
>title="Regressione registro: pendenza"
>abstract="Regressione logaritmo: Y = a ln(X) + b. Restituisce a."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |



## Logaritmo naturale {#natural-log}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_natural_log"
>title="Logaritmo naturale"
>abstract="Restituisce il logaritmo naturale di un numero. I logaritmi naturali si basano sulla costante e (2,71828182845904). LN è l’inverso della funzione EXP."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL NATURAL LOG(metric)]**

Restituisce il logaritmo naturale di un numero. I logaritmi naturali si basano sulla costante e (2,71828182845904). LN è l’inverso della funzione EXP.

| Argomento | Descrizione |
|---|---|
| metrica | Numero reale positivo di cui vuoi ottenere il logaritmo naturale |



## Not {#not}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_not"
>title="Not"
>abstract="Negazione come booleano. L’output è 0 (false) o 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL NOT(logical)]**

Negazione come booleano. L’output è 0 (false) o 1 (true).

| Argomento | Descrizione |
|---|---|
| logical | Obbligatorio. Valore o espressione che può essere valutato come TRUE o FALSE |



## Not Equal {#not-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_not_equal"
>title="Not Equal"
>abstract="Diverso da. L’output è 0 (false) o 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL NOT EQUAL()]**


Diverso da. L’output è 0 (false) o 1 (true).


| Argomento | Descrizione |
|---|---|
| metric_X | |
| metric_Y | |

### Esempio

`Metric 1 != Metric 2`


## Oppure {#or}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_or"
>title="Oppure"
>abstract="Disgiunzione. Diverso da zero è considerato vero e uguale a zero è considerato falso. L’output è 0 (false) o 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL OR(logical_test)]**


[!BADGE Riga]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| logical_test | Richiede almeno un parametro, ma può accettare un numero qualsiasi di parametri. Qualsiasi valore o espressione che può essere valutato come TRUE o FALSE |


>[!NOTE]
>
>0 (zero) significa False, mentre qualsiasi altro valore corrisponde a True.


## Pi {#pi}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_pi"
>title="Pi"
>abstract="Restituisce Pi: 3,14159..."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

Restituisce Pi: 3,14159...


## Regressione di potenza: coefficiente di correlazione {#power-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_power_regression_correlation_coefficient"
>title="Regressione di potenza: coefficiente di correlazione"
>abstract="Regressione di potenza: Y = b X ^ a. Restituisce il coefficiente di correlazione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da correlare con metric_Y |
| metric_Y | Metrica da correlare con metric_X |
| include_zeros | Se includere o meno i valori zero nei calcoli |



## Regressione di potenza: intersezione {#power-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_power_regression_intercept"
>title="Regressione di potenza: intersezione"
>abstract="Regressione di potenza: Y = b X ^ a. Restituisce b."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabella]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |


## Regressione di potenza: valore Y previsto {#power-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_power_regression_predicted_y"
>title="Regressione di potenza: valore Y previsto"
>abstract="Regressione di potenza: Y = b X ^ a. Restituisce Y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |



## Regressione di potenza: pendenza {#power-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_power_regression_slope"
>title="Regressione di potenza: pendenza"
>abstract="Regressione di potenza: Y = b X ^ a. Restituisce a."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |



## Regressione quadratica: coefficiente di correlazione {#quadratic-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_quadratic_regression_correlation_coefficient"
>title="Regressione quadratica: coefficiente di correlazione"
>abstract="Regressione quadratica: Y = (a + bX) ^ 2, Restituisce il coefficiente di correlazione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da correlare con metric_Y |
| metric_Y | Metrica da correlare con metric_X |
| include_zeros | Se includere o meno i valori zero nei calcoli |

## Regressione quadratica: intersezione {#quadratic-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_quadratic_regression_intercept"
>title="Regressione quadratica: intersezione"
>abstract="Regressione quadratica: Y = (a + bX) ^ 2, Restituisce a."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |


## Regressione quadratica: valore Y previsto {#quadratic-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_quadratic_regression_predicted_y"
>title="Regressione quadratica: valore Y previsto"
>abstract="Regressione quadratica: Y = (a + bX) ^ 2, Restituisce Y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |


## Regressione quadratica: pendenza {#quadratic-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_quadratic_regression_slope"
>title="Regressione quadratica: pendenza"
>abstract="Regressione quadratica: Y = (a + bX) ^ 2, Restituisce b."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |



## Regressione reciproca: coefficiente di correlazione {#reciprocal-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_reciprocal_regression_correlation_coefficient"
>title="Regressione reciproca: coefficiente di correlazione"
>abstract="Regressione reciproca: Y = a + b X ^ -1. Restituisce il coefficiente di correlazione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Metrica da correlare con metric_Y |
| metric_Y | Metrica da correlare con metric_X |
| include_zeros | Se includere o meno i valori zero nei calcoli |


## Regressione reciproca: intersezione {#reciprocal-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_reciprocal_regression_intercept"
>title="Regressione reciproca: intersezione"
>abstract="Regressione reciproca: Y = a + b X ^ -1. Restituisce un valore."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |


## Regressione reciproca: valore Y previsto {#reciprocal-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_reciprocal_regression_predicted_y"
>title="Regressione reciproca: valore Y previsto"
>abstract="Regressione reciproca: Y = a + b X ^ -1. Restituisce Y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |


## Regressione reciproca: pendenza {#reciprocal-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_reciprocal_regression_slope"
>title="Regressione Reciproale: Pendenza"
>abstract="Regressione reciproca: Y = a + b X ^ -1. Restituisce b."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabella]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metric_X | Una metrica da designare come dati dipendenti |
| metric_Y | Una metrica da designare come dati indipendenti |
| include_zeros | Se includere o meno i valori zero nei calcoli |




## Seno {#sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_sine"
>title="Seno"
>abstract="Restituisce il seno dell’angolo specificato. Se l&#39;angolo è espresso in gradi, moltiplicatelo per PI()/180."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL SINE(metric)]**


[!BADGE Riga]{type="Neutral"}


| Argomento | Descrizione |
|---|---|
| metrica | L’angolo in radianti di cui vuoi ottenere il seno |




## Punteggio T {#t-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_t_score"
>title="Punteggio T"
>abstract="La deviazione dalla [MEDIA](cm-functions.md#mean), divisa per la deviazione standard. Alias per [punteggio Z](#z-score)."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE(metric, include_zeros)]**

La deviazione dalla [MEDIA](cm-functions.md#mean), divisa per la deviazione standard. Alias per [punteggio Z](#z-score).

| Argomento | Descrizione |
|---|---|
| metrica | La metrica per la quale desideri il punteggio T |
| include_zeros | Se includere o meno i valori zero nei calcoli |


## Test T {#t-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_t_test"
>title="Test T"
>abstract="Esegue un test t a coda m con un punteggio t di x e n gradi di libertà."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL T-TEST(metric, degrees, tails)]**

Esegue un test t a coda m con un punteggio t di x e n gradi di libertà.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica sulla quale desideri eseguire un test T |
| gradi | I gradi di libertà |
| code | Lunghezza della coda da utilizzare per eseguire la prova T |

### Dettagli

La firma è T-TEST (metrica, gradi, code). Sotto, effettua semplicemente la chiamata a ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)**. Questa funzione è simile alla funzione **[Z-TEST](#z-test)**, che esegue ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)**.

- ***m*** è il numero di code.
- ***n*** è il grado di libertà e deve essere un numero costante per l&#39;intero report, ovvero non deve cambiare riga per riga.
- ***x*** è la statistica del test T e spesso è una formula (ad esempio, **[Z-SCORE](#z-score)**) basata su una metrica e viene valutata su ogni riga.

Il valore restituito è la probabilità di visualizzare la statistica x del test in base ai gradi di libertà e al numero di code.

### Esempi

1. Utilizza la funzione per trovare i valori erratici:

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. Combina la funzione con **[IF](#if)** per ignorare tassi non raggiunti molto elevati o bassi e contare le sessioni su tutto il resto:

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```



## Tangente {#tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_tangent"
>title="Tangente"
>abstract="Restituisce la tangente dell’angolo specificato. Se l&#39;angolo è espresso in gradi, moltiplicatelo per PI()/180."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENT(metric)]**

Restituisce la tangente dell’angolo specificato. Se l&#39;angolo è espresso in gradi, moltiplicatelo per PI()/180.

| Argomento | Descrizione |
|---|---|
| metrica | L’angolo in radianti di cui vuoi ottenere la tangente |



## Punteggio Z {#z-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_z_score"
>title="Punteggio Z"
>abstract="La deviazione dalla media divisa per la deviazione standard."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL Z-SCORE(metric, include_zeros)]**

[!BADGE Riga]{type="Neutral"}

| Argomento | Descrizione |
|---|---|
| metrica | La metrica per la quale desideri il punteggio Z |
| include_zeros | Se includere o meno i valori zero nei calcoli |

Un punteggio Z pari a 0 (zero) implica che il punteggio è uguale alla media. Un punteggio Z può essere positivo o negativo, il che significa se è superiore o inferiore alla media, oltre al numero di deviazioni standard.

L’equazione per il punteggio Z è:

![](assets/z_score.png)

Dove ***[!DNL x]*** è il punteggio non elaborato, ***[!DNL μ]*** è la media della popolazione e ***[!DNL σ]*** è la deviazione standard della popolazione.

>[!NOTE]
>
>***[!DNL μ]*** (mu) e ***[!DNL σ]*** (sigma) vengono calcolati automaticamente dalla metrica.



## Test Z {#z-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_z_test"
>title="Test Z"
>abstract="Esegue un test z a una coda n con un punteggio z pari a x."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST(metric_tails)]**

Esegue un test z a una coda n con un punteggio z pari a x.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica su cui desideri eseguire un test Z |
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