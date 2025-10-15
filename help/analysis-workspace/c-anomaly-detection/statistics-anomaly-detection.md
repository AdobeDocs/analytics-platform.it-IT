---
description: Scopri quali tecniche statistiche vengono utilizzate per identificare le anomalie.
title: Tecniche Di Statistica Utilizzate Nel Rilevamento Delle Anomalie
feature: Anomaly Detection
exl-id: 7165e7a1-a04f-450e-bffd-e329adac6903
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 36%

---

# Tecniche statistiche

Il rilevamento delle anomalie in Analysis Workspace utilizza una serie di tecniche di statistica avanzate per determinare se un’osservazione debba essere considerata come anomalia o meno.

A seconda della granularità della data applicata al rapporto, vengono usate 3 diverse tecniche statistiche per il rilevamento di anomalie su base oraria, giornaliera e settimanale/mensile. Tali tecniche sono descritte di seguito.

## Rilevamento delle anomalie con granularità giornaliera

Per i report con granularità giornaliera, l’algoritmo considera diversi fattori importanti per fornire risultati quanto più precisi possibile. In primo luogo, l’algoritmo determina il tipo di modello da applicare in base ai dati disponibili di cui seleziona una delle due classi: un modello basato su serie temporali o un modello di rilevamento di valori aberranti (segmentazione funzionale).

La selezione del modello della serie temporale si basa sulle seguenti combinazioni per tipo di errore, tendenza e stagionalità (ETS), come descritto da [Hyndman et al. (2008)](https://idp.springer.com/authorize?response_type=cookie&client_id=springerlink&redirect_uri=https%3A%2F%2Flink.springer.com%2Fbook%2F10.1007%2F978-3-540-71918-2). In particolare, l’algoritmo prova le seguenti combinazioni:

1. ANA (errore additivo, nessuna tendenza, stagionalità additiva)
1. AAA (errore additivo, tendenza additiva, stagionalità additiva)
1. MNM (errore moltiplicativo, nessuna tendenza, stagionalità moltiplicativa)
1. MNA (errore moltiplicativo, nessuna tendenza, stagionalità additiva)
1. AN (errore additivo, tendenza additiva, nessuna stagionalità)

L’algoritmo verifica l’idoneità di ciascuna di queste combinazioni selezionando quella con il miglior errore percentuale assoluto medio (MAPE). Tuttavia, se il MAPE del modello di serie temporali migliore è superiore al 15%, viene applicata la segmentazione funzionale. In genere, i dati con un elevato grado di ripetizione (ad esempio, settimana su settimana o mese su mese) sono i più adatti a un modello di serie temporali.

Dopo la selezione del modello, l’algoritmo regola quindi i risultati in base alle festività e alla stagionalità su base annua. Per le festività, l’algoritmo controlla se nell’intervallo di date del rapporto sono presenti le seguenti festività:

* Giorno della memoria
* 4 luglio
* Ringraziamento
* Black Friday
* Cyber Monday
* 24-26 dicembre
* Gennaio 1
* Dicembre 31

Queste festività sono state scelte da un’estesa analisi statistica su numerosi punti di dati di clienti, per individuare le ricorrenze più significative per la maggior parte delle tendenze relative ai clienti. Anche se l’elenco non è certamente esaustivo per tutti i clienti o cicli di business, l’applicazione delle festività migliora notevolmente le prestazioni complessive dell’algoritmo per quasi tutti i set di dati dei clienti.

Dopo aver selezionato il modello e individuato le festività nell’intervallo di date del rapporto, l’algoritmo procede come descritto di seguito:

1. Costruire il periodo di riferimento delle anomalie. Questo periodo di riferimento per le anomalie include fino a 35 giorni prima dell’intervallo di date del rapporto e un intervallo corrispondente di 1 anno prima. Conto per i giorni bisestili quando necessario e comprensivo di eventuali festività applicabili che possono essersi verificate in un giorno di calendario diverso nell’anno precedente.
1. Verifica se le festività nel periodo corrente (escludendo l’anno precedente) sono anomale in base ai dati più recenti.
1. Se la festività nell’intervallo di date corrente è anomala, regola il valore previsto e l’intervallo di affidabilità della festività corrente data la festività corrispondente dell’anno prima (considerando 2 giorni prima e dopo). La correzione per la festività corrente si basa sull’errore percentuale assoluto medio più basso di:

   1. Effetti additivi
   1. Effetti moltiplicativi
   1. Differenza YoY

Osserva il notevole miglioramento delle prestazioni per i giorni di Natale e Capodanno nell’esempio seguente:

![Grafici a due righe che mostrano le modifiche delle prestazioni con e senza le prestazioni delle festività.](assets/anomaly_statistics.png)

## Rilevamento delle anomalie con granularità oraria

I dati orari si basano sullo stesso approccio utilizzato dall’algoritmo di granularità giornaliera per le serie temporali. Tuttavia, contano su due pattern di tendenze: il ciclo di 24 ore e il ciclo weekend/feriale. Per cogliere questi due effetti stagionali, l’algoritmo orario costruisce due modelli distinti per un fine settimana e un giorno feriale, utilizzando lo stesso approccio descritto sopra.

Le finestre di formazione per le tendenze orarie si basano su un intervallo di lookback di 336 ore.

## Rilevamento delle anomalie con granularità settimanale e mensile

Le tendenze settimanali e mensili non presentano le stesse tendenze settimanali o giornaliere rilevate con granularità giornaliera o oraria, pertanto viene utilizzato un algoritmo separato. Ogni settimana e ogni mese, un approccio di rilevamento dei valori anomali in due fasi è noto come test GESD (Generalized Extreme Studentized Deviate). Questo test considera il numero massimo di anomalie previste combinate con l’approccio box-plot adeguato (un metodo non parametrico per la scoperta di valori aberranti) per determinare il numero massimo di valori aberranti. Le due fasi sono:

1. Funzione box-plot ponderata: determina il numero massimo di anomalie per i dati di input.
1. Funzione GESD: applicata ai dati di input con il risultato della prima fase.

La fase di rilevamento delle anomalie stagionali per festività e anno su anno quindi sottrae i dati dell’anno scorso da quelli di quest’anno. Quindi esegue di nuovo l’iterazione dei dati utilizzando il processo in due fasi descritto sopra per verificare che le anomalie siano appropriate in base alla stagionalità. Ognuna di queste granularità di date usa un periodo di lookback di 15 mesi o settimane che comprende l’intervallo di date selezionato per il rapporto e un intervallo di date corrispondente di un anno prima, a scopo di formazione.
