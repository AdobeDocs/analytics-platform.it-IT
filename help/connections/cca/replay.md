---
title: Funzionamento delle riproduzioni
description: Comprendere il concetto di "riproduzione" in Cross-Channel Analytics
exl-id: 1100043a-4e4f-4dbc-9cfc-9dcba5db5f67
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 1%

---

# Funzionamento delle riproduzioni

Cross-Channel Analytics effettua due passaggi sui dati di una determinata connessione:

* **Stitching live**: La CCA tenta di unire ogni hit mentre arriva. In genere, i nuovi dispositivi al set di dati che non hanno mai effettuato l’accesso non vengono uniti a questo livello. I dispositivi già riconosciuti vengono uniti immediatamente.
* **Riproduci**: CCA &quot;riproduce&quot; i dati in base a identificatori univoci appresi. In questa fase vengono uniti nuovi dispositivi alla connessione. L’Adobe offre due intervalli di riproduzione:
   * Giornaliero: I dati vengono riprodotti ogni giorno con un intervallo di lookback di 24 ore. Questa opzione offre un vantaggio in quanto le riproduzioni sono molto più frequenti, ma i visitatori non autenticati devono autenticarsi lo stesso giorno in cui visitano il tuo sito.
   * Settimanale: I dati vengono riprodotti una volta alla settimana con un intervallo di lookback di 7 giorni. Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati di età inferiore a una settimana non vengono uniti.

## Passaggio 1: Stitching live

CCA tenta di unire ogni evento sulla raccolta a dispositivi e canali noti. Prendi in considerazione l&#39;esempio seguente, in cui Bob utilizza due canali diversi.

*Dati visualizzati nel giorno in cui vengono raccolti:*

| Timestamp | ID persistente set di dati web | ID transitorio set di dati web | ID persona del call center | ID persona utilizzato | Spiegazione dell&#39;hit | Metrica Persone (cumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visita il tuo sito sul suo desktop, non autenticato | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob accede sul desktop | `2` (246 e Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob effettua una chiamata al servizio clienti | `2` (246 e Bob) |
| `4` | `3579` | - | - | `3579` | Bob accede al tuo sito sul suo dispositivo mobile, non autenticato | `3` (246, Bob e 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob accede tramite cellulare | `3` (246, Bob e 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob effettua un&#39;altra chiamata al servizio clienti | `3` (246, Bob e 3579) |
| `7` | `246` | - | - | `Bob` | Bob visita nuovamente il tuo sito sul desktop, non autenticato | `3` (246, Bob e 3579) |

Gli eventi non autenticati e non autenticati sui nuovi dispositivi vengono conteggiati come persone separate (temporaneamente). Gli eventi non autenticati sui dispositivi riconosciuti sono live-stitched.

L’attribuzione funziona non appena la variabile personalizzata di identificazione si collega a un dispositivo. Nell’esempio precedente, tutti gli eventi ad eccezione degli eventi 1 e 4 sono live-stitched (utilizzano tutti i `Bob` identificatore). L’attribuzione funziona sugli eventi 1 e 4 dopo la ripetizione dell’unione.

## Passaggio 2: Ripetete l&#39;unione

A intervalli regolari (una volta alla settimana o una volta al giorno a seconda dell’intervallo di lookback scelto), CCA ricalcola i dati storici in base ai dispositivi riconosciuti. Se un dispositivo invia inizialmente i dati mentre non è autenticato e quindi effettua l’accesso, CCA collega tali eventi non autenticati alla persona corretta. La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra numeri diversi in base alla riproduzione dei dati.

*Gli stessi dati dopo la riproduzione:*

| Timestamp | ID persistente set di dati web | ID transitorio set di dati web | ID persona del call center | ID persona utilizzato | Spiegazione dell&#39;hit | Metrica Persone (cumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visita il tuo sito sul suo desktop, non autenticato | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob accede sul desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob effettua una chiamata al servizio clienti | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accede al tuo sito sul suo dispositivo mobile, non autenticato | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob accede tramite cellulare | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob effettua un&#39;altra chiamata al servizio clienti | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visita nuovamente il tuo sito sul desktop, non autenticato | `1` (Bob) |

>[!NOTE]
>
>I dati vengono riprodotti solo per il set di dati del sito web. Il set di dati del call center rimane invariato, ma si verifica quando viene utilizzato l’ID persona corretto.

## Raccoglitore

* CCA unisce immediatamente i dispositivi noti, ma non unisce immediatamente i dispositivi nuovi o non riconosciuti.
* I dati vengono riprodotti a intervalli regolari e cambiano i dati storici nella connessione in base ai dispositivi che ha imparato a identificare.
