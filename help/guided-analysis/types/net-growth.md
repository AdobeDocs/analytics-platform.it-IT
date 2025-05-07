---
title: Analisi della crescita netta
description: Stai guadagnando o perdendo utenti?
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: be617c59cd2fced0031fda1130b86e638bee8f68
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 95%

---

# [!UICONTROL Net growth] analisi {#net-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_netgrowth_button"
>title="Crescita netta"
>abstract="Stai guadagnando o perdendo utenti?"

<!-- markdownlint-enable MD034 -->

L’analisi della ![NetGrowth](/help/assets/icons/NetGrowth.svg) **[!UICONTROL Net growth]** fornisce informazioni sulla velocità con cui guadagni o perdi utenti in un determinato periodo. L’asse orizzontale mostra un intervallo di tempo, mentre l’asse verticale indica la misura della crescita.

Ogni punto dati rappresenta la crescita netta, calcolata con la formula seguente:

`([New users] + [Return users]) / [Dormant users]`

Il risultato di questa formula è un rapporto. Una crescita netta di `1` rappresenta un equilibrio; ovvero il numero di utenti guadaganti dal prodotto coincide con il numero di utenti persi. Una crescita netta superiore a `1` indica una crescita positiva, ovvero il numero complessivo di utenti nuovi e di ritorno è superiore a quello degli utenti inattivi. Analogamente, una crescita netta inferiore a `1` rappresenta una perdita; ovvero il numero di utenti nuovi + di ritorno è inferiore a quello degli utenti inattivi.

Come nell’analisi della crescita [attiva](active-growth.md), gli utenti vengono definiti come illustrato di seguito:

* **[!UICONTROL New]**: l’utente era attivo durante il periodo corrente, ma non in precedenza. Scopri quanto risale indietro l’analisi per determinare un nuovo utente passando il puntatore su “[!UICONTROL New users]” nella legenda del grafico. L’intervallo di lookback viene determinato dinamicamente in base all’intervallo di date selezionato.
* **[!UICONTROL Return]**: l’utente è stato attivo nel periodo corrente, non è stato attivo nel periodo immediatamente precedente, ma è stato attivo ancora prima. Scopri quanto risale indietro l’analisi per determinare un utente di ritorno passando il puntatore su “[!UICONTROL Return users]” nella legenda del grafico. L’intervallo di lookback viene determinato dinamicamente in base all’intervallo di date selezionato.
* **[!UICONTROL Dormant]**: l’utente è stato attivo nel periodo immediatamente precedente, ma non è stato attivo nel periodo corrente. Gli utenti inattivi non concorrono al numero totale degli utenti attivi.

>[!NOTE]
>
>Gli utenti ripetuti non vengono presi in considerazione in questo calcolo, poiché non appartengono né agli utenti acquisiti né a quelli persi.

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?quality=12&learn=on)


## Casi d’uso

I casi d’uso per questa analisi includono:

* **Valutazione delle prestazioni**: consente di valutare le prestazioni complessive del prodotto in termini di acquisizione di nuovi utenti. Tracciando le tendenze di crescita, puoi capire meglio se il prodotto attrae e mantiene gli utenti al ritmo desiderato.
* **Analisi di acquisizione utenti**: consente di valutare l’efficacia delle strategie di acquisizione degli utenti. Analizzando le origini da cui prende forma la crescita degli utenti, ad esempio motori di ricerca, campagne o altri canali di marketing, portrai identificare le origini di crescita più significative e allocare le risorse di conseguenza.
* **Analisi dell’abbandono**: nella formula della crescita netta viene incluso anche l’attrito (utenti inattivi). In questo modo, puoi valutare lo stato complessivo della tua base utenti nel tempo. Una crescita netta costantemente inferiore a `1`, ad esempio, indica un’elevata quantità di attrito e potrebbe quindi suggerire la necessità di implementare strategie di conservazione.

## Interfaccia

Per una panoramica dell’interfaccia dell’analisi guidata, consulta [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL View]**: consente di passare da questa analisi a [Crescita attiva](active-growth.md).
* **[!UICONTROL Events]**: l’evento che desideri misurare. Poiché questa analisi è basata sull’utente, vengono conteggiati come utenti attivi anche coloro che interagiscono con l’evento una volta nell’arco del periodo. Puoi includere un evento in una query.
* **[!UICONTROL Counted as]**: metodo di conteggio da applicare agli eventi selezionati. <ul><li>**[!UICONTROL Options]** include [!UICONTROL Number of users] e [!UICONTROL Percentage of users].</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} Ulteriori **[!UICONTROL B2B options]** sono disponibili per Customer Journey Analytics B2B edition: [!UICONTROL Global accounts], [!UICONTROL Accounts], [!UICONTROL Buying groups], [!UICONTROL Opportunities], [!UICONTROL Percentage of global accounts], [!UICONTROL Percentage of accounts], [!UICONTROL Percentage of buying groups] e [!UICONTROL Percentage of opportunities].</li></ul>
* **[!UICONTROL Segments]**: il segmento che desideri misurare. Puoi includere un segmento in una query.

### Confronto temporale

{{apply-time-comparison}}

### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è costituita da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono: Oraria, Giornaliera, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere una granularità diversa, da cui dipende il numero di punti dati nel grafico e il numero di colonne nella tabella. Nella visualizzazione di un’analisi di tre giorni con granularità giornaliera, ad esempio, saranno presenti solo tre punti dati, mentre in quella di un’analisi di tre giorni con granularità oraria ne saranno presenti 72.
* **[!UICONTROL Date]**: la data di inizio e di fine. Per comodità, sono disponibili intervalli di date continui predefiniti e intervalli personalizzati salvati in precedenza; in alternativa, puoi utilizzare il selettore del calendario per scegliere un intervallo di date fisso.

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
