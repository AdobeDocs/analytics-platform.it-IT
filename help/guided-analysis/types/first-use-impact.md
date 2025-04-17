---
title: Analisi dell’impatto sul primo utilizzo
description: Misura l’impatto del primo utilizzo delle funzioni sugli indicatori chiave.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '635'
ht-degree: 100%

---

# [!UICONTROL First use impact] analisi {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_firstuseimpact_button"
>title="Impatto sul primo utilizzo"
>abstract="Misura l’impatto del primo utilizzo delle funzioni sugli indicatori chiave."

<!-- markdownlint-enable MD034 -->

L’analisi ![FirstUse](/help/assets/icons/FirstUse.svg) **[!UICONTROL First use impact]** mostra un confronto tra le prestazioni degli indicatori chiave prima e dopo che un utente utilizza una funzionalità di prodotto per la prima volta. L’asse orizzontale di questo rapporto è un intervallo di tempo relativo prima e dopo l’evento, mentre l’asse verticale misura gli indicatori chiave desiderati. Una barra verticale al centro del grafico rappresenta il giorno 0 del primo utilizzo di una caratteristica da parte di un utente specifico. Poiché gli utenti non adottano sempre le funzioni nello stesso giorno e i rollout possono potenzialmente verificarsi in più giorni, il giorno 0 può avere un significato diverso per ogni singolo utente.


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?quality=12&learn=on)


## Casi d’uso

I casi d’uso per questa analisi includono:

* **Nuova analisi delle funzionalità**: se stai avviando una nuova funzionalità nel tuo prodotto, puoi confrontare il modo in cui gli indicatori chiave sono stati eseguiti prima e dopo che gli utenti sono stati esposti a quella nuova funzionalità per la prima volta.
* **Rollout graduali**: poiché l’analisi cerca il primo utilizzo della funzionalità anziché una data fissa, questa analisi è utile se si esegue il rollout graduale delle funzionalità nel tempo.
* **Analisi della versione del nuovo prodotto**: se stai avviando una nuova versione del prodotto, puoi confrontare le prestazioni degli indicatori chiave prima e dopo l’esposizione degli utenti alla nuova versione per la prima volta. Seleziona “qualsiasi evento” come evento di primo utilizzo e filtralo nella proprietà Numero versione.
* **Miglioramenti di funzionalità esistenti**: se stai apportando miglioramenti a una funzionalità esistente all’interno del prodotto, puoi confrontare le prestazioni degli indicatori chiave prima e dopo l’esposizione degli utenti a tali nuovi miglioramenti per la prima volta. Puoi eseguire questa analisi in uno o più modi, a seconda della strumentazione della funzionalità.
   * Seleziona un evento che rappresenta il miglioramento come evento di primo utilizzo
   * Seleziona la data in cui è iniziato il rollout delle modifiche
   * Segmenta l’analisi per il gruppo di persone esposte ai miglioramenti
* **Efficacia di una campagna**: quando un utente fa clic su una determinata campagna, puoi confrontare le prestazioni degli indicatori chiave prima e dopo l’interazione dell’utente con tale campagna.

## Interfaccia

Per una panoramica dell’interfaccia di analisi guidata, consulta [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL View]**: consente di passare da questa analisi a [Versione](release-impact.md).
* **[!UICONTROL Key indicators]**: gli eventi che desideri misurare, per utente. Ogni indicatore chiave selezionato viene rappresentato da una linea colorata. Alla tabella viene aggiunta una riga che rappresenta l’evento. Puoi includere fino a tre eventi.
* **[!UICONTROL Counted as]**: metodo di conteggio che desideri applicare agli eventi selezionati. Le opzioni includono [!UICONTROL Events per user], [!UICONTROL Events], [!UICONTROL Sessions] e [!UICONTROL Users].
* **[!UICONTROL Factors]**: ci sono due fattori per questa analisi:
   * **[!UICONTROL Date]**: quanto indietro vuoi iniziare a cercare l’occorrenza del primo evento di utilizzo.
   * **[!UICONTROL Event]**: l’evento di cui desideri cercare il primo utilizzo, su cui basare l’analisi.
* **[!UICONTROL Segments]**: i segmenti che desideri misurare. Il segmento selezionato filtra i dati in modo da concentrarti solo sui singoli utenti che corrispondono ai criteri del segmento. Per questa analisi è supportato un singolo segmento.

### Impostazioni del grafico

L’analisi [!UICONTROL First use impact] offre le seguenti impostazioni di grafico, che possono essere regolate nel menu sopra di esso:

* **[!UICONTROL Chart type]**: tipo dio visualizzazione che desideri usare. Le opzioni includono Linea.

### Intervallo date

Le selezioni di date nell’analisi [!UICONTROL First use impact] funzionano in modo diverso rispetto ad altre analisi, in quanto questa analisi ruota attorno alla data specificata nella barra delle query. Sono disponibili le seguenti opzioni:

* **[!UICONTROL Interval]**: granularità della data in base alla quale desideri visualizzare i dati con tendenze. Le opzioni valide includono [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly] e [!UICONTROL Quarterly]. La modifica dell’intervallo influisce sulle opzioni disponibili per il periodo Prima e Dopo.
* **[!UICONTROL Before and after period]**: quantità di tempo da analizzare prima e dopo l’evento di primo utilizzo specificato nella barra delle query. Le opzioni disponibili dipendono dalla selezione dell’[!UICONTROL Interval].

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
