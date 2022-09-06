---
title: Operatori di filtro
description: Determinare in che modo un componente interagisce con un valore all’interno di un filtro.
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
source-git-commit: a8b884148a197b081e321582f70a9188a1bdc51e
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 45%

---

# Operatori di filtro

Il Generatore di filtri consente di confrontare e vincolare i valori utilizzando gli operatori selezionati. Esistono due categorie di operatori: [!UICONTROL Standard] e [!UICONTROL Distinct Count].

## Operatori standard

| Operatore | Descrizione |
| --- | --- |
| è uguale a | Restituisce elementi che corrispondono esattamente a un valore numerico o stringa. Se utilizzi caratteri jolly, utilizza l’operatore &quot;corrisponde a&quot;. |
| non è uguale a | Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore inserito.  Se utilizzi caratteri jolly, utilizza l’operatore &quot;non corrisponde a&quot;. |
| è uguale a uno qualsiasi di | Restituisce tutti gli elementi che contengono la corrispondenza dei valori della sottostringa immessi, delimitati da una virgola. |
| contiene | Restituisce elementi paragonabili alle sottostringhe dei valori inseriti. Ad esempio, se la regola per una dimensione stringa contiene `"Search"`, corrisponde a qualsiasi pagina con la sottostringa `"Search"` in esso, compresi `"Search Results"`, `"Search"`e `"Searching"`. Questo operatore distingue tra maiuscole e minuscole. |
| non contiene | Tutti gli elementi che corrispondono al valore immesso vengono esclusi dai risultati. Ad esempio, se la regola per una dimensione stringa non contiene `"Search"`, esclude qualsiasi pagina con la sottostringa `"Search"` in esso, compresi `"Search Results"`, `"Search"`e `"Searching"`. |
| contiene tutti | Restituisce elementi che includono tutte le sottostringhe (separate da uno spazio) in qualsiasi ordine. Ad esempio, immettendo `"Search Results"` con questo operatore corrisponde `"Search Results"` e `"Results of Search"`, ma non `"Search"` o `"Results"` indipendentemente. Questo operatore supporta fino a 100 parole delimitate da spazi. |
| non contiene tutti | Tutti gli elementi che corrispondono a ciascun valore immesso vengono esclusi dai risultati. Ad esempio, immettendo `"Search Results"` con questo operatore escluderebbe `"Search Results"` e `"Results of Search"`, ma non `"Search"` o `"Results"`. Questo operatore supporta fino a 100 parole delimitate da spazi. |
| contiene alcuni | Restituisce elementi che contengono una qualsiasi delle sottostringhe specificate. Ad esempio, immettendo `"Search Results"` con questo operatore corrisponde `"Search Results"`, `"Results of Search"`, `"Search"`e `"Results"`. Questo operatore supporta fino a 100 parole delimitate da spazi. |
| non contiene nessuno | Tutti gli elementi che corrispondono a una sottostringa sono esclusi dai risultati. Ad esempio, immettendo `"Search Results"` escluderei `"Search Results"`, `"Results of Search"`, `"Search"`e `"Results"`. Questo operatore supporta fino a 100 parole delimitate da spazi. |
| inizia con | Restituisce elementi che iniziano con il carattere o le stringhe del valore inserito. |
| non inizia con | Restituisce tutti gli elementi che non iniziano con i caratteri o le stringhe dei valori inseriti. |
| termina con | Restituisce elementi che terminano con il carattere o le stringhe del valore inserito. |
| non termina con | Restituisce tutti gli elementi che non terminano con i caratteri o le stringhe del valore inserito. |
| corrisponde | Restituisce elementi che contengono una corrispondenza esatta in base a un dato valore numerico o stringa. Supporta i caratteri jolly utilizzando un asterisco (`*`). Questo operatore distingue tra maiuscole e minuscole. Ad esempio:<ul><li>`a*e` corrisponde `ae`, `abcde`, `adobe`e `a whole sentence`.</li><li>`adob*` corrisponde `adobe`, `adobe analytics`e `adobo recipe`</li><li>`*dobe` corrisponde `dobe`, `adobe`e `cute little dobe`.</li></ul> |
| non corrisponde | Vengono esclusi tutti gli elementi che corrispondono alla stringa. Supporta i caratteri jolly utilizzando un asterisco (`*`). |
| esiste | Restituisce elementi se il valore non è nullo. |
| non esiste | Restituisce elementi se il valore è null. |

## Operatori di conteggio distinti

Puoi creare segmenti in base a un numero specifico di elementi all’interno di una dimensione. Ad esempio, puoi creare filtri per i visitatori che hanno visualizzato più di 5 prodotti distinti o per le visite in cui sono state visualizzate più di 5 pagine distinte.

| Operatore | Descrizione |
| --- | --- |
| è uguale a | Restituisce elementi dimensionali il cui conteggio univoco è uguale al valore inserito. |
| non è uguale a | Restituisce elementi dimensionali il cui conteggio univoco non è uguale al valore inserito. |
| è maggiore di | Restituisce elementi dimensionali il cui conteggio univoco è maggiore del valore inserito. |
| è minore di | Restituisce elementi dimensionali il cui conteggio univoco è inferiore al valore inserito. |
| è maggiore o uguale a | Restituisce elementi dimensionali il cui conteggio univoco è maggiore o uguale al valore inserito. |
| è minore o uguale a | Restituisce elementi dimensionali il cui conteggio univoco è minore o uguale al valore inserito. |
