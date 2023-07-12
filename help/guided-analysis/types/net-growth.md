---
title: Crescita netta
description: Saldo degli utili e delle perdite degli utenti.
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 0%

---

# Crescita netta

{{release-limited-testing}}

Il **Crescita netta** tipo di visualizzazione fornisce informazioni sulla frequenza con cui si acquisiscono o si perdono utenti in un periodo specifico. L’asse orizzontale è sempre una granularità temporale, mentre l’asse verticale è sempre la misurazione della crescita.

Ogni punto dati rappresenta la crescita netta di quel punto dati, calcolata con la seguente formula:

`([New users] + [Return users]) / [Dormant users]`

Simile a [Attivo](active.md) tipo di visualizzazione, gli utenti sono definiti come segue:

* **Nuovo**: l’utente era attivo durante il punto dati corrente e non è apparso in nessun punto dati precedente.
* **Ritorno**: l’utente non è comparso nel punto dati immediatamente precedente, ma non è un nuovo utente.
* **Inattivo**: l’utente non è apparso nel punto dati corrente, ma nel punto dati immediatamente precedente. Gli utenti inattivi non vengono conteggiati per il numero totale di utenti attivi.

**Ripeti** Gli utenti non sono presi in considerazione in questo calcolo, in quanto non rappresentano alcuna crescita o perdita.

Il risultato di questa formula è un rapporto con cui la base utente è cresciuta o si è ridotta durante quel punto dati. Una crescita netta di `1` rappresenta un equalibrium; il prodotto ha ottenuto lo stesso numero di utenti che ha perso. Una crescita netta maggiore di `1` rappresenta una crescita positiva; c’erano più utenti nuovi/di ritorno che utenti inattivi. Analogamente, una crescita netta inferiore a `1` rappresenta una perdita di utenti attivi; c&#39;erano più utenti inattivi rispetto agli utenti nuovi/di ritorno.

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Analisi dell&#39;acquisizione utente**: consente di valutare l’efficacia delle strategie di acquisizione degli utenti. L’analisi delle origini della crescita degli utenti, ad esempio motori di ricerca, campagne o altri canali di marketing, ti consente di identificare le origini di crescita più significative, in modo da allocare le risorse di conseguenza.
* **Valutazione delle prestazioni**: consente di valutare le prestazioni complessive del prodotto in termini di acquisizione di nuovi utenti. Tracciando le tendenze di crescita, puoi capire meglio se il tuo prodotto attrae e mantiene gli utenti al ritmo desiderato.
* **Analisi dell’abbandono**: la crescita netta include l’attrito nella sua formula (utenti inattivi). Puoi valutare lo stato complessivo della tua base di utenti nel tempo. Se la crescita netta è costantemente inferiore `1`, indica un elevato grado di attrito, che ti spinge a indagare le ragioni dietro di esso e a implementare strategie di fidelizzazione.

![Crescita netta](../assets/net-growth.png)

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **Eventi**: l’evento che desideri misurare. Poiché questo tipo di visualizzazione è basato sull’utente, un utente può toccare l’evento una volta entro la granularità della data impostata per essere nella crescita netta. È possibile includere un solo evento in una query.
* **Persone**: il segmento che desideri misurare. È possibile includere un solo segmento in una query.

## Intervallo date

L’intervallo di date desiderato. Questa impostazione è composta da due componenti importanti:

* **Interval**: granularità della data in cui desideri visualizzare i dati. Le opzioni valide includono Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi che influiscono sul numero di coordinate nel grafico e sul numero di colonne nella tabella. Ad esempio, la visualizzazione di un’analisi con granularità giornaliera della durata di tre giorni mostrerebbe solo tre punti di dati, mentre un’analisi con granularità oraria della durata di tre giorni mostrerebbe 72 punti di dati.
* **Data**: data di inizio e fine. Sono disponibili predefiniti per l’intervallo di date, oppure puoi utilizzare il selettore del calendario per impostare la data esatta desiderata.
