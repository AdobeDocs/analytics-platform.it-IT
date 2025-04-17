---
title: Operatori
description: Determina in che modo un componente interagisce con un valore all’interno di un segmento.
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters
role: User
source-git-commit: 716d6423c0cc8b91aa4951952191e0fd0e627c0f
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 23%

---

# Operatori

Il Generatore di filtri consente di confrontare e vincolare i valori per i componenti utilizzando gli operatori selezionati. Sono disponibili due categorie di operatori: [[!UICONTROL Standard]](#standard-operators) e [[!UICONTROL Distinct Count]](#distinct-count-operators).

## Operatori standard

| Operatore | Descrizione |
| --- | --- |
| **[!UICONTROL equals]** | Restituisce elementi che corrispondono esattamente a un valore numerico o stringa. Se utilizzi caratteri jolly, utilizza l’operatore matches. |
| **[!UICONTROL does not equal]** | Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore inserito.  Se utilizzi caratteri jolly, utilizza l’operatore non corrisponde a. |
| **[!UICONTROL equals any of]** | Restituisce tutti gli elementi che contengono la corrispondenza dei valori di sottostringa immessi, delimitati da una virgola. |
| **[!UICONTROL contains]** | Restituisce elementi paragonabili alle sottostringhe dei valori inseriti. Ad esempio, se il valore di una dimensione Nome pagina contiene `Search`, questo operatore corrisponde a qualsiasi pagina il cui nome contiene la sottostringa `Search`, inclusi `Search Results`, `Search` e `Searching`. Questo operatore distingue tra maiuscole e minuscole. |
| **[!UICONTROL does not contain]** | Tutti gli elementi che corrispondono al valore immesso vengono esclusi dai risultati. Ad esempio, se il valore di una dimensione Nome pagina non contiene `Search`, questo operatore esclude qualsiasi pagina il cui nome contiene la sottostringa `Search`, inclusi `Search Results`, `Search` e `Searching`. |
| **[!UICONTROL contains all of]** | Restituisce elementi che includono tutte le sottostringhe (separate da uno spazio) in qualsiasi ordine. Ad esempio, se si specifica `Search Results` come valore per questo operatore, verranno trovati `Search Results` e `Results of Search`, ma non `Search` o `Results` in modo indipendente. Questo operatore supporta fino a 100 parole delimitate da spazi. |
| **[!UICONTROL does not contain all of]** | Tutti gli elementi che corrispondono a ciascun valore inserito vengono esclusi dai risultati. Ad esempio, se si specifica `Search Results` come valore per questo operatore, verranno esclusi `Search Results` e `Results of Search`, ma non `Search` o `Results`. Questo operatore supporta fino a 100 parole delimitate da spazi. |
| **[!UICONTROL contains any of]** | Restituisce elementi che contengono una delle sottostringhe specificate. Ad esempio, se si specifica `Search Results` come valore per questo operatore, verranno trovate `Search Results`, `Results of Search`, `Search` e `Results`. Questo operatore supporta fino a 100 parole delimitate da spazi. |
| **[!UICONTROL does not contain any of]** | Tutti gli elementi che corrispondono a qualsiasi sottostringa vengono esclusi dai risultati. Ad esempio, se si specifica `Search Results` come valore per questo operatore, verranno esclusi `Search Results`, `Results of Search`, `Search` e `Results`. Questo operatore supporta fino a 100 parole delimitate da spazi. |
| **[!UICONTROL starts with]** | Restituisce elementi che iniziano con il carattere o le stringhe del valore specificato. |
| **[!UICONTROL does not start with]** | Restituisce tutti gli elementi che non iniziano con i caratteri o le stringhe del valore specificato. |
| **[!UICONTROL ends with]** | Restituisce elementi che terminano con il carattere o le stringhe del valore specificato. |
| **[!UICONTROL does not end with]** | Restituisce tutti gli elementi che non terminano con i caratteri o le stringhe del valore specificato. |
| **[!UICONTROL matches]** | Restituisce elementi che corrispondono esattamente a elementi basati su un valore numerico o stringa specificato. Supporta i caratteri jolly utilizzando un asterisco (`*`). Questo operatore distingue tra maiuscole e minuscole. Ad esempio:<ul><li>`a*e` corrisponde a `ae`, `abcde`, `adobe` e `a whole sentence`.</li><li>`adob*` corrisponde a `adobe`, `adobe analytics` e `adobo recipe`</li><li>`*dobe` corrisponde a `dobe`, `adobe` e `cute little dobe`.</li></ul> |
| **[!UICONTROL does not match]** | Tutti gli elementi che corrispondono alla stringa vengono esclusi. Supporta i caratteri jolly utilizzando un asterisco (`*`). |
| **[!UICONTROL exists]** | Restituisce gli elementi se il valore non è nullo. |
| **[!UICONTROL does not exist]** | Restituisce gli elementi se il valore è null. |

## Operatori di conteggio distinti

Puoi creare segmenti in base a un numero specifico di elementi all’interno di una dimensione. Ad esempio, puoi creare segmenti per le persone che hanno visualizzato più di 5 prodotti o visite distinti in cui sono state visualizzate più di 5 pagine distinte.

| Operatore | Descrizione |
| --- | --- |
| **[!UICONTROL equals]** | Restituisce elementi dimensionali il cui conteggio univoco è uguale al valore inserito. |
| **[!UICONTROL does not equal]** | Restituisce elementi dimensionali il cui conteggio univoco non è uguale al valore inserito. |
| **[!UICONTROL is greater than]** | Restituisce elementi dimensionali il cui conteggio univoco è maggiore del valore inserito. |
| **[!UICONTROL is less than]** | Restituisce elementi dimensionali il cui conteggio univoco è inferiore al valore inserito. |
| **[!UICONTROL is greater than or equal to]** | Restituisce elementi dimensionali il cui conteggio univoco è maggiore o uguale al valore inserito. |
| **[!UICONTROL is less than or equal to]** | Restituisce elementi dimensionali il cui conteggio univoco è minore o uguale al valore inserito. |
