---
title: Analisi della crescita netta
description: Stai guadagnando o perdendo utenti?
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Analisi [!UICONTROL Net growth] {#net-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_netgrowth_button"
>title="Crescita netta"
>abstract="Stai guadagnando o perdendo utenti?"

<!-- markdownlint-enable MD034 -->

L&#39;analisi ![NetGrowth](/help/assets/icons/NetGrowth.svg) **[!UICONTROL Net growth]** fornisce informazioni sulla frequenza con cui si acquisiscono o si perdono utenti in un periodo specifico. L&#39;asse orizzontale è un intervallo di tempo, mentre l&#39;asse verticale è la misura della crescita.

Ogni punto dati rappresenta la crescita netta, calcolata con la seguente formula:

`([New users] + [Return users]) / [Dormant users]`

Il risultato di questa formula è un rapporto. Una crescita netta di `1` rappresenta un equilibrio; il prodotto ha ottenuto lo stesso numero di utenti che ha perso. Una crescita netta superiore a `1` rappresenta una crescita positiva; c&#39;erano più utenti nuovi e di ritorno che utenti inattivi. Analogamente, una crescita netta inferiore a `1` rappresenta una perdita; erano presenti più utenti inattivi rispetto ai nuovi utenti + di ritorno.

Analogamente all&#39;analisi [Active](active-growth.md), gli utenti sono definiti come segue:

* **[!UICONTROL New]**: l&#39;utente era attivo durante il periodo corrente, ma non in precedenza. Verificare l&#39;intervallo di visualizzazione dell&#39;analisi per determinare un nuovo utente passando il cursore sopra &#39;[!UICONTROL New users]&#39; nella legenda del grafico. L’intervallo di lookback viene determinato dinamicamente in base all’intervallo e all’intervallo di date selezionati.
* **[!UICONTROL Return]**: l&#39;utente era attivo nel periodo corrente e non nel periodo immediatamente precedente, ma prima era attivo. Verificare l&#39;intervallo di visualizzazione dell&#39;analisi per determinare un utente restituito passando il cursore sopra &#39;[!UICONTROL Return users]&#39; nella legenda del grafico. L’intervallo di lookback viene determinato dinamicamente in base all’intervallo e all’intervallo di date selezionati.
* **[!UICONTROL Dormant]**: l&#39;utente era attivo nel periodo immediatamente precedente, ma non è attivo nel periodo corrente. Gli utenti inattivi non vengono conteggiati per il numero totale di utenti attivi.

>[!NOTE]
>
>Gli utenti ripetuti non sono presi in considerazione in questo calcolo, in quanto non rappresentano alcun guadagno o perdita di utenti.

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?learn=on)


## Casi d’uso

I casi di utilizzo per questa analisi includono:

* **Valutazione delle prestazioni**: consente di valutare le prestazioni complessive del prodotto in termini di acquisizione di nuovi utenti. Tracciando le tendenze di crescita, puoi capire meglio se il tuo prodotto attrae e mantiene gli utenti al ritmo desiderato.
* **Analisi acquisizione utente**: consente di valutare l&#39;efficacia delle strategie di acquisizione utente. L’analisi delle origini della crescita degli utenti, ad esempio motori di ricerca, campagne o altri canali di marketing, ti consente di identificare le origini di crescita più significative, in modo da allocare le risorse di conseguenza.
* **Analisi abbandono**: la crescita netta include l&#39;attrito nella formula (utenti inattivi). Puoi valutare lo stato complessivo della tua base di utenti nel tempo. Se la crescita netta è costantemente inferiore a `1`, ciò indica un elevato grado di attrito che potrebbe richiedere l&#39;implementazione di strategie di conservazione.

## Interfaccia

Per una panoramica dell&#39;interfaccia di analisi guidata, vedere [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL View]**: passa da questa analisi a [Crescita attiva](active-growth.md).
* **[!UICONTROL Events]**: evento che si desidera misurare. Poiché questa analisi è basata sull’utente, un utente che interagisce con l’evento una volta all’interno del periodo viene conteggiato come utente attivo. È possibile includere un evento in una query.
* **[!UICONTROL Counted as]**: metodo di conteggio da applicare agli eventi selezionati. Le opzioni includono [!UICONTROL Number of users] e [!UICONTROL Percentage of users].
* **[!UICONTROL Segments]**: il segmento che si desidera misurare. È possibile includere un segmento in una query.

### Confronto temporale

{{apply-time-comparison}}

### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono Orario, Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi che influiscono sul numero di coordinate nel grafico e sul numero di colonne nella tabella. Ad esempio, la visualizzazione di un’analisi con granularità giornaliera della durata di tre giorni mostrerebbe solo tre punti di dati, mentre un’analisi con granularità oraria della durata di tre giorni mostrerebbe 72 punti di dati.
* **[!UICONTROL Date]**: la data di inizio e di fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
