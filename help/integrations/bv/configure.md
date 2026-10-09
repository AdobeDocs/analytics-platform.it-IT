---
title: Visibilità dei brand configurazione integrazione in entrata
description: Scopri come configurare l’integrazione di Brand Visibility con Customer Journey Analytics
feature: Experience Platform Integration
role: Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: fbbb3ffb1b0d1d5361b594e81c260dab25f44338
workflow-type: tm+mt
source-wordcount: '1783'
ht-degree: 0%
---
# Configurare e configurare l’integrazione in entrata

Questo articolo descrive i [prerequisiti](#prerequisites), [responsabilità](#responsibilities), [passaggi da verificare](#verification), [passaggi per la risoluzione dei problemi](#troubleshoot) e [criteri di completamento](#completion-criteria) per l&#39;impostazione e la configurazione dell&#39;integrazione Brand Visibility in entrata con Customer Journey Analytics.

## Prerequisiti

Considera i seguenti prerequisiti prima di abilitare l’integrazione in entrata. E utilizza la procedura di verifica per verificare

### Inoltro registro BYOCDN

I registri di accesso CDN devono essere inoltrati e ricevuti da Adobe Brand Visibility per ciascun sito Brand Visibility prima che il connettore di origine Brand Visibility possa essere disponibile.

Questo requisito si applica a ogni sito di Visibilità dei brand. Una configurazione CDN o un feed di registro per un sito, dominio o sottodominio copre solo tale sito, a meno che Adobe non confermi tale copertura per un altro sito.

Verifica con Adobe entrambe le parti del passaggio di consegna:

1. Hai configurato la CDN o la pipeline di registro pertinente per inoltrare i registri di accesso richiesti alla destinazione Amazon S3 fornita da Adobe.
1. Adobe ha confermato che vengono ricevuti e rilevati i registri per il sito pertinente.

L’inoltro del registro BYOCDN fornisce i dati della richiesta CDN lato server utilizzati per l’analisi del traffico automatizzato dell’agente. I dati non dipendono dai tag di JavaScript in esecuzione in un browser. Il valore richiesto
Il feed di registro CDN garantisce che il set di dati di riepilogo a valle contenga i dati Visibilità dei brand previsti relativi al traffico agente. Per ulteriori informazioni, vedere [Riferimento inoltro registro BYOCDN](https://experienceleague.adobe.com/it/docs/brand-visibility/using/log-forwarding/log-forwarding-overview).

### Informazioni richieste

Assicurati di disporre di valori per tutti i dettagli richiesti elencati nella tabella seguente per ogni sito di Visibilità dei brand.

| Valore richiesto | Verifica o note |
|---|---|
| Visibilità dei brand sito o dominio | Conferma il sito coperto dall’inoltro del registro CDN. |
| Provider CDN | Identifica la rete CDN utilizzata per il sito. |
| Stato inoltro registro CDN | Prova che i registri del sito vengono inoltrati e rilevati dalla Visibilità dei brand. |
| Visibilità dei brand conferma di preparazione | Prima di abilitare e pianificare il connettore, conferma con il team dell’account di Adobe la fattibilità. |
| Organizzazione IMS | Utilizza l’organizzazione IMS associata a Brand Visibility, Experience Platform. |
| Sandbox | Utilizza il nome esatto della sandbox designato per l’integrazione in entrata. |
| Connessione | Identifica la connessione al Percorso di clienti che deve includere il set di dati. |
| Visualizzazione dati | Identifica una visualizzazione dati Customer Journey Analytics nuova o esistente che includa i componenti. |
| Amministratore o proprietario | Specifica il nome o il team che rappresenta il contatto per la configurazione. |

Prima che Adobe pianifichi il connettore gestito, il team del tuo account Adobe deve confermare che il sito è pronto per l’integrazione in entrata. Le comunicazioni di consegna si riferiscono a questo come all’approvazione della Visibilità dei brand o alla conferma della preparazione del sito. La pianificazione del connettore gestito è un requisito del servizio gestito, non un’azione self-service del cliente.

### Sandbox

Il connettore gestito deve creare il set di dati nella sandbox specifica denominata di AEP designata dal cliente all’interno dell’organizzazione IMS.

Conferma quanto segue:

* Organizzazione IMS
* Sandbox Experience Platform di Target

La sandbox AEP di destinazione è la stessa sandbox denominata utilizzata dalla connessione Customer Journey Analytics o dalle connessioni corrispondenti che includono il set di dati.

Il cliente può aggiungere il set di dati alla connessione CJA appropriata solo dopo che Adobe conferma che il set di dati gestito è stato creato.

### Set di dati di riepilogo

L’integrazione in entrata fornisce un set di dati di riepilogo aggregato in Experience Platform che contiene informazioni sulle richieste CDN lato server associate a LLM, bot e automated-agent
traffico.

Brand Visibility utilizza i registri di accesso CDN per identificare le richieste provenienti da bot e agenti automatizzati. Questo traffico non attiva i tag JavaScript del browser e pertanto non viene acquisito tramite un’implementazione di analisi web convenzionale.

Per la descrizione dettagliata dell&#39;integrazione in entrata, della struttura del set di dati e dei campi disponibili, vedi [informazioni sul set di dati](#about-the-dataset).

Il connettore gestito crea il set di dati di riepilogo in Experience Platform utilizzando:

* La classe **[!UICONTROL Metriche di riepilogo XDM]**
* Il gruppo di campi **[!UICONTROL Riepilogo richieste CDN]**
* Campi organizzati in un oggetto **[!UICONTROL cdn]**

Il connettore crea il set di dati per ogni sito Visibilità dei brand utilizzando il seguente pattern di denominazione: <code>Set di dati Adobe Brand Visibility (ABV) - _baseUrl senza schema_</code>. <br/>Ad esempio `Adobe Brand Visibility (ABV) Dataset - example.com` per il sito <https://example.com>.

I set di dati creati prima dell&#39;adozione di questa convenzione per i nomi visualizzano il set di dati LLMO (Optimization) <code>LLM precedente - _baseUrl senza schema_</code>.
In tutti i casi, i clienti devono confermare il nome esatto del set di dati o l’ID del set di dati con il proprio account team di Adobe dopo la creazione.

Il set di dati sono dati di riepilogo aggregati. Durante l&#39;analisi del volume di richieste in Customer Journey Analytics, utilizza la metrica **[!UICONTROL Numero richieste CDN]** fornita anziché contare le righe del set di dati.

Verifica i campi disponibili nello schema del set di dati creato per il sito di Visibilità dei brand specifico. Per pianificare la configurazione della visualizzazione dati, controlla i campi.

## Responsabilità

Adobe gestisce il connettore in entrata e, dopo la conferma dei prerequisiti:

* Abilita il connettore gestito ABV → AEP.
* Crea il set di dati di riepilogo per ogni sito ABV configurato.
* Carica il set di dati nella sandbox di AEP fornita dal cliente.
* Fornisce al cliente il nome o l’ID del set di dati per la verifica.

Le tue responsabilità in qualità di cliente sono:

* Per garantire che i registri CDN vengano inoltrati e ricevuti per Visibilità dei brand per ogni sito di Visibilità dei brand.
* Fornire l’organizzazione IMS corretta e la sandbox Experience Platform denominata.
* Per selezionare la connessione Customer Journey Analytics che deve includere il set di dati.
* Aggiungere il set di dati a tale connessione.
* Selezionare i campi da esporre come componenti nella visualizzazione dati di Customer Journey Analytics pertinente.
* Per verificare che le dimensioni e le metriche risultanti supportino l’analisi prevista.

>[!IMPORTANT]
>
>Il connettore gestito si arresta intenzionalmente dopo aver creato e popolato il set di dati di Experience Platform. Adobe non modifica le connessioni Customer Journey Analytics o le visualizzazioni dati.

Il set di dati non è disponibile per l’analisi Customer Journey Analytics finché non aggiungi il set di dati a una connessione. I dati
non è disponibile agli utenti tramite una visualizzazione dati finché i campi pertinenti non sono stati aggiunti a tale visualizzazione dati.

## Verifica

Per verificare l’integrazione in entrata, utilizza la procedura seguente:

1. Conferma disponibilità sito ABV e registro CDN

   Per ogni sito ABV:

   * Conferma il sito o il dominio esatto coperto dalla richiesta.
   * Conferma il provider CDN.
   * Conferma che la CDN o la pipeline del registro inoltrino i registri di accesso richiesti.
   * Conferma che Brand Visibility riceva o rilevi i registri per quel sito.
   * Ottieni da Adobe la conferma di preparazione alla Visibilità dei brand del sito.

   Non procedere con l’utilizzo di un’istruzione generale che indichi che &quot;i registri CDN sono abilitati&quot;, a meno che la conferma non riguardi il sito ABV specifico.

1. Verificare il set di dati gestito in Experience Platform

   Dopo che Adobe conferma che il connettore gestito ha creato il set di dati:
   1. Accedi a **[!UICONTROL Experience Platform]**.
   1. Dall’elenco delle sandbox, seleziona la sandbox denominata fornita durante l’acquisizione.
   1. Individua il nome o l&#39;ID del set di dati fornito da Adobe in **[!UICONTROL Set di dati]**.
   1. Conferma che il set di dati sia associato al sito di Visibilità dei brand previsto.
   1. Registra **[!UICONTROL ID set di dati]** e **[!UICONTROL Schema]** collegato.
   1. Esamina il conteggio dei record del set di dati, le informazioni sull’acquisizione più recente e i dati di esempio disponibili, se consentito.
   1. Apri lo schema collegato e verifica la struttura XDM prevista:
      * Classe: **[!UICONTROL Metriche di riepilogo XDM]**
      * Gruppo di campi: **[!UICONTROL Riepilogo richieste CDN]**
      * Oggetto: **[!UICONTROL cdn]**
      * Dimensioni e metriche previste, ad esempio **[!UICONTROL botType]**, **[!UICONTROL cdnProvider]**, **[!UICONTROL url]**, **[!UICONTROL host]**, **[!UICONTROL status]**, **[!UICONTROL richieste]** e **[!UICONTROL timeToFirstByte]**.

1. Aggiungere il set di dati a una connessione

   L’amministratore di Customer Journey Analytics deve aggiungere il set di dati gestito alla connessione prevista:

   1. Accedi a Customer Journey Analytics.
   1. [Crea una nuova connessione o modifica la connessione esistente prevista](/help/connections/create-connection.md). Verifica che la connessione utilizzi la stessa sandbox di Experience Platform in cui è stato creato il set di dati gestito.
   1. Cerca il set di dati utilizzando il nome o l’ID del set di dati fornito da Adobe.
   1. Aggiungi il set di dati alla connessione.
   1. Configura le impostazioni del set di dati in base alla progettazione Customer Journey Analytics del cliente.
   1. Salva la connessione.
   1. Per confermare che il set di dati è incluso e che l’acquisizione sta progredendo, rivedi i dettagli di connessione.

1. Configurare o aggiornare la visualizzazione dati

   Dopo che il set di dati fa parte della connessione:
   1. Accedi a Customer Journey Analytics.
   1. [Crea una nuova visualizzazione dati o modifica la visualizzazione dati](/help/data-views/create-dataview.md) associata al caso d&#39;uso di reporting previsto.
   1. Selezionare la connessione contenente il set di dati di Visibilità dei brand gestito.
   1. Aggiungi i campi dello schema richiesti come dimensioni o metriche.
   1. Includi i campi necessari per l’analisi pianificata, ad esempio:
      * **[!UICONTROL Tipo bot]**
      * **[!UICONTROL Provider CDN]**
      * **[!UICONTROL URL]**
      * **[!UICONTROL Host]**
      * **[!UICONTROL Stato HTTP]**
      * **[!UICONTROL Numero richieste]**
      * **[!UICONTROL Tempo al primo byte]**
   1. Salva la visualizzazione dati.
   1. Convalida i campi in Analysis Workspace o nel flusso di lavoro di reporting selezionato dal cliente.

1. Convalidare il risultato end-to-end

   Utilizza un periodo di reporting recente e verifica che:

   * Il sito di Visibilità dei brand previsto è rappresentato.
   * Sono presenti i valori previsti per il provider CDN e l’host.
   * È rappresentato il traffico di bot o agenti automatizzati.
   * Le dimensioni URL e HTTP-status contengono i valori previsti.
   * Sono disponibili il conteggio delle richieste CDN e le metriche delle prestazioni.
   * Il set di dati è incluso nella connessione prevista.
   * I campi obbligatori vengono esposti nella visualizzazione dati prevista.

Il tempo esatto necessario per la disponibilità dei dati dipende dall’acquisizione gestita e dal flusso di lavoro di elaborazione del Customer Journey Analytics. Il team del tuo account Adobe deve fornire tutte le aspettative di elaborazione applicabili alla tua richiesta.

## Risoluzione dei problemi

Di seguito sono riportate le operazioni da eseguire in caso di problemi:

* Il set di dati non viene visualizzato in AEP.

  Verifica che:

  * L’organizzazione IMS è corretta.
  * La sandbox di Experience Platform selezionata è corretta.
  * Adobe ha confermato che il connettore gestito è stato abilitato.
  * È stato utilizzato il nome o l’ID del set di dati fornito da Adobe.
  * Il set di dati è stato creato per il sito di Visibilità dei brand corretto.

* Il set di dati esiste ma non contiene dati previsti.

  Verifica che:
  * I registri CDN vengono inoltrati per l’esatto sito di Visibilità dei brand.
  * ABV ha confermato di ricevere o rilevare i registri.
  * Il sito o il dominio nella configurazione CDN corrisponde al sito Visibilità dei brand.
  * Il connettore gestito è stato abilitato dopo la conferma della preparazione del registro CDN.
  * L’intervallo di date selezionato include il periodo successivo all’inizio dell’acquisizione del registro.


* Il set di dati esiste in Experience Platform ma non è disponibile in Customer Journey Analytics.

  Verifica che:
  * La connessione Customer Journey Analytics utilizza la stessa sandbox Experience Platform denominata.
  * Il set di dati è stato aggiunto in modo esplicito alla connessione.
  * L’amministratore di Customer Journey Analytics dispone delle autorizzazioni necessarie.
  * La connessione è stata salvata dopo l’aggiunta del set di dati.

* Il set di dati è nella connessione, ma i campi non sono disponibili per il reporting.

  Verifica che:
  * La visualizzazione dati seleziona la connessione Customer Journey Analytics corretta.
  * I campi dello schema previsti sono stati aggiunti come componenti della visualizzazione dati.
  * I campi sono stati inseriti nella sezione **[!UICONTROL Dimensioni]** o **[!UICONTROL Metriche]** prevista.
  * La visualizzazione dati è stata salvata dopo l’aggiunta dei componenti.
  * Lo schema del set di dati corrisponde alla struttura prevista del gruppo di campi **[!UICONTROL Riepilogo richieste CDN]**.


## Criteri di completamento


L’integrazione in entrata è pronta per la configurazione Customer Journey Analytics lato cliente quando vengono confermate tutte le seguenti operazioni:

* I registri CDN vengono inoltrati e ricevuti per Visibilità dei brand per ciascun sito ABV richiesto.
* Adobe ha confermato la disponibilità del sito per il connettore gestito.
* È stata fornita l’organizzazione IMS.
* È stata fornita la sandbox Experience Platform di destinazione esatta.
* Adobe ha creato il set di dati di riepilogo per sito in tale sandbox.
* Hai verificato il set di dati e il relativo schema XDM.
* Il set di dati è stato aggiunto alla connessione CJA prevista.
* Sono stati configurati i relativi componenti Visualizzazione dati di CJA.

