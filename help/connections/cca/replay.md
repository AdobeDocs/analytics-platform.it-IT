---
title: Funzionamento delle riproduzioni
description: Comprendere il concetto di "ripetizione" in Analytics multicanale
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 1%

---


# Funzionamento delle riproduzioni

Analisi multicanale esegue due passaggi sui dati di una determinata connessione:

* **Colorazione** dal vivo: CCA tenta di cucire ogni hit mentre arriva. I nuovi dispositivi di rete al dataset che non hanno mai eseguito l&#39;accesso non vengono in genere inseriti a questo livello. I dispositivi già riconosciuti vengono cuciti immediatamente.
* **Riproduci**: CCA &quot;riproduce&quot; i dati in base a identificatori univoci appresi. In questa fase vengono uniti nuovi dispositivi alla connessione.  Adobe offre due intervalli di riproduzione:
   * Giornaliero: I dati vengono riprodotti ogni giorno con una finestra di lookback di 24 ore. Questa opzione offre un vantaggio che le riproduzioni sono molto più frequenti, ma i visitatori non autenticati devono autenticarsi lo stesso giorno in cui visitano il sito.
   * Settimanale: I dati vengono riprodotti una volta alla settimana con una finestra di lookback di 7 giorni. Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati di meno di una settimana non vengono cuciti.

## Passaggio 1: Cuciture dal vivo

CCA tenta di unire ogni evento al momento della raccolta a dispositivi e canali noti. Considerate l&#39;esempio seguente, in cui Bob utilizza due canali diversi.

*Dati visualizzati il giorno in cui viene raccolto:*

| Timestamp | ID persistente set di dati Web | ID transitorio set di dati Web | ID persona call center | ID persona utilizzato | Spiegazione dell&#39;hit | Metrica Persone (cumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visita il tuo sito sul suo desktop, non autenticato | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob accede sul desktop | `2` (246 e Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob effettua una chiamata al servizio clienti | `2` (246 e Bob) |
| `4` | `3579` | - | - | `3579` | Bob accede al sito sul suo dispositivo mobile, non autenticato | `3` (246, Bob e 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob accede tramite dispositivo mobile | `3` (246, Bob e 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob effettua un&#39;altra chiamata al servizio clienti | `3` (246, Bob e 3579) |
| `7` | `246` | - | - | `Bob` | Bob visita nuovamente il sito sul suo desktop, non autenticato | `3` (246, Bob e 3579) |

Sia gli eventi non autenticati che quelli autenticati sui nuovi dispositivi vengono conteggiati come persone separate (temporaneamente). Gli eventi non autenticati sui dispositivi riconosciuti sono live-cucite.

L&#39;attribuzione funziona non appena la variabile personalizzata di identificazione si collega a un dispositivo. Nell&#39;esempio precedente, tutti gli eventi ad eccezione degli eventi 1 e 4 sono live-cucite (utilizzano tutti l&#39;identificatore `Bob`). L&#39;attribuzione funziona sugli eventi 1 e 4 dopo aver ripetuto le cuciture.

## Passaggio 2: Ripetizione delle cuciture

A intervalli regolari (una volta alla settimana o una volta al giorno, a seconda della finestra di lookback scelta), CCA ricalcola i dati storici in base ai dispositivi riconosciuti. Se un dispositivo invia inizialmente i dati non autenticati e quindi effettua l’accesso, CCA associa tali eventi non autenticati alla persona corretta. La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra numeri diversi in base alla riproduzione dei dati.

*Gli stessi dati dopo la riproduzione:*

| Timestamp | ID persistente set di dati Web | ID transitorio set di dati Web | ID persona call center | ID persona utilizzato | Spiegazione dell&#39;hit | Metrica Persone (cumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visita il tuo sito sul suo desktop, non autenticato | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob accede sul desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob effettua una chiamata al servizio clienti | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accede al sito sul suo dispositivo mobile, non autenticato | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob accede tramite dispositivo mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob effettua un&#39;altra chiamata al servizio clienti | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visita nuovamente il sito sul suo desktop, non autenticato | `1` (Bob) |

## Recap

* CCA blocca immediatamente i dispositivi noti, ma non li blocca immediatamente.
* I dati vengono riprodotti a intervalli regolari e i dati storici della connessione vengono modificati in base ai dispositivi che ha imparato a identificare.
