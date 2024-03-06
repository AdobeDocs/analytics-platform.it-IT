---
title: Visualizzazione della crescita netta
description: Stai guadagnando o perdendo utenti?
feature: Adobe Product Analytics, Guided Analysis
keywords: analisi dei prodotti
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: 240a17923b55479865affaafb098b56e32d083a3
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 0%

---

# [!UICONTROL Net growth] visualizza

Il **[!UICONTROL Net growth]** tipo di visualizzazione fornisce informazioni sul tasso di guadagno o perdita degli utenti in un periodo specifico. L&#39;asse orizzontale è un intervallo di tempo, mentre l&#39;asse verticale è la misura della crescita.

Ogni punto dati rappresenta la crescita netta, calcolata con la seguente formula:

`([New users] + [Return users]) / [Dormant users]`

Il risultato di questa formula è un rapporto. Una crescita netta di `1` rappresenta un equilibrio; il prodotto ha guadagnato lo stesso numero di utenti che ha perso. Una crescita netta maggiore di `1` rappresenta una crescita positiva; c’erano più utenti nuovi e di ritorno che utenti inattivi. Analogamente, una crescita netta inferiore a `1` rappresenta una perdita; c&#39;erano più utenti inattivi che nuovi utenti + di ritorno.

Simile a [Attivo](active.md) tipo di visualizzazione, gli utenti sono definiti come segue:

* **[!UICONTROL New]**: l’utente era attivo durante il periodo corrente, ma non in precedenza. Osserva l’analisi indietro nel tempo per determinare un nuovo utente passando il puntatore del mouse su &quot;[!UICONTROL New users]&#39; nella legenda del grafico. L’intervallo di lookback viene determinato dinamicamente in base all’intervallo e all’intervallo di date selezionati.
* **[!UICONTROL Return]**: l’utente era attivo nel periodo corrente e non nel periodo immediatamente precedente, ma prima era attivo a un certo punto. Osserva quanto si estende l’analisi per determinare un utente di ritorno passando il puntatore del mouse su &quot;[!UICONTROL Return users]&#39; nella legenda del grafico. L’intervallo di lookback viene determinato dinamicamente in base all’intervallo e all’intervallo di date selezionati.
* **[!UICONTROL Dormant]**: l’utente era attivo nel periodo immediatamente precedente, ma non è attivo nel periodo corrente. Gli utenti inattivi non vengono conteggiati per il numero totale di utenti attivi.

>[!NOTE]
>
>Gli utenti ripetuti non sono presi in considerazione in questo calcolo, in quanto non rappresentano alcun guadagno o perdita di utenti.

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?learn=on)

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Valutazione delle prestazioni**: consente di valutare le prestazioni complessive del prodotto in termini di acquisizione di nuovi utenti. Tracciando le tendenze di crescita, puoi capire meglio se il tuo prodotto attrae e mantiene gli utenti al ritmo desiderato.
* **Analisi dell&#39;acquisizione utente**: consente di valutare l’efficacia delle strategie di acquisizione degli utenti. L’analisi delle origini della crescita degli utenti, ad esempio motori di ricerca, campagne o altri canali di marketing, ti consente di identificare le origini di crescita più significative, in modo da allocare le risorse di conseguenza.
* **Analisi dell’abbandono**: la crescita netta include l’attrito nella sua formula (utenti inattivi). Puoi valutare lo stato complessivo della tua base di utenti nel tempo. Se la crescita netta è costantemente inferiore `1`, indica un livello elevato di attrito che potrebbe richiedere l&#39;implementazione di strategie di fidelizzazione.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL View]**: passa da questo tipo di visualizzazione a [Attivo](active.md).
* **[!UICONTROL Events]**: l’evento che desideri misurare. Poiché questo tipo di visualizzazione è basato su utente, un utente che interagisce con l’evento una volta all’interno del periodo viene conteggiato come utente attivo. È possibile includere un evento in una query.
* **[!UICONTROL Counted as]**: metodo di conteggio da applicare agli eventi selezionati. Le opzioni includono [!UICONTROL Number of users] e [!UICONTROL Percentage of users].
* **[!UICONTROL Segments]**: il segmento che desideri misurare. È possibile includere un segmento in una query.

## Confronto temporale

{{apply-time-comparison}}

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono Orario, Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi che influiscono sul numero di coordinate nel grafico e sul numero di colonne nella tabella. Ad esempio, la visualizzazione di un’analisi con granularità giornaliera della durata di tre giorni mostrerebbe solo tre punti di dati, mentre un’analisi con granularità oraria della durata di tre giorni mostrerebbe 72 punti di dati.
* **[!UICONTROL Date]**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.
