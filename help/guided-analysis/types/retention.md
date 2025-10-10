---
title: Analisi conservazione
description: Misura quanti utenti continuano a utilizzare il prodotto.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 97%

---

# Analisi conservazione {#retention}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_retention_button"
>title="Conservazione"
>abstract="Misura quanti utenti continuano a utilizzare il prodotto."

<!-- markdownlint-enable MD034 -->

L’analisi ![Fidelizzazione](/help/assets/icons/Retention.svg) **[!UICONTROL Retention]** misura il modo in cui gli utenti continuano a utilizzare il prodotto nel tempo, il che può aiutarti a comprendere l’attabilità del tuo prodotto al mercato. L’analisi conta gli utenti in base a due eventi importanti:

* Evento iniziale: evento utilizzato per qualificare gli utenti da includere nell’analisi.
* Evento di ritorno: uno o più eventi con cui un utente deve interagire per essere considerato un utente di ritorno nell’analisi.

In questa analisi, l’asse x del grafico rappresenta il tempo trascorso dall’evento iniziale di un utente e l’asse y rappresenta la percentuale di utenti che interagiscono con uno o più eventi di ritorno. È possibile visualizzare sia la fidelizzazione che l’abbandono tra le diverse durate, e le durate visualizzate possono essere personalizzate tramite le impostazioni della query. Sotto il grafico, una tabella fornisce dati aggregati con l’opzione di mostrare le singole coorti, che sono un gruppo di persone che hanno attivato l’evento iniziale nella stessa data.

>[!VIDEO](https://video.tv.adobe.com/v/3430503/?quality=12&learn=on)


## Casi d’uso

I casi d’uso per questa analisi includono:

* **Analisi per coorte**: raggruppa gli utenti in coorti in base alle azioni da loro intraprese, ad esempio iscrizioni o acquisti. Puoi confrontare il livello di conservazione di questi gruppi e determinare come affrontare il miglioramento dell’esperienza utente di ciascun gruppo.
* **Adattabilità del prodotto al mercato**: misura l’utilizzo regolare del prodotto e visualizza curve di fidelizzazione. Una maggiore fidelizzazione significa una maggiore adattabilità del prodotto al mercato e la posizione in cui la curva si appiattisce indica quanto tempo è necessario per raggiungerla. Puoi visualizzare questa analisi a livello generale o raggrupparla per singole funzioni del prodotto, per ottenere informazioni più approfondite.
* **Analisi del servizio in abbonamento**: se il prodotto utilizza un abbonamento o un altro tipo di modello di ricavi ricorrenti, puoi vedere la percentuale di utenti che lo stanno utilizzando al meglio. Puoi identificare alcune qualità e comportamenti che accomunano questi utenti.
* **Coinvolgimento utente**: valuta il modo in cui alcuni tipi di utenti interagiscono con il tuo prodotto e confrontalo con la frequenza con cui ritornano. Un dato segmento con una fidelizzazione inferiore rispetto ad altri può fornirti informazioni sul miglioramento di potenziali esperienze secondarie per gli utenti.

## Interfaccia

Per una panoramica dell’interfaccia dell’analisi guidata, consulta [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Start event]**: i criteri dell’evento con cui un utente deve interagire per essere incluso nell’analisi. Gli utenti che interagiscono con l’evento di inizio vengono conteggiati nella colonna &quot;Utenti&quot; della tabella. Questo evento funge da denominatore per i tassi di fidelizzazione visualizzati. È supportato un evento e puoi applicare i filtri di proprietà in base alle esigenze. Per impostazione predefinita, l’evento di inizio e l’evento di ritorno sono collegati, il che significa che l’utente deve intraprendere l’evento selezionato una volta per essere incluso nella coorte e un’altra volta per essere conteggiato come utente di ritorno. Nel menu Altro, puoi scollegare gli eventi di inizio e di ritorno se desideri che l’azione di ritorno sia diversa dall’azione di inclusione.
* **[!UICONTROL Return events]**: i criteri dell’evento che un utente deve utilizzare per essere conteggiato come utente di ritorno nei bucket di durata. Puoi selezionare fino a tre eventi di ritorno tra cui confrontare la fidelizzazione.
* **[!UICONTROL Counted as]**: metodo di conteggio che si desidera applicare agli utenti fidelizzati. Le opzioni includono:
   * **[!UICONTROL Metric]**: mostra il numero di [!UICONTROL Users] o [!UICONTROL Percentage of users] fidelizzati. Il denominatore per la percentuale di utenti fidelizzati è rappresentato dagli utenti inclusi nella coorte ed è lo stesso per tutti i bucket di durata.
   * **[!UICONTROL Returning]**: consente di controllare la modalità di conteggio degli utenti di ritorno. Le opzioni includono:
      * **[!UICONTROL On or after]**: spesso definita fidelizzazione &quot;non limitata&quot;, questa opzione conta un utente se questi ritorna alla fine della durata specificata o dopo di essa. Ad esempio, il giorno 7 o in qualsiasi momento dopo il giorno 7. Questa opzione è utile per mostrare in che modo gli utenti continuano a interagire e genera di conseguenza una curva di fidelizzazione più uniforme.
      * **[!UICONTROL On exactly]**: spesso indicata come fidelizzazione &quot;limitata&quot;, questa opzione conta un utente se ritorna esattamente come da durata specificata. Ad esempio, esattamente il giorno 7. Questa opzione è utile per mostrare in che modo gli utenti ritornano entro intervalli di tempo specifici e genera una curva di fidelizzazione con conseguente maggiore ondulazione. Nota: l’analisi per coorte in Analysis Workspace utilizza il conteggio &quot;esattamente&quot; come base per l’analisi.
   * **[!UICONTROL Each]**: periodo di tempo desiderato per ogni bucket di durata. Le opzioni includono:
      * **[!UICONTROL Day/Week/Month]**: le opzioni disponibili dipendono dall’intervallo di date selezionato. Queste opzioni sono identiche all’impostazione **[!UICONTROL Interval]** quando si seleziona l’intervallo di date e si aggiorna automaticamente tale impostazione.
      * **[!UICONTROL Custom brackets]**: questa opzione è disponibile solo per l’impostazione “Su ogni”. Consente di contare gli utenti in un arco temporale più ampio, ad esempio Giorno 7-10, anziché solo Giorno 7.
   * **[!UICONTROL Duration settings]**: consente di controllare i bucket di durata visualizzati nel grafico e nella tabella. Una durata è il periodo di tempo successivo all’evento di inizio in cui si è verificato l’evento di ritorno. Nota: gli utenti idonei per i bucket di durata si basano sul tempo trascorso e non sui giorni del calendario. Ad esempio, se un utente è idoneo per un evento alle 23:00 del 6 settembre e poi per un evento di ritorno alle 00:00 del 7 settembre, non verrà visualizzato nel bucket di durata di 1 giorno. :55:05 Devono trascorrere 24 ore prima che l’utente possa qualificarsi per il bucket di durata di 1 giorno. I bucket di durata disponibili dipendono dall’intervallo di date impostato.
      * **[!UICONTROL Auto durations]** definisce automaticamente i bucket di durata in base alla lunghezza dell’intervallo di date e alla vicinanza al giorno corrente dell’intervallo di date.
      * **[!UICONTROL Custom durations]** consente di personalizzare i quattro bucket di durata visualizzati nel grafico e nella tabella.
* **[!UICONTROL Segments]**: segmenti che desideri misurare. Ogni segmento selezionato aggiunge una riga alla tabella coorte. Puoi includere fino a tre segmenti.

### Impostazioni del grafico

L’analisi della[!UICONTROL Retention] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Chart type]**: il tipo divisualizzazione che vuoi usare. Le opzioni includono [!UICONTROL Bar] e [!UICONTROL Line].

### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è costituita da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale si desidera visualizzare i dati di conservazione. Le opzioni valide includono Giornaliero, Settimanale e Mensile. Lo stesso intervallo di date può avere intervalli diversi, che influiscono sulle opzioni di bucket di durata.
* **[!UICONTROL Date]**: la data di inizio e di fine. Per comodità, sono disponibili intervalli di date continui predefiniti e intervalli personalizzati salvati in precedenza; in alternativa, puoi utilizzare il selettore del calendario per scegliere un intervallo di date fisso.

Se selezioni un intervallo di date vicino al giorno corrente, gli utenti che inizialmente si impegnano troppo vicino al giorno corrente non vengono inclusi. Questa analisi offre sempre a tutti gli utenti la possibilità di essere inclusi in tutti i bucket di durata. Un messaggio sotto il selettore calendario fornisce informazioni sull’intervallo di date in cui gli utenti interagiscono e sull’intervallo riservato solo agli utenti di ritorno:

* **[!UICONTROL Analyzing users who did the start event in [Date interval]]**: se un utente interagisce con l’evento entro questo intervallo di date, viene incluso nell’analisi. Questo intervallo di date garantisce a tutti gli utenti un tempo sufficiente per qualificarsi per tutti i bucket di durata. Questo intervallo di date può essere diverso dalla selezione se è vicino al giorno corrente.
* **[!UICONTROL Data from [Date interval] is reserved to complete the analysis]**: se un utente interagisce per la prima volta in questo periodo, **non** è incluso nell’analisi. Per gli intervalli di date recenti, questi utenti non avrebbero l’opportunità di qualificarsi per tutti bucket di durata. Per gli intervalli di date passati, questi utenti erano attivi al di fuori dell’intervallo di date selezionato.

<!--
## Example

See below for an example of the analysis.

![Retention](../assets/retention.png)

-->