---
title: Inserire dati Google Analytics in Adobe Experience Platform
description: 'Spiega come sfruttare il Customer Journey Analytics (CJA) per acquisire le Google Analytics e i dati firebase in Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: de822eb00a5e205889b4fa96f729845ad4c7e356
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 0%

---


# Inserire dati Google Analytics in Adobe Experience Platform

Questo caso d’uso si concentra su come inserire i dati di Google Analytics come set di dati in Adobe Experience Platform. Spieghiamo come acquisire sia dati storici che dati live. Al termine, puoi combinare entrambi i set di dati nel Customer Journey Analytics per ottenere una visualizzazione cross-device del percorso dell’utente.

I set di dati nell’Experience Platform sono composti di due elementi: uno schema e i record effettivi nel set di dati. Lo schema (lo chiamiamo modello dati di esperienza o XDM per farla breve) è simile alle colonne del set di dati ed è simile alla blueprint o alle regole che descrivono i dati stessi. All’interno di Platform, Adobe fornisce 2 tipi di schemi:

* Schemi predefiniti in cui è possibile mappare automaticamente i dati Google Analytics (denominato schema Evento esperienza)
* Schemi personalizzati che è possibile creare e mappare facilmente i dati delle Google Analytics su

Uno degli aspetti più potenti del modello dati di Adobe è che ti consente di standardizzare tutti i dati di interazione con il cliente in un unico schema comune, il che rende molto più semplice unire i dati in CJA.

## Prerequisiti

Per eseguire queste attività, devi disporre dei seguenti permessi e autorizzazioni:

* Accesso a Adobe Experience Platform
* Accesso a Google Analytics universali (versione 360 di Google Analytics) o Google Analytics 4 (versione gratuita o Google Analytics 360 di versione)
* Accesso al Customer Journey Analytics e alle relative [Autorizzazioni amministratore](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#admin-access-permissions).

La modalità di importazione dei dati di Google Analytics in Adobe Experience Platform dipende dalla versione di Google Analytics in uso:

| ID utilizzato | Hai anche bisogno di questa licenza... | E fai questo... |
| --- | --- | --- |
| **Analisi universale** | Google Analytics 360 | Esegui i passaggi 1-3 delle istruzioni seguenti |
| **Google Analytics 4** | Versione o Google Analytics GA gratuita 360 | Esegui i passaggi 1 e 3 delle istruzioni riportate di seguito. Non è necessario il passaggio 2. |

## Inserire dati storici (backfill)

### 1. Connetti i dati Google Analytics a BigQuery

Per ulteriori informazioni, fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/3416092?hl=en). Queste istruzioni sono basate su Google Analytics universali.

### 2. Trasforma le sessioni di Google Analytics in eventi in BigQuery ed esporta in Google Cloud Storage

>[!IMPORTANT]
>
>Questo passaggio si applica solo ai clienti di Universal Analytics

I dati GA memorizzano ogni record nei propri dati come sessione dell’utente anziché come singolo evento. È necessario creare una query SQL per trasformare i dati di Universal Analytics in un formato compatibile con Experience Platform. Applicare la funzione &quot;unnest&quot; al campo &quot;hits&quot; nello schema GA. Esempio SQL da utilizzare:

`SELECT
*,
timestamp_seconds(`` + hit.time) AS `` 
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
`visitStartTimetimestampyour_bq_table_2021_04_*`,
UNNEST(hits) AS hit 
)`

Al termine della query, salva i risultati completi in una tabella BigQuery.

Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql), che includono istruzioni sulla query SQL.

Il video seguente spiega anche il passaggio successivo, ovvero esportare gli eventi Google Analytics in Google Cloud Storage in formato JSON. Fai clic su **Esporta > Esporta in GCS**. Una volta arrivati, i dati sono pronti per essere inseriti in Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Importa i dati da Google Cloud Storage in Experience Platform e mappa sullo schema XDM

In Experience Platform, selezionare **[!UICONTROL Sources]** e trovare l&#39;opzione **[!UICONTROL Google Cloud Storage]**. Da lì è sufficiente trovare il set di dati salvato da BigQuery.

Nota bene:

* Assicurati di selezionare il formato JSON.
* Puoi selezionare un set di dati esistente o crearne uno nuovo (consigliato).
* Assicurati di selezionare lo stesso schema per i dati storici delle Google Analytics e i dati Live Streaming Google Analytics, anche se si trovano in set di dati separati. Successivamente è possibile unire i set di dati in una connessione [CJA](/help/connections/combined-dataset.md).

Per istruzioni, guarda questo video:

>[!VIDEO](https://video.tv.adobe.com/v/332676)

Puoi mappare i dati dell’evento GA in un set di dati esistente creato in precedenza o creare un nuovo set di dati, utilizzando lo schema XDM scelto. Dopo aver selezionato lo schema, l&#39;Experience Platform applica l&#39;apprendimento automatico per pre-mappare automaticamente ciascuno dei campi nei dati di Google Analytics al tuo [schema XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en#ui).

![](assets/schema-map.png)

Le mappature sono molto semplici da modificare e puoi anche creare campi derivati o calcolati dai dati delle Google Analytics. Una volta completata la mappatura dei campi nello schema XDM, puoi pianificare l’importazione su base periodica e applicare la convalida dell’errore durante il processo di acquisizione. In questo modo non si verificano problemi con i dati importati.

**Campo calcolato &quot;Timestamp&quot;**

Per il campo dello schema `timestamp` nei dati Google Analytics, è necessario creare un campo calcolato speciale nell’interfaccia utente dello schema di Experience Platform. Fare clic su **[!UICONTROL Add calculated field]** e racchiudere la stringa `timestamp` in una funzione `date`, come riportato di seguito:

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

È quindi necessario salvare questo campo calcolato nella struttura dati timestamp nello schema:

![](assets/timestamp.png)

**Campo calcolato &#39;_id&#39;**

Il campo dello schema `_id` deve avere un valore in esso - CJA non tiene conto del valore. Puoi semplicemente aggiungere un &quot;1&quot; al campo:

![](assets/_id.png)

## Inserire dati in streaming live Google Analytics

Puoi anche acquisire eventi in streaming dal vivo da Google Tag Manager direttamente in Adobe Experience Platform.

### 1. Aggiungi variabili personalizzate

Dopo aver effettuato l’accesso all’account Google Tag Manager, è necessario aggiungere alcune variabili costanti personalizzate relative all’Adobe. Probabilmente in Google Tag Manager sono già presenti variabili che vengono inviate a Google Analytics, ad esempio e-mail del cliente, nome del cliente, lingua e stato di accesso del cliente. È necessario definire 5 nuove variabili personalizzate:

* ID organizzazione Adobe Experience Cloud
* Endpoint di streaming DCS
* ID set di dati di Experience Platform
* Riferimento schema
* Timestamp pagina

Ottenendo questi valori, tutti i dati Google Analytics vengono inviati al set di dati corretto e dispongono dello schema corretto. Se non conosci la tua organizzazione Experience Cloud o una delle altre variabili che hai appena menzionato, il tuo account manager Adobe può aiutarti a rintracciarla.

Una volta definite queste variabili personalizzate, possiamo impostare un trigger per inviare anche tutti i dati che stai già inviando alle Google Analytics dell’Experience Platform.

### 2. Configurare un trigger in Google Tag Manager

In questo esempio, è stato definito il trigger &quot;Creazione account&quot;, dove `pageUrl equals account-creation`. Aggiungendo alcune informazioni a questo trigger, puoi assicurarti che quando l’utente esegue l’autenticazione e carica la pagina di creazione dell’account, i dati vengano inviati sia a Google Analytics che ad AEP.

Puoi anche fare riferimento a [Data Ingestion e Google Tag Manager](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=en#module9).

Per istruzioni, guarda questo video:

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## Creare una connessione in CJA al set di dati di Google Analytics

Una volta che Adobe Experience Platform ha iniziato a ricevere i dati delle Google Analytics live e hai inserito in backfill i dati storici delle Google Analytics da BigQuery, sei pronto per passare a CJA e [creare la tua prima connessione](/help/connections/create-connection.md). Questa connessione unirà i dati GA a tutti gli altri dati dei clienti utilizzando un comune &quot;ID cliente&quot;.

## Passaggi successivi

* Creare una visualizzazione dati basata sui dati delle Google Analytics
Successivamente, devi [creare una visualizzazione dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#cja-dataviews) in CJA, in base alla connessione che contiene i dati delle Google Analytics.

* Effettua delle analisi straordinarie in [Workspace](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/home.html?lang=en#cja-workspace). Controlla di nuovo più tardi per alcuni casi di utilizzo dei rapporti.