---
title: Integrazione LLM Optimizer
description: Integrare LLM Optimizer con Customer Journey Analytics
feature: Experience Platform Integration
role: User
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
source-git-commit: 3aa4e0c98e9a3e4163dad992e598638892fc88cd
workflow-type: tm+mt
source-wordcount: 2539
ht-degree: 2%

---


# Integrazione con LLM Optimizer

[Adobe LLM Optimizer](https://experienceleague.adobe.com/it/docs/llm-optimizer/using/home){target="_blank"} è un&#39;applicazione di intelligenza artificiale generativa per l&#39;ottimizzazione dei motori generativi, progettata per aiutare i brand a migliorare la visibilità, la precisione e l&#39;influenza negli ambienti di ricerca basati sull&#39;intelligenza artificiale. LLM Optimizer fornisce informazioni sulla presenza dei brand nelle risposte generate dall’intelligenza artificiale, offre contenuti consigliati e automatizza le correzioni di ottimizzazione.

L’intelligenza artificiale è diventato un canale di rilevamento primario. Gli agenti LLM, come ChatGPT, Claude, Copilot e Perplexity, scansionano contenuti di brand.

>[!PREREQUISITES]
>
>Devi aver eseguito il provisioning di un’offerta a pagamento LLM Optimizer e averla collegata alla configurazione Experience Platform tramite il connettore gestito.


>[!IMPORTANT]
>
>Come parte di questa integrazione, alcuni trattamenti temporanei dei dati di LLM Optimizer si verificano negli Stati Uniti. I dati vengono infine memorizzati nell’area geografica designata, come configurato nel contratto Customer Journey Analytics.


## Casi d’uso

L’integrazione tra Customer Journey Analytics e LLM Optimizer offre i seguenti vantaggi:

* **Integrazione in entrata**: utilizza i dati di LLM Optimizer in Customer Journey Analytics per misurare il traffico basato su LLM (crawler bot, richieste RAG, attività agente) insieme a dati web, mobili e di altro tipo esistenti. Sarà possibile, ad esempio:

  * Misura il traffico guidato da LLM per origine agente insieme ai canali tradizionali.

  * Identifica i contenuti molto utilizzati dai moduli LLM, ma con prestazioni inferiori nella conversione umana.

  * Rilevare dove le richieste dell’agente LLM non vanno a buon fine nei percorsi critici.

  * Confronta la domanda di bot LLM per una pagina con le conversioni e i ricavi di tale pagina nei dati web, confrontati a livello di URL e host.

* **Integrazione in uscita**: invia dati sulle prestazioni di Customer Journey Analytics a LLM Optimizer in modo da ottimizzare la visibilità AI per le origini LLM che inviano traffico prezioso, ad esempio ChatGPT o Perplessity. Sarà possibile, ad esempio:

  * Scopri quali fonti LLM inviano visitatori umani che continuano a convertire o generare ricavi. Customer Journey Analytics misura questo dal traffico web di riferimento, non dal set di dati bot.
  * Classifica le origini LLM in base al valore a valle dei visitatori umani inviati, quindi concentra il tuo lavoro di visibilità AI sulle origini che ottengono i migliori risultati.


## Integrazione in entrata

Il traffico LLM raggiunge il sito in due modi. Customer Journey Analytics misura ogni modo da un’origine dati diversa.

Il primo modo è una persona che legge una risposta di IA e poi fa clic sul sito. Tale visita esegue lo stesso JavaScript che raccoglie il resto dei dati web. I dati web Customer Journey Analytics esistenti includono quindi la visita e il dominio di riferimento che ti ha inviato l’utente, ad esempio chatgpt.com. Customer Journey Analytics non etichetta queste visite come traffico AI di per sé. Per identificarli e raggrupparli, crea un campo derivato sulla connessione che corrisponde ai domini di riferimento di IA, quindi genera segmenti e rapporti su tale campo. Vedi [Campi derivati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}. Non è necessario il set di dati LLM Optimizer per questo traffico umano.

Il secondo modo è un bot o un agente che richiede direttamente le pagine. Ciò include crawler che generano un indice di intelligenza artificiale e recuperi live che si verificano quando un utente invia una richiesta a un assistente di intelligenza artificiale. Queste richieste non eseguono JavaScript, pertanto i dati web esistenti non li registrano. Il set di dati LLM Optimizer acquisisce questo traffico dal livello CDN. Il resto di questa sezione descrive tale set di dati.

### Integrare il set di dati in Customer Journey Analytics

Il connettore gestito di LLM Optimizer fornisce i dati ad Experience Platform come set di dati di riepilogo. Per misurarlo in Customer Journey Analytics, è necessario completare due passaggi di configurazione:

1. Crea una connessione che includa il set di dati di LLM Optimizer. Vedi [Creare o modificare una connessione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}.
2. Crea una visualizzazione dati sulla connessione. La visualizzazione dati rende disponibili in Analysis Workspace le dimensioni e le metriche riportate di seguito. Consulta [Creare o modificare una visualizzazione dati](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}.

Il set di dati:

* Utilizza [set di dati di riepilogo](/help/data-views/summary-data.md) basati sulla classe Metriche di riepilogo XDM.
* Dati bucket per URL e host, ora e caratteristiche di richiesta come tipo di bot, provider CDN e stato.

>[!NOTE]
>
>Il set di dati di LLM Optimizer contiene dati aggregati. Non contiene dati PII come identificatori utente, prompt o risposte.
>

Poiché è un set di dati di riepilogo, puoi considerarlo come un set di dati di ricerca e unirlo a un set di dati evento su una chiave full URL.

LLM Optimizer fornisce questa chiave nella dimensione **URL CDN**. Combina l’host e il percorso richiesto in un unico URL completo normalizzato, in modo simile a come Customer Journey Analytics memorizza i dati web. La riuscita dell’unione dipende dalla tua raccolta di dati. Il set di dati dell’evento richiede un campo URL completo equivalente o un campo che puoi analizzare e normalizzare per corrispondere all’URL fornito da LLM Optimizer. Quando entrambi i lati risolvono lo stesso URL completo, il record LLM Optimizer corrisponde alla pagina corrispondente nei dati web.

### Informazioni sul set di dati

LLM Optimizer legge i registri di accesso CDN sul lato server ed estrae i record in cui la parte richiedente è un bot o un agente automatizzato. Poiché i dati provengono dal livello CDN, LLM Optimizer acquisisce le richieste dei bot che non attivano alcun tag JavaScript. Gli strumenti di analisi web standard non tengono conto di questo traffico.

Il set di dati utilizza il gruppo di campi **Riepilogo richieste CDN**. Ogni campo si trova sotto un oggetto `cdn`, pertanto i nomi dei campi nelle tabelle seguenti assumono la forma `cdn.<name>`, ad esempio `cdn.url` e `cdn.botType`.

Ogni record descrive una combinazione di host, percorso URL, tipo di bot, provider CDN, codice di stato, referrer, host inoltrato e tempo al primo byte per un’ora. Quando la stessa combinazione appare più di una volta all’ora, Customer Journey Analytics combina tali record in un’unica riga e aumenta il conteggio delle richieste. Utilizza la metrica **Numero richieste CDN** per misurare il volume. Non utilizzare il conteggio delle righe.

### Dimensioni

Le dimensioni seguenti sono disponibili per l’utilizzo come componenti in una visualizzazione dati dopo aver impostato una connessione che include un set di dati di LLM Optimizer. La colonna **Campo** mostra il campo di origine nel gruppo di campi Riepilogo richieste CDN.

| Dimensione | Campo | Descrizione |
|-----------|-------|-------------|
| URL CDN | `cdn.url` | L’URL completo normalizzato della richiesta, inteso come chiave di unione. LLM Optimizer combina l’host e il percorso richiesto in un unico URL e lo normalizza in modo che corrisponda al modulo URL completo memorizzato da Customer Journey Analytics per i dati web. Utilizza questa dimensione per unire il set di dati di ricerca LLM Optimizer a un set di dati evento con un campo full URL equivalente. Include l’host e il percorso, ma non lo schema. |
| Percorso URL CDN | `cdn.path` | Il percorso URL non elaborato e la stringa di query richiesti dall’agente, come consegnati dalla rete CDN. Non include lo schema o l&#39;host. Utilizzalo quando hai bisogno del percorso richiesto esatto anziché della chiave di join normalizzata. |
| Host CDN | `cdn.host` | Il nome host che ha ricevuto la richiesta, ad esempio www.example.com. Questo host fa anche parte della chiave di join dell’URL CDN. Un set di dati può contenere più host quando un’organizzazione ha più sottodomini sullo stesso account CDN. |
| Tipo di bot CDN | `cdn.botType` | Classificazione LLM Optimizer dell’agente richiedente. I valori coprono i crawler di ricerca classici, i crawler di indice IA e gli agenti Live Fetch di IA. Per la tassonomia completa, consulta le [categorie dell&#39;agente bot](#bot-agent-categories) di seguito. |
| Agente utente CDN | `cdn.userAgent` | Stringa non elaborata dell’agente utente dal registro CDN. Utile per distinguere i sottotipi all’interno di una classificazione bot o per convalidare la classificazione assegnata da LLM Optimizer. |
| Stato HTTP CDN | `cdn.status` | Il codice di stato della risposta HTTP. Indica se il bot ha ricevuto il contenuto richiesto. Consulta [Codici di stato](#status-codes) di seguito per le indicazioni di interpretazione specifiche per il traffico AI. |
| Provider CDN | `cdn.cdnProvider` | Quale CDN ha gestito la richiesta. I valori sono `akamai`, `byocdn-akamai`, `byocdn-fastly` e `byocdn-cloudfront`. Il prefisso `byocdn-` indica il percorso della raccolta di log, non un fornitore CDN diverso. Un set di dati può contenere più valori quando un’organizzazione dispone di host dietro diverse configurazioni CDN. |
| Referente CDN | `cdn.referer` | Il valore dell’intestazione HTTP Referer dal registro CDN. Spesso vuoto per il traffico da bot. Se presente, può indicare quale prodotto o dominio di intelligenza artificiale ha attivato il recupero. Ad esempio, chat.openai.com. |
| Host CDN inoltrato | `cdn.xForwardedHost` | Il valore dell’intestazione X-Forwarded-Host, se presente. Rilevante quando la richiesta passa attraverso un proxy inverso o un livello di schermatura CDN prima di raggiungere l’origine. |
| Data evento CDN | Derivato dalla marca temporale del record | Parte della data della marca temporale del batch orario per questo record. |
| Ora evento CDN | Derivato dalla marca temporale del record | Parte dell&#39;ora della marca temporale del batch orario per questo record. |

### Categorie di agenti bot

La dimensione **Tipo di bot CDN** organizza gli agenti in tre categorie. Ogni categoria risponde a una domanda analitica diversa.

**crawler di ricerca classici** indicizzano il contenuto per i motori di ricerca tradizionali. Utilizza questa categoria per misurare la visibilità del contenuto nei motori di ricerca tradizionali.

| Valore tipo di bot | Fornitore | Descrizione |
|---|---|---|
| `GoogleBot` | Google | crawler di indicizzazione di ricerca principale di Google. Google Discover e Google News sono inoltre disponibili. |
| `BingBot` | Microsoft | Crawler di indicizzazione di ricerca di Bing. Alimenta anche l&#39;indice di web grounding di Microsoft Copilot. |

**crawler di indici IA** scansionano contenuti per generare o aggiornare il corpus di formazione o l&#39;indice di ricerca di un prodotto AI. Questi crawler stanno preparando la knowledge base di un modello, non rispondendo a una richiesta live dell’utente. Quando un URL ha un volume di crawler elevato, i fornitori di IA considerano tale contenuto meritevole di essere indicizzato. Quando un URL ha un volume di crawler basso ma un volume di recupero live elevato, il modello attinge dalle conoscenze memorizzate nella cache anziché recuperare nuovi contenuti.

| Valore tipo di bot | Fornitore | Descrizione |
|---|---|---|
| `GPTBot` | OpenAI | Il crawler principale di OpenAI per la costruzione di basi di conoscenza e dati di formazione sui modelli. |
| `OAI-SearchBot` | OpenAI | Crawler di OpenAI per il prodotto di ricerca web di ChatGPT. Distinto da GPTBot. Questo agente genera l’indice di ricerca in tempo reale, non il corpus di formazione. |
| `ClaudeBot` | Antropico | Crawler principale dell’antropica per i dati di apprendimento dei modelli. |
| `Claude-SearchBot` | Antropico | Il crawler di Anthropic per l&#39;indice di ricerca e recupero di Claude. Distinto da ClaudeBot. |
| `PerplexityBot` | Perplessità | Il crawler di indice della perplessità. Perplessità utilizza questo agente per creare il corpo per la sua generazione di risposte. |

I **recuperi live di IA** si verificano quando un utente reale invia una richiesta a un assistente di IA e l&#39;assistente recupera la pagina live prima di rispondere. Utilizza questa categoria per misurare la domanda diretta degli utenti che arrivano tramite gli assistenti AI.

| Valore tipo di bot | Fornitore | Descrizione |
|---|---|---|
| `ChatGPT-User` | OpenAI | Un utente ha posto una domanda a ChatGPT. ChatGPT ha recuperato questo URL per leggerlo e rispondere. |
| `ChatGPT Clients` | OpenAI | L’app mobile ChatGPT (iOS e Android) esegue un recupero in tempo reale. La stringa user-agent include la versione dell’app e il dispositivo. |
| `Claude-User` | Antropico | Un utente o un’applicazione che utilizza Claude ha recuperato questo URL in tempo reale. La stringa user-agent può identificare lo specifico prodotto Claude, ad esempio claude-code. |
| `Perplexity-User` | Perplessità | Un utente ha posto una domanda a Perplexity. Perplessità ha recuperato questo URL per motivare la sua risposta. |
| `Google-NotebookLM` | Google | Un utente ha aperto Google NotebookLM ed ha creato questo dominio. NotebookLM recupera ogni URL raggiungibile all’interno di un dominio di origine. |
| `Google-ai-mode` | Google | La funzione Panoramiche basate sull’intelligenza artificiale di Google Search ha recuperato questo URL per includerlo nei risultati di ricerca in un pannello di risposta generato dall’intelligenza artificiale. |
| `Gemini-Deep-Research` | Google | Un utente ha eseguito una sessione di Gemini Deep Research. Deep Research effettua molte acquisizioni sequenziali su più sorgenti per compilare un rapporto di ricerca. |
| `GoogleAgent-URLContext` | Google | Un utente ha condiviso un URL con Gemini e ha fatto domande su quella pagina. Gemini ha recuperato l’URL in tempo reale per rispondere a domande su tale contenuto specifico. |
| `Amzn-User` | Amazon | Questo URL è stato recuperato in tempo reale da un agente di Amazon Alexa o Amazon AI. In genere viene visualizzato sul contenuto di riferimento e della documentazione. |
| `MistralAI-User` | Mistral | Recupero live da un consumatore di prodotti o API basato su Mistral. |

Quando LLM Optimizer non riesce a far corrispondere un agente utente a un modello riconosciuto, assegna il valore `Unknown`. È possibile utilizzare la dimensione **Agente utente CDN** per identificare l&#39;agente che ha effettuato tali richieste.

### Codici di stato

I codici di stato HTTP in questo set di dati indicano se l’agente di IA ha ricevuto il contenuto richiesto.

| Stato | Nome | Interpretazione |
|--------|------|----------------|
| 200 | OK | Il bot ha ricevuto la risposta completa. Il contenuto era disponibile per l’IA da utilizzare. |
| 304 | Non modificato | Il bot ha confermato che il contenuto non è stato modificato e ha utilizzato la versione cache. Il contenuto era disponibile. |
| 301 | Spostato in modo permanente | Il bot è stato reindirizzato a un nuovo URL. Ogni reindirizzamento aggiunge un ulteriore round trip. Un volume elevato di 301 su URL scansionati di frequente indica che il reindirizzamento deve essere risolto a livello di CDN. |
| 302 | Trovato (reindirizzamento temporaneo) | Stessa penalità di latenza di 301. A differenza di 301, non segnala una mossa permanente, quindi i bot continueranno a raggiungere l’URL originale. |
| 403 | Non consentito | La rete CDN o l’origine hanno bloccato il bot. Questo può essere intenzionale, ad esempio, attraverso le regole robots.txt o la politica di WAF, oppure non intenzionale, ad esempio, attraverso limiti di tasso eccessivamente ampi. Quando i recuperi AI sono bloccati, tale contenuto non può essere visualizzato nelle risposte AI. |
| 404 | Non trovato | L’URL non esiste. Un volume elevato di 404 sui tipi di agenti di IA indica che l’indice di IA contiene URL non aggiornati. Utilizza lo stato 410 per indicare ai crawler di rimuovere definitivamente un URL dal proprio indice. |
| 429 | Troppe richieste | La tariffa CDN limitava il bot. Se si verificano 429 errori persistenti sui tipi di agenti live-fetch, gli utenti che pongono agli assistenti AI domande sul contenuto riceveranno risposte incomplete o mancanti. |
| 504 | Timeout del gateway | La rete CDN ha smesso di attendere la risposta dell’origine. Il contenuto non ha raggiunto l’intelligenza artificiale. Quando una pagina subisce un timeout, l’IA non può accedere al relativo contenuto e non può includerlo in una risposta. Un volume elevato di 504 sui tipi di agenti live-fetch costituisce un rischio diretto di visibilità AI. |

### Metriche

Le metriche seguenti sono disponibili per l’utilizzo come componenti in una visualizzazione dati dopo aver configurato una connessione che include un set di dati di LLM Optimizer. La colonna **Campo** mostra il campo di origine nel gruppo di campi Riepilogo richieste CDN.

| Metrica | Campo | Descrizione |
|--------|-------|-------------|
| Conteggio richieste CDN | `cdn.requests` | Numero totale di richieste CDN, sommate dal campo delle richieste in tutte le righe. Usa sempre questa metrica per misurare il volume. Non utilizzare il conteggio delle righe. |
| Conteggio errori CDN | `cdn.status`, `cdn.requests` | Numero di richieste che hanno restituito un codice di stato HTTP 4xx o 5xx. |
| Tasso di errori CDN | Derivato dal conteggio degli errori CDN | Il conteggio degli errori come percentuale del totale delle richieste. |
| Tempo medio CDN al primo byte | `cdn.timeToFirstByte` | Tempo medio, in millisecondi, a partire dal momento in cui la rete CDN ha ricevuto una richiesta al primo byte della risposta. Le risposte CDN memorizzate nella cache sono in genere inferiori a 50 ms. Le risposte fornite dall’origine sono in genere da 300 ms a 700 ms. Gli agenti di live-fetch basati sull’intelligenza artificiale spesso mostrano valori molto più elevati, che corrispondono a risposte di timeout o di origine molto lente. Valori medi elevati sui tipi di agenti di recupero live meritano di essere esaminati come rischio di visibilità AI. |

### Limiti del set di dati

Questo set di dati acquisisce solo il traffico da bot dai registri di accesso CDN. Non contiene quanto segue:

* **Sessioni utente, conversioni o dati di coinvolgimento.** Un utente che fa clic su da una risposta AI esegue JavaScript sulla pagina, in modo che la visita si trovi nei dati web esistenti, non in questo set di dati. Puoi inserire entrambi i set di dati in Customer Journey Analytics e confrontarli per lo stesso URL e host.
* **Qualsiasi identificatore di persona come ECID.** Non è possibile creare un join a livello di persona da questo set di dati. Il join opera a livello di URL e host.
* **Granularità al secondo.** La marca temporale è oraria. Non è possibile suddividere il traffico in un’ora in minuti o secondi.
* **Contenuto pagina o HTML sottoposto a rendering.** Questo set di dati registra il fatto del recupero e il relativo risultato, non ciò che l’intelligenza artificiale ha letto dalla pagina.
* **Dati conversione.** Questo set di dati non indica se una risposta di IA ha portato una persona a visitare il sito o a convertire. Contiene dati di riepilogo CDN aggregati, non dati evento basati su persona, pertanto non collega alcuna richiesta a una singola persona o sessione.

## Integrazione in uscita

Da determinare.


<!-- 

# LLM Optimizer integration

[Adobe LLM Optimizer](https://experienceleague.adobe.com/en/docs/llm-optimizer/using/home){target="_blank"} is a generative AI-first application for Generative Engine Optimization, designed to help brands enhance their visibility, accuracy, and influence in AI-driven search environments. LLM Optimizer provides insights into brand presence in AI-generated answers, offers prescriptive content recommendations, and automates optimization fixes.

AI has become a primary discovery channel. LLM agents, such as ChatGPT, Claude, Copilot, and Perplexity, crawl and reference brand content. 

>[!PREREQUISITES]
>
>You must have an LLM Optimizer paid offering provisioned and connected to your Experience Platform configuration through the managed connector.


>[!IMPORTANT]
>
>As part of this integration, some temporary processing of LLM Optimizer data occurs in the United States. Data is ultimately stored in your designated region as configured in your Customer Journey Analytics contract.


## Use cases

You can benefit from the integration between Customer Journey Analytics and LLM Optimizer in two ways:

* **Inbound integration**: Use LLM Optimizer data in Customer Journey Analytics to measure LLM-driven traffic (bot crawlers, RAG requests, agent activity) alongside existing web, mobile, and other types of data. For example, to address the following use cases:
  
  * Measure LLM-driven traffic by agent source alongside traditional channels.
  
  * Identify content that is heavily consumed by LLMs but underperforms in human conversion.
  
  * Detect where LLM-agent requests fail across critical paths.

  * Correlate LLM activity with downstream business outcomes (revenue, conversions, engagement).
  
* **Outbound integration**: Use Customer Journey Analytics performance data inside LLM Optimizer so AI visibility can be optimized for real business outcomes. For example, to address the following use cases:

  * Evaluate how each LLM agent correlates with revenue, conversions, and engagement.
  * Identify which LLM agents are associated with stronger downstream performance. Which LLM agents are associated with higher engagement or conversion rates.


## Inbound integration

To ingest LLM Optimizer data into Customer Journey Analytics, use the LLM Optimizer datasets available in Experience Platform. The ingestion method:

* Uses [summary datasets](/help/data-views/summary-data.md) that are based on the XDM Summary Schema class.
* Buckets data by URL/host, time, and request characteristics such as bot type, CDN provider, and status.

>[!NOTE]
>
>The LLM Optimizer dataset contains aggregated data that does not contain any PII, such as user identifiers, prompts, or responses.
>

You use the LLM Optimizer dataset in a connection. Because the dataset is a summary dataset, you can use the dataset as a lookup dataset and potentially join to an event dataset on a full-URL key.

LLM Optimizer provides this key for you in the **CDN URL** dimension. The key combines the host and the requested path into a single normalized full URL, similar to how Customer Journey Analytics stores web data. This join-key field facilitates the join. The outcome depends on your Customer Journey Analytics implementation and whether your event dataset has a page URL field that matches the URL representation LLM Optimizer provides. When both sides resolve to the same full URL, the LLM Optimizer record matches the corresponding page in your web data.

### About the dataset

LLM Optimizer reads CDN access logs on the server side and extracts records where the requesting party is a bot or automated agent. Because the data comes from the CDN layer, LLM Optimizer captures requests from bots that do not execute any JavaScript tag. Standard web analytics tools miss this traffic entirely.

Each record describes one combination of host, URL path, bot type, CDN provider, status code, referrer, forwarded host, and time to first byte for one hour. When the same combination appears multiple times hourly, Customer Journey Analytics combines those records into one row and increases the request count. Use the **CDN Request Count** metric to measure volume. Do not use row count.

### Dimensions

The following dimensions are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Dimension | Description |
|-----------|-------------|
| CDN URL | The normalized full URL for the request, intended as the join key. LLM Optimizer combines the host and the requested path into a single URL and normalizes it to match the full-URL form that Customer Journey Analytics stores for web data. Use this dimension to join the LLM Optimizer lookup dataset to an event dataset that has an equivalent full-URL field. It includes the host and path, but not the scheme. |
| CDN URL Path | The raw URL path and query string that the agent requested, as delivered by the CDN. Does not include the scheme or host. Use this when you need the exact requested path rather than the normalized join key. |
| CDN Host | The hostname that received the request, for example, www.example.com. This host is also part of the CDN URL join key. A dataset can contain multiple hosts when an organization has multiple subdomains on the same CDN account. |
| CDN Bot Type | LLM Optimizer's classification of the requesting agent. Values cover classic search crawlers, AI index crawlers, and AI live-fetch agents. See the [Bot agent categories](#bot-agent-categories) below for the full taxonomy. |
| CDN User Agent | The raw user-agent string from the CDN log. Useful for distinguishing sub-types within a bot classification, or for validating the classification assigned by LLM Optimizer. |
| CDN HTTP Status | The HTTP response status code. Indicates whether the bot received the content it requested. See the [Status codes](#status-codes) below for interpretation guidance specific to AI traffic. |
| CDN Provider | Which CDN handled the request. Values are `akamai`, `byocdn-akamai`, `byocdn-fastly`, and b`yocdn-cloudfront`. The `byocdn-` prefix indicates the log collection pathway, not a different CDN vendor. A dataset can contain multiple values when an organization has hosts behind different CDN configurations. |
| CDN Referrer | The HTTP Referer header value from the CDN log. Often empty for bot traffic. When present, it can indicate which AI product or domain triggered the fetch. For example, chat.openai.com. |
| CDN Forwarded Host | The X-Forwarded-Host header value, if present. Relevant when the request passed through a reverse proxy or CDN shield layer before reaching the origin. |
| CDN Event Date | The date part of the hourly batch timestamp for this record. |
| CDN Event Hour | The hour part of the hourly batch timestamp for this record. |

### Bot agent categories

The **CDN Bot Type** dimension organizes agents into three categories. Each category answers a different analytical question.

**Classic search crawlers** index content for traditional search engines. Use this category to measure how visible your content is to traditional search engines.

| Bot type value | Vendor | Description |
|---|---|---|
| `GoogleBot` | Google | Google's main search index crawler. Also serves Google Discover and Google News. |
| `BingBot` | Microsoft | Bing's search index crawler. Also feeds Microsoft Copilot's web grounding index. |

**AI index crawlers** crawl content to build or update an AI product's training corpus or search index. These crawlers are preparing a model's knowledge base, not responding to a live user request. When a URL has high crawler volume, AI vendors consider that content worth indexing. When a URL has low crawler volume but high live-fetch volume, the model draws from cached knowledge rather than fetching fresh content.

| Bot type value | Vendor | Description |
|---|---|---|
| `GPTBot` | OpenAI | OpenAI's primary crawler for model training data and knowledge base construction. |
| `OAI-SearchBot` | OpenAI | OpenAI's crawler for ChatGPT's web search product. Distinct from GPTBot. This agent builds the real-time search index, not the training corpus. |
| `ClaudeBot` | Anthropic | Anthropic's primary crawler for model training data. |
| `Claude-SearchBot` | Anthropic | Anthropic's crawler for Claude's search and retrieval index. Distinct from ClaudeBot. |
| `PerplexityBot` | Perplexity | Perplexity's index crawler. Perplexity uses this agent to build the corpus for its answer generation. |

**AI live fetches** occur when a real user submits a prompt to an AI assistant and the assistant fetches the page live before responding. Use this category to measure direct user demand arriving through AI assistants.

| Bot type value | Vendor | Description |
|---|---|---|
| `ChatGPT-User` | OpenAI | A user asked ChatGPT a question. ChatGPT fetched this URL to read it and form its answer. |
| `ChatGPT Clients` | OpenAI | The ChatGPT mobile app (iOS and Android) doing a live fetch. The user-agent string includes the app version and device. |
| `Claude-User` | Anthropic | A user or application using Claude live-fetched this URL. The user-agent string may identify the specific Claude product, e.g., claude-code. |
| `Perplexity-User` | Perplexity | A user asked Perplexity a question. Perplexity fetched this URL to ground its answer. |
| `Google-NotebookLM` | Google | A user opened Google NotebookLM and sourced this domain. NotebookLM fetches every reachable URL within a sourced domain. |
| `Google-ai-mode` | Google | Google Search's AI Overviews feature fetched this URL to include it in an AI-generated answer panel in search results. |
| `Gemini-Deep-Research` | Google | A user ran a Gemini Deep Research session. Deep Research makes many sequential fetches across multiple sources to compile a research report. |
| `GoogleAgent-URLContext` | Google | A user shared a URL with Gemini and asked questions about that page. Gemini fetched the URL live to answer questions about that specific content. |
| `Amzn-User` | Amazon | An Amazon Alexa or Amazon AI agent live-fetched this URL. Typically appears on reference and documentation content. |
| `MistralAI-User` | Mistral | A live fetch from a Mistral-powered product or API consumer. |

When LLM Optimizer cannot match a user-agent to a recognized pattern, it assigns the value `Unknown`. You can use the **CDN User Agent** dimension to identify what agent made those requests.

### Status codes

HTTP status codes in this dataset indicate whether the AI agent received the content it requested.

| Status | Name | Interpretation |
|--------|------|----------------|
| 200 | OK | The bot received the full response. The content was available for the AI to use. |
| 304 | Not Modified | The bot confirmed the content has not changed and used its cached version. The content was available. |
| 301 | Moved Permanently | The bot was redirected to a new URL. Each redirect adds an extra round-trip. High 301 volume on frequently crawled URLs means the redirect should be resolved at the CDN level. |
| 302 | Found (Temporary Redirect) | Same latency penalty as 301. Unlike 301, it does not signal a permanent move, so bots will keep hitting the original URL. |
| 403 | Forbidden | The CDN or origin blocked the bot. This can be intentional, e.g., through robots.txt rules or WAF policy, or unintentional, e.g., through overly broad rate limits. When AI fetches are blocked, that content cannot appear in AI answers. |
| 404 | Not Found | The URL does not exist. High 404 volume on AI agent types indicates the AI's index contains stale URLs. Use the 410 status to tell crawlers to remove a URL from their index permanently. |
| 429 | Too Many Requests | The CDN rate-limited the bot. Sustained 429 errors on live-fetch agent types mean that users asking AI assistants questions about your content will receive incomplete or missing responses. |
| 504 | Gateway Timeout | The CDN stopped waiting for the origin to respond. The content did not reach the AI. When a page times out, the AI cannot access its content and cannot include it in an answer. High 504 volume on live-fetch agent types is a direct AI visibility risk. |

### Metrics

The following metrics are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Metric | Description |
|--------|-------------|
| CDN Request Count | The total count of CDN requests, summed from the requests field across all rows. Always use this metric to measure volume. Do not use row count. |
| CDN Error Count | The count of requests that returned a 4xx or 5xx HTTP status code. |
| CDN Error Rate | The error count as a percentage of total requests. |
| CDN Avg Time to First Byte | The average time in milliseconds from when the CDN received a request to the first byte of the response. CDN-cached responses are typically under 50ms. Responses served from the origin are typically 300ms to 700ms. AI live-fetch agents often show much higher values, which correspond to timed-out or very slow origin responses. High average values on live-fetch agent types are worth investigating as an AI visibility risk. |

### Dataset boundaries

This dataset captures only bot traffic from CDN access logs. It does not contain the following:

* **Human sessions, conversions, or engagement data.** Human sessions are in your existing web analytics dataset. To correlate AI demand with human outcomes, join the two datasets in CJA at the URL and host level.
* **Any person identifier such as ECID.** You cannot make a person-level join from this dataset. The join works at the URL and host level.
* **Sub-second time granularity.** The timestamp is hourly. You cannot break down traffic within an hour into minutes or seconds.
* **Page content or rendered HTML.** This dataset records the fact of the fetch and its outcome, not what the AI read from the page.
* **Conversion data.** Whether an AI answer led a user to visit the site or convert is not in this dataset. That analysis requires joining to human session data in CJA.

## Outbound integration

To be determined.

-->