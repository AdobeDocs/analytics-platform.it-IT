---
title: Uso di CJA con array di oggetti
description: Comprendere come il CJA crea rapporti sulle gerarchie di dati.
translation-type: tm+mt
source-git-commit: b7cd74f3fe2f0222e78452f58a7c387f6e0c86d2
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---


# Uso di CJA con array di oggetti

Alcuni schemi di piattaforma possono avere matrici di oggetti. Uno degli esempi più comuni sarebbe un carrello, che contiene più prodotti. Ogni prodotto ha un nome, uno SKU, una categoria, un prezzo, una quantità e qualsiasi altra dimensione da monitorare. Tutti questi facet hanno requisiti separati, ma devono rientrare tutti nello stesso hit.

Nelle versioni precedenti di Adobe  Analytics, questa operazione è stata eseguita utilizzando la `products` variabile. Era una stringa concatenata separata da punto e virgola (`;`) per separare facet di un prodotto, mentre virgole (`,`) prodotti delimitati. Era l&#39;unica variabile con supporto limitato di &quot;array di oggetti&quot;. Le variabili multivalore, come le variabili di elenco, potrebbero supportare l&#39;equivalente di array, ma non potevano supportare &quot;matrici di oggetti&quot;. CJA si espande su questo concetto sostenendo gerarchie arbitrariamente profonde all&#39;interno di una singola riga di dati, una funzione non disponibile in qualsiasi versione precedente di Adobe  Analytics.

## Stesso esempio

L&#39;hit seguente è un oggetto JSON che rappresenta un acquisto effettuato da un cliente di una lavatrice e di un essiccatore.

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

Quando si crea una visualizzazione dati, sono disponibili le dimensioni e la metrica seguenti (in base allo schema):

* **Dimensioni:**
   * ID
   * product : SKU
   * product : name
   * product : order_id
   * product : garanzia : cover
   * product : garanzia : length
   * product : garanzia : name
   * product : garanzia : type
* **Metriche:**
   * product : order
   * product : units
   * product : ricavo
   * product : garanzia
   * product : garanzia : ricavo

### Stessi esempi di hit (comportamento di reporting)

Utilizzando solo l’hit riportato sopra, le tabelle seguenti mostrano i rapporti Workspace con alcune combinazioni di dimensioni e metriche.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJA esamina in modo selettivo la dimensione e le metriche dell&#39;oggetto in base alla tabella.

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

Se desideri segnalare solo i ricavi della garanzia, il tuo progetto avrà un aspetto simile al seguente:

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

CJA esamina queste parti dell&#39;hit per generare il rapporto:

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

Poiché l&#39;asciugatrice non ha incluso una garanzia, non è inclusa nella tabella.

Dato che puoi combinare qualsiasi dimensione con qualsiasi metrica, la tabella seguente mostra come i dati verrebbero associati a valori di dimensione non specificati:

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Esiste un ordine di prodotto senza un nome di garanzia associato, pertanto il valore della dimensione è impostato su &#39;Non specificato&#39;. La stessa situazione si applica anche all&#39;ordine di garanzia del prodotto:

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
