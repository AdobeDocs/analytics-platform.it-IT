---
title: Analisi dell’impatto sulle versioni
description: Confronta le prestazioni in periodi uguali prima e dopo la versione.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '494'
ht-degree: 100%

---

# [!UICONTROL Release impact] analisi {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_releaseimpact_button"
>title="Impatto della versione"
>abstract="Confronta le prestazioni in periodi uguali prima e dopo la versione."

<!-- markdownlint-enable MD034 -->

L’analisi dell’**[!UICONTROL Release impact]** ![Release](/help/assets/icons/Release.svg) mostra un confronto tra le prestazioni degli indicatori chiave prima e dopo una determinata data. L’asse orizzontale di questo rapporto è un intervallo di tempo, mentre l’asse verticale misura gli indicatori chiave desiderati. Una barra verticale al centro del grafico rappresenta la data che si desidera confrontare prima e dopo. In genere, questa data rappresenta una modifica rilevante del prodotto su cui desideri effettuare la misurazione, ad esempio un aggiornamento del prodotto o il lancio di una campagna.

>[!VIDEO](https://video.tv.adobe.com/v/3423450/?quality=12&learn=on&captions=ita)

## Casi d’uso

I casi d’uso per questa analisi includono:

* **Valutazione complessiva delle prestazioni:** il confronto di indicatori chiave generali, come le misure di coinvolgimento, può aiutarti a determinare se una determinata versione ha avuto complessivamente esito positivo.
* **Monitoraggio**: tieni traccia delle metriche vitali che prevedi rimangano invariate quando vengono apportate modifiche, ad esempio il tempo di caricamento o il numero di accessi. Utilizza questa analisi per confrontarli prima e dopo una versione per assicurarti che non abbia avuto conseguenze indesiderate.
* **Adozione di funzione**: se un aggiornamento di prodotto è incentrato sul miglioramento di una determinata funzione, puoi utilizzare questa analisi per confrontare direttamente l’utilizzo di tale funzione prima e dopo l’aggiornamento del prodotto.
* **Rilevamento bug**: tracciare il numero di errori prima e dopo una versione può fornire un indicatore anticipato dei problemi della clientela. Se noti un aumento di errori subito dopo una versione, puoi collaborare con i team di progettazione o di sviluppo per identificare e correggere il problema, evitando un ulteriore impatto sulla clientela.

## Interfaccia

Per una panoramica dell’interfaccia dell’analisi guidata, consulta [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL View]**: passa da questa analisi a [Impatto primo utilizzo](first-use-impact.md).
* **[!UICONTROL Key indicators]**: gli eventi che desideri misurare per utente. Ogni indicatore chiave selezionato viene rappresentato da una linea colorata. Alla tabella viene aggiunta una riga che rappresenta l’evento. Puoi includere fino a tre eventi.
* **[!UICONTROL Counted as]**: il metodo di conteggio che desideri applicare agli eventi selezionati. Le opzioni includono [!UICONTROL Events per user], [!UICONTROL Percentage of users], [!UICONTROL Events], [!UICONTROL Sessions] e [!UICONTROL Users].
* **[!UICONTROL Factors]**: la data che desideri confrontare prima e dopo.
* **[!UICONTROL Segments]**: il segmentoi che desideri misurare. Il segmento selezionato filtra i dati in modo da concentrarti solo sui singoli utenti che corrispondono ai criteri del segmento.

### Impostazioni del grafico

L’analisi della[!UICONTROL Release impact] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Chart type]**: il tipo divisualizzazione che vuoi usare. Le opzioni includono [!UICONTROL Line] e [!UICONTROL Bar].

### Intervallo date

La selezione della data nell’analisi dell’impatto funziona in modo diverso rispetto ad altre analisi, in quanto il rapporto ruota attorno alla data specificata nella barra delle query. Sono disponibili le seguenti opzioni:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly] e [!UICONTROL Quarterly]. La modifica dell’intervallo influisce sulle opzioni disponibili per il periodo Prima e Dopo.
* **[!UICONTROL Before and after period]**: quantità di tempo da analizzare prima e dopo la data specificata nella barra delle query. Le opzioni disponibili dipendono dalla selezione dell’[!UICONTROL Interval].


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
