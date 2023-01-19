---
title: Guida introduttiva di Customer Journey Analytics
description: Scopri i prerequisiti e il flusso di lavoro necessari per implementare Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: f910f8e810c5c5d6f4d43aff2b609d8bf6c131ca
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 100%

---

# Guida introduttiva di Customer Journey Analytics

Per implementare Customer Journey Analytics, devi seguire questo flusso di lavoro. Alcune attività iniziali vengono eseguite in Adobe Experience Platform, altre in Customer Journey Analytics.

## Prerequisiti

Customer Journey Analytics è disponibile per i clienti che

* sono clienti Adobe Analytics [Select, Prime o Ultimate](https://www.adobe.com/it/analytics/compare-adobe-analytics-packages.html) e
* dispongono del provisioning per [Adobe Experience Platform](https://www.adobe.com/it/experience-platform.html) e
* hanno acquistato la SKU (Stock Keeping Unit) di Customer Journey Analytics.

## Flusso di lavoro

| Attività | Dettagli |
| --- | --- |
| **Passaggio 1: se stai eseguendo la migrazione da Adobe Analytics a CJA, scopri cosa fare.** | Vedi [Utilizzo dei dati della suite di rapporti di Adobe Analytics nel Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md). |
| **Passaggio 2: trasferire i dati in Adobe Experience Platform** | Questo passaggio, eseguito in Adobe Experience Platform, prevede diversi passaggi secondari:<ul><li>**Passaggio 2a: preparare lo schema dati**. Utilizza [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) per standardizzare i dati sull’esperienza del cliente e [definire schemi](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it) per la gestione della customer experience.</li><li>**Passaggio 2b: creare un set di dati basato sullo schema**. I dati in Platform sono costituiti da set di dati, ad esempio set di dati e-mail, CRM, POS, Adobe Analytics e così via. Ciascun set di dati è costituito da uno schema e da batch di dati. Puoi [creare un set di dati in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=it).</li><li>**Passaggio 2c: inserire dati in Experience Platform**. Sono disponibili diverse opzioni. Per ulteriori informazioni, consulta i [casi d’uso per l’acquisizione di dati](/help/data-ingestion/data-ingestion.md). |
| **Passaggio 3: creare connessioni tra set di dati di Platform e Customer Journey Analytics** | Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti sui set di dati bisogna prima stabilire una connessione tra i set di dati in Experience Platform e Workspace.<br>Consulta [Creare una connessione](/help/connections/create-connection.md). |
| **Passaggio 4: creare visualizzazioni dati** | Una visualizzazione dati è una visualizzazione “filtrata” dei dati. Puoi creare diverse visualizzazioni dati per la stessa connessione, con diverse impostazioni per timeout visita, attribuzione e così via. Puoi creare più visualizzazioni dati per un singolo set di dati.<br>Consulta [Creare una visualizzazione dati](/help/data-views/create-dataview.md). |
| **Passaggio 5: creare rapporti sui dati multicanale in Workspace** | Dopo aver creato connessioni e visualizzazioni dati, analizza i dati che hai immesso utilizzando la potenza e la flessibilità di Analysis Workspace.<br>Consulta [Eseguire analisi di base](/help/analysis-workspace/perform-basic-analysis.md) ed [Eseguire analisi avanzate](/help/analysis-workspace/perform-adv-analysis.md). |
