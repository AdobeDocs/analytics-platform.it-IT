---
title: Casi d’uso per l’esportazione di dati
description: Comprendere vari casi di utilizzo dell’esportazione di dati per il Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: 40e4c3bd8f3c37e9a6143200b85ffe0ac4bcb2ca
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 0%

---

# Casi d’uso per l’esportazione di dati

Questa sezione fornisce casi d’uso per l’esportazione di dati e come implementarli con una o più funzionalità di Customer Journey Analytics o Experience Platform. Ogni funzionalità è descritta in un articolo separato.

## Introduzione

Una delle differenze uniche tra Adobe Analytics e Customer Journey Analytics è relativa all’elaborazione dei dati per l’attribuzione e la sessionizzazione. Vedi [Confrontare l&#39;elaborazione dei dati in Adobe Analytics e Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) per ulteriori informazioni.

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

* L&#39;unione può _riprodurre_ dati ogni giorno o ogni settimana, associando eventi anonimi a eventi noti. Per ulteriori informazioni, vedere [Unione](../../stitching/overview.md).
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


## Casi d’uso e funzionalità

In generale, l’esportazione dei dati supporta una serie di casi d’uso. Ogni caso d’uso è diverso in termini di dati richiesti e di modalità di accesso ed esportazione di tali dati. Experience Platform e Customer Journey Analytics forniscono una serie di funzionalità che, indipendentemente o in combinazione, possono risolvere i vari casi d’uso. La tabella seguente fornisce una panoramica dei casi d’uso identificati per l’esportazione dei dati e delle funzionalità di Experience Platform e Customer Journey Analytics per implementare questi casi d’uso.

| Casi d’uso per l’esportazione di dati | Funzionalità Experience Platform e Customer Journey Analytics |
|---|---|
| **Backup dei dati**<br/> Conservare una copia completa dei dati digitali per motivi di conformità o normativi. | **Experience Platform**: [**Esporta i set di dati**](export-datasets.md)<br/> Esporta i dati raccolti in Experience Platform direttamente nelle destinazioni cloud secondo una pianificazione o ad hoc.<br/>*Versione attualmente limitata, la versione completa per i clienti di Customer Journey Analytics è prevista per giugno 2024.* |
| **Convalida dati**<br/> Valuta i dati clickstream per verificare la precisione della raccolta dati. | **Experience Platform**: [**Interfaccia PostgreSQL interattiva di Query Service (Data Distiller) ed esportazione di set di dati**](queryservice-export-datasets.md)<br/> per eseguire query SQL ad hoc utilizzando lo strumento SQL preferito per convalidare i dati nei set di dati.<br/><br/>**Customer Journey Analytics**: [**Esporta tabella completa**](export-full-table.md)<br/> Convalida i dati elaborati da CJA con attribuzione e sessionizzazione applicate. |
| **Strumenti Data Lake, Data Warehouse o BI**<br/> Inserisci dati digitali nei tuoi strumenti di business intelligence o Data Lake per utilizzarli con set di dati aggiuntivi. | **Customer Journey Analytics**: [**Estensione BI**](bi-extension.md)<br/> Aggiungi metriche elaborate dal Customer Journey Analytics agli strumenti di visualizzazione dei dati, ad esempio Power BI e combina con dati aggiuntivi per rapporti personalizzati <br/><br/>**Experience Platform**: [**Query Service (Data Distiller) ed esporta set di dati**](queryservice-export-datasets.md)<br> Genera dati clickstream personalizzati utilizzando SQL da consegnare alle destinazioni cloud. |
| **Preparazione per IA / ML**<br/> Migliorare i modelli e le attività di intelligenza artificiale/apprendimento automatico con i dati del Customer Journey Analytics. | **Customer Journey Analytics**: [**Esporta tabella completa**](export-full-table.md)<br/> Esporta dimensioni e metriche elaborate dal Customer Journey Analytics nelle destinazioni cloud una tantum o ricorrenti, incluse le metriche calcolate e la segmentazione.<br/><br/>**Experience Platform**: [**Query Service (Data Distiller) ed esporta set di dati**](queryservice-export-datasets.md)<br/> Genera dati clickstream personalizzati utilizzando SQL per arricchire modelli AI/ML. |
