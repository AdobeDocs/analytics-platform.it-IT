---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7b368f81c4036a3992fdfc34b983f344a61dc2fb
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 50%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (settembre 2024)

**Ultimo aggiornamento**: giovedì 11 settembre 2024

Queste note sulla versione coprono il periodo di rilascio dall’11 settembre 2024 ai primi di ottobre. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Informazioni aggiuntive nella colonna &quot;Usato in&quot; del gestore delle metriche calcolate e del gestore dei filtri** | La colonna “Utilizzato in” nel Gestore metriche calcolate e nel Gestore di filtri contiene le seguenti nuove aree di reporting:<ul><li>**Report Builder**: mostra il numero di metriche calcolate o filtri utilizzati nel Report Builder.</li><li>**Componenti ad hoc**: mostra il numero di metriche calcolate ad hoc o filtri ad hoc utilizzati nei progetti. Queste metriche e filtri calcolati ad hoc (altrimenti noti come “metriche calcolate rapide” e “filtri rapidi”) possono essere utilizzati solo nel progetto in cui sono stati creati, pertanto vengono segnalati separatamente dall’area di reporting “Progetto” nella colonna “Utilizzato in”.</li></ul>Per ulteriori informazioni, vedere [Gestione metriche calcolate](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager) e [Gestione filtri](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-filters/manage-filters). |  | 11 settembre 2024 |
| **Avvisi intelligenti** | Gli avvisi intelligenti in Customer Journey Analytics consentono di ricevere notifiche immediate quando si verificano eventi anomali nei dati.<p>Puoi impostare l’attivazione degli avvisi in base a soglie di anomalie, percentuali di modifica o punti dati specifici. Gli avvisi forniscono controlli granulari che si integrano con il Rilevamento delle anomalie, attivandosi quando sono più necessari.</p><p>Il processo di utilizzo degli avvisi intelligenti in Customer Journey Analytics è quasi identico a quello degli avvisi intelligenti in Adobe Analytics. Una differenza principale consiste nel fatto che gli avvisi orari non sono disponibili in Customer Journey Analytics. Questa differenza è dovuta al fatto che l’acquisizione dei dati per i vari tipi di dati evento che possono essere acquisiti è completa solo dopo un ritardo, che in genere varia da 3 a 9 ore oltre l’ora dell’evento dei dati. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/c-intelligent-alerts/intellligent-alerts) |  | Metà settembre 2024 |
| **Aggiornamenti al connettore di origine di Adobe Analytics** | La pagina dell’attività del set di dati non visualizza informazioni sui batch, poiché il connettore Source di Analytics è interamente gestito da Adobe. Puoi monitorare il flusso dei dati osservando le metriche relative ai record acquisiti. Per ulteriori informazioni, consulta la guida su [creazione di una connessione di origine per i dati di Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). |  | Disponibile ora |
| **Analisi utilizzo** | Scopri come la tua organizzazione utilizza il Customer Journey Analytics. Abilitando questa funzione viene creato un set di dati in Adobe Experience Platform che raccoglie dati quando un utente dell’organizzazione utilizza Analysis Workspace. Vengono inoltre create automaticamente una connessione e una visualizzazione dati, che consentono di accedere a dimensioni quali i principali tipi di progetto, gli utenti più attivi e i componenti più popolari utilizzati nei progetti. (Il link alla documentazione seguirà a breve) |  | 18 settembre 2024 |
| **Analisi guidata: incorporare in Workspace** | Combina più analisi guidate in un’unica vista in Analysis Workspace. (Il link alla documentazione seguirà a breve) | lunedì 22 settembre 2024 | giovedì 2 ottobre 2024 |


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
