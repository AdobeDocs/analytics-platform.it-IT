---
title: Supporto delle funzioni di Customer Journey Analytics
description: Confronto tra le funzioni di Customer Journey Analytics e quelle di Adobe Analytics.
translation-type: ht
source-git-commit: d6101371fc9c055a73c7b7bcd1a8d6d6fdc13322

---


# Supporto delle funzioni di Customer Journey Analytics

Le tabelle seguenti elencano le funzionalità di Adobe Analytics supportate totalmente, parzialmente o non supportate da Customer Journey Analytics (CJA). Con l’incremento delle funzioni aggiunte a CJA, questi elenchi subiranno modifiche nel tempo.

## Funzionalità/componenti completamente supportati

| Funzione | Note |
| --- | --- |
| Metriche | CJA sfrutta Experience Data Model (XDM) e supporta metriche illimitate, oltre a non essere legato agli eventi di successo personalizzati della versione tradizionale di Analytics. Alcune metriche standard sono state rinominate nella versione tradizionale di Analytics: Visitatori = Persone, Visite = Sessioni, Hit = Eventi. |
| Dimensioni | CJA sfrutta XDM e supporta dimensioni illimitate, oltre a non essere legato agli eventi di successo personalizzati del tradizionale Analytics. |
| Variabili elenco/Prop elenco | CJA sfrutta XDM e supporta variabili elenco illimitate. |
| Intervalli di date | Il supporto è pianificato per il calendario personalizzato. |
| Metriche calcolate | Eventuali metriche di calcolo esistenti nel tradizionale Analysis Workspace non verranno trasferite a CJA. |
| Segmenti | Ora denominati “Filtri”: eventuali segmenti esistenti nella versione tradizionale di Analysis Workspace non verranno caricati in CJA. |
| Attribution IQ | Supporto completo. |
| Conservazione del progetto | Supporto completo. |
| Collegamento del progetto | Supporto completo. |
| Confronto date | Supporto completo. |
| Suite di rapporti virtuali | Ora questa funzione è denominata [Visualizzazioni dati](/help/data-views/create-dataview.md). |
| Conservazione dei componenti VRS | Ora fa parte di Visualizzazioni dati. |
| Elaborazione dell’ora rapporto | CJA si basa esclusivamente sull’elaborazione dell’ora rapporto. |
| Eliminazione RGPD | Si noti che il RGPD è ora gestito in coordinamento con [!UICONTROL Experience Platform]: CJA eredita qualsiasi modifica apportata da [!UICONTROL Experience Platform] ai set di dati sottostanti. |

## Supportato con avvertenze

| Funzione | Note |
| --- | --- |
| Variabile di prodotto | La variabile di prodotto attualmente disponibile per il reporting dei dati conformi allo schema Experience Event (Evento esperienza), soprattutto sfruttando l’oggetto productListItems. |
| Visualizzazioni | Sono supportate tutte le visualizzazioni, tranne la visualizzazione Mappa. |
| AAM Audiences | Se i clienti utilizzano i set di dati [!UICONTROL Analytics Data Connector], questi faranno parte dei dati ADC. |
| Condivisione dei progetti | La condivisione dei progetti è supportata solo tra gli utenti di CJA, non esiste tra CJA e la versione tradizionale di Analysis Workspace. |
| Sessionizzazione personalizzata | Supporto per tutte le funzionalità di sessionizzazione personalizzata che sono diverse dagli hit di background per dispositivi mobili. |
| Impostazioni di persistenza eVar | Le eVar non fanno più parte di CJA. Tuttavia, le impostazioni di persistenza ora fanno parte di Visualizzazioni dati e sono disponibili per tutte le dimensioni. La persistenza si basa sull’elaborazione dell’ora rapporto, non sull’elaborazione della raccolta dati. Ciò significa che tutta la persistenza sarà basata sull’intervallo di date del reporting, anziché sui dati per intero. |
| Classificazioni | Adesso denominati “Set di dati di ricerca”, non vengono importati automaticamente dal tradizionale Analytics. Devono essere caricati su AEP prima di poter essere disponibili in CJA. |
| Attributi cliente | Ora detti “Set di dati del profilo”, non vengono importati automaticamente da Experience Cloud, ma dovranno essere caricati in AEP prima di poter essere disponibili in CJA. |

## Supporto parziale

| Funzione | Note |
| --- | --- |
| Dimensioni predefinite di Analysis Workspace (ad es. Browser Type, Referrer Type, Marketing Channels, Visit Number (Tipo di browser, Tipo di referente, Canali marketing, Numero visita) e così via). | CJA non fornisce queste dimensioni in modo nativo. Per i clienti che utilizzano Analytics Data Connector (ADC), sono disponibili alcune di queste dimensioni, ma non tutte. Fai riferimento alla nostra [documentazione relativa alle variabili Analytics che sono supportate tramite ADC](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Pannelli | Pieno supporto di Blank Panel (Pannello vuoto), Attribution Panel (Pannello Attribuzione) e pannello Freeform. Il confronto segmenti non è supportato. |
| eVar di Merchandising | Le eVar di merchandising possono essere utilizzate con set di dati basati su ADC, a meno che non siano rigorosamente conformi al medesimo schema XDM, similmente alle limitazioni dell’elenco di prodotti di cui sopra. |
| Filtro bot | Per i set di dati basati su Analytics Data Connector (ADC), viene applicato il filtro bot. La logica generale di filtro bot per altri set di dati non viene eseguita da [!UICONTROL Experience Platform] o da CJA. |
| Regole di elaborazione | Per i set di dati basati su ADC, si applicano ancora le regole di elaborazione. |
| Stitching dell’identità tra più dispositivi | I clienti sono limitati allo stitching di dati una tantum tramite Query Service oppure ora come ora devono applicare questa logica ai dati prima dell’inserimento [!UICONTROL Experience Platform]. |

## Funzioni al momento non supportate, ma pianificate

| Funzione | Note |
| --- | --- |
| Rilevamento delle anomalie | Il supporto è pianificato. |
| Analisi contributi | Il supporto è pianificato. |
| Segmento IQ | Il supporto è pianificato. |
| Pubblicazione dei segmenti (invio di segmenti da Workspace a Experience Cloud) | Il supporto è pianificato. |
| Autorizzazioni utente/Controlli dell’accesso ai dati | Tutti gli utenti di CJA dispongono dei medesimi controlli di accesso, il che significa che tutti gli utenti possono accedere a tutte le connessioni, visualizzazioni dati e così via. In pratica, tutti gli utenti sono utenti a livello di amministratore in CJA. Il supporto è previsto per il 2020. |
| Download di CSV | Il supporto è pianificato. |
| Report/progetti pianificati | Il supporto è pianificato. |
| Avvisi | Il supporto è pianificato. |
| Calendari personalizzati | Il supporto è pianificato. |
| Canali marketing | Il supporto è pianificato. |
| Esportazione PDF | Il supporto è pianificato. |
| Accesso API di reporting | Il supporto è pianificato. Sarà disponibile solo con API 2.0. |
| ID Stitching (Stitching ID) tramite Device Graph (Grafico dispositivo) | Il supporto è pianificato. |

## Supporto non ancora pianificato

| Funzione | Note |
| --- | --- |
| A4T | Il supporto non è ancora pianificato. |
| Analisi del video | Il supporto non è ancora pianificato. |
| Advertising Cloud | Il supporto non è ancora pianificato. |
| Report Builder (plugin di Excel) | Il supporto non è ancora pianificato. |
| Activity Map | Il supporto non è ancora pianificato. |
| Generatore regole di classificazione | Il supporto non è ancora pianificato. |
| Riepilogo origini dati | Il supporto non è ancora pianificato. |
| Reporting in tempo reale | Il supporto non è ancora pianificato. |

## Funzioni che non saranno mai supportate

| Funzione | Note |
| --- | --- |
| Metrica delle persone utilizzando Cross-Device Coop (Coop tra più dispositivi) |  |
| Dashboard di Reports &amp; Analytics |  |
| Segnalibri di Reports &amp; Analytics |  |
| Target di Reports &amp; Analytics |  |
| Eventi calendario di Reports &amp; Analytics |  |
| Ad Hoc Analysis |  |
| Reporting di Data Warehouse | [!UICONTROL Experience Platform Query Service] sarà la nuova interfaccia per questi casi d’uso in CJA. |
| Mobile Services |  |
| Feed dati |  |
