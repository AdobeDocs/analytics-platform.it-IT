---
title: Analisi attiva della crescita
description: Identifica gli utenti nuovi, mantenuti, che ritornano o inattivi.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 4%

---

# Analisi [!UICONTROL Active growth] {#active-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_activegrowth_button"
>title="Crescita attiva"
>abstract="Identifica gli utenti nuovi, mantenuti, che ritornano o inattivi."

<!-- markdownlint-enable MD034 -->


L&#39;analisi ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL Active growth]** fornisce informazioni sulla crescita e l&#39;acquisizione degli utenti in un periodo specifico. L’asse orizzontale è un intervallo di tempo, mentre l’asse verticale è una misurazione degli utenti. Gli utenti sono suddivisi in quattro categorie:

* **[!UICONTROL New]**: l&#39;utente era attivo durante il periodo corrente, ma non in precedenza. Osserva l&#39;analisi passando il cursore sopra _[!UICONTROL New users]_nella legenda del grafico. L’intervallo di lookback viene determinato dinamicamente in base all’intervallo e all’intervallo di date selezionati.
* **[!UICONTROL Repeat]**: l&#39;utente era attivo nel periodo corrente e immediatamente precedente.
* **[!UICONTROL Return]**: l&#39;utente era attivo nel periodo corrente e non nel periodo immediatamente precedente, ma prima era attivo. Osserva l&#39;analisi passando il cursore sopra _[!UICONTROL Return users]_nella legenda del grafico. L’intervallo di lookback viene determinato dinamicamente in base all’intervallo e all’intervallo di date selezionati.
* **[!UICONTROL Dormant]**: l&#39;utente era attivo nel periodo immediatamente precedente, ma non è attivo nel periodo corrente. Gli utenti inattivi non vengono conteggiati per il numero totale di utenti attivi.

Tutti gli utenti attivi (nuovo + repeat + return) appaiono come una tonalità di rosso sopra l&#39;asse orizzontale, mentre tutti gli utenti inattivi appaiono in arancione sotto l&#39;asse orizzontale.


>[!VIDEO](https://video.tv.adobe.com/v/3421667/?quality=12&learn=on)

## Casi d’uso

I casi di utilizzo per questa analisi includono:

* **Fidelizzazione e abbandono utenti:** fornisce una chiara visualizzazione dei periodi di fidelizzazione utenti elevata o bassa. Riconoscere questi periodi di conservazione elevata o bassa può aiutare a prendere decisioni sui prodotti per incoraggiare la conservazione elevata o ridurre al minimo l’abbandono.
* **Valutazione della campagna**: la visualizzazione di una campagna specifica può aiutarti a comprendere quanto traffico ha generato e quanto ha aiutato gli utenti a rimanere coinvolti.
* **Analisi del ciclo di vita dell&#39;utente**: l&#39;analisi della crescita degli utenti attivi durante l&#39;intero ciclo di vita dell&#39;utente può aiutare a identificare fasi specifiche in cui il coinvolgimento degli utenti subisce un calo. Ad esempio, se il numero di utenti inattivi per i singoli utenti in una fase di onboarding è elevato, ciò può indicare problemi di usabilità o la necessità di una migliore guida all’interno del prodotto.

## Interfaccia

Per una panoramica dell&#39;interfaccia di analisi guidata, vedere [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL View]**: passa da questa analisi a [Crescita netta](net-growth.md).
* **[!UICONTROL Events]**: evento che si desidera misurare. Poiché questa analisi è basata sull’utente, un utente che interagisce con l’evento una volta all’interno del periodo viene conteggiato come utente attivo. È possibile includere un evento in una query.
* **[!UICONTROL Counted as]**: metodo di conteggio da applicare agli eventi selezionati. Le opzioni includono [!UICONTROL Number of users] e [!UICONTROL Percentage of users].
* **[!UICONTROL Segments]**: segmento in base al quale filtrare i dati. È possibile includere un segmento in una query.

### Impostazioni grafico

L&#39;analisi [!UICONTROL Active growth] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Chart type]**: tipo di visualizzazione che si desidera utilizzare. Le opzioni includono [!UICONTROL Stacked bar] e [!UICONTROL Stacked area].

### Confronto temporale

{{apply-time-comparison}}

### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono Orario, Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi, che influiscono sul numero di coordinate nel grafico e sul numero di colonne nella tabella. Ad esempio, la visualizzazione di un’analisi con granularità giornaliera della durata di tre giorni mostrerebbe solo tre punti di dati, mentre un’analisi con granularità oraria della durata di tre giorni mostrerebbe 72 punti di dati.
* **[!UICONTROL Date]**: la data di inizio e di fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
