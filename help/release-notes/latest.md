---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: aa7f4361b1353a86b87c36c3d08e99ddb8ffd049
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 52%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (settembre 2023)

**Ultimo aggiornamento**: 13 settembre 2023

Queste note sulla versione coprono il periodo dal 13 settembre 2023 al 3 ottobre 2023. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzionalità | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Supporto per le classificazioni A4T nel connettore di origine di Analytics** | Il campo `_experience.decisioning.propositions.scopeDetails.correlationID` è ora disponibile nello schema del connettore sorgente di Adobe Analytics. Questo campo viene utilizzato a supporto delle classificazioni A4T e verrà popolato a partire da settembre 2023. | | N/D | 12 settembre 2023 |
| **Aggiornamenti ai campi derivati** | Sono stati apportati i seguenti aggiornamenti alla funzionalità dei campi derivati:<ul><li>Il [!UICONTROL Lookup] la funzione è stata rinominata in [!UICONTROL Classify], con opzioni aggiuntive per caricare i dati CSV. **(Versione del 27 settembre 2023)**</li><li>Sono disponibili funzioni aggiuntive da utilizzare per la definizione di un campo derivato: [!UICONTROL Trim], [!UICONTROL Lowercase] e [!UICONTROL Lookup].</li><li>Le definizioni dei campi derivate ora supportano anche i campi da [!UICONTROL Lookup] e [!UICONTROL Profile] set di dati.</li></ul>[Ulteriori informazioni](/help/data-views/derived-fields/derived-fields.md) | N/D | 13 settembre 2023 |
| **Nuove funzioni di Adobe Product Analytics** | <ul><li>**Rilevamento delle anomalie**: confronta gli eventi con i valori previsti derivati dalle tendenze storiche. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/usage.html)</li><li>**Tendenze Visualizzazione frequenza d&#39;uso**: misura l’adozione delle funzioni in base alla frequenza di utilizzo. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/frequency.html)</li><li>**Preferenze utente**: configura diverse preferenze utente, ad esempio palette di colori e formato dei numeri. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=it)</li></ul> | N/D | 18 settembre 2023 |
| **Ricerche per dispositivi Experience Edge** | Abilita la raccolta dati automatica dei tipi di dispositivo tramite la rete Edge Experienci Platform. Questo servizio Experience Edge offre vantaggi al Customer Journey Analytics insieme ad altre app di Experience Platform. (Segui il link alla documentazione) | N/D | 27 settembre 2023 |
| **Sono disponibili nuove colonne per la gestione dei componenti** | Le seguenti nuove colonne sono ora disponibili nel [Gestione metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-manager.md) e [Gestione filtri](/help/components/filters/manage-filters.md) durante la gestione dei componenti:<ul><li>Utilizzato in</li><li>Ultimo utilizzo</li></ul><p>Queste informazioni possono essere utili per determinare se un componente è utile per gli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato. Puoi utilizzare il dizionario dati insieme a queste informazioni per tenere traccia di come vengono utilizzati i componenti nell’organizzazione e per comprenderne meglio il funzionamento.</p> | 20 settembre 2023 | 4 ottobre 2023 |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-310972; AN-319509; AN-322245; AN-323411; AN-323719; AN-326101; AN-326125; AN-326888


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
