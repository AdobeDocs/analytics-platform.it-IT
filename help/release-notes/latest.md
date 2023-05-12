---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7e6383bf94e10f6ab6f9db990f4ef3df0fb826d3
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 25%

---

# Note sulla versione corrente di Customer Journey Analytics (CJA) (maggio 2023)

**Ultimo aggiornamento**: 8 maggio 2023

I rilasci di Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni principali e aggiornamenti

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Backfill per sandbox non di produzione** | Quando crei un flusso di dati del connettore di origine di Analytics in una sandbox non di produzione, il backfill nelle sandbox non di produzione sarà limitato a 3 mesi. Rimarrà a 13 mesi per le sandbox di produzione. | N/D | 26 aprile 2023 |
| **Condivisione dei collegamenti per i progetti (accesso non richiesto)** | Ora puoi condividere collegamenti di sola lettura ai progetti Analysis Workspace con persone che non hanno accesso ad Adobe Analytics. Ciò include la condivisione con persone esterne all’organizzazione o all’interno dell’organizzazione che non dispongono del provisioning per Adobe Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>Questa funzionalità è abilitata per impostazione predefinita e può essere disabilitata dall’amministratore di sistema. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 3 maggio 2023 | Giugno 2023 |
| **Schermata iniziale aggiornata per l’app delle dashboard di Analytics (app mobile)** | La nuova schermata Home aggiornata consente di visualizzare tutte le scorecard in un unico elenco di scorecard consolidato.  Se hai accesso a più organizzazioni con un solo accesso, tutte le scorecard delle organizzazioni saranno disponibili in un unico elenco. | N/D | 10 maggio 2023 |
| **Campi derivati** | Rappresenta la versione iniziale dei campi derivati. Un campo derivato ti consente di definire al volo (spesso complesse) le manipolazioni dei dati tramite un generatore di regole personalizzabile. Puoi definire ulteriormente il campo derivato come un componente (metrica o dimensione) nelle visualizzazioni Dati e quindi utilizzare il campo derivato come componente in Workspace.<p>Questa versione supporta un modello di canali di marketing e le seguenti funzioni:</p><ul><li>Concatenato</li><li>Case quando</li><li>Trova e sostituisci</li><li>Ricerca</li><li>Analisi URL</li></ul> <p>[Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 10 maggio 2023 | Da definire |
| **Report Builder per CJA - Seleziona visualizzazione dati dalla cella** | Questa funzione consente agli utenti di selezionare la visualizzazione dati per un blocco di dati da una cella. Questa opzione è utile se si crea una cartella di lavoro e si dispone di più visualizzazioni dati con struttura dati simile e si desidera poter riutilizzare una cartella di lavoro più volte con diverse visualizzazioni dati. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | N/D | 24 maggio 2023 |
| **Ordinare i componenti in Analysis Workspace** | <p>È ora disponibile una nuova opzione Ordina quando visualizzi i componenti nella barra a sinistra o nel dizionario dati in Analysis Workspace. Puoi ordinare i componenti per tipo Consigliato (quelli più comunemente utilizzati), Alfabetico o Categorico.</p><p>In precedenza era possibile cercare o filtrare solo i componenti. [Ulteriori informazioni](/help/components/overview.md)</p> | N/D | 17 maggio 2023 |
| **Eliminare righe contenenti dimensioni dinamiche da una tabella a forma libera** | In una tabella a forma libera in Analysis Workspace, è ora possibile eliminare rapidamente righe specifiche contenenti dimensioni dinamiche utilizzando l’icona x. In questo modo, viene applicata automaticamente una regola di filtro &quot;È diverso da&quot;.<p>In precedenza, l’unico modo per eliminare le righe contenenti dimensioni dinamiche era creare manualmente una regola nella finestra di dialogo Filtro. [Ulteriori informazioni](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | N/D | 17 maggio 2023 |
| **Nuovo pulsante per aggiungere una visualizzazione all’interno di un pannello** | È ora disponibile un nuovo pulsante nella parte inferiore di ciascun pannello in Analysis Workspace, che consente di aggiungere rapidamente una visualizzazione. <p>In precedenza, gli unici metodi per aggiungere una visualizzazione a un pannello consistevano nel trascinare una visualizzazione dalla barra a sinistra, duplicare o copiare una visualizzazione esistente o creare un pannello vuoto. [Ulteriori informazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | N/D | 17 maggio 2023 |
| **Collegamenti profondi (app mobile)** | Consente agli utenti di inviare collegamenti alle scorecard che li porteranno direttamente al progetto della scorecard nell’app. Questo rende ancora più facile condividere i progetti e aumentare l&#39;impegno da parte di un pubblico meno tecnico. | N/D | 17 maggio 2023 |
| **Sottotitoli intelligenti** | Arricchisci la narrazione per gli utenti con riassunti in lingua naturale di un [!UICONTROL Line] visualizzazione. [Ulteriori informazioni](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 maggio 2023 | 1 giugno 2023 |

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
| **Migrazione alle credenziali server-to-server OAuth di AdobeIO** | 11 maggio 2023 | I clienti che utilizzano le credenziali JWT di AdobeIO devono migrare alle credenziali server-to-server OAuth di AdobeIO API, CJA API e Livestream **1 gennaio 2025**. AdobeIO non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare la propria credenziale JWT esistente a una credenziale server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul>![](assets/jwt.png) |

{style="table-layout:auto"}

## Risorse correlate

* [Note sulle versione precedente di CJA per il 2023](/help/release-notes/2023.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
