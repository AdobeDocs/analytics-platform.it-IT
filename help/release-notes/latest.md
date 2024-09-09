---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: d748d89638704eace46b4ba172691b5004be1d67
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 82%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (agosto 2024)

**Ultimo aggiornamento**: martedì 9 settembre 2024

Queste note sulla versione coprono il periodo di rilascio compreso tra il 14 agosto 2024 e settembre 2024. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Informazioni aggiuntive nella colonna &quot;Usato in&quot; del gestore delle metriche calcolate e del gestore dei filtri** | La colonna &quot;Usato in&quot; nel gestore delle metriche calcolate e nel gestore dei filtri contiene le seguenti nuove aree per i rapporti:<ul><li>**Report Builder:** mostra il numero di metriche calcolate o filtri utilizzati nel Report Builder.</li><li>**Componenti ad hoc:** mostra il numero di metriche calcolate ad hoc o filtri ad hoc utilizzati nei progetti. Queste metriche e filtri calcolati ad hoc (altrimenti noti come &quot;metriche calcolate rapide&quot; e &quot;filtri rapidi&quot;) possono essere utilizzati solo nel progetto in cui sono stati creati, per cui vengono segnalati separatamente dall’area di reporting &quot;Progetto&quot; nella colonna &quot;Utilizzato in&quot;.</li></ul><p>Sono stati aggiornati i collegamenti alla documentazione.</p> | N/D | giovedì 11 settembre 2024 |
| **Origini dati a livello di riepilogo** | Consente di inserire dati di serie temporali privi di un ID persona. Questi dati di serie temporali possono essere utilizzati per supportare vari casi d’uso, ad esempio:<ul><li>Presentare indicatori di prestazioni di alto livello come parte o insieme ai dati a livello di evento. Può includere elementi semplici come una data e un singolo valore di metrica oppure più dimensioni e metriche, come impression pubblicitarie, aperture di e-mail, spese pubblicitarie, costo dei beni venduti e altro ancora.</li><li>Caricamento di target o obiettivi su base oraria o giornaliera, quindi posizionamento di questi target o obiettivi rispetto alle metriche a livello di evento, per aiutarti a visualizzare la tendenza delle metriche rispetto ai target o agli obiettivi organizzativi.</li></ul><p>Per ulteriori informazioni, consulta la sezione [Dati di riepilogo](/help/data-views/summary-data.md).</p> | 13 agosto 2024 | 21 agosto 2024 |
| **I tipi di pubblico sono pubblicati in una nuova sezione “Tipi di pubblico” in Experience Platform** | I tipi di pubblico pubblicati da Customer Journey Analytics ora sono disponibili nella nuova sezione “Tipi di pubblico” in Adobe Experience Platform.<p>In precedenza, i tipi di pubblico pubblicati da Customer Journey Analytics erano disponibili in Experience Platform nella sezione “Segmenti”.</p><p>Questo miglioramento offre i seguenti vantaggi:</p><ul><li>I tipi di pubblico non hanno più un ritardo di 1 ora prima di essere visualizzati in Experience Platform, ma sono disponibili pochi secondi dopo la pubblicazione.</li><li>I tipi di pubblico possono essere ordinati in Experience Platform utilizzando la colonna “Origine”, che mostra l’applicazione da cui sono stati originariamente pubblicati.</li><li>Le opzioni di filtro e ordinamento in Experience Platform consentono di trovare più rapidamente i tipi di pubblico rilevanti.</li></ul> <p>Per ulteriori informazioni, consulta la sezione [Utilizzare i tipi di pubblico di Customer Journey Analytics in Experience Platform](/help/components/audiences/publish.md#use-customer-journey-analytics-audiences-in-experience-platform) nell’articolo [Creare e pubblicare tipi di pubblico](/help/components/audiences/publish.md).</p> | Settembre 2024 | Settembre 2024 |
| **Avvisi intelligenti** | Gli avvisi intelligenti in Customer Journey Analytics consentono di ricevere notifiche immediate quando si verificano eventi anomali nei dati.<p>Puoi impostare l’attivazione degli avvisi in base a soglie di anomalie, percentuali di modifica o punti dati specifici. Gli avvisi forniscono controlli granulari che si integrano con il Rilevamento delle anomalie, attivandosi quando sono più necessari.</p><p>Il processo di utilizzo degli avvisi intelligenti in Customer Journey Analytics è quasi identico a quello degli avvisi intelligenti in Adobe Analytics. Una differenza principale consiste nel fatto che gli avvisi orari non sono disponibili in Customer Journey Analytics. Questa differenza è dovuta al fatto che l’acquisizione dei dati per i vari tipi di dati evento che possono essere acquisiti è completa solo dopo un ritardo, che in genere varia da 3 a 9 ore oltre l’ora dell’evento dei dati.</p><p>Il link alla documentazione aggiornata seguirà a breve</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | Da definire |

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
