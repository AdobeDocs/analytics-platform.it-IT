---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 81%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (settembre 2024)

**Ultimo aggiornamento**: 11 settembre 2024

Queste note sulla versione coprono il periodo di rilascio compreso tra l’11 settembre e gli inizi di ottobre 2024. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Informazioni aggiuntive nella colonna “Utilizzato in” Gestore metriche calcolate e Gestione filtri** | La colonna “Utilizzato in” nel Gestore metriche calcolate e nel Gestore di filtri contiene le seguenti nuove aree di reporting:<ul><li>**Report Builder:** mostra il numero di metriche calcolate o di filtri utilizzati in Report Builder.</li><li>**Componenti ad hoc:** mostra il numero di metriche calcolate o di filtri ad hoc utilizzati nei progetti. Queste metriche e filtri calcolati ad hoc (altrimenti noti come “metriche calcolate rapide” e “filtri rapidi”) possono essere utilizzati solo nel progetto in cui sono stati creati, pertanto vengono segnalati separatamente dall’area di reporting “Progetto” nella colonna “Utilizzato in”.</li></ul>Per ulteriori informazioni, vedere [Gestione metriche calcolate](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager) e [Gestione filtri](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-components/cja-filters/manage-filters). |  | 11 settembre 2024 |
| **Avvisi** | Gli avvisi nel Customer Journey Analytics ti consentono di ricevere notifiche in base a percentuali modificate o a punti dati specifici.<p>A seconda del pacchetto di Customer Journey Analytics, puoi anche utilizzare gli avvisi da attivare in base alle soglie delle anomalie. Questi avvisi (noti anche come &quot;avvisi intelligenti&quot;) forniscono controlli granulari che si integrano con il rilevamento delle anomalie, attivandosi quando sono più necessari.</p><p>La procedura di utilizzo degli avvisi in Customer Journey Analytics è quasi identica a quella di utilizzo degli avvisi in Adobe Analytics. Una differenza principale consiste nel fatto che gli avvisi orari non sono disponibili in Customer Journey Analytics. Questa differenza è dovuta al fatto che l’acquisizione dei dati per i vari tipi di dati evento che possono essere acquisiti è completa solo dopo un ritardo, che in genere varia da 3 a 9 ore oltre l’ora dell’evento dei dati.</p><p>Per ulteriori informazioni sulle differenze durante l&#39;utilizzo degli avvisi in Customer Journey Analytics da Adobe Analytics, vedere [Confronto delle funzionalità degli avvisi](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).</p><p>Per ulteriori informazioni sugli avvisi, consulta [Panoramica avvisi](/help/components/c-intelligent-alerts/intelligent-alerts.md) |  | sabato 13 settembre 2024 |
| **Aggiornamenti al connettore di origine di Adobe Analytics** | La pagina dell’attività del set di dati non mostra informazioni sui batch, poiché il connettore di origine di Analytics è interamente gestito da Adobe. Puoi monitorare il flusso dei dati osservando le metriche relative ai record acquisiti. Per ulteriori informazioni, consulta la guida su [Creazione di una connessione di origine per i dati di Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). |  | Disponibile ora |
| **Analisi di utilizzo** | Scopri come la tua organizzazione utilizza Customer Journey Analytics. Abilitando questa funzione viene creato un set di dati in Adobe Experience Platform che raccoglie dati quando un utente dell’organizzazione utilizza Analysis Workspace. Vengono inoltre create automaticamente una connessione e una visualizzazione dati, che consentono di accedere a dimensioni quali i principali tipi di progetto, gli utenti più attivi e i componenti più popolari utilizzati nei progetti. Il link alla documentazione seguirà a breve. |  | 18 settembre 2024 |
| **Analisi guidata: incorporare in Workspace** | Combina più analisi guidate in un’unica vista in Analysis Workspace. Il link alla documentazione seguirà a breve. | 22 settembre 2024 | 2 ottobre 2024 |


## Correzioni in Customer Journey Analytics

AN-352461; AN-355446: AN-355665

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
