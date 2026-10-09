---
title: Acquisire Dati Multimediali A Pagamento In Customer Journey Analytics
description: Scopri come acquisire dati multimediali a pagamento tramite i connettori di origine di Adobe Experience Platform e preparare connessioni, visualizzazioni dati e metriche in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Use Cases
hold: true
role: Admin
source-git-commit: 29a21d57b6b50d873a4464d1a705c1b4855dd3ea
workflow-type: tm+mt
source-wordcount: '1198'
ht-degree: 0%
---

# Acquisire e utilizzare dati multimediali a pagamento

I dati multimediali a pagamento includono le prestazioni pubblicitarie e i metadati da piattaforme quali [!DNL Meta Ads], [!DNL Google Ads], [!DNL TikTok] e [!DNL LinkedIn]. Questa guida spiega come acquisire tali dati in Adobe Experience Platform e renderli disponibili in Customer Journey Analytics per il reporting e l’analisi.

I dati multimediali a pagamento in genere si spostano attraverso tre fasi:

1. Le piattaforme Advertising forniscono dati su campagne, annunci, risorse e prestazioni.
1. Adobe Experience Platform acquisisce tali dati tramite un connettore di origine e li memorizza nei set di dati multimediali a pagamento standard.
1. Customer Journey Analytics espone i set di dati tramite una connessione e una visualizzazione dati in modo da poter analizzare i dati in Workspace.

I dati multimediali a pagamento vengono acquisiti tramite i connettori di origine di Experience Platform. È ad esempio possibile utilizzare il connettore [!DNL Meta Ads] nella categoria Advertising. Quando connetti un’origine supportata, Adobe esegue il provisioning dei set di dati multimediali a pagamento standard in base allo schema e ai gruppi di campi dei supporti a pagamento globali.

## Prerequisiti

Assicurati di disporre dei seguenti diritti di accesso in Experience Platform:

* Autorizzazione per visualizzare e gestire le origini.
* Autorizzazione per creare schemi, set di dati e flussi di dati.
* Una sandbox selezionata per funzionare in. Scegli la sandbox prima di procedere con i passaggi di configurazione.

Se utilizzi [!DNL Meta Ads] come origine, assicurati anche di disporre dei seguenti prerequisiti:

* Un account [!DNL Meta Business Manager] con almeno un account di annunci attivo che contiene campagne, set di annunci, annunci e risorse.
* App [!DNL Meta] autorizzata per [!DNL Graph API] e [!DNL Marketing API], configurata nella console per sviluppatori [!DNL Meta] e collegata a [!DNL Business Manager].
* Approvati `ads_read` e `ads_management` ambiti per l&#39;app.
* Accesso a livello di inserzionista o superiore per l’utente che autorizza la connessione.
* È stato verificato l&#39;accesso agli account annuncio desiderati nell&#39;interfaccia utente [!DNL Meta].

L&#39;autenticazione al connettore utilizza [!DNL OAuth 2.0]. Durante l’installazione, accedi e concedi l’accesso al connettore. Poiché i token di accesso scadono, preparati a autorizzare nuovamente la connessione in caso di revoca della concessione.

## Modello dati

La configurazione automatica di [Content Analytics Paid Media](/help/content-analytics/config/paid-media.md) spiega in dettaglio il modello di dati a pagamento. Tale configurazione automatica crea e configura i set di dati e i componenti richiesti in generale e per l’analisi specifica dei contenuti.

Per informazioni sul modello di dati a pagamento per file multimediali, consulta questa documentazione. Utilizzala per decidere quali set di dati utilizzare in Customer Journey Analytics. I connettori di origine configurati generano questi set di dati.

## Acquisire dati multimediali a pagamento

Utilizza il seguente procedimento per collegare un’origine e acquisire dati multimediali a pagamento in Experience Platform:

1. Verifica di disporre delle autorizzazioni di origine di Experience Platform e dell’accesso ad-platform richiesti.
1. In Experience Platform, vai a **[!UICONTROL Origini]** > **[!UICONTROL Catalogo]** > **[!UICONTROL Advertising]**.
1. Verifica di trovarti nella sandbox che contiene i set di dati per contenuti multimediali a pagamento.
1. Selezionare il connettore da utilizzare, ad esempio **[!DNL Meta Ads]**. Seleziona **[!UICONTROL Configura]** per creare una nuova connessione oppure seleziona **[!UICONTROL Aggiungi dati]** per aggiungere altri dati a una connessione esistente.
1. Eseguire l&#39;autenticazione con [!DNL OAuth 2.0] effettuando l&#39;accesso con un utente che dispone dell&#39;accesso a livello di inserzionista richiesto.
1. Seleziona gli account dell’annuncio, le entità e i dati insight che desideri acquisire.
1. Verifica che il provisioning dei set di dati di ricerca e del set di dati delle metriche di riepilogo sia stato eseguito correttamente.
1. Immetti le impostazioni del flusso di dati, conferma i set di dati di destinazione e configura la pianificazione dell’acquisizione.
1. Salva il flusso di dati e monitora le esecuzioni in **[!UICONTROL Origini]** > **[!UICONTROL Flussi di dati]**.
1. Verifica che siano presenti i set di dati multimediali a pagamento standard e che contengano dati.

Prima di passare a Customer Journey Analytics, convalida i dati acquisiti:

* Verificare che i valori dell&#39;entità `GUID` e dell&#39;ID nativo vengano popolati in modo coerente nelle metriche di riepilogo e nei set di dati di ricerca.
* Conferma che ogni riga delle metriche di riepilogo includa una marca temporale.
* Verificare che i campi di reporting chiave, quali le dimensioni (ad esempio: `channel`, `adNetwork`) e le metriche (ad esempio: `impressions`, `clicks`, `spend`) contengano valori. Non tutte le piattaforme di origine compilano alcuni campi come `region`.
* Conferma che i valori di valuta e fuso orario siano coerenti tra i relativi account.

## Utilizzare dati multimediali a pagamento

Customer Journey Analytics non genera rapporti diretti sui set di dati di Experience Platform. Al contrario, esponi i set di dati tramite una connessione e quindi crei una visualizzazione dati che definisce le dimensioni, le metriche e la logica utilizzate nel reporting.

### Creare o aggiornare una connessione

Per creare o aggiornare una connessione, attenersi alla procedura descritta di seguito.

1. In Customer Journey Analytics [crea o modifica una connessione esistente](/help/connections/create-connection.md).
1. Assicurati di selezionare la sandbox che contiene i set di dati per contenuti multimediali a pagamento come parte della configurazione della connessione.
1. Aggiungi i set di dati delle metriche di riepilogo come dati di riepilogo. Se sono disponibili più set di dati di metriche di riepilogo, utilizza [search](/help/connections/create-connection.md#add-datasets) per filtrare in base alle classi `Paid Media` per identificare i set di dati corretti.
1. Aggiungi ogni set di dati di ricerca come set di dati di ricerca. Unisci il set di dati di ricerca ai dati di riepilogo utilizzando gli identificatori GUID di entità corrispondenti (le chiavi globali generate da Adobe) per account, campagna, gruppo di annunci, annuncio, risorsa ed esperienza. Alcune piattaforme di origine supportano anche i join sui valori ID nativi.
1. Se necessario, aggiungi i dati dell’evento clickstream per correlare i dati multimediali a pagamento aggregati ai metadati condivisi, ad esempio ID, codici di tracciamento o parametri `UTM`.
1. Rivedi le [impostazioni specifiche per il set di dati](/help/connections/create-connection.md#dataset-settings) per ogni set di dati.
1. Salva la connessione e verifica che la connessione inizi a eseguire la retrocompilazione dei dati.

I dati multimediali a pagamento sono dati aggregati e non si basano sull’unione di identità a livello di persona. Gli identificatori di entità nella tabella di riepilogo vengono utilizzati per eseguire il join di identità simili nelle tabelle di ricerca.

### Creare una visualizzazione dati

Quando la connessione è pronta, è necessario creare o modificare una o più visualizzazioni dati per la connessione:


1. In Customer Journey Analytics, [crea o modifica una o più visualizzazioni dati](/help/data-views/create-dataview.md):
1. Definisci le impostazioni predefinite, ad esempio fuso orario e valuta.
1. Aggiungi i componenti necessari per l’analisi dei file multimediali a pagamento.

Includi componenti, come i seguenti:

* **Dimensioni**: campagna, canale, rete di annunci, gruppo di annunci, annuncio, risorsa, account, regione e tipo di dispositivo.
* **Metriche**: impression, clic, tasso di click-through, spesa, conversioni, valore di conversione, impegni e metriche pertinenti di condivisione di video o impression.
* **Campi derivati**: normalizza o classifica le dimensioni utilizzando la logica [parsing](/help/data-views/derived-fields/derived-fields.md#url-parse), [espressioni regolari](/help/data-views/derived-fields/derived-fields.md#regex-replace) o [lookup](/help/data-views/derived-fields/derived-fields.md#lookup) per produrre valori di canale e campagna coerenti nelle reti di annunci.
* **Raggruppamento di riepilogo**: [combinare valori correlati da più set di dati in un&#39;unica dimensione di reporting](/help/data-views/component-settings/summary-data-group.md), ad esempio una dimensione del canale a pagamento unificato.
* **Metriche calcolate**: definisci metriche di efficienza riutilizzabili come CPC, CPM, CPA, CTR e tasso di conversione.

### Creare un progetto

Per generare rapporti e analizzare i dati multimediali a pagamento, crea un progetto in Analysis Workspace.

## Convalida

Utilizza il seguente elenco di controllo per convalidare l’implementazione.

### Controlli Adobe Experience Platform

* Verifica che siano presenti le autorizzazioni di origine e l’accesso ad ad-platform.
* Verifica che il connettore sia autenticato e che il flusso di dati sia in esecuzione secondo pianificazione.
* Verifica che tutti i set di dati a pagamento siano presenti e compilati.
* Conferma che gli schemi utilizzino le classi globali di file multimediali a pagamento e i gruppi di campi.
* Conferma che le chiavi di unione, le marche temporali e i campi di reporting chiave siano compilati.

### Controlli Customer Journey Analytics

* Verifica che la connessione includa il set di dati delle metriche di riepilogo e i sei set di dati di ricerca.
* Conferma che la visualizzazione dati includa le dimensioni pubblicitarie e le metriche dei file multimediali a pagamento richieste.
* Conferma che i campi derivati normalizzino i valori del canale e della campagna come previsto.
* Confermare che il raggruppamento riepilogativo consolidi i dati multi-rete laddove necessario.
* Conferma che le metriche calcolate siano definite per i rapporti utilizzati dalla tua organizzazione.
* Verifica che il reporting di Workspace sia allineato al reporting di origine di ad-platform.


>[!MORELIKETHIS]
>
>[Connettore di origine di Meta Ads](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/meta-ads)
>[Configurazione automatica di Content Analytics Paid Media](/help/content-analytics/config/paid-media.md)
