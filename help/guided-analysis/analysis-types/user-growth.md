---
title: Crescita degli utenti
description: Monitora la crescita della base di utenti del tuo prodotto.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
source-git-commit: c18ed01f899b7a521c67ed6a0008210099b858bf
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# Crescita degli utenti

{{release-limited-testing}}

Il **Crescita degli utenti** [Tipo di analisi](overview.md) fornisce informazioni sulla crescita e l’acquisizione degli utenti in un periodo specifico. L’asse orizzontale è sempre una granularità temporale, mentre l’asse verticale è sempre una misurazione degli utenti. Gli utenti vengono analizzati dall’inizio dell’intervallo di date, suddivisi in quattro categorie:

* **Nuovo**: è la prima volta che l’utente viene visualizzato nell’intervallo di date specificato. Il primo punto dati è sempre un nuovo utente al 100%, poiché l’analisi non viene visualizzata al di fuori dell’intervallo di date.
* **Ripeti**: l’utente è apparso nel punto dati immediatamente precedente e nel punto dati corrente.
* **Ritorno**: l’utente non è comparso nel punto dati immediatamente precedente, ma non è un nuovo utente. Gli utenti di ritorno non possono essere visualizzati nella prima o nella seconda coordinata, in quanto devono prima apparire come un nuovo utente e poi come un utente inattivo.
* **Inattivo**: l’utente non è apparso nel punto dati corrente, ma nel punto dati immediatamente precedente. Gli utenti inattivi non vengono conteggiati per il numero totale di utenti attivi.

Tutti gli utenti attivi (nuovo + repeat + return) appaiono come una tonalità di rosso sopra l&#39;asse orizzontale, mentre tutti gli utenti inattivi appaiono in arancione sotto l&#39;asse orizzontale.

I casi di utilizzo per questo tipo di analisi includono:

* **Valutazione delle prestazioni**: la crescita degli utenti consente di valutare le prestazioni complessive del prodotto in termini di acquisizione di nuovi utenti. Tracciando le tendenze di crescita, puoi capire meglio se il tuo prodotto attrae e mantiene gli utenti al ritmo desiderato.
* **Fidelizzazione e abbandono degli utenti:** La crescita degli utenti fornisce una chiara visualizzazione dei periodi di fidelizzazione elevata o bassa degli utenti. Riconoscere questi periodi di conservazione elevata o bassa può aiutare a prendere decisioni sui prodotti per incoraggiare la conservazione elevata o ridurre al minimo l’abbandono.
* **Valutazione della campagna**: la visualizzazione della crescita degli utenti in relazione a una campagna specifica può aiutarti a comprendere non solo la quantità di traffico generato, ma anche quanto la campagna abbia aiutato gli utenti a rimanere coinvolti.

[Schermata della crescita degli utenti]

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **Eventi**: l’evento che desideri misurare. Poiché questo tipo di analisi è basato su utente, un utente può toccare l’evento una volta all’interno della granularità della data impostata per essere conteggiato come utente attivo. È possibile includere un solo evento in una query.
* **Persone**: il segmento che desideri misurare. È possibile includere un solo segmento in una query.

## Tipi di visualizzazione

La crescita degli utenti offre i seguenti tipi di visualizzazione. È possibile modificare il tipo di visualizzazione utilizzando il menu a discesa in alto a sinistra del grafico.

* **Attivo:** Misura la crescita della base di utenti.

## Impostazioni grafico

Crescita utenti offre le seguenti impostazioni del grafico. È possibile regolare le impostazioni del grafico utilizzando il menu tra il tipo di visualizzazione e il selettore del calendario.

* **Metrica**: la metrica da misurare. Le opzioni includono Numero di utenti e Percentuale di utenti.
* **Tipo di grafico**: tipo di visualizzazione che desideri utilizzare. Le opzioni disponibili sono Barre sovrapposte e Aree sovrapposte.

## Intervallo date

L’intervallo di date desiderato. Questa impostazione è composta da due componenti importanti:

* **Interval**: granularità della data in cui desideri visualizzare i dati. Le opzioni valide includono Orario, Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi che influiscono sul numero di coordinate nel grafico e sul numero di colonne nella tabella. Ad esempio, la visualizzazione di un’analisi con granularità giornaliera della durata di tre giorni mostrerebbe solo tre punti di dati, mentre un’analisi con granularità oraria della durata di tre giorni mostrerebbe 72 punti di dati.
* **Data**: data di inizio e fine. Sono disponibili predefiniti per l’intervallo di date, oppure puoi utilizzare il selettore del calendario per impostare la data esatta desiderata.
