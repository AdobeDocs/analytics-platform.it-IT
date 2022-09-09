---
title: Configurare i dati delle Google Analytics di streaming in Adobe Experience Platform
description: Scopri come configurare la tua implementazione per inviare un livello di dati Google a Adobe Experience Platform
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 2%

---

# Configurare i dati delle Google Analytics di streaming in Adobe Experience Platform

Questa pagina si concentra su come inserire i dati Live Google Analytics in Adobe Experience Platform, consentendoti di fare riferimento a tale set di dati in una visualizzazione dati all’interno di un Customer Journey Analytics. Puoi combinare i passaggi di questa pagina con [Inserire dati storici Google Analytics in Adobe Experience Platform](backfill.md), che genera un set di dati contenente dati storici. Combina un set di dati in streaming con un set di dati di backfill per ottenere una visualizzazione senza soluzione di continuità dei dati passati e presenti in Customer Journey Analytics.

La configurazione della raccolta dati prevede i seguenti passaggi:

1. Implementare [Tag per Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it). Consulta la sezione [Guida rapida](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) per rendere operativa un’implementazione di base.
1. Installa il [Estensione Google Data Layer](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). Questa estensione funge da alternativa all’installazione dell’estensione SDK per web, specificamente destinata a un livello di dati Google.
1. [Creare un archivio dati](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) nella raccolta dati di Adobe Experience Platform. Configura il Datastream per inviare dati a Adobe Experience Platform. È attualmente necessario mappare ogni oggetto livello dati Google a un campo XDM applicabile. Adobe prevede di semplificare il flusso di lavoro di mappatura in futuro.

Una volta implementati e pubblicati i tag desiderati sul sito, puoi quindi procedere per [Creare una connessione](/help/connections/create-connection.md), quindi [Creare una visualizzazione dati](/help/data-views/create-dataview.md).
