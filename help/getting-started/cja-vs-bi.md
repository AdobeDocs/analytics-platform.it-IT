---
title: Confronto tra Customer Journey Analytics e soluzioni BI
description: Confronto tra Customer Journey Analytics e soluzioni BI
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: ae66cd06-7ec1-4174-a3cf-939c3a66b840
source-git-commit: dd83785ea67a48e2051c60568e6fe5b436edf4db
workflow-type: tm+mt
source-wordcount: '1649'
ht-degree: 65%

---

# Confronto tra Customer Journey Analytics e soluzioni BI

Con l’attuale attenzione per l’esperienza clienti, i brand richiedono soluzioni avanzate per comprendere meglio la customer journey nel suo insieme. La comprensione di questo percorso clienti completo consente di analizzare e ottenere informazioni utili su come i canali online e offline coinvolgono l’utente e contribuiscono a incrementare le conversioni, la customer retention e la fidelizzazione. In questo contesto, un percorso potrebbe essere ad esempio il semplice ordine online di un pasto presso una catena di sushi. Oppure l’acquisto di una nuova auto, con un mix di ricerche online e visite presso una concessionaria fino all’acquisto finale di persona.

Molte organizzazioni hanno consolidato i dati omni-channel in un data lake o un data warehouse. A questi archivi di dati vengono applicati strumenti di Business Intelligence (BI) per fornire rapporti, visualizzazioni e informazioni utili a comprendere la customer journey. Spesso, viene usato un mix di soluzioni e strumenti destinati a un uso generico, e non specifici per l’anilisi della clientela. Il Customer Journey Analytics si concentra sull’emancipazione dei responsabili dell’esperienza del cliente, come addetti al marketing, analisti di dati e data scientist. Questo strumento consente di visualizzare il percorso cliente nel suo contesto completo attraverso tutti i canali in tempo reale, senza le limitazioni che caratterizzano molti strumenti di Business Intelligence.

Questa sezione della documentazione spiega le differenze fondamentali tra gli strumenti di business intelligence di Customer Journey Analytics e quelli comunemente utilizzati, innanzitutto analizzando il flusso di lavoro generale utilizzato per raggiungere l’obiettivo indicato sopra: comprendere tale percorso di clienti. Fornisce quindi ulteriori dettagli su come i dati vengono memorizzati, raccolti e interrogati in modo diverso tra gli strumenti di Customer Journey Analytics e BI. Infine, sono spiegate le differenze a livello di funzionalità di visualizzazione.

## Flusso di lavoro BI tradizionale

Spesso gli approcci tradizionali all’analisi del percorso clienti hanno lo svantaggio di non essere incentrati sulle persone. Ogni team raccoglie i dati in silos, analizzando e ottimizzando le esperienze in base ai dati a cui ha accesso.

![Flusso di lavoro tradizionale di BI come descritto in questa sezione](./assets/biworkflow.png)

Per comprendere in che modo una campagna digitale specifica influisce su un’azione offline memorizzata in un altro silos di dati, si invia una richiesta alla coda del team BI. Il team BI scrive la query necessaria per acquisire e trasformare i dati. Una volta recuperati i dati non elaborati, il team BI crea la visualizzazione. I dati vengono condivisi con l’utente, che si occuperà di esaminare le informazioni ed estrarre i dati per l’attivazione in altri sistemi.

Ognuno di questi passaggi può richiedere diverse ore, giornate o addirittura settimane. Se sorgono questiti o problemi di follow-up relativi ai dati interrogati, questi possono richiedere ulteriore tempo e il ciclo continua. Per esigenze di analisi, esplorazione e comprensione continuative del percorso clienti, questo processo è inefficiente e non scalabile. Inoltre, i team BI in genere affrontano anche altre questioni, oltre alle domande relative al percorso clienti.

## Customer Journey Analytics: flusso di lavoro semplificato per dati online e offline

Il Customer Journey Analytics fornisce un ambiente per collegare dati cross-channel online e offline a livello del cliente principale al solo scopo di comprendere il percorso del cliente. Richiede una configurazione iniziale per la [connessione](/help/connections/overview.md) ai dati qualificati come rilevanti e per [definirne le visualizzazioni](/help/data-views/data-views.md). Tuttavia, una volta completata la configurazione, tali dati sono subito disponibili per analisi ed esplorazione continuative. Progressivamente puoi così acquisire sempre più insight utili per comprendere a fondo il percorso clienti. Democratizzando i dati online e offline combinati, è possibile rispondere in pochi secondi alle domande relative al percorso clienti.

![Flusso di lavoro di Customer Journey Analytics come descritto in questa sezione](./assets/cjaworkflow.png)

Puoi usare il Customer Journey Analytics per porre domande utilizzando l’ambiente di Analysis Workspace visivo e ottenere informazioni quasi istantaneamente. I dati e i rapporti cross-channel sono immediatamente disponibili, senza la richiesta di codice SQL. Si possono eseguire ulteriori query e analisi con un semplice trascinamento nell’interfaccia utente, con i dati completamente correlati. Puoi continuare a fare domande, esplorando progressivamente più dettagli come richiesto. Puoi eseguire azioni immediate sulle informazioni scoperte, come la suddivisione dei tipi di pubblico per l’attivazione e l’orchestrazione.

## Il potente motore di reporting del Customer Journey Analytics

Il Customer Journey Analytics utilizza una potente architettura proprietaria che distribuisce l’analisi su centinaia o persino migliaia di server per visualizzare i dati in Analysis Workspace in pochi secondi. Alcune proprietà di rilievo di questa architettura di elaborazione includono:

* **Ottimizzato per singole query relative ai clienti**: tecnicamente, il Customer Journey Analytics memorizza i dati in un motore di reporting distribuito che fa un ampio utilizzo della memorizzazione in cache. Tale motore è ottimizzato per le query dinamiche sui dati di evento a livello individuale e, come tale, è perfettamente ottimizzato per le query relative al cliente. Il motore di reporting memorizza i dati in indici bitmap orientati su colonne che consentono un rapido calcolo immediato delle metriche aggregate. Dispone di un ampio motore di filtro che consente potenti analisi di segmentazione/pubblico. Inoltre, ha una comprensione essenziale della sequenza tra i punti di dati che è utile per analizzare il comportamento tra questi punti di dati (l’ordine in cui si sono verificate le cose) e per assegnare l’attribuzione utilizzando modelli vari e complessi.

* **Applicazione rapida di percorsi e filtri complessi**: il motore di reporting funziona su set di dati gerarchici parzialmente ordinati (ad esempio, persona -> sessioni -> eventi). Tutti i dati di un oggetto di primo livello (profili individuali) si trovano su un singolo nodo di elaborazione per ottenere risultati precisi. Questo partizionamento consente di applicare rapidamente percorsi e filtri complessi. Le operazioni complesse, come la creazione di sessioni, l’attribuzione, la persistenza dello stato degli attributi di dati e le opzioni di manipolazione dei dati complesse, vengono eseguite su larga scala con tempi di reporting rapidi. Nelle soluzioni BI, questo tipo di operazioni in genere richiede la creazione di nuovi cubi OLAP per ogni caso d’uso. Il motore di reporting di Customer Journey Analytics consente l’accesso illimitato all’intero set di dati su ogni query, con conseguente piena correlazione dei dati senza richiedere alcun cubing in anticipo.

* **Query efficiente di flussi di dati complessi**: una delle più grandi differenze tra i database SQL e NoSQL tradizionali e il motore di reporting è la capacità di quest’ultimo di determinare i predicati in base a relazioni orientate ad una sequenza a un livello fondamentale. Queste operazioni di query fondamentali possono esaminare il flusso di record, che è composto da molte sequenze con interfoliazione (e anche nidificate). Eseguono una query su tutti questi flussi di dati interconnessi con l’efficienza di un’unica operazione a sequenza contigua.

* **Progettato per rispondere rapidamente a query di grandi dimensioni**: il motore di reporting non ha lo stesso scopo generale dei sistemi di Big Data tradizionali. Tuttavia, è progettato specificamente per rispondere a query che si estendono su milioni o persino miliardi di record (dati evento / eventi di esperienza), generalmente in meno di un secondo. A differenza di altri sistemi di Big Data, non lo fa campionando i dati o precompilando le risposte a tutte le domande che si potrebbero fare. Al contrario, è in grado di calcolare le risposte abbastanza rapidamente da supportare i casi d’uso di query interattive. Questa progettazione specifica del motore di reporting di Customer Journey Analytics facilita la rapida e immediata disponibilità dei dati per l’analisi e l’esplorazione continue, consentendoti quindi di acquisire progressivamente informazioni approfondite e di comprendere i percorsi dei clienti.

* **Funge da soluzione di business intelligence headless**: definisci dimensioni, metriche, filtri in un’unica posizione, quindi qualsiasi client di Customer Journey Analytics (inclusa la nostra API di Customer Journey Analytics pubblica) può accedere a tali componenti. In questo modo le query complesse vengono sottratte agli utenti finali e si garantisce che i risultati siano gli stessi, indipendentemente dal client di reporting o di visualizzazione utilizzato.

## Funzionalità di visualizzazione esclusive del Customer Journey Analytics

Il motore di reporting è fondamentale per il Customer Journey Analytics per consentirti di interagire progressivamente con tutti i dati del percorso del cliente all’interno di tale motore di reporting. Il Customer Journey Analytics è dotato di un ampio set di componenti che consentono di eseguire questa operazione visivamente e tramite trascinamento della selezione. Gli strumenti di visualizzazione BI ti consentono di esplorare i contenuti entro i limiti dei dati preparati da SQL (come definiti da IT). Il Customer Journey Analytics consente di suddividere e suddividere in base alle proprie esigenze, senza dover tornare al reparto IT per creare un&#39;altra visualizzazione SQL.

&quot;Progressivamente&quot; è un concetto chiave in questo caso: a differenza della maggior parte delle visualizzazioni negli strumenti di business intelligence, l’interfaccia utente visiva con trascinamento della selezione in Customer Journey Analytics consente di suddividere continuamente i dati in base alle esigenze specifiche: puoi creare query visive in modo interattivo utilizzando metriche, dimensioni, filtri (segmenti), calcoli, linee temporali, annotazioni e altri valori di analisi rilevanti.

In questi componenti di visualizzazione sono incorporate funzionalità avanzate come:

* **Funzioni di Virtual Analyst** quali il [Rilevamento delle anomalie](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) che utilizzano algoritmi predittivi e apprendimento automatico per fornire informazioni su ciò che sta causando comportamenti insoliti nei dati.

* **Funzioni di analisi avanzate** che si concentrano specificamente sulle informazioni sul percorso del cliente, come [diagrammi di flusso](/help/analysis-workspace/visualizations/c-flow/flow.md), [Pannello Attribution](/help/analysis-workspace/c-panels/attribution.md), [diagrammi di abbandono](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), e [analisi dettagliate delle dimensioni](/help/components/dimensions/t-breakdown-fa.md). Alcuni esempi di visualizzazioni pronte all’uso sono:

   * [Analisi della conservazione dei clienti tramite tabelle coorte/di latenza](/help/analysis-workspace/visualizations/cohort-table/cohort-use-cases.md), in cui puoi semplicemente trascinare metriche/dimensioni in un generatore ed eseguire le operazioni in meno di 30 secondi,

   * visualizzazioni di [fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md) / [flusso](/help/analysis-workspace/visualizations/c-flow/create-flow.md). Configurazione in meno di un minuto.

* **Capacità di segmentazione in ogni fase dell’esplorazione progressiva**: ogni volta che lo ritieni opportuno, puoi pubblicare nuovamente il pubblico in Experience Platform e da lì a una qualsiasi delle destinazioni supportate.

* **Creazione di sessioni** completamente [personalizzabile](/help/data-views/component-settings/persistence.md): puoi determinare quando inizia e termina una sessione, come parte di un canale in un percorso di clienti.

* **Cura e democratizzazione**: le dashboard create nel Customer Journey Analytics possono essere:

   * [curate](/help/analysis-workspace/curate-share/curate.md) per altri individui dell’organizzazione per un’esplorazione continua,
   * esportate in Excel utilizzando [Report Builder](/help/report-builder/report-buider-overview.md) (un plug-in dedicato),
   * [condivise](/help/analysis-workspace/curate-share/share-projects.md) in vari formati, tra cui [PDF](/help/analysis-workspace/export/download-send.md), [CSV](/help/analysis-workspace/export/download-send.md) e attraverso una [app mobile dedicata](/help/mobile-app/home.md), con coloro che sono interessati ai rapporti finali e/o alle visualizzazioni.

Confrontare le funzionalità di visualizzazione del Customer Journey Analytics con quelle offerte dagli strumenti di business intelligence è difficile a causa della varietà di visualizzazioni disponibili. Alcuni strumenti di business intelligence dispongono di visualizzazioni più avanzate, ma Customer Journey Analytics si concentra su visualizzazioni interattive e interoperabili del percorso di clienti che consentono di suddividere i dati in pochi secondi senza dover pagare per ogni query aggiuntiva.


## Riepilogo

Il Customer Journey Analytics si differenzia dagli strumenti di business intelligence per il modo in cui integra perfettamente un motore di reporting altamente ottimizzato incentrato sul percorso del cliente con strumenti e componenti di facile utilizzo per eseguire analisi e creare rapporti e visualizzazioni avanzate. Il tutto dall’interno di un’unica interfaccia utente, senza dover passare da un motore di query all’altro e dall’ambiente di visualizzazione.
