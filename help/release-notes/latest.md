---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: dcd7484a98363a6a818b59e9e183f699eecc1ed4
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 34%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (maggio 2024)

**Ultimo aggiornamento**: mercoledì 21 maggio 2024

Queste note sulla versione coprono il periodo dal 15 maggio 2024 a giugno 2024. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Estensione BI** | L&#39;estensione BI consente l&#39;accesso SQL alle visualizzazioni dati definite nel Customer Journey Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension) | | giovedì 15 maggio 2024 |
| **I tipi di pubblico vengono pubblicati in una nuova sezione &quot;Tipi di pubblico&quot; nell’Experience Platform** | I tipi di pubblico pubblicati da Customer Journey Analytics sono ora disponibili nella nuova sezione &quot;Tipi di pubblico&quot; in Adobe Experience Platform.<p>In precedenza, i tipi di pubblico pubblicati da Customer Journey Analytics erano disponibili in Experienci Platform nella sezione &quot;Segmenti&quot;.</p><p>Questo miglioramento offre i seguenti vantaggi:</p><ul><li>I tipi di pubblico non hanno più un ritardo di 1 ora prima di essere visualizzati in Experienci Platform; sono disponibili pochi secondi dopo la pubblicazione.</li><li>I tipi di pubblico possono essere ordinati in Experienci Platform utilizzando la colonna &quot;Origine&quot;, che mostra l’applicazione da cui il pubblico è stato pubblicato originariamente.</li><li>Le opzioni di filtro e ordinamento in Experienci Platform consentono di trovare più rapidamente i tipi di pubblico rilevanti.</li></ul> <p>(Il link alla documentazione è stato aggiornato)</p> |  | Da fine maggio a inizio giugno 2024 |
| **Assistente AI per Customer Journey Analytics** | Consente di porre domande in lingua naturale nell’interfaccia utente del Customer Journey Analytics e di ottenere risposte in base alla documentazione del Customer Journey Analytics. <p>(Il link alla documentazione è stato aggiornato)</p> | | 30 maggio 2024 |
| **Dati multimediali in streaming: invia dati web alla rete Edge di Adobe Experience Platform con Web SDK** | Ora puoi utilizzare Adobe Experience Platform Web SDK per inviare i dati web di Streaming Media all’Edge Network di Adobe Experience Platform, consentendoti di creare campagne più personalizzate e fornire contenuti più personalizzati, con conseguente aumento dei dati di tracciamento da includere nei rapporti.<p>Questo miglioramento fornisce un metodo di raccolta unificato per le implementazioni web in tutte le soluzioni Platform, come Customer Journey Analytics, RT-CDP, AJO e Inoltro eventi. In precedenza, l’unico modo per inviare i dati web di Streaming Media ad Edge Network era utilizzare l’API Media Edge. <p>[Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | giovedì 29 maggio 2024 |
| **Campi derivati - Funzione matematica** | Consente di eseguire semplici operatori matematici all’interno delle visualizzazioni dati per rispondere a domande sugli utenti. Ad esempio, puoi combinare i ricavi da prodotti, garanzia e spedizione. <p>(Il link alla documentazione è stato aggiornato)</p> | | giovedì 5 giugno 2024 |
| **Condividere account e percorsi utilizzati per l&#39;esportazione e l&#39;importazione** | Gli utenti possono ora rendere disponibili a tutti gli utenti della propria organizzazione gli account e le posizioni creati. Solo i proprietari degli account e delle posizioni e gli amministratori di sistema possono modificare ed eliminare gli account e le posizioni.<p>In precedenza, gli account e le posizioni potevano essere utilizzati solo dall’utente che li aveva creati.</p><p>Queste impostazioni sono disponibili quando gli utenti configurano account di esportazione cloud e percorsi di esportazione cloud.</p> <p>(Il link alla documentazione è stato aggiornato)</p> | giovedì 12 giugno 2024 | lunedì 30 giugno 2024 |
| **Nuova documentazione per l’aggiornamento da Adobe Analytics a Customer Journey Analytics** | Per le organizzazioni che eseguono l’aggiornamento da Adobe Analytics a Customer Journey Analytics, esistono diverse opzioni e molte considerazioni da tenere a mente, a seconda dell’implementazione Adobe Analytics corrente e degli obiettivi a lungo termine dell’organizzazione. Sono ora disponibili nuove risorse di documentazione per aiutarti a comprendere meglio:<ul><li>I vari percorsi di aggiornamento esistenti</li><li>Quali percorsi di aggiornamento sono disponibili in base all’implementazione Adobe Analytics corrente dell’organizzazione</li><li>Vantaggi e svantaggi di ciascun percorso di aggiornamento</li><li>Linee guida dettagliate per ogni percorso di aggiornamento</li><li>Considerazioni per la gestione dei dati storici</li></ul>[Introduzione alla migrazione a Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Disponibile ora |
| **Nuova documentazione su [Casi d’uso per l’esportazione dei dati](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-export/overview)** | Questa nuova sezione illustra casi di utilizzo dell’esportazione di dati come<ul><li>Backup dei dati</li><li>Convalida dei dati</li><li>Data Lake, Data Warehouse o strumenti BI</li><li>Preparazione per IA/ML</li></ul> e come implementarli utilizzando le funzionalità di Experience Platform e Customer Journey Analytics. | | Disponibile ora |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-342309; AN-342312; AN-345267; AN-345909; AN-346016; AN-346049; AN-346052; AN-346287; AN-346624; AN-347919

## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| N/D | | |

{style="table-layout:auto"}

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2024](/help/release-notes/2024.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
