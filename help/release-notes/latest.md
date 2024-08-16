---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1be029f373ea5c161631a432bc275e5afd8dc761
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 77%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (agosto 2024)

**Ultimo aggiornamento**: giovedì 14 agosto 2024

Queste note sulla versione coprono il periodo compreso tra il 14 agosto 2024 e settembre 2024. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Origini dati a livello di riepilogo** | Consente di inserire dati di serie temporali privi di un ID persona. Questi dati di serie temporali possono essere utilizzati per supportare vari casi d’uso, ad esempio:<ul><li>Presentare indicatori di prestazioni di alto livello come parte o insieme ai dati a livello di evento. Può includere elementi semplici come una data e un singolo valore di metrica oppure più dimensioni e metriche, come impression pubblicitarie, aperture di e-mail, spese pubblicitarie, costo dei beni venduti e altro ancora.</li><li>Caricamento di destinazioni o obiettivi su base oraria o giornaliera, quindi posizionamento di tali destinazioni o obiettivi rispetto alle metriche a livello di evento. Questo consente di visualizzare la tendenza delle metriche rispetto agli obiettivi o ai target dell’organizzazione.</li></ul><p>Per ulteriori informazioni, vedere [Dati di riepilogo](/help/data-views/summary-data.md).</p> | mercoledì 13 agosto 2024 | giovedì 21 agosto 2024 |
| **I tipi di pubblico sono pubblicati in una nuova sezione “Tipi di pubblico” in Experience Platform** | I tipi di pubblico pubblicati da Customer Journey Analytics ora sono disponibili nella nuova sezione “Tipi di pubblico” in Adobe Experience Platform.<p>In precedenza, i tipi di pubblico pubblicati da Customer Journey Analytics erano disponibili in Experience Platform nella sezione “Segmenti”.</p><p>Questo miglioramento offre i seguenti vantaggi:</p><ul><li>I tipi di pubblico non hanno più un ritardo di 1 ora prima di essere visualizzati in Experience Platform, ma sono disponibili pochi secondi dopo la pubblicazione.</li><li>I tipi di pubblico possono essere ordinati in Experience Platform utilizzando la colonna “Origine”, che mostra l’applicazione da cui sono stati originariamente pubblicati.</li><li>Le opzioni di filtro e ordinamento in Experience Platform consentono di trovare più rapidamente i tipi di pubblico rilevanti.</li></ul> <p>Per ulteriori informazioni, vedere [Utilizzare i tipi di pubblico di Customer Journey Analytics nell&#39;Experience Platform](/help/components/audiences/publish.md#use-customer-journey-analytics-audiences-in-experience-platform) nell&#39;articolo [Creare e pubblicare tipi di pubblico](/help/components/audiences/publish.md).</p> | 14 agosto 2024 | 22 agosto 2024 |
| **Avvisi intelligenti** | Gli avvisi intelligenti nel Customer Journey Analytics consentono di ricevere notifiche immediate quando si verificano eventi anomali nei dati.<p>Puoi impostare l’attivazione degli avvisi in base a soglie di anomalie, percentuali di modifica o punti dati specifici. Gli avvisi forniscono controlli granulari che si integrano con il Rilevamento delle anomalie, attivandosi quando sono più necessari.</p><p>Il processo di utilizzo degli avvisi intelligenti in Customer Journey Analytics è quasi identico a quello degli avvisi intelligenti in Adobe Analytics. Una differenza principale consiste nel fatto che gli avvisi orari non sono disponibili in Customer Journey Analytics. Questa differenza è dovuta al fatto che l’acquisizione dei dati per i vari tipi di dati evento che possono essere acquisiti è completa solo dopo un ritardo, che in genere varia da 3 a 9 ore oltre l’ora dell’evento dei dati.</p><p>Il link alla documentazione aggiornata seguirà a breve</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | Da definire |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-354359; AN-351646; AN-346873; AN-352504; AN-353755; AN-354199; AN-354268; AN-354791; AN-354598; AN-354462; AN-354547;

## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| N/D | | |

{style="table-layout:auto"}

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2024](/help/release-notes/2024.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione del componente aggiuntivo di raccolta contenuti in streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
