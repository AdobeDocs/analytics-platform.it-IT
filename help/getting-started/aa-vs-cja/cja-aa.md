---
title: Supporto delle funzioni di Customer Journey Analytics
description: Confronto tra le funzioni di Customer Journey Analytics e quelle di Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: ca161bd86b4f926991c1adec2ccf3918f2bc4347
workflow-type: tm+mt
source-wordcount: '1586'
ht-degree: 94%

---

# Supporto delle funzioni di Customer Journey Analytics

Le tabelle seguenti elencano le funzionalità di Adobe Analytics supportate totalmente, parzialmente o non supportate da Customer Journey Analytics (CJA). Con l’incremento delle funzioni aggiunte a CJA, questi elenchi subiranno modifiche nel tempo.

## Funzionalità/componenti completamente supportati

| Funzionalità di Adobe Analytics | Note sul supporto |
| --- | --- |
| Rilevamento delle anomalie | Supporto completo. |
| Attribution IQ | Supporto completo. |
| Metriche calcolate | Supporto completo; eventuali metriche di calcolo esistenti nella versione tradizionale di Analysis Workspace non verranno trasferite a CJA. |
| Eventi calendario | Supporto completo. Gli eventi Calendario sono stati implementati come [Annotazioni](/help/components/annotations/overview.md) in Workspace. |
| Download di CSV | Supporto completo. |
| Calendari personalizzati | Supporto completo. |
| Confronto date | Supporto completo. |
| Intervalli di date | È supportata tutta la funzionalità per intervalli di date. |
| Dimensioni | Supporto completo; CJA sfrutta XDM e supporta dimensioni illimitate. CJA non è legato alle proprietà o agli eVar personalizzati della versione tradizionale di Adobe Analytics. |
| Eliminazione RGPD | Supporto completo; tieni presente che le funzioni RGPD sono ora gestite in coordinamento con [!UICONTROL Adobe Experience Platform]. CJA eredita tutte le modifiche apportate da [!UICONTROL Experience Platform] ai set di dati sottostanti. |
| Reporting di incremento e affidabilità | Supporto completo tramite [Pannello Sperimentazione](/help/analysis-workspace/c-panels/experimentation.md) |
| Variabili elenco/Prop elenco | Supporto completo; CJA sfrutta XDM e supporta array di stringhe illimitati che possono essere utilizzati in modo simile a listVars. |
| eVar di merchandising | Supporto completo tramite [dimensioni di binding e metriche di binding](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=it#binding-dimension) |
| Metriche | Supporto completo; CJA sfrutta Experience Data Model (XDM), supporta metriche illimitate e non è legato agli eventi di successo personalizzati della versione tradizionale di Analytics. Alcune metriche standard sono state rinominate nella versione tradizionale di Analytics: Visitatori = Persone, Visite = Sessioni, Hit = Eventi. |
| Dashboard/scorecard per dispositivi mobili | Supporto completo. |
| Pannelli | Il pannello vuoto, il pannello di attribuzione, il pannello a forma libera e Quick Insights sono completamente supportati. |
| Esportazione PDF | Supporto completo. |
| Conservazione del progetto | Supporto completo. |
| Collegamento del progetto | Supporto completo. |
| Elaborazione dell’ora rapporto | Supporto completo; CJA si basa esclusivamente sull’elaborazione dell’ora rapporto. |
| Accesso API di reporting | Supporto completo; disponibile tramite l’[API CJA](https://www.adobe.io/cja-apis/docs/). |
| Report/progetti pianificati | Supporto completo. |
| Segmenti | Supporto completo; ora denominati “Filtri”: eventuali segmenti esistenti nella versione tradizionale di Analysis Workspace non verranno caricati in CJA. |
| Suite di rapporti virtuali | Supporto completo; ora denominata [Visualizzazioni dati](/help/data-views/create-dataview.md). |
| Conservazione dei componenti VRS | Supporto completo; ora fa parte di Visualizzazioni dati. |
| Analisi di dati multimediali in streaming | I dati multimediali sono disponibili tramite il Connettore dati di Analytics come parte del pannello Visualizzatori simultanei di contenuti multimediali e del pannello Tempo di riproduzione multimediale utilizzato in Workspace. |

{style=&quot;table-layout:auto&quot;}

## Supportato in una nuova modalità

| Funzione | Note |
| --- | --- |
| Pubblicazione dei tipi di pubblico (Pubblicazione dei segmenti) | Supportata se concessa in licenza con i prodotti Customer Data Platform o Journey Optimizer di Adobe. La [pubblicazione di tipi di pubblico](/help/components/audiences/audiences-overview.md) invia tipi di pubblico a Real-time Customer Profile in Experience Platform. |
| Classificazioni | Ora denominati “Set di dati di ricerca”. Le classificazioni utilizzate in Analytics possono essere importate in Experience Platform e in CJA tramite il connettore di origine delle classificazioni di Analytics. I set di dati di ricerca possono anche essere caricati direttamente in AEP e resi disponibili in CJA. |
| Generatore regole di classificazione | Supportato utilizzando le [sottostringhe](/help/data-views/component-settings/substring.md) in CJA. Invece dei set di dati di ricerca, vengono utilizzate manipolazioni delle stringhe al momento della generazione del rapporto. |
| Sessionizzazione personalizzata | Supporto per tutte le funzionalità di sessionizzazione personalizzata a esclusione degli hit di background per dispositivi mobili. |
| Persistenza della variabile merchandising | Supporto completo tramite [dimensioni di binding e metriche di binding](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=it#binding-dimension) |
| Attributi cliente | Ora detti “Set di dati profilo”, non vengono importati automaticamente da Experience Cloud, ma dovranno essere caricati in AEP prima di poter essere disponibili in CJA. |
| Feed dati | L’esportazione di dati di prima generazione di set di dati è disponibile tramite [API di accesso ai dati AEP](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) e [Destinazioni AEP](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en). Queste opzioni forniscono l’esportazione a livello di hit/riga di tutti i dati raccolti o acquisiti in AEP Data Lake. Le colonne dei dati del processo di post non sono disponibili perché le colonne dei post sono calcolate in fase di query. L’esportazione di colonne di post è disponibile tramite reporting. |
| Deduplica delle metriche | Ora è configurato per le metriche all’interno di Visualizzazioni dati. La deduplica delle metriche avviene a livello di persona o di sessione anziché a livello di set di dati, visualizzazione dati o connessione. |
| Dimensioni e metriche per entrata, uscita e tempo trascorso | Supportate (le entrate e le uscite sono ora denominate Inizio sessione e Fine sessione) e calcolate in modo leggermente diverso. |
| Impostazioni di persistenza eVar | Le eVar non fanno più parte di CJA. Tuttavia, le impostazioni di persistenza ora fanno parte di Visualizzazioni dati e sono disponibili per tutte le dimensioni. La persistenza si basa sull’elaborazione dell’ora rapporto, non sull’elaborazione della raccolta dati. Le dimensioni impostate nelle visualizzazioni dati sono limitate a una persistenza massima di 90 giorni e non supportano la persistenza illimitata. |
| Offuscamento IP | Per i clienti CJA che utilizzano il connettore di origine di Analytics per compilare i dati da Adobe Analytics in CJA: le impostazioni di offuscamento dell’IP applicate in Adobe Analytics scorrono nei dati CJA. Puoi controllare queste impostazioni in Adobe Analytics in base alle esigenze.<p>Per i clienti CJA che utilizzano l’SDK per web di Adobe Experience Platform per compilare direttamente i dati in Platform e CJA: puoi utilizzare la preparazione dei dati per la raccolta in Platform per configurare regole che offuschino l’indirizzo IP in base ai requisiti della tua azienda. |
| Rapporti sulla sessione nuovi e ripetuti | Precedentemente ottenuti utilizzando la dimensione Numero di visite. Sono supportate le sessioni nuove a dispetto di quelle ripetute [con un intervallo di lookback di 13 mesi](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat). |
| Variabile di prodotto | In Experience Platform, per soddisfare questo caso d’uso è possibile utilizzare una matrice di campi di tipo Oggetto all’interno di uno schema di set di dati. In CJA, è possibile utilizzare un qualsiasi numero di variabili di prodotto, senza essere vincolati a una singola variabile come accade invece in Adobe Analytics. |
| Condivisione dei progetti | La condivisione dei progetti è supportata solo tra gli utenti di CJA, non esiste tra CJA e la versione tradizionale di Analysis Workspace. |
| Visualizzazioni | Sono supportate tutte le visualizzazioni, tranne la visualizzazione Mappa. |
| Report Builder (plug-in di Excel) | Supportato con un nuovo plug-in di Office 365 per Excel. |
| Autorizzazioni utente/Controlli per l’accesso ai dati | CJA distingue tra amministratori di prodotto, amministratori dei profili di prodotto e utenti di [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=it). Solo gli amministratori di prodotto possono creare/aggiornare/eliminare connessioni, progetti, filtri o metriche calcolate create da altri utenti, mentre gli amministratori di prodotto e gli amministratori dei profili di prodotto possono modificare le visualizzazioni dati. Sono disponibili autorizzazioni aggiuntive per gli utenti, ad esempio per creare metriche calcolate, filtri o annotazioni. |
| Regole di elaborazione, regole VISTA, regole di elaborazione dei canali di marketing | Supportate utilizzando la funzionalità Preparazione dati di Adobe Experience Platform per set di dati basati su Web SDK e per i dati provenienti dal Connettore dati di Analytics. |

{style=&quot;table-layout:auto&quot;}

## Supporto parziale

| Funzione | Note |
| --- | --- |
| Canali marketing | I dati dei canali di marketing fluiscono in CJA tramite il connettore di origine di Analytics. Le regole del canale di marketing devono ancora essere configurate nel Adobe Analytics tradizionale e alcune regole non sono supportate. Per ulteriori informazioni, consulta la [Documentazione dei canali di marketing CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=it#cja-usecases). Inoltre, per le implementazioni Web SDK, sono disponibili plug-in per la definizione dei canali di marketing lato client. È pianificato il supporto futuro per le regole di elaborazione dei canali di marketing al momento del rapporto. |
| Unione cross-device/cross-channel | Supportata per i set di dati direttamente contenenti informazioni di identità (nota anche come unione “basata su campi”). L’unione basata sui grafici non è ancora supportata, ma lo sarà presto. Consulta l’[Analisi cross-channel](/help/cca/overview.md). |
| Filtro bot | Per i set di dati basati sul [Connettore sorgente Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it), viene applicato il filtro bot. La logica generale di filtro bot per altri set di dati non viene eseguita da [!UICONTROL Experience Platform] o da CJA. |
| Dimensioni di dispositivo, referrer, browser e tecnologia | Supportato per i set di dati basati sul [Connettore di origine di Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). Fai riferimento alla nostra [documentazione relativa alle variabili Analytics che sono supportate tramite ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=it).<p>Se non utilizzi il connettore di origine di Adobe per compilare i dati da Adobe Analytics in CJA, ma utilizzi invece la raccolta dati di Experience Platform Web SDK, il dispositivo e le dimensioni basati sulla ricerca di dispositivo non sono attualmente supportate, È pianificato il supporto futuro. |
| Dimensioni GeoSegmentation | Tutti i dati di GeoSegmentation o posizione geografica raccolti in Adobe Analytics fluiscono in CJA tramite il [connettore di origine Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). Le implementazioni che non utilizzano il connettore di origine di Analytics, come quelle che si basano su AEP Web SDK per la raccolta di dati digitali, non dispongono della serie completa di funzioni per la ricerca automatica basata su dati geografici: sono supportati i dati di paese e provincia, ma non quelli di città e codice postale. |
| Pannelli | Il pannello vuoto, il pannello di attribuzione, il pannello a forma libera e Quick Insights sono completamente supportati. I pannelli confronto segmenti e Analytics for Target (A4T) non sono supportati. |
| Regole di elaborazione | Per i set di dati basati sul connettore di origine di Analytics, le regole di elaborazione vengono ancora applicate. [Le funzionalità di preparazione dei dati in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) possono essere utilizzate anche al posto delle regole di elaborazione per i dati che vanno direttamente in Platform. |
| A4T | Il supporto parziale viene fornito tramite i campi nel [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). È pianificato il supporto per nomi descrittivi A4T nelle attività e nelle esperienze di Target. |

{style=&quot;table-layout:auto&quot;}

## Funzioni al momento non supportate, ma pianificate

| Funzione | Note |
| --- | --- |
| Avvisi | Il supporto è pianificato. |
| Analisi contributi | Il supporto è pianificato. |
| Reporting di Data Warehouse | Il supporto di questa funzione è pianificato per l’interfaccia di Analysis Workspace. Anche Adobe Experience Platform [[!UICONTROL Query Service]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=it) fornisce un’interfaccia per questi casi d’uso in CJA. |
| ID Stitching (Stitching ID) tramite Device Graph (Grafico dispositivo) | Il supporto è pianificato. |
| Modelli di progetto | Il supporto è pianificato. |
| Reporting in tempo reale | Il supporto è pianificato. |
| Segmento IQ | Il supporto è pianificato. |
| Conversione valuta | Il supporto è pianificato. |
| Origini dati ID transazione | Il supporto è pianificato. |
| Migrazione di progetti/filtri/metriche calcolate da AA a CJA | Il supporto è pianificato. |
| Origini dati a livello di riepilogo | Il supporto è pianificato. |

{style=&quot;table-layout:auto&quot;}

## Supporto non ancora pianificato.

| Funzione | Note |
| --- | --- |
| Activity Map | Il supporto non è ancora pianificato. |
| Advertising Cloud | Il supporto non è ancora pianificato. |

{style=&quot;table-layout:auto&quot;}

## Funzioni che non saranno mai supportate

* Metrica Persone con Cross-Device Coop
* Dashboard di Reports &amp; Analytics
* Segnalibri di Reports &amp; Analytics
* Target di Reports &amp; Analytics
* Mobile Services
