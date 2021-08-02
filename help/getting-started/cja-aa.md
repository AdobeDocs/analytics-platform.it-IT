---
title: Supporto delle funzioni di Customer Journey Analytics
description: Confronto tra le funzioni di Customer Journey Analytics e quelle di Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
source-git-commit: 58627fd11c4031449f156e70cbfa41dac143ac90
workflow-type: tm+mt
source-wordcount: '1075'
ht-degree: 60%

---

# Supporto delle funzioni di Customer Journey Analytics

Le tabelle seguenti elencano le funzionalità di Adobe Analytics supportate totalmente, parzialmente o non supportate da Customer Journey Analytics (CJA). Con l’incremento delle funzioni aggiunte a CJA, questi elenchi subiranno modifiche nel tempo.

## Funzionalità/componenti completamente supportati

| Funzione Adobe Analytics | Note sul supporto |
| --- | --- |
| Rilevamento delle anomalie | Supporto completo. |
| Attribution IQ | Supporto completo. |
| Metriche calcolate | Eventuali metriche di calcolo esistenti nel tradizionale Analysis Workspace non verranno trasferite a CJA. |
| Stitching cross-device/cross-channel | Consulta [Analisi cross-channel](/help/connections/cca/overview.md). |
| Confronto date | Supporto completo. |
| Intervalli di date | Il supporto è pianificato per il calendario personalizzato. |
| Dimensioni | CJA sfrutta XDM e supporta dimensioni illimitate, oltre a non essere legato agli eVar personalizzati o alle proprietà del tradizionale Analytics. |
| Dimensioni predefinite di Analysis Workspace (ad esempio tipo di browser, tipo di referente, sistema operativo, ecc.) | CJA fornisce queste dimensioni in modo nativo, purché i campi XDM di base (come l’agente utente o l’ID dispositivo) siano compilati. Per i clienti che utilizzano Connettore dati di Analytics (ADC), sono disponibili alcune di queste dimensioni, ma non tutte. Fai riferimento alla nostra [documentazione relativa alle variabili Analytics che sono supportate tramite ADC](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Eliminazione RGPD | Si noti che il RGPD è ora gestito in coordinamento con [!UICONTROL Adobe Experience Platform]: CJA eredita qualsiasi modifica apportata da [!UICONTROL Experience Platform] ai set di dati sottostanti. |
| Variabili elenco/Prop elenco | CJA sfrutta XDM e supporta array di stringhe illimitati che possono essere utilizzati in modo simile a listVars. |
| Metriche | CJA sfrutta Experience Data Model (XDM) e supporta metriche illimitate, oltre a non essere legato agli eventi di successo personalizzati della versione tradizionale di Analytics. Alcune metriche standard sono state rinominate nella versione tradizionale di Analytics: Visitatori = Persone, Visite = Sessioni, Hit = Eventi. |
| Esportazione PDF | Supporto completo. |
| Conservazione del progetto | Supporto completo. |
| Collegamento del progetto | Supporto completo. |
| Elaborazione dell’ora rapporto | CJA si basa esclusivamente sull’elaborazione dell’ora rapporto. |
| Accesso API di reporting | Ora disponibile utilizzando l’ [API CJA](https://www.adobe.io/cja-apis/docs/). |
| Report/progetti pianificati | Supporto completo. |
| Segmenti | Ora denominati “Filtri”: eventuali segmenti esistenti nella versione tradizionale di Analysis Workspace non verranno caricati in CJA. |
| Autorizzazioni utente/Controlli per l’accesso ai dati | CJA distingue tra utenti e amministratori dei prodotti di Adobe Admin Console. Solo gli amministratori dei prodotti sono in grado di 1) creare, aggiornare ed eliminare connessioni o visualizzazioni dati; 2) aggiornare e eliminare progetti, filtri o metriche di calcolo creati da altri utenti; e 3) condividere un progetto Workspace con tutti gli utenti. |
| Suite di rapporti virtuali | Ora questa funzione è denominata [Visualizzazioni dati](/help/data-views/create-dataview.md). |
| Conservazione dei componenti VRS | Ora fa parte di Visualizzazioni dati. |
| A4T | Il supporto viene fornito tramite i campi in [Connettore dati di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en). |

## Supportato con avvertenze

| Funzione | Note |
| --- | --- |
| Classificazioni | Ora denominati &quot;Set di dati di ricerca&quot;. Le classificazioni utilizzate in Analytics possono essere importate nell’Experience Platform e in CJA tramite il Connettore dati classificazioni di Analytics. I set di dati di ricerca possono anche essere caricati direttamente in AEP e resi disponibili in CJA. |
| Sessionizzazione personalizzata | Supporto per tutte le funzionalità di sessionizzazione personalizzata che sono diverse dagli hit di background per dispositivi mobili. |
| Attributi cliente | Ora detti “Set di dati del profilo”, non vengono importati automaticamente da Experience Cloud, ma dovranno essere caricati in AEP prima di poter essere disponibili in CJA. |
| Dimensioni del dispositivo, del browser e della tecnologia | Queste dimensioni vengono incluse automaticamente quando un set di dati AEP include campi di schema XDM specifici e sono conformi alla classe Experience Event XDM. |
| Dimensioni e metriche di Entrate, Uscite e Tempo trascorso | Supportati (le entrate e le uscite sono ora denominate Avvio sessione e Fine sessione) e vengono calcolati in un modo leggermente diverso. |
| Impostazioni di persistenza eVar | Le eVar non fanno più parte di CJA. Tuttavia, le impostazioni di persistenza ora fanno parte di Visualizzazioni dati e sono disponibili per tutte le dimensioni. La persistenza si basa sull’elaborazione dell’ora rapporto, non sull’elaborazione della raccolta dati. I Dimension impostati nelle visualizzazioni dati sono limitati a una persistenza massima di 90 giorni e non supportano la persistenza illimitata. |
| Canali marketing | I dati dei canali di marketing fluiscono in CJA tramite Analytics Data Connector. Le regole del canale di marketing devono ancora essere configurate nel tradizionale Adobe Analytics. Alcune regole non sono supportate. Per ulteriori informazioni, consulta la [documentazione sui canali di marketing CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en#cja-usecases). |
| Variabile di prodotto | Nell’Experience Platform, gli utenti possono utilizzare una matrice di campi di tipo Oggetto all’interno di uno schema di set di dati per soddisfare questo caso d’uso. All’interno di CJA, i clienti possono utilizzare un qualsiasi numero di variabili di prodotto e non sono limitati a una singola variabile come in Adobe Analytics. |
| Condivisione dei progetti | La condivisione dei progetti è supportata solo tra gli utenti di CJA, non esiste tra CJA e la versione tradizionale di Analysis Workspace. |
| Visualizzazioni | Sono supportate tutte le visualizzazioni, tranne la visualizzazione Mappa. |

## Supporto parziale

| Funzione | Note |
| --- | --- |
| Filtro bot | Per i set di dati basati su Connettore dati di Analytics (ADC), viene applicato il filtro bot. La logica generale di filtro bot per altri set di dati non viene eseguita da [!UICONTROL Experience Platform] o da CJA. |
| Media Analytics | I dati multimediali sono disponibili come parte del Connettore dati di Analytics. |
| eVar di Merchandising | Il comportamento degli eVar di merchandising può essere ottenuto utilizzando dimensioni all’interno di un array di oggetti, in quanto un eVar di merchandising non è impostato per utilizzare la persistenza. Al momento, la persistenza della dimensione merchandising non è disponibile. |
| Pannelli | Il pannello vuoto, il pannello di attribuzione, il pannello a forma libera e Quick Insights sono completamente supportati. I pannelli Confronto segmenti, Analytics for Target (A4T) e Visualizzatori simultanei di contenuti multimediali non sono supportati. |
| Regole di elaborazione | Per i set di dati basati su Connettore dati di Analytics, le regole di elaborazione vengono ancora applicate. [Le funzionalità di preparazione dei dati in Adobe Experience ](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) Platform possono essere utilizzate anche come sostituzione delle regole di elaborazione per i dati che vanno direttamente in Platform. |

## Funzioni al momento non supportate, ma pianificate

| Funzione | Note |
| --- | --- |
| Avvisi | Il supporto è pianificato. |
| Analisi contributi | Il supporto è pianificato. |
| Download di CSV | Il supporto è pianificato. |
| Calendari personalizzati | Il supporto è pianificato. |
| Reporting sulle Date Warehouse (esportazione riga al 100%) | Il supporto è pianificato dall’interfaccia di Analysis Workspace. [!UICONTROL Experience Platform Query Service] fornisce anche un’interfaccia per questi casi d’uso in CJA. |
| ID Stitching (Stitching ID) tramite Device Graph (Grafico dispositivo) | Il supporto è pianificato. |
| Deduplicazione delle metriche | Il supporto è pianificato. |
| Persistenza variabile merchandising | Il supporto è pianificato. |
| Reporting in tempo reale | Il supporto è pianificato. |
| Report Builder (plugin di Excel) | Il supporto è pianificato. |
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
