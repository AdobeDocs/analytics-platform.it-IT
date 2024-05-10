---
title: Casi d’uso per l’esportazione di dati
description: Comprendere vari casi di utilizzo dell’esportazione di dati per il Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: 8118435a3982c405f76de9070afa05b8fd71ebf3
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 0%

---

# Casi d’uso per l’esportazione di dati

Questa sezione fornisce casi d’uso per l’esportazione di dati. Ogni caso d’uso è descritto nel proprio articolo. Per alcuni casi d’uso, viene fornita più di una soluzione.

## Introduzione

Una delle differenze uniche tra Adobe Analytics e Customer Journey Analytics è relativa all’elaborazione dei dati per l’attribuzione e la sessionizzazione. Consulta [Confrontare l’elaborazione dei dati in Adobe Analytics e Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) per ulteriori informazioni.

### Adobe Analytics: attribuzione e sessionizzazione del tempo di raccolta.

In Adobe Analytics, tutti gli eventi vengono elaborati live e in ordine per ID dispositivo, consentendo ad Adobe di generare, archiviare ed esportare dati clickstream con valori persistenti o attribuiti al momento della raccolta, tra cui:

* Persistenza del Dimension (ad esempio, codici di tracciamento delle campagne che scadono dopo 90 giorni).
* Numero di visite e sessionizzazione.
* Valori Dimension, calcolati mediante elaborazione e regole VISTA.

Questo influisce sull’esportazione di dati da Adobe Analytics:

* L’elaborazione dei dati è statica dopo la raccolta iniziale.
* I feed di dati includono colonne &quot;post&quot; che riflettono l’elaborazione al momento della raccolta.


### Customer Journey Analytics: attribuzione e sessionizzazione in fase di query

Nel Customer Journey Analytics, gli eventi non vengono raccolti in ordine e viene utilizzato un ID persona invece di un ID dispositivo, che consente al Customer Journey Analytics di aggiornare l’attribuzione e la sessionizzazione al momento della generazione del rapporto. Questo tipo di raccolta dati introduce flessibilità, ad esempio:

* Possibilità di unione _riproduci_ dati giornalieri o settimanali, associando eventi anonimi a eventi noti. Consulta [Stitching](../../stitching/overview.md) per ulteriori informazioni.
* La sessionizzazione e i valori persistenti cambiano ogni volta
   * vengono raccolti nuovi dati o
   * l’unione di più aggiunge eventi alla cronologia di una persona.

L’elaborazione al momento del reporting influisce sull’esportazione di dati dal Customer Journey Analytics. Le esportazioni che includono valori persistenti, non corrisponderanno ai rapporti di Customer Journey Analytics e i valori si allontaneranno nel tempo.

Per coerenza metrica, è preferibile utilizzare le nuove funzioni di Customer Journey Analytics. In generale, la funzionalità di esportazione dei dati di Experience Platform e Customer Journey Analytics supera la funzionalità di feed dati di Adobe Analytics. Experience Platform e Customer Journey Analytics forniscono:

* nuove origini dati ed elaborazione soggette all’esportazione di dati

   * includere fonti di dati non digitali,
   * applicare l’attribuzione e la sessionizzazione personalizzate in base alle regole aziendali; e
   * aggiorna i percorsi dei clienti con l’unione.

* realizzazione di casi d’uso personalizzati per l’esportazione di dati

   * esportare i dati dove sono necessari, inclusi gli strumenti di Business Intelligence (BI) e le destinazioni cloud,
   * mantenere i dati sincronizzati con Analysis Workspace tramite l’integrazione di strumenti di business intelligence,
   * non è necessario replicare la logica di elaborazione nei propri sistemi,
   * nuovo supporto per metriche calcolate, campi derivati e segmentazione, e

* valutazione della sicurezza e della governance dei dati fin dalla progettazione

   * monitorare tutte le esportazioni di dati per utente e destinazione,
   * fissare limiti ai dati disponibili per l&#39;esportazione e
   * imposta gli avvisi per i problemi di consegna e i limiti per le finestre di consegna pianificate.


## Casi d’uso e soluzioni

In generale, l’esportazione dei dati supporta una serie di casi d’uso. Ogni caso d’uso è diverso in termini di dati richiesti e di modalità di accesso ed esportazione di tali dati. Experience Platform e Customer Journey Analytics forniscono una serie di funzionalità che, indipendentemente o in combinazione, possono risolvere i vari casi d’uso. La tabella seguente fornisce una panoramica dei casi d’uso identificati per l’esportazione dei dati e delle funzionalità di Experience Platform e Customer Journey Analytics per implementare questi casi d’uso.

| Casi d’uso per l’esportazione di dati | Funzionalità Experience Platform e Customer Journey Analytics |
|---|---|
| **Backup dei dati**<br/> Conservare una copia completa dei dati digitali per scopi di conformità o normativi. | **Experience Platform**: [**Esportare i set di dati**](export-datasets.md)<br/> Esporta i dati raccolti in Experienci Platform direttamente nelle destinazioni cloud secondo una pianificazione o ad hoc.<br/>*Al momento la versione limitata, la versione completa per i clienti di Customer Journey Analytics è prevista per giugno 2024.* |
| **Convalida dei dati**<br/> Valuta i dati clickstream per una raccolta accurata dei dati. | **Experience Platform**: [**Servizio query (Data Distiller) ed esporta set di dati**](queryservice-export-datasets.md)<br/> Interfaccia interattiva PostgreSQL per eseguire query SQL ad hoc utilizzando lo strumento SQL preferito per convalidare i dati nei set di dati.<br/><br/>**Customer Journey Analytics**: [**Esporta tabella completa**](export-full-table.md)<br/> Convalida i dati elaborati da CJA con attribuzione e sessionizzazione applicate. |
| **Strumenti Data Lake, Data Warehouse o BI**<br/> Inserisci dati digitali nei tuoi strumenti di business intelligence o nel Data Lake per utilizzarli con set di dati aggiuntivi. | **Customer Journey Analytics**: [**Estensione BI**](bi-extension.md)<br/> Aggiungere metriche elaborate dal Customer Journey Analytics a strumenti di visualizzazione dei dati come Power BI e combinarle con dati aggiuntivi per rapporti personalizzati <br/><br/>**Experience Platform**: [**Servizio query (Data Distiller) ed esporta set di dati**](queryservice-export-datasets.md)<br> Genera dati clickstream personalizzati utilizzando SQL da consegnare alle destinazioni cloud. |
| **Preparazione per IA/ML**<br/> Migliora i modelli e le attività di intelligenza artificiale/apprendimento automatico con i dati di Customer Journey Analytics. | **Customer Journey Analytics**: [**Esporta tabella completa**](export-full-table.md)<br/> Esporta metriche e dimensioni elaborate dal Customer Journey Analytics in destinazioni cloud una tantum o ricorrenti, incluse metriche calcolate e segmentazione.<br/><br/>**Experience Platform**: [**Servizio query (Data Distiller) ed esporta set di dati**](queryservice-export-datasets.md)<br/> Genera dati clickstream personalizzati utilizzando SQL per arricchire modelli AI/ML. |
