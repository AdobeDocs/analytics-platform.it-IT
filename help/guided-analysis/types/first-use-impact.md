---
title: Analisi dell’impatto sul primo utilizzo
description: Misura l’impatto del primo utilizzo delle funzioni sugli indicatori chiave.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 6%

---

# Analisi [!UICONTROL First use impact] {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_firstuseimpact_button"
>title="Impatto sul primo utilizzo"
>abstract="Misura l’impatto del primo utilizzo delle funzioni sugli indicatori chiave."

<!-- markdownlint-enable MD034 -->

L&#39;analisi ![FirstUse](/help/assets/icons/FirstUse.svg) **[!UICONTROL First use impact]** mostra un confronto tra le prestazioni degli indicatori chiave prima e dopo che un utente utilizza una funzionalità di prodotto per la prima volta. L’asse orizzontale di questo rapporto è un intervallo di tempo relativo prima e dopo l’evento, mentre l’asse verticale misura gli indicatori chiave desiderati. Una barra verticale al centro del grafico rappresenta il giorno 0 del primo utilizzo di una caratteristica da parte di un utente specifico. Poiché gli utenti non adottano sempre le funzioni nello stesso giorno e i rollout possono potenzialmente verificarsi in più giorni, il giorno 0 può avere un significato diverso per ogni singolo utente.


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)


## Casi d’uso

I casi di utilizzo per questa analisi includono:

* **Nuova analisi delle funzionalità**: se stai avviando una nuova funzionalità nel tuo prodotto, puoi confrontare il modo in cui gli indicatori chiave sono stati eseguiti prima e dopo che gli utenti sono stati esposti a quella nuova funzionalità per la prima volta.
* **Rollout graduali**: poiché l&#39;analisi cerca il primo utilizzo della funzionalità anziché una data fissa, questa analisi è utile se si esegue il rollout graduale delle funzionalità nel tempo.
* **Analisi della versione del nuovo prodotto**: se stai avviando una nuova versione del prodotto, puoi confrontare il modo in cui gli indicatori chiave sono stati eseguiti prima e dopo che gli utenti sono stati esposti a quella nuova versione per la prima volta. Seleziona &quot;qualsiasi evento&quot; come evento di primo utilizzo e filtralo nella proprietà Numero versione.
* **Miglioramenti di funzionalità esistenti**: se stai apportando miglioramenti a una funzionalità esistente all&#39;interno del prodotto, puoi confrontare il modo in cui gli indicatori chiave hanno funzionato prima e dopo che gli utenti sono stati esposti a tali nuovi miglioramenti per la prima volta. Potete eseguire questa analisi in uno o più modi a seconda della strumentazione della feature.
   * Seleziona un evento che rappresenta il miglioramento come evento di primo utilizzo
   * Seleziona la data in cui è iniziato il rollout delle modifiche
   * Segmentare l’analisi per il gruppo di persone esposte ai miglioramenti
* **Efficacia della campagna**: quando un utente fa clic su una determinata campagna, puoi confrontare il modo in cui gli indicatori chiave hanno funzionato prima e dopo che l&#39;utente ha interagito con tale campagna.

## Interfaccia

Per una panoramica dell&#39;interfaccia di analisi guidata, vedere [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL View]**: Passare da questa analisi alla [versione](release-impact.md).
* **[!UICONTROL Key indicators]**: eventi che si desidera misurare per utente. Ogni indicatore chiave selezionato viene rappresentato da una linea colorata. Alla tabella viene aggiunta una riga che rappresenta l’evento. Puoi includere fino a tre eventi.
* **[!UICONTROL Counted as]**: metodo di conteggio da applicare agli eventi selezionati. Le opzioni includono [!UICONTROL Events per user], [!UICONTROL Events], [!UICONTROL Sessions] e [!UICONTROL Users].
* **[!UICONTROL Factors]**: ci sono due fattori per questa analisi:
   * **[!UICONTROL Date]**: quanto indietro vuoi iniziare a cercare il primo evento di utilizzo che si è verificato.
   * **[!UICONTROL Event]**: l&#39;evento di cui si desidera cercare il primo utilizzo, su cui basare l&#39;analisi.
* **[!UICONTROL Segments]**: il segmento che si desidera misurare. Il segmento selezionato filtra i dati in modo da concentrarti solo sui singoli utenti che corrispondono ai criteri del segmento. Per questa analisi è supportato un singolo segmento.

### Impostazioni grafico

L&#39;analisi [!UICONTROL First use impact] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Chart type]**: tipo di visualizzazione che si desidera utilizzare. Le opzioni includono Linea.

### Intervallo date

Le selezioni di date nell&#39;analisi [!UICONTROL First use impact] funzionano in modo diverso rispetto ad altre analisi, in quanto l&#39;analisi ruota attorno alla data specificata nella barra delle query. Sono disponibili le seguenti opzioni:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly] e [!UICONTROL Quarterly]. La modifica dell’intervallo influisce sulle opzioni disponibili per il periodo Prima e Dopo.
* **[!UICONTROL Before and after period]**: quantità di tempo da analizzare prima e dopo il primo evento di utilizzo specificato nella barra delle query. Le opzioni disponibili dipendono dalla selezione di [!UICONTROL Interval].

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
