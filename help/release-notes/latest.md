---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f02cda499b2050cd238ca2352237ae2cc9a502d6
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 62%

---

# Note sulla versione corrente di Customer Journey Analytics (CJA) (giugno 2023)

**Ultimo aggiornamento**: 6 giugno 2023

I rilasci di Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Punti salienti della versione {#highlights}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Didascalie intelligenti** | Arricchisci la narrazione per gli utenti con riepiloghi in lingua naturale di una [!UICONTROL Line] visualizzazione. [Ulteriori informazioni](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 maggio 2023 | 1 giugno 2023 |
| **Condivisione dei collegamenti per i progetti (accesso non richiesto)** | Ora puoi condividere collegamenti di sola lettura per i progetti Analysis Workspace con chi non ha accesso ad Adobe Analytics. Ad esempio, puoi condividerli con persone esterne all’organizzazione o con persone all’interno dell’organizzazione che non dispongono del provisioning per Adobe Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=it#share-public-link) <p>Questa funzionalità è abilitata per impostazione predefinita e può essere disabilitata dall’amministratore di sistema. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=it#company-preferences)</p> | 3 maggio 2023 | 6 giugno 2023 |
| **Campi derivati** | Questo è il primo rilascio della funzionalità Campi derivati. Un campo derivato consente di definire al volo manipolazioni (spesso complesse) dei dati tramite un generatore di regole personalizzabile. Puoi definire ulteriormente il campo derivato come un componente (metrica o dimensione) nelle visualizzazioni Dati e quindi utilizzare il campo derivato come componente in Workspace.<p>Questa versione supporta un modello di canali di marketing e le seguenti funzioni:</p><ul><li>Concatena</li><li>Case When</li><li>Trova e sostituisci</li><li>Ricerca</li><li>Parsing URL</li></ul> <p>[Ulteriori informazioni](/help/data-views/derived-fields/derived-fields.md)</p> | 10 maggio 2023 | 21 giugno 2023 |
| **Accesso di Power BI e Tableau alle visualizzazioni dati di CJA** | Il connettore SQL di Customer Journey Analytics (CJA) consente l’accesso SQL alle visualizzazioni dati definite in CJA. I data engineer e gli analisti che hanno più familiarità con Power BI, Tableau o altri strumenti di business intelligence e visualizzazione possono ora creare rapporti e dashboard basati sulle stesse visualizzazioni dati utilizzate dagli utenti CJA per i loro progetti Analysis Workspace. [Ulteriori informazioni](/help/data-views/sql-connector.md) |  | 30 giugno 2023 |
| **Ricerche geografiche di Experience Edge** | Una volta abilitate le ricerche geografiche di Experience Edge per lo stream di dati, potrai creare rapporti utilizzando i dati di geolocalizzazione in CJA. |  | 30 giugno 2023 |
| **Supporto esteso della ricerca ai dati di profilo e di ricerca** | Potrai aggiungere set di dati di ricerca non solo a set di dati evento, ma anche a set di dati di profilo e di ricerca. | 21 giugno 2023 | 12 luglio 2023 |
| **Supporto per la conversione di valuta** | CJA supporterà la conversione della valuta come parte della formattazione di un componente metrico in una visualizzazione dati. | 21 giugno 2023 | 19 luglio 2023 |

{style="table-layout:auto"}

## Altre nuove funzioni o aggiornamenti {#other-new}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Visualizzazioni dati di Adobe Journey Optimizer** | Gli amministratori CJA hanno accesso ad alcune visualizzazioni dati aggiuntive in CJA, denominate &quot;Visualizzazione dati AJO (nome-sandbox)&quot;. Queste visualizzazioni dati vengono utilizzate per alimentare i rapporti in Adobe Journey Optimizer (AJO). Possono inoltre essere utilizzati per eseguire analisi più approfondite delle attività AJO in CJA. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html). | | 25 maggio 2023 |
| **Retrocompilazione per sandbox non di produzione** | Quando crei un flusso di dati del connettore di origine di Analytics in una sandbox non di produzione, la retrocompilazione nelle sandbox non di produzione sarà limitata a 3 mesi. Per le sandbox di produzione resterà invece a 13 mesi. | N/D | 26 aprile 2023 |
| **Condivisione dei collegamenti per i progetti (accesso non richiesto)** | Ora puoi condividere collegamenti di sola lettura per i progetti Analysis Workspace con chi non ha accesso ad Adobe Analytics. Ad esempio, puoi condividerli con persone esterne all’organizzazione o con persone all’interno dell’organizzazione che non dispongono del provisioning per Adobe Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=it#share-public-link) <p>Questa funzionalità è abilitata per impostazione predefinita e può essere disabilitata dall’amministratore di sistema. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 3 maggio 2023 | 6 giugno 2023 |
| **Schermata Home aggiornata per l’app delle dashboard di Analytics (app mobile)** | La nuova schermata Home aggiornata consente di visualizzare tutte le scorecard in un unico elenco di scorecard consolidato.  Se hai accesso a più organizzazioni con un solo login, tutte le scorecard delle organizzazioni saranno disponibili in un unico elenco. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | N/D | 10 maggio 2023 |
| **Campi derivati** | Questo è il primo rilascio della funzionalità Campi derivati. Un campo derivato consente di definire al volo manipolazioni (spesso complesse) dei dati tramite un generatore di regole personalizzabile. Puoi definire ulteriormente il campo derivato come un componente (metrica o dimensione) nelle visualizzazioni Dati e quindi utilizzare il campo derivato come componente in Workspace.<p>Questa versione supporta un modello di canali di marketing e le seguenti funzioni:</p><ul><li>Concatena</li><li>Case When</li><li>Trova e sostituisci</li><li>Ricerca</li><li>Parsing URL</li></ul> <p>[Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html?lang=it)</p> | 10 maggio 2023 | 2 agosto 2023 |
| **Report Builder per CJA: selezione della visualizzazione dati da una cella** | Questa funzione consente agli utenti di selezionare la visualizzazione dati per un blocco di dati da una cella. Si tratta di un’opzione utile se si crea una cartella di lavoro e si dispone di più visualizzazioni dati con struttura dati simile e si desidera poter riutilizzare una cartella di lavoro più volte con diverse visualizzazioni dati. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=it) | N/D | 24 maggio 2023 |
| **È stata aggiornata la pagina Apprendimento per CJA** | La scheda Apprendimento nella pagina di destinazione del Customer Journey Analytics ora contiene contenuti specifici per CJA, inclusi contenuti incentrati sulla transizione da Adobe Analytics a CJA.<p>Nella scheda Apprendimento sono disponibili anche i seguenti miglioramenti aggiuntivi:</p><ul><li>Design migliorato che mostra più contenuti di apprendimento in una singola pagina con una navigazione migliorata</li><li>Possibilità di personalizzare i contenuti di apprendimento per livello di esperienza (principiante, intermedio e avanzato)</li></ul><p>In precedenza, la scheda Apprendimento in CJA conteneva informazioni identiche a quelle della scheda Apprendimento in Adobe Analytics.</p> [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | N/D | 30 giugno 2023 |
| **Ordinare i componenti in Analysis Workspace** | <p>È ora disponibile una nuova opzione Ordina quando si visualizzano i componenti nella barra a sinistra o nel dizionario dei dati in Analysis Workspace. I componenti possono essere elencati a partire da quelli consigliati (utilizzati più spesso), in ordine alfabetico oppure per categoria (o tipo).</p><p>In precedenza era possibile solo cercare o filtrare i componenti. [Ulteriori informazioni](/help/components/overview.md)</p> | N/D | Da definire |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-318343; AN-319453

## Avvisi importanti per amministratori CJA

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| N/D | N/D | N/D |

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server AdobeIO OAuth** | 11 maggio 2023 | I clienti Adobe Analytics API, CJA API e Livestream che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server di AdobeIO OAuth entro il **1 gennaio 2025**. AdobeIO non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale da server a server OAuth o migrare le credenziali JWT esistenti a una credenziale da server a server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## Risorse correlate

* [Note sulle versione precedente di CJA per il 2023](/help/release-notes/2023.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
