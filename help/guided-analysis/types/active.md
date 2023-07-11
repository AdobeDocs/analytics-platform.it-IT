---
title: Attivo
description: Misura la crescita della base di utenti.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
source-git-commit: 14c7aa342649afbe9923b0086947e5a0adeefff2
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%

---

# Attivo

{{release-limited-testing}}

Il **Attivo** tipo di visualizzazione fornisce informazioni sulla crescita e l’acquisizione degli utenti in un periodo specifico. L’asse orizzontale è sempre una granularità temporale, mentre l’asse verticale è sempre una misurazione degli utenti. Gli utenti vengono analizzati dall’inizio dell’intervallo di date, suddivisi in quattro categorie:

* **Nuovo**: l’utente era attivo durante il punto dati corrente e non è apparso in nessun punto dati precedente. Passa il puntatore del mouse su &#39;[!UICONTROL New users]&#39; nella legenda del grafico per vedere quanto indietro deve andare il report per determinare un nuovo utente. Questa data viene selezionata in modo dinamico in base alla lunghezza e alla granularità dell’intervallo di date.
* **Ripeti**: l’utente è apparso nel punto dati immediatamente precedente e nel punto dati corrente.
* **Ritorno**: l’utente non è comparso nel punto dati immediatamente precedente, ma non è un nuovo utente.
* **Inattivo**: l’utente non è apparso nel punto dati corrente, ma nel punto dati immediatamente precedente. Gli utenti inattivi non vengono conteggiati per il numero totale di utenti attivi.

Tutti gli utenti attivi (nuovo + repeat + return) appaiono come una tonalità di rosso sopra l&#39;asse orizzontale, mentre tutti gli utenti inattivi appaiono in arancione sotto l&#39;asse orizzontale.

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Fidelizzazione e abbandono degli utenti:** Offre una chiara visualizzazione dei periodi di fidelizzazione degli utenti. Riconoscere questi periodi di conservazione elevata o bassa può aiutare a prendere decisioni sui prodotti per incoraggiare la conservazione elevata o ridurre al minimo l’abbandono.
* **Valutazione della campagna**: la visualizzazione di una campagna specifica può aiutarti a comprendere non solo la quantità di traffico generato, ma anche quanto la campagna abbia aiutato gli utenti a rimanere coinvolti.
* **Analisi del ciclo di vita degli utenti**: l’analisi della crescita degli utenti attivi durante l’intero ciclo di vita degli utenti può aiutare a identificare fasi specifiche in cui il coinvolgimento degli utenti subisce un calo. Ad esempio, se esiste un elevato tasso di utenti inattivi per coloro che si trovano in una fase di onboarding, può indicare problemi di usabilità o la necessità di una migliore guida all’interno del prodotto.

[Schermata della crescita degli utenti]

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **Eventi**: l’evento che desideri misurare. Poiché questo tipo di visualizzazione è basato su utente, un utente può toccare l’evento una volta all’interno della granularità della data impostata per essere conteggiato come utente attivo. È possibile includere un solo evento in una query.
* **Persone**: il segmento che desideri misurare. È possibile includere un solo segmento in una query.

## Impostazioni grafico

Questo tipo di visualizzazione offre le seguenti impostazioni del grafico. È possibile regolare le impostazioni del grafico utilizzando il menu tra il tipo di visualizzazione e il selettore del calendario.

* **Metrica**: la metrica da misurare. Le opzioni includono Numero di utenti e Percentuale di utenti.
* **Tipo di grafico**: tipo di visualizzazione che desideri utilizzare. Le opzioni disponibili sono Barre sovrapposte e Aree sovrapposte.

## Applica confronto temporale

{{apply-time-comparison}}

## Intervallo date

L’intervallo di date desiderato. Questa impostazione è composta da due componenti importanti:

* **Interval**: granularità della data in cui desideri visualizzare i dati. Le opzioni valide includono Orario, Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi che influiscono sul numero di coordinate nel grafico e sul numero di colonne nella tabella. Ad esempio, la visualizzazione di un’analisi con granularità giornaliera della durata di tre giorni mostrerebbe solo tre punti di dati, mentre un’analisi con granularità oraria della durata di tre giorni mostrerebbe 72 punti di dati.
* **Data**: data di inizio e fine. Sono disponibili predefiniti per l’intervallo di date, oppure puoi utilizzare il selettore del calendario per impostare la data esatta desiderata.
