---
title: Tassi di mantenimento
description: Misura quanti utenti continuano a utilizzare il prodotto.
feature: Guided Analysis
keywords: analisi dei prodotti
hide: true
hidefromtoc: true
source-git-commit: 1cadf9d863c18f590a99e22d7b0e79b1074bf29f
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 1%

---

# Tassi di mantenimento

{{release-limited-testing}}

Il **[!UICONTROL Retention rates]** visualizza mostra la percentuale di utenti che tornano dopo il coinvolgimento iniziale entro l’intervallo di date desiderato. L’asse orizzontale rappresenta il numero di giorni trascorsi dall’intervento iniziale di un utente. L’asse verticale rappresenta la percentuale di utenti che si impegnano nuovamente.

Questa analisi conta gli utenti in base a due eventi importanti:

* Evento iniziale: la prima volta che un utente si è attivato con l’evento entro l’intervallo di date
* Evento di ritorno: ora più recente in cui un utente si è impegnato con l’evento all’interno dell’intervallo di date analizzato

Il bucket di durata &quot;Giorno 0&quot; rappresenta il momento iniziale in cui un utente si è attivato con l’evento ed è sempre esattamente uguale al 100%. Questo bucket è il denominatore utilizzato per calcolare la percentuale di utenti mantenuti.

I successivi periodi fissi di durata contano il numero di utenti che sono ritornati durante o dopo tale durata. Questo conteggio è il numeratore utilizzato per calcolare la percentuale di utenti mantenuti.

* Se un utente si impegna con l’evento una sola volta nell’intervallo di date desiderato (il coinvolgimento iniziale), questo viene visualizzato solo nel bucket di durata &quot;Giorno 0&quot;.
* Se un utente si impegna con l’evento più giorni dopo aver ottenuto inizialmente la qualifica per l’inclusione nell’analisi, vengono visualizzati nell’ultimo bucket di durata ammissibile e in tutti i bucket di durata che lo precedono. Questo tipo di calcolo è talvolta indicato come &quot;conservazione non limitata&quot;.
* Se un utente si impegna più volte con l’evento durante l’intervallo di date configurato, nell’analisi vengono inclusi solo il primo e l’ultimo evento.

![Schermata Tassi di mantenimento](../assets/retention-rates.png)

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Analisi per coorte**: raggruppa gli utenti in coorti basate sulle azioni da loro intraprese, ad esempio iscrizioni o acquisti. Puoi confrontare il livello di mantenimento di questi gruppi e determinare come affrontare il miglioramento dell’esperienza utente di ciascun gruppo.
* **Analisi del servizio di abbonamento**: se il tuo prodotto utilizza un abbonamento o un altro tipo di modello di ricavo ricorrente, puoi vedere la percentuale di utenti che stanno sfruttando al meglio il tuo prodotto. Puoi identificare alcune qualità e comportamenti che questi utenti mostrano per comprendere meglio come si adatta il tuo mercato di prodotto.
* **Coinvolgimento degli utenti**: valuta il modo in cui alcuni tipi di utenti interagiscono con il prodotto e confronta insieme la frequenza con cui ritornano. Un dato segmento con una fidelizzazione inferiore rispetto ad altri può fornirti informazioni sul miglioramento di potenziali esperienze secondarie che potrebbero avere.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Start & return event]**: i criteri dell’evento con cui un utente deve interagire per qualificarsi per l’inclusione nell’analisi. È supportato un evento, ma puoi includere filtri di proprietà.
* **[!UICONTROL People]**: i segmenti che desideri misurare. Ogni segmento selezionato aggiunge una riga alla tabella coorte. Puoi includere fino a tre segmenti.

## Impostazioni grafico

Il [!UICONTROL Retention rates] visualizza offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Metric]**: come desideri misurare il mantenimento degli utenti. Le opzioni includono [!UICONTROL Users retained] e [!UICONTROL Percentage of users retained].
* **[!UICONTROL Chart type]**: tipo di visualizzazione che desideri utilizzare. Le opzioni includono [!UICONTROL Bar] e [!UICONTROL Line].

## Impostazioni durata

Consente di controllare il modo in cui l’analisi visualizza gli utenti in base al numero di giorni trascorsi.

* **[!UICONTROL Auto durations]**: imposta automaticamente le durate in base alla lunghezza dell’intervallo di date e alla vicinanza al giorno corrente in cui si trova l’intervallo di date. I bucket di durata sono curati per i casi d’uso più comuni.
* **[!UICONTROL Custom durations]**: imposta manualmente gli intervalli desiderati. È possibile impostare quattro durate.

I periodi fissi di durata disponibili dipendono dall’intervallo di date impostato.

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati di conservazione. Le opzioni valide includono Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi, che influiscono sull’impostazione automatica dei periodi fissi di durata.
* **[!UICONTROL Date]**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.

Se selezioni un intervallo di date vicino al giorno corrente, gli utenti che inizialmente si impegnano troppo vicino al giorno corrente non vengono inclusi. Questa analisi offre sempre a tutti gli utenti la possibilità di essere inclusi in tutti i bucket di durata. Un messaggio sotto la selezione del calendario fornisce informazioni sull’intervallo di date in cui gli utenti interagiscono e sull’intervallo riservato solo agli utenti di ritorno:

* **Analisi degli utenti che hanno eseguito l&#39;evento di avvio in [Intervallo date]**: se un utente interagisce con l’evento all’interno di questo intervallo di date, viene incluso nell’analisi. Questo intervallo di date garantisce a tutti gli utenti un tempo sufficiente per qualificarsi per tutti i periodi fissi di durata. Questo intervallo di date può essere diverso dalla selezione se è vicino al giorno corrente.
* **Dati da [Intervallo date] si riserva di completare l’analisi**: se un utente si impegna per la prima volta in questo periodo, **non** inclusi nell’analisi. Per gli intervalli di date recenti, questi utenti non avrebbero l’opportunità di qualificarsi per tutti i periodi fissi di durata. Per gli intervalli di date passati, questi utenti erano attivi al di fuori dell’intervallo di date selezionato.

## Tabella coorte

La tabella sotto il grafico fornisce una vista aggregata (simile ai dati del grafico) e una tabella coorte completa. La tabella coorte completa fornisce dettagli su ogni singolo intervallo di date e su quando gli utenti si sono impegnati.
