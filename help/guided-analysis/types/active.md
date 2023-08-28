---
title: Visualizzazione attiva
description: Identifica gli utenti nuovi, mantenuti, che ritornano o inattivi.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
keywords: analisi dei prodotti
source-git-commit: 4aed07568d345770183d18041a762adc441e6bc3
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 0%

---

# [!UICONTROL Active] view

Il **Attivo** fornisce informazioni sulla crescita e l’acquisizione degli utenti in un periodo specifico. L’asse orizzontale è un intervallo di tempo, mentre l’asse verticale è una misurazione degli utenti. Gli utenti sono suddivisi in quattro categorie:

* **[!UICONTROL New]**: l’utente era attivo durante il periodo corrente, ma non in precedenza. Per vedere quanto si spinge l’analisi indietro, passa il cursore sopra &quot;[!UICONTROL New users]&#39; nella legenda del grafico. L’intervallo di lookback viene determinato dinamicamente in base all’intervallo e all’intervallo di date selezionati.
* **[!UICONTROL Repeat]**: l’utente era attivo nel periodo corrente e immediatamente precedente.
* **[!UICONTROL Return]**: l’utente era attivo nel periodo corrente e non nel periodo immediatamente precedente, ma prima era attivo a un certo punto. Per vedere quanto si spinge l’analisi indietro, passa il cursore sopra &quot;[!UICONTROL Return users]&#39; nella legenda del grafico. L’intervallo di lookback viene determinato dinamicamente in base all’intervallo e all’intervallo di date selezionati.
* **[!UICONTROL Dormant]**: l’utente era attivo nel periodo immediatamente precedente, ma non è attivo nel periodo corrente. Gli utenti inattivi non vengono conteggiati per il numero totale di utenti attivi.

Tutti gli utenti attivi (nuovo + repeat + return) appaiono come una tonalità di rosso sopra l&#39;asse orizzontale, mentre tutti gli utenti inattivi appaiono in arancione sotto l&#39;asse orizzontale.

>[!VIDEO](https://video.tv.adobe.com/v/3421667/?learn=on)

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **[!UICONTROL User retention and chur]n:** Offre una chiara visualizzazione dei periodi di fidelizzazione degli utenti. Riconoscere questi periodi di conservazione elevata o bassa può aiutare a prendere decisioni sui prodotti per incoraggiare la conservazione elevata o ridurre al minimo l’abbandono.
* **[!UICONTROL Campaign assessment]**: la visualizzazione di una campagna specifica può aiutarti a comprendere non solo la quantità di traffico generato, ma anche quanto la campagna abbia aiutato gli utenti a rimanere coinvolti.
* **[!UICONTROL User lifecycle analysis]**: l’analisi della crescita degli utenti attivi durante l’intero ciclo di vita degli utenti può aiutare a identificare fasi specifiche in cui il coinvolgimento degli utenti subisce un calo. Ad esempio, se il numero di utenti inattivi per i singoli utenti in una fase di onboarding è elevato, ciò può indicare problemi di usabilità o la necessità di una migliore guida all’interno del prodotto.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Events]**: l’evento che desideri misurare. Poiché questo tipo di visualizzazione è basato su utente, un utente che interagisce con l’evento una volta all’interno del periodo viene conteggiato come utente attivo. È possibile includere un evento in una query.
* **[!UICONTROL People]**: il segmento che desideri misurare. È possibile includere un segmento in una query.

## Impostazioni grafico

Il [!UICONTROL Active] visualizza offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Metric]**: la metrica da misurare. Le opzioni includono Numero di utenti e Percentuale di utenti.
* **[!UICONTROL Chart type]**: tipo di visualizzazione che desideri utilizzare. Le opzioni disponibili sono Barre sovrapposte e Aree sovrapposte.

## Applica confronto temporale

{{apply-time-comparison}}

![Confronto tempo attivo](../assets/active-compare.png)

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono Orario, Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi che influiscono sul numero di coordinate nel grafico e sul numero di colonne nella tabella. Ad esempio, la visualizzazione di un’analisi con granularità giornaliera della durata di tre giorni mostrerebbe solo tre punti di dati, mentre un’analisi con granularità oraria della durata di tre giorni mostrerebbe 72 punti di dati.
* **[!UICONTROL Date]**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.
