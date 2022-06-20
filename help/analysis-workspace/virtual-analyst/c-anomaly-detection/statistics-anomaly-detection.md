---
description: Il rilevamento delle anomalie in Analysis Workspace utilizza una serie di tecniche di statistica avanzate per determinare se un’osservazione debba essere considerata come anomalia o meno.
title: Tecniche di statistica utilizzate nel rilevamento delle anomalie
feature: Anomaly Detection
exl-id: 7165e7a1-a04f-450e-bffd-e329adac6903
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 100%

---

# Tecniche di statistica utilizzate nel rilevamento delle anomalie

Il rilevamento delle anomalie in Analysis Workspace utilizza una serie di tecniche di statistica avanzate per determinare se un’osservazione debba essere considerata come anomalia o meno.

A seconda della granularità della data applicata al rapporto, vengono usate 3 diverse tecniche statistiche per il rilevamento di anomalie su base oraria, giornaliera e settimanale/mensile. Tali tecniche sono descritte di seguito.

## Rilevamento delle anomalie con granularità giornaliera

Per i report con granularità giornaliera, l’algoritmo considera diversi fattori importanti per fornire risultati quanto più precisi possibile. Innanzitutto, viene determinato che tipo di modello applicare in base ai dati disponibili per la classe selezionata. Sono disponibili due classi: un modello basato su serie temporale e uno per il rilevamento di dati aberranti (filtro funzionale).

Il primo si basa sulle seguenti combinazioni per tipo di errore, tendenza e stagionalità (ETS) come descritto da [Hyndman et al. (2008)](https://www.springer.com/us/book/9783540719168). Nello specifico, l’algoritmo prova le seguenti combinazioni:

1. ANA (errore additivo, nessuna tendenza, stagionalità additiva)
1. AAA (errore additivo, tendenza additiva, stagionalità additiva)
1. MNM (errore moltiplicativo, nessuna tendenza, stagionalità moltiplicativa)
1. MNA (errore moltiplicativo, nessuna tendenza, stagionalità additiva)
1. AAN (errore additivo, tendenza additiva, nessuna stagionalità)

L’algoritmo verifica quale di queste combinazioni è la più adatta selezionando quella con il miglior valore di errore medio assoluto percentuale (MAPE, Mean Absolute Percentage Error). Tuttavia, se il valore MAPE del modello per serie temporale migliore è maggiore del 15%, viene applicato il filtro funzionale. Solitamente, per i dati altamente ripetitivi (ad esempio, di settimana in settima o di mese in mese) risulta più adatto il modello di serie temporale.

Dopo la selezione del modello, l’algoritmo regola i risultati in base a festività e stagionalità anno su anno. Per le festività, l’algoritmo verifica la presenza delle seguenti festività nell’intervallo di date del rapporto:

* Memorial Day
* 4 luglio
* Giorno del Ringraziamento
* Black Friday
* Cyber Monday
* 24-26 dicembre
* Gennaio 1
* Dicembre 31

Queste festività sono state scelte da un’estesa analisi statistica su numerosi punti di dati di clienti, per individuare le ricorrenze più significative per la maggior parte delle tendenze relative ai clienti. Non è certo un elenco completo per tutti i clienti o cicli di business, ma l’applicazione di queste festività migliora notevolmente le prestazioni complessive dell’algoritmo per quasi tutti i set di dati dei clienti.

Dopo aver selezionato il modello e individuato le festività nell’intervallo di date del rapporto, l’algoritmo procede come descritto di seguito:

1. Genera il periodo di riferimento per le anomalie. Questo comprende fino a 35 giorni prima dell’intervallo di date del rapporto e un intervallo corrispondente di 1 anno prima (tenendo conto di eventuali anni bisestili e delle festività applicabili cadute in giorni diversi).
1. Verifica se le festività nel periodo corrente (escludendo l’anno precedente) sono anomale in base ai dati più recenti.
1. Se la festività nell’intervallo di date corrente è anomala, regola il valore previsto e l’intervallo di affidabilità della festività corrente data la festività corrispondente dell’anno prima (considerando 2 giorni prima e dopo). La correzione per la festività corrente si basa sul valore MAPE più basso di:

   1. Effetti additivi
   1. Effetti moltiplicativi
   1. Differenza anno su anno

Osserva il notevole miglioramento delle prestazioni per i giorni di Natale e Capodanno nell’esempio seguente:

![](assets/anomaly_statistics.png)

## Rilevamento delle anomalie con granularità oraria

I dati orari si basano sullo stesso approccio algoritmico utilizzato per la granularità giornaliera. Tuttavia, contano su due pattern di tendenze: il ciclo di 24 ore e il ciclo weekend/feriale. Per acquisire questi due effetti stagionali, l’algoritmo orario crea due modelli distinti per weekend e giorno feriale utilizzando lo stesso approccio già descritto.

Le finestre di formazione per le tendenze orarie si basano su una finestra di lookback di 336 ore.

## Rilevamento delle anomalie con granularità settimanale e mensile

Le tendenze settimanali e mensili non presentano le stesse tendenze settimanali o giornaliere riscontrate con granularità giornaliera o oraria; per questo motivo viene utilizzato un algoritmo distinto. Per la granularità settimanale e mensile, viene usato un approccio di rilevamento dati aberranti in due fasi: il test Generalized Extreme Studentized Deviate (GESD). Questo test considera il numero massimo di anomalie previste combinato con l’approccio di tipo diagramma a scatola regolato (metodo non parametrico per il rilevamento di dati aberranti) per determinare il numero massimo di dati aberranti. Le due fasi sono:

1. Funzione box-plot ponderata: determina il numero massimo di anomalie per i dati di input.
1. Funzione GESD: applicata ai dati di input con il risultato della prima fase.

La fase di rilevamento delle anomalie stagionali per festività e anno su anno quindi sottrae i dati dell’anno precedente da quelli correnti. Applica quindi ai dati il processo in due fasi descritto qui sopra per verificare che le anomalie sono appropriate in base alla stagionalità. Ognuna di queste granularità di date usa un periodo di lookback di 15 mesi o settimane che comprende l’intervallo di date selezionato per il rapporto e un intervallo di date corrispondente di un anno prima, a scopo di formazione.
