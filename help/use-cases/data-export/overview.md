---
title: Casi d’uso per l’esportazione di dati
description: Comprendere vari casi di utilizzo per l’esportazione di dati per Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
TQID: https://experienceleague.adobe.com/ad4wWxqEZZxsnSTpus7pxFMlwNo3nNUpHeS9VfxrEdw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 1%
---
# Casi d’uso per l’esportazione di dati {#data-export-use-cases}

<!-- This contextual help is for the upgrade checklist -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds-step"
>title="Utilizzare funzioni di esportazione simili ai feed dati"
>abstract="Anche se una sostituzione esatta dei feed di dati non è ancora disponibile in Customer Journey Analytics, funzionalità simili sono disponibili tramite l’esportazione di tabelle complete, l’esportazione di set di dati di Platform, l’integrazione di strumenti BI e l’API di reporting."

<!-- markdownlint-enable MD034 -->

Questa sezione fornisce casi di utilizzo per l’esportazione di dati e come implementarli con una o più funzionalità di Customer Journey Analytics o Experience Platform. Ogni funzionalità è descritta in un articolo separato.

## Introduzione

Una delle differenze uniche tra Adobe Analytics e Customer Journey Analytics è relativa all’elaborazione dei dati per l’attribuzione e la sessionizzazione. Per ulteriori informazioni, vedere [Confrontare l&#39;elaborazione dei dati in Adobe Analytics e Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md).

### Adobe Analytics: attribuzione e sessionizzazione del tempo di raccolta.

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
* La sessionizzazione e i valori persistenti cambiano ogni volta
  * vengono raccolti nuovi dati o
  * l’unione di più aggiunge eventi alla cronologia di una persona.

L’elaborazione al momento del reporting influisce sull’esportazione di dati da Customer Journey Analytics. Le esportazioni che includono valori persistenti non corrispondono ai rapporti di Customer Journey Analytics e i valori divergono nel tempo.

Per coerenza metrica, è preferibile utilizzare le nuove funzioni di Customer Journey Analytics. In generale, la funzionalità di esportazione dei dati di Experience Platform e Customer Journey Analytics supera la funzionalità di feed dati di Adobe Analytics. Experience Platform e Customer Journey Analytics forniscono:

* nuove origini dati ed elaborazione soggette all’esportazione di dati

  * includere fonti di dati non digitali,
  * applicare l’attribuzione e la sessionizzazione personalizzate in base alle regole aziendali; e
  * aggiorna i percorsi dei clienti con l’unione.

* implementazione di casi d’uso personalizzati per l’esportazione di dati

  * esportare i dati dove sono necessari, inclusi gli strumenti di Business Intelligence (BI) e le destinazioni cloud,
  * mantenere i dati sincronizzati con Analysis Workspace tramite l’integrazione di strumenti di business intelligence,
  * non è necessario duplicare la logica di elaborazione nei propri sistemi,
  * nuovo supporto per metriche calcolate, campi derivati e segmentazione, e

* considerazione della sicurezza e della governance dei dati

  * monitorare tutte le esportazioni di dati per utente e destinazione,
  * fissare limiti ai dati disponibili per l&#39;esportazione e
  * imposta gli avvisi per i problemi di consegna e i limiti per le finestre di consegna pianificate.


## Casi d’uso e funzionalità

In generale, l’esportazione dei dati supporta una serie di casi d’uso. Ogni caso d’uso è diverso in termini di dati richiesti e di modalità di accesso ed esportazione di tali dati. Experience Platform e Customer Journey Analytics forniscono una serie di funzionalità che, in modo indipendente o combinato, possono risolvere i vari casi d’uso. La tabella seguente fornisce una panoramica dei casi d’uso identificati per l’esportazione dei dati e delle funzionalità di Experience Platform e Customer Journey Analytics per implementare questi casi d’uso.

| Casi d’uso per l’esportazione di dati | Funzionalità di Experience Platform e Customer Journey Analytics |
|---|---|
| **Backup dei dati**<br/> Conservare una copia completa dei dati digitali per motivi di conformità o normativi. | **Experience Platform**: [**Esporta i set di dati**](export-datasets.md)<br/> Esporta i dati raccolti in Experience Platform direttamente nelle destinazioni cloud secondo una pianificazione o ad hoc. |
| **Convalida dati**<br/> Valuta i dati clickstream per verificare la precisione della raccolta dati. | **Experience Platform**: [**Interfaccia PostgreSQL interattiva di Query Service (Data Distiller) ed esportazione di set di dati**](queryservice-export-datasets.md)<br/> per eseguire query SQL ad hoc utilizzando lo strumento SQL preferito per convalidare i dati nei set di dati.<br/><br/>**Customer Journey Analytics**: [**Esporta tabella completa**](export-full-table.md)<br/> Convalida i dati elaborati da CJA con attribuzione e sessionizzazione applicate. |
| **Strumenti Data Lake, Data Warehouse o BI**<br/> Inserisci dati digitali nei tuoi strumenti di business intelligence o Data Lake per utilizzarli con set di dati aggiuntivi. | **Customer Journey Analytics**: [**BI Extension**](bi-extension.md)<br/> Aggiungi metriche elaborate da Customer Journey Analytics a strumenti di visualizzazione dati come Power BI e combinale con dati aggiuntivi per rapporti personalizzati <br/><br/>**Experience Platform**: [**Query Service (Data Distiller) ed esporta set di dati**](queryservice-export-datasets.md)<br> Genera dati clickstream personalizzati utilizzando SQL da distribuire alle destinazioni cloud. |
| **Preparazione per IA / ML**<br/> Migliorare i modelli e le attività di intelligenza artificiale/apprendimento automatico con i dati di Customer Journey Analytics. | **Customer Journey Analytics**: [**Esporta tabella completa**](export-full-table.md)<br/> Esporta dimensioni e metriche elaborate da Customer Journey Analytics in destinazioni cloud una tantum o ricorrenti, incluse metriche calcolate e segmentazione.<br/><br/>**Experience Platform**: [**Query Service (Data Distiller) ed esporta set di dati**](queryservice-export-datasets.md)<br/> Genera dati clickstream personalizzati utilizzando SQL per arricchire modelli AI/ML. |
| **Generazione rapporti ad hoc e periodici**<br/> Accesso self-service di singoli utenti o team aziendali ai dati Customer Journey Analytics elaborati senza configurare una pipeline di dati. | **Customer Journey Analytics**: [**Esportazione Workspace**](workspace-export.md)<br/> Scarica o invia dati tramite e-mail direttamente da un progetto Analysis Workspace per analisi o condivisione occasionali.<br/><br/>**Customer Journey Analytics**: [**Report Builder**](report-builder.md)<br/> Estrai dati di Customer Journey Analytics nelle cartelle di lavoro di Excel per rapporti ricorrenti e di facile utilizzo da parte degli utenti aziendali. |
| **Integrazione dell&#39;applicazione personalizzata**<br/> Power dashboards, strumenti interni o flussi di lavoro automatizzati con dati Customer Journey Analytics. | **Customer Journey Analytics**: [**API di reporting**](reporting-api.md)<br/> Recupera i dati di Customer Journey Analytics a livello di programmazione per l&#39;integrazione con le tue applicazioni o automazione. |

## Scegli tra le funzionalità

Diverse funzionalità possono implementare lo stesso caso d’uso. Quando scegli tra di loro, considera:

* **Volume dati**: i metodi ad hoc, come [Esportazione Workspace](/help/use-cases/data-export/workspace-export.md) e [Report Builder](/help/use-cases/data-export/report-builder.md), sono limitati a decine di migliaia di righe. [Esporta tabella completa](/help/use-cases/data-export/export-full-table.md) e [Esporta set di dati](/help/use-cases/data-export/export-datasets.md) supportano milioni di righe.
* **Dati non elaborati rispetto a dati elaborati**: [Esporta set di dati](/help/use-cases/data-export/export-datasets.md) e [Query Service (Data Distiller) ed Esporta set di dati](/help/use-cases/data-export/queryservice-export-datasets.md) forniscono dati non elaborati dal data lake. [Estensione BI](/help/use-cases/data-export/bi-extension.md), [Esporta tabella completa](/help/use-cases/data-export/export-full-table.md), [Esportazione Workspace](/help/use-cases/data-export/workspace-export.md), [Report Builder](/help/use-cases/data-export/report-builder.md) e [API di reporting](/help/use-cases/data-export/reporting-api.md) forniscono dati già elaborati da Customer Journey Analytics, inclusi attribuzione, sessionizzazione e metriche calcolate.
* **Competenze tecniche**: [Query Service (Data Distiller) ed esporta set di dati](/help/use-cases/data-export/queryservice-export-datasets.md) e l&#39;estensione [BI](/help/use-cases/data-export/bi-extension.md) richiedono conoscenze SQL. [Esportazione Workspace](/help/use-cases/data-export/workspace-export.md) e [Report Builder](/help/use-cases/data-export/report-builder.md) utilizzano interfacce point-and-click. [API di reporting](/help/use-cases/data-export/reporting-api.md) richiede conoscenze di programmazione.
* **È necessario pianificare**: [Esporta set di dati](/help/use-cases/data-export/export-datasets.md), [Esporta tabella completa](/help/use-cases/data-export/export-full-table.md) e [Report Builder](/help/use-cases/data-export/report-builder.md) supportano la consegna ricorrente e pianificata. I download di [esportazione Workspace](/help/use-cases/data-export/workspace-export.md) sono solo ad hoc.
* **Formato e destinazione di output**: verificare se è necessario un file nell&#39;archiviazione cloud, una tabella in uno strumento BI, una cartella di lavoro in Excel o una risposta da una chiamata API, quindi verificare che la funzionalità fornita corrisponda a quella richiesta.
