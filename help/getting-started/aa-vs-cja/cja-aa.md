---
title: Supporto delle funzioni di Customer Journey Analytics
description: Confronto tra le funzioni di Customer Journey Analytics e quelle di Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 8e6f16acc475fb89c9b9ba50ccef174d3c7b10ea
workflow-type: tm+mt
source-wordcount: '2189'
ht-degree: 96%

---

# Supporto delle funzioni di Customer Journey Analytics

Le tabelle seguenti elencano le funzioni di Adobe Analytics supportate, parzialmente supportate o non supportate in Customer Journey Analytics e le funzioni di Customer Journey Analytics non supportate o disponibili in Adobe Analytics. Con l’incremento delle funzioni aggiunte a Customer Journey Analytics, questi elenchi subiranno modifiche nel tempo.

## Funzionalità/componenti completamente supportati {#full-support}

| Funzionalità di Adobe Analytics | Note sul supporto |
| --- | --- |
| Rilevamento delle anomalie | Supporto completo |
| Attribution IQ | Supporto completo |
| Rilevamento bot | [Supporto completo](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=it) |
| Metriche calcolate | Supporto completo. Eventuali metriche calcolate esistenti nella versione tradizionale di Analysis Workspace non vengono caricate in Customer Journey Analytics. |
| Eventi calendario | Supporto completo. Gli eventi Calendario sono stati implementati come [Annotazioni](/help/components/annotations/overview.md) in Workspace. |
| Download di CSV | Supporto completo |
| Calendari personalizzati | Supporto completo |
| Confronto date | Supporto completo |
| Intervalli di date | È supportata tutta la funzionalità per intervalli di date. |
| Dimensioni | Supporto completo. Customer Journey Analytics utilizza XDM e supporta dimensioni illimitate. Customer Journey Analytics non è legato alle proprietà o agli eVar personalizzati della versione tradizionale di Adobe Analytics. |
| Eliminazione GDPR | Supporto completo: tieni presente che le funzioni GDPR sono ora gestite in coordinamento con [!UICONTROL Adobe Experience Platform]. Customer Journey Analytics eredita tutte le modifiche apportate da [!UICONTROL Experience Platform] ai set di dati sottostanti. |
| Reporting di incremento e affidabilità | Supporto completo tramite [Pannello Sperimentazione](/help/analysis-workspace/c-panels/experimentation.md) |
| Variabili elenco/Prop elenco | Supporto completo. Customer Journey Analytics sfrutta XDM e supporta array di stringhe illimitati che possono essere utilizzati in modo simile a listVars. |
| eVar di merchandising | Supporto completo tramite [dimensioni di binding e metriche di binding](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=it#binding-dimension) |
| Metriche | Supporto completo; Customer Journey Analytics utilizza Experience Data Model (XDM), supporta metriche illimitate e non è legato agli eventi di successo personalizzati di Adobe Analytics. Alcune metriche standard sono state rinominate da Adobe Analytics: Visitatori = Persone, Visite = Sessioni, Hit = Eventi. |
| Spostare progetti, filtri e metriche calcolate da Adobe Analytics a Customer Journey Analytics | Supporto completo. |
| Dashboard/scorecard per dispositivi mobili | Supporto completo |
| Pannelli | Supporto completo per i seguent pannelli: pannello vuoto, pannello di attribuzione, pannello a forma libera, Quick Insights ed elemento Successivo o Precedente. |
| Esportazione PDF | Supporto completo. |
| Cura dei progetti | Supporto completo. |
| Collegamento del progetto | Supporto completo. |
| Elaborazione dei tempi di reporting | Supporto completo; Customer Journey Analytics si basa esclusivamente sull’elaborazione dei tempi di reporting. |
| Accesso API di reporting | Supporto completo; disponibile tramite l’[API Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/). |
| Rapporti/progetti pianificati | Supporto completo. |
| Segmenti | Supporto completo. Ora denominati “Filtri”: tieni presente che eventuali segmenti esistenti nella versione tradizionale di Analysis Workspace non vengono caricati in Customer Journey Analytics. |
| Suite di rapporti virtuali | Supporto completo. Ora questa funzione è denominata [Visualizzazioni dati](/help/data-views/create-dataview.md). |
| Cura dei componenti della suite di rapporti virtuali | Supporto completo. Ora fa parte di Visualizzazioni dati. |
| Dimensioni di dispositivo, referrer, browser e tecnologia | Supportato per i set di dati basati sul [connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it) e per i set di dati generati da WebSDK. Consulta la [documentazione su quali variabili Analytics sono supportate tramite ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=it). Se utilizzi la raccolta dati di Experience Platform Web SDK, il dispositivo e le dimensioni basati sulla ricerca del dispositivo non sono attualmente supportati. Il supporto è pianificato per il futuro. Per aggiungere ricerche per dispositivi e browser allo stream di dati Web SDK, fai riferimento a [questa documentazione](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it) |
| Analisi di dati multimediali in streaming | I dati multimediali sono disponibili tramite il connettore di origine di Analytics come parte del pannello Visualizzatori simultanei di contenuti multimediali e del pannello Tempo di riproduzione multimediale utilizzato in Workspace. |

{style="table-layout:auto"}

## Supportato in una nuova modalità {#new-support}

| Funzione | Note |
| --- | --- |
| Analytics for Target (A4T) | Il [integrazione tra Adobe Customer Journey Analytics e Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja/target-reporting-in-cja) fornisce potenti strumenti di analisi per il programma di ottimizzazione, che consentono di risparmiare tempo prezioso. |
| Pubblicazione dei tipi di pubblico | Supportata se concessa in licenza con i prodotti Customer Data Platform o Journey Optimizer di Adobe. La [pubblicazione di tipi di pubblico](/help/components/audiences/audiences-overview.md) invia tipi di pubblico a Real-time Customer Profile in Experience Platform. |
| Classificazioni | Ora denominati “Set di dati di ricerca”. Le classificazioni utilizzate in Analytics possono essere importate in Experience Platform e in Customer Journey Analytics tramite il connettore di origine delle classificazioni di Analytics. I set di dati di ricerca possono anche essere caricati direttamente in Experience Platform e resi disponibili in Customer Journey Analytics. |
| Generatore regole di classificazione | Supportato utilizzando le [sottostringhe](/help/data-views/component-settings/substring.md) in Customer Journey Analytics. Invece dei set di dati di ricerca, vengono utilizzate manipolazioni delle stringhe al momento della generazione del rapporto. |
| Lunghezza della sessione personalizzata | La lunghezza della sessione può essere configurata tramite le [Impostazioni sessione](../../data-views/create-dataview.md#session-settings) in una Visualizzazione dati. Per ulteriori informazioni, consulta le [Impostazioni sessione](../../data-views/session-settings.md). <br/>La gestione degli eventi in background per dispositivi mobili è supportata tramite Adobe Experience Platform Mobile SDK. Consulta [Ciclo di vita della rete Edge](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) per ulteriori informazioni. |
| Conversione valuta | Supportata come parte della [formattazione di un componente metrico](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=it#currency) in una visualizzazione dati. |
| Persistenza della variabile merchandising | Supporto completo tramite [dimensioni di binding e metriche di binding](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=it#binding-dimension) |
| Attributi cliente | Ora chiamati “Set di dati profilo”, non vengono importati automaticamente da Experience Cloud, ma devono essere caricati in Experience Platform prima di poter essere disponibili in Customer Journey Analytics. |
| Feed di dati | L’esportazione dei set di dati di prima generazione è disponibile tramite l’[API di accesso ai dati di Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=it) e attraverso le [destinazioni di Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=it). Queste opzioni forniscono l’esportazione a livello di evento/riga di tutti i dati raccolti o acquisiti nel data lake di Experience Platform. Le colonne dei dati di post-elaborazione non sono disponibili perché le colonne post vengono calcolate in fase di query. L’esportazione delle colonne post è disponibile tramite il reporting. |
| Reporting di Data Warehouse | L’[Esportazione tabella completa di Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) è l’evoluzione dei rapporti Data Warehouse in Adobe Analytics, con molte nuove funzioni, spesso richieste, che oggi non sono disponibili in Data Warehouse. |
| Dimensioni e metriche per entrata, uscita e tempo trascorso | Supportate (le entrate e le uscite sono ora denominate Inizio sessione e Fine sessione) e calcolate in modo leggermente diverso. |
| Impostazioni di persistenza eVar | Le eVar non fanno più parte di Customer Journey Analytics. Tuttavia, le impostazioni di persistenza ora fanno parte di Visualizzazioni dati e sono disponibili per tutte le dimensioni. La persistenza si basa sull’elaborazione dell’ora rapporto, non sull’elaborazione della raccolta dati. Le dimensioni impostate nelle visualizzazioni dati sono limitate a una persistenza massima di 90 giorni e non supportano la persistenza illimitata. |
| Dimensioni Geosegmentazione | [Supporto completo](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it) |
| Offuscamento IP | Per i clienti Customer Journey Analytics che utilizzano il connettore di origine di Analytics per compilare i dati da Adobe Analytics in Customer Journey Analytics: le impostazioni di offuscamento dell’IP applicate in Adobe Analytics fluiscono nei dati di Customer Journey Analytics. Puoi controllare queste impostazioni in Adobe Analytics in base alle esigenze.<p>In questo modo i clienti di Customer Journey Analytics che utilizzano Experience Platform Web SDK possono compilare direttamente i dati in Platform e Customer Journey Analytics. Puoi utilizzare la preparazione dati per la raccolta dati in Platform per configurare regole che offuscano l’indirizzo IP in base ai requisiti della tua azienda. |
| Canali di marketing | Utilizzando il connettore di origine di Analytics, i dati dei canali di marketing fluiscono in Customer Journey Analytics attraverso tale connettore. Le regole del canale di marketing vengono configurate nella versione tradizionale di Adobe Analytics e alcune regole non sono supportate. Per ulteriori informazioni, consulta [Canali marketing in Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html?lang=it). <br/>Per le implementazioni di Web SDK, le regole di elaborazione del canale di marketing al momento dell’elaborazione del report sono supportate tramite i [Campi derivati](../../data-views/derived-fields/derived-fields.md). |
| Deduplica delle metriche | Ora è configurato per le metriche all’interno di Visualizzazioni dati. La deduplica delle metriche avviene a livello di persona o di sessione anziché a livello di set di dati, visualizzazione dati o connessione. |
| Rapporti sulla sessione nuovi e ripetuti | Precedentemente ottenuti utilizzando la dimensione Numero di visite. Sono supportate le sessioni nuove a dispetto di quelle ripetute [con un intervallo di lookback di 13 mesi](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=it). |
| Regole di elaborazione, regole VISTA, regole di elaborazione del canale di marketing | Supportate utilizzando la funzionalità Preparazione dati di Adobe Experience Platform e i [campi derivati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html?lang=it) per i set di dati basati su Web SDK e per i dati provenienti dal connettore di origine di Analytics. |
| Variabile dei prodotti | In Experience Platform, per soddisfare questo caso d’uso, gli utenti possono utilizzare una matrice di oggetti all’interno di uno schema di set di dati. In Customer Journey Analytics gli utenti possono utilizzare un qualsiasi numero di variabili di prodotto, senza essere vincolati a una singola variabile come accade invece in Adobe Analytics. |
| Condivisione dei progetti | La condivisione dei progetti è supportata solo tra gli utenti di Customer Journey Analytics, non esiste tra Customer Journey Analytics e la versione tradizionale di Analysis Workspace. |
| Report Builder | Supportato con un nuovo plug-in di Office 365 per Excel. |
| Autorizzazioni utente/Controlli dell’accesso ai dati | Customer Journey Analytics distingue tra amministratori di prodotto, amministratori di prodotto di [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=it) e amministratori e utenti dei profili di prodotto. Solo gli amministratori di prodotto possono creare/aggiornare/eliminare connessioni, progetti, filtri o metriche calcolate create da altri utenti, mentre gli amministratori di prodotto e gli amministratori dei profili di prodotto possono modificare le visualizzazioni dati. Sono disponibili autorizzazioni aggiuntive per gli utenti, ad esempio per creare metriche calcolate, filtri o annotazioni. |
| Visualizzazioni | Sono supportate tutte le visualizzazioni Workspace, tranne la visualizzazione Mappa. |
| Unione cross-device/cross-channel | Supportata per i set di dati direttamente contenenti informazioni di identità (nota anche come unione “basata su campi”). L’unione basata sui grafici non è ancora supportata, ma lo sarà presto. Consulta [Unione](../../stitching/overview.md). |

{style="table-layout:auto"}

## Supporto parziale {#partial}

| Funzione | Note |
| --- | --- |
| Pannelli | Il pannello vuoto, il pannello di attribuzione, il pannello a forma libera e Quick Insights sono completamente supportati. I pannelli confronto segmenti e Analytics for Target (A4T) non sono supportati. |

{style="table-layout:auto"}

## Nessun supporto, ma è pianificato {#planned}

| Funzione | Note |
| --- | --- |
| Avvisi | Il supporto è pianificato. |
| Analisi dei contributi | Il supporto è pianificato. |
| Unione ID tramite grafo di dispositivi | Il supporto è pianificato. |
| Modelli di progetto | Il supporto è pianificato. |
| Reporting in tempo reale | Il supporto è pianificato. |
| Segmento IQ | Il supporto è pianificato. |
| Origini dati ID transazione | Il supporto è pianificato. |
| Origini dati a livello di riepilogo | Il supporto è pianificato. |

{style="table-layout:auto"}

## Nessun supporto, non ancora pianificato {#not-planned}

| Funzione | Note |
| --- | --- |
| Activity Map | Il supporto non è ancora pianificato. |
| Advertising Cloud | Il supporto non è ancora pianificato. |

{style="table-layout:auto"}

## Funzioni che non saranno mai supportate {#never}

* Metrica Persone con Cross-Device Coop

## Funzioni di Adobe Customer Journey Analytics non disponibili in Adobe Analytics {#cja-not-aa}

Nella tabella seguente sono elencate le funzioni disponibili in Customer Journey Analytics che non sono supportate in Adobe Analytics.

| Funzione | Maggiori dettagli |
| --- | --- |
| Possibilità di combinare set di dati (come suite di rapporti di Adobe Analytics) | Customer Journey Analytics consente di combinare dati provenienti da più suite di rapporti come se si trattasse di una singola suite di rapporti in Adobe Analytics. |
| Sistemazione per qualsiasi tipo di dati | Customer Journey Analytics è combinato con la capacità di Experience Platform di contenere tutti i tipi e schemi di dati. Utilizzando [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) i dati possono essere rappresentati e organizzati in modo uniforme e sono pronti per essere combinati ed esaminati. Adobe Analytics si concentra principalmente sui dati di analisi del web e dei dispositivi mobili con alcune funzionalità per [importare i dati](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=it). |
| Cross-Device Analytics | Customer Journey Analytics supporta la combinazione perfetta di set di dati specifici per dispositivo, provenienti da sessioni non autenticate e autenticate. Customer Journey Analytics consente di eseguire la retrocompilazione dei dati storici su dispositivi noti. In Analytics, questa funzionalità è limitata a una singola suite di rapporti e all’utilizzo di un grafo dei dispositivi. |
| Miglioramenti della dimensione | Customer Journey Analytics offre una grande flessibilità nell’utilizzo delle dimensioni: <ul><li>**Dimensioni personalizzate basate su numeri**:[offre la possibilità di creare dimensioni personali a bse numerica all’interno di una vista dati](/help/data-views/create-dataview.md#components).</li><li>**Ordinamento dimensioni basate su stringhe**: [ordina in modo alfabetico le dimensioni in una tabella a forma libera.](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>In Adobe Analytics erano disponibili sono alcune dimensioni numeriche preimpostate e l’ordinamento delle dimensioni basate su stringhe non era possibile.</p> |
| Campi derivati | I campi derivati consentono trasformazioni al momento dell’elaborazione del report. I dati possono essere combinati, corretti o creati immediatamente e si applicano retroattivamente a tutto il reporting. |
| Opzioni di sicurezza e privacy migliorate: ambito dell’HIPAA | Customer Journey Analytics conforme all’HIPAA e offre opzioni di sicurezza aggiuntive per la conformità alle normative. Adobe Analytics non è conforme all’HIPAA. |
| Analisi della sperimentazione | Customer Journey Analytics può valutare l’incremento e l’affidabilità di qualsiasi esperimento da qualsiasi origine dati definita come parte di una connessione. Questa valutazione consente di comprendere le relazioni causa-effetto tra le interazioni dei clienti che si estendono su qualsiasi canale. Analytics è limitato all’analisi di sperimentazione tramite A4T. |
| Previsione | La previsione è una funzionalità AI/ML che include una previsione statistica per i dati relativi alla serie temporale basata sui dati storici già esistenti in Customer Journey Analytics. Le previsioni possono essere visualizzate in tabelle a forma libera e in visualizzazioni con grafico a linee. |
| Analisi guidata | L’analisi guidata è un formato di reporting che consente agli utenti di soddisfare rapidamente le proprie esigenze di dati in modo da ottenere rapidamente informazioni di elevata qualità e prendere decisioni maggiormente basate sui dati. L’analisi guidata fa parte di Adobe Product Analytics, un componente aggiuntivo di Customer Journey Analytics. |
| Didascalie intelligenti | Le didascalie intelligenti utilizzano l’apprendimento automatico avanzato e l’intelligenza artificiale generativa per fornire informazioni approfondite relative al linguaggio naturale per le visualizzazioni di Workspace. La versione iniziale fornisce informazioni approfondite generate automaticamente per la visualizzazione [Linee](/help/analysis-workspace/visualizations/line.md). |
| Trasformazioni al momento del rapporto | Le visualizzazioni dati in Customer Journey Analytics consentono di interpretare ulteriormente i dati da una connessione. Puoi modificare o rimuovere dati senza modificare l’implementazione, utilizzare sottostringhe per manipolare le dimensioni, creare metriche da qualsiasi valore o filtrare gli eventi secondari. Tutte queste trasformazioni sono effettuate in modo non distruttivo. Adobe Analytics offre funzionalità limitate tramite suite di rapporti virtuali e una lunghezza della sessione personalizzata. |
| Estensione BI | L’estensione BI consente di collegare direttamente CJA ai più diffusi strumenti di visualizzazione di BI, come PowerBI o Tableau, per far corrispondere i rapporti di BI con precisione a quelli visualizzati in Analysis Workspace e in altre interfacce di reporting di CJA. Questo è un modo molto più semplice per ottenere rapporti BI per CJA senza la necessità di ricreare rapporti/metriche dai dati non elaborati. |
| Accesso SQL | Utilizzando l’opzione Data Distiller, Customer Journey Analytics può rimuovere le limitazioni dei dati raccolti durante l’elaborazione backend di Adobe. Puoi modificare i dati con SQL, creare valori e set di dati specifici per la tua azienda e continuare ad approfondire. Analytics non supporta alcun tipo di accesso SQL ai propri dati. |
| Dimensioni e metriche illimitate per la clientela | In Customer Journey Analytics le dimensioni sono illimitate; i valori possono essere numeri, testo, oggetti, elenchi o una combinazioni di questi. Le dimensioni possono essere nidificate o gerarchiche. <p>Al contrario, Analytics supporta fino a un massimo di 75 proprietà e 250 eVar.</p> |
| Valori univoci illimitati | Customer Journey Analytics supporta valori univoci illimitati o elementi dimensionali che possono essere inseriti in un rapporto all’interno di una singola dimensione.<p>Non ci sono [limiti di cardialità su una dimensione](/help/components/dimensions/high-cardinality.md) e quindi ogni valore univoco può comparire ed essere contato.</p><p>Questo approccio elimina le limitazioni di reportistica e analisi che si possono incontrare con implementazioni su larga scala di Adobe Analytics, risultando in etichette [!UICONTROL Low Traffic].</p><p>In Customer Journey Analytics è possibile vedere un’etichetta [!UICONTROL Uniques Exceeded], ma questo accade molto meno di frequente e può essere limitato applicando filtri o segmenti ai dati.</p> |

{style="table-layout:auto"}
