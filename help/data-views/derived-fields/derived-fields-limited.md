---
title: Campi derivati
description: Un campo derivato specifica la manipolazione in fase di report dei campi dello schema e/o dei componenti standard tramite un set di funzioni e modelli di funzioni disponibili.
solution: Customer Journey Analytics
feature: Derived Fields
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 1b81b0fb81119132b6568726761e9897c2b4e47c
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 24%

---


# Campi derivati (test limitato){#derived-fields}

{{release-limited-testing}}

>[!IMPORTANT]
>
>Questa è una documentazione preliminare di nuove funzioni derivate sul campo che non sono ancora generalmente disponibili. Utilizzare queste informazioni per informazioni sulle nuove funzioni dei campi derivati. Questa documentazione è ancora soggetta a modifiche e non è possibile derivare alcun obbligo legale dalla versione corrente di questo articolo.
>&#x200B;><br/>Consulta [Campi derivati](derived-fields.md) per informazioni sulle funzionalità dei campi derivati in generale e sulle funzioni e i modelli di funzioni attualmente disponibili.
>

## Riferimento funzione

{{select-package}}

Per ciascuna funzione supportata, di seguito trovi i dettagli su:

- specifiche:
   - tipo di dati di input: tipo di dati supportati,
   - input: possibili valori di input,
   - operatori inclusi: operatori supportati per questa funzione (se presenti),
   - limitazioni: limitazioni applicabili a questa funzione specifica,
   - output

- casi d’uso, tra cui:
   - (facoltativo) dati prima di definire il campo derivato,
   - come definire il campo derivato,
   - (facoltativo) dati dopo la definizione del campo derivato.

- vincoli (se applicabili).



<!-- DATE MATH -->

### Matematica data {#datemath}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_datemath"
>title="Matematica data"
>abstract="Questa funzione consente di restituire la differenza tra due campi data o data-ora."

Restituisce la differenza tra due campi data-ora o data-ora.

+++ Dettagli

## Specifiche {#datemath-io}

| Tipo di dati di input | Input | Operatori inclusi | Limitazioni | Output |
|---|---|---|---|---|
| <ul><li>Data</li><li>Data e ora</li></ul> | <ul><li>[!UICONTROL Scope]<ul><li>Evento</li><li>Sessione</li><li>Persona</li></ul></li><li>[!UICONTROL Value]:<ul><li>Data</li><li>Data-ora</li><li>Data statica (immessa dall&#39;utente)</li><li>Data-ora statica (immessa dall&#39;utente)</li><li>Data dinamica<ul><li>Oggi</li></ul></li><li>Data-ora dinamica<ul><li>Ora</li></ul></li></ul></li><li>[!UICONTROL Granularity]:<ul><li>Seconds</li><li>Minutes</li><li>Ore</li><li>Days</li><li>Weeks</li><li>Months</li><li>trimestri</li><li>Anni</li></ul></li><li>Per ogni ritorno data o data-ora:<ul><li>Primo (all’interno della sessione o della persona)</li><li>Ultimo (entro sessione o persona)</li></ul></li></ul> | <p>N/D</p> | <p>2 funzioni per campo derivato</p> | <p>Nuovo campo derivato</p> |

{style="table-layout:auto"}


## Caso d’uso 1 {#datemath-uc1}

In qualità di analista di marketing di una società alberghiera, vorresti comprendere la differenza del numero di giorni tra le date di check-in dei clienti e le date di prenotazione nell’ultima settimana.


### Campo derivato {#datemath-uc1-derivedfield}

Definisci un campo derivato `Days between booking and check-in`. Utilizzare la funzione [!UICONTROL DATE MATH] per definire una regola per calcolare i giorni per [!UICONTROL Scope] [!DNL Person] tra [!UICONTROL Booking Date] e [!UICONTROL Check-in Date]. Si seleziona [!UICONTROL Day] come [!UICONTROL Output granularity]. Selezionare [!UICONTROL Return the last] sia per [!UICONTROL Booking Date] che per [!UICONTROL Check-in Date] per assicurarsi che nel calcolo venga utilizzato il valore con ambito dell&#39;ultima persona.

![Schermata della regola di data matematica](assets/datemath-1.png)


## Caso d’uso 2 {#datemath-uc2}

Come analista di marketing di un negozio di mattoni e malta si vuole capire quanti giorni fa è stata l&#39;ultima visita di un cliente al negozio. Puoi utilizzare la funzionalità di geolocalizzazione all’interno di un’app mobile e dei beacon nel negozio per acquisire le visite fisiche dei clienti.

### Campo derivato {#datemath-uc2-derivedfield}

Definisci un nuovo campo derivato `Days Since Visit To Shop`. Utilizzare la funzione [!UICONTROL DATE MATH] per definire una regola per calcolare i giorni tra una data-ora personalizzata (specificata in [!UICONTROL Date]) e il [!UICONTROL Local Time] (dal gruppo di campi [!UICONTROL placeContext] del set di dati evento) con un [!UICONTROL Deduplication scope] di [!UICONTROL Person]. Selezionare [!UICONTROL Return the last] per assicurarsi che nel calcolo venga utilizzato il valore con ambito dell&#39;ultima persona per [!UICONTROL Local time]. Si seleziona Giorno come [!UICONTROL Output granularity].

![Schermata della regola di data matematica 2](assets/datemath-2.png)


## Caso d’uso 3 {#datemath-uc3}

Desideri comprendere il tempo di ricerca in minuti prima che un cliente all’interno di una sessione effettui un ordine.

Si definisce un nuovo campo derivato `Time Between Search And Order In Minutes` che è il risultato di due [[!UICONTROL CASE WHEN] funzioni](#case-when) per definire i valori [!UICONTROL Search Time] e [!UICONTROL Order Time].
Utilizzare quindi questi due valori per calcolare la differenza con una funzione [!UICONTROL DATE MATH] con [!UICONTROL Scope] impostato su [!UICONTROL Session], valori impostati su [!UICONTROL Search Time] e [!UICONTROL Order Time] e [!UICONTROL Output granularity] impostato su [!UICONTROL Minute]. Per entrambi i valori, selezionare [!UICONTROL Return the first] per assicurarsi che vengano restituiti i primi [!UICONTROL Search Time] e [!UICONTROL Order Time].

![Schermata della regola di data matematica 3](assets/datemath-3.png)



<!--
| Visitor ID | Marketing Channel | Events |
|----|---|---:|
| ABC123 | paid search | 1 |
| DEF123 | email | 1 |
| JKL123 | natural search | 1 |

{style="table-layout:auto"}

-->

+++



<!-- DEPTH -->

### Profondità {#depth}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_depth"
>title="Profondità"
>abstract="Questa funzione consente di restituire la profondità di qualsiasi campo, in modo analogo alla funzionalità del componente standard relativo alla profondità di un evento."

Restituisce la profondità di un campo, in modo simile a quanto è possibile ottenere con la dimensione predefinita [Profondità evento standard](/help/components/dimensions/overview.md#standard-dimensions).

+++ Dettagli

## Specifiche {#depth-io}

| Tipo di dati di input | Input | Operatori inclusi | Limitazioni | Output |
|---|---|---|---|---|
| Qualsiasi | Qualsiasi campo | N/D | 3 funzioni per campo derivato | Nuovo campo derivato |

{style="table-layout:auto"}


<!--
## Example Data {#depth-example}

| event# | page name | search | product view | cart add  | order |
|:---:|---|:---:|:---:|:---:|:---:|
| 1 |  home page        |  0  | 0  | 0  | 0 |
| 2 |  search page      |  1  | 0  | 0  | 0 |
| 3 |  product page     |  0  | 0  | 0  | 0 |
| 4 |  cart page        |  0  | 0  | 1  | 0 |
| 5 |  confirmation     |  0  | 0  | 0  | 1 |

-->

## Caso d’uso {#depth-uc1}

Desideri comprendere la profondità della ricerca (che puoi anche interpretare come il numero di ricerche). Puoi quindi utilizzare tale profondità di ricerca in un secondo momento per cercare il termine associato a una profondità di ricerca specifica.


### Campo derivato {#depth-uc1-derivedfield}

Definisci un nuovo campo derivato `Search Depth`. Utilizzare la funzione [!UICONTROL DEPTH] per definire una regola per recuperare la profondità di [!UICONTROL Search] e archiviarla in un nuovo campo derivato.

![Schermata della regola di profondità](assets/depth-1.png)

+++


<!-- TYPECASE -->

### Typecast {#typecast}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_typecast"
>title="Typecast"
>abstract="Questa funzione consente di modificare istantaneamente il tipo di campo, al fine di renderlo disponibile per ulteriori trasformazioni in Customer Journey Analytics."

Modifica il tipo di campo di un campo per renderlo disponibile per ulteriori trasformazioni in Customer Journey Analytics.

+++ Dettagli

## Specifiche {#typecast-io}

| Tipo di dati di input | Input | Operatori inclusi | Limite | Output |
|---|---|---|---|---|
| <ul><li>Numerici</li><li>Data</li><li>Data e ora</li><li>Stringa</li></ul> | <ul><li>[!UICONTROL Field] | <p><ul><li>Intero<ul><li>Alla Stringa <strong>(Deve)</strong></li></ul></li><li>Doppio<ul><li>Alla Stringa <strong>(Deve)</strong><ul><li>Includi numero di posizioni decimali da ereditare (massimo 5?)</li></ul></li><li>Al numero intero <strong>(dovrebbe)</strong></li></ul></li><li>Byte<ul><li>Alla Stringa <strong>(Deve)</strong></li></ul></li><li>Lungo<ul><li>Alla Stringa <strong>(Deve)</strong></li></ul></li><li>Data<ul><li>Alla Stringa <strong>(Deve)</strong><ul><li>Consente di definire il formato di output</li></ul></li><li>Esempi<ul><li>Data (esempio del 7 gennaio 2025)<ul><li data-stringify-indent="1" data-stringify-border="0">DD/MM/YY<ul><li data-stringify-indent="2" data-stringify-border="0">Esempio: 01-07-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">Esempio: 01-07-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">GG-MM-AA<ul><li data-stringify-indent="2" data-stringify-border="0">Esempio: 07-01-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">GG-MM-AAAA<ul><li data-stringify-indent="2" data-stringify-border="0">Esempio: 07-01-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/YY<ul><li data-stringify-indent="2" data-stringify-border="0">Esempio: 25-01-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">Esempio: 07/01/2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">GG/MM/AA<ul><li data-stringify-indent="2" data-stringify-border="0">Esempio: 01/07/25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">GG/MM/AAAA<ul><li data-stringify-indent="2" data-stringify-border="0">Esempio: 01/07/2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">AAAA/MM/GG<ul><li data-stringify-indent="2" data-stringify-border="0">Esempio: 2025/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">AA/MM/GG<ul><li data-stringify-indent="2" data-stringify-border="0">Esempio: 25/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD MMM YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">Esempio: mercoledì 7 gennaio 2025</li></ul></li></ul></li></ul></li></ul></li><li>Data e ora<ul><li>Alla Stringa <strong>(Deve)</strong><ul><li>Consente di definire il formato di output</li></ul></li><li>Esempi<ul><li data-stringify-indent="0" data-stringify-border="0">Data-ora (esempio del 7 gennaio 2025 a 1:30pm, 52 secondi)<ul><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Esempio: 01-07-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Esempio: 01-07-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Esempio: 07-01-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Esempio: 07-01-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Esempio: 25-01-07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Esempio: 07/01/2025 13/0&rbrace;52:30:</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Esempio: 01/07/25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Esempio: 01/07/2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">AAAA/MM/GG hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Esempio: 2025/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">AA/MM/GG hh:mm :ss<ul><li data-stringify-indent="3" data-stringify-border="0">Esempio: 25/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD MMM YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Esempio: 7 gennaio 2025 13:30:52</li></ul></li></ul></li></ul></li><li>Stringa<ul><li>Al Numerico <strong>(Dovrebbe)</strong><ul><li>Se i valori non sono numerici, restituiranno null.</li><li>Sarà necessario immettere la precisione e la lingua da utilizzare. </li></ul></li></ul></li></ul></li></ul></p> | <p>3 funzioni per campo derivato</p> | <p>Nuovo campo derivato</p> |

{style="table-layout:auto"}


## Caso d’uso 1 {#typecast-uc1}

Hai un campo intero, altezza schermo (ad esempio device.screenHeight dal set di dati dell’evento), che desideri utilizzare come dimensione basata su stringhe.


### Campo derivato {#typecast-uc1-derivedfield}

Definisci un campo derivato `Screen Height`. Utilizzare la funzione [!UICONTROL TYPECAST] per definire una regola per [!UICONTROL Typecast to] [!UICONTROL String] il campo [!UICONTROL Screen height] e archiviarlo nel nuovo campo derivato.

![Schermata della regola Typecast 1](assets/typecast-1.png)



## Caso d’uso 2 {#typecast-uc2}

Si desidera utilizzare i ricavi in una tabella coorte (che supporta solo i numeri interi), ma il campo Ricavi è di tipo Double.

![Schermata della regola Typecast 2](assets/typecast-2.png)


### Campo derivato {#typecast-uc2-derivedfield}

Definisci un campo derivato `Revenue (integer)`. Utilizzare la funzione [!UICONTROL TYPECAST] per definire una regola per [!UICONTROL Typecast to] [!UICONTROL Integer] il campo [!UICONTROL Revenue] e archiviarlo nel nuovo campo derivato.


+++
