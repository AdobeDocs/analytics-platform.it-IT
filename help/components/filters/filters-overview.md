---
title: Panoramica sui filtri
description: Scopri i filtri utilizzati e come creare un filtro semplice.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
source-git-commit: ff1f28015a2c52f79fae975c16bb7cb76f6179c3
workflow-type: tm+mt
source-wordcount: '1099'
ht-degree: 72%

---

# Panoramica sui filtri

Customer Journey Analytics ti consente di generare, gestire e condividere filtri potenti e precisi del pubblico e di applicarli ai rapporti. I filtri ti consentono di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni con siti web. I filtri sono progettati come approfondimenti codificati del pubblico che puoi generare in base alle tue esigenze specifiche e quindi verificare, modificare e condividere con altri membri del gruppo.

I filtri possono essere basati su attributi (tipo di browser, dispositivo, numero di visite, paese, sesso), interazioni (campagne, ricerca di parole chiave, motore di ricerca), uscite e ingressi (visitatori da Facebook, una pagina di destinazione definita, dominio di provenienza), variabili personalizzate (campo modulo, categorie definite, ID cliente) e altri criteri.

Puoi generare e salvare filtri nel Generatore di filtri o generarli da una visualizzazione Fallout (in Workspace). Inoltre, i filtri possono essere utilizzati insieme come filtri sovrapposti.

Gli strumenti per filtri includono il [Generatore di filtri](/help/components/filters/create-filters.md), per creare filtri ed eseguire un test preliminare, e il [Gestore filtri](/help/components/filters/manage-filters.md) per raccogliere i filtri, assegnare loro tag, approvarli, impostarne la protezione e condividerli all’interno dell’organizzazione.

## Tipi di filtro

Puoi creare diversi tipi di filtri in Workspace e nel Generatore di filtri, a seconda di quanto debbano essere complessi, se devono essere applicati solo a questo progetto, ecc. Di seguito è riportato un riepilogo dei tipi di filtro:

| Tipo di filtro | Creato dove? | Applicabile dove? | Quando utilizzare |
| --- | --- | --- | --- |
| Filtro elenco componenti | Fai clic su +, per passare al [Generatore di filtri](/help/components/filters/create-filters.md) | Tutti i progetti Workspace | Filtri sequenziali per filtri più complessi |
| Filtro rapido | [Generatore di filtri rapido](/help/components/filters/quick-filters.md) | Solo progetto, ma può salvare e aggiungere all’elenco dei segmenti. | Flessibilità per aggiungere/modificare una o più regole |
| Filtro del progetto ad hoc | [Trascina nella zona di rilascio segmenti di un progetto](/help/components/filters/ad-hoc-filters.md) | Solo progetto, ma può salvare e aggiungere all’elenco dei filtri. | Filtri a regola singola |
| Filtri nell’analisi dell’abbandono | [Visualizzazione ](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md) Abbandono in Analysis Workspace | Per singole visualizzazioni di abbandono | Creare filtri da un punto di contatto, aggiungere filtri come punto di contatto e confrontare flussi di lavoro chiave tra vari filtri |
| Filtro basato su metriche calcolate | [Generatore di metriche calcolate](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html) | Per una singola metrica calcolata | Applicare filtri all’interno della definizione metrica |

## Filtri sequenziali

I filtri sequenziali ti consentono di identificare i visitatori in base alla navigazione e alla visualizzazione di pagine nel sito, fornendo un filtro di azioni e interazioni definite. I filtri sequenziali consentono di identificare cosa piace a un visitatore e cosa evita. Quando si creano filtri sequenziali, l’operatore THEN viene utilizzato per definire e ordinare la navigazione dei visitatori.

Ecco un esempio:

![](assets/sequential_fil.png)

| Visita uno | Visita due | Visita tre |
| --- | --- | --- |
| Il visitatore ha visitato la pagina di destinazione principale (A), ha escluso la pagina della campagna (B), quindi ha visualizzato la pagina di prodotto (C). | Il visitatore ha nuovamente visitato la pagina di destinazione principale (A), ha escluso la pagina della campagna (B), ha visitato nuovamente la pagina di prodotto (C) e quindi una nuova pagina (D). | Il visitatore è entrato e ha seguito lo stesso percorso della prima e seconda visita, quindi ha escluso la pagina F per passare direttamente a una pagina di prodotto mirata (G). |

## Contenitori di filtri

I filtri si basano su una gerarchia a livello di Persona, Sessione ed Evento che utilizza un modello di contenitore nidificato. I contenitori nidificati ti consentono di definire gli attributi e le azioni delle persone in base alle regole tra e all’interno dei contenitori.

>[!NOTE]
>Il contenitore Persona era precedentemente noto come contenitore Visitatore. Il contenitore Sessione era denominato contenitore Visita e il contenitore Evento era il contenitore Hit.

Un filtro imposta le condizioni per filtrare un visitatore in base agli attributi o alle interazioni con il sito. Per impostare le condizioni in un filtro, imposta le regole per filtrare i visitatori in base alle loro caratteristiche e/o quelle di navigazione. Per suddividere ulteriormente i dati dei visitatori, puoi filtrare in base a visite e/o hit di visualizzazione pagina specifiche per ciascun visitatore. Il Generatore di filtri fornisce un’architettura semplice per generare questi sottoinsiemi e applicare le regole come contenitori Persona, Sessione o Evento nidificati e gerarchici.

L’architettura del contenitore utilizzata nel Generatore filtri definisce Persona come il contenitore più esterno, contenente i dati generali specifici del visitatore per visite e visualizzazioni di pagina. Un contenitore Sessione nidificato consente di impostare regole per suddividere i dati del visitatore in base alle sessioni, mentre un contenitore Evento nidificato consente di suddividere le informazioni del visitatore in base alle singole viste di pagina. Ogni contenitore consente di generare rapporti sulla cronologia di un visitatore e le sue interazioni suddivise per sessioni o di suddividere singoli eventi.

### Contenitore Persona

Il contenitore Persona include ogni visita e visualizzazione di pagina dei visitatori entro un intervallo di tempo specificato. Un filtro a livello di Persona restituisce la pagina che soddisfa la condizione più tutte le altre pagine visualizzate dal visitatore (e vincolate solo da intervalli di date definiti). Poiché è il contenitore definito in maniera più ampia, i rapporti generati a livello del contenitore Persona restituiscono le visualizzazioni di pagina per tutte le visite e consentono di generare un’analisi per più visite. Di conseguenza, il contenitore Persona è quello più suscettibile a modifiche in base a intervalli di date definiti.
I contenitori Persona possono includere valori basati sulla cronologia generale di un visitatore:

* Giorni precedenti al primo acquisto
* Pagina di ingresso originale
* Domini di riferimento originali

### Contenitore Sessione

Il contenitore Sessione consente di identificare le interazioni di pagina, le campagne o le conversioni per una sessione specifica. Il contenitore Sessione è il contenitore più comunemente utilizzato in quanto acquisisce i comportamenti per l’intera sessione di visita una volta soddisfatta la regola e consente di definire quali sessioni includere o escludere nella creazione e applicazione di un filtro. Può aiutarti a rispondere alle seguenti domande:

* Quanti visitatori hanno visualizzato le sezioni Notizie e Sport nella stessa sessione?
* Quali pagine hanno contribuito alla conversione in una vendita?

I contenitori Sessione includono valori basati sull’occorrenza per sessione:

* Numero di sessioni
* Pagina di ingresso
* Frequenza di ritorno
* Metriche di partecipazione
* Metriche allocate linearmente

### Contenitore Evento

Il contenitore Evento definisce gli eventi di pagina da includere o escludere da un filtro. Si tratta del più ristretto tra i contenitori disponibili per identificare clic specifici e visualizzazioni di pagina quando viene soddisfatta una condizione, consentendoti di visualizzare un singolo codice di tracciamento o di isolare il comportamento all’interno di una particolare sezione del sito. Puoi inoltre identificare un valore specifico quando si verifica un’azione, ad esempio il canale di marketing al momento di un ordine.

I contenitori Evento includono raggruppamenti di singole pagine basati su valori:

* Prodotti
* Proprietà elenco
* Dimensioni elenco
* Dimensioni del merchandising (nel contesto degli eventi)

## Modello di filtro preconfigurato

La funzione tradizionale di Analytics include molti filtri (filtri) e metriche calcolate pronti all’uso. Molti di essi non sono applicabili in CJA, o dovranno essere rinominati o ricreati. Altri dipenderanno da una soluzione per le variabili in base al contesto in CJA.

| Nome filtro | Descrizione |
| --- | --- |
| Tutti i dati | Si tratta di un filtro obbligatorio che viene aggiunto dinamicamente al reporting quando una metrica viene aggiunta alla riga di una tabella a forma libera. |
