---
title: Come funziona l’unione
description: Comprendere il concetto di unione
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 506838a0-0fe3-4b5b-bb9e-2ff20feea8bc
source-git-commit: 8ca11b37ebda952d95ae38473a9c0d62be007e79
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 21%

---

# Come funziona l’unione

L’unione esegue almeno due passaggi sui dati in un determinato set di dati:

* **Unione live**: tenta di unire ogni hit (evento) nel momento in cui arriva. Gli hit da dispositivi che sono &quot;nuovi&quot; al set di dati (non sono mai stati autenticati) in genere non vengono uniti a questo livello. Gli hit da dispositivi già riconosciuti vengono uniti immediatamente.

* **Ripeti unione**: &quot;riproduce&quot; i dati in base a identificatori univoci (ID transitori) appresi. In questa fase vengono uniti gli hit da dispositivi precedentemente sconosciuti (ID persistenti) (a ID transitori). Adobe offre due intervalli di ripetizione:
   * **Giornaliero**: i dati vengono riprodotti ogni giorno con un intervallo di lookback di 24 ore. Questa opzione offre un vantaggio in quanto le ripetizioni sono molto più frequenti, ma i visitatori non autenticati devono autenticarsi lo stesso giorno in cui visitano il sito.
   * **Ogni settimana**: i dati vengono ripetuti una volta alla settimana con un intervallo di lookback di 7 giorni. Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di una settimana non vengono rielaborati fino alla successiva riproduzione settimanale.

* **Privacy (facoltativo)**: quando vengono ricevute richieste relative alla privacy, oltre a rimuovere l’identità richiesta, qualsiasi unione di tale identità tra eventi non autenticati deve essere annullata.

I dati oltre l’intervallo di lookback non vengono riprodotti. Un visitatore deve effettuare l’autenticazione all’interno di un intervallo di lookback specificato perché una visita non autenticata e una visita autenticata siano identificate insieme. Una volta riconosciuto, il dispositivo è live stitched da quel momento in poi.

## Passaggio 1: live stitching

L’unione live tenta di unire ogni evento al momento della raccolta su dispositivi e canali noti. Prendi in considerazione l’esempio seguente, in cui Bob registra eventi diversi come parte di un set di dati evento.

*Dati visualizzati nel giorno in cui vengono raccolti:*

| Evento | Marca temporale | ID persistente (ID cookie) | ID transitorio (ID accesso) | ID unione (dopo unione live) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **246** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | |
| 7 | 2023-05-12 12:07 | 246 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 10 | 2023-05-12 12:02 | 81911 ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **81911** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** |
| | | **3 dispositivi** | | **4 persone**:<br/>246, Bob, 3579, 81911 |

Gli eventi non autenticati e autenticati sui nuovi dispositivi vengono conteggiati come persone separate (temporaneamente). Gli eventi non autenticati sui dispositivi riconosciuti sono live stitched.

L’attribuzione funziona quando la variabile personalizzata di identificazione si collega a un dispositivo. Nell’esempio precedente, tutti gli eventi ad eccezione di 1, 8, 9 e 10 sono live stitched (utilizzano tutti `Bob` identificatore). L’unione live &quot;risolve&quot; l’ID unione per gli eventi 4, 6 e 12.


<!--

### Delayed data

When incoming data for 'Live' stitching is delayed and over 24 hours old, and when no identities in that delayed data can be matched against identities already considered for 'Live' stitching, that delayed data is not added to the data considered for 'Live' stitching.

In the example below, the data in event 2 is delayed but will be part of 'Live' stitching.

| Event | Timestamp | Persistent ID (Cookie ID) | Transient ID (Login ID) | Stitched ID (after live stitch) | 
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg)| - | **246** |
| 2 | 2023-05-14 12:02 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |

In the example below, the data in event 2 is delayed and will NOT become part of 'Live' stitching.

| Event | Timestamp | Persistent ID (Cookie ID) | Transient ID (Login ID) | Stitched ID (after live stitch) | 
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg)| - | **246** |
| ~~2~~ | ~~2023-05-14 12:02~~ | ~~891~~ |  | (not considered for 'Live' stitching) |

-->


## Passaggio 2: ripetere l’unione

A intervalli regolari (una volta alla settimana o una volta al giorno, a seconda dell’intervallo di lookback scelto), la ripetizione dell’unione ricalcola i dati storici in base ai dispositivi riconosciuti. Se un dispositivo invia inizialmente i dati mentre non è autenticato e poi effettua l’accesso, la ripetizione dell’unione collega tali eventi non autenticati alla persona corretta. La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra numeri diversi in base alla ripetizione dei dati.

*Gli stessi dati dopo la ripetizione:*

| Evento | Marca temporale | ID persistente (ID cookie) | ID transitorio (ID accesso) | ID unione (dopo unione live) | ID unione (dopo la riproduzione) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![Freccia su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob |
| 7 | 2023-05-12 12:07 | 246 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![Freccia su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob |
| | | **3 dispositivi** | | **4 persone**:<br/>246, Bob, 3579, 81911 | **2 persone**:<br/>Bob, 3579 |

{style="table-layout:auto"}

L’attribuzione funziona quando la variabile personalizzata di identificazione si collega a un dispositivo. Nell’esempio precedente, l’evento 1 e 10 vengono uniti in seguito alla ripetizione, lasciando separati solo gli eventi 8 e 9. E riducendo la metrica delle persone (cumulativa) a 2.

## Passaggio 3: richiesta di accesso a dati personali

Quando ricevi una richiesta di accesso a dati personali, la riga contenente le informazioni utente originali viene rimossa, insieme a tutti gli ID uniti che contengono queste informazioni sulla stessa persona. La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra l’effetto che una richiesta di privacy per Bob ha sui dati dopo l’elaborazione. Le righe in cui Bob si è autenticato vengono rimosse (2, 3, 5, 7 e 11) insieme alla rimozione di Bob come ID transitorio per altre righe.

*Gli stessi dati dopo una richiesta di privacy per Bob:*

| Evento | Marca temporale | ID persistente (ID cookie) | ID transitorio (ID accesso) | ID unione (dopo unione live) | ID unione (dopo la riproduzione) | ID transitorio (ID accesso) | ID unione (dopo la richiesta di privacy) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** | - | 246 |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![Freccia su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob | - | 246 |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob | - | 246 |
| 7 | 2023-05-12 12:07 | 246 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 8 | 2023-05-12 12:03 | 3579 ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 9 | 2023-05-12 12:09 | 3579 ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** | - | 81911 |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![Freccia su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 81911 |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob | - | 81911 |
| | | **3 dispositivi** | | **4 persone**:<br/>246, Bob, 3579, 81911 | **2 persone**:<br/>Bob, 3579 |  | **3 persone**:<br/>248, 3579, 81911 |


<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Call center person ID | Person ID used (stitched ID) | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visits your site on a desktop, unauthenticated | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accesses your site on a mobile device, unauthenticated | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `1` (Bob) |
-->

## Riepilogo

* L’unione unisce immediatamente gli eventi da dispositivi noti, ma non unisce immediatamente gli eventi da dispositivi nuovi o non riconosciuti.
* I dati vengono ripetuti a intervalli regolari e cambiano i dati storici nella connessione in base ai dispositivi che ha imparato a identificare.
* L’unione live e l’unione di ripetizione vengono eseguite su un singolo set di dati. Il risultato è un nuovo set di dati con privilegi elevati che è più adatto per essere utilizzato quando combinato con altri set di dati (ad esempio, dati dei call center) per eseguire l’analisi cross-channel.
* Le richieste di accesso a dati personali rimuovono le identità distribuite su righe non autenticate.
