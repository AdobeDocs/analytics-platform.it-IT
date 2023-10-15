---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 57124124254f5ca9eb2a9f63a7478cd288c19b0e
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 38%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (ottobre 2023)

**Ultimo aggiornamento**: 13 ottobre 2023

Queste note sulla versione coprono il periodo dal 4 ottobre 2023 al 24 ottobre 2023. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzionalità | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Esporta tabelle complete nel cloud** | L’esportazione di tabelle intere di Customer Journey Analytics consente di esportare milioni di righe di Workspace in destinazioni cloud. <p>L’esportazione di tabelle complete offre la consegna una tantum o pianificata di tabelle di dati progettate in Workspace con supporto per fino a cinque raggruppamenti, cinque metriche, filtri e metriche calcolate, il tutto in una tabella concatenata. È l’evoluzione dei rapporti Data Warehouse in Adobe Analytics, con molte nuove funzioni, spesso richieste, che oggi non sono disponibili in Data Warehouse.</p><p> Le opzioni di esportazione cloud includono:</p><ul><li>Area di destinazione dati Adobe Experience Platform</li><li>ARN per ruolo Amazon S3</li><li>Piattaforma Google Cloud</li><li>SAS di Azure</li><li>RBAC di Azure</li><li>Snowflake</li></ul>Per ulteriori informazioni, consulta [Esportare i rapporti di Customer Journey Analytics nel cloud](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html). | 4 ottobre 2023 | 19 ottobre 2023 |
| **Sono disponibili nuove colonne per la gestione dei componenti** | Le seguenti nuove colonne sono ora disponibili nel [Gestione metriche calcolate](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html) e [Gestione filtri](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html) durante la gestione dei componenti:<ul><li>Utilizzato in</li><li>Ultimo utilizzo</li></ul>Queste informazioni possono essere utili per determinare se un componente è utile per gli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato. Puoi utilizzare il dizionario dati insieme a queste informazioni per tenere traccia di come vengono utilizzati i componenti nell’organizzazione e per comprenderne meglio il funzionamento. | 23 settembre 2023 | 4 ottobre 2023 |
| **Migra al Customer Journey Analytics i progetti Adobe Analytics ed eventuali componenti inclusi** | Ora puoi migrare i progetti Adobe Analytics al Customer Journey Analytics. Questo processo semplifica la transizione da Adobe Analytics a Customer Journey Analytics. <p>Quando esegui la migrazione dei progetti al Customer Journey Analytics, le risorse vengono mappate da una suite di rapporti di Adobe Analytics a una visualizzazione dati del Customer Journey Analytics.</p> <p>Esegui la migrazione dei progetti al Customer Journey Analytics dall’interfaccia di Adobe Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)</p> | N/D | 9 ottobre 2023 |
| **Adobe Product Analytics: Mostra/Nascondi serie** | Fai clic sulla legenda del grafico o sulle righe della tabella per controllare la visibilità delle serie nelle visualizzazioni.  [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/overview.html?lang=en) | N/D | 4 ottobre 2023 |
| **Annotazioni nell’Adobe Product Analytics** | L’analisi guidata ora supporta la possibilità di visualizzare le annotazioni create nel Customer Journey Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/annotations/overview.html?lang=en) | N/D | 4 ottobre 2023 |
| **Reporting Activity Manager** | Reporting Activity Manager consente di visualizzare la capacità di reporting per ogni connessione nell’organizzazione. Offre agli amministratori una visibilità dettagliata sul consumo di reporting per diagnosticare e risolvere facilmente i problemi di capacità durante i periodi in cui si verificano picchi di reporting. Le funzionalità principali di Reporting Activity Manager includono:<ul><li>Annullare le richieste di reporting correnti (comprese le richieste da analisi guidate ed esportazioni di tabelle complete)</li><li>Limita le richieste successive per un periodo di tempo definito</li></ul>Oltre ad annullare le richieste correnti, gli amministratori possono ora limitare le richieste per un periodo di tempo definito. Gli amministratori possono limitare le richieste in base a richieste, progetti o utenti.  [Ulteriori informazioni](/help/reporting-activity-manager/reporting-activity-overview.md) | 17 ottobre 2023 | 23 ottobre 2023 |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-325940; AN-326468; AN-328301; AN-328640; AN-329370

## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| N/D | N/D | N/D |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL)

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | 11 maggio 2023 | I clienti API di Adobe Analytics, API di Customer Journey Analytics e Livestream che utilizzano le credenziali JWT di Adobe I/O devono effettuare la migrazione alle credenziali server-to-server OAuth di Adobe I/O entro il **1° gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1 maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2023](/help/release-notes/2023.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
