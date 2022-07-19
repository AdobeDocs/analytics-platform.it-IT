---
title: Supporto delle funzioni di Customer Journey Analytics
description: Confronto tra le funzioni di Customer Journey Analytics e quelle di Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 9d928a68e9b2eb16ba14cd793857547432ba11b0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
| Generatore regole di classificazione | Supporto completo. In CJA, [sottostringhe](/help/data-views/component-settings/substring.md). Invece dei set di dati di ricerca, vengono utilizzate manipolazioni delle stringhe al momento della generazione del rapporto. |
| Stitching cross-device/cross-channel | Supporto completo; consulta [Cross-Channel Analytics](/help/connections/cca/overview.md). |
| Download di CSV | Supporto completo. |
| Calendari personalizzati | Supporto completo. |
| Confronto date | Supporto completo. |
| Intervalli di date | È supportata tutta la funzionalità per intervalli di date. |
| Ora legale | Supporto completo. |
| Dimensioni di dispositivo, referrer, browser e tecnologia | Queste dimensioni vengono incluse automaticamente quando un set di dati AEP include campi di schema XDM specifici e sono conformi alla classe XDM Experience Event. Fai riferimento alla nostra [documentazione relativa alle variabili Analytics che sono supportate tramite ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=it).<p>Se non utilizzi il connettore di origine di Adobe per compilare i dati da Adobe Analytics in CJA, ma utilizzi invece la raccolta dati di Experience Platform Web SDK, il dispositivo e le dimensioni basati sulla ricerca di dispositivo non sono attualmente supportate, ma lo saranno prossimamente. |
| Dimensioni | Supporto completo; CJA sfrutta XDM e supporta dimensioni illimitate. CJA non è legato alle proprietà o agli eVar personalizzati della versione tradizionale di Adobe Analytics. |
| Eliminazione RGPD | Supporto completo; tieni presente che le funzioni RGPD sono ora gestite in coordinamento con [!UICONTROL Adobe Experience Platform]. CJA eredita tutte le modifiche apportate da [!UICONTROL Experience Platform] ai set di dati sottostanti. |
| Variabili elenco/Prop elenco | Supporto completo; CJA sfrutta XDM e supporta array di stringhe illimitati che possono essere utilizzati in modo simile a listVars. |
| Persistenza della variabile merchandising | Supporto completo tramite [dimensioni di binding e metriche di binding](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=it#binding-dimension) |
| eVar di merchandising | Supporto completo tramite [dimensioni di binding e metriche di binding](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Metriche | Supporto completo; CJA sfrutta Experience Data Model (XDM), supporta metriche illimitate e non è legato agli eventi di successo personalizzati della versione tradizionale di Analytics. Alcune metriche standard sono state rinominate nella versione tradizionale di Analytics: Visitatori = Persone, Visite = Sessioni, Hit = Eventi. |
| Deduplicazione delle metriche | Supporto completo. |
| Dashboard/scorecard per dispositivi mobili | Supporto completo. |
| Pannelli | Il pannello vuoto, il pannello di attribuzione, il pannello a forma libera e Quick Insights sono completamente supportati. |
| Esportazione PDF | Supporto completo. |
| Conservazione del progetto | Supporto completo. |
| Collegamento del progetto | Supporto completo. |
| Report Builder (plugin di Excel) | Supporto completo. |
| Elaborazione dell’ora rapporto | Supporto completo; CJA si basa esclusivamente sull’elaborazione dell’ora rapporto. |
| Accesso API di reporting | Supporto completo; disponibile tramite l’[API CJA](https://www.adobe.io/cja-apis/docs/). |
| Report/progetti pianificati | Supporto completo. |
| Segmenti | Supporto completo; ora denominati “Filtri”: eventuali segmenti esistenti nella versione tradizionale di Analysis Workspace non verranno caricati in CJA. |
| Analisi multimediali | I dati multimediali saranno disponibili il 30 luglio 2022 come parte del pannello Visualizzatori simultanei di contenuti multimediali e del pannello Tempo di riproduzione multimediale trascorso in Workspace. |
| Autorizzazioni utente/Controlli per l’accesso ai dati | Supporto completo; CJA distingue tra utenti e amministratori del prodotto [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=it). Solo gli amministratori di prodotto possono <ul><li>Creare/aggiornare/eliminare connessioni o visualizzazioni dati</li><li>Aggiornare o eliminare progetti, filtri o metriche di calcolo creati da altri utenti</li><li>Condividere un progetto Workspace con tutti gli utenti.</li></ul> |
| Suite di rapporti virtuali | Supporto completo; ora denominata [Visualizzazioni dati](/help/data-views/create-dataview.md). |
| Conservazione dei componenti VRS | Supporto completo; ora fa parte di Visualizzazioni dati. |

{style=&quot;table-layout:auto&quot;}

## Supportato con avvertenze

| Funzione | Note |
| --- | --- |
| A4T | Il supporto viene fornito tramite i campi nel [connettore origine Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). |
| Classificazioni | Ora denominati “Set di dati di ricerca”. Le classificazioni utilizzate in Analytics possono essere importate in Experience Platform e in CJA tramite il connettore di origine delle classificazioni di Analytics. I set di dati di ricerca possono anche essere caricati direttamente in AEP e resi disponibili in CJA. |
| Sessionizzazione personalizzata | Supporto per tutte le funzionalità di sessionizzazione personalizzata a esclusione degli hit di background per dispositivi mobili. |
| Attributi cliente | Ora detti “Set di dati profilo”, non vengono importati automaticamente da Experience Cloud, ma dovranno essere caricati in AEP prima di poter essere disponibili in CJA. |
| Dimensioni [!UICONTROL Device], [!UICONTROL Browser], [!UICONTROL Referrer], [!UICONTROL Technology] | Queste dimensioni vengono incluse automaticamente quando un set di dati AEP include campi di schema XDM specifici e sono conformi alla classe XDM Experience Event. Consulta la [documentazione relativa alle variabili Analytics supportate tramite il connettore di origine Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=it). Per i clienti CJA che non utilizzano il connettore di origine per compilare i dati da Adobe Analytics in CJA, ma che utilizzano invece la raccolta dati di AEP Web SDK, [!UICONTROL Device] e dimensioni basate sulla ricerca Dispositivo non sono attualmente supportate, ma lo saranno prossimamente. |
| Dimensioni e metriche per entrata, uscita e tempo trascorso | Supportate (le entrate e le uscite sono ora denominate Inizio sessione e Fine sessione) e calcolate in modo leggermente diverso. |
| Impostazioni di persistenza eVar | Le eVar non fanno più parte di CJA. Tuttavia, le impostazioni di persistenza ora fanno parte di Visualizzazioni dati e sono disponibili per tutte le dimensioni. La persistenza si basa sull’elaborazione dell’ora rapporto, non sull’elaborazione della raccolta dati. Le dimensioni impostate nelle visualizzazioni dati sono limitate a una persistenza massima di 90 giorni e non supportano la persistenza illimitata. |
| Dimensioni GeoSegmentation | Tutti i dati di GeoSegmentation o posizione geografica raccolti in Adobe Analytics fluiscono in CJA tramite il [connettore di origine Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Le implementazioni che non utilizzano il connettore di origine di Analytics, come quelle che si basano su AEP Web SDK per la raccolta di dati digitali, non dispongono della serie completa di funzioni per la ricerca automatica basata su dati geografici: sono supportati i dati di paese e provincia, ma non quelli di città e codice postale. |
| Canali marketing | I dati dei canali di marketing fluiscono in CJA tramite il connettore di origine di Analytics. Le regole del canale di marketing devono ancora essere configurate nella versione tradizionale di Adobe Analytics. Alcune regole non sono supportate. Per ulteriori informazioni, consulta la [documentazione sui canali di marketing CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=it#cja-usecases). |
| Rapporti sulla sessione nuovi e ripetuti | Supportato il 17 agosto 2022, [con un intervallo di lookback di 13 mesi](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat). |
| Variabile di prodotto | In Experience Platform, per soddisfare questo caso d’uso è possibile utilizzare una matrice di campi di tipo Oggetto all’interno di uno schema di set di dati. In CJA, è possibile utilizzare un qualsiasi numero di variabili di prodotto, senza essere vincolati a una singola variabile come accade invece in Adobe Analytics. |
| Condivisione dei progetti | La condivisione dei progetti è supportata solo tra gli utenti di CJA, non esiste tra CJA e la versione tradizionale di Analysis Workspace. |
| Visualizzazioni | Sono supportate tutte le visualizzazioni, tranne la visualizzazione Mappa. |

{style=&quot;table-layout:auto&quot;}

## Supporto parziale

| Funzione | Note |
| --- | --- |
| Filtro bot | Per i set di dati basati sul [Connettore sorgente Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html), viene applicato il filtro bot. La logica generale di filtro bot per altri set di dati non viene eseguita da [!UICONTROL Experience Platform] o da CJA. |
| Pannelli | Il pannello vuoto, il pannello di attribuzione, il pannello a forma libera e Quick Insights sono completamente supportati. I pannelli confronto segmenti e Analytics for Target (A4T) non sono supportati. |
| Regole di elaborazione | Per i set di dati basati sul connettore di origine di Analytics, le regole di elaborazione vengono ancora applicate. [Le funzionalità di preparazione dei dati in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) possono essere utilizzate anche al posto delle regole di elaborazione per i dati che vanno direttamente in Platform. |

{style=&quot;table-layout:auto&quot;}

## Funzioni al momento non supportate, ma pianificate

| Funzione | Note |
| --- | --- |
| Avvisi | Il supporto è pianificato. |
| Analisi contributi | Il supporto è pianificato. |
| Generazione rapporti su Data Warehouse (esportazione riga al 100%) | Il supporto di questa funzione è pianificato per l’interfaccia di Analysis Workspace. Anche Adobe Experience Platform [[!UICONTROL Query Service]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=it) fornisce un’interfaccia per questi casi d’uso in CJA. |
| ID Stitching (Stitching ID) tramite Device Graph (Grafico dispositivo) | Il supporto è pianificato. |
| Reporting di incremento e affidabilità | Il supporto è pianificato. |
| Regole di elaborazione, regole VISTA, regole di elaborazione dei canali di marketing | Supporto pianificato, ma funziona in fase di query anziché durante la raccolta dei dati per manipolazioni dei dati più flessibili e retroattive e non distruttive. |
| Modelli di progetto | Il supporto è pianificato. |
| Reporting in tempo reale | Il supporto è pianificato. |
| Segmento IQ | Il supporto è pianificato. |

{style=&quot;table-layout:auto&quot;}

## Supporto non ancora pianificato.

| Funzione | Note |
| --- | --- |
| Activity Map | Il supporto non è ancora pianificato. |
| Advertising Cloud | Il supporto non è ancora pianificato. |
| Conversione valuta | Il supporto non è ancora pianificato. |
| Feed dati | Il supporto non è ancora pianificato. |
| Riepilogo origini dati | Il supporto non è ancora pianificato. |
| Origini dati ID transazione | Il supporto non è ancora pianificato. |

{style=&quot;table-layout:auto&quot;}

## Funzioni che non saranno mai supportate

* Metrica Persone con Cross-Device Coop
* Dashboard di Reports &amp; Analytics
* Segnalibri di Reports &amp; Analytics
* Target di Reports &amp; Analytics
* Mobile Services
