---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente del Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 2a1f97a9a454c11e0c006579e8f550bda55d47db
workflow-type: tm+mt
source-wordcount: '1433'
ht-degree: 67%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (giugno 2023)

**Ultimo aggiornamento**: 22 giugno 2023

Le versioni di Adobe Customer Journey Analytics funzionano su [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Punti salienti della versione {#highlights}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Aggiornamenti alla documentazione di analisi e unione cross-channel** | In previsione delle modifiche imminenti per abilitare le unioni e per chiarire ulteriormente come l’analisi cross-channel può essere elevata utilizzando le unioni, la documentazione relativa alla funzionalità Cross-Channel Analytics viene modificata per fare riferimento a [analisi cross-channel](../use-cases/cross-channel/cross-channel.md) come capacità di Customer Journey Analytics e caso d’uso, e [Stitching](../stitching/overview.md) come funzionalità importante per eseguire questa operazione. | 28 giugno 2023 | 28 giugno 2023 |
| **Didascalie intelligenti** | Arricchisci la presentazione dei dati fornendo agli utenti riepiloghi in linguaggio naturale nella visualizzazione [!UICONTROL Line]. [Ulteriori informazioni](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 maggio 2023 | 1 giugno 2023 |
| **Condivisione dei collegamenti per i progetti (accesso non richiesto)** | Ora puoi condividere collegamenti di sola lettura per i progetti Analysis Workspace con chi non ha accesso ad Adobe Analytics. Ad esempio, puoi condividerli con persone esterne all’organizzazione o con persone all’interno dell’organizzazione che non dispongono del provisioning per Adobe Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=it#share-public-link) <p>Questa funzionalità è abilitata per impostazione predefinita e può essere disabilitata dall’amministratore di sistema. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=it#company-preferences)</p> | 3 maggio 2023 | 6 giugno 2023 |
| **Campi derivati** | Questo è il primo rilascio della funzionalità Campi derivati. Un campo derivato consente di definire al volo manipolazioni (spesso complesse) dei dati tramite un generatore di regole personalizzabile. Puoi definire ulteriormente il campo derivato come componente (metrica o dimensione) nelle visualizzazioni dati, quindi utilizzare il campo derivato come componente in Workspace.<p>Questa versione supporta un modello di canali di marketing e le seguenti funzioni:</p><ul><li>Concatena</li><li>Case When</li><li>Trova e sostituisci</li><li>Ricerca</li><li>Parsing URL</li></ul> <p>[Ulteriori informazioni](/help/data-views/derived-fields/derived-fields.md)</p> | 10 maggio 2023 | 14 giugno 2023 |
| **Supporto conversione valuta** | La conversione della valuta è supportata come parte della formattazione di un componente metrico in una visualizzazione dati. [Ulteriori informazioni](../data-views/component-settings/format.md#currency) | 7 giugno 2023 | 21 giugno 2023 |
| **Accesso di Power BI e Tableau alle visualizzazioni dati del Customer Journey Analytics** | Il connettore SQL di Adobe Customer Journey Analytics consente l&#39;accesso SQL alle visualizzazioni dati definite nel Customer Journey Analytics. I data engineer e gli analisti che hanno più familiarità con Power BI, Tableau o altri strumenti di business intelligence e visualizzazione possono ora creare rapporti e dashboard basati sulle stesse visualizzazioni dati utilizzate dagli utenti del Customer Journey Analytics per i loro progetti Analysis Workspace. [Ulteriori informazioni](/help/data-views/sql-connector.md) |  | 30 giugno 2023 |
| **Supporto esteso della ricerca ai dati di profilo e di ricerca** | Potrai aggiungere set di dati di ricerca non solo a set di dati evento, ma anche a set di dati di profilo e di ricerca. | 28 giugno 2023 | 12 luglio 2023 |
| **Ricerche geografiche di Experience Edge** | Una volta abilitate le ricerche geografiche di Adobe Experience Edge per lo stream di dati, potrai creare rapporti utilizzando i dati di geolocalizzazione nel Customer Journey Analytics. |  | 26 luglio 2023 |

{style="table-layout:auto"}

## Altre nuove funzioni o aggiornamenti {#other-new}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Visualizzazioni dati di Adobe Journey Optimizer** | Gli amministratori di Customer Journey Analytics hanno accesso ad alcune visualizzazioni di dati aggiuntive nel Customer Journey Analytics, denominate &quot;Visualizzazione dati AJO (nome-sandbox)&quot;. Queste visualizzazioni dati vengono utilizzate per alimentare i rapporti in Adobe Journey Optimizer. Possono inoltre essere utilizzati per eseguire analisi più approfondite delle attività di Adobe Journey Optimizer nel Customer Journey Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html?lang=it). | | 25 maggio 2023 |
| **Retrocompilazione per sandbox non di produzione** | Quando crei un flusso di dati del connettore di origine di Analytics in una sandbox non di produzione, la retrocompilazione nelle sandbox non di produzione sarà limitata a 3 mesi. Per le sandbox di produzione resterà invece a 13 mesi. | N/D | 26 aprile 2023 |
| **Condivisione dei collegamenti per i progetti (accesso non richiesto)** | Ora puoi condividere collegamenti di sola lettura per i progetti Analysis Workspace con chi non ha accesso ad Adobe Analytics. Ad esempio, puoi condividerli con persone esterne all’organizzazione o con persone all’interno dell’organizzazione che non dispongono del provisioning per Adobe Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=it#share-public-link) <p>Questa funzionalità è abilitata per impostazione predefinita e può essere disabilitata dall’amministratore di sistema. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=it#ims-organization-preferences)</p> | 3 maggio 2023 | 6 giugno 2023 |
| **Schermata Home aggiornata per l’app delle dashboard di Analytics (app mobile)** | La nuova schermata Home aggiornata consente di visualizzare tutte le scorecard in un unico elenco di scorecard consolidato.  Se hai accesso a più organizzazioni con un solo login, tutte le scorecard delle organizzazioni saranno disponibili in un unico elenco. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html?lang=it#use-dashboards) | N/D | 10 maggio 2023 |
| **Report Builder per Customer Journey Analytics - Seleziona visualizzazione dati dalla cella** | Questa funzione consente agli utenti di selezionare la visualizzazione dati per un blocco di dati da una cella. Si tratta di un’opzione utile se si crea una cartella di lavoro e si dispone di più visualizzazioni dati con struttura dati simile e si desidera poter riutilizzare una cartella di lavoro più volte con diverse visualizzazioni dati. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=it) | N/D | 24 maggio 2023 |
| **Pagina di apprendimento aggiornata per il Customer Journey Analytics** | La scheda Apprendimento nella pagina di destinazione del Customer Journey Analytics ora contiene contenuti specifici per il Customer Journey Analytics, inclusi contenuti incentrati sulla transizione al Customer Journey Analytics da Adobe Analytics.<p>Nella scheda Apprendimento sono disponibili anche i seguenti miglioramenti aggiuntivi:</p><ul><li>Design migliorato che mostra più contenuti di apprendimento in una singola pagina con una navigazione ottimizzata</li><li>Possibilità di personalizzare i contenuti di apprendimento per livello di esperienza (principiante, intermedio e avanzato)</li></ul><p>In precedenza, la scheda Apprendimento nel Customer Journey Analytics conteneva informazioni identiche a quelle della scheda Apprendimento in Adobe Analytics.</p> [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | 27 giugno 2023 | 30 giugno 2023 |
| **Ordinare i componenti in Analysis Workspace** | <p>È ora disponibile una nuova opzione Ordina quando si visualizzano i componenti nella barra a sinistra o nel dizionario dei dati in Analysis Workspace. I componenti possono essere elencati a partire da quelli consigliati (utilizzati più spesso), in ordine alfabetico oppure per categoria (o tipo).</p><p>In precedenza era possibile solo cercare o filtrare i componenti. [Ulteriori informazioni](/help/components/overview.md)</p> | N/D | 7 giugno 2023 |
| **Eliminare righe contenenti dimensioni dinamiche da una tabella a forma libera** | In una tabella a forma libera di Analysis Workspace, ora è possibile utilizzare l’icona X per eliminare rapidamente righe specifiche contenenti dimensioni dinamiche. In questo modo, viene applicata automaticamente una regola di filtro “Escludi sempre gli elementi”.<p>In precedenza, per eliminare le righe contenenti dimensioni dinamiche era necessario creare manualmente una regola nella finestra di dialogo Filtro. [Ulteriori informazioni](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | N/D | 17 maggio 2023 |
| **Nuovo pulsante per aggiungere una visualizzazione all’interno di un pannello** | Nella parte inferiore di ciascun pannello di Analysis Workspace è ora disponibile un nuovo pulsante che consente di aggiungere rapidamente una visualizzazione. <p>In precedenza, per aggiungere una visualizzazione a un pannello eano disponibili solo i seguenti metodi: trascinare una visualizzazione dalla barra a sinistra, duplicare o copiare una visualizzazione esistente, oppure creare un pannello vuoto. [Ulteriori informazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | N/D | 17 maggio 2023 |
| **Deep Linking (app mobile)** | Consente agli utenti di inviare collegamenti alle scorecard che li porteranno direttamente al progetto della scorecard nell’app. Questo agevola ulteriormente la condivisione dei progetti e il coinvolgimento di un pubblico meno tecnico. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=it#share-scorecards-using-a-shareable-link) | N/D | 17 maggio 2023 |
| **Didascalie intelligenti** | Arricchisci la presentazione dei dati fornendo agli utenti riepiloghi in linguaggio naturale nella visualizzazione [!UICONTROL Line]. [Ulteriori informazioni](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 maggio 2023 | 1 giugno 2023 |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-318343; AN-319453

## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| Modifiche al modo in cui il Customer Journey Analytics elabora i dati | 22 giugno 2023 | Di recente abbiamo modificato il modo in cui i dati vengono elaborati nel Customer Journey Analytics.<ul><li>Viene inviato in streaming qualsiasi dato evento con una marca temporale precedente a 24 ore.</li><li>Qualsiasi dato evento con una marca temporale più vecchia di 24 ore (anche se si trova nello stesso batch dei dati più recenti) viene considerato come backfill e verrà acquisito con una priorità inferiore.</li></ul> |

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

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
