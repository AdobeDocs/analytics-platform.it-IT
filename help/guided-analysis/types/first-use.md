---
title: Vista primo utilizzo
description: Misura l’impatto del primo utilizzo delle funzioni sugli indicatori chiave.
feature: Guided Analysis
source-git-commit: 9fa4b894e69a25b26632a93f00a655eec8e8aa86
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 3%

---

# Vista primo utilizzo

{{release-limited-testing}}

Il **Primo utilizzo** visualizza mostra un confronto tra le prestazioni degli indicatori chiave prima e dopo che un utente ha toccato un dato evento per la prima volta. L’asse orizzontale di questo rapporto è un intervallo di tempo relativo prima e dopo l’evento, mentre l’asse verticale misura gli indicatori chiave desiderati. Una barra verticale al centro del grafico rappresenta il momento in cui si è verificato l&#39;evento per un determinato utente.

![del prossimo maggio (?)](../assets/first-use.png)

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Nuova analisi delle feature**: se avvii una nuova funzione all’interno del prodotto, puoi confrontare il modo in cui gli indicatori chiave vengono eseguiti prima e dopo che gli utenti sono stati esposti a tale nuova funzione per la prima volta.
* **Efficacia della campagna**: quando un utente visualizza una determinata campagna, puoi confrontare il modo in cui gli indicatori chiave vengono eseguiti prima e dopo che l’utente ha visto la campagna o ha interagito con essa.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **Indicatori chiave**: gli eventi che desideri misurare per utente. Ogni indicatore chiave selezionato viene rappresentato da una linea colorata. Alla tabella viene aggiunta una riga che rappresenta l’evento. Puoi includere fino a tre eventi.
* **Fattori**: ci sono due fattori per questa visualizzazione:
   * **Data**: quando indietro desideri cercare la prima volta che un evento è stato toccato.
   * **Evento**: l’evento che desideri confrontare prima e dopo che è stato toccato.
* **Persone**: il segmento che desideri misurare. Il segmento selezionato filtra i dati in modo da concentrarti solo sui singoli utenti che corrispondono ai criteri del segmento.

## Impostazioni grafico

La vista Primo utilizzo offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **Metrica**: la metrica da misurare. Le opzioni includono [!UICONTROL Events per user], [!UICONTROL Events], [!UICONTROL Sessions],  e [!UICONTROL Users].
* **Tipo di grafico**: tipo di visualizzazione che desideri utilizzare. Le opzioni includono Linea.

## Intervallo date

Le selezioni delle date nei rapporti di impatto operano in modo diverso rispetto ad altri tipi di analisi, in quanto il rapporto ruota intorno a un dato evento toccato per la prima volta (specificato nella barra delle query). Sono disponibili le seguenti opzioni:

* **Interval**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly], e [!UICONTROL Quarterly]. La modifica dell’intervallo influisce sulle opzioni disponibili per il periodo Prima e Dopo.
* **Periodo prima e dopo**: tempo di analisi prima e dopo l’evento toccato specificato nella barra delle query. Le opzioni disponibili dipendono dal [!UICONTROL Interval] selezione.
