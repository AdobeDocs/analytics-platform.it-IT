---
title: Acquisire dati Google Analytics in Adobe Experience Platform
description: 'Come sfruttare Customer Journey Analytics (CJA) per acquisire i dati Google Analytics in Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: ht
source-wordcount: '1163'
ht-degree: 100%

---


# Acquisire dati Google Analytics in Adobe Experience Platform

Questo caso d’uso si concentra su come acquisire i dati Google Analytics come set di dati in Adobe Experience Platform. Viene spiegato come acquisire sia dati storici che dati live. Al termine, puoi combinare entrambi i set di dati in Customer Journey Analytics per ottenere una visualizzazione cross-device del percorso dell’utente.

I set di dati in Experience Platform sono composti di due elementi: uno schema e i record effettivi nel set di dati. Lo schema (Experience Data Model, o XDM) è simile alle colonne del set di dati e al blueprint o alle regole che descrivono i dati stessi. In Platform, Adobe fornisce 2 tipi di schemi:

* Schemi predefiniti su cui è possibile mappare automaticamente i dati Google Analytics (schema Experience Event)
* Schemi personalizzati, facili da creare e sui cui è possibile mappare i dati Google Analytics

Una delle caratteristiche più potenti del modello dati di Adobe è che consente di standardizzare tutti i dati relativi alle interazioni con il cliente in un unico schema comune, facilitando notevolmente l’unione dei dati in CJA.

## Prerequisiti

Per queste attività, devi disporre dei diritti di accesso e delle autorizzazioni seguenti:

* Accesso a Adobe Experience Platform
* Accesso a Universal Google Analytics (Google Analytics versione 360) o Google Analytics 4 (versione gratuita o Google Analytics versione 360)
* Accesso a Customer Journey Analytics e alle sue [Autorizzazioni amministratore](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it#admin-access-permissions).

Il modo in cui si importano i dati Google Analytics in Adobe Experience Platform dipende dalla versione di Google Analytics in uso:

| Versione utilizzata | Licenza necessaria | Operazioni necessarie |
| --- | --- | --- |
| **Universal Analytics** | Google Analytics 360 | Passaggi 1-3 delle istruzioni di seguito |
| **Google Analytics 4** | Versione gratuita di GA oppure Google Analytics 360 | Passaggi 1 e 3 delle istruzioni di seguito. Non è necessario eseguire il passaggio 2. |

## Acquisire dati storici (retrocompilazione)

### 1. Connetti i dati Google Analytics a BigQuery.

Per ulteriori informazioni, consulta [queste istruzioni](https://support.google.com/analytics/answer/3416092?hl=it). Tieni presente che queste istruzioni si riferiscono a Universal Google Analytics.

### 2. Trasforma le sessioni di Google Analytics in eventi in BigQuery ed esportali in Google Cloud Storage.

>[!IMPORTANT]
>
>Questo passaggio è valido solo per i clienti di Universal Analytics.

Nei dati GA, ogni record è memorizzato come sessione utente anziché come singolo evento. È necessario creare una query SQL per trasformare i dati di Universal Analytics in un formato compatibile con Experience Platform. Applica la funzione “unnest” al campo “hits” nello schema GA. Esempio di query SQL da utilizzare:

```
SELECT
   *,
   timestamp_seconds(`visitStartTime` + hit.time) AS `timestamp` 
FROM
   (
      SELECT
         fullVisitorId,
         visitNumber,
         visitId,
         visitStartTime,
         trafficSource,
         socialEngagementType,
         channelGrouping,
         device,
         geoNetwork,
         hit 
      FROM
         `your_bq_table_2021_04_*`,
         UNNEST(hits) AS hit 
   )
```

Al termine della query, salva i risultati completi in una tabella BigQuery.

Consulta [queste istruzioni](https://support.google.com/analytics/answer/7029846?hl=it&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql), che includono istruzioni sulla query SQL.

Il video seguente illustra anche il passaggio successivo, per esportare gli eventi Google Analytics per Google Cloud Storage in formato JSON. Fai clic su **Export > Export to GCS** (Esporta > Esporta in GCS). A questo punto, i dati sono pronti per essere inseriti in Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Importa i dati da Google Cloud Storage in Experience Platform e mappali sullo schema XDM.

In Experience Platform, seleziona **[!UICONTROL Sources]** e individua l’opzione **[!UICONTROL Google Cloud Storage]**. Quindi trova il set di dati salvato da BigQuery.

Aspetti da considerare:

* Assicurati di selezionare il formato JSON.
* Puoi selezionare un set di dati esistente o crearne uno nuovo (consigliato).
* Seleziona lo stesso schema per i dati storici di Google Analytics e i dati live in streaming di Google Analytics, anche se si trovano in set di dati separati. Successivamente puoi unire i set di dati in una [connessione CJA](/help/connections/combined-dataset.md).

Per istruzioni, guarda questo video:

>[!VIDEO](https://video.tv.adobe.com/v/332676)

Puoi mappare i dati evento GA in un set di dati esistente creato in precedenza, oppure puoi creare un nuovo set di dati, utilizzando lo schema XDM scelto. Dopo aver selezionato lo schema, Experience Platform applica l’apprendimento automatico per pre-mappare sullo [schema XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it#ui) ciascuno dei campi presenti nei dati Google Analytics.

![](assets/schema-map.png)

È molto semplice modificare le mappature e puoi anche creare campi derivati o calcolati dai dati Google Analytics. Una volta completata la mappatura dei campi sullo schema XDM, puoi pianificare l’importazione su base periodica. Applicando la convalida degli errori durante il processo di acquisizione, puoi verificare che non vi siamo problemi con i dati importati.

**Campo calcolato “Timestamp”**

Per campo schema `timestamp` nei dati Google Analytics, è necessario creare un campo calcolato speciale nell’interfaccia utente dello schema di Experience Platform. Fai clic su **[!UICONTROL Add calculated field]** e racchiudi la stringa `timestamp` in una funzione `date`, così:

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

Quindi, salva il campo calcolato nella struttura dati timestamp nello schema:

![](assets/timestamp.png)

**Campo calcolato “_id”**

Il campo schema `_id` deve contenere un valore; per CJA non importa di quale valore si tratti. Puoi semplicemente aggiungere “1” al campo:

![](assets/_id.png)

## Acquisire dati Google Analytics live in streaming

Puoi anche acquisire eventi live in streaming da Google Tag Manager direttamente in Adobe Experience Platform.

### 1. Aggiungere variabili personalizzate

Dopo aver effettuato l’accesso all’account Google Tag Manager, è necessario aggiungere alcune variabili costanti personalizzate relative ad Adobe. Probabilmente in Google Tag Manager sono già presenti variabili che vengono inviate a Google Analytics, quali e-mail, nome, lingua e stato di accesso del cliente. È necessario definire 5 nuove variabili personalizzate:

* ID organizzazione Adobe Experience Cloud
* Endpoint di streaming DCS
* ID del set di dati di Experience Platform
* Riferimento dello schema
* Timestamp della pagina

Con questi valori, tutti i dati Google Analytics vengono inviati al set di dati corretto e associati allo schema corretto. Se non conosci la tua organizzazione Experience Cloud o altre di queste variabili, rivolgiti al tuo account manager Adobe che potrà aiutarti a rintracciarle.

Una volta definite queste variabili personalizzate, puoi impostare un trigger per inviare a Experience Platform anche tutti i dati che vengono già inviati a Google Analytics.

### 2. Configurare un trigger in Google Tag Manager

In questo esempio, è stato definito il trigger “Account Creation” (Creazione account), dove `pageUrl equals account-creation`. Aggiungendo alcune informazioni a questo trigger, puoi assicurarti che quando l’utente si autentica e carica la pagina di creazione dell’account, i dati vengano inviati sia a Google Analytics che a AEP.

Consulta anche [Acquisizione dei dati e gestione dei tag di Google](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=it#module9).

Per istruzioni, guarda questo video:

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## Creare una connessione in CJA al set di dati Google Analytics

Una volta che Adobe Experience Platform inizia a ricevere i dati live di Google Analytics e che i dati storici da Google Analytics sono stati inseriti mediante BigQuery, puoi passare a CJA e [creare la prima connessione](/help/connections/create-connection.md). Questa connessione unirà i dati GA a tutti gli altri dati dei clienti utilizzando un “ID cliente” comune.

## Passaggi successivi

* Crea un [visualizzazione dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=it#cja-dataviews) in base alla connessione contenente i dati di Google Analytics.

* Fai straordinarie [analisi in Workspace](/help/use-cases/ga-to-cja-reporting.md).