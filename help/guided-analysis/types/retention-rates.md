---
title: Tassi di mantenimento
description: Misura quanti utenti continuano a utilizzare il prodotto.
feature: Guided Analysis
keywords: analisi dei prodotti
source-git-commit: 74525c4ce9ad1fd3f3abf35a9d9cb2c521d23874
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 1%

---

# Tassi di mantenimento

Il **[!UICONTROL Retention rates]** visualizza mostra la percentuale di utenti che tornano dopo il coinvolgimento iniziale entro l’intervallo di date desiderato. L’asse orizzontale rappresenta il numero di giorni trascorsi dal primo coinvolgimento di un utente. L’asse verticale rappresenta la percentuale di utenti che si impegnano nuovamente.

Questa analisi conta gli utenti in base a due eventi importanti:

* La prima volta che un utente si è interessato all’evento entro l’intervallo di date
* Ora più recente in cui un utente si è impegnato con l’evento all’interno dell’intervallo di date analizzato

Il bucket di durata &quot;giorno 0&quot; rappresenta la prima volta che un utente si interagisce con l’evento ed è sempre uguale esattamente al 100%. Il tempo che intercorre tra il coinvolgimento iniziale e l’accordo di ritorno determina la posizione in cui l’utente viene visualizzato.

* Se un utente si connette all’evento una sola volta nell’intervallo di date desiderato (l’engagement iniziale), questo viene visualizzato solo nel bucket &quot;giorno 0&quot;.
* Se un utente si impegna con l’evento più giorni dopo aver ottenuto inizialmente la qualifica per l’inclusione nell’analisi, vengono visualizzati nell’ultimo bucket di durata ammissibile e in tutti i bucket di durata che lo precedono.
* Se un utente si impegna più volte con l’evento durante l’intervallo di date configurato, nell’analisi vengono inclusi solo il primo e l’ultimo evento.

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Analisi per coorte**: raggruppa gli utenti in coorti basate su qualsiasi evento, ad esempio iscrizioni o acquisti. Puoi confrontare la fedeltà di questi gruppi e determinare come approcciare il miglioramento dell’esperienza utente del gruppo.
* **Analisi del servizio di abbonamento**: se il tuo prodotto utilizza un abbonamento o un altro tipo di modello di ricavo ricorrente, puoi vedere la percentuale di utenti che stanno sfruttando al meglio il tuo prodotto. Coloro che non utilizzano il prodotto o il servizio hanno maggiori probabilità di abbandono, consentendoti di identificare e concentrarsi su tali utenti.
* **Coinvolgimento degli utenti**: valuta il modo in cui alcuni tipi di utenti interagiscono con il prodotto e confronta insieme la frequenza con cui ritornano. Un dato segmento con una curva di fidelizzazione più ripida rispetto ad altri può fornirti informazioni sul miglioramento di potenziali esperienze secondarie che potrebbero avere.

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

* **[!UICONTROL Auto durations]**: imposta automaticamente le durate in base alla lunghezza dell’intervallo di date e alla vicinanza al giorno corrente in cui si trova l’intervallo di date.
* **[!UICONTROL Custom durations]**: imposta manualmente i giorni trascorsi desiderati. È possibile impostare quattro durate.

Non è possibile impostare una durata superiore al tempo necessario a un utente per interagire con un evento e qualificarsi per l’ultimo periodo fisso di durata prima di raggiungere il giorno corrente. Ad esempio, se la data corrente è il 30 settembre e l’intervallo di date configurato è dal 1° al 30 settembre, la durata massima per questo intervallo di date è di 14 giorni.

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data desiderata per visualizzare i dati di conservazione. Le opzioni valide includono Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi, che influiscono sull’impostazione automatica dei giorni di durata.
* **[!UICONTROL Date]**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.

Se selezioni un intervallo di date vicino al giorno corrente, gli utenti che inizialmente si impegnano troppo vicino al giorno corrente non vengono inclusi. Questa analisi offre sempre a tutti gli utenti la possibilità di essere inclusi in tutti i bucket di durata. Un messaggio sotto la selezione del calendario fornisce informazioni sull’intervallo di date in cui gli utenti interagiscono e sull’intervallo riservato solo agli utenti di ritorno:

* **Analisi della prima [Intervallo date] della coorte da [Intervallo di date]**: se un utente interagisce con l’evento all’interno di questo intervallo di date, viene incluso nell’analisi. Questo intervallo di date garantisce a tutti gli utenti un tempo sufficiente per qualificarsi per tutti i periodi fissi di durata. Questo intervallo di date può essere diverso dalla selezione se è vicino al giorno corrente.
* **La versione finale [Intervallo date] si riserva di completare l’analisi**: se un utente si connette all’evento per la prima volta in questo intervallo, **non** inclusi nell’analisi. Gli utenti che inizialmente interagiscono con l’evento entro questo intervallo non avrebbero l’opportunità di qualificarsi per tutti i bucket di durata o non rientrano nell’intervallo di date desiderato.

## Tabella coorte

La tabella sotto il grafico fornisce una vista aggregata (simile ai dati del grafico) e una tabella coorte completa. La tabella coorte completa fornisce dettagli su ogni singolo intervallo di date e su quando gli utenti si sono impegnati.
