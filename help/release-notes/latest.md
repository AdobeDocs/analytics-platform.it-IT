---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 503276813210215ffe96795ab934259153f13074
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 76%

---

# Note sulla versione corrente di Customer Journey Analytics (CJA) (maggio 2023)

**Ultimo aggiornamento**: 6 giugno 2023

I rilasci di Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni principali e aggiornamenti

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Visualizzazioni dati di Adobe Journey Optimizer** | Gli amministratori CJA hanno accesso ad alcune visualizzazioni dati aggiuntive in CJA, denominate &quot;Visualizzazione dati AJO (nome-sandbox)&quot;. Queste visualizzazioni dati vengono utilizzate per alimentare i rapporti in Adobe Journey Optimizer (AJO). Possono inoltre essere utilizzati per eseguire analisi più approfondite delle attività AJO in CJA. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html). |  | 25 maggio 2023 |
| **Retrocompilazione per sandbox non di produzione** | Quando crei un flusso di dati del connettore di origine di Analytics in una sandbox non di produzione, la retrocompilazione nelle sandbox non di produzione sarà limitata a 3 mesi. Per le sandbox di produzione resterà invece a 13 mesi. | N/D | 26 aprile 2023 |
| **Condivisione dei collegamenti per i progetti (accesso non richiesto)** | Ora puoi condividere collegamenti di sola lettura per i progetti Analysis Workspace con chi non ha accesso ad Adobe Analytics. Ad esempio, puoi condividerli con persone esterne all’organizzazione o con persone all’interno dell’organizzazione che non dispongono del provisioning per Adobe Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=it#share-public-link) <p>Questa funzionalità è abilitata per impostazione predefinita e può essere disabilitata dall’amministratore di sistema. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 3 maggio 2023 | 6 giugno 2023 |
| **Schermata Home aggiornata per l’app delle dashboard di Analytics (app mobile)** | La nuova schermata Home aggiornata consente di visualizzare tutte le scorecard in un unico elenco di scorecard consolidato.  Se hai accesso a più organizzazioni con un solo login, tutte le scorecard delle organizzazioni saranno disponibili in un unico elenco. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | N/D | 10 maggio 2023 |
| **Campi derivati** | Questo è il primo rilascio della funzionalità Campi derivati. Un campo derivato consente di definire al volo manipolazioni (spesso complesse) dei dati tramite un generatore di regole personalizzabile. Puoi definire ulteriormente il campo derivato come un componente (metrica o dimensione) nelle visualizzazioni Dati e quindi utilizzare il campo derivato come componente in Workspace.<p>Questa versione supporta un modello di canali di marketing e le seguenti funzioni:</p><ul><li>Concatena</li><li>Case When</li><li>Trova e sostituisci</li><li>Ricerca</li><li>Parsing URL</li></ul> <p>[Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html?lang=it)</p> | 10 maggio 2023 | 2 agosto 2023 |
| **Report Builder per CJA: selezione della visualizzazione dati da una cella** | Questa funzione consente agli utenti di selezionare la visualizzazione dati per un blocco di dati da una cella. Si tratta di un’opzione utile se si crea una cartella di lavoro e si dispone di più visualizzazioni dati con struttura dati simile e si desidera poter riutilizzare una cartella di lavoro più volte con diverse visualizzazioni dati. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=it) | N/D | 24 maggio 2023 |
| **Ordinare i componenti in Analysis Workspace** | <p>È ora disponibile una nuova opzione Ordina quando si visualizzano i componenti nella barra a sinistra o nel dizionario dei dati in Analysis Workspace. I componenti possono essere elencati a partire da quelli consigliati (utilizzati più spesso), in ordine alfabetico oppure per categoria (o tipo).</p><p>In precedenza era possibile solo cercare o filtrare i componenti. [Ulteriori informazioni](/help/components/overview.md)</p> | N/D | Da definire |
| **Eliminare righe contenenti dimensioni dinamiche da una tabella a forma libera** | In una tabella a forma libera di Analysis Workspace, ora è possibile utilizzare l’icona X per eliminare rapidamente righe specifiche contenenti dimensioni dinamiche. In questo caso, viene applicata automaticamente una regola di filtro &quot;Escludi sempre elementi&quot;.<p>In precedenza, per eliminare le righe contenenti dimensioni dinamiche era necessario creare manualmente una regola nella finestra di dialogo Filtro. [Ulteriori informazioni](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | N/D | 17 maggio 2023 |
| **Nuovo pulsante per aggiungere una visualizzazione all’interno di un pannello** | Nella parte inferiore di ciascun pannello di Analysis Workspace è ora disponibile un nuovo pulsante che consente di aggiungere rapidamente una visualizzazione. <p>In precedenza, per aggiungere una visualizzazione a un pannello eano disponibili solo i seguenti metodi: trascinare una visualizzazione dalla barra a sinistra, duplicare o copiare una visualizzazione esistente, oppure creare un pannello vuoto. [Ulteriori informazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | N/D | 17 maggio 2023 |
| **Deep Linking (app mobile)** | Consente agli utenti di inviare collegamenti alle scorecard che li porteranno direttamente al progetto della scorecard nell’app. Questo agevola ulteriormente la condivisione dei progetti e il coinvolgimento di un pubblico meno tecnico. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#share-scorecards-using-a-shareable-link) | N/D | 17 maggio 2023 |
| **Didascalie intelligenti** | Arricchisci la narrazione per gli utenti con riepiloghi in lingua naturale di una [!UICONTROL Line] visualizzazione. [Ulteriori informazioni](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 maggio 2023 | 1 giugno 2023 |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-316412; AN-317105; AN-318122; AN-317353

## Avvisi importanti per amministratori CJA

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| N/D | N/D | N/D |

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server AdobeIO OAuth** | 11 maggio 2023 | I clienti Adobe Analytics API, CJA API e Livestream che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server di AdobeIO OAuth entro il **1 gennaio 2025**. AdobeIO non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale da server a server OAuth o migrare le credenziali JWT esistenti a una credenziale da server a server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul>![](assets/jwt.png) |

{style="table-layout:auto"}

## Risorse correlate

* [Note sulle versione precedente di CJA per il 2023](/help/release-notes/2023.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
