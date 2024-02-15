---
title: Vista primo utilizzo
description: Misura l’impatto del primo utilizzo delle funzioni sugli indicatori chiave.
feature: Guided Analysis
keywords: analisi dei prodotti
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: de78569389f5a9d74603870e72b4f3871ef4aa92
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 1%

---

# [!UICONTROL First use] visualizza

Il **[!UICONTROL First use]** La vista mostra un confronto tra le prestazioni degli indicatori chiave prima e dopo che un utente utilizza una funzione del prodotto per la prima volta. L’asse orizzontale di questo rapporto è un intervallo di tempo relativo prima e dopo l’evento, mentre l’asse verticale misura gli indicatori chiave desiderati. Una barra verticale al centro del grafico rappresenta il giorno 0 del primo utilizzo di una caratteristica da parte di un utente specifico. Poiché gli utenti non adottano sempre le funzioni nello stesso giorno e i rollout possono potenzialmente verificarsi in più giorni, il giorno 0 può avere un significato diverso per ogni singolo utente.

>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Nuova analisi delle feature**: se avvii una nuova funzione all’interno del prodotto, puoi confrontare il modo in cui gli indicatori chiave vengono eseguiti prima e dopo che gli utenti sono stati esposti a tale nuova funzione per la prima volta.
* **Rollout graduali**: poiché l’analisi cerca il primo utilizzo della funzione anziché una data fissa, questa visualizzazione è utile se si esegue il rollout graduale delle funzioni nel tempo.
* **Analisi della versione del nuovo prodotto**: se avvii una nuova versione del prodotto, puoi confrontare il modo in cui gli indicatori chiave vengono eseguiti prima e dopo che gli utenti sono stati esposti a tale nuova versione per la prima volta. Seleziona &quot;qualsiasi evento&quot; come evento di primo utilizzo e filtralo nella proprietà Numero versione.
* **Miglioramenti delle funzioni esistenti**: se stai apportando miglioramenti a una funzione esistente nel tuo prodotto, puoi confrontare il modo in cui gli indicatori chiave venivano eseguiti prima e dopo che gli utenti erano stati esposti a tali nuovi miglioramenti per la prima volta. Potete eseguire questa analisi in uno o più modi a seconda della strumentazione della feature.
   * Seleziona un evento che rappresenta il miglioramento come evento di primo utilizzo
   * Seleziona la data in cui è iniziato il rollout delle modifiche
   * Segmentare l’analisi per il gruppo di persone esposte ai miglioramenti
* **Efficacia della campagna**: quando un utente fa clic su da una determinata campagna, puoi confrontare il modo in cui gli indicatori chiave hanno funzionato prima e dopo che l’utente ha interagito con tale campagna.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL View]**: passa da questo tipo di visualizzazione a [Versione](release.md).
* **[!UICONTROL Key indicators]**: gli eventi che desideri misurare per utente. Ogni indicatore chiave selezionato viene rappresentato da una linea colorata. Alla tabella viene aggiunta una riga che rappresenta l’evento. Puoi includere fino a tre eventi.
* **[!UICONTROL Counted as]**: la metrica da misurare. Le opzioni includono [!UICONTROL Events per user], [!UICONTROL Events], [!UICONTROL Sessions], e [!UICONTROL Users].
* **[!UICONTROL Factors]**: ci sono due fattori per questa visualizzazione:
   * **[!UICONTROL Date]**: quanto indietro vuoi iniziare a cercare il primo evento di utilizzo che si è verificato.
   * **[!UICONTROL Event]**: l’evento di cui desideri cercare il primo utilizzo, su cui centrare l’analisi.
* **[!UICONTROL Segments]**: il segmento che desideri misurare. Il segmento selezionato filtra i dati in modo da concentrarti solo sui singoli utenti che corrispondono ai criteri del segmento. Per questo tipo di visualizzazione è supportato un singolo segmento.

## Impostazioni grafico

La vista Primo utilizzo offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Chart type]**: tipo di visualizzazione che desideri utilizzare. Le opzioni includono Linea.

## Intervallo date

Le selezioni di date nell’analisi di impatto funzionano in modo diverso rispetto ad altri tipi di analisi, in quanto l’analisi ruota attorno alla data specificata nella barra delle query. Sono disponibili le seguenti opzioni:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly], e [!UICONTROL Quarterly]. La modifica dell’intervallo influisce sulle opzioni disponibili per il periodo Prima e Dopo.
* **[!UICONTROL Before and after period]**: tempo di analisi prima e dopo il primo evento di utilizzo specificato nella barra delle query. Le opzioni disponibili dipendono dal [!UICONTROL Interval] selezione.
