---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7d915fc9b50163b7ec9c48232b99a85a3b063a77
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 53%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics di Adobe (luglio 2024)

**Ultimo aggiornamento**: giovedì 17 luglio 2024

Queste note sulla versione coprono il periodo dal 17 luglio 2024 ad agosto 2024. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di distribuzione continua](releases.md), che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Avvisi intelligenti** | Gli avvisi intelligenti sono ora disponibili in Customer Journey Analytics e consentono di ricevere notifiche immediate quando si verificano eventi anomali nei dati.<p>Puoi impostare l’attivazione degli avvisi in base a soglie di anomalie, percentuali di modifica o punti dati specifici. Gli avvisi forniscono controlli granulari che si integrano con Rilevamento anomalie, attivandosi quando sono più necessari.</p><p>Il processo di utilizzo degli avvisi intelligenti nel Customer Journey Analytics è quasi identico a quello degli avvisi intelligenti in Adobe Analytics. Una differenza chiave è che gli avvisi orari non sono disponibili nel Customer Journey Analytics. Questa differenza è dovuta al fatto che l’acquisizione dei dati per i vari tipi di dati evento che possono essere acquisiti è completa solo dopo un ritardo, che in genere varia da 3 a 9 ore oltre l’ora dell’evento dei dati.</p><p>(Link alla documentazione aggiornati a seguire)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | sabato 26 luglio 2024 |
| **Impostazioni dell’amministratore per controllare gli account e le posizioni utilizzate durante l’esportazione dei report nel cloud** | Una nuova [scheda “Impostazioni amministratore” in Gestione posizioni](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only) consente agli amministratori di controllare se gli utenti possono creare e modificare account e posizioni.<p>Queste impostazioni si applicano quando gli utenti [configurano account di esporazione cloud](/help/components/exports/cloud-export-accounts.md) e [posizioni di esportazione cloud](/help/components/exports/cloud-export-locations.md).</p><p>Gli amministratori possono inoltre limitare i tipi di account che gli utenti possono creare e utilizzare. I tipi di account includono Google Cloud Platform, Azure RBAC, Amazon S3, AEP Data Landing Zone, Snowflake e così via.</p><p>In precedenza, tutti gli utenti potevano creare, modificare e utilizzare account e posizioni per qualsiasi tipo di account.</p> | 11 luglio 2024 | 19 luglio 2024 |
| **Origini dati di riepilogo** | Consente di inserire dati di serie temporali privi di un ID persona. Questi dati di serie temporali possono essere utilizzati per supportare vari casi d’uso, ad esempio:<ul><li>Presentare indicatori di prestazioni di alto livello come parte o accanto ai dati a livello di evento. Può includere elementi semplici come una data e un singolo valore di metrica oppure più dimensioni e metriche, come impressioni pubblicitarie, aperture di e-mail, spese pubblicitarie, costo del bene venduto e altro ancora.</li><li>Caricamento di target o obiettivi su base giornaliera, settimanale, mensile o trimestrale e posizionamento di questi target o obiettivi rispetto alle metriche a livello di evento per aiutarti a visualizzare la tendenza delle metriche rispetto ai target o agli obiettivi organizzativi.</li></ul><p>(Link alla documentazione aggiornati a seguire)</p> |  | giovedì 31 luglio 2024 |
| **Campi derivati - Deduplica funzione** | La funzione [Deduplicate](/help/data-views/derived-fields/derived-fields.md#deduplicate) nei campi derivati consente di evitare di contare più volte un valore. |  | giovedì 17 luglio 2024 |
| **Provisioning guidato delle analisi per i clienti CJA** | L’analisi guidata consente agli utenti di gestire autonomamente dati e informazioni di alta qualità sul percorso del cliente tramite flussi di lavoro guidati, basati sui dati multicanale del Customer Journey Analytics. <p>I team interfunzionali, dal marketing al prodotto, possono connettersi in tempo reale per utilizzare e comprendere questi rapporti.</p><p>All’interno dei pacchetti CJA sono ora disponibili fino a 11 visualizzazioni di analisi guidate. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/overview)</p> |  | giovedì 17 luglio 2024 |
| **Condividere account e posizioni utilizzati per l’esportazione e l’importazione** | Gli utenti possono ora rendere disponibili a tutti gli utenti della propria organizzazione gli account e le posizioni creati. Solo i proprietari degli account e delle posizioni e gli amministratori di sistema possono modificarli ed eliminarli. In precedenza, gli account e le posizioni potevano essere utilizzati solo dall’utente che li aveva creati. Queste impostazioni sono disponibili quando gli utenti [configurano account](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) e le [posizioni di esportazione cloud](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12 giugno 2024 | Metà luglio 2024 |
| **I tipi di pubblico sono pubblicati in una nuova sezione “Tipi di pubblico” in Experience Platform** | I tipi di pubblico pubblicati da Customer Journey Analytics ora sono disponibili nella nuova sezione “Tipi di pubblico” in Adobe Experience Platform.<p>In precedenza, i tipi di pubblico pubblicati da Customer Journey Analytics erano disponibili in Experience Platform nella sezione “Segmenti”.</p><p>Questo miglioramento offre i seguenti vantaggi:</p><ul><li>I tipi di pubblico non hanno più un ritardo di 1 ora prima di essere visualizzati in Experience Platform, ma sono disponibili pochi secondi dopo la pubblicazione.</li><li>I tipi di pubblico possono essere ordinati in Experience Platform utilizzando la colonna “Origine”, che mostra l’applicazione da cui sono stati originariamente pubblicati.</li><li>Le opzioni di filtro e ordinamento in Experience Platform consentono di trovare più rapidamente i tipi di pubblico rilevanti.</li></ul> <p>(Il link alla documentazione seguirà a breve)</p> |  | Da definire |

{style="table-layout:auto"}

## Correzioni in Customer Journey Analytics

AN-306000; AN-288748; AN-351547; AN-351110

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
