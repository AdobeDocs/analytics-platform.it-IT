---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente del Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: daf41a2aefeebe6339b4f86cc04c071b57887ce3
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 40%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (luglio 2023)

**Ultimo aggiornamento**: 10 luglio 2023

Le versioni di Adobe Customer Journey Analytics funzionano su [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analytics è un nuovo modo di interagire con i dati e le informazioni cross-channel nel Customer Journey Analytics. Queste nuove funzionalità consentono ai team di prodotto di gestire in autonomia dati e insight sulla loro esperienza di prodotto attraverso flussi di lavoro di analisi guidati. I team possono:<ul><li>Comprendere i pattern di coinvolgimento degli utenti nel tempo</li><li>Monitora la crescita e il mantenimento della base di utenti del prodotto&#x200B;</li><li>Identificare le aree di attrito nel prodotto</li><li>Misura l’impatto delle versioni di funzioni &#x200B; primo utilizzo</li><li>Scopri segmenti significativi di utenti che desiderano interagire con il prodotto e svilupparlo durante tutto il loro percorso lavorativo&#x200B;</li><li>Connessione ad Analysis Workspace per analisi più approfondite e collaborazione con gli analisti</li></ul>L’Adobe Product Analytics è un componente aggiuntivo a pagamento per il Customer Journey Analytics. Se desideri ottenere il provisioning della tua organizzazione per utilizzare questa funzione, contatta il team del tuo account Adobe. [Ulteriori informazioni](/help/guided-analysis/overview.md) | N/D | 17 luglio 2023 |
| **Campi derivati** | Questo è il primo rilascio della funzionalità Campi derivati. Un campo derivato consente di definire al volo manipolazioni (spesso complesse) dei dati tramite un generatore di regole personalizzabile. Puoi definire ulteriormente il campo derivato come componente (metrica o dimensione) nelle visualizzazioni dati, quindi utilizzare il campo derivato come componente in Workspace.<p>Questa versione supporta un modello di canali di marketing e le seguenti funzioni:</p><ul><li>Concatena</li><li>Case When</li><li>Trova e sostituisci</li><li>Ricerca</li><li>Parsing URL</li></ul> <p>[Ulteriori informazioni](/help/data-views/derived-fields/derived-fields.md)</p> | 10 maggio 2023 | 2 agosto 2023 |
| **Supporto esteso della ricerca per i dati di profilo e di ricerca** | Consente di aggiungere set di dati come ricerche di campi all’interno di set di dati Profilo o Ricerca. In precedenza, erano supportati solo i set di dati evento. [Ulteriori informazioni] | 21 giugno 2023 | 12 luglio 2023 |
| **Miglioramenti al Report Builder** | <ul><li>Filtra da cella per più blocchi di dati. Puoi modificare i filtri su più blocchi di dati da una cella. Utilizza una cella predefinita, assegnala a più blocchi di dati e aggiorna i dati in base ai filtri definiti nella cella. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=en)</li><li>Mostrare e nascondere le intestazioni di riga e di colonna. Puoi mostrare o nascondere le intestazioni delle tabelle dei blocchi di dati o le intestazioni di riga e colonna per riformattare la tabella e allineare i blocchi di dati in un rapporto. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=en#build-the-data-block)</li></ul> | N/D | 19 luglio 2023 |
| **Ricerche geografiche di Experience Edge** | Adobe Experience Edge sta aggiungendo un servizio di ricerca geografica che fornisce dati geografici unificati a tutti gli utenti Experience Edge (Adobe Analytics, Customer Journey Analytics, Adobe Target, Adobe Medium Analytics, Adobe Experience Platform, ecc.). | N/D | 26 luglio 2023 |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-317971; AN-319234; AN-320439; AN-320519; AN-321740; AN-322444; AN-323116

## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| **Modifiche al modo in cui il Customer Journey Analytics elabora i dati** | 22 giugno 2023 | Di recente abbiamo modificato il modo in cui i dati vengono elaborati nel Customer Journey Analytics.<ul><li>Viene inviato in streaming qualsiasi dato evento con una marca temporale precedente a 24 ore.</li><li>Qualsiasi dato evento con una marca temporale più vecchia di 24 ore (anche se si trova nello stesso batch dei dati più recenti) viene considerato come backfill e verrà acquisito con una priorità inferiore.</li></ul> |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL)

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server AdobeIO OAuth** | 11 maggio 2023 | I clienti Adobe Analytics API, Customer Journey Analytics API e Livestream che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server di AdobeIO OAuth tramite **1 gennaio 2025**. AdobeIO non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Risorse correlate

* [Note sulle versioni del Customer Journey Analytics precedente per il 2023](/help/release-notes/2023.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
