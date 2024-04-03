---
title: Guardrail Customer Journey Analytics
description: Scopri i guardrail per il Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: eca9b101cea489b77af0ec5287ff96907e637d1e
workflow-type: tm+mt
source-wordcount: '1523'
ht-degree: 7%

---

# Guardrail Customer Journey Analytics

Questo documento stabilisce i limiti per i vari componenti del Customer Journey Analytics. Per guardrail, parametri di ambito e diritti, vedere [Descrizione prodotto per Customer Journey Analytics](https://helpx.adobe.com/it/legal/product-descriptions/customer-journey-analytics.html) o [Descrizione del prodotto per il componente aggiuntivo Adobe Analytics: Customer Journey Analytics](https://helpx.adobe.com/it/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

## Tipi di limite

In questo documento sono disponibili due tipi di limiti predefiniti:

| Tipo di guardrail | Descrizione |
|----------|---------|
| **Guardrail delle prestazioni (limite soft)** | I guardrail di prestazioni sono limiti di utilizzo relativi all’ambito dei tuoi casi d’uso. Quando si superano i guardrail delle prestazioni, è possibile che si verifichi un peggioramento delle prestazioni e della latenza. L’Adobe non è responsabile di tale degrado delle prestazioni. I clienti che superano costantemente un Guardrail delle prestazioni possono scegliere di concedere in licenza una capacità aggiuntiva per evitare il degrado delle prestazioni. |
| **Guardrail applicati dal sistema (limite rigido)** | I guardrail applicati dal sistema vengono applicati dall’interfaccia utente o dall’API del Customer Journey Analytics. Si tratta di limiti che non possono essere superati poiché l’interfaccia utente e l’API non consentono di farlo o restituiscono un errore. |

{style="table-layout:auto"}

Alcune delle funzioni e il relativo valore associato per il limite dipendono dal pacchetto di Customer Journey Analytics a cui hai diritto.

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

{style="table-layout:auto"}

<!--
## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}
-->

## Tipi di pubblico

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Filtri del pubblico | 20 | Guardrail imposto dal sistema | Numero massimo di [filtri](../components/filters/filters-overview.md) per pubblico. |
| Numero di identità del pubblico | 20 milioni | Guardrail imposto dal sistema | Numero massimo di identità per pubblico. |
| Frequenza aggiornamento pubblico | 4 | Guardrail imposto dal sistema | Frequenza massima in ore e [pubblico](../components/audiences/audiences-overview.md) può essere aggiornato. |
| Intervallo di lookback dell’aggiornamento del pubblico | 90 | Guardrail imposto dal sistema | Numero massimo di giorni per l’intervallo di lookback dell’aggiornamento. |
| Aggiornamento della data di scadenza del pubblico | 13 | Guardrail imposto dal sistema | Numero massimo di mesi in cui il pubblico non viene più aggiornato dalla data di creazione. I clienti possono estenderla per altri 13 mesi. |
| Numero di tipi di pubblico di aggiornamento | 74, 100 | Guardrail imposto dal sistema | Numero massimo di tipi di pubblico di aggiornamento, il valore varia a seconda del pacchetto (consulta Descrizione del prodotto). |

{style="table-layout:auto"}

Vedi anche Experience Platform [Guardrail Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=it).


## Scadenza set di dati automatizzato

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|:---:|
| Ordini di lavoro | 20 | Guardrail imposto dal sistema | Numero massimo di ordini di lavoro con scadenza set di dati automatizzati al mese. |

{style="table-layout:auto"}



## Connessioni, visualizzazioni dati, progetti

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Progetti | 50.000 | Guardrail imposto dal sistema | Numero massimo di progetti per un’organizzazione. |
| Visualizzazioni dati | 2.000 | Guardrail imposto dal sistema | Numero massimo di [visualizzazioni dati](../data-views/data-views.md) per un’organizzazione. |
| Visualizzazioni dati | 50 | Guardrail imposto dal sistema | Numero massimo di visualizzazioni dati per una connessione |
| Set di dati | 100 | Guardrail imposto dal sistema | Numero massimo di [set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=it) per connessione. |
| Connessioni | 1000 | Guardrail imposto dal sistema | Numero massimo di [connessioni](../connections/overview.md) per un’organizzazione. |
| Titolo connessione | 500 | Guardrail imposto dal sistema | Numero massimo di caratteri per un titolo di connessione. |
| Metriche | 5.000 | Guardrail imposto dal sistema | Numero massimo di metriche in una visualizzazione dati. |
| Dimensioni | 5.000 | Guardrail imposto dal sistema | Numero massimo di dimensioni in una visualizzazione dati. |
| Titolo annotazione | 100 | Guardrail imposto dal sistema | Numero massimo di caratteri per un titolo di annotazione. |
| Descrizione annotazione | 250 | Guardrail imposto dal sistema | Numero massimo di caratteri per una descrizione di annotazione. |
| Campi schema | 10 | Guardrail imposto dal sistema | Numero massimo di campi schema (esclusi i campi standard) durante la definizione delle regole per un [campo derivato](../data-views/derived-fields/derived-fields.md). |
| Campi ricerca/profilo | 3 | Guardrail imposto dal sistema | Numero massimo di campi dello schema di ricerca o profilo all’interno del numero massimo di campi dello schema (esclusi i campi standard) durante la definizione delle regole per un campo derivato. |
| Campi derivati | 100 | Guardrail imposto dal sistema | Numero massimo di campi derivati per connessione. |

{style="table-layout:auto"}


## Limiti di trasferimento dei dati

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Campi | 10.000 | Guardrail imposto dal sistema | Numero massimo di proprietà o campi per riga in un set di dati. |
| Stringhe univoche | 10 milioni | Guardrail imposto dal sistema | Numero massimo di chiavi univoche per set di dati di ricerca. |
| Righe | 1 milione | Guardrail imposto dal sistema | Numero massimo di righe per ID persona univoco in un dato mese all’interno di una connessione. |
| Dimensione riga | 2 | Guardrail delle prestazioni / Guardrail imposto dal sistema | Dimensione media in kilobyte per riga di dati acquisiti nel Customer Journey Analytics (limite soft). Un limite statico per la dimensione della riga è determinato dai guardrail per l’acquisizione dei dati in Experienci Platform. |

{style="table-layout:auto"}

Vedi anche Experience Platform [Guardrail per l’acquisizione dei dati](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html).


## Zona di destinazione dati

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Data Landing Zone per Sandbox | 1 | Guardrail imposto dal sistema | Numero massimo di zone di destinazione dati per sandbox. |
| Archiviazione dati | 7 | Guardrail imposto dal sistema | Numero massimo di giorni in cui i dati vengono memorizzati nella zona di destinazione dati prima di essere eliminati. |

{style="table-layout:auto"}


## Unione basata sui campi

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Set di dati uniti | 10 | Guardrail imposto dal sistema | Numero massimo di set di dati uniti per cliente, il valore varia a seconda del pacchetto di Customer Journey Analytics applicabile (consulta la descrizione del prodotto applicabile). |
| Dati di backfill | 60 | Guardrail imposto dal sistema | Numero massimo di giorni di recupero dati. |

{style="table-layout:auto"}


## Filtri e metriche calcolate

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Contenitori per filtro | 50 | Guardrail imposto dal sistema | Numero massimo di contenitori per filtro. |
| Metriche per metrica calcolata | 25 | Guardrail imposto dal sistema | Numero massimo di metriche per metrica calcolata. |
| Metriche e Dimension per filtro | 25 | Guardrail imposto dal sistema | Numero massimo di metriche e dimensioni univoche per filtro. |
| Contenitori nidificati per filtro | 10 | Guardrail imposto dal sistema | Numero massimo di contenitori nidificati per filtro. |
| Regole per filtro | 100 | Guardrail imposto dal sistema | Numero massimo di regole per filtro. |
| Confronti di stringhe al Dimension per filtro | 100 | Guardrail imposto dal sistema | Numero massimo di confronti di stringhe per dimensione per filtro. |
| Metriche calcolate  | 6.000 | Guardrail imposto dal sistema | Numero massimo di metriche calcolate per un’organizzazione. |
| Filtri | 50.000 | Guardrail imposto dal sistema | Numero massimo di filtri che è possibile definire per un’organizzazione. |
| Chiamate API | 120 | Guardrail imposto dal sistema | Richieste API al minuto (12 richieste ogni 6 secondi). |

{style="table-layout:auto"}


## Applicazione mobile

| Nome | Valore | Tipo limite | Descrizione |
|---|--:|---|---|
| Riquadri | 16 | Guardrail imposto dal sistema | Numero massimo di sezioni per scorecard. |
| Filtri | 10 | Guardrail imposto dal sistema | Numero massimo di filtri per scorecard. |
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
| Righe per report | 3 milioni - 300 milioni | Guardrail imposto dal sistema | Numero massimo di righe di reporting per rapporto; il valore varia a seconda del pacchetto di Customer Journey Analytics applicabile (vedi la descrizione del prodotto applicabile). |
| Raggruppamenti per tabella | 5 | Guardrail imposto dal sistema | Numero massimo di raggruppamenti per tabella. |
| Metriche per tabella | 5 | Guardrail imposto dal sistema | Numero massimo di metriche per tabella. |
| Frequenza Schedule | 1 | Guardrail imposto dal sistema | Le esportazioni possono essere programmate una volta (1) al giorno o con una pianificazione più lunga (ad esempio, una volta ogni 2 giorni o settimanalmente). |

{style="table-layout:auto"}

## Latenze

>[!NOTE]
>
>I tempi di elaborazione riportati di seguito sono guardrail e non accordi contrattuali sul livello di servizio (SLA). La latenza varia a seconda della configurazione del cliente, dei volumi di dati e delle applicazioni consumer. I tempi di elaborazione effettivi sono spesso più rapidi. Per informazioni sui termini contrattuali e gli SLA specifici, fare riferimento al contratto di Customer Journey Analytics. Vedi Experience Platform [Guardrail per l’acquisizione dei dati](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html) per ulteriori informazioni.

| Flusso di dati | Latenza prevista |
|---|---|
| Connettore di origine da Adobe Analytics ad Adobe Analytics (A4T abilitato) | &lt; 30 minuti |
| Connettore di origine di Adobe Analytics per Real-time Customer Profile (A4T non abilitato) | &lt; 2 minuti |
| Connettore di origine di Adobe Analytics per Real-time Customer Profile (A4T abilitato) | &lt; 30 minuti |
| Acquisizione dei dati in Data Lake da Edge Network o Streaming Ingestion | &lt; 60 minuti |
| Acquisizione dei dati nel Data Lake dal connettore di origine di Adobe Analytics | &lt; 2,25 ore |
| Acquisizione dei dati nel Customer Journey Analytics da Data Lake | &lt; 90 minuti |
| Stitching (funzione facoltativa; vedere [Panoramica sull’unione](../stitching/overview.md) per ulteriori informazioni) | &lt; 3,25 ore |
| Recupero dal connettore di origine di Adobe Analytics di meno di 10 miliardi di eventi (massimo 13 mesi di dati storici) | &lt; 4 settimane |
| Pubblicazione di tipi di pubblico su Real-time Customer Profile, inclusa la creazione automatica del segmento di streaming e la possibilità per il segmento di essere pronto a ricevere i dati. | ≈ 60 minuti |
| Frequenza di aggiornamento per i tipi di pubblico | Aggiornamento unico: latenza inferiore a 5 minuti.<br/>Aggiorna ogni 4 ore, ogni giorno, ogni settimana, ogni mese (la latenza va di pari passo con la frequenza di aggiornamento). |

{style="table-layout:auto"}
