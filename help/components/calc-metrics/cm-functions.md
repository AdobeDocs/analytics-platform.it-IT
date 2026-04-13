---
title: Funzioni di base
description: Scopri le funzioni di base delle metriche calcolate.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 211f0411d0bf70288cbd46bb219fce7ae99fe03d
workflow-type: tm+mt
source-wordcount: '3599'
ht-degree: 45%

---

# Funzioni di base


Il [Generatore di metriche calcolate](cm-workflow/cm-build-metrics.md) consente di applicare funzioni statistiche e matematiche. Questo articolo riporta un elenco alfabetico delle funzioni e delle relative definizioni.

>[!NOTE]
>
>Se [!DNL metric] è identificato come argomento in una funzione, sono consentite anche altre espressioni di metriche. Ad esempio, [COLUMN MAXIMUM(metrics)](#column-maximum) consente anche [COLUMN MAXIMUM(PageViews + Sessions)](#column-maximum).



## Funzioni tabella e funzioni riga

Una funzione tabella è una funzione in cui l’output è lo stesso per ogni riga della tabella. Una funzione riga è una funzione in cui l’output è diverso per ogni riga della tabella.

Se applicabile e pertinente, una funzione viene annotata con il tipo di funzione: [!BADGE Tabella]{type="Neutral"} o [!BADGE Riga]{type="Neutral"}

## Che cosa significa il parametro include-zeros?

Il parametro indica se includere gli zeri all’interno del calcolo. Talvolta lo zero *non* ha alcun significato, ma in determinate occasioni può risultare importante.

Ad esempio, se hai una metrica Revenue (Entrate) e ne aggiungi al report una del tipo Page Views (Visualizzazioni pagina), improvvisamente saranno presenti più righe per le entrate che sono pari a zero. Probabilmente non vorrai che questa metrica aggiuntiva influisca su **[MEAN](cm-functions.md#mean)**, **[ROW MINIMUM](cm-functions.md#row-min)**, **[QUARTILE](cm-functions.md#quartile)** e altri calcoli presenti nella colonna dei ricavi. In questo caso, dovrai controllare il parametro `include-zeros`.

In alternativa, puoi avere due metriche di interesse e una con una media o un minimo più elevati, perché alcune righe sono pari a zero.  In tal caso, puoi scegliere di non selezionare il parametro per includere degli zeri



## Valore assoluto {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-abs"
>title="Valore assoluto"
>abstract="Restituisce il valore assoluto di un numero. Il valore assoluto di un numero è il numero con un valore positivo."

<!-- markdownlint-enable MD034 -->


![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL VALORE(metrica) ASSOLUTO]**

[!BADGE Riga]{type="Neutral"} Restituisce il valore assoluto di un numero. Il valore assoluto di un numero è il numero con un valore positivo.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica della quale desideri calcolare il valore assoluto. |

**Caso d&#39;uso**: assicurati che tutti i risultati siano positivi durante l&#39;analisi di metriche che potrebbero produrre valori negativi, come delta ricavi o modifiche percentuali. Questo aiuta a focalizzare l&#39;attenzione sulla portata del cambiamento indipendentemente dalla direzione.

**Nel Generatore di metriche calcolate**: racchiudere la metrica o l&#39;espressione nella funzione **Valore assoluto**, ad esempio: **Valore assoluto**(Ricavi correnti - Ricavi precedenti). In questo modo eventuali differenze negative vengono convertite in valori positivi.

>[!TIP]
>
>Utilizzalo per misurare le differenze assolute tra due periodi di tempo o segmenti, indipendentemente dal fatto che le prestazioni siano aumentate o diminuite.
>

## Massimo colonna {#column-maximum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-max"
>title="Massimo colonna"
>abstract="Restituisce il valore più grande in un insieme di elementi dimensionali della colonna di una metrica. MAXV valuta verticalmente all’interno di una singola colonna (metrica) tra gli elementi dimensionali."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL COLONNA MASSIMO(metrica, include_zeros)]**

Restituisce il valore più grande in un insieme di elementi dimensionali della colonna di una metrica. MAXV valuta verticalmente all’interno di una singola colonna (metrica) tra gli elementi dimensionali.

| Argomento | Descrizione |
|---|---|
| metrica | Richiede almeno una metrica, ma può accettare un numero qualsiasi di metriche come parametri. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |

**Caso d&#39;uso**: identifica il valore più alto all&#39;interno di un raggruppamento, ad esempio il giorno con il maggior numero di visite o il prodotto con il maggior fatturato. Questo consente di evidenziare i picchi di prestazioni tra le categorie.

**Nel Generatore di metriche calcolate**: applica **Numero massimo di colonne** a una metrica come *Ricavi* o *Sessioni* con suddivisione per *Giorno* o *Prodotto*. La funzione restituisce il valore più grande in quella colonna per ogni riga.

>[!TIP]
>
>Utilizza un&#39;istruzione [IF](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if), ad esempio **IF**(*Revenue* = **Column Maximum***(Revenue*), 1, 0) per evidenziare l&#39;elemento con prestazioni migliori nel raggruppamento.
>

## Minimo colonna {#column-minimum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-min"
>title="Minimo colonna"
>abstract="Restituisce il valore più piccolo in un insieme di elementi dimensionali della colonna di una metrica. MINV valuta verticalmente all’interno di una singola colonna (metrica) tra gli elementi dimensionali."

<!-- markdownlint-enable MD034 -->


![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL COLONNA MINIMA(metrica, include_zeros)]**

Restituisce il valore più piccolo in un insieme di elementi dimensionali della colonna di una metrica. MINV valuta verticalmente all’interno di una singola colonna (metrica) tra gli elementi dimensionali.

| Argomento | Descrizione |
|---|---|
| metrica | Richiede almeno una metrica, ma può accettare un numero qualsiasi di metriche come parametri. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |

**Caso d&#39;uso**: identifica il valore con le prestazioni più basse all&#39;interno di un raggruppamento, ad esempio la campagna con le conversioni più basse o il giorno con le entrate più basse. Questo consente di far emergere rapidamente segmenti poco performanti.

**Nel Generatore di metriche calcolate**: Applica **Colonna minima** a una metrica come *Ricavo* o *Tasso di conversione* quando si suddivide per *Campagna* o *Giorno*. La funzione restituisce il valore più piccolo in quella colonna per ogni riga.

>[!TIP]
>
>Utilizza un&#39;istruzione [IF](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if), ad esempio **IF**(*Revenue* = **Column Minimum***(Revenue*), 1, 0) per evidenziare l&#39;elemento con le prestazioni peggiori nel raggruppamento.
>


## Somma colonna {#column-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-sum"
>title="Somma colonna"
>abstract="Somma tutti i valori numerici di una metrica all’interno di una colonna (negli elementi di una dimensione)."

<!-- markdownlint-enable MD034 -->


![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL SOMMA COLONNA(metrica)]**

Somma tutti i valori numerici di una metrica all’interno di una colonna (negli elementi di una dimensione).

| Argomento | Descrizione |
|---|---|
| metrica | Richiede almeno una metrica, ma può accettare un numero qualsiasi di metriche come parametri. |

**Caso d&#39;uso**: calcola il totale di tutti i valori all&#39;interno di un raggruppamento, ad esempio i ricavi totali per tutti i prodotti o le visite totali per tutti i giorni. Questo è utile quando hai bisogno di un totale complessivo da confrontare con i singoli valori di riga.

**Nel Generatore di metriche calcolate**: Applica **Somma colonna** a una metrica come *Ricavi* o *Sessioni* durante la suddivisione per *Prodotto* o *Giorno*. La funzione restituisce il totale di tutti i valori in quella colonna per ogni riga.

>[!TIP]
>
>Utilizzare quando è necessario un riferimento al totale complessivo per calcolare le quote o le percentuali delle prestazioni totali.
>


## Conteggio {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="Conteggio"
>abstract="Restituisce il numero, o conteggio, di valori diversi da zero di una metrica all’interno di una colonna (il numero di elementi univoci riportati all’interno di una dimensione)."

<!-- markdownlint-enable MD034 -->


![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL CONTEGGIO(metrica)]**

[!BADGE Tabella]{type="Neutral"} Restituisce il numero, o conteggio, di valori diversi da zero per una metrica all&#39;interno di una colonna (il numero di elementi univoci riportati all&#39;interno di una dimensione).

| Argomento | Descrizione |
|---|---|
| metrica | La metrica da conteggiare. |

**Caso d&#39;uso**: conta il numero di punti dati inclusi in un calcolo, ad esempio il numero di giorni in un intervallo di date o il numero di prodotti in un raggruppamento. Questo aiuta quando devi sapere quanti elementi contribuiscono a un valore aggregato.

**Nel generatore di metriche calcolate**: applica **Count** a una metrica come *Sessioni* o *Entrate* per restituire il numero totale di righe (o punti dati) inclusi nel raggruppamento o nell&#39;intervallo di date corrente.

>[!TIP]
>
>Usare insieme a **Somma colonna** per calcolare manualmente le medie (ad esempio, **Somma colonna**(*Ricavi*) / **Conteggio**(Ricavi)).
>

## Esponente {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="Esponente"
>abstract="Restituisce e elevato alla potenza di un numero specificato. La costante e è uguale a 2,71828182845904, la base del logaritmo naturale. ESPONENTE è l’inverso di LN, il logaritmo naturale di un numero."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ESPONENTE(metrica)]**

[!BADGE Riga]{type="Neutral"} Restituisce *e* elevato alla potenza di un numero specificato. La costante *e* è uguale a 2,71828182845904, la base del logaritmo naturale. ESPONENTE è l’inverso di LN, il logaritmo naturale di un numero.

| Argomento | Descrizione |
|---|---|
| metrica | L’esponente applicato alla base *e*. |

**Caso d&#39;uso**: aumenta di *e* alla potenza di un numero o di una metrica specificata. Ciò è utile quando si modellano le tendenze di crescita o si ridimensiona una metrica in modo esponenziale.

**Nel generatore di metriche calcolate**: utilizzare **Esponente** con una metrica. Ad esempio: **Esponente**(*Sessioni*) eleva *e* alla potenza della metrica *Sessioni*.

>[!TIP]
>
>Combina con **Logaritmo** per la modellazione avanzata o per uniformare i dati altamente variabili durante il confronto dei modelli di crescita.
>


## Media {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="Media"
>abstract="Restituisce la media aritmetica, o la media, di una metrica in una colonna."

<!-- markdownlint-enable MD034 -->


![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIA(metrica, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Restituisce la media aritmetica di una metrica in una colonna.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica di cui desideri calcolare la media. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |

**Caso d&#39;uso**: calcola la media aritmetica di un set di valori, ad esempio il ricavo medio giornaliero o il numero medio di visite per campagna. Questo aiuta a stabilire una linea di base per il confronto di singoli valori all’interno di un set di dati.

**Nel Generatore di metriche calcolate**: Applica **Media** a una metrica come *Ricavi* o *Sessioni* per restituire il valore medio in tutti i punti dati nel raggruppamento o nell&#39;intervallo di date selezionato.

>[!TIP]
>
>Utilizzare per comprendere le tendenze generali delle prestazioni o combinarle con **Deviazione standard** per misurare la coerenza rispetto alla media.
>

## Mediana {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="Mediana"
>abstract="Restituisce la mediana di una metrica in una colonna. La mediana è il numero al centro di un insieme di numeri. In altre parole, metà dei numeri è costituita da valori maggiori o uguali alla mediana e l’altra metà da quelli minori o uguali alla mediana."

<!-- markdownlint-enable MD034 -->


![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIANA(metric, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Restituisce la mediana di una metrica in una colonna. La mediana è il numero al centro di un insieme di numeri. In altre parole, metà dei numeri è costituita da valori maggiori o uguali alla mediana e l’altra metà da quelli minori o uguali alla mediana.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica di cui desideri calcolare la mediana. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |

**Caso d&#39;uso**: identifica il valore intermedio in un set di dati, ad esempio il ricavo giornaliero mediano o le visualizzazioni di pagina mediane per visita. Questa funzione è utile quando vuoi ridurre l’impatto di valori anomali e individuare la tendenza centrale dei dati.

**Nel generatore di metriche calcolate**: Applica mediana a una metrica come Ricavi o Visualizzazioni pagina per restituire il valore del punto intermedio in tutte le coordinate nel raggruppamento o nell&#39;intervallo di date selezionato.

>[!TIP]
>
>Utilizza invece di **Media** quando i tuoi dati contengono valori massimi o minimi che potrebbero distorcere la media.
>


## Modulo {#modulo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-modulo"
>title="Modulo"
>abstract="Restituisce il resto dopo aver diviso x per y utilizzando la divisione euclidea. "

<!-- markdownlint-enable MD034 -->


![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X, metric_Y)]**

Restituisce il resto dopo aver diviso x per y utilizzando la divisione euclidea.

| Argomento | Descrizione |
|---|---|
| metric_X | La prima metrica che desideri dividere. |
| metric_Y | La seconda metrica che desideri dividere. |

**Caso d&#39;uso**: restituire il resto dopo aver diviso un numero per un altro. Questo può essere utile per modelli ciclici o ripetuti, come l’identificazione ogni giorno ennesimo o una campagna in una sequenza.

**Nel generatore di metriche calcolate**: utilizzare **Modulo** con due input numerici. Ad esempio: **Modulo**(*Numero giorno*, 7) restituisce il resto dopo aver diviso il numero giorno per sette, in modo da semplificare il raggruppamento dei dati per settimana.

>[!TIP]
>
>Combina con logica condizionale per evidenziare intervalli ricorrenti o per segmentare i dati in base a cicli ripetuti.
>

### Altri esempi

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

## Percentile {#percentile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-percentile"
>title="Percentile"
>abstract="Restituisce l’ennesimo percentile, che è un valore compreso tra 0 e 100. Quando n &lt; 0, la funzione utilizza zero. Quando n > 100, la funzione restituisce 100."

<!-- markdownlint-enable MD034 -->


![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE(metrica, k, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Restituisce l&#39;ennesimo percentile, che è un valore compreso tra 0 e 100. Quando n &lt; 0, la funzione utilizza zero. Quando n > 100, la funzione restituisce 100.

| Argomento | Descrizione |
|---|---|
| metrica | Il valore percentile compreso tra 0 e 100 incluso. |
| k | La colonna della metrica che definisce la condizione relativa. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |

**Caso d&#39;uso**: identifica il valore al di sotto del quale rientra una determinata percentuale di punti dati, ad esempio il 90° percentile delle entrate giornaliere o delle visualizzazioni di pagina. Questo consente di misurare la distribuzione e rilevare valori anomali ad alte prestazioni.

**Nel Generatore di metriche calcolate**: Applica **Percentile** a una metrica come *Ricavi* o *Sessioni* e specifica il valore percentile desiderato (ad esempio, **Percentile**(*Ricavi*, 90)). Il risultato mostra la soglia al di sotto della quale il 90% dei punti dati.

>[!TIP]
>
>Utilizza per impostare benchmark di prestazioni o per filtrare in base alle giornate, campagne o prodotti con prestazioni migliori.
>

## Operatore di potenza {#power-operator}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pow"
>title="Operatore di potenza"
>abstract="Restituisce x elevato alla potenza y."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL OPERATORE DI ALIMENTAZIONE(metric_X, metrix_Y)]**

Restituisce x elevato alla potenza y.

| Argomento | Descrizione |
|---|---|
| metric_X | La metrica da elevare alla potenza metric_Y. |
| metric_Y | La potenza a cui desideri elevare metric_X. |

**Caso d&#39;uso**: aumentare un numero o una metrica alla potenza di un altro, ad esempio quadrare un valore o applicare un peso esponenziale. Questo è utile quando si modellano la crescita, si scalano i valori o si eseguono trasformazioni matematiche avanzate.

**Nel Generatore di metriche calcolate**: utilizzare **Operatore avanzato** tra due valori numerici o metriche. Ad esempio: *Revenue* ^ 2 eleva il valore *Revenue* alla seconda potenza.

>[!TIP]
>
>Simile alla funzione **Esponente** ma espressa come operatore matematico, consente formule più compatte nelle metriche calcolate.
>

## Quartile {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="Quartile"
>abstract="Restituisce il quartile dei valori di una metrica. Ad esempio, i quartili possono essere utilizzati per trovare il 25% dei prodotti che generano maggiori ricavi."

<!-- markdownlint-enable MD034 -->


![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric, quartile, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Restituisce il quartile dei valori per una metrica. Ad esempio, i quartili possono essere utilizzati per trovare il 25% dei prodotti che generano maggiori ricavi. [COLUMN MINIMUM](#column-minimum), [MEDIAN](#median) e [COLUMN MAXIMUM](#column-maximum) restituiscono lo stesso valore di [QUARTILE](#quartile) quando quartile è uguale rispettivamente a `0` (zero), `2` e `4`.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica di cui desideri calcolare il valore del quartile. |
| quartile | Indica quale valore del quartile restituire. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |

**Caso d&#39;uso**: dividi un set di dati in quattro parti uguali per capire come vengono distribuiti i valori, ad esempio per identificare il primo 25% dei giorni in base ai ricavi o alle visite. Questo consente di segmentare le prestazioni in gruppi classificati per un confronto più approfondito.

**Nel Generatore di metriche calcolate**: Applica **Quartile** a una metrica come *Ricavi* o *Sessioni* e specifica il quartile da restituire (ad esempio, **Quartile**(*Ricavi*, 3) per trovare la soglia per il terzo quartile, o il 25% superiore).

>[!TIP]
>
>Utilizzare per raggruppare i valori in livelli di prestazioni quali campagne o prodotti a basse, medie e alte prestazioni.
>

## Arrotondamento {#round}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-round"
>title="Arrotondamento"
>abstract="L’arrotondamento senza un parametro *numerico* è uguale all’arrotondamento con un parametro *numero* pari a 0, vale a dire arrotondato al numero intero più vicino.  Con un parametro *numerico* ROUND restituisce il *numero* di cifre a destra del decimale.  Se il *numero* è negativo, restituisce gli 0 a sinistra del decimale."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL ARROTONDA(metrica, numero)]**

L’arrotondamento senza un parametro *numerico* è uguale all’arrotondamento con un parametro *numero* pari a 0, vale a dire arrotondato al numero intero più vicino.  Con un parametro *numerico* ROUND restituisce il *numero* di cifre a destra del decimale.  Se il *numero* è negativo, restituisce gli 0 a sinistra del decimale.

| Argomento | Descrizione |
|---|---|
| metrica | La metrica da arrotondare. |
| number | Quante cifre a destra del decimale restituire. Se la cifra è negativa, restituisce gli zero a sinistra del decimale. |

**Caso d&#39;uso**: i risultati numerici vengono arrotondati a un numero specificato di cifre decimali. Questa funzione è utile per creare visualizzazioni più nitide o per semplificare la lettura delle metriche calcolate nei rapporti.

**Nel generatore di metriche calcolate**: Applica **Round** a una metrica o espressione e specifica il numero di posizioni decimali. Ad esempio: **Round**(*Tasso di conversione*, 2) arrotonda il valore a due posizioni decimali.

>[!TIP]
>
>Utilizza per standardizzare la formattazione delle metriche nei rapporti, in particolare quando vengono visualizzate percentuali o valori di valuta.
>

### Altri esempi

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```

## Conteggio righe {#row-count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-rows"
>title="Conteggio righe"
>abstract="Restituisce il numero di righe di una colonna specificata (il numero di elementi univoci riportati all’interno di una dimensione). *Univoci superati* viene conteggiato come 1."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL NUMERO RIGHE()]**

Restituisce il numero di righe di una colonna specificata (il numero di elementi univoci riportati all’interno di una dimensione). *Univoci superati* viene conteggiato come 1.

**Caso d&#39;uso**: conta il numero totale di righe restituite in un raggruppamento o in un set di dati, ad esempio il numero di giorni, campagne o prodotti inclusi in un rapporto. Questo aiuta a capire quanti elementi contribuiscono all’analisi.

**Nel Generatore di metriche calcolate**: Applica **Conteggio righe** per restituire il numero totale di righe nel raggruppamento o nel segmento corrente. Ad esempio, quando si visualizzano *Ricavi* per *Prodotto*, **Conteggio righe** restituisce il numero di prodotti visualizzati.

>[!TIP]
>
>Usare con altre funzioni come **Somma colonna** per calcolare manualmente le medie (ad esempio, **Somma colonna**(*Ricavi*) / **Conteggio righe**()).
>

## Massimo riga {#row-max}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-max"
>title="Massimo riga"
>abstract="Il massimo delle colonne di ogni riga."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL RIGA MAX(metric, include_zeros)]**

Il massimo delle colonne di ogni riga.

| Argomento | Descrizione |
|---|---|
| metrica | Richiede almeno una metrica, ma può accettare un numero qualsiasi di metriche come parametri. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |

**Caso d&#39;uso**: identifica il valore più alto in tutte le metriche in una singola riga, ad esempio determinando quale metrica (ad esempio, *Ricavi*, *Ordini* o *Sessioni*) ha il valore più alto per un giorno o un segmento specifico. Questo aiuta a evidenziare quale metrica lead all’interno di ogni riga di dati.

**Nel generatore di metriche calcolate**: applicare **Massimo riga** quando più metriche sono incluse in una metrica calcolata. Ad esempio: **Numero massimo righe**(*Ricavi*, *Ordini*, *Sessioni*) restituisce il valore più grande tra queste metriche per ogni riga.

>[!TIP]
>
>Utilizza per confrontare le metriche correlate una accanto all’altra e identificare quale contribuisce maggiormente alle prestazioni all’interno di ogni riga.
>

## Minimo riga {#row-min}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-min"
>title="Minimo riga"
>abstract="Minimo di colonne di ogni riga."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL RIGA MIN(metrica, include_zeros)]**

Minimo di colonne di ogni riga.

| Argomento | Descrizione |
|---|---|
| metrica | Richiede almeno una metrica, ma può accettare un numero qualsiasi di metriche come parametri. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |

**Caso d&#39;uso**: identifica il valore più basso in tutte le metriche in una singola riga, ad esempio la ricerca della metrica (ad esempio, *Ricavi*, *Ordini* o *Sessioni*) con il valore più basso per un giorno o un segmento particolare. Questo consente di individuare la metrica con le prestazioni più deboli all’interno di ogni riga di dati.

**Nel Generatore di metriche calcolate**: applicare **Minimo riga** quando si confrontano più metriche. Ad esempio: **Minimo riga**(*Ricavi*, *Ordini*, *Sessioni*) restituisce il valore più piccolo tra queste metriche per ogni riga.

>[!TIP]
>
>Combina con il valore Maximum di riga per calcolare gli intervalli di prestazioni o per evidenziare metriche con prestazioni inferiori in un confronto affiancato.
>

## Somma righe {#row-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-sum"
>title="Somma righe"
>abstract="Somma delle colonne di ogni riga."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL SOMMA RIGA(metrica, include_zeros)]**

Somma delle colonne di ogni riga.

| Argomento | Descrizione |
|---|---|
| metrica | Richiede almeno una metrica, ma può accettare un numero qualsiasi di metriche come parametri. |

**Caso d&#39;uso**: aggiungi i valori di più metriche all&#39;interno di una singola riga, ad esempio sommando *Ricavi* e *Imposta* per calcolare il valore totale della transazione o combinando *Sessioni* da origini diverse. Questo consente di consolidare le metriche correlate in un unico totale.

**Nel generatore di metriche calcolate**: applica **Somma righe** per combinare più metriche. Ad esempio: **Row Sum**(*Revenue*, *Tax*) aggiunge queste due metriche per ogni riga della suddivisione.

>[!TIP]
>
>Utilizza per creare totali combinati o per raggruppare gli indicatori di prestazioni correlati in un’unica metrica calcolata.
>

## Radice quadrata {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="Radice quadrata"
>abstract="Restituisce la radice quadrata positiva di un numero. La radice quadrata di un numero è il valore di quel numero elevato alla potenza di 1/2."

<!-- markdownlint-enable MD034 -->


![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL RADICE QUADRATA(metrica, include_zeros)]**

[!BADGE Riga]{type="Neutral"} Restituisce la radice quadrata positiva di un numero. La radice quadrata di un numero è il valore di quel numero elevato alla potenza di 1/2.

| Argomento | Descrizione |
|---|---|
| metrica | Metrica per la quale desideri calcolare la radice quadrata. |

**Caso d&#39;uso**: restituisce la radice quadrata di un numero o di una metrica, ad esempio la ricerca della radice della varianza durante il calcolo della deviazione standard o la normalizzazione dei valori in un set di dati. Ciò è utile per calcoli statistici o di trasformazione dei dati avanzati.

**Nel generatore di metriche calcolate**: applicare **Radice quadrata** a una metrica o espressione. Ad esempio: **Radice quadrata**(Varianza(*Ricavi*)) restituisce la deviazione standard di *Ricavi*.

>[!TIP]
>
>Da utilizzare quando è necessario scalare le metriche in modo proporzionale o per supportare altre funzioni statistiche che si basano sui valori radice.
>

## Deviazione standard {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="Deviazione standard"
>abstract="Restituisce la deviazione standard, o radice quadrata della varianza, in base a una popolazione di dati campione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL DEVIAZIONE STANDARD(metrica, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Restituisce la deviazione standard, o radice quadrata della varianza, in base a una popolazione di dati campione.

| Argomento | Descrizione |
|---|---|
| | Metrica per la quale desideri calcolare la deviazione standard. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |

**Caso d&#39;uso**: misura quanto valori variano rispetto alla media, ad esempio valutando la coerenza delle entrate giornaliere o delle visite nel tempo. Questo aiuta a identificare volatilità, stabilità o fluttuazioni insolite nelle prestazioni.

**Nel Generatore di metriche calcolate**: applica **Deviazione standard** a una metrica come *Ricavi* o *Sessioni* per calcolare la distribuzione dei valori all&#39;interno del raggruppamento o dell&#39;intervallo di date selezionato. Ad esempio: **Deviazione standard**(*Ricavi*) mostra il numero di ricavi giornalieri che si discostano dalla media.

>[!TIP]
>
>Utilizza con *Media* per rilevare anomalie o confrontare la coerenza delle prestazioni tra campagne, prodotti o segmenti.
>

## Varianza {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="Varianza"
>abstract="Restituisce la varianza in base a una popolazione di dati campione."

<!-- markdownlint-enable MD034 -->

![Effetto](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANZA(metrica, include_zeros)]**

[!BADGE Tabella]{type="Neutral"} Restituisce la varianza in base a una popolazione di dati campione.

| Argomento | Descrizione |
|---|---|
| metrica | Metrica per la quale desideri calcolare la varianza. |
| include_zeros | Specifica se includere o meno valori zero nei calcoli. |

**Caso d&#39;uso**: misura quanto i valori in un set di dati si distaccano dalla media, ad esempio analizzando il numero di entrate giornaliere o la durata della sessione che varia nel tempo. Questo consente di quantificare il grado di coerenza o fluttuazione nelle prestazioni.

**Nel Generatore di metriche calcolate**: Applica **Varianza** a una metrica come *Ricavi* o *Tempo trascorso per visita* per calcolare la deviazione media al quadrato dalla media. Ad esempio: **Varianza**(*Ricavi*) mostra quanto i valori dei ricavi differiscono dalla media nell&#39;intervallo selezionato.

>[!TIP]
>
>Usare con **Deviazione standard** per comprendere meglio la variabilità dei dati e identificare aree di prestazioni imprevedibili.
>

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

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers-that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

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