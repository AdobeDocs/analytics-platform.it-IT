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
source-git-commit: e3958dfbad19f5fdd78b2755817d21afad8f8e84
workflow-type: tm+mt
source-wordcount: '2118'
ht-degree: 0%
---
# Configurare e configurare l’integrazione in entrata

Questo articolo descrive i [prerequisiti](#prerequisites), [responsabilità](#responsibilities), [passaggi da verificare](#verification), [passaggi per la risoluzione dei problemi](#troubleshoot) e [criteri di completamento](#completion-criteria) per l&#39;impostazione e la configurazione dell&#39;integrazione Brand Visibility in entrata con Customer Journey Analytics.

## Prerequisiti

Considera i seguenti prerequisiti prima di abilitare l’integrazione in entrata. Utilizza la [procedura di verifica](#verification) seguente per confermare ogni prerequisito.

### Inoltro registro BYOCDN

I registri di accesso CDN devono essere inoltrati e ricevuti da Adobe Brand Visibility per ciascun sito Brand Visibility prima che il connettore di origine Brand Visibility possa essere disponibile.

Questo requisito si applica a ogni sito di Visibilità dei brand. Una configurazione CDN o un feed di registro per un sito, dominio o sottodominio copre solo tale sito.

Confermare entrambe le parti del passaggio di consegne:

1. Hai configurato la CDN o la pipeline di registro pertinente per inoltrare i registri di accesso richiesti alla destinazione Amazon S3 fornita da Adobe.
1. Brand Visibility sta ricevendo e rilevando i registri per il sito pertinente. Il sito è quindi disponibile per la selezione nell’origine Adobe Brand Visibility in Experience Platform.

L’inoltro del registro BYOCDN fornisce i dati della richiesta CDN lato server utilizzati per l’analisi del traffico automatizzato dell’agente. I dati non dipendono dai tag di JavaScript in esecuzione in un browser. Il valore richiesto
Il feed di registro CDN garantisce che il set di dati di riepilogo a valle contenga i dati Visibilità dei brand previsti relativi al traffico agente. Per ulteriori informazioni, vedere [Riferimento inoltro registro BYOCDN](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview).

### Informazioni richieste

Assicurati di disporre di valori per tutti i dettagli richiesti elencati nella tabella seguente per ogni sito di Visibilità dei brand.

| Valore richiesto | Verifica o note |
|---|---|
| Visibilità dei brand sito o dominio | Conferma il sito coperto dall’inoltro del registro CDN. |
| Provider CDN | Identifica la rete CDN utilizzata per il sito. |
| Stato inoltro registro CDN | Prova che i registri del sito vengono inoltrati e rilevati dalla Visibilità dei brand. |
| Sito disponibile in origine Visibilità dei brand | Conferma che il sito sia disponibile per la selezione nell’origine Visibilità dei brand. Un sito è disponibile in base alla disponibilità di registri CDN analizzati in Brand Visibility. |
| Organizzazione IMS | Utilizza l’organizzazione IMS associata a Brand Visibility, Experience Platform. |
| Sandbox | Utilizza il nome esatto della sandbox designato per l’integrazione in entrata. |
| Connessione | Identifica la connessione al Percorso di clienti che deve includere il set di dati. |
| Visualizzazione dati | Identifica una visualizzazione dati Customer Journey Analytics nuova o esistente che includa i componenti. |
| Amministratore o proprietario | Specifica il nome o il team che rappresenta il contatto per la configurazione. |

Prima di continuare, verificare che ogni sito sia disponibile per la selezione nell&#39;origine di Adobe Brand Visibility.

### Sandbox

Puoi aggiungere il set di dati alla connessione CJA dopo che il set di dati verrà visualizzato in **[!UICONTROL Set di dati]** nella sandbox.

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

L’origine Visibilità dei brand crea il set di dati di riepilogo in Experience Platform utilizzando:

* La classe **[!UICONTROL Metriche di riepilogo XDM]**
* Il gruppo di campi **[!UICONTROL Riepilogo richieste CDN]**
* Campi organizzati in un oggetto **[!UICONTROL cdn]**

Il connettore crea il set di dati per ogni sito Visibilità dei brand utilizzando il seguente pattern di denominazione: <code>Set di dati Adobe Brand Visibility (ABV) - _baseUrl senza schema_</code>. <br/>Ad esempio `Adobe Brand Visibility (ABV) Dataset - example.com` per il sito <https://example.com>.

I set di dati creati prima dell&#39;adozione di questa convenzione per i nomi visualizzano il set di dati LLMO (Optimization) <code>LLM precedente - _baseUrl senza schema_</code>.

Trova il set di dati in **[!UICONTROL Set di dati]** nella sandbox in cui hai creato il flusso di dati.

Il set di dati sono dati di riepilogo aggregati. Durante l&#39;analisi del volume di richieste in Customer Journey Analytics, utilizza la metrica **[!UICONTROL Numero richieste CDN]** fornita anziché contare le righe del set di dati.

Verifica i campi disponibili nello schema del set di dati creato per il sito di Visibilità dei brand specifico. Per pianificare la configurazione della visualizzazione dati, controlla i campi.

## Responsabilità

Dopo aver abilitato l&#39;origine Visibilità dei brand, Visibilità dei brand:

* Fornisce il set di dati di riepilogo per il sito selezionato.
* Sposta il set di dati nella sandbox in cui hai creato il flusso di dati.

Le tue responsabilità in qualità di cliente sono:

* Per garantire che i registri CDN vengano inoltrati e ricevuti per Visibilità dei brand per ogni sito di Visibilità dei brand.
* Per abilitare l’origine Visibilità dei brand nella sandbox corretta, verifica che il sito sia disponibile per la selezione e selezionalo.
* Per selezionare la connessione Customer Journey Analytics che deve includere il set di dati.
* Aggiungere il set di dati a tale connessione.
* Selezionare i campi da esporre come componenti nella visualizzazione dati di Customer Journey Analytics pertinente.
* Per verificare che le dimensioni e le metriche risultanti supportino l’analisi prevista.

>[!IMPORTANT]
>
>Il connettore gestito si arresta intenzionalmente dopo aver creato e popolato il set di dati di Experience Platform. Adobe non modifica le connessioni Customer Journey Analytics o le visualizzazioni dati.

Il set di dati non è disponibile per l’analisi Customer Journey Analytics finché non aggiungi il set di dati a una connessione. I dati
non è disponibile agli utenti tramite una visualizzazione dati finché i campi pertinenti non sono stati aggiunti a tale visualizzazione dati.

Per abilitare l&#39;origine:

1. In Experience Platform, seleziona la sandbox in cui desideri il set di dati. È possibile allocare un sito una sola volta, quindi assicurati che questa sandbox sia quella desiderata.
1. Vai a **[!UICONTROL Origini]**, quindi **[!UICONTROL Catalogo]** e infine alle applicazioni Adobe. Sulla scheda **[!UICONTROL Adobe Brand Visibility]**, seleziona **[!UICONTROL Configura]** la prima volta. Successivamente, nella scheda viene visualizzato **[!UICONTROL Aggiungi dati]**.

   ![Seleziona Visibilità dei brand da origini](assets/aep-sources-select-bv.png)

1. Seleziona **[!UICONTROL Aggiungi dati]**.

   ![Aggiungi dati all&#39;origine Visibilità dei brand](assets/aep-sources-bv-add-data.png)

1. Nel passaggio ➊ **[!UICONTROL Seleziona dati]**:

   1. Selezionare il sito dalla tabella **[!UICONTROL Nome sito]**. Una volta allocato un sito a un flusso di dati, non puoi selezionarlo nuovamente in quella o in altre sandbox.

      ![Passaggio 1 della configurazione di origine di Brand Visibility](assets/bv-source-step-1.png)

   1. Seleziona **[!UICONTROL Avanti]**.

1. Nel passaggio ➋ **[!UICONTROL Dettagli flusso di dati]**:

   1. Immettere un **[!UICONTROL nome flusso di dati]** e una **[!UICONTROL descrizione]** facoltativa. È inoltre possibile sottoscrivere gli avvisi **[!UICONTROL Avvio esecuzione flusso di dati origini]**, **[!UICONTROL Completamento esecuzione flusso di dati origini]** e **[!UICONTROL Errore esecuzione flusso di dati origini]**.

      ![Passaggio 2 della configurazione di origine di Brand Visibulity](assets/bv-source-step-2.png)

   1. Seleziona **[!UICONTROL Avanti]**.

1. Nel passaggio ➌ **[!UICONTROL Rivedi]**:

   1. Controlla la connessione e l’assegnazione del set di dati.

      ![Passaggio 3 della configurazione di origine di Brand Visibility](assets/bv-source-step-3.png)

   1. selezionare **[!UICONTROL Fine]**.

Il set di dati viene assegnato automaticamente e non è richiesta alcuna mappatura dei campi.

>[!IMPORTANT]
>
>Un sito può essere allocato una sola volta. Per utilizzare il sito in una sandbox diversa, elimina il flusso di dati a cui è allocato il sito. L’eliminazione del flusso di dati influisce su qualsiasi connessione Customer Journey Analytics o visualizzazione dati che si basa sui dati di questa origine.
>


## Verifica

Per verificare l’integrazione in entrata, utilizza la procedura seguente:

1. Verifica che il sito ABV e il registro CDN siano pronti.

   Per ogni sito ABV:

   * Conferma il sito o il dominio coperto dall’inoltro del registro CDN.
   * Verifica che il sito sia disponibile per la selezione nell’origine Visibilità dei brand in Experience Platform. Un sito è disponibile in base alla disponibilità di registri CDN analizzati in Brand Visibility.
   * Non procedere con un&#39;istruzione generale che indica che &quot;i registri CDN sono abilitati&quot;. Procedi quando il sito ABV specifico è disponibile per la selezione.
   * Conferma che Brand Visibility riceva o rilevi i registri per quel sito.
   * Ottieni da Adobe la conferma di preparazione alla Visibilità dei brand del sito.

1. Verifica il set di dati in Experience Platform.

   Dopo aver creato il flusso di dati:
   1. Accedi a **[!UICONTROL Experience Platform]**.
   1. Seleziona la sandbox in cui hai creato il flusso di dati.
   1. Individua il set di dati per il sito di Visibilità dei brand in **[!UICONTROL Set di dati]**.
   1. Conferma che il set di dati sia associato al sito di Visibilità dei brand previsto.
   1. Registra **[!UICONTROL ID set di dati]** e **[!UICONTROL Schema]** collegato.
   1. Esamina il conteggio dei record del set di dati, le informazioni sull’acquisizione più recente e i dati di esempio disponibili, se consentito.
   1. Apri lo schema collegato e verifica la struttura XDM prevista:
      * Classe: **[!UICONTROL Metriche di riepilogo XDM]**
      * Gruppo di campi: **[!UICONTROL Riepilogo richieste CDN]**
      * Oggetto: **[!UICONTROL cdn]**
      * Dimensioni e metriche previste, ad esempio **[!UICONTROL botType]**, **[!UICONTROL cdnProvider]**, **[!UICONTROL url]**, **[!UICONTROL host]**, **[!UICONTROL status]**, **[!UICONTROL richieste]** e **[!UICONTROL timeToFirstByte]**.

1. Aggiungere il set di dati a una connessione

   L’amministratore di Customer Journey Analytics deve aggiungere il set di dati alla connessione prevista:

   1. Accedi a Customer Journey Analytics.
   1. [Crea una nuova connessione o modifica la connessione esistente prevista](/help/connections/create-connection.md). Verifica che la connessione utilizzi la stessa sandbox di Experience Platform in cui è stato creato il set di dati.
   1. Cerca il set di dati per nome o ID set di dati.
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
      * **[!UICONTROL Tipo di bot CDN]**
      * **[!UICONTROL Provider CDN]**
      * **[!UICONTROL URL CDN]**
      * **[!UICONTROL Host CDN]**
      * **[!UICONTROL Stato HTTP CDN]**
      * **[!UICONTROL Numero richieste CDN]**
      * **[!UICONTROL Tempo medio CDN al primo byte]**
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

Il tempo esatto necessario per la disponibilità dei dati dipende dal flusso di lavoro di acquisizione ed elaborazione del Customer Journey Analytics.

## Risoluzione dei problemi

In caso di problemi, controlla i seguenti passaggi:

* Il set di dati non viene visualizzato in AEP.

  Verifica che:

  * L’organizzazione IMS è corretta.
  * La sandbox di Experience Platform selezionata è corretta.
  * L’origine è stata abilitata dopo il funzionamento dell’inoltro del registro CDN.
  * È stato utilizzato il nome o l’ID del set di dati fornito da Adobe.
  * Il set di dati è stato creato per il sito di Visibilità dei brand corretto.

* Il set di dati esiste ma non contiene dati previsti.

  Verifica che:
  * I registri CDN vengono inoltrati per l’esatto sito di Visibilità dei brand.
  * Brand Visibility sta ricevendo o rilevando i registri per il sito.
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

* Il sito non è incluso nell&#39;elenco.

  Verifica che:

  * È disponibile un sito per la selezione in base alla disponibilità di registri CDN analizzati in Brand Visibility.
  * L’inoltro del registro CDN è configurato e funziona per il sito.

* Impossibile selezionare il sito.

  Tieni presente che una volta allocato un sito a un flusso di dati, non può più essere selezionato in quella o in altre sandbox. Per utilizzare il sito in una sandbox diversa, elimina il flusso di dati a cui è allocato il sito. Il sito può quindi essere nuovamente selezionato. L’eliminazione del flusso di dati influisce su qualsiasi connessione Customer Journey Analytics o visualizzazione dati che si basa sui dati di questa origine.

* Il flusso di dati mostra uno stato di errore.

  Utilizza il dashboard **[!UICONTROL Monitoraggio]**. La panoramica di **[!UICONTROL Origini]** indica che un flusso di dati di origine che genera un errore continuo per 30 giorni viene disabilitato automaticamente.


## Criteri di completamento


L’integrazione in entrata è pronta per la configurazione Customer Journey Analytics lato cliente quando vengono confermate tutte le seguenti operazioni:

* I registri CDN vengono inoltrati e ricevuti per Visibilità dei brand per ciascun sito ABV richiesto.
* Ogni sito di Visibilità dei brand è disponibile per la selezione nell&#39;origine Adobe Brand Visibility.
* Hai attivato l’origine Adobe Brand Visibility nella sandbox desiderata.
* Il set di dati di riepilogo per sito viene visualizzato in tale sandbox.
* Hai verificato il set di dati e il relativo schema XDM.
* Il set di dati è stato aggiunto alla connessione CJA prevista.
* Sono stati configurati i relativi componenti Visualizzazione dati di CJA.

