---
title: Funzionamento delle riproduzioni
description: Comprendere il concetto di “ripetizione” in Cross-Channel Analytics
exl-id: 1100043a-4e4f-4dbc-9cfc-9dcba5db5f67
solution: Customer Journey Analytics
feature: Cross-Channel Analysis
hide: true
hidefromtoc: true
source-git-commit: ca037fa439a6a94ca071c610089a3ad931cc921d
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 89%

---

# Funzionamento delle riproduzioni

Cross-Channel Analytics effettua due passaggi sui dati di una determinata connessione:

* **Live-stitching**: CCA tenta di unire ogni evento nel momento in cui arriva. In genere, i nuovi dispositivi al set di dati che non hanno mai effettuato l’accesso a questo livello non vengono uniti. I dispositivi già riconosciuti vengono uniti immediatamente.
* **Ripetizione**: CCA “ripete” i dati in base a identificatori univoci appresi. Questa è la fase in cui vengono uniti nuovi dispositivi alla connessione. Adobe offre due intervalli di ripetizione:
   * Giornaliero: i dati vengono ripetuti ogni giorno con un intervallo di lookback di 24 ore. Questa opzione offre un vantaggio in quanto le ripetizioni sono molto più frequenti, ma le persone non autenticate devono autenticarsi lo stesso giorno in cui visitano il sito.
   * Settimanale: i dati vengono ripetuti una volta alla settimana con un intervallo di lookback di 7 giorni. Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati che hanno meno di una settimana non vengono uniti.

I dati oltre l’intervallo di lookback non vengono riprodotti. Una persona deve effettuare l’autenticazione all’interno di un intervallo di lookback specificato affinché una visita non autenticata e una visita autenticata siano identificate insieme. Una volta riconosciuto, il dispositivo è live-stitched da quel momento in poi.

## Passaggio 1: live-stitching

CCA tenta di unire ogni evento al momento della raccolta su dispositivi e canali noti. Prendi in considerazione l’esempio seguente, in cui Bob utilizza due canali diversi.

*Dati visualizzati nel giorno in cui vengono raccolti:*

| Marca temporale | ID persistente del set di dati web | ID transitorio del set di dati web | ID persona del call center | ID persona utilizzato | Spiegazione dell’evento | Metrica delle persone (cumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visita il tuo sito sul suo desktop, senza essere autenticato | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob si autentica sul desktop | `2` (246 e Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob chiama il servizio clienti | `2` (246 e Bob) |
| `4` | `3579` | - | - | `3579` | Bob accede al tuo sito sul suo dispositivo mobile, senza essersi autenticato | `3` (246, Bob e 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob accede tramite cellulare | `3` (246, Bob e 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob chiama nuovamente il servizio clienti | `3` (246, Bob e 3579) |
| `7` | `246` | - | - | `Bob` | Bob visita nuovamente il tuo sito sul desktop, senza autenticarsi | `3` (246, Bob e 3579) |

Gli eventi non autenticati e autenticati sui nuovi dispositivi vengono conteggiati come persone separate (temporaneamente). Gli eventi non autenticati sui dispositivi riconosciuti sono live-stitched.

L’attribuzione funziona non appena la variabile personalizzata di identificazione si collega a un dispositivo. Nell’esempio precedente, tutti gli eventi ad eccezione di 1 e 4 sono live-stitched (utilizzano tutti l’identificatore `Bob`). L’attribuzione funziona sugli eventi 1 e 4 dopo la ripetizione dell’unione.

## Passaggio 2: ripetere l’unione

A intervalli regolari (una volta alla settimana o una volta al giorno a seconda dell’intervallo di lookback scelto), CCA ricalcola i dati storici sui dispositivi riconosciuti. Se un dispositivo invia inizialmente i dati mentre non è autenticato e poi effettua l’accesso, CCA collega gli eventi non autenticati alla persona corretta. La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra numeri diversi in base alla ripetizione dei dati.

*Gli stessi dati dopo la ripetizione:*

| Marca temporale | ID persistente del set di dati web | ID transitorio del set di dati web | ID persona del call center | ID persona utilizzato | Spiegazione dell’evento | Metrica delle persone (cumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visita il tuo sito sul suo desktop, senza essere autenticato | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob si autentica sul desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob chiama il servizio clienti | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accede al tuo sito sul suo dispositivo mobile, senza essersi autenticato | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob accede tramite cellulare | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob chiama nuovamente il servizio clienti | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visita nuovamente il tuo sito sul desktop, senza autenticarsi | `1` (Bob) |

>[!NOTE]
>
>I dati vengono ripetuti solo per il set di dati del sito web. Il set di dati del call center rimane invariato, ma viene fatto corrispondere quando viene utilizzato l’ID persona corretto.

## Riassunto

* CCA unisce immediatamente i dispositivi noti, ma non unisce immediatamente i dispositivi nuovi o non riconosciuti.
* I dati vengono ripetuti a intervalli regolari e cambiano i dati storici nella connessione in base ai dispositivi che ha imparato a identificare.
