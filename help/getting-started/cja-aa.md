---
title: Supporto delle funzioni di Customer Journey Analytics
description: Confronto tra le funzioni di Customer Journey Analytics e quelle di Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
source-git-commit: d970539d19fad6f274245dcc7bac6b3f13e7b7a2
workflow-type: tm+mt
source-wordcount: '1194'
ht-degree: 97%

---

# Supporto delle funzioni di Customer Journey Analytics

Le tabelle seguenti elencano le funzionalità di Adobe Analytics supportate totalmente, parzialmente o non supportate da Customer Journey Analytics (CJA). Con l’incremento delle funzioni aggiunte a CJA, questi elenchi subiranno modifiche nel tempo.

## Funzionalità/componenti completamente supportati

| Funzionalità di Adobe Analytics | Note sul supporto |
| --- | --- |
| Rilevamento delle anomalie | Supporto completo. |
| Attribution IQ | Supporto completo. |
| Metriche calcolate | Supporto completo; eventuali metriche di calcolo esistenti nella versione tradizionale di Analysis Workspace non verranno trasferite a CJA. |
| Stitching cross-device/cross-channel | Supporto completo; consulta [Cross-Channel Analytics](/help/connections/cca/overview.md). |
| Download di CSV | Supporto completo. |
| Calendari personalizzati | Supporto completo. |
| Confronto date | Supporto completo. |
| Intervalli di date | È supportata tutta la funzionalità per intervalli di date. |
| Ora legale | Supporto completo. |
| Dimensioni | Supporto completo; CJA sfrutta XDM e supporta dimensioni illimitate. CJA non è legato alle proprietà o agli eVar personalizzati della versione tradizionale di Adobe Analytics. |
| Dimensioni predefinite di Analysis Workspace (ad esempio, tipo di browser, tipo di referente, sistema operativo, ecc.) | CJA fornisce queste dimensioni in modalitù nativa, purché i campi XDM di base (come agente utente o ID dispositivo) siano compilati. Per i clienti che utilizzano Connettore dati di Analytics (ADC), sono disponibili alcune di queste dimensioni, ma non tutte. Fai riferimento alla nostra [documentazione relativa alle variabili Analytics che sono supportate tramite ADC](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Eliminazione RGPD | Supporto completo; tieni presente che le funzioni RGPD sono ora gestite in coordinamento con [!UICONTROL Adobe Experience Platform]. CJA eredita tutte le modifiche apportate da [!UICONTROL Experience Platform] ai set di dati sottostanti. |
| Variabili elenco/Prop elenco | Supporto completo; CJA sfrutta XDM e supporta array di stringhe illimitati che possono essere utilizzati in modo simile a listVars. |
| Persistenza della variabile merchandising | Supporto completo (gennaio 2022) |
| Metriche | Supporto completo; CJA sfrutta Experience Data Model (XDM), supporta metriche illimitate e non è legato agli eventi di successo personalizzati della versione tradizionale di Analytics. Alcune metriche standard sono state rinominate nella versione tradizionale di Analytics: Visitatori = Persone, Visite = Sessioni, Hit = Eventi. |
| Deduplicazione delle metriche | Supporto completo. |
| Pannelli | Il pannello vuoto, il pannello di attribuzione, il pannello a forma libera e Quick Insights sono completamente supportati. |
| Esportazione PDF | Supporto completo. |
| Conservazione del progetto | Supporto completo. |
| Collegamento del progetto | Supporto completo. |
| Report Builder (plugin di Excel) | Supporto completo. |
| Elaborazione dell’ora rapporto | Supporto completo; CJA si basa esclusivamente sull’elaborazione dell’ora rapporto. |
| Accesso API di reporting | Supporto completo; disponibile tramite l’[API CJA](https://www.adobe.io/cja-apis/docs/). |
| Report/progetti pianificati | Supporto completo. |
| Segmenti | Supporto completo; ora denominati “Filtri”: eventuali segmenti esistenti nella versione tradizionale di Analysis Workspace non verranno caricati in CJA. |
| Autorizzazioni utente/Controlli per l’accesso ai dati | Supporto completo; CJA distingue tra utenti e amministratori del prodotto [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=it). Solo gli amministratori di prodotto possono <ul><li>Creare/aggiornare/eliminare connessioni o visualizzazioni dati</li><li>Aggiornare o eliminare progetti, filtri o metriche di calcolo creati da altri utenti</li><li>Condividere un progetto Workspace con tutti gli utenti.</li></ul> |
| Suite di rapporti virtuali | Supporto completo; ora denominata [Visualizzazioni dati](/help/data-views/create-dataview.md). |
| Conservazione dei componenti VRS | Supporto completo; ora fa parte di Visualizzazioni dati. |

## Supportato con avvertenze

| Funzione | Note |
| --- | --- |
| A4T | Il supporto viene fornito tramite i campi nel [connettore origine Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). |
| Classificazioni | Ora denominati “Set di dati di ricerca”. Le classificazioni utilizzate in Analytics possono essere importate in Experience Platform e in CJA tramite il Connettore dati classificazioni di Analytics. I set di dati di ricerca possono anche essere caricati direttamente in AEP e resi disponibili in CJA. |
| Sessionizzazione personalizzata | Supporto per tutte le funzionalità di sessionizzazione personalizzata che sono diverse dagli hit di background per dispositivi mobili. |
| Attributi cliente | Ora detti “Set di dati profilo”, non vengono importati automaticamente da Experience Cloud, ma dovranno essere caricati in AEP prima di poter essere disponibili in CJA. |
| Dimensioni per dispositivo, browser e tecnologia | Queste dimensioni vengono incluse automaticamente quando un set di dati AEP include campi di schema XDM specifici e sono conformi alla classe Experience Event XDM. |
| Dimensioni e metriche per entrata, uscita e tempo trascorso | Supportate (le entrate e le uscite sono ora denominate Inizio sessione e Fine sessione) e calcolate in modo leggermente diverso. |
| Impostazioni di persistenza eVar | Le eVar non fanno più parte di CJA. Tuttavia, le impostazioni di persistenza ora fanno parte di Visualizzazioni dati e sono disponibili per tutte le dimensioni. La persistenza si basa sull’elaborazione dell’ora rapporto, non sull’elaborazione della raccolta dati. Le dimensioni impostate nelle visualizzazioni dati sono limitate a una persistenza massima di 90 giorni e non supportano la persistenza illimitata. |
| Dimensioni GeoSegmentation | Tutti i dati di geosegmentazione o posizione geografica raccolti in Adobe Analytics fluiscono in CJA tramite il connettore dati di Analytics. Le implementazioni che non utilizzano il connettore dati di Analytics, come quelle che si basano su AEP Web SDK per la raccolta di dati digitali, non dispongono della serie completa di funzioni per la ricerca automatica basata su dati geografici (sono supportati i dati di paese e provincia, ma non quelli di città e codice postale). |
| Canali marketing | I dati dei canali di marketing fluiscono in CJA tramite il connettore dati di Analytics. Le regole del canale di marketing devono ancora essere configurate nella versione tradizionale di Adobe Analytics. Alcune regole non sono supportate. Per ulteriori informazioni, consulta la [documentazione sui canali di marketing CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=it#cja-usecases). |
| Variabile di prodotto | In Experience Platform, per soddisfare questo caso d’uso è possibile utilizzare una matrice di campi di tipo Oggetto all’interno di uno schema di set di dati. In CJA, è possibile utilizzare un qualsiasi numero di variabili di prodotto, senza essere vincolati a una singola variabile come accade invece in Adobe Analytics. |
| Condivisione dei progetti | La condivisione dei progetti è supportata solo tra gli utenti di CJA, non esiste tra CJA e la versione tradizionale di Analysis Workspace. |
| Visualizzazioni | Sono supportate tutte le visualizzazioni, tranne la visualizzazione Mappa. |

## Supporto parziale

| Funzione | Note |
| --- | --- |
| Filtro bot | Per i set di dati basati su Connettore dati di Analytics (ADC), viene applicato il filtro bot. La logica generale di filtro bot per altri set di dati non viene eseguita da [!UICONTROL Experience Platform] o da CJA. |
| Media Analytics | I dati multimediali sono disponibili come parte del connettore dati di Analytics. |
| eVar di Merchandising | Il comportamento degli eVar di merchandising può essere ottenuto utilizzando dimensioni all’interno di un array di oggetti, in quanto un eVar di merchandising non è impostato per utilizzare la persistenza. Al momento, la persistenza della dimensione merchandising non è disponibile. |
| Pannelli | Il pannello vuoto, il pannello di attribuzione, il pannello a forma libera e Quick Insights sono completamente supportati. I pannelli Confronto segmenti, Analytics for Target (A4T) e Visualizzatori simultanei di contenuti multimediali non sono supportati. |
| Regole di elaborazione | Per i set di dati basati sul connettore dati di Analytics, le regole di elaborazione vengono ancora applicate. [Le funzionalità di preparazione dei dati in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) possono essere utilizzate anche al posto delle regole di elaborazione per i dati che vanno direttamente in Platform. |

## Funzioni al momento non supportate, ma pianificate

| Funzione | Note |
| --- | --- |
| Avvisi | Il supporto è pianificato. |
| Analisi contributi | Il supporto è pianificato. |
| Generazione rapporti su Data Warehouse (esportazione riga al 100%) | Il supporto di questa funzione è pianificato per l’interfaccia di Analysis Workspace. Adobe Experience Platform [[!UICONTROL Query Service]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=en) fornisce anche un’interfaccia per questi casi d’uso in CJA. |
| ID Stitching (Stitching ID) tramite Device Graph (Grafico dispositivo) | Il supporto è pianificato. |
| Reporting in tempo reale | Il supporto è pianificato. |
| Segmento IQ | Il supporto è pianificato. |
| Pubblicazione dei segmenti (invio di segmenti da Workspace a Experience Cloud) | Il supporto è pianificato. |

## Supporto non ancora pianificato.

| Funzione | Note |
| --- | --- |
| Activity Map | Il supporto non è ancora pianificato. |
| Advertising Cloud | Il supporto non è ancora pianificato. |
| Generatore regole di classificazione | Il supporto non è ancora pianificato. |
| Feed dati | Il supporto non è ancora pianificato. |
| Riepilogo origini dati | Il supporto non è ancora pianificato. |

## Funzioni che non saranno mai supportate

* Metrica delle persone utilizzando Cross-Device Coop (Coop tra più dispositivi)
* Dashboard di Reports &amp; Analytics
* Segnalibri di Reports &amp; Analytics
* Target di Reports &amp; Analytics
* Eventi calendario di Reports &amp; Analytics
* Mobile Services
