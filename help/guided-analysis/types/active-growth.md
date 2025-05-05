---
title: Analisi della crescita attiva
description: Identifica gli utenti nuovi, mantenuti, che ritornano o inattivi.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 98%

---

# [!UICONTROL Active growth] analisi {#active-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_activegrowth_button"
>title="Crescita attiva"
>abstract="Identifica gli utenti nuovi, mantenuti, che ritornano o inattivi."

<!-- markdownlint-enable MD034 -->


L’analisi della ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL Active growth]** fornisce informazioni sulla crescita e l’acquisizione degli utenti in un determinato periodo. L’asse orizzontale mostra un intervallo di tempo, mentre l’asse verticale indica la misura degli utenti. Gli utenti sono suddivisi in quattro categorie:

* **[!UICONTROL New]**: l’utente è stato attivo nel periodo corrente, ma non in precedenza. Scopri quanto risale indietro l’analisi passando il puntatore su _[!UICONTROL New users]_&#x200B;nella legenda del grafico. L’intervallo di lookback viene determinato dinamicamente in base all’intervallo di date selezionato.
* **[!UICONTROL Repeat]**: l’utente è stato attivo nel periodo corrente e in quello immediatamente precedente.
* **[!UICONTROL Return]**: l’utente è stato attivo nel periodo corrente, non è stato attivo nel periodo immediatamente precedente, ma è stato attivo ancora prima. Scopri quanto risale indietro l’analisi passando il puntatore su _[!UICONTROL Return users]_&#x200B;nella legenda del grafico. L’intervallo di lookback viene determinato dinamicamente in base all’intervallo di date selezionato.
* **[!UICONTROL Dormant]**: l’utente è stato attivo nel periodo immediatamente precedente, ma non è stato attivo nel periodo corrente. Gli utenti inattivi non concorrono al numero totale degli utenti attivi.

Tutti gli utenti attivi (nuovi + ripetuti + di ritorno) vengono visualizzati in una tonalità di verde sopra l’asse orizzontale, mentre tutti gli utenti inattivi vengono visualizzati in arancione sotto l’asse orizzontale.


>[!VIDEO](https://video.tv.adobe.com/v/3423395/?quality=12&learn=on&captions=ita)

## Casi d’uso

I casi d’uso per questa analisi includono:

* **Mantenimento e abbandono degli utenti:** fornisce una chiara visualizzazione dei periodi di maggiore o minore mantenimento degli utenti. Riconoscere questi periodi di maggiore o minore capacità di mantenimento può aiutare a prendere decisioni sui prodotti utili ad aumentare la fidelizzazione e ridurre al minimo l’abbandono.
* **Valutazione della campagna**: visualizzando una campagna specifica, potrai capire quanto traffico ha generato e quanto ha contribuito a tenere gli utenti coinvolti.
* **Analisi del ciclo di vita degli utenti**: l’analisi della crescita degli utenti attivi durante il relativo ciclo di vita consente di identificare le fasi specifiche in cui il loro coinvolgimento subisce un calo. Un’alta percentuale di utenti inattivi in una fase di onboarding, ad esempio, può indicare problemi di usabilità o la necessità di migliorare le indicazioni fornite all’interno del prodotto.

## Interfaccia

Per una panoramica dell’interfaccia dell’analisi guidata, consulta [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL View]**: consente di passare da questa analisi a [Crescita netta](net-growth.md).
* **[!UICONTROL Events]**: l’evento che desideri misurare. Poiché questa analisi è basata sull’utente, vengono conteggiati come utenti attivi anche coloro che interagiscono con l’evento una volta nell’arco del periodo. Puoi includere un evento in una query.
* **[!UICONTROL Counted as]**: il metodo di conteggio che desideri applicare agli eventi selezionati. Le opzioni includono [!UICONTROL Number of users] e [!UICONTROL Percentage of users].
* **[!UICONTROL Segments]**: segmento in base al quale si desidera segmentare i dati. Puoi includere un segmento in una query.

### Impostazioni del grafico

L’analisi della[!UICONTROL Active growth] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Chart type]**: il tipo divisualizzazione che vuoi usare. Le opzioni includono [!UICONTROL Stacked bar] e [!UICONTROL Stacked area].

### Confronto temporale

{{apply-time-comparison}}

### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è costituita da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono: Oraria, Giornaliera, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere una granularità diversa, da cui dipende il numero di punti dati nel grafico e il numero di colonne nella tabella. Nella visualizzazione di un’analisi di tre giorni con granularità giornaliera, ad esempio, saranno presenti solo tre punti dati, mentre in quella di un’analisi di tre giorni con granularità oraria ne saranno presenti 72.
* **[!UICONTROL Date]**: la data di inizio e di fine. Per comodità, sono disponibili intervalli di date continui predefiniti e intervalli personalizzati salvati in precedenza; in alternativa, puoi utilizzare il selettore del calendario per scegliere un intervallo di date fisso.

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
