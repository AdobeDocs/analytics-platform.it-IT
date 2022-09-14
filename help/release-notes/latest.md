---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 8552e2e784cefc842f5105c41dcffc14192d5ceb
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 76%

---

# Note sulla versione del Customer Journey Analytics corrente (CJA) (settembre 2022)

**Ultimo aggiornamento**: 14 settembre 2022

## Risorse correlate

* [Note sulla versione precedente di CJA per il 2022](/help/release-notes/2022.md)

* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)

* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)

* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)

## Funzioni chiave

| Funzione | Descrizione | [Data definita](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Supporto per aree geografiche diverse per il connettore di origine di Analytics** | È ora possibile acquisire suite di rapporti da qualsiasi area geografica (Stati Uniti, Regno Unito o Singapore). Tuttavia, queste suite di rapporti devono essere mappate sulla stessa organizzazione dell’istanza Sandbox di Experience Platform in cui viene creata la connessione di origine. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) | 24 agosto 2022 |
| **Report della prima sessione** | Scopri se una particolare sessione è stata la prima di un utente. [Ulteriori informazioni](/help/data-views/data-views-usecases.md) | 24 agosto 2022 |
| **Pannello di sperimentazione per CJA** | Questo nuovo pannello Workspace consente agli utenti di CJA di valutare l’incremento e l’affidabilità di qualsiasi esperimento A/B da qualsiasi sorgente (online, offline, dalle soluzioni di Adobe, Adobe Journey Optimizer e persino dai dati BYO (fai-da-te). [Ulteriori informazioni](/help/analysis-workspace/c-panels/experimentation.md) | [Versione limitata](/help/release-notes/releases.md) a partire dal 14 settembre 2022 |
| **Visualizzazione grafici combinati in Workspace** | I grafici combinati consentono di confrontare le metriche in modo più semplice e intuitivo all’interno di Workspace. [Ulteriori informazioni](/help/analysis-workspace/visualizations/combo-charts.md) | 14 settembre 2022 |
| **Supporto di CJA per etichette e criteri per la governance dei dati** | Automatizza l’integrazione tra le etichette e i criteri di privacy di CJA e Adobe Experience Platform. Le etichette per dati create sui set di dati utilizzati da Platform vengono mostrate nelle visualizzazioni dati di CJA per interrompere o avvisare gli utenti che creano metriche e/o dimensioni dai campi sensibili. Inoltre, quando i dati vengono esportati da CJA (tramite le funzionalità di reporting in Workspace o Report Builder, l’esportazione, le API, ecc.) verranno aggiunte avvertenze o etichette per avvisare gli utenti che un rapporto contiene informazioni sensibili che devono essere trattate in modo specifico. [Ulteriori informazioni](/help/data-views/data-governance.md) | 14 settembre 2022 |

{style=&quot;table-layout:auto&quot;}

## Correzioni

AN-298412

## Avvisi importanti per amministratori CJA

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| **Mappatura IP-geolocalizzazione migliorata** | 9 settembre 2022 | Il fornitore di Adobe per le ricerche IP, Digital Element, sta effettuando l’aggiornamento a un nuovo set di dati migliorato (NetAcuity Pulse) per la mappatura IP-geolocalizzazione. Adobe Analytics adotterà questo nuovo set di dati in **5 ottobre 2022**. Il nuovo database sarà più accurato delle versioni precedenti. Alcune mappature IP-geolocalizzazione cambieranno/miglioreranno quando verrà adottato il nuovo database.<p> Anche i dati CJA forniti tramite il connettore origine di Analytics sfrutteranno automaticamente le nuove mappature. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics - Aggiornamenti della documentazione](/help/release-notes/doc-changes.md)
