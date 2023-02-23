---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4e41bda273f0f7e93941bb00b55bffc6b357ac1f
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 79%

---

# Note sulla versione corrente di Customer Journey Analytics (CJA) (Febbraio 2023)

**Ultimo aggiornamento**: 23 febbraio 2023

I rilasci di Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni principali e aggiornamenti

| Funzione | Descrizione | [Inizio del rollout](/help/release-notes/releases.md) | [Disponibilità generale](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Aggiornamento dei tipi di pubblico di CJA Audiences** | Dopo aver creato un pubblico, Adobe crea un segmento Experience Platform in streaming per ogni nuovo pubblico CJA. Un segmento in streaming verrà creato solo se l’organizzazione è configurata per la segmentazione in streaming. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=it#after-audience-created) | N/D | 3 febbraio 2023 |
| **Nascondere gli intervalli di date di confronto nelle scorecard per dispositivi mobili** | Ora è possibile nascondere gli intervalli di date di confronto con le scorecard per dispositivi mobili. | N/D | 8 febbraio 2023 |
| **Aggiornamenti del calendario in Workspace** | <ul><li>Date del pannello di ancoraggio: è possibile correlare i componenti dell’intervallo di date al calendario del pannello. [Ulteriori informazioni](/help/components/date-ranges/calendar.md)</li><li>Aggiornamenti dello stile del calendario: gli stili del calendario nell’interfaccia utente sono stati aggiornati per presentare un flusso di lavoro più coerente e facile da usare.</li><li>Aggiornamenti della formula del calendario: se si utilizzano date relative, tutte le formule del calendario rispecchieranno l&#39;inizio dell&#39;intervallo di date del pannello. [Ulteriori informazioni](/help/components/date-ranges/calendar.md)</li></ul> | N/D | 8 febbraio 2023 |
| **Aggiornamenti degli intervalli di date del pannello** | In Workspace sono stati aggiunti i seguenti miglioramenti:<ul><li>A partire dalla versione di febbraio, le anteprime dei dati e dei componenti saranno basate sull’intervallo di date del pannello e non sugli ultimi 90 giorni. </li><li>Tutti i componenti elencati nella barra a sinistra saranno disponibili in base all’intervallo di date del pannello.</li><li>Tutte le anteprime di date nel segmento e i generatori di metriche calcolate saranno basate sull’intervallo di date del pannello (a meno che non siano accessibili dai gestori dei componenti, che non hanno un pannello associato, saranno comunque basate sugli ultimi 90 giorni).</li><li>Tutte le anteprime dei dati visualizzeranno dati o componenti in base all’intervallo di date del pannello.</li></ul> | N/D | 8 febbraio 2023 |
| **Filtro riga/colonna per lo streaming del connettore di origine di Adobe Analytics** | Il connettore di origine di Analytics in Adobe Experience Platform ora consente di filtrare i dati di Analytics che vengono utilizzati per popolare i profili nel [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it).<p>Il filtro a livello di riga consente di ridurre il numero di eventi associati ai profili. Il filtro a livello di colonna consente di ridurre la rilevanza degli eventi stessi, consentendoti in tal modo di ottimizzare l’utiizzo delle adesioni al profilo. Questo filtro si applica solo ai dati inviati al Profilo cliente in tempo reale e al [servizio Identity](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=it).<p>**Il filtro non influisce sui dati inviati al Data Lake per l’utilizzo in applicazioni come Customer Journey Analytics**. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it#filtering-for-profile) | N/D | Programmata il 29 marzo 2023 |

{style=&quot;table-layout:auto&quot;}

## Correzioni in Customer Journey Analytics

AN-309106

## Avvisi importanti per amministratori CJA

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| Nessun avviso corrente | N/D | N/D |

{style=&quot;table-layout:auto&quot;}

## Risorse correlate

* [Note sulle versione precedente di CJA per il 2023](/help/release-notes/2023.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
