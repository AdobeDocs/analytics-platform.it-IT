---
title: Supporto delle funzioni di Customer Journey Analytics
description: Confronto tra le funzioni di Customer Journey Analytics e quelle di Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 264b5a3d3793ab6531f570d83cbd4fd96bfbd67a
workflow-type: tm+mt
source-wordcount: '2080'
ht-degree: 36%

---

# Supporto delle funzioni di Adobe Customer Journey Analytics

Le tabelle seguenti elencano le funzioni di Adobe Analytics supportate, parzialmente supportate o non supportate in Customer Journey Analytics e le funzioni di Customer Journey Analytics non supportate o disponibili in Adobe Analytics. Questi elenchi cambieranno nel tempo man mano che le funzioni vengono aggiunte al Customer Journey Analytics.

## Funzionalità/componenti completamente supportati {#full-support}

| Funzionalità di Adobe Analytics | Note sul supporto |
| --- | --- |
| Rilevamento delle anomalie | Supporto completo. |
| Attribution IQ | Supporto completo. |
| Metriche calcolate | Supporto completo. Eventuali metriche calcolate esistenti nell’Analysis Workspace tradizionale non vengono trasferite al Customer Journey Analytics. |
| Eventi calendario | Supporto completo. Gli eventi Calendario sono stati implementati come [Annotazioni](/help/components/annotations/overview.md) in Workspace. |
| Download di CSV | Supporto completo. |
| Calendari personalizzati | Supporto completo. |
| Confronto date | Supporto completo. |
| Intervalli di date | È supportata tutta la funzionalità per intervalli di date. |
| Dimensioni | Supporto completo. Il Customer Journey Analytics utilizza XDM e supporta dimensioni illimitate. Il Customer Journey Analytics non è legato alle proprietà o agli eVar personalizzati della versione tradizionale di Adobe Analytics. |
| Eliminazione RGPD | Supporto completo; tieni presente che le funzioni RGPD sono ora gestite in coordinamento con [!UICONTROL Adobe Experience Platform]. Il Customer Journey Analytics eredita qualsiasi modifica ai dati [!UICONTROL Experience Platform] crea nei set di dati sottostanti. |
| Reporting di incremento e affidabilità | Supporto completo tramite [Pannello Sperimentazione](/help/analysis-workspace/c-panels/experimentation.md) |
| Variabili elenco/Prop elenco | Supporto completo. Il Customer Journey Analytics utilizza XDM e supporta array di stringhe illimitati che possono essere utilizzati in modo simile a listVars. |
| eVar di merchandising | Supporto completo tramite [dimensioni di binding e metriche di binding](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=it#binding-dimension) |
| Metriche | Supporto completo; il Customer Journey Analytics utilizza Experience Data Model (XDM), supporta metriche illimitate e non è legato agli eventi di successo personalizzati di Adobe Analytics. Alcune metriche standard sono state rinominate da Adobe Analytics: Visitatori = Persone, Visite = Sessioni, Hit = Eventi. |
| Dashboard/scorecard per dispositivi mobili | Supporto completo. |
| Pannelli | Il pannello vuoto, il pannello di attribuzione, il pannello a forma libera e Quick Insights sono completamente supportati. |
| Esportazione PDF | Supporto completo. |
| Conservazione del progetto | Supporto completo. |
| Collegamento del progetto | Supporto completo. |
| Elaborazione dell’ora rapporto | Supporto completo; il Customer Journey Analytics si basa esclusivamente sull’elaborazione dell’ora rapporto. |
| Accesso API di reporting | Supporto completo; disponibile tramite [API CUSTOMER JOURNEY ANALYTICS](https://developer.adobe.com/cja-apis/docs/). |
| Report/progetti pianificati | Supporto completo. |
| Segmenti | Supporto completo. Ora denominati &quot;Filtri&quot;: eventuali segmenti esistenti nella versione tradizionale di Analysis Workspace non vengono trasferiti al Customer Journey Analytics. |
| Suite di rapporti virtuali | Supporto completo. Ora chiamato [Visualizzazioni dati](/help/data-views/create-dataview.md). |
| Cura dei componenti delle suite di rapporti virtuali | Supporto completo. Ora fa parte di Visualizzazioni dati. |
| Analisi di dati multimediali in streaming | I dati multimediali sono disponibili utilizzando il connettore di origine di Analytics come parte del pannello Visualizzatori simultanei di contenuti multimediali e del pannello Tempo trascorso su contenuti multimediali in Workspace. |

{style="table-layout:auto"}

## Supportato in una nuova modalità {#new-support}

| Funzione | Note |
| --- | --- |
| Pubblicazione dei tipi di pubblico (Pubblicazione dei segmenti) | Supportata se concessa in licenza con i prodotti Customer Data Platform o Journey Optimizer di Adobe. La [pubblicazione di tipi di pubblico](/help/components/audiences/audiences-overview.md) invia tipi di pubblico a Real-time Customer Profile in Experience Platform. |
| Classificazioni | Ora denominati “Set di dati di ricerca”. Le classificazioni utilizzate in Analytics possono essere importate nell’Experience Platform e nel Customer Journey Analytics utilizzando il connettore di origine delle classificazioni di Analytics. I set di dati di ricerca possono anche essere caricati direttamente in Experienci Platform e resi disponibili nel Customer Journey Analytics. |
| Generatore regole di classificazione | Supportato tramite [sottostringhe](/help/data-views/component-settings/substring.md) nel Customer Journey Analytics. Invece dei set di dati di ricerca, vengono utilizzate manipolazioni delle stringhe al momento della generazione del rapporto. |
| Sessionizzazione personalizzata | La sessionizzazione personalizzata può essere configurata tramite [Impostazioni sessione](../../data-views/create-dataview.md#session-settings) in una visualizzazione dati. Consulta  [Sessioni in base al contesto](../../data-views/context-aware-sessions.md) per ulteriori informazioni. <br/>La gestione degli eventi in background per dispositivi mobili è supportata tramite l’SDK di Adobe Experience Platform Mobile. Consulta [Ciclo di vita per Edge Network](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) per ulteriori informazioni. |
| Conversione valuta | Supportato come parte di [formattazione di un componente metrica](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=en#currency) in una visualizzazione dati. |
| Persistenza della variabile merchandising | Supporto completo tramite [dimensioni di binding e metriche di binding](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=it#binding-dimension) |
| Attributi cliente | Ora detti &quot;Set di dati profilo&quot;, non vengono importati automaticamente da Experience Cloud, ma devono essere caricati in Experienci Platform prima di poter essere disponibili in Customer Journey Analytics. |
| Feed dati | L’esportazione dei set di dati di prima generazione è disponibile tramite [API di accesso ai dati Experienci Platform](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) e attraverso [Destinazioni Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en). Queste opzioni forniscono l’esportazione a livello di evento/riga di tutti i dati raccolti o acquisiti in Experienci Platform Data Lake. Le colonne di dati post-elaborazione non sono disponibili perché le colonne post vengono calcolate in fase di query. L’esportazione delle colonne Post è disponibile tramite il reporting. |
| Deduplica delle metriche | Ora è configurato per le metriche all’interno di Visualizzazioni dati. La deduplica delle metriche avviene a livello di persona o di sessione anziché a livello di set di dati, visualizzazione dati o connessione. |
| Dimensioni e metriche per entrata, uscita e tempo trascorso | Supportate (le entrate e le uscite sono ora denominate Inizio sessione e Fine sessione) e calcolate in modo leggermente diverso. |
| Impostazioni di persistenza eVar | Le eVar non fanno più parte del Customer Journey Analytics. Tuttavia, le impostazioni di persistenza ora fanno parte di Visualizzazioni dati e sono disponibili per tutte le dimensioni. La persistenza si basa sull’elaborazione dell’ora rapporto, non sull’elaborazione della raccolta dati. I Dimension impostati nelle Visualizzazioni dati sono limitati a una persistenza massima di 90 giorni e non supportano la persistenza illimitata. |
| Offuscamento IP | Per i clienti del Customer Journey Analytics che utilizzano il connettore di origine di Analytics per compilare i dati da Adobe Analytics nel Customer Journey Analytics: le impostazioni di offuscamento dell’IP applicate in Adobe Analytics scorrono nei dati del Customer Journey Analytics. Puoi controllare queste impostazioni in Adobe Analytics in base alle esigenze.<p>Per i clienti del Customer Journey Analytics che utilizzano Experienci Platform Web SDK per compilare direttamente i dati in Platform e Customer Journey Analytics. Puoi utilizzare la preparazione dati per la raccolta dati in Platform per configurare regole che offuschino l’indirizzo IP in base ai requisiti della tua azienda. |
| Rapporti sulla sessione nuovi e ripetuti | Precedentemente ottenuti utilizzando la dimensione Numero di visite. Sono supportate le sessioni nuove a dispetto di quelle ripetute [con un intervallo di lookback di 13 mesi](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=it). |
| Variabile di prodotto | In Experience Platform, per soddisfare questo caso d’uso è possibile utilizzare una matrice di campi di tipo Oggetto all’interno di uno schema di set di dati. All’interno di Customer Journey Analytics, i clienti possono utilizzare un qualsiasi numero di variabili di prodotto e non sono limitati a una singola variabile, come accade invece in Adobe Analytics. |
| Condivisione dei progetti | La condivisione dei progetti è supportata solo tra gli utenti del Customer Journey Analytics; non esiste condivisione dei progetti tra il Customer Journey Analytics e il tradizionale Analysis Workspace. |
| Visualizzazioni | Sono supportate tutte le visualizzazioni, tranne la visualizzazione Mappa. |
| Report Builder (plug-in di Excel) | Supportato con un nuovo plug-in di Office 365 per Excel. |
| Autorizzazioni utente/Controlli per l’accesso ai dati | Il Customer Journey Analytics distingue tra [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=it) amministratori di prodotto, amministratori dei profili di prodotto e utenti. Solo gli amministratori di prodotto possono creare/aggiornare/eliminare connessioni, progetti, filtri o metriche calcolate create da altri utenti, mentre gli amministratori di prodotto e gli amministratori dei profili di prodotto possono modificare le visualizzazioni dati. Sono disponibili autorizzazioni aggiuntive per gli utenti, ad esempio per creare metriche calcolate, filtri o annotazioni. |
| Regole di elaborazione, regole VISTA, regole di elaborazione dei canali di marketing | Supportato utilizzando la funzionalità Preparazione dati di Adobe Experience Platform per set di dati basati su Web SDK e per i dati provenienti dal connettore di origine di Analytics. |
| Canali marketing | Quando si utilizza il connettore di origine di Analytics, i dati dei canali di marketing fluiscono nel Customer Journey Analytics attraverso tale connettore. Le regole del canale di marketing sono configurate nella versione tradizionale di Adobe Analytics e alcune regole non sono supportate. Per ulteriori dettagli, consulta [Documentazione dei canali di marketing Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html). <br/>Per le implementazioni Web SDK, le regole di elaborazione dei canali di marketing al momento del reporting sono supportate tramite [Campi derivati](../../data-views/derived-fields/derived-fields.md). |

{style="table-layout:auto"}

## Supporto parziale {#partial}

| Funzione | Note |
| --- | --- |
| Unione cross-device/cross-channel | Supportata per i set di dati direttamente contenenti informazioni di identità (nota anche come unione “basata su campi”). L’unione basata sui grafici non è ancora supportata, ma lo sarà presto. Consulta [Stitching](../../stitching/overview.md). |
| Filtro bot | Per [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it)set di dati basati su, viene applicato il filtro bot. La logica generale di filtro bot per altri set di dati non viene eseguita da [!UICONTROL Experience Platform] o Customer Journey Analytics. |
| Dimensioni di dispositivo, referrer, browser e tecnologia | Supportato per [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it)Set di dati basati su. Fai riferimento a [documentazione sulle variabili Analytics supportate tramite ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=it).<p>Se utilizzi la raccolta dati di Experienci Platform Web SDK, il dispositivo e le dimensioni basati sulla ricerca del dispositivo non sono attualmente supportati. È pianificato il supporto futuro. |
| Dimensioni GeoSegmentation | Tutti i dati di GeoSegmentation o posizione geografica raccolti in Adobe Analytics fluiscono nel Customer Journey Analytics tramite [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). Le implementazioni che non utilizzano il connettore di origine di Analytics, ma si basano su Experienci Platform Web SDK per la raccolta di dati digitali, possono utilizzare [Servizio di ricerca geografica di Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en). |
| Pannelli | Il pannello vuoto, il pannello di attribuzione, il pannello a forma libera e Quick Insights sono completamente supportati. I pannelli confronto segmenti e Analytics for Target (A4T) non sono supportati. |
| Regole di elaborazione | Per i set di dati basati sul connettore di origine Analytics, le regole di elaborazione vengono ancora applicate. [Le funzionalità di preparazione dei dati in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) possono essere utilizzate anche al posto delle regole di elaborazione per i dati che vanno direttamente in Platform. |
| A4T | Il supporto parziale viene fornito tramite i campi nella sezione [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). È pianificato il supporto per nomi compatibili con A4T nelle esperienze e nelle attività di Target. |

{style="table-layout:auto"}

## Nessun supporto, ma pianificato {#planned}

| Funzione | Note |
| --- | --- |
| Avvisi | Il supporto è pianificato. |
| Analisi contributi | Il supporto è pianificato. |
| Reporting di Data Warehouse | Il supporto di questa funzione è pianificato per l’interfaccia di Analysis Workspace. Adobe Experience Platform [[!UICONTROL Query Service]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=it>) fornisce anche un’interfaccia per questi casi d’uso nel Customer Journey Analytics. |
| ID Stitching (Stitching ID) tramite Device Graph (Grafico dispositivo) | Il supporto è pianificato. |
| Modelli di progetto | Il supporto è pianificato. |
| Reporting in tempo reale | Il supporto è pianificato. |
| Segmento IQ | Il supporto è pianificato. |
| Origini dati ID transazione | Il supporto è pianificato. |
| Migrazione di progetti/filtri/metriche calcolate da Adobe Analytics al Customer Journey Analytics | Il supporto è pianificato. |
| Origini dati a livello di riepilogo | Il supporto è pianificato. |

{style="table-layout:auto"}

## Nessun supporto, non ancora pianificato {#not-planned}

| Funzione | Note |
| --- | --- |
| Activity Map | Il supporto non è ancora pianificato. |
| Advertising Cloud | Il supporto non è ancora pianificato. |

{style="table-layout:auto"}

## Mai supportato {#never}

* Metrica Persone con Cross-Device Coop
* Dashboard di Reports &amp; Analytics
* Segnalibri di Reports &amp; Analytics
* Target di Reports &amp; Analytics

## Funzioni di Adobe Customer Journey Analytics non disponibili in Adobe Analytics {#cja-not-aa}

Nella tabella seguente sono elencate le funzioni disponibili in Customer Journey Analytics, ma non supportate in Adobe Analytics.

| Funzione | Maggiori dettagli |
| --- | --- |
| Alloggio per qualsiasi tipo di dati | Customer Journey Analytics è combinato con la capacità di Experienci Platform di contenere tutti i tipi di schemi e tipi di dati. Utilizzo di [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it), i dati possono essere rappresentati e organizzati in modo uniforme, per poi essere combinati ed esplorati. Adobe Analytics si concentra principalmente sui dati di analisi web e mobile con alcune funzionalità per [importare dati](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=it). |
| Dimension e metriche cliente illimitati | Le dimensioni del Customer Journey Analytics sono illimitate; i valori possono essere numerici, testo, oggetti, elenchi o combinazioni di tutti. I Dimension possono essere nidificati o gerarchici. Analytics supporta fino a un massimo di 75 proprietà e 250 eVar. |
| Cardinalità/valori univoci illimitati | Il Customer Journey Analytics supporta valori univoci illimitati o elementi dimensionali che possono essere segnalati all’interno di una singola dimensione. Adobe Analytics è limitato a 500.000 valori univoci. L’illimitazione di valori o dimensioni univoci elimina le limitazioni di reporting e analisi attualmente esistenti con l’implementazione su larga scala di Analytics. |
| Trasformazioni ora rapporto | Le trasformazioni temporali dei rapporti (meglio note come visualizzazioni dati) nel Customer Journey Analytics consentono di interpretare ulteriormente i dati di una connessione. Puoi modificare o rimuovere i dati senza riimplementarli; utilizzare sottostringhe per manipolare le dimensioni; creare metriche da qualsiasi valore; filtrare i sottoeventi. E le trasformazioni sono tutte effettuate in modo non distruttivo. Adobe Analytics fornisce funzionalità limitate tramite suite di rapporti virtuali e sessionizzazione. |
| Analisi della sperimentazione | Il Customer Journey Analytics può valutare l’incremento e l’affidabilità di qualsiasi esperimento da qualsiasi origine dati definita come parte di una connessione. Questa valutazione consente di comprendere le relazioni causa-effetto tra le interazioni dei clienti che si estendono su qualsiasi canale. Analytics è limitato alla sperimentazione con Analytics tramite l’integrazione Analytics for Target (A4T). |
| Analytics tra dispositivi | Il Customer Journey Analytics supporta la combinazione perfetta di set di dati specifici per dispositivo provenienti da sessioni non autenticate e autenticate. Il Customer Journey Analytics offre di eseguire il backfill dei dati storici su dispositivi noti. In Analytics, questa funzionalità è limitata a una singola suite di rapporti e all’utilizzo di un grafico dei dispositivi. |
| Accesso SQL | Utilizzando l’opzione Data Distiller, il Customer Journey Analytics può rimuovere le limitazioni dei dati raccolti durante l’elaborazione backend di Adobe. Puoi modificare i dati con SQL, creare valori e set di dati specifici per la tua azienda e continuare a esplorare. Analytics non supporta alcun tipo di accesso SQL ai propri dati. |
| Opzioni di sicurezza e privacy migliorate: preparazione HIPAA | Il Customer Journey Analytics è pronto per HIPAA e offre opzioni di sicurezza aggiuntive per la conformità alle normative. Adobe Analytics non è pronto per HIPAA. |

{style="table-layout:auto"}
