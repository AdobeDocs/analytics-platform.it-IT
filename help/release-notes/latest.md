---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 8f299dad39678047d362291cfe8a2a3c116071dd
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 78%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (agosto 2023)

**Ultimo aggiornamento**: 24 agosto 2023

Queste note sulla versione coprono il periodo dal 9 agosto al 13 settembre 2023. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Miglioramenti a Report Builder** | <ul><li>È possibile scaricare un&#39;attività pianificata dalla scheda Cartelle di lavoro, assegnarle un titolo, salvarla e condividerla. [Ulteriori informazioni](/help/report-builder/schedule-reportbuilder.md)</li><li>Data di inizio come dimensione consente di rendere visibile la data di inizio del blocco di dati come dimensione nell’output del blocco di dati. [Ulteriori informazioni](/help/report-builder/create-a-data-block.md) </li></ul> | N/D | 17 agosto 2023 |
| **Conversione valuta** | Il Percorso di clienti sta aggiungendo la possibilità di supportare più valute. È possibile convertire una valuta in un’altra valuta nelle impostazioni delle visualizzazioni dati. [Ulteriori informazioni](/help/data-views/component-settings/format.md) | N/D | 30 agosto 2023 |
| **Supporto per le classificazioni A4T nel connettore di origine di Analytics** | Stiamo aggiungendo un ID di correlazione per unire facilmente i dati di classificazione per le attività e gli eventi di esperienza di Adobe Target. | N/D | 11 settembre 2023 |
| **Reporting Activity Manager** | Fornisce agli amministratori una visibilità dettagliata del consumo di reporting per ogni connessione, consentendo agli amministratori di diagnosticare e risolvere facilmente i problemi di capacità durante i periodi in cui si verificano picchi di reporting. | N/D | 12 settembre 2023 |
| **Accesso di Power BI e Tableau alle visualizzazioni dati di Customer Journey Analytics** | Il connettore SQL di Adobe Customer Journey Analytics consente l’accesso SQL alle visualizzazioni dati definite in Customer Journey Analytics. I tecnici dei dati e gli analisti che hanno più familiarità con Power BI, Tableau o altri strumenti di business intelligence e visualizzazione possono ora creare rapporti e dashboard basati sulle stesse visualizzazioni dati utilizzate dagli utenti di Customer Journey Analytics per i loro progetti Analysis Workspace. [Ulteriori informazioni](/help/data-views/sql-connector.md) | N/D | 12 settembre 2023 |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-309141; AN-319198; AN-324576; AN-324939; AN-325138; AN-325554

## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| **Modifiche al modo in cui Customer Journey Analytics elabora i dati** | 22 giugno 2023 | Di recente abbiamo modificato il modo in cui i dati vengono elaborati in Customer Journey Analytics.<ul><li>Viene inviato in streaming qualsiasi dato evento con una marca temporale di non più di 24 ore.</li><li>Qualsiasi dato evento con una marca temporale antecedente alle 24 ore (anche se si trova nello stesso batch dei dati più recenti) viene considerato come retrocompilazione e verrà acquisito con una priorità inferiore.</li></ul> |

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
