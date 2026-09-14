---
title: Implementare informazioni sulla conversazione
description: Scopri come gestire l’applicazione o il servizio agente per Informazioni su conversazioni.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: b29ee2f04a1775dca6a8fd93c3ac3050b67f0ceb
workflow-type: tm+mt
source-wordcount: '2257'
ht-degree: 6%
---
# Implementare informazioni sulla conversazione

Per produrre dati di conversazione come eventi esperienza XDM e assicurarti che questi eventi di esperienza di conversazione finiscano in Adobe Experience Platform come set di dati, puoi dotare l’applicazione o il servizio dell’agente di strumenti per utilizzare Informazioni sulla conversazione.

Questo articolo documenta i passaggi di implementazione richiesti.

>[!PREREQUISITES]
>
>* Per raccogliere i dati è necessario disporre di un ambiente Experience Platform (organizzazione e sandbox).
>* L’organizzazione Adobe deve essere abilitata per i gruppi di campi agente sperimentale e di conversazione.
>

## Schema e set di dati

Configura i set di dati per gli eventi di conversazione principali: prompt, risposta, feedback. Questi set di dati possono essere basati sullo stesso schema (ad esempio, uno schema generico di Informazioni sulla conversazione) o su singoli schemi.
Puoi definire set di dati separati per prompt, risposte e feedback oppure combinare dati in set di dati. Ad esempio, utilizza un set di dati per prompt e risposte e un altro set di dati per il feedback. In alternativa, utilizza un singolo set di dati per tutti gli eventi di conversazione.

Lo schema utilizzato per i set di dati di prompt, risposta e feedback deve estendere lo schema di base XDM Experience Event con i gruppi di campi obbligatori. E può estendere lo schema di base XDM Experience Event con gruppi di campi aggiuntivi.

### Gruppo di campi Informazioni agente

Il gruppo di campi **[!UICONTROL Informazioni sull&#39;agente]** è obbligatorio e utilizza l&#39;oggetto `agenticExperience`.

+++ Dettagli

| Percorso campo (notazione punti) | Tipo | Esempio di valore | Note |
|---|---|---|---|
| `conciergeID` | stringa | `"concierge-abc123"` | **Nuovo.** Identificatore univoco per il concierge |
| `name` | stringa | `"Brand Concierge"` | Nome del concierge che combina un set di agenti |
| `version` | stringa | `"1.0.0"` | Versione del concierge che combina un set di agenti |
| `environment` | stringa | `"prod"` | Ambiente da cui ha avuto origine questo evento (dev, stage, prod) |
| `mode` | stringa | `"release"` | Modalità in cui si trova l’agente (test, anteprima, rilascio) |
| `agents[]` | array | Vedi oggetto agente di seguito | Array di agenti utilizzati |
| `agents[].agentID` | stringa | `"agent-001"` | **Nuovo.** Identificatore univoco dell&#39;agente, a cui fa riferimento `skills[].agentID` di seguito |
| `agents[].name` | stringa | `"Chatbot Assistant"` | Nome agente |
| `agents[].version` | stringa | `"2.1.3"` | Versione agente |
| `agents[].score` | numero | `0.92` | Punteggio di affidabilità dell’agente nei valori restituiti |
| `agents[].skills[]` | array | Vedi l’oggetto abilità di seguito | **Obsoleto**: utilizza l&#39;array `skills[]` di primo livello sottostante, che possiede l&#39;elenco ordinato completo delle chiamate di abilità e collega ognuna al proprio agente tramite `agentID` |
| `agents[].skills[].name` | stringa | `"Intent Recognition"` | Nome abilità (array obsoleto) |
| `agents[].skills[].version` | stringa | `"1.0.0"` | Versione abilità (array obsoleto) |
| `agents[].skills[].score` | numero | `0.95` | Punteggio affidabilità abilità (0-1) (array obsoleto) |
| `agents[].skills[].parameters[]` | array | Vedi i parametri di seguito | Parametri inviati all’abilità (coppie chiave-valore) (array obsoleto) |
| `agents[].skills[].parameters[].key` | stringa | `"language"` | Chiave parametro |
| `agents[].skills[].parameters[].value` | stringa | `"en-US"` | Valore parametro |
| `skills[]` | array | Vedi oggetto di chiamata abilità di seguito | **Nuovo, sperimentale.** Elenco completo e ordinato delle chiamate di abilità per questa esperienza, tra tutti gli agenti. Sostituisce l&#39;array per-agent `agents[].skills[]` obsoleto |
| `skills[].skillID` | stringa | `"skill-intent-recognition"` | Identificatore della definizione dell’abilità denominata |
| `skills[].skillInvocationID` | stringa | `"inv-9f2a-001"` | Identificatore univoco per questa singola chiamata di abilità, coerente anche con le riconsegne. Chiave di deduplicazione durante l&#39;unione degli array di competenze a valle |
| `skills[].name` | stringa | `"Intent Recognition"` | Nome dell’abilità denominata |
| `skills[].version` | stringa | `"1.0.0"` | Versione dell’abilità denominata |
| `skills[].agentID` | stringa | `"agent-001"` | Identificatore dell&#39;agente che ha richiamato questa abilità, correlato a `agents[].agentID`. Raggruppare i consumatori chiave per ordinare le abilità all’interno di un agente, in quanto i subagenti vengono eseguiti in parallelo |
| `skills[].invocationSource` | stringa | `"main"` | Indica se viene richiamato dal loop agente principale (`main`) o da un subagente (`subagent`) |
| `skills[].score` | numero | `0.95` | Punteggio risultante dalla corrispondenza con l’abilità |
| `skills[].failed` | booleano | `false` | Flag che indica che l’esecuzione dell’abilità non è riuscita |
| `skills[].errorReason` | stringa | `"timeout"` | Motivo dell&#39;abilità non riuscita quando `failed` è true |
| `skills[].sequenceNumber` | numero intero | `1` | Indice che aumenta in modo monotonico di questa chiamata di abilità all’interno di un’esecuzione di un singolo agente — non diventa globale, poiché i subagenti vengono eseguiti in parallelo. I consumatori ordinano per `agentID`, quindi `sequenceNumber` e infine `timestamp` come tiebreaker. Facoltativo |
| `skills[].timestamp` | stringa (data-ora) | `"2026-09-11T00:03:15Z"` | Ora in cui è stata richiamata l’abilità, ISO 8601 UTC. Chiave di ordinamento utilizzata dopo `sequenceNumber`. I produttori devono sempre compilare questo campo |
| `skills[].skillSource` | stringa | `"inline"` | Modalità di recapito della definizione dell&#39;abilità al runtime: `inline` (caricato in linea nel contesto) o `deferred` (caricato su richiesta) |
| `skills[].executionContext` | stringa | `"inline"` | Dove viene eseguita l&#39;abilità relativa all&#39;agente chiamante: `inline` o `forked` (viene eseguito in un contesto di agente secondario con fork) |
| `skills[].reasoning.narration` | stringa | `"Recognized an intent to verify a geography fact"` | Spiegazione in linguaggio naturale del motivo per cui questa abilità è stata chiamata |
| `skills[].parameters[]` | array | Vedi i parametri di seguito | Parametri trasmessi all’abilità |
| `skills[].parameters[].key` | stringa | `"language"` | Chiave parametro |
| `skills[].parameters[].value` | stringa | `"en-US"` | Valore parametro |

+++

Per implementare gli eventi che propagano il gruppo di campi Informazioni agente con i dati, è necessario assicurarsi che:

* Configurazione agente

  * Ogni agente ha una combinazione univoca di agentID, nome e versione.
  * I punteggi dell&#39;agente sono normalizzati tra `0.0` e `1.0`.
  * Utilizza `agentID` per fare riferimento agli agenti tramite chiamata abilità.

* Chiamata abilità

  * Genera una sola voce per chiamata di abilità, per tutti gli agenti, invece di nidificare le abilità sotto ogni agente.
  * Compilare skillInvocationID in modo che la fusione a valle possa rimuovere gli eventi recapitati duplicati.
  * Ordinare correttamente i consumatori. Raggruppa per `agentID`, quindi ordina per `sequenceNumber`, tornando a `timestamp`. L&#39;ordinamento è necessario perché i subagent possono essere eseguiti in parallelo
  * Utilizzare `invocationSource` e `executionContext` per distinguere le abilità primario e subagente e l&#39;esecuzione in linea rispetto a quella con fork.
  * Evitare di utilizzare l&#39;array `agents[].skills[]` obsoleto. Se l&#39;array è già stato utilizzato in passato, considerarlo come oggetto di sola lettura.

* Parametri abilità

  * I parametri utilizzano il tipo di dati chiave-valore XDM di Adobe e utilizzano tipi di parametri comuni per le impostazioni del linguaggio, le soglie e le configurazioni del modello. Ad esempio, `"key":"language", "value":"en-US"`.

+++ Esempio di utilizzo del gruppo di campi Informazioni agente 

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffe",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"agent.interaction",
  "identityMap":{
    "ECID":[
      {
        "id": "12345678901234567890123456789012345678",
        "primary": true
      }
    ]
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      {
        "agentID":"agent-001",
        "name":"Chatbot Assistant",
        "version":"2.1.3",
        "score":0.92
      },
      {
        "agentID":"agent-002",
        "name":"Voice Assistant",
        "version":"3.0.0",
        "score":0.88
      }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline",
        "reasoning":{
          "narration":"Recognized an intent to verify a geography fact"
        },
        "parameters":[
          { "key":"language", "value":"en-US" },
          { "key":"confidenceThreshold", "value":"0.8" }
        ]
      },
      {
        "skillID":"skill-faq-retrieval",
        "skillInvocationID":"inv-9f2a-002",
        "name":"FAQ Retrieval",
        "version":"1.2.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.89,
        "failed":false,
        "sequenceNumber":2,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"inline",
        "executionContext":"forked",
        "parameters":[
          { "key":"maxResults", "value":"5" }
        ]
      },
      {
        "skillID":"skill-speech-recognition",
        "skillInvocationID":"inv-9f2a-003",
        "name":"Speech Recognition",
        "version":"2.0.1",
        "agentID":"agent-002",
        "invocationSource":"main",
        "score":0.91,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"deferred",
        "executionContext":"inline",
        "parameters":[
          { "key":"languageModel", "value":"general" },
          { "key":"noiseSuppression", "value":"true" }
        ]
      }
    ]
  }
}
```

+++


### Gruppo di campi Evento di conversazione

Il gruppo di campi **[!UICONTROL Evento di conversazione]** è obbligatorio e utilizza l&#39;oggetto `conversation`.

L&#39;oggetto di conversazione acquisisce i dati per:

#### Conversazione

Un `conversationID` univoco identifica una conversazione. Ad esempio: `conversationID = "conv-001"`. Lo schema supporta anche `conversationName`. Nome leggibile che descrive il contesto generale della conversazione, ad esempio: `France Geography Q&A`.

`conversationID` consente di raggruppare tutti gli eventi di turni correlati nella stessa esperienza di conversazione.

#### Turno

Un turno è un ciclo di interazione all&#39;interno di una conversazione.

`turnID` Un `turnID` univoco identifica un turno. Ad esempio:

`conversationID = "conv-001"`
`turnID = "turn-001"`

Gli stessi `conversationID` e `turnID` vengono utilizzati per correlare i prompt, la risposta e il feedback associati a tale turno. Tale correlazione funziona tra record consegnati separatamente o finiti in set di dati diversi.


#### Prompt

Un prompt è l&#39;input inviato all&#39;agente. Nella maggior parte degli scenari dei clienti, questo input è la domanda, la richiesta, l’istruzione o il messaggio dell’utente.

Il prompt utilizza la seguente rappresentazione: `conversation.prompt`

I campi di richiesta importanti includono:

| Campo | Significato |
|---|---|
| `prompt.source` | Chi o cosa ha prodotto il prompt, solitamente l’utente finale. |
| `prompt.raw[]` | Uno o più segmenti di contenuto non elaborato. |
| `prompt.raw[].text` | Il testo o il contenuto effettivo del prompt. |
| `prompt.raw[].purpose` | Lo scopo del contenuto, ad esempio Input utente o collegamento. |

Un prompt può contenere più segmenti non elaborati. Ad esempio, un utente immette del testo e include un URL.

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`


#### Risposta

Una risposta è il contenuto restituito dall&#39;agente o da un&#39;altra parte rispondente.

`conversation.response` Un `responseID` univoco rappresenta la risposta.

I campi di risposta importanti includono:

| Campo | Significato |
|---|---|
| `response.source` | Chi o cosa ha prodotto la risposta. |
| `response.raw[]` | Uno o più segmenti di contenuto di risposta |
| `response.raw[].text` | Testo o contenuto della risposta. |
| `response.raw[].purpose` | Lo scopo del segmento di contenuto. |

I tipi di origine documentati includono:

| Origine | Significato |
|---|----|
| `bot` | Risposta automatica dell’agente. |
| `canned` | Risposta predefinita o basata su modelli. |
| `concierge` | Risposta dell&#39;agente umano. |
| `end-user` | Contenuti generati dall’utente, se applicabile. |

#### Feedback

Il feedback è l’esplicita valutazione o reazione dell’utente all’interazione.

La struttura del feedback include: `conversation.feedback`.

Esempi:

* `feedback.raw[].text: "Great help"`
* feedback.rating.score: 1
* feedback.rating.classification: &quot;Miniature in alto&quot;
* `feedback.rating.reasons[]: ["Accurate", "Quick response"]`

L&#39;intervallo di punteggio di valutazione documentato è compreso tra `-1.0` e `1.0`.

Un evento di feedback può essere rappresentato come evento di solo feedback utilizzando: `eventType = "conversation.feedback"`.

Quando il feedback si applica a un particolare turno, conserva i `conversationID` e `turnID` appropriati in modo che il frullatore di conversazione possa associare il feedback all&#39;interazione rilevante.


#### Segnale

Un segnale è un’osservazione analitica strutturata sul contenuto di una conversazione. Il servizio di estrazione del segnale estrae i segnali.

Un segnale ha i seguenti campi.

| Campo | Significato |
|---|----|
| `scope` | Intervallo di input utilizzato per derivare il segnale, ad esempio la conversione o la conversione. |
| `name` | L’identificatore del segnale, ad esempio soggetti, intenti, toni o sentiment. Sono supportati anche i nomi dei segnali definiti dal produttore. |
| `type` | Il tipo di valore: stringa, numero o booleano. |
| `values[]` | Uno o più valori associati al segnale. |
| `stringValue` | Un valore di segnale stringa, ad esempio un intento, un tono o un oggetto. |
| `numberValue` | Un valore di segnale numerico, ad esempio un punteggio sentiment. |
| `booleanValue` | Un valore di segnale true/false. |
| `confidence` | Affidabilità opzionale del produttore nel valore del segnale, normalmente tra 0 e 1. |
| `qualifiers[]` | Descrittori facoltativi che aggiungono contesto a un valore di segnale. |
| `metadata[]` | Metadati chiave/valore facoltativi definiti dal produttore. |


Il servizio di estrazione del segnale popola l&#39;oggetto `signals` per il set di dati dei segnali.

Il contenitore `signals[].attributes.{subjects,intents,tones,sentiment}` precedente è obsoleto.

#### Conversazione

Per informazioni complete su un oggetto di conversazione, vedere di seguito.

+++ Dettagli 

| Percorso campo (notazione punti) | Tipo | Esempio di valore | Note |
|---|---|---|---|
| `conversationID` | stringa | `"conv-001"` | Raggruppa più giri |
| `conversationName` | stringa | `"France Geography Q&A"` | **Nuovo.** Nome assegnato a una conversazione che rappresenta il contesto generale |
| `turnID` | stringa | `"turn-001"` | ID univoco per questo turno |
| `prompt.source` | stringa | `"end-user"` | Source di prompt, altre opzioni possono includere un valore memorizzato nella cache, un valore non memorizzato in cache, ecc. |
| `prompt.raw[]` | array | Vedi l&#39;oggetto non elaborato di seguito | Dati non elaborati dei prompt |
| `prompt.raw[].text` | stringa | `"What is the capital of France?"` | Contenuto testo effettivo |
| `prompt.raw[].purpose` | stringa | `"User Input"` | Scopo del segmento di testo |
| `response.source` | stringa | `"bot"` | Source di risposta |
| `response.raw[]` | array | Vedi l&#39;oggetto non elaborato di seguito | Dati di risposta non elaborati |
| `response.raw[].text` | stringa | `"The capital of France is Paris."` | Contenuto testo risposta |
| `response.raw[].purpose` | stringa | `"main"` | Scopo del segmento di risposta; altre opzioni possono includere collegamenti, immagini e così via. |
| `feedback.source` | stringa | `"end-user"` | Source di feedback |
| `feedback.raw[]` | array | Vedi l&#39;oggetto non elaborato di seguito | Dati di feedback non elaborati |
| `feedback.raw[].text` | stringa | `"Great help"` | Testo del feedback |
| `feedback.raw[].purpose` | stringa | `"free-form text"` | Scopo del segmento di feedback; altre opzioni possono includere schermate, file multimediali, ecc. |
| `feedback.rating.score` | numero | `1` | Punteggio di valutazione numerico da -1,0 a 1,0 |
| `feedback.rating.classification` | stringa | `"Thumbs Up"` | Classificazione della valutazione |
| `feedback.rating.reasons[]` | array | `["Accurate", "Quick response"]` | Matrice di motivi di valutazione |
| `signals[]` | array | Vedi l&#39;oggetto segnale di seguito | Segnali derivati in base a questo evento e alla conversazione corrente. Ogni voce è un singolo segnale denominato con il proprio ambito |
| `signals[].scope` | stringa | `"turn"` | Ambito degli input da cui deriva questo insieme di segnali (passaggio, conversazione corrente, ultimi N passaggi, feedback) |
| `signals[].attributes` | oggetto | Vedi gli attributi di seguito | **Obsoleto.** Contenitore per attributi di segnale. Ogni attributo è un oggetto contenente un valore o più valori. Ciò per soddisfare la necessità prevista di supportare la popolazione di informazioni ML/agente utilizzate per generare il segnale. |
| `signals[].attributes.subjects` | oggetto | Vedi gli argomenti di seguito | **Obsoleto.** Contenitore Soggetti |
| `signals[].attributes.subjects.values[]` | array | Vedi i valori oggetto di seguito | **Obsoleto.** Matrice di valori oggetto |
| `signals[].attributes.subjects.values[].phrase` | stringa | `"product pricing"` | **Obsoleto.** Una frase o una parola chiave estratta dall’input definito nell’ambito |
| `signals[].attributes.subjects.values[].qualifiers[]` | array | `["important", "urgent"]` | **Obsoleto.** Elenco dei qualificatori per la frase |
| `signals[].attributes.intents` | oggetto | Vedi gli intenti di seguito | **Obsoleto.** Contenitore Intenti |
| `signals[].attributes.intents.values[]` | array | `["make a purchase", "learn more"]` | **Obsoleto.** Intenti derivati dall&#39;input con ambito |
| `signals[].attributes.tones` | oggetto | Visualizza i toni sotto | **Obsoleto.** Contenitore Tonalità |
| `signals[].attributes.tones.values[]` | array | `["thrilled", "contemplative"]` | **Obsoleto.** Toni derivati dall&#39;input con ambito |
| `signals[].attributes.sentiment` | oggetto | Vedi il sentiment di seguito | **Obsoleto.** Contenitore sentiment |
| `signals[].attributes.sentiment.value` | numero | `0.71` | **Obsoleto.** Punteggio da -1 (negativo) a 1 (positivo) indicante il sentiment |
| `signals[].name` | stringa | `"sentiment"` | **Nuovo** (sostituisce il contenitore `attributes` obsoleto). Identificatore per questo segnale, ad esempio &quot;soggetti&quot;, &quot;intenti&quot;, &quot;toni&quot;, &quot;sentiment&quot; o qualsiasi nome definito dal produttore — i produttori possono aggiungere nuovi tipi di segnale senza modificare lo schema |
| `signals[].type` | stringa | `"number"` | **Nuovo.** Tipo di dati dei valori di questo segnale (`string`, `number` o `boolean`): indica ai consumatori il campo del valore digitato che viene popolato su ogni voce di `values[]` |
| `signals[].values[]` | array | Vedi l’oggetto valori seguente | Uno o più valori per questo segnale |
| `signals[].values[].stringValue` | stringa | `"curious"` | Compilato quando `type` è &quot;stringa&quot;: un valore categorico come un intento, un tono o una frase estratta |
| `signals[].values[].numberValue` | numero | `0.71` | Compilato quando `type` è &quot;number&quot;, ad esempio un punteggio sentiment da -1 a 1 o un&#39;intensità |
| `signals[].values[].booleanValue` | booleano | `true` | Compilato quando `type` è &quot;booleano&quot;: un flag true/false |
| `signals[].values[].confidence` | numero | `0.9` | **Nuovo.** Affidabilità assegnata dal produttore a questo valore, da 0 a 1 |
| `signals[].values[].qualifiers[]` | array | `["important", "urgent"]` | Descrittori aggiuntivi per questo valore, simili alle parole chiave ma più significativi |
| `signals[].values[].metadata[]` | array | Vedi i parametri di seguito | **Nuovo.** Metadati definiti dal produttore per questo valore come coppie chiave/valore, ad esempio contesto sull’agente ML/agente che ha generato il segnale |

+++




### Gruppi di campi aggiuntivi

Puoi aggiungere gruppi di campi facoltativi allo schema utilizzato per i set di dati di prompt, risposta e feedback. Ad esempio:

* **Dettagli Web** gruppo di campi. Per acquisire dettagli sulla pagina web, la conversazione è stata incorporata in.
* **Gruppo di campi Dettagli Commerce**. Acquisire i dettagli del prodotto consigliato indicato come parte della conversazione.



Il cliente è responsabile della produzione degli eventi di conversazione sorgente. Successivamente, Adobe Platform esegue l’estrazione del segnale e la fusione dei dati. Il cliente non ha bisogno di implementare i servizi di estrazione del segnale o di miscelazione.

Questo documento descrive i requisiti di input di MVP per Informazioni sulla conversazione e l’aggiornamento dello schema agente corrente. Non include le funzionalità di Informazioni sulla conversazione 1.0 o i requisiti per una versione successiva.

### Tipo di evento

È necessario impostare uno dei seguenti valori per `eventType` (stringa) per ogni evento di conversazione:

| Valore | Spiegazione |
|---|---|
| `conversation turn` | Completa la conversazione con prompt e risposta |
| `conversation recommendation` | Consigli basati su conversazioni |
| `conversation feedback` | Evento di solo feedback |


### Tipo di Source

È necessario impostare uno dei seguenti valori per `source` per ogni oggetto `prompt`, `response` o `feedback` in un evento:

| Valore | Descrizione |
|---|---|
| `end-user` | Input utente umano |
| `bot` | Risposta automatica dell’agente |
| `canned` | Risposta predefinita/basata su modelli |
| `concierge` | Risposta dell’agente umano |

### Tipo di scopo (testo non elaborato)

È necessario impostare uno dei seguenti valori per l&#39;attributo `purpose` su qualsiasi elemento dell&#39;oggetto `raw` in un oggetto `prompt`, `response` o `feedback`.

| Valore | Descrizione |
|---|---|
| `User Input` | Input utente primario |
| `main` | Contenuto della risposta principale |
| `advertisement` | Contenuti promozionali |
| `citation` | Collegamenti di riferimento/sorgente |
| `link` | Collegamenti esterni |
| `image` | Riferimenti immagine |
| `enum picker` | Selezione strutturata del feedback |


### Esempio

Di seguito è riportato un esempio di utilizzo del gruppo di campi Evento di conversazione in vari scenari.

+++ Dettagli 

>[!BEGINTABS]

>[!TAB Esempio di evento turn]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What is the capital of France? This link says it is Lyon.", "purpose": "User Input" },
        { "text": "https://wrong.geography.com/france", "purpose": "link" }
      ]
    }
  }
}
```

>[!TAB Esempio di evento di risposta]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffd",
  "timestamp":"2026-09-11T00:03:16Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "The capital of France is Paris.", "purpose": "main" },
        { "text": "Would you like to plan a trip to Paris?", "purpose": "advertisement" },
        { "text": "https://en.wikipedia.org/wiki/France", "purpose": "citation" }
      ]
    }
  }
}
```

>[!TAB Esempio di evento Feedback]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffb",
  "timestamp":"2026-09-12T00:03:15Z",
  "eventType":"conversation.feedback",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "feedback": {
      "source": "end-user",
      "raw": [
        { "text": "Great help", "purpose": "text box" }
      ],
      "rating": {
        "score": 1,
        "classification": "Thumbs Up",
        "reasons": ["Accurate", "Quick response"]
      }
    }
  }
}
```

>[!TAB Esempio di evento consigli di prodotto]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffa",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.recommendation",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-xyz789",
    "name":"Product Concierge",
    "version":"1.0.0",
    "environment":"prod",
    "mode":"release",
    "agents":[
      { "agentID":"agent-010", "name":"Product Advisor", "version":"1.0.0", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "turnID": "int-099",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What product do you recommend for a new user trying to create a poster?", "purpose": "User Input" }
      ]
    },
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "To create a poster, we would recommend Adobe Express - https://express.adobe.com.", "purpose": "main" },
        { "text": "https://express.adobe.com", "purpose": "link" }
      ]
    }
  },
  "productListItems": [
    { "SKU": "express" }
  ]
}
```

>[!ENDTABS]

+++

## Raccolta dati

Utilizza la seguente strategia di raccolta dati per Informazioni su conversazioni.


### Tipi di evento

L’applicazione o il servizio agente invia un evento il prima possibile. Assicurati che l’app o il servizio non attenda una risposta prima di inviare il messaggio con le informazioni disponibili al momento dell’evento.

Questa raccomandazione implica che:

* Gli oggetti Prompt, Response e Feedback vengono compilati in modo indipendente e non devono far parte di un singolo evento.
* Sono previsti più eventi con lo stesso `conversationID` e `turnID` tra set di dati.

### Correlazione degli eventi

L&#39;applicazione o il servizio agente deve conservare identificatori stabili in tutti gli eventi correlati.

| Percorso campo | Descrizione |
|---|---|
| `conversation.conversationID` | Identificatore univoco della conversazione complessiva. |
| `conversation.turnID` | Identificatore univoco di un singolo turno all’interno della conversazione. |
| `_id` | Identificatore del record di Experience Event. |
| `timestamp` | Ora in cui si è verificato l’evento. |
| `eventType` | Identifica il tipo di evento di conversazione. |

* Lo stesso `conversationID` deve essere utilizzato per tutti gli eventi appartenenti alla stessa conversazione.

* Lo stesso `turnID` deve essere utilizzato per il prompt, la risposta e qualsiasi feedback associato allo stesso turno. Possono esistere più eventi con lo stesso `turnID` nei set di dati di prompt, risposta e feedback.

L’applicazione o il servizio agente genera ID che rimangono stabili durante i nuovi tentativi o la riconsegna. Questo consente all’elaborazione a valle di associare correttamente gli eventi ed evitare duplicati non intenzionali.

## Estrazione del segnale

L&#39;estrazione del segnale avviene dopo la raccolta dei dati. L&#39;applicazione o il servizio agente non compila segnali aggiuntivi.

+++ Evento di svolta di esempio con segnali

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id":"12345678901234567890123456789012345678", "primary":true }
    ]
  },
  "web":{
    "webPageDetails":{ "URL":"https://www.adobe.com", "name":"Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline"
      }
    ]
  },
  "conversation":{
    "conversationID":"conv-001",
    "conversationName":"France Geography Q&A",
    "turnID":"int-001",
    "signals":[
      {
        "scope":"turn",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"capital of France", "confidence":0.93, "qualifiers":["geographical","factual-question"] },
          { "stringValue":"Lyon", "confidence":0.87, "qualifiers":["incorrect","misinformation"] }
        ]
      },
      {
        "scope":"turn",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"seek-information" },
          { "stringValue":"verify-facts" }
        ]
      },
      {
        "scope":"turn",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"curious" },
          { "stringValue":"uncertain" }
        ]
      },
      {
        "scope":"turn",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.1 }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"unreliable source", "qualifiers":["external-link","potentially-misleading"] },
          { "stringValue":"geography knowledge", "qualifiers":["educational","basic-facts"] }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"fact-checking" },
          { "stringValue":"learn-correct-information" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"questioning" },
          { "stringValue":"seeking-clarification" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.3 }
        ]
      }
    ],
    "prompt":{
      "source":"end-user",
      "raw":[
        { "text":"What is the capital of France? This link says it is Lyon.", "purpose":"User Input" },
        { "text":"https://wrong.geography.com/france", "purpose":"link" }
      ]
    }
  }
}
```

+++

## Fusione dei dati

Il servizio di fusione delle conversazioni unisce gli eventi dai set di dati di prompt, risposta, feedback e eventi di segnale in un set di dati di eventi di conversazione misti dedicato. Tale set di dati viene utilizzato in Customer Journey Analytics come parte di una connessione. I componenti all’interno di tale set di dati vengono aggiunti alle visualizzazioni dati specificate per una configurazione di Informazioni sulla conversazione.
