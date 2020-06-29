---
title: Uso di array di oggetti
description: Comprendere come CJA crea rapporti sulle gerarchie di dati.
translation-type: ht
source-git-commit: 52fecf03cc503fa59101f6280c671e153e2129e9
workflow-type: ht
source-wordcount: '420'
ht-degree: 100%

---


# Uso di array di oggetti

Alcuni schemi di piattaforma possono avere array di oggetti. Uno degli esempi più comuni è un carrello, che può contenere più prodotti. Ogni prodotto ha un nome, uno SKU, una categoria, un prezzo, una quantità e altre dimensioni che è possibile monitorate. Questi facet hanno requisiti separati, ma devono rientrare tutti nello stesso hit.

Nelle versioni precedenti di Adobe Analytics, questa funzione è stata eseguita utilizzando la variabile `products`. Si trattava di una stringa concatenata in cui i punti e virgola (`;`) separavano i facet di un prodotto, mentre le virgole (`,`) delineavano i prodotti. Era l’unica variabile con supporto limitato di “array di oggetti”. Le variabili multivalore, come le variabili di elenco, erano in grado di supportare l’equivalente degli array, ma non gli “array di oggetti”. CJA amplia questo concetto con il supporto di gerarchie arbitrariamente profonde all’interno di una singola riga di dati, una funzione non disponibile nelle versioni precedenti di Adobe Analytics.

## Stesso esempio di hit

L’hit seguente è un oggetto JSON che rappresenta un acquisto effettuato da un cliente di una lavatrice e di un’asciugatrice.

```json
{
  "ID": "1", 
  "product": [
    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
  ], 
  "timestamp": 1534219229
}
```

Quando si crea una visualizzazione dati, sono disponibili le dimensioni e le metriche seguenti (in base allo schema):

* **Dimensioni:**
   * ID
   * product : SKU
   * product : name
   * product : order_id
   * product : warranty : coverage
   * product : warranty : length
   * product : warranty : name
   * product : warranty : type
* **Metriche:**
   * product : orders
   * product : units
   * product : revenue
   * product : warranty
   * product : warranty : revenue

### Stessi esempi di hit (comportamento di reporting)

Utilizzando solo l’hit riportato sopra, le tabelle seguenti mostrano i rapporti Workspace con alcune combinazioni di dimensioni e metriche.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJA esamina in modo selettivo le dimensioni e le metriche dell’oggetto in base alla tabella.

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
+      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
+      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
+      "name": "LG Dryer 2000", 
+      "orders": 1, 
+      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Se desideri creare un rapporto solo sui ricavi della garanzia, il tuo progetto avrà un aspetto simile al seguente:

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

CJA esamina queste parti dell’hit per generare il rapporto:

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
+          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
+          "revenue": 200
+        }, 
+        {
+          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
+          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
+  ], 
+  "timestamp": 1534219229
+}
```

Poiché l’asciugatrice non includeva una garanzia, non è stata inserita nella tabella.

Dato che è possibile combinare qualsiasi dimensione con qualsiasi metrica, la tabella seguente illustra i dati che emergerebbero nel caso di valori di dimensione non specificati:

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Un ordine di prodotto esiste senza un nome di garanzia associato, pertanto il valore della dimensione è impostato su “Non specificato”. La stessa situazione si applica anche all’ordine di garanzia del prodotto:

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
          "coverage": "full coverage", 
          "length": "2 year", 
+          "name": "LG 2000 standard", 
+          "orders": 1, 
          "revenue": 200
+        }, 
+        {
          "coverage": "extended", 
          "length": "1 year", 
+          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
+      "orders": 1, 
      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Prendi nota degli ordini ai quali non è associato un nome. Si tratta degli ordini attribuiti al valore della dimensione “Non specificato”.

### Combinazione di metriche

CJA non combina in modo nativo metriche con nomi simili se si trovano su diversi livelli dell’oggetto.

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

Tuttavia, è possibile creare una metrica calcolata che combini le metriche desiderate:

Metrica calcolata “Entrate totali”: `[product : revenue] + [product : warranty : revenue]`

L’applicazione di questa metrica calcolata mostra i risultati desiderati:

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |

## Esempi di persistenza

