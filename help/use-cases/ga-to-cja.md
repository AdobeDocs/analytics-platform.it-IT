---
title: Impostare il reporting delle Google Analytics nel Customer Journey Analytics
description: null
translation-type: tm+mt
source-git-commit: 9bbc625aca9e0b8384b3e95d79fd695fda863f0b
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---


# Impostare il reporting delle Google Analytics nel Customer Journey Analytics

configurazione di Google Cloud Storage Connector,

configurare Google Tag Manager

Schema di esportazione BigQuery (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)

1. Convertire sessioni GA in eventi in Big Query
1. Esportare eventi Google Analytics in Google Cloud Storage
1. Importare eventi GCS in Adobe Experience Platform ed eseguirne il mapping allo schema XDM

## Prerequisiti

* Accesso a Adobe Experience Platform
* Accesso a Google Analytics universali (versione 360 di Google Analytics) o Google Analytics 4 (versione gratuita o Google Analytics 360 di versione)
* Accesso al Customer Journey Analytics

## Collegare i dati delle Google Analytics a Adobe Experience Platform

La modalità di importazione dei dati di Google Analytics in Adobe Experience Platform dipende dalla versione di Google Analytics in uso:

| ID utilizzato | Hai anche bisogno di questa licenza... | E fai questo... |
| --- | --- | --- |
| **Google Analytics universali** | Google Analytics 360 | Esegui i passaggi 1 - x delle istruzioni seguenti |
| **Google Analytics 4** | Versione o Google Analytics GA gratuita 360 | Non è necessario eseguire il passaggio x nelle istruzioni riportate di seguito. |

Le seguenti istruzioni sono basate su Google Analytics universali.

1. Collega i dati Google Analytics a BigQuery e
Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/3416092?hl=en).
1. (Solo per i clienti Universal Analytics) Trasforma le sessioni di Google Analytics in eventi in BigQuery.
Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/3437618?hl=en).
1. Esporta eventi Google Analytics in Google Cloud Storage.
Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).
