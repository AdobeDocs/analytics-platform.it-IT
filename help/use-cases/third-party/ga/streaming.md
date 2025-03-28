---
title: Configurare i dati in streaming di Google Analytics
description: Scopri come configurare la tua implementazione per inviare un livello di dati Google ad Adobe Experience Platform
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
source-git-commit: 8262539078c57e32bc3195ef669325fa4889bea0
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 89%

---

# Configurare i dati in streaming di Google Analytics

Questa pagina contiene informazioni su come acquisire in Adobe Experience Platform i dati live da Google Analytics, in modo che sia possibile farvi riferimento in una visualizzazione dati in Customer Journey Analytics. Puoi combinare i passaggi descritti in questa pagina con quelli per generare un set di dati storici, descritti in [Acquisire dati storici da Google Analytics in Adobe Experience Platform](backfill.md). Combina un set di dati in streaming con un set di dati precedenti per ottenere una visualizzazione diretta di dati passati e presenti in Customer Journey Analytics.

La configurazione della raccolta dati prevede i seguenti passaggi:

1. Implementa [Tag per Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it). Consulta la [guida rapida](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=it) per rendere operativa un’implementazione di base.
1. Installa l’[estensione Google Data Layer](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html?lang=it). Questa estensione funge da alternativa all’installazione dell’estensione Web SDK, specificamente destinata a un livello dati Google.
1. [Crea uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=it) nella raccolta dati di Adobe Experience Platform. Configura lo stream di dati per inviare dati ad Adobe Experience Platform. Attualmente è necessario mappare ogni oggetto di livello dati Google su un campo XDM applicabile. Adobe prevede di semplificare il flusso di lavoro di mappatura in futuro.

Dopo aver implementato e pubblicato i tag desiderati sul sito, puoi passare a [creare una connessione](/help/connections/create-connection.md), quindi [creare una visualizzazione dati](/help/data-views/create-dataview.md).
