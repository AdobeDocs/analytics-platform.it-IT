---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 13c697331004b715271a7256c671293afb3c9b1f
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 40%

---

# Note sulla versione del Customer Journey Analytics corrente (CJA) (febbraio 2023)

**Ultimo aggiornamento**: 6 febbraio 2023

I rilasci di Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni principali e aggiornamenti

| Funzione | Descrizione | [Inizio del rollout](/help/release-notes/releases.md) | [Disponibilità generale](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Aggiornamento di CJA Audiences** | Dopo aver creato un pubblico, Adobe crea un segmento di streaming Experience Platform per ogni nuovo pubblico CJA. Un segmento in streaming verrà creato solo se l’organizzazione è configurata per la segmentazione in streaming. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created) | N/D | 3 febbraio 2023 |
| **Nascondere intervalli di date di confronto nelle scorecard per dispositivi mobili** | Con le scorecard per dispositivi mobili, ora puoi nascondere gli intervalli di date del confronto. | N/D | 8 febbraio 2023 |
| **Aggiornamenti del calendario in Workspace** | <ul><li>Date del pannello di ancoraggio: Puoi rendere i componenti dell’intervallo di date relativi al calendario del pannello. [Ulteriori informazioni](/help/components/date-ranges/calendar.md)</li><li>Aggiornamenti dello stile del calendario: Gli stili del calendario in tutta l’interfaccia utente sono stati aggiornati per presentare un flusso di lavoro più coerente e facile da usare.</li><li>Aggiornamenti della formula del calendario: Se si utilizzano date relative, tutte le formule del calendario rifletteranno l&#39;inizio dell&#39;intervallo di date del pannello. [Ulteriori informazioni](/help/components/date-ranges/calendar.md)</li></ul> | N/D | 8 febbraio 2023 |
| **Filtro riga/colonna per lo streaming del connettore sorgente Adobe Analytics** | Il connettore di origine di Analytics in Adobe Experience Platform ora consente di filtrare i dati di Analytics che vengono utilizzati per popolare i profili in [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it).<p>Il filtro a livello di riga consente di ridurre il numero di eventi associati ai profili. Il filtro a livello di colonna consente di ridurre la ricchezza degli eventi stessi, consentendoti in tal modo di ottimizzare l’uso delle adesioni al profilo. Questo filtro si applica solo ai dati inviati a Profilo cliente in tempo reale e [Servizio identità](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=it).<p>**Il filtro non influisce sui dati inviati a Data Lake per l&#39;utilizzo in applicazioni come Customer Journey Analytics**. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | N/D | 22 febbraio 2023 |

{style=&quot;table-layout:auto&quot;}

## Correzioni nel Customer Journey Analytics

AN-309106

## Avvisi importanti per amministratori CJA

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| Nessun avviso corrente | N/D | N/D |

{style=&quot;table-layout:auto&quot;}

## Risorse correlate

* [Note sulle versioni precedenti di CJA per il 2023](/help/release-notes/2023.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
