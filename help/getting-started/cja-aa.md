---
title: Supporto delle funzioni di Customer Journey Analytics
description: Confronto tra le funzioni di Customer Journey Analytics e quelle di Adobe Analytics.
translation-type: tm+mt
source-git-commit: b77165ee5994ec59e346cf6314a7e051ffa07524
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 69%

---


# Supporto delle funzioni di Customer Journey Analytics

Le tabelle seguenti elencano le funzionalità di Adobe Analytics supportate totalmente, parzialmente o non supportate da Customer Journey Analytics (CJA). Con l’incremento delle funzioni aggiunte a CJA, questi elenchi subiranno modifiche nel tempo.

## Funzionalità/componenti completamente supportati

|  di Adobe Analytics | Note |
| --- | --- |
| Metriche | CJA sfrutta Experience Data Model (XDM) e supporta metriche illimitate, oltre a non essere legato agli eventi di successo personalizzati della versione tradizionale di Analytics. Alcune metriche standard sono state rinominate nella versione tradizionale di Analytics: Visitatori = Persone, Visite = Sessioni, Hit = Eventi. |
| Dimensioni | CJA sfrutta XDM e supporta dimensioni illimitate, oltre a non essere legato agli eventi di successo personalizzati del tradizionale Analytics. |
| Variabili elenco/Prop elenco | CJA sfrutta XDM e supporta variabili elenco illimitate. |
| Intervalli di date | Il supporto è pianificato per il calendario personalizzato. |
| Metriche calcolate | Eventuali metriche di calcolo esistenti nel tradizionale Analysis Workspace non verranno trasferite a CJA. |
| Segmenti | Ora denominati “Filtri”: eventuali segmenti esistenti nella versione tradizionale di Analysis Workspace non verranno caricati in CJA. |
| Rilevamento delle anomalie | Supporto completo. |
| Attribution IQ | Supporto completo. |
| Conservazione del progetto | Supporto completo. |
| Collegamento del progetto | Supporto completo. |
| Confronto date | Supporto completo. |
| Suite di rapporti virtuali | Ora questa funzione è denominata [Visualizzazioni dati](/help/data-views/create-dataview.md). |
| Conservazione dei componenti VRS | Ora fa parte di Visualizzazioni dati. |
| Elaborazione dell’ora rapporto | CJA si basa esclusivamente sull’elaborazione dell’ora rapporto. |
| Eliminazione RGPD | Si noti che il RGPD è ora gestito in coordinamento con [!UICONTROL Adobe Experience Platform]: CJA eredita qualsiasi modifica apportata da [!UICONTROL Experience Platform] ai set di dati sottostanti. |
| Autorizzazioni utente/Controlli per l’accesso ai dati | CJA distingue tra utenti e amministratori dei prodotti di Adobe Admin Console. Solo gli amministratori dei prodotti sono in grado di 1) creare, aggiornare ed eliminare connessioni o visualizzazioni dati; 2) aggiornare e eliminare progetti, filtri o metriche di calcolo creati da altri utenti; e 3) condividere un progetto Workspace con tutti gli utenti. |
| Cucitura tra dispositivi/canali | Vedere [Analisi tra canali](/help/connections/cca/overview.md). |
| Dimensioni predefinite  Analysis Workspace (ad es. Tipo di browser, Tipo di referente, Sistema operativo, ecc.) | CJA fornisce queste dimensioni in modo nativo purché i campi XDM di base (ad esempio, agente utente o ID dispositivo) siano popolati. Per i clienti che utilizzano Connettore dati di Analytics (ADC), sono disponibili alcune di queste dimensioni, ma non tutte. Fai riferimento alla nostra [documentazione relativa alle variabili Analytics che sono supportate tramite ADC](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Accesso API di reporting | Attualmente disponibile tramite Analytics API 2.0. |

## Supportato con avvertenze

| Funzione | Note |
| --- | --- |
| Variabile di prodotto | All&#39;interno del Experience Platform , gli utenti possono utilizzare una matrice di campi di tipo Oggetto all&#39;interno di uno schema di dataset per soddisfare questo caso d&#39;uso. All&#39;interno di CJA, i clienti possono utilizzare un numero qualsiasi di variabili di prodotto e non sono limitati a una singola variabile come in  Adobe Analytics. |
| Canali marketing | I dati di Marketing Channels fluiscono in CJA attraverso il Connettore dati di Analytics. Le regole del canale di marketing devono essere ancora configurate nel  Adobe Analytics tradizionale. Alcune regole non sono supportate. Per ulteriori dettagli, consultare la [documentazione di CJA Marketing Channels](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en#cja-usecases). |
| Visualizzazioni | Sono supportate tutte le visualizzazioni, tranne la visualizzazione Mappa. |
| Condivisione dei progetti | La condivisione dei progetti è supportata solo tra gli utenti di CJA, non esiste tra CJA e la versione tradizionale di Analysis Workspace. |
| Sessionizzazione personalizzata | Supporto per tutte le funzionalità di sessionizzazione personalizzata che sono diverse dagli hit di background per dispositivi mobili. |
| Impostazioni di persistenza eVar | Le eVar non fanno più parte di CJA. Tuttavia, le impostazioni di persistenza ora fanno parte di Visualizzazioni dati e sono disponibili per tutte le dimensioni. La persistenza si basa sull’elaborazione dell’ora rapporto, non sull’elaborazione della raccolta dati. Gli Dimension impostati in Visualizzazioni dati sono limitati a una persistenza massima di 90 giorni e non supportano la persistenza illimitata. |
| Classificazioni | Ora denominato &quot;Set di dati di ricerca&quot;. Le classificazioni utilizzate in Analytics possono essere importate nel Experience Platform  e nel CJA tramite il Connettore dati classificazione di Analytics. I set di dati di ricerca possono essere caricati direttamente su AEP e resi disponibili in CJA. |
| Attributi cliente | Ora detti “Set di dati del profilo”, non vengono importati automaticamente da Experience Cloud, ma dovranno essere caricati in AEP prima di poter essere disponibili in CJA. |
| Dimensioni dispositivo, browser, tecnologia | Queste dimensioni vengono incluse automaticamente quando un set di dati AEP include campi di schema XDM specifici e è conforme alla classe XDM Experience Event. |
| Entrate, uscite e dimensioni e metriche dell&#39;intervallo di tempo | Supportato (le voci e le uscite sono ora denominate avvii di sessione e fine di sessione) e sono calcolate in modo leggermente diverso. |

## Supporto parziale

| Funzione | Note |
| --- | --- |
| Pannelli | Il pannello vuoto, il pannello di attribuzione, il pannello a forma libera e Quick Insights sono completamente supportati. I pannelli Confronto segmenti, Analytics for Target (A4T) e Visualizzatori simultanei di contenuti multimediali non sono supportati. |
| eVar di Merchandising | Il comportamento delle eVar di merchandising può essere ottenuto utilizzando dimensioni all&#39;interno di un array di oggetti, dato che un merchandising  eVar non è impostato per utilizzare la persistenza. Al momento, la persistenza della dimensione merchandising non è disponibile. |
| Filtro bot | Per i set di dati basati su Connettore dati di Analytics (ADC), viene applicato il filtro bot. La logica generale di filtro bot per altri set di dati non viene eseguita da [!UICONTROL Experience Platform] o da CJA. |
| Regole di elaborazione | Per i dataset basati su Connettore dati di Analytics, le regole di elaborazione sono ancora applicate. |
| Media Analytics | I dati multimediali sono disponibili come parte del connettore dati di Analytics. |

## Funzioni al momento non supportate, ma pianificate

| Funzione | Note |
| --- | --- |
| Analisi contributi | Il supporto è pianificato. |
| Segmento IQ | Il supporto è pianificato. |
| Pubblicazione dei segmenti (invio di segmenti da Workspace a Experience Cloud) | Il supporto è pianificato. |
| Download di CSV | Il supporto è pianificato. |
| Calendari personalizzati | Il supporto è pianificato. |
| Deduplicazione delle metriche | Il supporto è pianificato. |
| Persistenza variabile Merchandising | Il supporto è pianificato. |
| Report/progetti pianificati | Il supporto è pianificato. |
| Avvisi | Il supporto è pianificato. |
| Esportazione PDF | Il supporto è pianificato. |
| ID Stitching (Stitching ID) tramite Device Graph (Grafico dispositivo) | Il supporto è pianificato. |
| Report Builder (plugin di Excel) | Il supporto è pianificato. |
| Reporting in tempo reale | Il supporto è pianificato. |

## Supporto non ancora pianificato.

| Funzione | Note |
| --- | --- |
| A4T | Il supporto non è ancora pianificato. |
| Advertising Cloud | Il supporto non è ancora pianificato. |
| Activity Map | Il supporto non è ancora pianificato. |
| Generatore regole di classificazione | Il supporto non è ancora pianificato. |
| Riepilogo origini dati | Il supporto non è ancora pianificato. |

## Funzioni che non saranno mai supportate

* Metrica delle persone utilizzando Cross-Device Coop (Coop tra più dispositivi)
* Dashboard di Reports &amp; Analytics
* Segnalibri di Reports &amp; Analytics
* Target di Reports &amp; Analytics
* Eventi calendario di Reports &amp; Analytics
* Ad Hoc Analysis
* Reporting di Data Warehouse - [!UICONTROL Experience Platform Query Service] sarà la nuova interfaccia per questi casi d’uso in CJA.
* Mobile Services
* Feed dati
