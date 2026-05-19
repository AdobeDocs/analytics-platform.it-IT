---
title: Configurare i dati in streaming di Google Analytics
description: Scopri come configurare la tua implementazione per inviare un livello dati Google ad Adobe Experience Platform
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T09:49:39.181Z'
TQID: 'https://experienceleague.adobe.com/xav7bGdbGLjYXm70GJBSxnDMfNDZpYp5qij1IqkaZSY'
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
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 259
ht-degree: 90%

---

# Configurare i dati in streaming di Google Analytics

Questa pagina contiene informazioni su come acquisire in Adobe Experience Platform i dati live da Google Analytics, in modo che sia possibile farvi riferimento in una visualizzazione dati in Customer Journey Analytics. Puoi combinare i passaggi descritti in questa pagina con quelli per generare un set di dati storici, descritti in [Acquisire dati storici da Google Analytics in Adobe Experience Platform](backfill.md). Combina un set di dati in streaming con un set di dati precedenti per ottenere una visualizzazione diretta di dati passati e presenti in Customer Journey Analytics.

La configurazione della raccolta dati prevede i seguenti passaggi:

1. Implementa [Tag per Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it). Consulta la [guida rapida](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=it) per rendere operativa un’implementazione di base.
1. Installa l’[estensione Google Data Layer](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html?lang=it). Questa estensione funge da alternativa all’installazione dell’estensione Web SDK, specificamente destinata a un livello dati Google.
1. [Crea uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=it) nella raccolta dati di Adobe Experience Platform. Configura lo stream di dati per inviare dati ad Adobe Experience Platform. Attualmente è necessario mappare ogni oggetto di livello dati Google su un campo XDM applicabile. Adobe prevede di semplificare il flusso di lavoro di mappatura in futuro.

Dopo aver implementato e pubblicato i tag desiderati sul sito, puoi passare a [creare una connessione](/help/connections/create-connection.md), quindi [creare una visualizzazione dati](/help/data-views/create-dataview.md).
