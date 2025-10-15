---
title: Utilizzare i campi derivati per creare rapporti sul traffico generato da LLM e AI
description: Scopri come utilizzare i campi derivati come base per creare rapporti sul traffico generato da LLM e AI in Workspace.
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 39b3e0eb43e69c81c12e56fc7605e5746c2d650c
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 1%

---


# Rapporto su LLM e traffico generato da IA

Questo articolo del caso d’uso illustra come utilizzare la funzionalità dei campi derivati da Customer Journey Analytics come base per creare rapporti sul traffico generato da LLM (Large Language Model) e AI.

>[!NOTE]
>
>L&#39;efficacia dei [metodi di rilevamento](#detection-methods), delle [firme di rilevamento](#detection-signatures) e delle [strategie di implementazione](#implementation) dipende dal metodo di raccolta dati specifico, dalla copertura del set di dati di Experience Platform e dall&#39;implementazione di Customer Journey Analytics. I risultati possono variare in base all’ambiente tecnico, alle politiche di governance dei dati e all’approccio di implementazione. Quando utilizzi Experience Edge, devi scegliere se registrare la stringa non elaborata dell’agente utente o raccogliere le informazioni sul dispositivo.
>

## Metodi di rilevamento

Per rilevare il traffico generato da LLM e AI, distingui tra:

* **LLM crawler**: raccogli i dati per l&#39;addestramento e il recupero di generazione aumentata (RAG).
* **Agenti AI**: fungono da interfacce che eseguono attività per conto di utenti umani. Gli agenti di intelligenza artificiale preferiscono interagire tramite API, ignorando così i metodi di tracciamento dell’analisi web. Tuttavia, puoi ancora analizzare una parte significativa del traffico generato dall’intelligenza artificiale tramite i siti web.

Tre metodi comuni di rilevamento di base per identificare e monitorare il traffico generato da LLM e AI sono:

* **Identificazione dell&#39;agente utente**: quando viene effettuata una richiesta al server, l&#39;intestazione dell&#39;agente utente HTTP viene estratta e analizzata in base ai pattern noti dell&#39;agente e del crawler di IA. Questo metodo lato server richiede l’accesso alle intestazioni HTTP ed è più efficace se implementato a livello di raccolta dati.
* **Classificazione del referente**: l&#39;intestazione del referente HTTP contiene l&#39;URL della pagina Web precedente collegata alla richiesta corrente. Questa intestazione mostra quando gli utenti fanno clic sul tuo sito da interfacce web come ChatGPT o Perplexity.
* **Rilevamento parametri di query**: i servizi di IA possono aggiungere parametri URL (in particolare parametri UTM) ai collegamenti. Questi parametri persistono nell’URL e possono essere rilevati tramite implementazioni di analisi standard, rendendo questi parametri URL indicatori preziosi anche in scenari di tracciamento lato client.


La tabella seguente illustra come i metodi di rilevamento possono essere utilizzati in diversi scenari di interazione LLM e AI.

| Scenario | Identificazione dell’agente utente | Classificazione referrer | Rilevamento dei parametri di query |
|---|---|---|---|
| **Apprendimento di un modello** | L&#39;agente (`GPTBot`, `ClaudeBot` e altro) può essere identificato quando viene implementata la registrazione lato server. | Non è possibile alcuna classificazione. I crawler basati su IA non generano referrer durante l’apprendimento. | Rilevamento impossibile. I crawler basati su IA non aggiungono parametri durante l’apprendimento. |
| **Esplorazione agente** | L&#39;agente (`ChatGPT-User`, `claude-web`) può essere identificato quando la registrazione lato server acquisisce le intestazioni. | La classificazione è possibile se l’agente passa da un’interfaccia IA con conservazione del referente. | Il rilevamento è talvolta possibile se il servizio AI aggiunge parametri di tracciamento. |
| **Recupero della generazione aumentata (RAG) per rispondere alla query** | L&#39;agente (`OAI-SearchBot`, `PerplexityBot`) può essere identificato con la registrazione lato server. | In genere non è possibile effettuare alcuna classificazione, in quanto le operazioni RAG spesso ignorano i meccanismi di riferimento. | Il rilevamento è raramente possibile se non specificamente implementato dal provider di IA. |
| **L&#39;utente fa clic su** | Impossibile identificare l&#39;agente. L’agente di IA viene visualizzato come un normale agente utente. | La classificazione è possibile quando gli utenti fanno clic sui collegamenti dalle interfacce di intelligenza artificiale ([chatgpt.com](https://chatgpt.com), [claude.ai](https://claude.ai) e altro). | Il rilevamento è possibile quando i servizi di intelligenza artificiale aggiungono parametri UTM ai collegamenti in uscita. |
| **Condizioni di visibilità del traffico** | Richiedi integrazione di registrazione lato server con Customer Journey Analytics o assegnazione di tag lato server per l’identificazione dell’agente. | La classificazione dipende dai criteri del referente della piattaforma di intelligenza artificiale e dalla corretta trasmissione delle intestazioni HTTP. | Il rilevamento richiede la conservazione dei parametri tramite reindirizzamenti e la corretta raccolta di parametri URL. |

### Sfide

Gli agenti LLM e AI mostrano comportamenti complessi e in evoluzione durante l’interazione con le proprietà digitali. Queste tecnologie operano in modo incoerente su più piattaforme e versioni. Questa incoerenza crea problemi unici per i professionisti dei dati. I modelli comportamentali variano in modo significativo e dipendono dalla piattaforma di intelligenza artificiale, dalla versione e dalla modalità di interazione utilizzate. Questa diversità operativa complica gli sforzi per tenere traccia e classificare il traffico generato da LLM e dall’intelligenza artificiale all’interno dei framework di analisi standard. La natura complessa di queste interazioni, combinata con la loro rapida evoluzione, richiede metodi di rilevamento e classificazione sfumati per mantenere l’integrità dei dati:

* **Raccolta dati parziale**: alcuni agenti di intelligenza artificiale più recenti eseguono JavaScript con limiti, causando dati di analisi incompleti per le implementazioni lato client. Di conseguenza, alcune interazioni vengono tracciate, mentre altre vengono ignorate.
* **Dati della sessione incoerenti**: gli agenti di IA potrebbero eseguire JavaScript in modo diverso nelle sessioni o nei tipi di pagina. Questa differenza di esecuzione crea percorsi di utenti frammentati in Customer Journey Analytics per le implementazioni lato client.
* **Problemi di rilevamento**: con il tracciamento parziale, il rilevamento diventa inaffidabile in quanto alcuni punti di contatto potrebbero essere invisibili ad Analytics.


## Firme di rilevamento

A partire da agosto 2025, per ciascuno dei metodi di rilevamento possono essere identificati i seguenti segnali specifici.

### Identificazione dell’agente utente

<table>
<thead>
<tr>
<th>Crawler</th>
<th>Stringa agente utente</th>
<th>Finalità/Comportamento</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>GPTBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; GPTBot/1.1; +<a href="https://openai.com/gptbot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/gptbot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">Web crawler principale di OpenAI per la formazione di ChatGPT e modelli di linguaggio</a></td>
</tr>
<tr>
<td><strong>ChatGPT-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/1.0; +<a href="https://openai.com/bot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/bot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">Utilizzato quando ChatGPT naviga sui siti web per conto degli utenti (legacy)</a></td>
</tr>
<tr>
<td><strong>ChatGPT-User v2</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/2.0; +<a href="https://openai.com/bot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/bot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">Versione aggiornata di ChatGPT per il recupero su richiesta e le ricerche in risposta</a></td>
</tr>
<tr>
<td><strong>OAI-SearchBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; OAI-SearchBot/1.0; +<a href="https://openai.com/searchbot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/searchbot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">Crawler di ChatGPT incentrato sulla ricerca per individuare contenuti</a></td>
</tr>
<tr>
<td><strong>ClaudeBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ClaudeBot/1.0; +claudebot@anthropic.com</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Crawler antropico per l'addestramento e l'aggiornamento dell'assistente Claude AI</a></td>
</tr>
<tr>
<td><strong>Claude-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Claude-User/1.0; +Claude-User@anthropic.com)</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Supporta Claude AI utenti quando gli individui fanno domande a Claude, può accedere ai siti web utilizzando un Cl...</a></td>
</tr>
<tr>
<td><strong>Claude-SearchBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Claude-SearchBot/1.0; +Claude-SearchBot@anthropic.com)</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Naviga sul web per migliorare la qualità dei risultati di ricerca per gli utenti Claude AI analizzando il contenuto...</a></td>
</tr>
<tr>
<td><strong>PerplexityBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; PerplexityBot/1.0; +<a href="https://www.perplexity.ai/perplexitybot" target="_blank" rel="noopener nofollow noreferrer">https://perplexity.ai/perplexitybot</a>)</code></td>
<td><a href="https://docs.perplexity.ai/guides/bots" target="_blank" rel="noopener nofollow noreferrer">Crawler di Perplexity.ai per l’indicizzazione dei dati web in tempo reale</a></td>
</tr>
<tr>
<td><strong>Perplessità-Utente</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Perplexity-User/1.0; +<a href="https://www.perplexity.ai/useragent" target="_blank" rel="noopener nofollow noreferrer">https://www.perplexity.ai/useragent</a>)</code></td>
<td><a href="https://docs.perplexity.ai/guides/bots" target="_blank" rel="noopener nofollow noreferrer">Carica le pagine quando gli utenti fanno clic sulle citazioni di Perplessità (ignora robots.txt)</a></td>
</tr>
<tr>
<td><strong>Google - Esteso</strong></td>
<td><code>Mozilla/5.0 (compatible; Google-Extended/1.0; +<a href="https://support.google.com/webmasters/answer/182072" target="_blank" rel="noopener nofollow noreferrer">http://www.google.com/bot.html</a>)</code></td>
<td><a href="https://blog.google/technology/ai/an-update-on-web-publisher-controls/" target="_blank" rel="noopener nofollow noreferrer">Crawler Google incentrato sull'intelligenza artificiale per Gemini separato da Googlebot standard</a></td>
</tr>
<tr>
<td><strong>BingBot</strong></td>
<td><code>Mozilla/5.0 (compatible; BingBot/1.0; +<a href="http://www.bing.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.bing.com/bot.html</a>)</code></td>
<td>Crawler Microsoft che alimenta Bing Search e Bing Chat (Copilot)</td>
</tr>
<tr>
<td><strong>DuckAssistBot</strong></td>
<td><code>Mozilla/5.0 (compatible; DuckAssistBot/1.0; +<a href="https://duckduckgo.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.duckduckgo.com/bot.html</a>)</code></td>
<td><a href="https://duckduckgo.com/duckduckgo-help-pages/results/duckassistbot" target="_blank" rel="noopener nofollow noreferrer">Elimina contenuto per DuckAssist, funzionalità di risposta di IA privata di DuckDuckGo</a></td>
</tr>
<tr>
<td><strong>YouBot</strong></td>
<td><code>Mozilla/5.0 (compatible; YouBot (+<a href="http://www.you.com" target="_blank" rel="noopener nofollow noreferrer">http://www.you.com</a>))</code></td>
<td>Crawler dietro la ricerca AI di You.com e assistente del browser</td>
</tr>
<tr>
<td><strong>meta-externalagent</strong></td>
<td><code>Mozilla/5.0 (compatible; meta-externalagent/1.1 (+<a href="https://developers.facebook.com/docs/sharing/webmasters/web-crawlers" target="_blank" rel="noopener nofollow noreferrer">https://developers.facebook.com/docs/sharing/webmasters/crawler</a>))</code></td>
<td><a href="https://developers.facebook.com/docs/sharing/webmasters/web-crawlers#identify-2" target="_blank" rel="noopener nofollow noreferrer">bot di Meta per la raccolta di dati per addestrare o perfezionare i moduli LLM</a></td>
</tr>
<tr>
<td><strong>Amazonbot</strong></td>
<td><code>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKit/600.2.5 (KHTML, like Gecko) Version/8.0.2 Safari/600.2.5 (Amazonbot/0.1; +<a href="https://developer.amazon.com/amazonbot" target="_blank" rel="noopener nofollow noreferrer">https://developer.amazon.com/support/amazonbot</a>)</code></td>
<td><a href="https://developer.amazon.com/amazonbot" target="_blank" rel="noopener nofollow noreferrer">Crawler di Amazon per applicazioni di ricerca e IA</a></td>
</tr>
<tr>
<td><strong>Applebot</strong></td>
<td><code>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_5) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/13.1.1 Safari/605.1.15 (Applebot/0.1; +<a href="https://support.apple.com/kb/HT6619" target="_blank" rel="noopener nofollow noreferrer">http://www.apple.com/go/applebot</a>)</code></td>
<td><a href="https://support.apple.com/en-us/119829" target="_blank" rel="noopener nofollow noreferrer">Crawler Apple per Spotlight, Siri e Safari</a></td>
</tr>
<tr>
<td><strong>Applebot-Extended</strong></td>
<td><code>Mozilla/5.0 (compatible; Applebot-Extended/1.0; +<a href="https://www.apple.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.apple.com/bot.html</a>)</code></td>
<td><a href="https://support.apple.com/en-us/119829" target="_blank" rel="noopener nofollow noreferrer">Crawler incentrato sull’intelligenza artificiale di Apple per i futuri modelli di intelligenza artificiale (consenso)</a></td>
</tr>
<tr>
<td><strong>Bytespider</strong></td>
<td><code>Mozilla/5.0 (compatible; Bytespider/1.0; +<a href="https://www.bytedance.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.bytedance.com/bot.html</a>)</code></td>
<td>Raccolta di dati di IA di ByteDance per TikTok e altri servizi</td>
</tr>
<tr>
<td><strong>Utente MistralAI</strong></td>
<td><code>Mozilla/5.0 (compatible; MistralAI-User/1.0; +<a href="https://mistral.ai/bot" target="_blank" rel="noopener nofollow noreferrer">https://mistral.ai/bot</a>)</code></td>
<td><a href="https://docs.mistral.ai/robots/" target="_blank" rel="noopener nofollow noreferrer">Recupero della citazione in tempo reale di Mistral per l’assistente di "Le Chat"</a></td>
</tr>
<tr>
<td><strong>cohere-ai</strong></td>
<td><code>Mozilla/5.0 (compatible; cohere-ai/1.0; +<a href="http://www.cohere.ai/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.cohere.ai/bot.html</a>)</code></td>
<td>Raccoglie dati testuali per i modelli di linguaggio Cohere</td>
</tr>
</tbody>
</table>


### Classificazione referrer

<table>
<thead>
<tr>
<th><strong>Origine</strong></th>
<th><strong>Pagina di provenienza</strong></th>
<th><strong>Tipo di traffico</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>ChatGPT</td>
<td>chatgpt.com</td>
<td>Traffico diretto dall’interfaccia ChatGPT</td>
</tr>
<tr>
<td>Claude</td>
<td>claude.ai</td>
<td>Traffico dall'interfaccia Claude di Anthropic</td>
</tr>
<tr>
<td>Google Gemini</td>
<td>gemini.google.com</td>
<td>Traffico dall’assistente AI di Google</td>
</tr>
<tr>
<td>Copilota Microsoft</td>
<td>copilot.microsoft.com</td>
<td>Traffico dall’assistente AI di Microsoft</td>
</tr>
<tr>
<td>Copilota Microsoft</td>
<td>m365.cloud.microsoft</td>
<td>Traffico dall’assistente AI di Microsoft (Microsoft 365 Cloud Services)</td>
</tr>
<tr >
<td>IA perplessità</td>
<td>perplexity.ai</td>
<td>Traffico da ricerca IA con citazioni</td>
</tr>
<tr>
<td>META AI</td>
<td>meta.ai</td>
<td>Traffico dall’assistente AI di Meta</td>
</tr>
</tbody>
</table>

### Rilevamento dei parametri di query

<table>
<thead>
<tr>
<th><strong>Servizio LLM</strong></th>
<th>URL di esempio</th>
<th><strong>Parametro query</strong></th>
<th><strong>Esempio di valore</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>ChatGPT</td>
<td ><a href="https://www.yoursite.com/product?utm_source=chatgpt.com" target="_blank" rel="noopener nofollow noreferrer">https://www.yoursite.com/product?utm_source=chatgpt.com</a></td>
<td>utm_source</td>
<td>chatgpt.com</td>
</tr>
<tr>
<td>Perplessità</td>
<td><a href="https://www.yoursite.com/article?utm_source=perplexity" target="_blank" rel="noopener nofollow noreferrer">https://www.yoursite.com/article?utm_source=perplexity</a></td>
<td>utm_source</td>
<td>perplessità</td>
</tr>
</tbody>
</table>


## Implementazione

È possibile creare rapporti sul traffico generato da LLM e AI all&#39;interno di una tipica configurazione di Customer Journey Analytics ([connessione](/help/connections/overview.md), [visualizzazioni dati](/help/data-views/data-views.md) e [progetti Workspace](/help/analysis-workspace/home.md)) tramite la configurazione specifica di [campi derivati](#derived-fields), [segmenti](#segments) e [progetti Workspace](#workspace-project).


### Campi derivati

Per configurare i metodi di rilevamento e i segnali di rilevamento, utilizza i campi derivati come base. Ad esempio, definisci i campi derivati per [identificazione agente utente](#user-agent-identification), [rilevamento parametri query](#query-parameter-detection) e [classificazione referrer](#referrer-classification).

#### Identificazione dell’agente utente LLM/AI

Utilizza le funzioni di campo derivato [Case When](/help/data-views/derived-fields/derived-fields.md#case-when) per definire un campo derivato che identifica gli agenti utente LLM/AI.

![Identificazione agente utente LLM/AI](assets/aitraffic-useragents.png){zoomable="yes"}


#### Rilevamento parametri query LLM/AI

Utilizza le funzioni di campo derivato [URL Parse](/help/data-views/derived-fields/derived-fields.md#url-parse) e [Classify](/help/data-views/derived-fields/derived-fields.md#classify) per definire un campo derivato che rileva i parametri di query.

![Rilevamento parametri LLM/AI UTM](assets/aitraffic-utmparams.png){zoomable="yes"}


#### Classificazione del referente LLM/AI

Utilizza le funzioni di campo derivato [URL Parse](/help/data-views/derived-fields/derived-fields.md#url-parse) e [Classify](/help/data-views/derived-fields/derived-fields.md#classify) per definire un campo derivato che classifica i referenti.

![LLM/Classificazione referrer AI](assets/aitraffic-referrers.png){zoomable="yes"}


### Segmenti

Configura segmenti dedicati che ti aiutano a identificare eventi, sessioni o persone correlati al traffico generato da LLM e AI. Ad esempio, utilizza i campi derivati creati in precedenza per definire un segmento che identifica il traffico generato da LLM e AI.

![LLM e segmento di traffico generato da IA](assets/aitraffic-segment.png){zoomable="yes"}


### progetto Workspace

Utilizza i campi e i segmenti derivati per generare rapporti e analisi sul traffico generato da LLM e AI. Ad esempio, consulta il progetto annotato di seguito.

![Progetto Workspace per traffico generato da LLM e AI](assets/aitraffic-workspace.png){zoomable="yes"}



>[!MORELIKETHIS]
>
>Questo articolo del caso d&#39;uso si basa sull&#39;articolo del blog [Tracciamento e analisi del traffico generato da LLM e AI in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/tracking-and-analyzing-llm-and-ai-generated-traffic-in-adobe/ba-p/771967).
>
>
