---
title: Panoramica di Informazioni sulla conversazione
description: Scopri il valore e la terminologia di Conversation Insights e come funziona.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: 39d6847296cc385d501defda292b5b3cae98b46a
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 1%
---
# Approfondimenti conversazione

Informazioni sulla conversazione consente di analizzare le conversazioni dalle esperienze agente offerte ai clienti. Queste esperienze agente possono essere basate su modelli di linguaggio di grandi dimensioni (Large Language Model, LLM) o su conversazioni umane. Informazioni sulla conversazione analizza le conversazioni su larga scala e fornisce il contesto per tali conversazioni all’interno dell’intero percorso di clienti. Tramite Informazioni sulla conversazione sei in grado di comprendere l’impatto degli agenti sui risultati effettivi degli utenti.

Approfondimenti conversazione affronta problemi che potresti incontrare. Ad esempio:

* Insight non è in grado di capire cosa accade quando i clienti interagiscono con agenti (LLM o umani) all’interno del contesto del percorso.
* Non hai la capacità di comprendere:
  * quali sono gli agenti che informano i clienti su larga scala.
  * il modo in cui i clienti interagiscono con gli agenti su larga scala.
  * qual è l’impatto complessivo sui KPI risultante da queste interazioni.
* Puoi creare esperienze dinamiche in base alle preferenze degli utenti in cambiamento.

Con Conversation Insights sei in grado di capire:

* Cosa dicono gli agenti agli utenti.
* Quali sono le richieste degli utenti agli agenti.
* Impatto delle conversazioni sui KPI.

Puoi determinare le prestazioni degli agenti rispetto alle direttive, la loro aderenza alle linee guida del marchio e se il costo di gestione degli agenti è giustificato dai risultati.


## Concetti

A un livello elevato di Informazioni sulla conversazione, una [conversazione](#conversation) è una sequenza di [giri](#turn) correlati. Ogni turno può avere consegnato in modo indipendente [prompt](#prompt), [risposta](#response) e [feedback](#feedback) eventi. [I segnali](#signal) sono osservazioni strutturate derivate dalla conversazione, mentre il set di dati combinato riunisce gli eventi di origine e i segnali per il reporting.

Informazioni sulla conversazione analizza le interazioni dell&#39;agente a due livelli:

* [Livello di conversazione](#conversation): l&#39;interazione completa tra un utente e un agente, che contiene più giri.
* [Livello &#x200B;](#turn): un ciclo di interazione all&#39;interno della conversazione, costituito da un prompt utente e una risposta dell&#39;agente.

L’applicazione o il servizio agente genera in Experience Platform eventi di esperienza relativi alla conversazione. I dati dell’evento di richiesta, risposta e feedback possono arrivare in modo indipendente. I servizi di Platform correlano e combinano tali eventi in un record a livello di svolta, arricchiscono facoltativamente i dati con i segnali estratti e rendono disponibili i dati risultanti per il reporting di Customer Journey Analytics.

### Conversazione

Una conversazione è la completa interazione tra un utente e un agente. Può contenere uno o più giri.

Una conversazione è il livello contenitore o raggruppamento. Tale contenitore è utile per domande quali:

* Quante conversazioni si sono verificate?
* Qual è stato l&#39;argomento generale di una conversazione?
* Come è cambiato il sentiment in una conversazione?
* Quali conversazioni hanno portato alla conversione?

Per informazioni dettagliate sull&#39;implementazione, fare riferimento all&#39;oggetto [conversation](./conversation-insights-implement.md#conversation) nella documentazione di [Implementa approfondimenti conversazione](./conversation-insights-implement.md).

### Turno

Un turno è un ciclo di interazione all&#39;interno di una conversazione.

Una virata tipica è costituita da

* Prompt utente
* Risposta dell’agente
* (facoltativo) Feedback utente

Il turno è l’oggetto analitico principale a scopo di reporting. Il servizio frullatore di conversazioni combina le informazioni disponibili su richiesta, risposta, feedback e segnale in record a livello di svolta.

Per informazioni dettagliate sull&#39;implementazione, consulta l&#39;oggetto [turn](./conversation-insights-implement.md#turn) nella documentazione di [Implementa approfondimenti conversazione](./conversation-insights-implement.md).

### Prompt

Un prompt è l&#39;input inviato all&#39;agente. Nella maggior parte degli scenari dei clienti, questo input è la domanda, la richiesta, l’istruzione o il messaggio dell’utente.

Un prompt può contenere più segmenti non elaborati. Ad esempio, un utente immette del testo e include un URL.

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`

Il prompt è l’input principale da cui Conversation Insights può derivare informazioni analitiche quali:

* Intento dell&#39;utente
* Oggetto o argomento
* Tono dell&#39;utente
* Il sentiment dell’utente
* Altri segnali supportati

Per informazioni dettagliate sull&#39;implementazione, fare riferimento all&#39;oggetto [prompt](./conversation-insights-implement.md#prompt) nella documentazione [Implementare informazioni sulla conversazione](./conversation-insights-implement.md).

### Risposta

Una risposta è il contenuto restituito dall&#39;agente o da un&#39;altra parte rispondente.

Una risposta spesso contiene diversi tipi di contenuto. Ad esempio:

* Risposta principale
* Citazione o riferimento
* Collegamento
* Immagine
* Contenuti promozionali

Questa distinzione è utile perché l’analisi deve separare la risposta principale da collegamenti di supporto, citazioni, annunci pubblicitari o altri componenti di risposta.

Per informazioni dettagliate sull&#39;implementazione, consulta l&#39;oggetto [response](./conversation-insights-implement.md#response) nella documentazione [Implement Conversation Insights](./conversation-insights-implement.md).

### Feedback

Il feedback è l’esplicita valutazione o reazione dell’utente all’interazione.

Il feedback può contenere:

* Testo di feedback in formato libero
* Una valutazione numerica
* Una classificazione di valutazione
* Uno o più motivi della valutazione

Il feedback non è necessariamente disponibile contemporaneamente alla richiesta o alla risposta. Puoi inviare il feedback in un secondo momento dall’applicazione o dal servizio agente, dopo che l’utente ha valutato la risposta.

Per informazioni dettagliate sull&#39;implementazione, consulta l&#39;oggetto [feedback](./conversation-insights-implement.md#feedback) nella documentazione [Implementare informazioni sulla conversazione](./conversation-insights-implement.md).

### Segnale

Un segnale è un’osservazione analitica strutturata sul contenuto di una conversazione. Il servizio di estrazione del segnale estrae i segnali.

Per informazioni dettagliate sull&#39;implementazione, consulta l&#39;oggetto [signal](./conversation-insights-implement.md#signal) nella documentazione di [Implementare informazioni sulla conversazione](./conversation-insights-implement.md).


### Agente

Per identificare l’applicazione o il servizio agente, è necessario fornire informazioni sull’agente per ogni evento di Informazioni sulla conversazione (prompt, risposta, feedback, segnale).

#### Chiamate abilità

Se l&#39;applicazione esperienza agente supporta la chiamata di abilità che rappresentano le capacità richiamate durante l&#39;elaborazione, è possibile aggiungere queste chiamate di abilità come parte del gruppo di campi informazioni agente.

Per informazioni dettagliate sull&#39;implementazione, consulta il gruppo di campi [Informazioni sull&#39;agente](./conversation-insights-implement.md#agentic-information-field-group) nella documentazione di [Implementare informazioni sulla conversazione](./conversation-insights-implement.md).

## Come funziona

Conversation Insights si basa su tre funzionalità principali:

* **Raccolta dati**: consente agli utenti di comprendere il livello di efficienza di LLM e degli agenti nell&#39;esecuzione delle attività. La raccolta dei dati è necessaria per raccogliere tutti i punti di dati necessari.
* **Estrazione dei segnali e fusione delle conversazioni**: trasforma i prompt e le risposte non strutturati (noti anche come svolte) in punti dati da segnalare, come intento e sentiment. Gli utenti possono creare rapporti su questi punti di dati su larga scala.
* **Generazione rapporti**: per determinare l&#39;efficacia e il ROI di un agente, analizzare le conversazioni su larga scala nel contesto del percorso di clienti.

Di seguito è illustrato il processo complessivo di raccolta dei dati, estrazione del segnale e fusione delle conversazioni.

![Illustrazione del funzionamento di Conversation Insights](assets/conversation-insights.png){zoomable="yes"}

| | Descrizione |
|---|---|
| 1 | L&#39;applicazione o il servizio dell&#39;agente viene strumentato per creare eventi che contengono ![CommentText](/help/assets/icons2/CommentText.svg), ![CommentReply](/help/assets/icons2/CommentReply.svg) e ![Feedback](/help/assets/icons2/Feedback.svg) set di dati.<br/>Per informazioni dettagliate su come gestire l&#39;applicazione o il servizio agente, consultare la [documentazione sull&#39;implementazione](./conversation-insights-implement.md). |
| 2 | Il servizio di estrazione segnali estrae i segnali dai prompt ![CommentText](/help/assets/icons2/CommentText.svg), dalle risposte ![CommentReply](/help/assets/icons2/CommentReply.svg) e dai set di dati di feedback ![Feedback](/help/assets/icons2/Feedback.svg) come eventi segnale ![OnAir](/help/assets/icons/OnAir.svg) e memorizza questi eventi segnale in un nuovo set di dati.<br>Questo passaggio è implementato come parte della definizione di una [configurazione di Informazioni sulla conversazione](./conversation-insights-configure.md). |
| 3 | Il servizio frullatore conversazioni unisce gli eventi dei prompt ![CommentText](/help/assets/icons2/CommentText.svg), delle risposte ![CommentReply](/help/assets/icons2/CommentReply.svg), del feedback ![Feedback](/help/assets/icons2/Feedback.svg) e segnala i set di dati dell&#39;evento ![OnAir](/help/assets/icons/OnAir.svg) e restituisce gli eventi ![Merge](/help/assets/icons/Merge.svg)combinati in un nuovo set di dati.<br>Questo passaggio è implementato come parte della definizione di una [configurazione di Informazioni sulla conversazione](./conversation-insights-configure.md). |
| 4 | Il set di dati ![Merge](/help/assets/icons/Merge.svg) di blend diventa parte della connessione e i componenti definiti nello schema utilizzato per il set di dati di blend diventano parte della visualizzazione dati.<br>Questo passaggio è implementato come parte della definizione di una [configurazione di Informazioni sulla conversazione](./conversation-insights-configure.md). |

