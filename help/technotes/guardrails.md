---
title: Guardrail Customer Journey Analytics
description: Scopri i guardrail per Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: 88956946aabb74d94cd84a8b4ef30d9eb1044ebd
workflow-type: tm+mt
source-wordcount: '1900'
ht-degree: 7%

---

# Guardrail Customer Journey Analytics

Questo documento definisce i limiti per i vari componenti di Customer Journey Analytics. Per i guardrail, i parametri di ambito e i diritti, vedere la [descrizione del prodotto per Customer Journey Analytics](https://helpx.adobe.com/it/legal/product-descriptions/customer-journey-analytics.html), la [descrizione del prodotto per il componente aggiuntivo Adobe Analytics: Customer Journey Analytics](https://helpx.adobe.com/it/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html) o la [descrizione del prodotto per Customer Journey Analytics B2B edition](https://helpx.adobe.com/it/legal/product-descriptions/customer-journey-analytics-b2b.html).

## Tipi di limite

In questo documento sono disponibili due tipi di limiti predefiniti:

| Tipo di guardrail | Descrizione |
|----------|---------|
| **Guardrail delle prestazioni (limite soft)** | I guardrail di prestazioni sono limiti di utilizzo relativi all’ambito dei tuoi casi d’uso. Quando si superano i guardrail delle prestazioni, è possibile che si verifichi un peggioramento delle prestazioni e della latenza. Adobe non è responsabile di tale degrado delle prestazioni. I clienti che superano costantemente un Guardrail delle prestazioni possono scegliere di concedere in licenza una capacità aggiuntiva per evitare il degrado delle prestazioni. |
| **Guardrail applicati dal sistema (limite rigido)** | I guardrail applicati dal sistema vengono applicati dall’interfaccia utente o dall’API di Customer Journey Analytics. Si tratta di limiti che non possono essere superati poiché l’interfaccia utente e l’API non consentono di farlo o restituiscono un errore. |

{style="table-layout:auto"}

Alcune delle funzioni e il valore associato per il limite dipendono dal pacchetto Customer Journey Analytics a cui hai diritto.

>[!NOTE]
>
>I valori descritti in questo documento sono soggetti a modifiche in base ai continui miglioramenti apportati al prodotto. Controlla regolarmente la disponibilità di aggiornamenti. Se ti interessa conoscere i limiti personalizzati, contatta il rappresentante dell’assistenza clienti.

## Query SQL ad hoc

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Timeout Riprova | 90 | Guardrail imposto dal sistema | Numero massimo di secondi prima che il motore di reporting risponda che la richiesta impiega troppo tempo per restituire i risultati (probabilmente a causa di altre richieste simultanee); è possibile effettuare nuovamente la richiesta. |
| Non riprovare Timeout | 600 | Guardrail imposto dal sistema | Numero massimo di secondi prima del timeout delle query SQL ad hoc. In caso contrario, il numero massimo di secondi prima che i motori di reporting riferiscano che la richiesta ha impiegato troppo tempo per restituire i risultati e non deve essere ritentata. Molto probabilmente la richiesta non restituisce mai risultati a causa di problemi nel processo in background. |
| Metriche | 150 | Guardrail imposto dal sistema | Numero massimo di metriche in una richiesta. |
| Righe output query interattive | 50.000 | Guardrail imposto dal sistema | Numero predefinito di righe restituite, se non specificato diversamente. |

{style="table-layout:auto"}

## Progetti Analysis Workspace

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Righe visibili per tabella | 400 | Guardrail imposto dal sistema | Numero massimo di righe visibili in una tabella a forma libera in un progetto Analysis Workspace. |
| Righe esportabili per tabella | 50.000 | Guardrail imposto dal sistema | Numero massimo di righe che possono essere esportate per singola dimensione. |
| Pannelli per progetto | 15 | Guardrail imposto dal sistema | Numero massimo di [pannelli](../analysis-workspace/home.md#panels) per progetto. |
| Visualizzazioni per pannello | 25 | Guardrail imposto dal sistema | Numero massimo di [visualizzazioni](../analysis-workspace/home.md#visualizations) per pannello. |
| Campi derivati per tabella a forma libera | 5 | Guardrail imposto dal sistema | Numero massimo di campi derivati diversi in una singola tabella a forma libera. |
| Commenti per progetto | 1.000 | Guardrail imposto dal sistema | Numero massimo di commenti per progetto. |

{style="table-layout:auto"}


<!--

Add this to the table above, change - for pipe : (End of April, 2025 when project commenting is GA)

Comments per project - 1,000 - System-enforced Guardrail - Maximum number of comments per project. 
Replies per comment - 100 - System-enforced Guardrail - Maximum number of replies per comment. 
Images per comment - 5 - System-enforced Guardrail - Maximum number of images per comment. 
Image size - 2 - System-enforced Guardrail - Maximim upload size per image in MB 

-->

<!--

## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

-->

## Tipi di pubblico

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Segmenti di pubblico | 20 | Guardrail imposto dal sistema | Numero massimo di [segmenti](../components/segments/seg-overview.md) per pubblico. |
| Numero di identità del pubblico | 20 milioni | Guardrail imposto dal sistema | Numero massimo di identità per pubblico. |
| Frequenza aggiornamento pubblico | 4 | Guardrail imposto dal sistema | Frequenza massima in ore un [pubblico](../components/audiences/audiences-overview.md) può essere aggiornato. |
| Intervallo di lookback aggiornamento pubblico | 90 | Guardrail imposto dal sistema | Numero massimo di giorni per l’intervallo di lookback dell’aggiornamento. |
| Aggiornamento della data di scadenza del pubblico | 13 | Guardrail imposto dal sistema | Numero massimo di mesi in cui il pubblico non viene più aggiornato dalla data di creazione. I clienti possono estenderla per altri 13 mesi. |
| Numero di tipi di pubblico di aggiornamento | 74, 150 | Guardrail imposto dal sistema | Numero massimo di tipi di pubblico di aggiornamento. Il valore varia a seconda del pacchetto Customer Journey Analytics (vedi Descrizione del prodotto). |

{style="table-layout:auto"}

Consulta anche Experience Platform [Real-time Customer Data Platform Guardrail](https://experienceleague.adobe.com/it/docs/experience-platform/rtcdp/guardrails/overview).


## Scadenza set di dati automatizzato

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|:---:|
| Ordini di lavoro | 20 | Guardrail imposto dal sistema | Numero massimo di ordini di lavoro con scadenza set di dati automatizzati al mese. |

{style="table-layout:auto"}



## Connessioni, visualizzazioni dati, progetti

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Progetti | 50.000 | Guardrail imposto dal sistema | Numero massimo di progetti per un’organizzazione. |
| Visualizzazioni dati | 2.000 | Guardrail imposto dal sistema | Numero massimo di [visualizzazioni dati](../data-views/data-views.md) per un&#39;organizzazione. |
| Visualizzazioni dati | 500 - 1000 | Guardrail imposto dal sistema | Numero massimo di visualizzazioni dati per una connessione. Il valore varia a seconda del pacchetto Customer Journey Analytics (vedi Descrizione del prodotto). |
| Set di dati | 100 | Guardrail imposto dal sistema | Numero massimo di [set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=it) per connessione. |
| Connessioni | 1000 | Guardrail imposto dal sistema | Numero massimo di [connessioni](../connections/overview.md) per un&#39;organizzazione. |
| Titolo connessione | 500 | Guardrail imposto dal sistema | Numero massimo di caratteri per un titolo di connessione. |
| Metriche | 5.000 | Guardrail imposto dal sistema | Numero massimo di metriche in una visualizzazione dati. |
| Dimensioni | 5.000 | Guardrail imposto dal sistema | Numero massimo di dimensioni in una visualizzazione dati. |
| Titolo annotazione | 100 | Guardrail imposto dal sistema | Numero massimo di caratteri per un titolo di annotazione. |
| Descrizione annotazione | 250 | Guardrail imposto dal sistema | Numero massimo di caratteri per una descrizione di annotazione. |
| Campi schema | 10 | Guardrail imposto dal sistema | Numero massimo di campi schema (esclusi i campi standard) durante la definizione delle regole per un [campo derivato](../data-views/derived-fields/derived-fields.md). |
| Campi ricerca/profilo | 3 | Guardrail imposto dal sistema | Numero massimo di campi dello schema di ricerca o profilo all’interno del numero massimo di campi dello schema (esclusi i campi standard) durante la definizione delle regole per un campo derivato. |
| Campi derivati | 100 - 500 | Guardrail imposto dal sistema | Numero massimo di campi derivati per connessione. Il valore varia a seconda del pacchetto Customer Journey Analytics (vedi Descrizione del prodotto). |

{style="table-layout:auto"}


## Limiti di trasferimento dei dati

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Campi | 10.000 | Guardrail imposto dal sistema | Numero massimo di proprietà o campi per riga in un set di dati. |
| Stringhe univoche | 10 milioni | Guardrail imposto dal sistema | Numero massimo di chiavi univoche per set di dati di ricerca. |
| Righe | 1 milione | Guardrail imposto dal sistema | Numero massimo di righe per ID persona univoco in un dato mese all’interno di una connessione. |
| Dimensione riga | 2 | Guardrail delle prestazioni / Guardrail imposto dal sistema | Dimensione media in kilobyte per riga di dati acquisiti in Customer Journey Analytics (limite soft). Un limite statico per la dimensione della riga è determinato dai guardrail per l’acquisizione dei dati in Experience Platform. |

{style="table-layout:auto"}

Consulta anche Experience Platform [Guardrail per l&#39;acquisizione dei dati](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=it).


## Esportazione dei dati delle destinazioni

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Esportazione dati | Archiviazione totale del data lake autorizzato | Barra di protezione delle prestazioni | Il cliente può utilizzare l’esportazione del set di dati di destinazione per esportare i dati del cliente nel data lake fino allo storage totale autorizzato del data lake. |
| Set di dati disponibili | Profilo ed evento | Guardrail imposto dal sistema | Set di dati di evento, profilo o ricerca creati nell’interfaccia utente di Experience Platform dopo l’acquisizione o la raccolta di dati tramite Origini, Web SDK, Mobile SDK, Connettore dati di Analytics e Audience Manager. |

{style="table-layout:auto"}

Vedi anche Experience Platform [Guide di esportazione set di dati](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/guardrails#dataset-exports)


## Zona di destinazione dati

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Data Landing Zone per Sandbox | 1 | Guardrail imposto dal sistema | Numero massimo di zone di destinazione dati per sandbox. |
| Archiviazione dati | 7 | Guardrail imposto dal sistema | Numero massimo di giorni in cui i dati vengono memorizzati nella zona di destinazione dati prima di essere eliminati. |

{style="table-layout:auto"}


## Unione basata sui campi

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Set di dati uniti | 5 - 50 | Guardrail imposto dal sistema | Numero massimo di set di dati uniti per cliente. Il valore varia a seconda del pacchetto Customer Journey Analytics (vedi Descrizione del prodotto). |
| Lunghezza retrocompilazione | 6 — 25 | Guardrail imposto dal sistema | Numero massimo di mesi di dati di backfill. Il valore varia a seconda del pacchetto Customer Journey Analytics (vedi Descrizione del prodotto). |
| Intervallo di lookback/Frequenza di ripetizione | 1/1 - 30/7 | Guardrail imposto dal sistema | Intervallo di lookback massimo in giorni/Frequenza di ripetizione. Il valore varia a seconda del pacchetto Customer Journey Analytics (vedi Descrizione del prodotto). |

{style="table-layout:auto"}


## Unione basata su grafo

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Set di dati uniti | 15 — 50 | Guardrail imposto dal sistema | Numero massimo di set di dati uniti per cliente. Il valore varia a seconda del pacchetto Customer Journey Analytics (vedi Descrizione del prodotto). |
| Lunghezza retrocompilazione | 6 — 25 | Guardrail imposto dal sistema | Numero massimo di mesi di dati di backfill. Il valore varia a seconda del pacchetto Customer Journey Analytics (vedi Descrizione del prodotto). |
| Intervallo di lookback/Frequenza di ripetizione | 1/1 - 30/7 | Guardrail imposto dal sistema | Intervallo di lookback massimo in giorni/Frequenza di ripetizione. Il valore varia a seconda del pacchetto Customer Journey Analytics (vedi Descrizione del prodotto). |


## Segmenti e metriche calcolate

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Contenitori per segmento | 50 | Guardrail imposto dal sistema | Numero massimo di contenitori per segmento. |
| Metriche per metrica calcolata | 25 | Guardrail imposto dal sistema | Numero massimo di metriche per metrica calcolata. |
| Metriche e dimensioni per segmento | 25 | Guardrail imposto dal sistema | Numero massimo di metriche e dimensioni univoche per segmento. |
| Contenitori nidificati per segmento | 10 | Guardrail imposto dal sistema | Numero massimo di contenitori nidificati per segmento. |
| Regole per segmento | 100 | Guardrail imposto dal sistema | Numero massimo di regole per segmento. |
| Confronti di stringhe per Dimension per segmento | 100 | Guardrail imposto dal sistema | Numero massimo di confronti di stringhe per dimensione per segmento. |
| Metriche calcolate | 6.000 | Guardrail imposto dal sistema | Numero massimo di metriche calcolate per un’organizzazione. |
| Segmenti | 50.000 | Guardrail imposto dal sistema | Numero massimo di segmenti che è possibile definire per un’organizzazione. |
| Chiamate API | 120 | Guardrail imposto dal sistema | Richieste API al minuto (12 richieste ogni 6 secondi). |

{style="table-layout:auto"}


## Applicazione mobile

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Riquadri | 16 | Guardrail imposto dal sistema | Numero massimo di sezioni per scorecard. |
| Segmenti | 10 | Guardrail imposto dal sistema | Numero massimo di segmenti per scorecard. |
| Dimensioni | 10 | Guardrail imposto dal sistema | Numero massimo di dimensioni per scorecard. |

{style="table-layout:auto"}

## Report Builder

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Dimensione file cartella di lavoro | 5 | Guardrail imposto dal sistema | Dimensione massima del file in MB di una cartella di lavoro pianificata. |
| Blocchi di dati | 1000 | Guardrail imposto dal sistema | Numero massimo di [blocchi di dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=it) per cartella di lavoro. |
| Metriche | 20 | Guardrail imposto dal sistema | Numero massimo di metriche per blocco di dati. |
| Intervallo date | 13 | Guardrail imposto dal sistema | Numero massimo di mesi che un intervallo di date può estendere per blocco di dati. |
| Righe | 50.000 | Guardrail imposto dal sistema | Numero massimo di righe per blocco di dati. |

{style="table-layout:auto"}


## Esportazione tabella completa

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Righe per report | 3 milioni - 300 milioni | Guardrail imposto dal sistema | Numero massimo di righe di reporting per report. Il valore varia a seconda del pacchetto Customer Journey Analytics (vedi Descrizione del prodotto). |
| Raggruppamenti per tabella | 5 | Guardrail imposto dal sistema | Numero massimo di raggruppamenti per tabella. |
| Metriche per tabella | 5 | Guardrail imposto dal sistema | Numero massimo di metriche per tabella. |
| Frequenza Schedule | 1 | Guardrail imposto dal sistema | Le esportazioni possono essere programmate una volta (1) al giorno o con una pianificazione più lunga (ad esempio, una volta ogni 2 giorni o settimanalmente). |

{style="table-layout:auto"}


## Metriche e dimensioni condivise

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Libreria condivisa | 1 | Guardrail imposto dal sistema | Numero massimo di librerie condivise per una connessione. |
| Metrica condivisa | 10.000 | Guardrail imposto dal sistema | Numero massimo di metriche condivise per libreria condivisa. |
| Dimensioni condivise | 10.000 | Guardrail imposto dal sistema | Numero massimo di dimensioni condivise per libreria condivisa. |

{style="table-layout:auto"}


## Agente Data Insights

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Visualizzazioni dati | 50 | Guardrail imposto dal sistema | Numero massimo di visualizzazioni dati che possono essere abilitate per Data Insights Agent. Quando sono abilitate più visualizzazioni dati, in Data Insights Agent sono disponibili solo le visualizzazioni dati più utilizzate. Questo guardrail non influisce sulle [guardrail che definiscono il numero massimo di visualizzazioni dati che è possibile definire per una connessione o all&#39;interno dell&#39;organizzazione](#connections-data-views-projects). |


## Latenze

>[!NOTE]
>
>I tempi di elaborazione riportati di seguito sono guardrail e non accordi contrattuali sul livello di servizio (SLA). La latenza varia a seconda della configurazione del cliente, dei volumi di dati e delle applicazioni consumer. I tempi di elaborazione effettivi sono spesso più rapidi. Per informazioni sui termini contrattuali e gli SLA specifici, consultare il contratto Customer Journey Analytics. Per ulteriori informazioni, vedi [Guardrail di Experience Platform per l&#39;acquisizione dei dati](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=it).

| Flusso di dati | Latenza prevista |
|---|---|
| Connettore da Adobe Analytics ad Adobe Analytics Source (A4T abilitato) | &lt; 30 minuti |
| Connettore Source Adobe Analytics per Real-time Customer Profile (A4T non abilitato) | &lt; 2 minuti |
| Connettore Source Adobe Analytics per Real-time Customer Profile (abilitato A4T) | &lt; 30 minuti |
| Acquisizione dei dati nel Data Lake da Edge Network o acquisizione in streaming | &lt; 60 minuti |
| Acquisizione dei dati nel data lake da Adobe Analytics Source Connector | &lt; 2,25 ore |
| Acquisizione dei dati in Customer Journey Analytics da Data Lake | &lt; 90 minuti |
| Unione (funzionalità facoltativa; per ulteriori informazioni, vedere [Panoramica dell&#39;unione](../stitching/overview.md)) | &lt; 4 ore |
| Backfill del connettore Source di Adobe Analytics di meno di 10 miliardi di eventi (massimo 13 mesi di dati storici) | &lt; 4 settimane |
| Pubblicazione di tipi di pubblico su Real-time Customer Profile, inclusa la creazione automatica del segmento di streaming e la possibilità per il segmento di essere pronto a ricevere i dati. | ≈ 60 minuti |
| Frequenza di aggiornamento per i tipi di pubblico | Aggiornamento unico: latenza inferiore a 5 minuti.<br/>Aggiorna ogni 4 ore, ogni giorno, ogni settimana, ogni mese (la latenza è associata alla frequenza di aggiornamento). |

{style="table-layout:auto"}
