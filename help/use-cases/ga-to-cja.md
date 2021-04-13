---
title: Come inserire dati Google Analytics in Adobe Experience Platform per l’analisi in Customer Journey Analytics (CJA)
description: 'Spiega come sfruttare il Customer Journey Analytics (CJA) per acquisire le Google Analytics e i dati firebase in Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 793b2ce4ec8a487f6c4290fe2eff00879fcca13d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 0%

---


# Inserire dati Google Analytics in Adobe Experience Platform

Questo caso d’uso si concentra su come inserire i dati di Google Analytics come set di dati in Adobe Experience Platform. (Questo vale sia per i dati storici che per quelli live.) Al termine, puoi combinare entrambi i set di dati per ottenere una visualizzazione cross-device del percorso dell’utente.

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
| **Google Analytics universali** | Google Analytics 360 | Esegui i passaggi da 1 a 5 delle istruzioni seguenti |
| **Google Analytics 4** | Versione o Google Analytics GA gratuita 360 | Esegui i passaggi 1 e 3-5 delle istruzioni riportate di seguito. Non è necessario il passaggio 2. |

## 1. Connetti i dati Google Analytics a BigQuery

Le seguenti istruzioni sono basate su Google Analytics universali.

Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/3416092?hl=en).

## 2. Trasforma le sessioni di Google Analytics in eventi in BigQuery

>[!IMPORTANT]
>
>Questo passaggio si applica solo ai clienti di Universal Analytics

I dati GA memorizzano ogni record nei propri dati come sessione dell’utente anziché come singolo evento. La trasformazione dei dati rende i dati compatibili con Adobe Experience Platform.

Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/3437618?hl=en).

È necessario creare una query SQL per trasformare i dati di Universal Analytics in un formato compatibile con Experience Platform. Visualizza questo video per le istruzioni:

>[!VIDEO](https://video.tv.adobe.com/v/332634)

## 3. Esportare gli eventi Google Analytics in formato JSON in Google Cloud Storage e salvarli in un bucket

Fare riferimento a [queste istruzioni](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

## 4. Inserire i dati da Google Cloud Storage in Experience Platform

Visualizza questo video per le istruzioni:

>[!VIDEO](https://video.tv.adobe.com/v/332641)

## 5. Importare eventi GCS in Adobe Experience Platform e mappare lo schema XDM

Schema di esportazione BigQuery (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
