---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fc1a5b1b0f01ace6207820e2421d1770f68c3583
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 45%

---

# Note sulla versione di Customer Journey Analytics (CJA) (ottobre 2022)

**Ultimo aggiornamento**: 5 ottobre 2022

I rilasci di Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Per piacere, controllatele regolarmente.

## Risorse correlate

* [Note sulle versioni precedenti di CJA per il 2022](/help/release-notes/2022.md)

* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)

* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)

* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)

## Funzioni chiave

| Funzione | Descrizione | [Data definita](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Pannello Sperimentazione** | Questo nuovo pannello di Workspace consente agli utenti di CJA di valutare l’incremento e l’affidabilità di qualsiasi esperimento A/B da qualsiasi origine (online, offline, dalle soluzioni Adobe, da Adobe Journey Optimizer e persino dai dati BYO). [Ulteriori informazioni](/help/analysis-workspace/c-panels/experimentation.md) | 5 ottobre 2022 |
| **[!UICONTROL Key metric summary] visualizzazione** | La [!UICONTROL Key metric summary] la visualizzazione ti consente di vedere come si presentano le metriche importanti in un singolo arco di tempo. Consente inoltre di confrontare le prestazioni delle metriche in due intervalli di tempo. Ulteriori informazioni | Rollout graduale a partire dal 5 ottobre 2022 |
| **Supporto per il campo data in CJA** | Consente a CJA di generare rapporti sui campi data e data-ora. [Ulteriori informazioni](/help/data-views/data-views-usecases.md#date) | 5 ottobre 2022 |
| **App mobile: Visualizzazioni dettagli personalizzate** | Le visualizzazioni di dettaglio personalizzate ti consentono di essere ancora più mirati sulle informazioni che condividi con il pubblico, consentendo loro di concentrarsi su ciò che è più importante. È possibile modificare il layout della visualizzazione dettagli associata a ogni tessera della scorecard e aggiungere testo per spiegare meglio cosa l’utente finale può vedere nei dati. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=it) | 5 ottobre 2022 |

{style=&quot;table-layout:auto&quot;}

## Avvisi importanti per amministratori CJA

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| **Pagina di destinazione predefinita** | 29 settembre 2023 | La [nuova pagina di destinazione](/help/getting-started/landing.md) introdotto all&#39;inizio di quest&#39;anno diventerà l&#39;esperienza predefinita per tutti gli utenti in **Gennaio 2023**. La pagina corrente diventerà obsoleta e tutti dovranno utilizzare la nuova esperienza. |
| **Mappatura IP-geolocalizzazione migliorata** | 29 settembre 2022 | Il fornitore di Adobe per le ricerche IP, Digital Element, sta effettuando l’aggiornamento a un nuovo set di dati migliorato (NetAcuity Pulse) per la mappatura IP-geolocalizzazione. Adobe Analytics ha posticipato l&#39;adozione di questo nuovo set di dati a **Gennaio 2023**. Il nuovo database sarà più accurato delle versioni precedenti. Quando il nuovo database verrà adottato, alcune mappature IP-geolocalizzazione verranno modificate/migliorate.<p> Dati CJA forniti tramite [!UICONTROL Analytics Source Connector] sfrutterà automaticamente anche le nuove mappature. |
| **[!UICONTROL Anomaly detection]condizioni di funzionamento automatico** | 29 settembre 2022 | Oggi, [!UICONTROL Anomaly detection] viene eseguito automaticamente su tutte le colonne di tabelle a forma libera serie temporale. Per garantire che i dati siano disponibili per l’analisi e che i progetti vengano caricati più rapidamente, l’Adobe cambierà il modo in cui [!UICONTROL Anomaly detection] esegue automaticamente. Avvio **26 ottobre 2022**, il rilevamento delle anomalie viene eseguito automaticamente solo sulla prima colonna metrica di una tabella. Puoi configurare le impostazioni colonna da eseguire [!UICONTROL Anomaly detection] su altre colonne, se necessario. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics - Aggiornamenti della documentazione](/help/release-notes/doc-changes.md)
