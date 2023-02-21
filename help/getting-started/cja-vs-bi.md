---
title: Confronto tra le soluzioni CJA e BI
description: Confronto tra soluzioni Customer Journey Analytics e BI
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 91cfd3ccfe1864b6a2a50a8881e73bd778a7848e
workflow-type: tm+mt
source-wordcount: '1615'
ht-degree: 0%

---


# Confronto tra le soluzioni CJA e BI

Con l’attuale attenzione all’esperienza dei clienti, i brand richiedono soluzioni avanzate per comprendere meglio il percorso olistico dei clienti. Comprendere questo percorso completo dei clienti ti consente di analizzare e ottenere informazioni utili su come i canali online e offline coinvolgono i clienti e portano ad aumentare le conversioni, la fidelizzazione e la fidelizzazione. Un percorso cliente in questo contesto può essere l&#39;ordine online diretto di un pasto a una catena alimentare sushi. Oppure l&#39;acquisto di un&#39;auto nuova, dove il cliente combina ricerca online con visite allo showroom del dealer e un acquisto finale di persona.

Molte organizzazioni hanno consolidato i propri dati omnicanale in un data lake o data warehouse. Gli strumenti di Business Intelligence (BI) vengono utilizzati in cima a questi archivi di dati per fornire i report, le visualizzazioni e le informazioni necessarie all&#39;azienda per comprendere il percorso cliente. Spesso, questa combinazione di soluzioni e strumenti è uno scopo generale per natura e design, e non si concentra esplicitamente sul cliente. Il Customer Journey Analytics (CJA) si concentra sulla responsabilizzazione dei responsabili della customer experience, ad esempio addetti al marketing, analisti di dati, esperti di data scientist. Lo strumento consente loro di visualizzare il percorso del cliente in un contesto completo su tutti i canali in tempo reale, senza limitazioni di molti altri strumenti BI.

Questa sezione della documentazione spiega le differenze fondamentali tra CJA e gli strumenti BI comunemente utilizzati, innanzitutto esaminando il flusso di lavoro generale utilizzato per raggiungere l’obiettivo sopra indicato: comprendere il percorso del cliente. Vengono quindi forniti ulteriori dettagli su come i dati vengono memorizzati, raccolti e interrogati in modo diverso tra gli strumenti CJA e BI. Infine, spiega le differenze nelle funzionalità di visualizzazione.

## Flusso di lavoro BI tradizionale

Un ostacolo frequente con gli approcci tradizionali all&#39;analisi dei percorsi dei clienti è che non è incentrato sul cliente. Ogni team raccoglie i dati in silos, analizzando e ottimizzando le esperienze in base ai dati a cui ha accesso.

![Flusso di lavoro BI tipico](./assets/biworkflow.png)

Se desideri comprendere in che modo una campagna digitale specifica influisce su un’azione offline memorizzata in un silos di dati diverso, invia una richiesta alla coda del team BI. Il team BI scrive la query necessaria per acquisire e trasformare i dati. Una volta recuperati i dati non elaborati, il team BI crea la visualizzazione. I dati vengono condivisi con te e trascorri del tempo a esaminare le informazioni ed estrarre i dati per l’attivazione in altri sistemi.

Ognuno di questi passaggi può richiedere ore, giorni o anche settimane. Se ci sono domande di follow-up o problemi con i dati interrogati, può richiedere ancora più tempo prima che tali domande siano affrontate e il ciclo continua. Per l’analisi, l’esplorazione e la comprensione costanti del percorso di clienti, questo processo è inefficiente e non scalabile. Inoltre, i team BI in genere rispondono a più di semplici domande relative al percorso dei clienti.

## CJA: Flusso di lavoro democratico per dati online e offline

CJA fornisce un ambiente per la connessione dei dati cross-channel online e offline a livello di cliente complessivo al solo scopo di comprendere il percorso del cliente. È necessaria una configurazione iniziale per connettersi e definire le visualizzazioni ai dati che si qualificano come rilevanti. Tuttavia, una volta completati, tali dati sono immediatamente disponibili per l’analisi e l’esplorazione continue, consentendo di acquisire progressivamente informazioni e comprensione dei percorsi dei clienti. democratizzando i dati combinati online e offline, puoi rispondere in pochi secondi alle domande relative al percorso dei clienti.

![Flusso di lavoro CJA](./assets/cjaworkflow.png)

È possibile utilizzare CJA per porre domande utilizzando l’ambiente dell’area di lavoro di analisi visiva e ottenere informazioni in modo quasi istantaneo. I dati e i rapporti cross-channel sono immediatamente disponibili, senza alcun codice SQL richiesto. Puoi eseguire ulteriori query e analisi con un semplice trascinamento nell’interfaccia utente, con dati completamente correlati. Puoi continuare a fare domande, esplorando progressivamente più dettagli come ti serve. Puoi quindi intraprendere azioni immediate sulle informazioni che scopri, come la condivisione di tipi di pubblico per l’attivazione e l’orchestrazione.

## Il potente motore di reporting di CJA

CJA utilizza un’architettura proprietaria potente che distribuisce l’analisi su centinaia o persino migliaia di server per visualizzare i dati in Analysis Workspace in pochi secondi. Alcune proprietà di rilievo di questa architettura di elaborazione includono:

* **Ottimizzato per query relative a singoli clienti**: Tecnicamente, CJA memorizza i dati in un motore di reporting distribuito che utilizza in modo esteso il caching. Tale motore è ottimizzato per le query reattive sui dati evento a livello individuale e, di conseguenza, è perfettamente ottimizzato per le query relative al cliente. Il motore di reporting memorizza i dati in indici bitmap orientati alle colonne che consentono un rapido calcolo immediato delle metriche aggregate. Dispone di un ampio motore di filtraggio che consente potenti analisi di segmentazione/pubblico. Inoltre, ha una comprensione fondamentale della sequenza tra i punti di dati che è utile per analizzare il comportamento tra questi punti di dati (l’ordine in cui si sono verificate le cose) e per assegnare l’attribuzione utilizzando vari modelli complessi.

* **Applicazione rapida di percorsi e filtri complessi**: Il motore di reporting funziona su set di dati gerarchici parzialmente ordinati (ad esempio, persona -> sessioni -> eventi). Tutti i dati di un oggetto di livello principale (singoli profili) risiedono su un singolo nodo di elaborazione per ottenere risultati precisi. Questo partizionamento consente di applicare rapidamente percorsi e filtri complessi. Le operazioni complesse, come la sessionizzazione, l’attribuzione, la persistenza dello stato degli attributi di dati e le opzioni di manipolazione dei dati complesse, vengono eseguite in scala con tempi di reporting rapidi. Nel mondo BI, questi tipi di operazioni in genere richiedono la creazione di nuovi cubi OLAP per ogni caso di utilizzo. Il motore di reporting di CJA consente l’accesso illimitato all’intero set di dati su ogni query, consentendo di ottenere dati completamente correlati senza bisogno di alcun cubo in anticipo.

* **Query efficiente di flussi di dati complessi**: Una delle più grandi differenze tra i database SQL e NoSQL tradizionali del motore di reporting è la sua capacità di determinare i predicati in base a relazioni orientate alla sequenza a un livello fondamentale. Queste operazioni di query fondamentali possono guardare il flusso di record, che è composto da molte sequenze interlacciate (e anche nidificate). Eseguono una query su tutti questi flussi di dati interconnessi con l&#39;efficienza di un&#39;unica operazione a sequenza contigua.

* **Progettato per rispondere rapidamente a grandi query**: Il motore di generazione rapporti non ha lo stesso scopo generale dei sistemi di grandi dimensioni tradizionali. Tuttavia, è progettato specificamente per rispondere a query che si estendono su milioni o persino miliardi di record (dati evento / eventi di esperienza), generalmente in meno di un secondo. A differenza di altri grandi sistemi di dati, non lo fa campionando i dati o precompilando le risposte a tutte le domande che pensa di poter fare. Al contrario, è in grado di calcolare le risposte abbastanza rapidamente da supportare i casi di utilizzo di query interattive. Questa progettazione specifica del motore di reporting di CJA facilita la disponibilità dei dati e l’analisi e l’esplorazione continue ad alta velocità, consentendoti quindi di acquisire progressivamente informazioni e comprendere i percorsi dei clienti.

* **Agire come soluzione BI headless**: Puoi definire le dimensioni, le metriche, i filtri in un’unica posizione e quindi qualsiasi client CJA (incluso il nostro API CJA pubblico) può accedere a tali componenti. In questo modo si sottraggono query complesse agli utenti finali e si garantisce che i risultati siano gli stessi, indipendentemente dal client di reporting o visualizzazione utilizzato.

## Funzionalità di visualizzazione uniche di CJA

Il motore di reporting è fondamentale per CJA per consentirti di interagire progressivamente con e di agire in base a tutti i dati del percorso cliente all’interno di tale motore di reporting. CJA viene fornito con un’ampia gamma di componenti che ti consentono di eseguire questa operazione visivamente e tramite trascinamento della selezione. Gli strumenti di visualizzazione BI consentono di esplorare i contenuti entro i limiti dei dati preparati da SQL (come definiti dal reparto IT). CJA consente di suddividere e suddividere il più possibile, senza dover tornare all’IT per creare un’altra visualizzazione SQL.

&quot;Progressivamente&quot; è un concetto chiave qui: contrariamente alla maggior parte delle visualizzazioni negli strumenti BI, l’interfaccia utente visiva con trascinamento della selezione di CJA consente di suddividere continuamente i dati in base alle tue esigenze specifiche: crea query visivamente utilizzando metriche, dimensioni, filtri (segmenti) rilevanti, calcoli, linee temporali, annotazioni e altri valori di analisi.

I componenti di visualizzazione incorporati sono funzionalità avanzate come:

* **Funzioni di analisi virtuale** quali [Rilevamento delle anomalie](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) che utilizzano algoritmi predittivi e apprendimento automatico per fornire informazioni su ciò che sta causando comportamenti insoliti nei dati.

* **Funzioni di analisi avanzate** che si concentrano specificamente sulle informazioni sul percorso del cliente, come [diagrammi di flusso](/help/analysis-workspace/visualizations/c-flow/flow.md), [Attribution IQ](/help/analysis-workspace/attribution/overview.md), [diagrammi di abbandono](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)e [analisi dettagliate delle dimensioni](/help/components/dimensions/t-breakdown-fa.md). Esempi di visualizzazioni predefinite:

   * [Analisi della fidelizzazione dei clienti tramite tabelle a coorte/a latenza](/help/analysis-workspace/visualizations/cohort-table/cohort-use-cases.md), in cui puoi semplicemente trascinare metriche/dimensioni in un generatore ed eseguire le operazioni in meno di 30 secondi,

   * [Abbandono](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md) / [flusso](/help/analysis-workspace/visualizations/c-flow/create-flow.md) visualizzazioni. in meno di un minuto

   * [Modelli di attribuzione](/help/analysis-workspace/attribution/algorithmic.md) come primo contatto, ultimo contatto, partecipazione, decadimento nel tempo, anche quelli personalizzati che richiedono pochi clic per la configurazione,

* **Capacità di segmentazione in ogni fase dell’esplorazione progressiva**: ogni volta che lo ritieni opportuno, puoi pubblicare nuovamente il pubblico in Experience Platform e da lì a una qualsiasi delle destinazioni supportate,

* **Sessionizzazione** completamente [personalizzabile](/help/data-views/component-settings/persistence.md): puoi determinare quando inizia e termina una sessione, come parte di un canale in un percorso di clienti.

* **Cura e democratizzazione**: Le dashboard create in CJA possono essere:

   * [Curato](/help/analysis-workspace/curate-share/curate.md) ad altri individui dell&#39;organizzazione per un&#39;esplorazione continua,
   * Esportato in Excel con [Report Builder](/help/report-builder/report-buider-overview.md) (un plug-in dedicato),
   * [Condiviso](/help/analysis-workspace/curate-share/share-projects.md) in vari formati, tra cui [PDF](/help/analysis-workspace/curate-share/download-send.md), [CSV](/help/analysis-workspace/curate-share/download-send.md) e attraverso [app mobile dedicata](/help/mobile-app/home.md), a coloro che sono interessati ai rapporti finali e/o alle visualizzazioni.

Confrontare le funzionalità di visualizzazione di CJA con quelle offerte dagli strumenti BI è difficile a causa della varietà di visualizzazioni disponibili. Alcuni strumenti BI dispongono di visualizzazioni più avanzate, ma CJA si concentra sulle visualizzazioni interattive e interoperabili dei percorsi di clienti che ti consentono di suddividere i dati in pochi secondi senza &quot;caricare&quot; per ogni query aggiuntiva.


## Riepilogo

CJA si distingue dagli strumenti BI per l’integrazione di un motore di reporting altamente ottimizzato incentrato sul percorso di clienti, con strumenti e componenti facili da usare per eseguire analisi e generare report e visualizzazioni avanzate. Il tutto dall’interno di un’unica interfaccia utente, senza che sia necessario passare da un motore di query all’altro e dall’ambiente di visualizzazione.

