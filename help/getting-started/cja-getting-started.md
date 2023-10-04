---
title: Guida introduttiva di Customer Journey Analytics
description: Scopri i prerequisiti e il flusso di lavoro necessari per implementare Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 8d3517c86743434aed345bf06b3bd3345490b0ee
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 73%

---

# Guida introduttiva di Customer Journey Analytics

Per implementare Customer Journey Analytics, devi seguire questo flusso di lavoro. Alcune attività iniziali vengono eseguite in Adobe Experience Platform, altre in Customer Journey Analytics.

## Prerequisiti

Customer Journey Analytics è disponibile per i clienti che

* dispongono del provisioning per [Adobe Experience Platform](https://www.adobe.com/it/experience-platform.html) e
* hanno acquistato la SKU (Stock Keeping Unit) di Customer Journey Analytics.

## Flusso di lavoro

| Attività | Dettagli |
| --- | --- |
| **Passaggio 1: se stai eseguendo la migrazione da Adobe Analytics a Customer Journey Analytics, esegui la migrazione dei dati e replica i tuoi progetti.** | Per informazioni sulla migrazione dei dati da Adobe Analytics a Customer Journey Analytics, consulta: <ul><li>[Utilizzare i dati della suite di rapporti di Adobe Analytics in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)</li><li>[Inserire e usare i dati dalla versione tradizionale di Adobe Analytics](../data-ingestion/analytics.md)</li></ul><p>Per informazioni sulla replica dei progetti Adobe Analytics nel Customer Journey Analytics e sulla mappatura dei componenti di progetto da una suite di rapporti di Adobe Analytics a una visualizzazione dati del Customer Journey Analytics, vedi:</p><ul><li>[Migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html)</li></ul> |
| **Passaggio 2: trasferire i dati in Adobe Experience Platform** | Questo passaggio, eseguito in Adobe Experience Platform, prevede diversi passaggi secondari:<ul><li>**Passaggio 2a: preparare lo schema dati**. Utilizza [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) per standardizzare i dati sull’esperienza del cliente e [definire schemi](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it) per la gestione della customer experience.</li><li>**Passaggio 2b: creare un set di dati basato sullo schema**: i dati in Platform sono costituiti da set di dati, ad esempio set di dati e-mail, CRM, POS, Adobe Analytics e così via. Ogni set di dati è costituito da uno schema e da batch di dati. È possibile [creare un set di dati in Experienci Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=it).</li><li>**Passaggio 2c: inserire dati in Experience Platform**. Sono disponibili diverse opzioni.</li></ul> |
| **Passaggio 3: creare connessioni tra set di dati di Platform e Customer Journey Analytics** | Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti sui set di dati bisogna prima stabilire una connessione tra i set di dati in Experience Platform e Workspace.<br>Consulta [Creare una connessione](/help/connections/create-connection.md). |
| **Passaggio 4: creare visualizzazioni dati** | Una visualizzazione dati è una visualizzazione “filtrata” dei dati. Puoi creare diverse visualizzazioni dati per la stessa connessione, con diverse impostazioni per timeout visita, attribuzione e così via. Puoi creare più visualizzazioni dati per un singolo set di dati.<br>Consulta [Creare una visualizzazione dati](/help/data-views/create-dataview.md). |
| **Passaggio 5: creare rapporti sui dati multicanale in Workspace** | Dopo aver creato connessioni e visualizzazioni dati, analizza i dati che hai immesso utilizzando la potenza e la flessibilità di Analysis Workspace.<br>Consulta [Eseguire analisi di base](/help/analysis-workspace/perform-basic-analysis.md) ed [Eseguire analisi avanzate](/help/analysis-workspace/perform-adv-analysis.md). |

## Guide rapide

La sezione [Acquisizione dei dati](../data-ingestion/data-ingestion.md) fornisce guide rapide sul flusso di lavoro di cui sopra. Queste guide rapide illustrano come acquisire i dati da diverse origini (incluso Adobe Analytics) in Adobe Experience Platform e utilizzarli in Customer Journey Analytics.
