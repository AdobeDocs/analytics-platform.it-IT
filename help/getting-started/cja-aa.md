---
title: Supporto delle funzioni Analisi del percorso del cliente
description: Confronto tra le funzioni di analisi del percorso cliente e quelle di Adobe Analytics.
translation-type: tm+mt
source-git-commit: 1d65b22ab2323bebf42b2782b2bab2ed52869a02

---


# Supporto delle funzioni Analisi del percorso del cliente

Le tabelle seguenti elencano le funzionalità di Adobe Analytics supportate, supportate parzialmente o non supportate in Analisi percorso cliente (CJA). Questi elenchi cambieranno nel tempo man mano che le funzioni vengono aggiunte alla CJA.

## Funzionalità/componenti completamente supportati

| Funzione | Note |
| --- | --- |
| Metriche | CJA sfrutta il modello dati esperienza (XDM) e supporta metriche illimitate e non è legato agli eventi di successo personalizzati di Analytics tradizionale. Alcune metriche standard sono state rinominate in Analytics tradizionale: Visitatori = Persone, Visite = Sessioni, Hit = Eventi. |
| Dimensioni | CJA sfrutta XDM e supporta dimensioni illimitate e non è legato agli eventi di successo personalizzati di Analytics tradizionale. |
| Elenca variabili/Elenco proprietà | CJA sfrutta XDM e supporta variabili elenco illimitate |
| Intervalli di date | È pianificato il supporto per il calendario personalizzato. |
| Metriche calcolate | Eventuali metriche di calcolo esistenti nell’Area di lavoro Analisi tradizionale non verranno portate in CJA. |
| Segmenti | Ora denominata &quot;Filtri&quot; - tenete presente che eventuali segmenti esistenti in Analysis Workspace tradizionale non verranno caricati nel CJA. |
| Attribution IQ | Supporto completo |
| Cura del progetto | Supporto completo |
| Collegamento progetto | Supporto completo |
| Confronto date | Supporto completo |
| Suite di rapporti virtuali | Ora denominata Visualizzazioni [](/help/data-views/create-dataview.md)dati. |
| Cura dei componenti VRS | Ora fa parte delle visualizzazioni dati. |
| Elaborazione tempo report | CJA si basa esclusivamente sull&#39;elaborazione dei tempi di report. |
| Eliminazione GDPR | GDPR è ora gestito in coordinamento con Adobe Experience Platform. CJA eredita qualsiasi modifica apportata dai dati da Experience Platform ai dataset sottostanti. |

## Supportato da cavezze

| Funzione | Note |
| --- | --- |
| Variabile di prodotto | La variabile di prodotto attualmente disponibile per il reporting per i dati conformi allo schema Evento esperienza (utilizzando in particolare l&#39;oggetto productListItems). |
| Visualizzazioni | Sono supportate tutte le visualizzazioni, tranne la visualizzazione Mappa. |
| AAM Audiences | Se i clienti utilizzano insiemi di dati del connettore dati di Analytics, questi dati saranno parte dei dati ADC. |
| Condivisione dei progetti | La condivisione dei progetti è supportata solo tra gli utenti di CJA; non esiste condivisione dei progetti tra CJA e Analysis Workspace tradizionale. |
| Sessionizzazione personalizzata | Supporto per tutte le funzionalità di sessione personalizzate diverse dagli hit di background per dispositivi mobili. |
| Impostazioni di persistenza eVar | Le eVar non fanno più parte della CJA. Tuttavia, le impostazioni di persistenza ora fanno parte di Visualizzazioni dati e sono disponibili per tutte le dimensioni. Tenere presente che la persistenza si basa sull&#39;elaborazione del tempo del rapporto, non sull&#39;elaborazione della raccolta dati. Ciò significa che tutta la persistenza sarà basata sull&#39;intervallo di date del rapporto anziché sull&#39;intera interezza dei dati. |
| Classificazioni | I &quot;Set di dati di ricerca&quot;, ora denominati &quot;Set di dati di ricerca&quot;, non vengono importati automaticamente da Analytics tradizionale. Devono essere caricati su AEP prima di essere disponibili in CJA. |
| Attributi cliente | Ora chiamati &quot;Profile Datasets&quot;, non vengono importati automaticamente da Experience Cloud, ma dovranno essere caricati in AEP prima di essere disponibili in CJA. |

## Supporto parziale

| Funzione | Note |
| --- | --- |
| Dimensioni predefinite di Analysis Workspace (ad es. Tipo di browser, Tipo di referente, Canali di marketing, Numero di visita ecc.) | La CJA non fornisce queste dimensioni in modo nativo. Per i clienti che utilizzano il Connettore dati di Analytics (ADC), alcune di queste dimensioni sono disponibili, ma non tutte. Fai riferimento alla nostra [documentazione in cui le variabili Analytics sono supportate tramite ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Pannelli | Pannello vuoto, pannello Attribuzione e pannello a forma libera sono completamente supportati. Confronto segmenti non supportato. |
| eVars Merchandising | Le eVar di merchandising funzionano solo con set di dati basati su ADC a meno che non siano rigorosamente conformi allo stesso schema XDM (simile alle limitazioni dell&#39;elenco di prodotti sopra). |
| Filtro bot | Per i set di dati basati su Connettore dati di Analytics (ADC), viene applicato il filtro bot. La logica generale di filtraggio dei bot per altri set di dati non viene eseguita da Experience Platform o CJA. |
| Regole di elaborazione | Per i set di dati basati su ADC, le regole di elaborazione sono ancora applicate. |
| Unione delle identità tra dispositivi | I clienti possono utilizzare solo una sola volta i dati tramite il servizio Query oppure devono applicare questa logica ai dati prima dell’assimilazione dei dati della piattaforma Experience. |

## Al momento non supportato, ma pianificato

| Funzione | Note |
| --- | --- |
| Rilevamento delle anomalie | Il supporto è pianificato. |
| Analisi contributi | Il supporto è pianificato. |
| Segmento IQ | Il supporto è pianificato. |
| Pubblicazione dei segmenti (invio di segmenti da Workspace a Experience Cloud) | Il supporto è pianificato. |
| Autorizzazioni utente/Controlli dell&#39;accesso ai dati | Tutti gli utenti di CJA dispongono degli stessi controlli di accesso, il che significa che tutti gli utenti hanno accesso a tutte le connessioni, viste dati, ecc. In sostanza, tutti gli utenti sono utenti a livello di amministratore in CJA. Il sostegno è previsto per il 2020. |
| Download CSV | Il supporto è pianificato. |
| Rapporti/progetti pianificati | Il supporto è pianificato. |
| Avvisi | Il supporto è pianificato. |
| Calendari personalizzati | Il supporto è pianificato. |
| Canali marketing | Il supporto è pianificato. |
| PDF Export | Il supporto è pianificato. |
| Accesso API di reporting | Il supporto è pianificato. Sarà disponibile solo con API 2.0. |
| Installazione ID tramite Device Graph | Il supporto è pianificato. |

## Supporto non ancora pianificato

| Funzione | Note |
| --- | --- |
| A4T | Il supporto non è ancora pianificato. |
| Analisi del video | Il supporto non è ancora pianificato. |
| Advertising Cloud | Il supporto non è ancora pianificato. |
| Generatore di report (plug-in Excel) | Il supporto non è ancora pianificato. |
| Activity Map | Il supporto non è ancora pianificato. |
| Generatore regole di classificazione | Il supporto non è ancora pianificato. |
| Origini dati di riepilogo | Il supporto non è ancora pianificato. |
| Rapporti in tempo reale | Il supporto non è ancora pianificato. |

## Non sarà mai supportato

| Funzione | Note |
| --- | --- |
| Metrica Persone con Coop multi-dispositivo |  |
| Dashboard di Reporting e analisi |  |
| Segnalibri Reporting e analisi |  |
| Destinazioni Reporting e analisi |  |
| Eventi calendario Reporting e analisi |  |
| Ad Hoc Analysis  |  |
| Report di Data Warehouse | Adobe Experience Platform Query Service sarà la nuova interfaccia per questi casi di utilizzo in CJA. |
| Mobile Services |  |
| Feed dati |  |
