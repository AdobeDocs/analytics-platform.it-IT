---
title: Acquisire dati storici di Google Analytics
description: Come utilizzare Adobe Customer Journey Analytics per acquisire i dati Google Analytics in Adobe Experience Platform.
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T07:58:46.205Z'
TQID: 'https://experienceleague.adobe.com/X5R0sqTkZKxvzH7mwv69-Ez3MIbuTg6XDGuxrw-iugw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 662
ht-degree: 78%

---

# Acquisire dati storici di Google Analytics

Questa pagina contiene informazioni su come acquisire dati storici da Google Analytics in Adobe Experience Platform come set di dati, in modo che sia possibile farvi riferimento in una visualizzazione dati in Customer Journey Analytics. Puoi combinare i passaggi descritti in questa pagina con quelli per generare un set di dati ricorrente descritti in [Configurazione di un’implementazione live di Google Analytics](streaming.md). Combina questo set di dati storici con il set di dati dell’implementazione corrente per ottenere una visualizzazione diretta in Customer Journey Analytics con dati sia correnti che precedenti.

## Prerequisiti

Per queste attività, devi disporre dei diritti di accesso e delle autorizzazioni seguenti:

* Accesso a Adobe Experience Platform
* Accesso a Google Analytics (GA Standard o GA 360)
* [Accesso amministratore](/help/technotes/access-control.md) a Customer Journey Analytics

## Configurare un’esportazione BigQuery

La struttura dei dati nelle proprietà di Universal Analytics è diversa da quella nelle proprietà di Google Analytics 4. Puoi configurare un’esportazione BigQuery in base al tipo di proprietà da cui desideri esportare i dati:

* [Configurare un’esportazione BigQuery per una proprietà Universal Analytics](https://support.google.com/analytics/answer/3416092)
* [Configurare un’esportazione BigQuery per una proprietà Google Analytics 4](https://support.google.com/analytics/answer/9823238)

### Requisiti aggiuntivi per le proprietà di Universal Analytics

>[!NOTE]
>
>Questa sezione è applicabile solo alle proprietà di Universal Analytics. Se devi esportare dati da una proprietà GA4, consulta [Esportare dati in Google Cloud Platform](#export-gcp).

Le proprietà di Universal Analytics memorizzano ogni record nei propri dati come sessione dell’utente invece che come singolo evento. È necessaria una query SQL per trasformare i dati di Universal Analytics in un formato compatibile con Adobe Experience Platform. Applica la funzione `UNNEST` al campo `hits` nello schema GA e salvalo come tabella BigQuery.


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Da Google Analytics a Customer Journey Analytics - BigQuery](https://video.tv.adobe.com/v/332634?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


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

In Google Cloud Platform, passa a **Export > Export to GCS** (Esporta > Esporta in GCS). Una volta che i dati sono in Google Cloud Storage, sono pronti per essere estratti in Adobe Experience Platform.

## Importare i dati da Google Cloud Storage in Experience Platform

1. In Adobe Experience Platform, seleziona **[!UICONTROL Origini]** a sinistra.
1. Nel catalogo, individua l&#39;opzione **[!UICONTROL Google Cloud Storage]**. Fare clic su **[!UICONTROL Aggiungi dati]**.


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Importa dati Google Analytics in Adobe Experience Platform](https://video.tv.adobe.com/v/332676?quality=12&learn=on){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]


>[!TIP]
>
>Se prevedi di importare sia dati storici di Google Analytics che dati live in streaming, assicurati di utilizzare lo stesso schema per entrambi i set di dati. È possibile unire i set di dati in un Customer Journey Analytics utilizzando un [set di dati combinato](/help/connections/combined-dataset.md).

Puoi mappare i dati di eventi GA in un set di dati esistente creato in precedenza, oppure puoi creare un nuovo set di dati, utilizzando lo schema XDM scelto. Dopo che hai selezionato lo schema, Experience Platform applica l’apprendimento automatico per premappare sullo [schema XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it#ui) ciascuno dei campi presenti nei dati di Google Analytics.

![Mappa dello schema che evidenzia i campi di dati GA e le mappature dello schema di destinazione](../../assets/schema-map.png)

Una volta completata la mappatura dei campi sullo schema XDM, puoi pianificare l’importazione su base periodica. Applicando la convalida degli errori durante il processo di acquisizione, puoi verificare che non vi siamo problemi con i dati importati.

## Campi XDM richiesti

Alcuni campi XDM in Platform richiedono il formato corretto per consentire la corretta elaborazione dei dati.

* **`timestamp`**: crea un campo calcolato speciale nell’interfaccia utente dello schema di Experience Platform. Fare clic su **[!UICONTROL Aggiungi campo calcolato]** e racchiudere la stringa `timestamp` in una funzione `date`:

  `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

  Salva il campo calcolato nella struttura dati della marca temporale nello schema:

  ![Marca temporale](../../assets/timestamp.png)

* **`_id`**: questo campo deve contenere un valore. Per Customer Journey Analytics non importa di quale valore si tratti. Puoi semplicemente aggiungere “1” al campo:

  ![ID](../../assets/_id.png)

## Passaggi successivi

* Se disponi di dati correnti da inviare ad Adobe Experience Platform, consulta [Configurare lo streaming per i dati Google Analytics](streaming.md).
* Per iniziare a generare rapporti sui dati precedenti, consulta [Creare una connessione](/help/connections/create-connection.md).
