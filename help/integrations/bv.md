---
title: Integrazione Brand Visibility
description: Integrare Brand Visibility con Customer Journey Analytics
feature: Experience Platform Integration
role: User
source-git-commit: e90a8d978f8d910f426dcb0fbf28881724d0f5a7
workflow-type: tm+mt
source-wordcount: '2543'
ht-degree: 2%

---


# Integrazione con Adobe Brand Visibility

[Adobe Brand Visibility](https://experienceleague.adobe.com/it/docs/llm-optimizer/using/home){target="_blank"} è un&#39;applicazione di intelligenza artificiale generativa per l&#39;ottimizzazione dei motori generativi, progettata per aiutare i brand a migliorare la visibilità, la precisione e l&#39;influenza negli ambienti di ricerca basati sull&#39;intelligenza artificiale. Brand Visibility fornisce informazioni approfondite sulla presenza dei brand nelle risposte generate dall’intelligenza artificiale, offre contenuti consigliati e automatizza le correzioni di ottimizzazione.

L’intelligenza artificiale è diventato un canale di rilevamento primario. Gli agenti LLM (Large Language Model), come ChatGPT, Claude, Copilot e Perplexity, scansionano i contenuti del brand.

>[!PREREQUISITES]
>
>È necessario disporre di un’offerta a pagamento Visibilità dei brand predisposta e connessa alla configurazione Experience Platform tramite il connettore gestito.


>[!IMPORTANT]
>
>Come parte di questa integrazione, alcuni trattamenti temporanei dei dati Brand Visibility avvengono negli Stati Uniti. I dati vengono infine memorizzati nell’area geografica designata, come configurato nel contratto Customer Journey Analytics.


## Casi d’uso

L&#39;integrazione tra Customer Journey Analytics e Brand Visibility offre i seguenti vantaggi:

* **Integrazione in entrata**: utilizza i dati Brand Visibility in Customer Journey Analytics per misurare il traffico basato su LLM (crawler bot, richieste RAG, attività agente) insieme a dati Web, mobili e di altro tipo esistenti. Sarà possibile, ad esempio:

  * Misura il traffico guidato da LLM per origine agente insieme ai canali tradizionali.

  * Identifica i contenuti molto utilizzati dai moduli LLM, ma con prestazioni inferiori nella conversione umana.

  * Rilevare dove le richieste dell’agente LLM non vanno a buon fine nei percorsi critici.

  * Confronta la domanda di bot LLM per una pagina con le conversioni e i ricavi di tale pagina nei dati web, confrontati a livello di URL e host.

* **Integrazione in uscita**: invia dati sulle prestazioni di Customer Journey Analytics a Brand Visibility in modo da ottimizzare la visibilità AI per le origini LLM che inviano traffico prezioso, ad esempio ChatGPT o Perplessity. Sarà possibile, ad esempio:

  * Scopri quali fonti LLM inviano visitatori umani che continuano a convertire o generare ricavi. Customer Journey Analytics misura questo dal traffico web di riferimento, non dal set di dati bot.
  * Classifica le origini LLM in base al valore a valle dei visitatori umani inviati, quindi concentra il tuo lavoro di visibilità AI sulle origini che ottengono i migliori risultati.


## Integrazione in entrata

Il traffico LLM raggiunge il sito in due modi. Customer Journey Analytics misura ogni modo da un’origine dati diversa.

Il primo modo è una persona che legge una risposta di IA e poi fa clic sul sito. Tale visita esegue lo stesso JavaScript che raccoglie il resto dei dati web. I dati web Customer Journey Analytics esistenti includono quindi la visita e il dominio di riferimento che ti ha inviato l’utente, ad esempio chatgpt.com. Customer Journey Analytics non etichetta queste visite come traffico AI di per sé. Per identificarli e raggrupparli, crea un campo derivato sulla connessione che corrisponde ai domini di riferimento di IA, quindi genera segmenti e rapporti su tale campo. Vedi [Campi derivati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}. Non è necessario il set di dati Brand Visibility per questo traffico umano.

Il secondo modo è un bot o un agente che richiede direttamente le pagine. Ciò include crawler che generano un indice di intelligenza artificiale e recuperi live che si verificano quando un utente invia una richiesta a un assistente di intelligenza artificiale. Queste richieste non eseguono JavaScript, pertanto i dati web esistenti non li registrano. Il set di dati Brand Visibility acquisisce questo traffico dal livello CDN. Il resto di questa sezione descrive tale set di dati.

### Integrare il set di dati in Customer Journey Analytics

Il connettore gestito Brand Visibility fornisce i dati ad Experience Platform come set di dati di riepilogo. Per misurarlo in Customer Journey Analytics, è necessario completare due passaggi di configurazione:

1. Crea una connessione che includa il set di dati Brand Visibility. Vedi [Creare o modificare una connessione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}.
2. Crea una visualizzazione dati sulla connessione. La visualizzazione dati rende disponibili in Analysis Workspace le dimensioni e le metriche riportate di seguito. Consulta [Creare o modificare una visualizzazione dati](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}.

Il set di dati:

* Utilizza [set di dati di riepilogo](/help/data-views/summary-data.md) basati sulla classe Metriche di riepilogo XDM.
* Dati bucket per URL e host, ora e caratteristiche di richiesta come tipo di bot, provider CDN e stato.

>[!NOTE]
>
>Il set di dati Brand Visibility contiene dati aggregati. Non contiene dati PII come identificatori utente, prompt o risposte.
>

Poiché è un set di dati di riepilogo, puoi considerarlo come un set di dati di ricerca e unirlo a un set di dati evento su una chiave full URL.

Brand Visibility fornisce questa chiave nella dimensione **URL CDN**. Combina l’host e il percorso richiesto in un unico URL completo normalizzato, in modo simile a come Customer Journey Analytics memorizza i dati web. La riuscita dell’unione dipende dalla tua raccolta di dati. Il set di dati dell’evento richiede un campo URL completo equivalente o un campo che puoi analizzare e normalizzare per corrispondere all’URL fornito da Brand Visibility. Quando entrambi i lati risolvono lo stesso URL completo, il record Visibilità dei brand corrisponde alla pagina corrispondente nei dati web.

### Informazioni sul set di dati

Brand Visibility legge i registri di accesso CDN sul lato server ed estrae i record in cui la parte richiedente è un bot o un agente automatizzato. Poiché i dati provengono dal livello CDN, Brand Visibility acquisisce le richieste dei bot che non attivano alcun tag JavaScript. Gli strumenti di analisi web standard non tengono conto di questo traffico.

Il set di dati utilizza il gruppo di campi **Riepilogo richieste CDN**. Ogni campo si trova sotto un oggetto `cdn`, pertanto i nomi dei campi nelle tabelle seguenti assumono la forma `cdn.<name>`, ad esempio `cdn.url` e `cdn.botType`.

Ogni record descrive una combinazione di host, percorso URL, tipo di bot, provider CDN, codice di stato, referrer, host inoltrato e tempo al primo byte per un’ora. Quando la stessa combinazione appare più di una volta all’ora, Customer Journey Analytics combina tali record in un’unica riga e aumenta il conteggio delle richieste. Utilizza la metrica **Numero richieste CDN** per misurare il volume. Non utilizzare il conteggio delle righe.

### Dimensioni

Le dimensioni seguenti sono disponibili per l’utilizzo come componenti in una visualizzazione dati dopo aver impostato una connessione che include un set di dati Visibilità dei brand. La colonna **Campo** mostra il campo di origine nel gruppo di campi Riepilogo richieste CDN.

| Dimensione | Campo | Descrizione |
|-----------|-------|-------------|
| URL CDN | `cdn.url` | L’URL completo normalizzato della richiesta, inteso come chiave di unione. Brand Visibility combina l’host e il percorso richiesto in un unico URL e lo normalizza in modo che corrisponda al modulo URL completo memorizzato da Customer Journey Analytics per i dati web. Utilizza questa dimensione per unire il set di dati di ricerca Brand Visibility a un set di dati evento con un campo full-URL equivalente. Include l’host e il percorso, ma non lo schema. |
| Percorso URL CDN | `cdn.path` | Il percorso URL non elaborato e la stringa di query richiesti dall’agente, come consegnati dalla rete CDN. Non include lo schema o l&#39;host. Utilizzalo quando hai bisogno del percorso richiesto esatto anziché della chiave di join normalizzata. |
| Host CDN | `cdn.host` | Il nome host che ha ricevuto la richiesta, ad esempio www.example.com. Questo host fa anche parte della chiave di join dell’URL CDN. Un set di dati può contenere più host quando un’organizzazione ha più sottodomini sullo stesso account CDN. |
| Tipo di bot CDN | `cdn.botType` | Classificazione di visibilità dei brand dell&#39;agente richiedente. I valori coprono i crawler di ricerca classici, i crawler di indice IA e gli agenti Live Fetch di IA. Per la tassonomia completa, consulta le [categorie dell&#39;agente bot](#bot-agent-categories) di seguito. |
| Agente utente CDN | `cdn.userAgent` | Stringa non elaborata dell’agente utente dal registro CDN. Utile per distinguere i sottotipi all’interno di una classificazione bot o per convalidare la classificazione assegnata per Visibilità dei brand. |
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

Quando Brand Visibility non riesce a far corrispondere un agente utente a un modello riconosciuto, assegna il valore `Unknown`. È possibile utilizzare la dimensione **Agente utente CDN** per identificare l&#39;agente che ha effettuato tali richieste.

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

Le metriche seguenti sono disponibili per l’utilizzo come componenti in una visualizzazione dati dopo aver impostato una connessione che include un set di dati Brand Visibility. La colonna **Campo** mostra il campo di origine nel gruppo di campi Riepilogo richieste CDN.

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
