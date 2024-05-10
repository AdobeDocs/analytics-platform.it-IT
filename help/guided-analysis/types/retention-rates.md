---
title: Tassi di mantenimento
description: Misura quanti utenti continuano a utilizzare il prodotto.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 1%

---

# Tassi di mantenimento

Il **[!UICONTROL Retention rates]** visualizza mostra il comportamento di utilizzo ripetuto degli utenti nel prodotto nel tempo, che può aiutarti a comprendere le esigenze del mercato del prodotto. In questa vista, l’asse orizzontale rappresenta il numero di giorni trascorsi dall’intervento iniziale di un utente e l’asse verticale rappresenta la percentuale di utenti che si impegnano nuovamente.

Questa analisi conta gli utenti in base a due eventi importanti:

* Evento iniziale: la prima volta che un utente si è attivato con l’evento entro l’intervallo di date
* Evento di ritorno: ora più recente in cui un utente si è impegnato con l’evento all’interno dell’intervallo di date analizzato

Il bucket di durata &quot;Giorno 0&quot; rappresenta il momento iniziale in cui un utente si è attivato con l’evento ed è sempre esattamente uguale al 100%. Questo bucket è il denominatore utilizzato per calcolare la percentuale di utenti mantenuti.

I successivi periodi fissi di durata contano il numero di utenti che sono ritornati durante o dopo tale durata. Questo conteggio è il numeratore utilizzato per calcolare la percentuale di utenti mantenuti.

* Se un utente si impegna con l’evento una sola volta nell’intervallo di date desiderato (il coinvolgimento iniziale), questo viene visualizzato solo nel bucket di durata &quot;Giorno 0&quot;.
* Se un utente si impegna con l’evento più giorni dopo aver ottenuto inizialmente la qualifica per l’inclusione nell’analisi, vengono visualizzati nell’ultimo bucket di durata ammissibile e in tutti i bucket di durata che lo precedono. Questo tipo di calcolo viene talvolta definito &quot;conservazione non limitata&quot;. Puoi modificare questa impostazione di calcolo nella barra delle query.

Gli utenti idonei per i periodi fissi di durata si basano sul tempo trascorso e non sul giorno del calendario. Ad esempio, se un utente si qualifica per un evento alle 23:55 del 6 settembre e poi per un evento di ritorno alle 00:05 del 7 settembre, non verrà visualizzato nel bucket di durata di 1 giorno. Devono trascorrere 24 ore prima che l’utente possa qualificarsi per il periodo fisso di durata di 1 giorno.

![Schermata Tassi di mantenimento](../assets/retention-rates.png){style="border:1px solid gray"}

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Analisi per coorte**: raggruppa gli utenti in coorti basate sulle azioni da loro intraprese, ad esempio iscrizioni o acquisti. Puoi confrontare il livello di mantenimento di questi gruppi e determinare come affrontare il miglioramento dell’esperienza utente di ciascun gruppo.
* **Adattabilità al mercato del prodotto**: misura l’utilizzo regolare del prodotto e visualizzalo come curve di fidelizzazione. Una maggiore fidelizzazione significa una maggiore aderenza al mercato del prodotto e la posizione in cui la curva si appiattisce indica quanto tempo è necessario per raggiungere l’adesione. Puoi visualizzare questa analisi a livello generale o suddividerla per singole funzioni del prodotto, per ottenere informazioni più approfondite.
* **Analisi del servizio di abbonamento**: se il tuo prodotto utilizza un abbonamento o un altro tipo di modello di ricavo ricorrente, puoi vedere la percentuale di utenti che stanno sfruttando al meglio il tuo prodotto. Puoi identificare alcune qualità e comportamenti che questi utenti mostrano.
* **Coinvolgimento degli utenti**: valuta il modo in cui alcuni tipi di utenti interagiscono con il prodotto e confronta insieme la frequenza con cui ritornano. Un dato segmento con una fidelizzazione inferiore rispetto ad altri può fornirti informazioni sul miglioramento di potenziali esperienze secondarie che potrebbero avere.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Start event]**: i criteri dell’evento con cui un utente deve interagire per qualificarsi per l’inclusione nell’analisi. Gli utenti che interagiscono con l’evento di inizio vengono inclusi nel bucket iniziale di utenti che totalizza il 100%. È supportato un evento, ma puoi includere filtri di proprietà. Puoi collegare gli eventi di inizio e ritorno utilizzando il menu a tre punti. Il collegamento degli eventi di inizio e di ritorno indica che i criteri da visualizzare nel bucket di durata iniziale e nei bucket di durata successivi sono gli stessi.
* **[!UICONTROL Return events]**: i criteri dell’evento con cui un utente deve interagire per qualificarsi per l’inclusione nei periodi fissi di durata successivi. Puoi selezionare fino a tre eventi di ritorno. Ogni evento di ritorno genera un’analisi affiancata con gli altri eventi di ritorno inclusi.
* **[!UICONTROL Counted as]**: metodo di conteggio che desideri applicare agli utenti mantenuti. Le opzioni includono:
   * **[!UICONTROL Metric]**: conteggio del numero di [!UICONTROL Users retained] o [!UICONTROL Percentage of users retained].
   * **[!UICONTROL Returning]**: per impostazione predefinita, questa analisi include gli utenti nel bucket restituito e in tutti i bucket precedenti. Cambia questa impostazione in **[!UICONTROL On exactly]** per includere gli utenti solo nel bucket esatto per il quale sono idonei.
   * **[!UICONTROL Each]**: il periodo di tempo desiderato per ogni bucket di durata. Questa impostazione è identica a **[!UICONTROL Interval]** quando si seleziona l’intervallo di date.
   * **[!UICONTROL Duration settings]**: consente di controllare la modalità di visualizzazione degli utenti nell’analisi in base al numero di giorni trascorsi. I periodi fissi di durata disponibili dipendono dall’intervallo di date impostato. **[!UICONTROL Auto durations]** imposta automaticamente i periodi fissi di durata in base alla lunghezza dell’intervallo di date e alla vicinanza al giorno corrente in cui si trova l’intervallo di date. **[!UICONTROL Custom durations]** consente di impostare manualmente quattro periodi fissi di durata agli intervalli desiderati.
* **[!UICONTROL Segments]**: i segmenti che desideri misurare. Ogni segmento selezionato aggiunge una riga alla tabella coorte. Puoi includere fino a tre segmenti.

## Impostazioni grafico

Il [!UICONTROL Retention rates] visualizza offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Chart type]**: tipo di visualizzazione che desideri utilizzare. Le opzioni includono [!UICONTROL Bar] e [!UICONTROL Line]. La visualizzazione delle linee mostra visivamente il giorno 0 nel grafico.

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati di conservazione. Le opzioni valide includono Giornaliero, Settimanale e Mensile. Lo stesso intervallo di date può avere intervalli diversi, che influiscono sulle opzioni del periodo fisso di durata.
* **[!UICONTROL Date]**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.

Se selezioni un intervallo di date vicino al giorno corrente, gli utenti che inizialmente si impegnano troppo vicino al giorno corrente non vengono inclusi. Questa analisi offre sempre a tutti gli utenti la possibilità di essere inclusi in tutti i bucket di durata. Un messaggio sotto la selezione del calendario fornisce informazioni sull&#39;intervallo di date in cui gli utenti interagiscono e sull&#39;intervallo riservato solo agli utenti di ritorno:

* **[!UICONTROL Analyzing users who did the start event in [Date interval]]**: se un utente interagisce con l’evento all’interno di questo intervallo di date, viene incluso nell’analisi. Questo intervallo di date garantisce a tutti gli utenti un tempo sufficiente per qualificarsi per tutti i periodi fissi di durata. Questo intervallo di date può essere diverso dalla selezione se è vicino al giorno corrente.
* **[!UICONTROL Data from [Date interval] is reserved to complete the analysis]**: se un utente si impegna per la prima volta in questo periodo, **non** inclusi nell’analisi. Per gli intervalli di date recenti, questi utenti non avrebbero l’opportunità di qualificarsi per tutti i periodi fissi di durata. Per gli intervalli di date passati, questi utenti erano attivi al di fuori dell’intervallo di date selezionato.

## Tabella coorte

La tabella sotto il grafico fornisce una vista aggregata (simile ai dati del grafico) e una tabella coorte completa. La tabella coorte completa fornisce i dettagli di ogni singolo intervallo di date e di quando gli utenti si sono impegnati.
