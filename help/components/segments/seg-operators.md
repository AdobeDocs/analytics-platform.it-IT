---
description: Scopri come utilizzare gli operatori nel generatore di segmenti per confrontare e vincolare i valori.
title: Operatori
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters, Segments
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 35%

---

# Operatori

Il Generatore di segmenti consente di confrontare e vincolare i valori per i componenti utilizzando gli operatori selezionati. Sono disponibili tre categorie di operatori: [Standard](#standard-operators), [Data Warehouse](#data-warehouse-operators) e [Conteggio valori univoci](#distinct-count-operators).

A seconda dell’operatore selezionato:

* È possibile immettere un valore.
* È possibile immettere parte di un valore e selezionare da un menu a discesa (se disponibile).
* Seleziona immediatamente un valore dal menu a discesa (se disponibile).

Quando digiti un valore per un operatore che convalida i valori disponibili, come **[!UICONTROL è uguale a]**, e il valore non corrisponde ai valori disponibili per il componente, viene visualizzata l&#39;icona ![AlertRed](/help/assets/icons/AlertRed.svg). È possibile selezionare un valore dal menu a discesa oppure premere **[!UICONTROL _Invio_]** per immettere il valore.

![Segmento uguale a](assets/segment-operator-equals.png)

## Caratteri jolly

L&#39;unico carattere jolly supportato per gli operatori che supportano i caratteri jolly è l&#39;asterisco: `*`. Se devi cercare il carattere &#42; specifico, puoi eseguirne l&#39;escape con una barra rovesciata, ad esempio `\*`.

Ad esempio, hai un nome di pagina denominato *My cool product*.

* La regola del segmento **[!UICONTROL Nome pagina]** **[!UICONTROL corrisponde]** `* product` corrisponderà al nome della pagina indicato sopra.
* Tuttavia, la regola **[!UICONTROL Nome pagina]** **[!UICONTROL corrisponde]** `My \* product` corrisponde solo al nome pagina *Il mio * Prodotto*.

## Operatori standard

| Operatore | L’evento di dimensione, segmento o metrica selezionato... |
|--- |--- |
| **[!UICONTROL è uguale a]** | Restituisce elementi che corrispondono esattamente a un valore numerico o stringa. Nota: se utilizzi caratteri jolly, utilizza l&#39;operatore **[!UICONTROL matches]**. |
| **[!UICONTROL è diverso da]** | Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore inserito.  Nota: se utilizzi caratteri jolly, usa l&#39;operatore **[!UICONTROL non corrisponde]**. |
| **[!UICONTROL è uguale a qualsiasi di]** | Restituisce elementi che corrispondono esattamente a qualsiasi valore nel campo di input (fino a 500 elementi). Ad esempio, l&#39;immissione di `Search Results, Homepage` per la dimensione **[!UICONTROL Nome pagina]** con questo operatore corrisponderebbe a *Risultati ricerca* e *Home page* e verrebbe conteggiata come 2 elementi. Il campo di input per questo operatore è delimitato da virgole. |
| **[!UICONTROL non è uguale a nessuno di]** | Identifica gli elementi che corrispondono esattamente a qualsiasi valore nel campo di input (fino a 500 elementi) e restituisce solo gli elementi senza questi valori. Ad esempio, l&#39;immissione di `Search Results, Homepage` con questo operatore per la dimensione **[!UICONTROL Nome pagina]** identificherebbe *Risultati ricerca* e *Home page*, quindi **escluderli** dagli elementi restituiti. In questo esempio vengono conteggiati 2 elementi. Il campo di input per questo operatore è delimitato da virgole. |
| **[!UICONTROL contiene]** | Restituisce elementi paragonabili alle sottostringhe dei valori inseriti. Ad esempio, se la regola è **[!UICONTROL Nome pagina]** **[!UICONTROL contiene]** `Search`, questa regola corrisponderà a qualsiasi pagina contenente la sottostringa `Search`, inclusi *Risultati ricerca*, *Ricerca* e *Ricerca in corso*. La clausola &quot;contains&quot; non distingue tra maiuscole e minuscole in Adobe Analytics, ma in Customer Journey Analytics distingue tra maiuscole e minuscole. |
| **[!UICONTROL non contiene]** | Restituisce l&#39;inverso della regola **[!UICONTROL contains]**. Nello specifico, tutti gli elementi che corrispondono al valore inserito verranno esclusi dai valori inseriti. Ad esempio, se la regola è **[!UICONTROL Nome pagina]** **[!UICONTROL non contiene]** `Search`, non corrisponderà ad alcuna pagina contenente la sottostringa `Search`, inclusi *Risultati ricerca*, *Ricerca* e *Ricerca*. Questi valori verranno esclusi dai risultati. |
| **[!UICONTROL contiene tutti]** | Restituisce gli elementi confrontati con le sottostringhe, compresi più valori uniti tra loro. Ad esempio, l&#39;immissione di `Search Results` con questo operatore per la dimensione **[!UICONTROL Nome pagina]** corrisponde a *Risultati ricerca* e *Risultati ricerca*, ma non a *Ricerca* o *Risultati* singolarmente. La regola corrisponderebbe a *Ricerca* E *Risultati* trovati insieme. Il campo di input per questo operatore è delimitato da spazi (100 parole). |
| **[!UICONTROL non contiene tutti]** | Identifica gli elementi confrontati con le sottostringhe, compresi più valori uniti tra loro, e restituisce solo gli elementi senza questi valori. Ad esempio, l&#39;immissione di `Search Results` con questo operatore per la dimensione **[!UICONTROL Nome pagina]** identificherebbe *Risultati ricerca* e *Risultati ricerca* (ma non *Ricerca* o *Risultati* singolarmente) e quindi escluderebbe questi elementi. Il campo di input per questo operatore è delimitato da spazi (100 parole). |
| **[!UICONTROL contiene uno di]** | Restituisce gli elementi confrontati con le sottostringhe, compresi più valori uniti o identificati in modo indipendente. Ad esempio, l&#39;immissione di `Search Results` con questo operatore corrisponde a *Risultati ricerca*, *Risultati ricerca*, *Ricerca* e *Risultati*. Corrisponderebbe a *Ricerca* O *Risultati* trovati insieme o in modo indipendente. Il campo di input per questo operatore è delimitato da spazi (100 parole). |
| **[!UICONTROL non contiene nessuno di]** | Identifica gli elementi in base alle sottostringhe e restituisce valori che non contengono tali sottostringhe. Può avere più valori uniti o valori identificati in modo indipendente. Ad esempio, l&#39;immissione di `Search Results` per la dimensione **[!UICONTROL Nome pagina]** corrisponderebbe a *Risultato ricerca* s, *Risultati ricerca*, *Ricerca* e *Risultati* in cui *Ricerca* o *Risultato* vengono trovati insieme o in modo indipendente. Gli elementi che contengono tali sottostringhe vengono poi esclusi. Il campo di input per questo operatore è delimitato da spazi (100 parole). |
| **[!UICONTROL inizia con]** | Restituisce elementi che iniziano con il valore stringa inserito. |
| **[!UICONTROL non inizia con]** | Restituisce tutti gli elementi che non iniziano con il valore stringa inserito. L&#39;inverso dell&#39;operatore **[!UICONTROL inizia con]**. |
| **[!UICONTROL termina con]** | Restituisce elementi che terminano con il valore stringa immesso. |
| **[!UICONTROL non termina con]** | Restituisce tutti gli elementi che non terminano con il valore stringa inserito. Si tratta dell&#39;inverso dell&#39;operatore **[!UICONTROL termina con]**. |
| **[!UICONTROL corrispondenze]** | Restituisce elementi che contengono una corrispondenza esatta in base a un dato valore numerico o stringa. La clausola **[!UICONTROL matches]** fa distinzione tra maiuscole e minuscole in Adobe Analytics e Customer Journey Analytics. **Nota**: utilizza questo operatore quando utilizzi le funzionalità [jolly](#wildcards) (globbing). Esempi di globbing:<ul><li>`a*e` corrisponde a `ae`, `abcde`, `adobe` e `a whole sentence`</li><li>`adob*` corrisponde a `adobe`, `adobe analytics` e `adobo recipe`</li><li>`*dobe` corrisponde a `dobe`, `adobe` e `cute little dobe`</li></ul> |
| **[!UICONTROL non corrisponde]** | Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore inserito. Nota: utilizza questo operatore quando utilizzi le funzionalità [caratteri jolly](#wildcards) (globbing). |
| **[!UICONTROL esiste]** | Restituisce il numero di elementi esistenti. Ad esempio, se valuti la dimensione **[!UICONTROL Pagine non trovate]** utilizzando l&#39;operatore **[!UICONTROL exists]**, viene restituito il numero di pagine di errore esistenti. |
| **[!UICONTROL non esiste]** | Restituisce tutti gli elementi che non esistono. Ad esempio, se valuti la dimensione **[!UICONTROL Pagine non trovate]** utilizzando l&#39;operatore **[!UICONTROL does not exist]**, viene restituito il numero di pagine in cui la pagina di errore non esiste. |

## Operatori Data Warehouse

| Operatore | L’evento di dimensione, segmento o metrica selezionato... |
| --- | --- |
| **[!UICONTROL è minore di]** | Restituisce elementi il cui conteggio numerico è inferiore al valore inserito. |
| **[!UICONTROL è minore di o uguale a]** | Restituisce elementi il cui conteggio numerico è minore o uguale al valore inserito. |
| **[!UICONTROL è maggiore di]** | Restituisce elementi il cui conteggio numerico è maggiore del valore inserito. |
| **[!UICONTROL è maggiore o uguale a]** | Restituisce elementi il cui conteggio numerico è maggiore di o uguale al valore inserito. |

## Operatori di conteggio distinti

Puoi creare segmenti in base a un numero specifico di elementi all’interno di una dimensione. Esempi: *Visitatori che hanno visualizzato più di 5 prodotti distinti* o *Visite in cui sono state visualizzate più di 5 pagine distinte*.

| Operatore | L’evento di dimensione, segmento o metrica selezionato... |
| --- | --- |
| **[!UICONTROL è uguale a]** | Restituisce elementi dimensionali il cui conteggio univoco è uguale al valore inserito. |
| **[!UICONTROL è diverso da]** | Restituisce elementi dimensionali il cui conteggio univoco non è uguale al valore inserito. |
| **[!UICONTROL è maggiore di]** | Restituisce elementi dimensionali il cui conteggio univoco è maggiore del valore inserito. |
| **[!UICONTROL è minore di]** | Restituisce elementi dimensionali il cui conteggio univoco è inferiore al valore inserito. |
| **[!UICONTROL è maggiore o uguale a]** | Restituisce elementi dimensionali il cui conteggio univoco è maggiore o uguale al valore inserito. |
| **[!UICONTROL è minore di o uguale a]** | Restituisce elementi dimensionali il cui conteggio univoco è minore o uguale al valore inserito. |


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Conteggi dimensioni distinti](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/components/calculated-metrics/approximate-count-distinct-function-in-calculated-metrics){target="_blank"}.

>[!ENDSHADEBOX]
