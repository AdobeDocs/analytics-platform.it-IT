---
title: Inserire dati Google Analytics in Adobe Experience Platform
description: 'Spiega come sfruttare il Customer Journey Analytics (CJA) per acquisire le Google Analytics e i dati firebase in Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: b6f62c1d53d023c230fbd7f8ad366ac5c6b13954
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 0%

---


# Inserire dati Google Analytics in Adobe Experience Platform

Questo caso d’uso si concentra su come inserire i dati di Google Analytics come set di dati in Adobe Experience Platform. Spiegheremo come acquisire sia dati storici che dati live. Al termine, puoi combinare entrambi i set di dati nel Customer Journey Analytics per ottenere una visualizzazione cross-device del percorso dell’utente.

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
| **Analisi universale** | Google Analytics 360 | Esegui i passaggi da 1 a 5 delle istruzioni seguenti |
| **Google Analytics 4** | Versione o Google Analytics GA gratuita 360 | Esegui i passaggi 1 e 3-5 delle istruzioni riportate di seguito. Non è necessario il passaggio 2. |

## Inserire dati storici

### 1. Connetti i dati Google Analytics a BigQuery

Le seguenti istruzioni sono basate su Google Analytics universali. Si applicano ai dati storici. Per istruzioni sui dati in streaming live, vai su [Trasferisci i dati in streaming live in AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/ga-to-cja.html?lang=en#ingest-live-streaming-google-analytics-data).

Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/3416092?hl=en).

### 2. Trasforma le sessioni di Google Analytics in eventi in BigQuery

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

Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql).

O guarda questo video:

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Esportare gli eventi Google Analytics in formato JSON in Google Cloud Storage e salvarli in un bucket

Successivamente, verranno importati gli eventi Google Analytics in Google Cloud Storage in formato JSON.

Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

### 4. Inserire i dati da Google Cloud Storage in Experience Platform

In Experience Platform, selezionare **[!UICONTROL Sources]** e trovare l&#39;opzione **[!UICONTROL Google Cloud Storage]**. Da lì è sufficiente trovare il set di dati salvato da Big Query.

Visualizza questo video per le istruzioni:

>[!VIDEO](https://video.tv.adobe.com/v/332641)

### 5. Importare eventi GCS in Adobe Experience Platform e mappare lo schema XDM

Successivamente, è possibile mappare i dati dell&#39;evento GA in un set di dati esistente creato in precedenza o creare un nuovo set di dati utilizzando lo schema XDM scelto. Dopo aver selezionato lo schema, l&#39;Experience Platform applica l&#39;apprendimento automatico per mappare automaticamente ciascuno dei campi nei dati Google Analytics al proprio schema.

Le mappature sono molto semplici da modificare e puoi anche creare campi derivati o calcolati dai dati delle Google Analytics. Una volta completata la mappatura dei campi nello schema XDM, puoi pianificare l’importazione su base periodica e applicare la convalida dell’errore durante il processo di acquisizione. In questo modo non si verificano problemi con i dati importati.

## Inserire dati in streaming live Google Analytics

Puoi anche acquisire eventi in streaming dal vivo da Google Tag Manager direttamente in Adobe Experience Platform.

### Aggiungi variabili personalizzate

Dopo aver effettuato l’accesso all’account Google Tag Manager, è necessario aggiungere Variabili costanti personalizzate relative agli ID organizzazione di Adobe e agli ID dei set di dati. Probabilmente in Google Tag Manager sono già presenti variabili che vengono inviate a Google Analytics, ad esempio e-mail del cliente, nome del cliente, lingua e stato di accesso del cliente. È necessario definire 5 nuove variabili personalizzate:

* ID organizzazione Adobe Experience Cloud
* Endpoint di streaming DCS
* ID set di dati di Experience Platform
* Riferimento schema
* Timestamp pagina.

Ottenendo questi valori, tutti i dati Google Analytics vengono inviati al set di dati corretto e dispongono dello schema corretto. Se non conosci la tua organizzazione Experience Cloud o una delle altre variabili che hai appena menzionato, il tuo account manager Adobe può aiutarti a rintracciarla.

Una volta definite queste variabili personalizzate, possiamo impostare un trigger per inviare anche tutti i dati che stai già inviando alle Google Analytics dell’Experience Platform.

### Configurare un trigger in Google Tag Manager

In questo esempio, è stato definito il trigger &quot;Creazione account&quot;, dove `pageUrl equals account-creation`. Aggiungendo alcune informazioni a questo trigger, puoi assicurarti che quando l’utente esegue l’autenticazione e carica la pagina di creazione dell’account, i dati vengano inviati sia a Google Analytics che ad AEP.

Per istruzioni, guarda questo video:

>[!VIDEO](https://video.tv.adobe.com/v/332668)

### Passaggi successivi

Una volta che Adobe Experience Platform ha iniziato a ricevere i dati delle Google Analytics in tempo reale e hai inserito in backfill i dati storici delle Google Analytics da BigQuery, sei pronto per passare a CJA e

1. [Crea la tua prima ](/help/connections/create-connection.md) connessione, che unirà i dati GA a tutti gli altri dati del cliente utilizzando un comune &quot;ID cliente&quot;.
1. Effettua un’analisi straordinaria in Workspace, ad esempio...

*È qui che l&#39;argomento deve fermarsi o dobbiamo andare nel dettaglio sulla connessione?*
