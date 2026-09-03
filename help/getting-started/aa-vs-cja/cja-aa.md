---
title: Supporto delle funzioni di Customer Journey Analytics
description: Scopri le funzioni di Customer Journey Analytics rispetto a quelle di Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
TQID: https://experienceleague.adobe.com/3TqNaNKkAo2Ug92F5244fVbnv-Po6x5l2sAf3ZHZuCw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: e634a07b-b7ca-4af3-a124-3024ce559e17
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: aff2ef09-fc60-4018-9197-e2befd623064
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d13dba12-733d-4914-8d92-d643658bbe5d
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: d47d27f9-fcd6-414d-a127-a8a739dac811
  - id: ddf59f64-0e46-4986-a525-056acc143c70
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e0be3531-517c-451a-b2ff-6fcafd56ca0d
  - id: e2ff1689-912e-40ed-a029-ed8d02d9f34a
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 28cfbe249f20361bf56f0a6216bc715dae5a6d3a
workflow-type: tm+mt
source-wordcount: 3109
ht-degree: 99%

---

# Supporto delle funzioni di Customer Journey Analytics

Le tabelle seguenti elencano quali funzioni univoche di Customer Journey Analytics e Adobe Analytics sono supportate, parzialmente supportate o non supportate in Customer Journey Analytics. Con l’incremento delle funzioni aggiunte a Customer Journey Analytics, questi elenchi subiranno modifiche nel tempo.

## Funzioni univoche di Adobe Customer Journey Analytics {#cja-not-aa}

Nella tabella seguente sono elencate le funzioni disponibili in Customer Journey Analytics che non sono supportate in Adobe Analytics.

| Funzione | Maggiori dettagli |
| --- | --- |
| **Possibilità di combinare set di dati (come le suite di rapporti di Adobe Analytics)** | Customer Journey Analytics consente di [combinare dati](/help/connections/combined-dataset.md) provenienti da più suite di rapporti come se si trattasse di una singola suite di rapporti in Adobe Analytics. |
| **Sistemazione per qualsiasi tipo di dati** | Customer Journey Analytics è combinato con la capacità di Experience Platform di contenere tutti i tipi e schemi di dati. Utilizzando [Experience Data Model (XDM)](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/home) i dati possono essere rappresentati e organizzati in modo uniforme e sono pronti per essere combinati ed esaminati. Adobe Analytics si concentra principalmente sui dati di analisi del web e dei dispositivi mobili con alcune funzionalità per [importare i dati](https://experienceleague.adobe.com/it/docs/analytics/import/home). |
| **B2B Edition** | [Customer Journey Analytics B2B Edition](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition?lang=it) aiuta le aziende B2B ad allineare i team di marketing, vendita e prodotto fornendo insight sugli account da utilizzare per stimolare la crescita dei ricavi. Collocando l’account al centro del modello dati, tutte le analisi si concentrano sul suo percorso. L’aggiunta di un nuovo livello di entità (account, opportunità e gruppi acquisti), oltre a eventi basati su persona e tempo, crea un quadro completo del ciclo di vita di marketing e ricavi B2B. |
| **Estensione BI** | L’[Estensione BI](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-usecases/data-export/bi-extension) consente di collegare Customer Journey Analytics direttamente agli strumenti di visualizzazione di BI più diffusi, come PowerBI o Tableau. Utilizzando questa estensione, puoi far corrispondere esattamente i rapporti di BI a quelli visualizzati in Analysis Workspace e in altre interfacce di reporting di Customer Journey Analytics. Questa estensione offre un modo molto più semplice per ottenere il reporting BI per Customer Journey Analytics senza la necessità di ricreare rapporti/metriche dai dati non elaborati. |
| **Commenti nei progetti Workspace** | I commenti consentono di condividere informazioni e porre domande nel contesto di un [progetto di Analysis Workspace](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects?lang=it). Questo può semplificare le discussioni sui dati, mantenendo le conversazioni nell’ambito del contesto dei dati che vengono discussi. |
| **Content Analytics** | [Content Analytics](https://experienceleague.adobe.com/it/docs/analytics-platform/using/content-analytics/content-analytics) aiuta i marketer a comprendere in che modo i contenuti influiscono sugli indicatori di prestazioni chiave definiti da un’azienda. Oltre ai dati comportamentali, Content Analytics raccoglie i dati sul modo in cui il contenuto viene utilizzato e su come genera un impatto. |
| **Analytics tra dispositivi** | Customer Journey Analytics supporta la combinazione perfetta di set di dati specifici per dispositivo, provenienti da sessioni non autenticate e autenticate. Customer Journey Analytics consente di eseguire la retrocompilazione dei dati storici su dispositivi noti. In Adobe Analytics, questa funzionalità è limitata a una singola suite di rapporti e all’utilizzo di un grafo dei dispositivi. |
| **Agente Data Insights** | L’[agente Data Insights](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai?lang=it), che fa parte dell’Assistente IA in Customer Journey Analytics, è un agente per conversazioni di IA generativa. Utilizza i componenti della visualizzazione dati e i dati effettivi per rispondere in modo rapido ed efficiente a domande incentrate sui dati creando visualizzazioni rilevanti in Analysis Workspace. |
| **Miglioramenti della dimensione** | Customer Journey Analytics offre una grande flessibilità nell’utilizzo delle dimensioni: <ul><li>**Dimensioni personalizzate basate su numeri**:[offre la possibilità di creare dimensioni personali a bse numerica all’interno di una vista dati](/help/data-views/create-dataview.md#components).</li><li>**Ordinamento dimensioni basate su stringhe**: [ordina in modo alfabetico le dimensioni in una tabella a forma libera.](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>In Adobe Analytics erano disponibili solo alcune dimensioni numeriche incorporate e l’ordinamento delle dimensioni basate su stringhe non era possibile.</p> |
| **Campi derivati** | I [campi derivati](/help/data-views/derived-fields/derived-fields.md) consentono trasformazioni al momento dell’elaborazione del report. I dati possono essere combinati, corretti o creati immediatamente e queste trasformazioni si applicano retroattivamente a tutti i rapporti. |
| **Opzioni di sicurezza e privacy migliorate** : ambito dell’HIPAA | Customer Journey Analytics è conforme all’HIPAA e offre [opzioni di sicurezza aggiuntive](/help/privacy/cmk.md) per la conformità alle normative. Adobe Analytics non è conforme all’HIPAA. |
| **Analisi della sperimentazione** | Customer Journey Analytics può [valutare l’incremento e l’affidabilità di qualsiasi esperimento](/help/analysis-workspace/c-panels/experimentation.md) da qualsiasi origine dati definita come parte di una connessione. Questa valutazione consente di comprendere le relazioni causa-effetto tra le interazioni dei clienti che si estendono su qualsiasi canale. Analytics è limitato all’analisi di sperimentazione tramite A4T. |
| **Previsione** | La [previsione](/help/analysis-workspace/c-forecast/forecasting.md) è una funzionalità AI/ML che include una previsione statistica per i dati relativi alla serie temporale basata sui dati storici già esistenti in Customer Journey Analytics. Le previsioni possono essere visualizzate in tabelle a forma libera e in visualizzazioni con grafico a linee. |
| **Analisi guidata** | L’[analisi guidata](/help/guided-analysis/overview.md) consente agli utenti di gestire in autonomia dati e informazioni approfondite di alta qualità sul percorso cliente tramite flussi di lavoro guidati, basati sui dati cross-channel di Customer Journey Analytics. |
| **Didascalie intelligenti** | Le [didascalie intelligenti](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) utilizzano l’apprendimento automatico avanzato e l’intelligenza artificiale generativa per fornire informazioni approfondite in linguaggio naturale valide per le visualizzazioni di Workspace. Le didascalie intelligenti sono supportate nelle seguenti visualizzazioni: Linea, Multilinea, Barra, Barra orizzontale, Anello, Area, Flusso e Abbandono. |
| **Area di lavoro del percorso** | L’[area di lavoro del percorso](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas?lang=it) è una visualizzazione in Analysis Workspace che consente di analizzare il modo in cui le persone proseguono o abbandonano un percorso definito. |
| **Utilizzo del prodotto** | [Utilizzo del prodotto](https://experienceleague.adobe.com/it/docs/analytics-platform/using/tools/product-usage/usage-overview) mostra come la tua organizzazione utilizza Customer Journey Analytics. |
| **Trasformazioni al momento del rapporto** | Le [visualizzazioni dati](/help/data-views/data-views.md) in Customer Journey Analytics consentono di interpretare i dati di una connessione. Puoi cambiare o rimuovere i dati senza modificare l’implementazione. Utilizza le sottostringhe per intervenire sulle dimensioni. Crea metriche da qualsiasi valore o filtra gli eventi secondari. Tutte queste trasformazioni sono effettuate in modo non distruttivo. Adobe Analytics offre funzionalità limitate tramite suite di rapporti virtuali e una lunghezza della sessione personalizzata. |
| **Metriche e dimensioni condivise tra le visualizzazioni dati** | Le metriche e le dimensioni condivise consentono di [applicare le impostazioni di dimensioni e metriche a più visualizzazioni dati](/help/data-views/shared-metrics-dimensions/smd-overview.md). Le modifiche apportate a una dimensione o metrica condivisa si applicano a tutte le istanze di tale dimensione o metrica in tutte le visualizzazioni dati applicabili. |
| **Accesso SQL** | Utilizzando l’opzione Data Distiller, Customer Journey Analytics può rimuovere le limitazioni dei dati raccolti durante l’elaborazione backend di Adobe. Puoi modificare i dati con SQL, creare valori e set di dati specifici per la tua azienda e continuare ad approfondire. Analytics non supporta alcun tipo di accesso SQL ai propri dati. |
| **Stitching** | L’[unione delle identità](/help/stitching/overview.md) è una funzione potente che migliora l’idoneità di un set di dati evento per l’analisi cross-channel. L’analisi cross-channel è un caso d’uso principale che può essere gestito da Customer Journey Analytics. L’analisi cross-channel ti consente di combinare ed eseguire rapporti in modo semplice su più set di dati da canali diversi, in base a un identificatore comune (ID persona). |
| **Modelli in Adobe Journey Optimizer** | Puoi personalizzare la nuova interfaccia di reporting in Adobe Journey Optimizer creando o modificando un [modello](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/templates/create-templates?lang=it) in Customer Journey Analytics, quindi salvando il modello da utilizzare nella pagina Rapporti in Journey Optimizer. |
| **Dimensioni e metriche cliente illimitate** | In Customer Journey Analytics le dimensioni sono illimitate; i valori possono essere numeri, testo, oggetti, elenchi o una combinazioni di questi. Le dimensioni possono essere nidificate o gerarchiche. <br/>Al contrario, Analytics supporta fino a un massimo di 75 proprietà e 250 eVar. |
| **Valori univoci illimitati** | Customer Journey Analytics supporta valori univoci illimitati o elementi dimensionali che possono essere inseriti in un rapporto all’interno di una singola dimensione.<p>Non ci sono [limiti di cardialità su una dimensione](/help/components/dimensions/high-cardinality.md) e quindi ogni valore univoco può comparire ed essere contato.</p><p>Questo approccio elimina le limitazioni di reporting e analisi che possono verificarsi con le implementazioni di Adobe Analytics su larga scala, che causano la comparsa di etichette [!UICONTROL Traffico ridotto].</p><p>In Customer Journey Analytics è possibile visualizzare un’etichetta [!UICONTROL Valori univoci eccessivi], ma questo tipo di etichetta è meno frequente e può essere limitata applicando un segmento ai dati.</p> |

## Funzioni/componenti di Adobe Analytics completamente supportati {#full-support}

| Funzionalità di Adobe Analytics | Note sul supporto di Customer Journey Analytics |
| --- | --- |
| **Rilevazione delle anomalie** | Supporto completo |
| **Trasferimento risorse** | Supporto completo |
| **Funzioni di attribuzione** | Supporto completo |
| **Rilevamento bot** | [Supporto completo](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/bot-detection) |
| **Metriche calcolate** | Supporto completo. Eventuali metriche calcolate esistenti nella versione tradizionale di Analysis Workspace non vengono caricate in Customer Journey Analytics. |
| **Eventi calendario** | Supporto completo. Gli eventi Calendario sono stati implementati come [Annotazioni](/help/components/annotations/overview.md) in Workspace. |
| **Download di CSV** | Supporto completo |
| **Calendari personalizzati** | Supporto completo |
| **Confronto date** | Supporto completo |
| **Intervalli di date** | È supportata tutta la funzionalità per intervalli di date. |
| **Dimensioni** | Supporto completo. Customer Journey Analytics utilizza XDM e supporta dimensioni illimitate. Customer Journey Analytics non è legato alle proprietà o agli eVar personalizzati della versione tradizionale di Adobe Analytics. |
| **Eliminazione GDPR** | Supporto completo: tieni presente che le funzioni GDPR sono ora gestite in coordinamento con [!UICONTROL Adobe Experience Platform]. Customer Journey Analytics eredita tutte le modifiche apportate da [!UICONTROL Experience Platform] ai set di dati sottostanti. |
| **Reporting di incremento e affidabilità** | Supporto completo tramite [Pannello Sperimentazione](/help/analysis-workspace/c-panels/experimentation.md) |
| **Variabili elenco/Prop elenco** | Supporto completo. Customer Journey Analytics sfrutta XDM e supporta array di stringhe illimitati che possono essere utilizzati in modo simile a listVars. |
| **eVar di merchandising** | Supporto completo tramite [dimensioni e metriche di binding](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/component-settings/persistence) |
| **Metriche** | Supporto completo; Customer Journey Analytics utilizza Experience Data Model (XDM), supporta metriche illimitate e non è legato agli eventi di successo personalizzati di Adobe Analytics. Alcune metriche standard sono state rinominate da Adobe Analytics: Visitatori = Persone, Visite = Sessioni, Hit = Eventi. |
| **Migrazione di progetti, segmenti e metriche calcolate da Adobe Analytics a Customer Journey Analytics** | Supporto completo. |
| **Scorecard mobile/Dashboard** | Supporto completo |
| **Pannelli** | Supporto completo per i seguent pannelli: pannello vuoto, pannello di attribuzione, pannello a forma libera, Quick Insights ed elemento Successivo o Precedente. |
| **Esportazione PDF** | Supporto completo |
| **Cura dei progetti** | Supporto completo |
| **Collegamento del progetto** | Supporto completo |
| **Modelli di prodotto** | Include [modelli predefiniti](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/templates/use-templates) e [modelli aziendali](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/templates/create-templates#access-a-company-template). |
| **Elaborazione al momento del rapporto** | Supporto completo; Customer Journey Analytics si basa esclusivamente sull’elaborazione al momento del rapporto. |
| **Accesso API di reporting** | Supporto completo; disponibile tramite l’[API Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/). |
| **Rapporti/progetti pianificati** | Supporto completo |
| **Segmenti** | Supporto completo. In precedenza, in Customer Journey Analytics i segmenti erano denominati *Filtri*. |
| **Streaming Media Collection** | I dati multimediali in streaming sono disponibili tramite il connettore di origine di Analytics come parte del pannello Visualizzatori simultanei di contenuti multimediali e del pannello Tempo di riproduzione multimediale utilizzato in Workspace. |
| **Origini dati a livello di riepilogo** | Supporto completo |
| **Suite di rapporti virtuali** | Supporto completo. Le [visualizzazioni dati](/help/data-views/create-dataview.md) di Customer Journey Analytics corrispondono alle suite di rapporti di Adobe Analytics. |
| **Cura dei componenti della suite di rapporti virtuali** | Supporto completo. La cura dei componenti fa parte della funzionalità di visualizzazione dati. |
| **Dimensioni di dispositivo, browser, referrer e tecnologia** | Supportato per i set di dati basati sul [connettore di origine di Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/analytics) e per i set di dati generati da WebSDK. Consulta la [documentazione su quali variabili Analytics sono supportate tramite ADC](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). Se utilizzi la raccolta dati di Experience Platform Web SDK, il dispositivo e le dimensioni basate sulla ricerca del dispositivo non sono attualmente supportati. Il supporto è pianificato per il futuro. Per aggiungere ricerche per dispositivi e browser allo stream di dati Web SDK, fai riferimento a [questa documentazione](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/configure) |

## Supportato in una nuova modalità {#new-support}

| Funzione | Note |
| --- | --- |
| **Advertising** | È possibile [raccogliere i dati storici per gli ID AMO e gli ID EF da utilizzare in Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/advertising/integrations/analytics/planning/rvars-to-evars). |
| **Avvisi** | Il processo di [utilizzo degli avvisi in Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) è quasi identico a quello degli avvisi in Adobe Analytics. <p>Tuttavia, a causa dei tempi di raccolta dei dati in Customer Journey Analytics, gli avvisi orari non sono disponibili. In Customer Journey Analytics, gli avvisi possono essere configurati come giornalieri, settimanali o mensili.</p> |
| **Analytics for Target (A4T)** | [L’integrazione tra Adobe Customer Journey Analytics e Target](https://experienceleague.adobe.com/it/docs/target/using/integrate/cja/target-reporting-in-cja) fornisce potenti strumenti di analisi per il programma di ottimizzazione, che consentono di risparmiare tempo prezioso. |
| **Pubblicazione dei tipi di pubblico** | Supportata se concessa in licenza con i prodotti Customer Data Platform o Journey Optimizer di Adobe. La [pubblicazione di tipi di pubblico](/help/components/audiences/audiences-overview.md) invia tipi di pubblico a Real-time Customer Profile in Experience Platform. |
| **Classificazioni** | I set di dati di ricerca corrispondono alle classificazioni di Adobe Analytics. Le classificazioni utilizzate in Analytics possono essere importate in Experience Platform e in Customer Journey Analytics tramite il connettore di origine delle classificazioni di Analytics. I set di dati di ricerca possono anche essere caricati direttamente in Experience Platform e resi disponibili in Customer Journey Analytics. |
| **Generatore regole di classificazione** | Supportato utilizzando le [sottostringhe](/help/data-views/component-settings/substring.md) in Customer Journey Analytics. Invece dei set di dati di ricerca, vengono utilizzate manipolazioni delle stringhe al momento della generazione del rapporto. |
| **Lunghezza della sessione personalizzata** | La lunghezza della sessione può essere configurata tramite le [Impostazioni sessione](../../data-views/create-dataview.md#session-settings) in una Visualizzazione dati. Per ulteriori informazioni, consulta le [Impostazioni sessione](../../data-views/session-settings.md). <br/>La gestione degli eventi in background per dispositivi mobili è supportata tramite Adobe Experience Platform Mobile SDK. Consulta [Ciclo di vita della rete Edge](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) per ulteriori informazioni. |
| **Conversione valuta** | Supportata come parte della [formattazione di un componente metrico](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/component-settings/format) in una visualizzazione dati. |
| **Attributi cliente** | I set di dati profilo corrispondono all’attribuzione del cliente. I set di dati profilo non vengono importati automaticamente da Experience Cloud, ma devono essere caricati in Experience Platform prima di poter essere disponibili in Customer Journey Analytics. |
| **Feed dati** | L’esportazione dei set di dati di prima generazione è disponibile tramite l’[API di accesso ai dati di Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/data-access/api) e attraverso le [destinazioni di Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/export-datasets). Queste opzioni forniscono l’esportazione a livello di evento/riga di tutti i dati raccolti o acquisiti nel data lake di Experience Platform. Le colonne dei dati di post-elaborazione non sono disponibili perché le colonne post vengono calcolate in fase di query. L’esportazione delle colonne post è disponibile tramite il reporting. |
| **Reporting di Data Warehouse** | L’[Esportazione tabella completa di Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) è l’evoluzione dei rapporti Data Warehouse in Adobe Analytics, con molte nuove funzioni, spesso richieste, che oggi non sono disponibili in Data Warehouse. |
| **Dimensioni e metriche per entrata, uscita e tempo trascorso** | Supportate (le entrate e le uscite sono ora denominate Inizio sessione e Fine sessione) e calcolate in modo leggermente diverso. |
| **Impostazioni di persistenza eVar** | Le eVar non fanno più parte di Customer Journey Analytics. Tuttavia, le impostazioni di persistenza ora fanno parte di Visualizzazioni dati e sono disponibili per tutte le dimensioni. La persistenza si basa sull’elaborazione dell’ora rapporto, non sull’elaborazione della raccolta dati. Le dimensioni impostate nelle visualizzazioni dati sono limitate a una persistenza massima di 90 giorni e non supportano la persistenza illimitata. |
| **Dimensioni di segmentazione geografica** | [Supporto completo](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/configure) |
| **Unione basata sui grafici** | Tramite [Unione basata su grafo](https://experienceleague.adobe.com/it/docs/analytics-platform/using/stitching/overview#graph-based-stitching), puoi sfruttare la potenza del grafo delle identità in [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/it/docs/experience-platform/identity/home) per elevare i set di dati alla loro identità preferita. |
| **Avvisi** | Il processo di utilizzo degli [avvisi](/help/components/c-intelligent-alerts/intelligent-alerts.md) in Customer Journey Analytics è quasi identico a quello degli avvisi in Adobe Analytics. Tuttavia, esistono [differenze importanti](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-components/alerts/alerts-feature-comparison). |
| **Offuscamento IP** | Per la clientela di Customer Journey Analytics che utilizza il connettore di origine di Analytics per compilare i dati da Adobe Analytics in Customer Journey Analytics: le impostazioni di offuscamento dell’IP applicate in Adobe Analytics fluiscono nei dati di Customer Journey Analytics. Puoi controllare queste impostazioni in Adobe Analytics in base alle esigenze.<p>In questo modo i clienti di Customer Journey Analytics che utilizzano Experience Platform Web SDK possono compilare direttamente i dati in Platform e Customer Journey Analytics. Puoi utilizzare la preparazione dati per la raccolta dati in Platform per configurare regole che offuscano l’indirizzo IP in base ai requisiti della tua azienda. |
| **Canali di marketing** | Utilizzando il connettore di origine di Analytics, i dati dei canali di marketing fluiscono in Customer Journey Analytics attraverso tale connettore. Le regole del canale di marketing vengono configurate nella versione tradizionale di Adobe Analytics e alcune regole non sono supportate. Per ulteriori informazioni, consulta [Canali marketing in Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels). <br/>Per le implementazioni di Web SDK, le regole di elaborazione del canale di marketing al momento dell’elaborazione del report sono supportate tramite i [Campi derivati](../../data-views/derived-fields/derived-fields.md). |
| **Persistenza della variabile merchandising** | Supporto completo tramite [dimensioni e metriche di binding](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/component-settings/persistence) |
| **Deduplica delle metriche** | Configurata per le metriche all’interno delle Visualizzazioni dati. La deduplica delle metriche avviene a livello di persona o di sessione anziché a livello di set di dati, visualizzazione dati o connessione. |
| **Rapporti sulle sessioni nuove e ripetute** | Precedentemente ottenuti utilizzando la dimensione Numero di visite. Le sessioni nuove e ripetute sono supportate [con un intervallo di lookback di 13 mesi](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases). |
| **Regole di elaborazione, regole VISTA, regole di elaborazione del canale di marketing** | Supportate utilizzando la funzionalità Preparazione dati di Adobe Experience Platform e i [campi derivati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/derived-fields) per i set di dati basati su Web SDK e per i dati provenienti dal connettore di origine di Analytics. |
| **Variabile dei prodotti** | In Experience Platform, per soddisfare questo caso d’uso, gli utenti possono utilizzare un array di oggetti all’interno di uno schema di set di dati. In Customer Journey Analytics gli utenti possono utilizzare un qualsiasi numero di variabili di prodotto, senza essere vincolati a una singola variabile come accade invece in Adobe Analytics. |
| **Condivisione dei progetti** | La condivisione dei progetti è supportata solo tra gli utenti di Customer Journey Analytics, non esiste tra Customer Journey Analytics e la versione tradizionale di Analysis Workspace. |
| **Reporting in tempo reale** | Il reporting in tempo reale in Customer Journey Analytics mostra e aggiorna dati e visualizzazioni in uno o più pannelli di Analysis Workspace in tempo reale. |
| **Report Builder** | Supportato con un nuovo plug-in Office 365 per Microsoft Excel. |
| **Autorizzazioni utente/Controlli dell’accesso ai dati** | Customer Journey Analytics distingue tra amministratori di prodotto di [Adobe Admin Console](https://experienceleague.adobe.com/it/docs/core-services/interface/administration/admin-tool-experience-cloud), amministratori di profili di prodotto, e utenti. Solo gli amministratori di prodotto possono creare, aggiornare ed eliminare connessioni, progetti, segmenti o metriche calcolate create da altri utenti. Gli amministratori di prodotto e gli amministratori dei profili di prodotto possono modificare le visualizzazioni dati. Sono disponibili autorizzazioni aggiuntive per gli utenti, ad esempio per creare metriche calcolate, segmenti o annotazioni. |
| **Visualizzazioni** | Sono supportate tutte le visualizzazioni di Workspace. |
| **Unione cross-device/cross-channel** | Supportata per i set di dati evento contenenti informazioni di identità. Consulta [Unione](../../stitching/overview.md). |

## Supporto parziale {#partial}

| Funzione | Note |
| --- | --- |
| **Pannelli di Workspace** | Il pannello vuoto, il pannello di attribuzione, il pannello a forma libera e Quick Insights sono completamente supportati. I pannelli confronto segmenti e Analytics for Target (A4T) non sono supportati. |

## Nessun supporto, ma è pianificato {#planned}

| Funzione | Note |
| --- | --- |
| **Origini dati ID transazione** | Il supporto è pianificato. |

## Nessun supporto, non ancora pianificato {#not-planned}

| Funzione | Note |
| --- | --- |
| **Activity Map** | Il supporto non è ancora stato pianificato. |
| **Analisi dei contributi** | Il supporto non è ancora stato pianificato. |

## Mai supportate {#never}

* Metrica Persone con Cross-Device Coop
* Trigger
