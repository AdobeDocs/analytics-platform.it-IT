---
description: Scopri come la previsione in Analysis Workspace utilizza una serie di tecniche statistiche avanzate per determinare i valori della previsione.
title: Tecniche di statistica
feature: Visualizations
role: User
exl-id: f042a6dd-6af5-4bdd-afc9-07546d8ded6e
TQID: https://experienceleague.adobe.com/hbfehTAPC7nw96Wdm47bdX-D5c4cfTCeCtlHlINBBxI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: d13dba12-733d-4914-8d92-d643658bbe5d
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 552
ht-degree: 4%

---

# Tecniche statistiche

Il servizio di previsione attualmente supporta Prophet ed è stato dimostrato che funziona in modo efficiente e affidabile per la maggior parte dei dati. Prophet è un pacchetto di previsione open-source ampiamente utilizzato sviluppato da Meta. Scompone i dati in componenti per tendenze, stagionalità ed eventi. Il modello Profeta è efficiente e si adatta bene a molte applicazioni di previsione. Inoltre, il modello funziona in modo affidabile contro valori anomali e dati mancanti.

In futuro, si prevede di selezionare modelli basati sull&#39;euristica, ad esempio scegliere Online Approximate Gaussian Process per i dati in streaming, o NeuralProphet quando gli utenti specificano la migliore precisione di previsione e possono tollerare tempi di attesa più lunghi.

Il servizio esegue automaticamente il downscale dei dati quando sono presenti troppi punti di dati, per garantire il tempo di risposta. Il tempo di risposta di destinazione è impostato su ~3 secondi. Attualmente, quando il numero di punti di dati supera i 5500, i dati delle serie temporali vengono ricampionati verso il basso adattando la frequenza a seconda della lunghezza dei dati. L’output viene riconvertito alla frequenza dati originale, pertanto il processo di campionamento adattivo non influirà sulle esperienze degli utenti.

Gli effetti festivi vengono considerati quando sono disponibili dati di più anni. Attualmente, l’elenco delle festività considerate è:

* Martin Luther King Day
* Festa dei presidenti
* Giorno della memoria
* 4 luglio
* Ringraziamento
* Black Friday
* Cyber Monday
* Natale

Il servizio può anche eseguire una semplice rimozione delle anomalie (outlier), ad esempio rimuovendo punti dati che non rientrano nell’intervallo di sei sigma. Questa opzione non è abilitata per impostazione predefinita in quanto si presume che tutte le coordinate siano valide. Le anomalie possono avere un&#39;influenza negativa sulla qualità del modello anche se il modello Profeta è resiliente agli outlier in generale.

Il servizio accetta impostazioni di stagionalità specificate dall’utente, ad esempio stagionalità giornaliera e settimanale. In caso contrario, il modello seleziona automaticamente la stagionalità. Per una granularità dei dati diversa, il servizio utilizza lunghezze di dati storici diverse per generare modelli di previsione. Ad esempio, per i dati giornalieri, vengono estratti più di un anno di dati (se disponibili). Per i dati orari, vengono estratte otto settimane di dati (se disponibili). Il richiamo dei dati può richiedere molto tempo e a volte causa tempi di attesa più lunghi.

I dati storici richiesti per granularità temporale diversa:

| Granularità | Dati storici richiesti |
|---|--:|
| Minuto | 3 giorni |
| Ora | 2 settimane |
| Giorno | 8 settimane |
| Settimana | 2 anni |
| Mese | 2 anni |
| Trimestre | 8 trimestri |
| Anno | 8 anni |


Il risultato della previsione per ogni tempo specificato viene fornito con un intervallo di previsione (definito dal limite inferiore e superiore), che dovrebbe contenere il valore futuro osservato il 95% del tempo, spesso denominato intervallo di affidabilità. Non vi è alcun limite alla previsione futura del servizio. Tuttavia, l&#39;incertezza nelle previsioni aumenta con date più lontane nel futuro, rispecchiata da un più ampio intervallo di previsione nel tempo.

Il servizio non fa alcuna supposizione sui dati utente. Ad esempio, il servizio non presuppone che i dati non siano negativi. Ciò significa che le previsioni e/o i loro limiti possono essere negativi, se i dati mostrano una forte tendenza al ribasso, anche se tutti i punti di dati osservati non sono negativi.


## Riferimenti

1. Taylor, Sean J. e Benjamin Letham: *Previsione su larga scala.* The American Statistician 72.1 (2018): 37-45.
1. Triebe, Oskar, et al.: *Neuralprophet: previsioni spiegabili su scala.* prestampa arXiv arXiv:2111.15397(2021).
1. Zhang e Arbor: *Rilevamento anomalie della serie temporale.* Domanda di brevetto USA #18/057883.
