---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e55cd5d9da816b9413dba7542acb385f12709642
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 98%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics di Adobe (luglio 2023)

**Ultimo aggiornamento**: 13 luglio 2023

I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analytics è un nuovo modo di interagire con dati e approfondimenti cross-channel in Customer Journey Analytics. Queste nuove funzionalità consentono ai team di prodotto di gestire in autonomia dati e insight sulla loro esperienza di prodotto attraverso flussi di lavoro di analisi guidati. I team possono:<ul><li>Comprendere i pattern di coinvolgimento degli utenti nel tempo</li><li>Monitorare la crescita e il mantenimento della base utenti del prodotto</li><li>Identificare le aree di attrito nel prodotto</li><li>Misurare l’impatto del rilascio delle funzioni e il primo utilizzo</li><li>Scoprire segmenti significativi di utenti da coinvolgere e coltivare per tutto il percorso con il prodotto</li><li>Connettersi a Analysis Workspace per analisi più approfondite e collaborazione con gli analisti</li></ul>Adobe Product Analytics è un componente aggiuntivo a pagamento di Customer Journey Analytics. Contatta il team Adobe Account per effettuare il provisioning di questa funzione per la tua organizzazione. [Ulteriori informazioni](/help/guided-analysis/overview.md) | N/D | 17 luglio 2023 |
| **Campi derivati** | Questo è il primo rilascio della funzionalità Campi derivati. Un campo derivato consente di definire al volo manipolazioni (spesso complesse) dei dati tramite un generatore di regole personalizzabile. Puoi definire ulteriormente il campo derivato come un componente (metrica o dimensione) nelle visualizzazioni dati e quindi utilizzare il campo derivato come componente in Workspace.<p>Questa versione supporta un modello di canali di marketing e le seguenti funzioni:</p><ul><li>Concatena</li><li>Case When</li><li>Trova e sostituisci</li><li>Ricerca</li><li>Parsing URL</li></ul> <p>[Ulteriori informazioni](/help/data-views/derived-fields/derived-fields.md)</p> | 10 maggio 2023 | 2 agosto 2023 |
| **Supporto esteso della ricerca ai dati di profilo e di ricerca** | Consente di aggiungere set di dati come ricerche di campi all’interno di set di dati di profilo o di ricerca. In precedenza erano supportati solo i set di dati evento. [Ulteriori informazioni](/help/connections/create-connection.md) | 21 giugno 2023 | 12 luglio 2023 |
| **Miglioramenti a Report Builder** | <ul><li>Filtro per più blocchi di dati da cella. Puoi modificare i filtri su più blocchi di dati da una cella. Utilizza una cella predefinita, assegnala a più blocchi di dati e aggiorna i dati in base ai filtri definiti nella cella. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=it)</li><li>Mostra e nascondi le intestazioni di riga e colonna. Puoi mostrare o nascondere le intestazioni delle tabelle dei blocchi di dati o le intestazioni di riga e colonna per riformattare la tabella e allineare i blocchi di dati in un rapporto. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=it#build-the-data-block)</li></ul> | N/D | 19 luglio 2023 |
| **Ricerche geografiche di Experience Edge** | [Adobe Experience Edge sta aggiungendo un servizio di ricerca geografica che fornisce dati geografici unificati a tutti gli utenti Experience Edge (Adobe Analytics, Customer Journey Analytics, Adobe Target, Adobe Media Analytics, Adobe Experience Platform, ecc.).](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | N/D | 26 luglio 2023 |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-317971; AN-319234; AN-320439; AN-320519; AN-321740; AN-322444; AN-323116

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
