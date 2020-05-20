---
title: Guida introduttiva all'analisi del percorso del cliente
description: Guida Introduttiva All'Analisi Del Percorso Del Cliente.
translation-type: tm+mt
source-git-commit: 7ff761d9a2f2ebbe0e051e5785f12048ca2ea937
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 1%

---


# Guida introduttiva all&#39;analisi del percorso del cliente

Per implementare Analisi percorso cliente, devi seguire questo flusso di lavoro. Alcune attività iniziali vengono eseguite in Adobe Experience Platform, altre in Customer Journey Analytics.

## Prerequisiti

Analisi del percorso del cliente è disponibile per i clienti che

* Sono clienti Adobe Analytics [Select, Prime o Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) e
* dispongono del provisioning per [Adobe Experience Platform](https://www.adobe.com/it/experience-platform.html)e
* Hai acquistato lo SKU di analisi del percorso del cliente

## Flusso di lavoro

| Attività | Dettagli |
|---|---|
| **Passaggio 1: Come ottenere i dati in Adobe Experience Platform** | Questo passaggio, eseguito in Adobe Experience Platform, prevede diversi passaggi secondari:<ul><li>**Fase 1 bis: Prepara lo schema** dati: Utilizzate [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) per standardizzare i dati sull&#39;esperienza cliente e [definire schemi](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md) per la gestione dell&#39;esperienza cliente.</li><li>**Passaggio 1 ter: Crea un dataset basato sullo schema**: I dati in Piattaforma sono costituiti da set di dati, ad esempio set di dati e-mail, set di dati CRM, set di dati POS, set di dati Adobe Analytics, ecc. Ciascun set di dati è costituito da uno schema e da batch di dati. Puoi creare un set di dati [in Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).</li><li>**Passaggio 1 quater: Acquisisci dati in Experience Platform**: Utilizza il connettore della piattaforma Adobe Analytics fornito con i prodotti per l’importazione di dati Adobe Analytics tradizionali nella piattaforma. Puoi creare una connessione sorgente per ogni suite di rapporti. Consultate [Creare una connessione sorgente con Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) nella documentazione di Adobe Experience Platform. Una volta creata la connessione, viene automaticamente creato uno schema di destinazione e un dataset che contiene i dati in arrivo. Inoltre, si verifica il recupero dei dati e vengono acquisiti fino a 13 mesi di dati storici. Al termine dell&#39;assimilazione iniziale, potete procedere con `Step 2` la creazione di una connessione tra il set di dati di Analytics e l&#39;analisi del percorso del cliente. In alternativa, è possibile assimilare altri tipi di dati tramite caricamento [](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md)batch, inserimento[streaming](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)o [altri connettori](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)di origine.</li></ul> |
| **Passaggio 2: Creare connessioni tra set di dati della piattaforma e analisi del percorso cliente** | Una connessione consente di integrare i set di dati di Adobe Experience Platform in Workspace. Per generare rapporti sui set di dati della piattaforma Experience, è innanzitutto necessario stabilire una connessione tra i set di dati in Experience Platform e Workspace.<br>Consultate [Creare una connessione](/help/connections/create-connection.md). |
| **Passaggio 3: Creazione di viste dati** | Una visualizzazione dati è una visualizzazione &quot;filtrata&quot; dei dati. Puoi creare diverse viste dati per la stessa connessione, con diverse impostazioni per timeout visita, attribuzione e così via. Potete creare più viste dati per un singolo dataset.<br>Consultate [Creare una visualizzazione](/help/data-views/create-dataview.md)dati. |
| **Passaggio 4: Report sui dati multicanale in Workspace** | Dopo aver creato connessioni e viste dati, analizzi i dati che hai portato con te utilizzando la potenza e la flessibilità di Analysis Workspace.<br>Consultate [Eseguire analisi](/help/projects/perform-basic-analysis.md) di base ed [Eseguire analisi](/help/projects/perform-adv-analysis.md)avanzate. |
