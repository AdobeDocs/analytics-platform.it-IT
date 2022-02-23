---
title: Guida introduttiva a Customer Journey Analytics
description: Scopri i prerequisiti e il flusso di lavoro necessari per implementare Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '538'
ht-degree: 100%

---

# Guida introduttiva a Customer Journey Analytics

Per implementare Customer Journey Analytics, devi seguire questo flusso di lavoro. Alcune attività iniziali vengono eseguite in Adobe Experience Platform, altre in Customer Journey Analytics.

## Prerequisiti

Customer Journey Analytics è disponibile per i clienti che

* sono clienti Adobe Analytics [Select, Prime o Ultimate](https://www.adobe.com/it/analytics/compare-adobe-analytics-packages.html) e
* dispongono del provisioning per [Adobe Experience Platform](https://www.adobe.com/it/experience-platform.html) e
* hanno acquistato la SKU (Stock Keeping Unit) di Customer Journey Analytics.

## Flusso di lavoro

| Attività | Dettagli |
|---|---|
| **Passaggio 1: trasferire i dati in Adobe Experience Platform** | Questo passaggio, eseguito in Adobe Experience Platform, prevede diversi passaggi secondari:<ul><li>**Passaggio 1a: preparare lo schema dati**. Utilizza [Adobe Experience Data Model (XDM)](https://docs.adobe.com/content/help/it-IT/experience-platform/xdm/home.html) per standardizzare i dati sull’esperienza del cliente e [definire schemi](https://docs.adobe.com/content/help/it-IT/experience-platform/tutorials/home.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md) per la gestione della customer experience.</li><li>**Passaggio 1b: creare un set di dati basato sullo schema**. I dati in Platform sono costituiti da set di dati, ad esempio set di dati e-mail, CRM, POS, Adobe Analytics e così via. Ciascun set di dati è costituito da uno schema e da batch di dati. Puoi creare un set di dati [in Experience Platform](https://docs.adobe.com/content/help/it-IT/experience-platform/tutorials/home.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).</li><li>**Passaggio 1c: inserire i dati in Experience Platform**. Utilizza il connettore predefinito di Adobe Analytics Platform per inserire i dati tradizionali Adobe Analytics in Platform. Puoi creare una connessione sorgente per ogni suite di rapporti. Consulta [Creare una connessione sorgente con Adobe Analytics](https://docs.adobe.com/content/help/it-IT/experience-platform/tutorials/home.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) nella documentazione di Adobe Experience Platform. Una volta creata la connessione, vengono automaticamente creati uno schema di destinazione e un set di dati per contenere i dati in arrivo. Inoltre, avviene il recupero dei dati e vengono acquisiti fino a 13 mesi di dati storici. Al termine dell’acquisizione iniziale, puoi procedere con lo `Step 2` per creare una connessione tra questo set di dati di Analytics e Customer Journey Analytics. In alternativa, è possibile inserire altri tipi di dati tramite [inserimento batch](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md), [inserimento streaming](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) o [altri connettori sorgente](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md).</li></ul> |
| **Passaggio 2: creare connessioni tra set di dati di Platform e Customer Journey Analytics** | Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti sui set di dati bisogna prima stabilire una connessione tra i set di dati in Experience Platform e Workspace.<br>Consulta [Creare una connessione](/help/connections/create-connection.md). |
| **Passaggio 3: creare visualizzazioni dati** | Una visualizzazione dati è una visualizzazione “filtrata” dei dati. Puoi creare diverse visualizzazioni dati per la stessa connessione, con diverse impostazioni per timeout visita, attribuzione e così via. Puoi creare più visualizzazioni dati per un singolo set di dati.<br>Consulta [Creare una visualizzazione dati](/help/data-views/create-dataview.md). |
| **Passaggio 4: creare rapporti sui dati multicanale in Workspace** | Dopo aver creato connessioni e visualizzazioni dati, analizza i dati che hai immesso utilizzando la potenza e la flessibilità di Analysis Workspace.<br>Consulta [Eseguire analisi di base](/help/analysis-workspace/perform-basic-analysis.md) ed [Eseguire analisi avanzate](/help/analysis-workspace/perform-adv-analysis.md). |
