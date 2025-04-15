---
title: Casi d’uso per l’esportazione di dati
description: Understand various data export use cases for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: efb961c571ddcde1017e6bf2080fc2a97c28bb13
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 7%

---

# Casi d’uso per l’esportazione di dati {#data-export-use-cases}

<!-- This contextual help is for the upgrade checklist -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds-step"
>title="Utilizzare funzioni di esportazione simili ai feed dati"
>abstract="Una sostituzione esatta dei feed di dati non è ancora disponibile in Customer Journey Analytics. Tuttavia, funzionalità simili possono essere ottenute con caratteristiche quali l’esportazione di tabelle complete, l’esportazione di set di dati di Platform, l’integrazione di strumenti BI e l’API di reporting."

<!-- markdownlint-enable MD034 -->

This section provides data export use cases and how to implement these use cases with one or more functionalities of Customer Journey Analytics or Experience Platform. Each functionality is further detailed in a separate article.

## Introduzione

One of the unique differences between Adobe Analytics and Customer Journey Analytics is related to the processing of data for attribution and sessionization. See [Compare data processing across Adobe Analytics and Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) for more information.

### Adobe Analytics: collection time attribution and sessionization.

In Adobe Analytics, tutti gli eventi vengono elaborati live e in ordine per ID dispositivo, consentendo ad Adobe di generare, archiviare ed esportare dati clickstream con valori persistenti o attribuiti al momento della raccolta, tra cui:

* Persistenza Dimension (ad esempio, codici di tracciamento delle campagne che scadono dopo 90 giorni).
* Numero di visite e sessionizzazione.
* Valori Dimension, calcolati tramite l’elaborazione e le regole VISTA.

Questo influisce sull’esportazione di dati da Adobe Analytics:

* L’elaborazione dei dati è statica dopo la raccolta iniziale.
* I feed di dati includono colonne &quot;post&quot; che riflettono l’elaborazione al momento della raccolta.


### Customer Journey Analytics: attribuzione e sessionizzazione in fase di query

In Customer Journey Analytics, gli eventi non vengono raccolti in ordine e viene utilizzato un ID persona invece di un ID dispositivo, che consente a Customer Journey Analytics di aggiornare l’attribuzione e la sessionizzazione al momento della generazione del rapporto. Questo tipo di raccolta dati introduce flessibilità, ad esempio:

* L&#39;unione può _riprodurre_ dati ogni giorno o ogni settimana, associando eventi anonimi a eventi noti. Per ulteriori informazioni, vedere [Unione](../../stitching/overview.md).
* Sessionization and persisted values change every time
   * new data is collected or
   * stitching adds events to a person&#39;s history.

The report-time processing impacts the export of data from Customer Journey Analytics. Exports that include persisted values, will not match Customer Journey Analytics reports and values will drift away over time.

Per coerenza metrica, è preferibile utilizzare le nuove funzioni di Customer Journey Analytics. In general, Experience Platform and Customer Journey Analytics data export functionality exceeds the data feed functionality of Adobe Analytics. Experience Platform and Customer Journey Analytics do provide:

* new data sources and processing subject to data export

   * include non-digital data sources,
   * apply custom attribution and sessionization based on business rules, and
   * keep customer journeys updated with stitching.

* realizzazione di casi d’uso personalizzati per l’esportazione di dati

   * esportare i dati dove sono necessari, inclusi gli strumenti di Business Intelligence (BI) e le destinazioni cloud,
   * keep data synchronized with Analysis Workspace through BI tools integration,
   * no need to replicate processing logic in your own systems,
   * new support for calculated metrics, derived fields and segmentation, and

* valutazione della sicurezza e della governance dei dati fin dalla progettazione

   * monitor all data export by user and destination,
   * fissare limiti ai dati disponibili per l&#39;esportazione e
   * imposta gli avvisi per i problemi di consegna e i limiti per le finestre di consegna pianificate.


## Casi d’uso e funzionalità

In generale, l’esportazione dei dati supporta una serie di casi d’uso. Ogni caso d’uso è diverso in termini di dati richiesti e di modalità di accesso ed esportazione di tali dati. Experience Platform and Customer Journey Analytics provide a number of functionalities that either independently or combined can solve the various use cases. The table below provides an overview of identified data export use cases and the Experience Platform and Customer Journey Analytics functionalities to implement these use cases.

| Casi d’uso per l’esportazione di dati | Experience Platform &amp; Customer Journey Analytics functionalities |
|---|---|
| **Backup dei dati**<br/> Conservare una copia completa dei dati digitali per motivi di conformità o normativi. | **Experience Platform**: [**Esporta i set di dati**](export-datasets.md)<br/> Esporta i dati raccolti in Experience Platform direttamente nelle destinazioni cloud secondo una pianificazione o ad hoc. |
| **Data Validation**<br/> Evaluate clickstream data for data collection accuracy. | **Experience Platform**: [**Interfaccia PostgreSQL interattiva di Query Service (Data Distiller) ed esportazione di set di dati**](queryservice-export-datasets.md)<br/> per eseguire query SQL ad hoc utilizzando lo strumento SQL preferito per convalidare i dati nei set di dati.<br/><br/>**Customer Journey Analytics**: [**Esporta tabella completa**](export-full-table.md)<br/> Convalida i dati elaborati da CJA con attribuzione e sessionizzazione applicate. |
| **Strumenti Data Lake, Data Warehouse o BI**<br/> Inserisci dati digitali nei tuoi strumenti di business intelligence o Data Lake per utilizzarli con set di dati aggiuntivi. | **Customer Journey Analytics**: [**BI Extension**](bi-extension.md)<br/> Aggiungi metriche elaborate da Customer Journey Analytics a strumenti di visualizzazione dati come Power BI e combinale con dati aggiuntivi per rapporti personalizzati <br/><br/>**Experience Platform**: [**Query Service (Data Distiller) ed esporta set di dati**](queryservice-export-datasets.md)<br> Genera dati clickstream personalizzati utilizzando SQL da distribuire alle destinazioni cloud. |
| **Preparazione per IA / ML**<br/> Migliorare i modelli e le attività di intelligenza artificiale/apprendimento automatico con i dati di Customer Journey Analytics. | **Customer Journey Analytics**: [**Esporta tabella completa**](export-full-table.md)<br/> Esporta dimensioni e metriche elaborate da Customer Journey Analytics in destinazioni cloud una tantum o ricorrenti, incluse metriche calcolate e segmentazione.<br/><br/>**Experience Platform**: [**Query Service (Data Distiller) ed esporta set di dati**](queryservice-export-datasets.md)<br/> Genera dati clickstream personalizzati utilizzando SQL per arricchire modelli AI/ML. |
