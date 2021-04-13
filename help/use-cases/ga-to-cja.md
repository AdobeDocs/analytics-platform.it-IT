---
title: Impostare il reporting delle Google Analytics nel Customer Journey Analytics
description: null
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 49b49f24dbc68b1d9e843e0f4522123e6792a438
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Impostare il reporting delle Google Analytics nel Customer Journey Analytics

Questo caso d’uso spiega come inserire i dati Google Analytics in Adobe Experience Platform e quindi

## Prerequisiti

* Accesso a Adobe Experience Platform
* Accesso a Google Analytics universali (versione 360 di Google Analytics) o Google Analytics 4 (versione gratuita o Google Analytics 360 di versione)
* Accesso al Customer Journey Analytics

## 1. Connettere i dati Google Analytics a Adobe Experience Platform

La modalità di importazione dei dati di Google Analytics in Adobe Experience Platform dipende dalla versione di Google Analytics in uso:

| ID utilizzato | Hai anche bisogno di questa licenza... | E fai questo... |
| --- | --- | --- |
| **Google Analytics universali** | Google Analytics 360 | Esegui i passaggi da 1 a 5 delle istruzioni seguenti |
| **Google Analytics 4** | Versione o Google Analytics GA gratuita 360 | Esegui i passaggi 2 - 5 delle istruzioni riportate di seguito. Non è necessario il passaggio 1. |

Le seguenti istruzioni sono basate su Google Analytics universali.

1. Collega i dati Google Analytics a BigQuery in modo da poter trasformare alcuni dei dati.
Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/3416092?hl=en).

1. (Solo per i clienti Universal Analytics) Trasforma le sessioni di Google Analytics in eventi in BigQuery.
Questo rende i dati compatibili con Adobe Experience Platform. Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/3437618?hl=en).

   Dettagli: In BigQuery, i dati GA verranno visualizzati come tabella:

   ![](assets/ga-bigquery.png)
È necessario creare una query SQL per trasformare i dati di Universal Analytics in un formato compatibile con Experience Platform. Visualizza questo video per le istruzioni:

   >[!VIDEO](https://video.tv.adobe.com/v/332634)

1. Esporta gli eventi Google Analytics in formato JSON in Google Cloud Storage e salvalo in un bucket.
Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

1. Experience Platform i dati di Google Cloud Storage.
Visualizza questo video per le istruzioni:

   >[!VIDEO](https://video.tv.adobe.com/v/332641)

1. Importare eventi GCS in Adobe Experience Platform ed eseguirne il mapping allo schema XDM

Schema di esportazione BigQuery (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
