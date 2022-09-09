---
title: Inserire dati storici Google Analytics in Adobe Experience Platform
description: Spiega come utilizzare Customer Journey Analytics (CJA) per acquisire i dati Google Analytics in Adobe Experience Platform.
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: f65f13d696ad2045f58ccb5c9ef7fed45eb9d68c
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 9%

---


# Inserire dati storici Google Analytics in Adobe Experience Platform

Questa pagina si concentra su come inserire i dati storici Google Analytics in Adobe Experience Platform come set di dati, consentendoti di fare riferimento a tale set di dati in una visualizzazione dati all’interno di un Customer Journey Analytics. Puoi combinare i passaggi di questa pagina con [Configurazione di un’implementazione Live Google Analytics](streaming.md), che genera un set di dati ricorrente. Combina questo set di dati storici con il set di dati dell’implementazione corrente per ottenere una visualizzazione fluida dei dati in Customer Journey Analytics con dati sia correnti che precompilati.

## Prerequisiti

Per queste attività, devi disporre dei diritti di accesso e delle autorizzazioni seguenti:

* Accesso a Adobe Experience Platform
* Accesso alle Google Analytics (GA Standard o GA 360)
* [Accesso amministratore](/help/getting-started/cja-access-control.md) al Customer Journey Analytics

## Impostare un&#39;esportazione BigQuery

La struttura dei dati nelle proprietà di Universal Analytics è diversa dalla struttura dei dati nelle proprietà di Google Analytics 4. Imposta un&#39;esportazione BigQuery in base al tipo di proprietà da cui desideri esportare i dati:

* [Impostare un&#39;esportazione BigQuery per una proprietà Universal Analytics](https://support.google.com/analytics/answer/3416092)
* [Impostare un&#39;esportazione BigQuery per una proprietà Google Analytics 4](https://support.google.com/analytics/answer/9823238)

### Requisiti aggiuntivi per le proprietà di Universal Analytics

>[!NOTE]
>
>Questa sezione si applica solo alle proprietà di Universal Analytics. Se si esporta da una proprietà GA4, è possibile procedere a [Esportare dati in Google Cloud Platform](#export-gcp).

Le proprietà di Universal Analytics memorizzano ogni record nei propri dati come sessione dell&#39;utente invece che come singolo evento. È necessaria una query SQL per trasformare i dati di Universal Analytics in un formato compatibile con Adobe Experience Platform. Applica la `UNNEST` alla funzione `hits` nello schema GA e salvarlo come tabella BigQuery.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

```sql
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
         `example_bq_table_*`,
         UNNEST(hits) AS hit 
   )
```

## Esportare dati in Google Cloud Platform {#export-gcp}

In Google Cloud Platform, passa a **Esporta > Esporta in GCS**. Una volta che i dati sono in Google Cloud Storage, è pronto per essere estratti in Adobe Experience Platform.

## Importare i dati da Google Cloud Storage in Experience Platform

1. In Adobe Experience Platform, seleziona **[!UICONTROL Sources]** a sinistra.
1. Sotto il Catalogo, individua **[!UICONTROL Google Cloud Storage]** opzione . Fai clic su **[!UICONTROL Add data]**.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>Se prevedi di importare sia i dati storici che i dati delle Google Analytics di streaming live, assicurati di utilizzare lo stesso schema per entrambi i set di dati. Puoi unire i set di dati in un CJA utilizzando un [Set di dati combinato](/help/connections/combined-dataset.md).

Puoi mappare i dati dell’evento GA in un set di dati esistente creato in precedenza oppure creare un set di dati, utilizzando lo schema XDM scelto. Dopo aver selezionato lo schema, Experience Platform applica l’apprendimento automatico per pre-mappare sullo [schema XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it#ui) ciascuno dei campi presenti nei dati Google Analytics.

![Mappa dello schema](../assets/schema-map.png)

Una volta completata la mappatura dei campi nello schema XDM, puoi pianificare l’importazione su base periodica e applicare la convalida dell’errore durante il processo di acquisizione. Questa convalida assicura che non ci siano problemi con i dati importati.

## Campi XDM richiesti

Alcuni campi XDM in Platform richiedono il formato corretto per consentire la corretta elaborazione dei dati.

* **`timestamp`**: Crea un campo calcolato speciale nell’interfaccia utente dello schema di Experience Platform. Fai clic su **[!UICONTROL Add calculated field]** e avvolgere `timestamp` stringa in un `date` funzione:

   `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

   Salva il campo calcolato nella struttura dati timestamp nello schema:

   ![Marca temporale](../assets/timestamp.png)

* **`_id`**: Questo campo deve avere un valore in esso - CJA non importa quale sia il valore. Puoi aggiungere un &quot;1&quot; al campo:

   ![ID](../assets/_id.png)

## Passaggi successivi

* Se disponi di dati correnti da inviare in Adobe Experience Platform, consulta [Impostare lo streaming per i dati Google Analytics](streaming.md).
* Per iniziare a generare rapporti sui dati precompilati, consulta [Creare una connessione](/help/connections/create-connection.md).
