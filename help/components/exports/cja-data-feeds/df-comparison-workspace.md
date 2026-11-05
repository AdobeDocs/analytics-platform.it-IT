---
description: Scopri come confrontare la funzionalità dei feed dati in Customer Journey Analytics e Adobe Analytics
keywords: clickstream;feed dati;datafeed;feed dati
title: Confrontare la funzionalità dei feed di dati in Customer Journey Analytics e Adobe Analytics
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 03beb4bd52769a5428ca084beacefd8996d4c810
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%
---
# Comprendere le discrepanze di dati tra i feed di dati e Analysis Workspace

{{release-limited-testing}}

I dati in un’esportazione di feed dati non sempre corrispondono esattamente ai dati visualizzati in Analysis Workspace. Le informazioni su questa pagina spiegano alcuni dei motivi principali.

## Finestra di elaborazione (feed di dati) e finestra di reporting (Analysis Workspace) {#processing-window}

Ogni consegna di feed di dati utilizza una finestra di elaborazione continua di 30 giorni. La finestra di elaborazione fornisce il contesto storico necessario per classificare gli eventi in una consegna di feed di dati. Per informazioni dettagliate sulla finestra di elaborazione, inclusi esempi, vedere [Comprendere la finestra di elaborazione](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window).

In questo senso, la finestra di elaborazione è simile alla finestra di reporting in Analysis Workspace (l’intervallo di date scelto per un rapporto). Tuttavia, esistono differenze fondamentali.

| Differenze chiave | Finestra di reporting (Analysis Workspace) | Finestra di elaborazione (feed dati) |
|---------|---------|----------|
| **Limite dati**<br/> Se i dati sono inclusi in un report o feed | Flessibile<p>Gli eventi che non rientrano nell’intervallo di reporting possono comunque essere inclusi in un rapporto Workspace se sono influenzati da uno dei seguenti fattori:</p><ul><li>**Persistenza Dimension**: può persistere oltre l&#39;intervallo di reporting quando si utilizza Sessione, Ora personalizzata o Metrica [Scadenza](/help/data-views/component-settings/persistence.md#expiration-settings). Uguale all&#39;intervallo di reporting quando si utilizza l&#39;intervallo di reporting della persona [scadenza](/help/data-views/component-settings/persistence.md#expiration-settings). I dati sono aggregati.</li><li>**Qualificazione del segmento**: per impostazione predefinita, i segmenti possono estendersi oltre l&#39;intervallo di reporting.<p>Gli utenti possono scegliere di limitare il segmento all&#39;intervallo di reporting quando creano il segmento.<!--add link to new docs--></p></li><li>**Calcolo sessione**: le sessioni possono estendersi oltre l&#39;intervallo di reporting. </li><li>**Trasformazioni di campi derivate**</li></ul> | Fisso<p>Gli eventi che non rientrano nella finestra di elaborazione in genere non influenzano un feed di dati. La finestra di elaborazione si applica ai seguenti fattori:</p><ul><li>**Persistenza Dimension**: può persistere oltre la finestra di elaborazione (fino a 90 giorni) quando si utilizza l&#39;ora personalizzata [scadenza](/help/data-views/component-settings/persistence.md#expiration-settings), come in Workspace. Impossibile mantenere oltre la finestra di elaborazione quando si utilizza l&#39;intervallo di reporting della persona [scadenza](/help/data-views/component-settings/persistence.md#expiration-settings). Dati non aggregati.</li><li>**Qualificazione del segmento**: sempre limitata alla finestra di elaborazione.</li><li>**Calcolo sessione**: sempre limitato alla finestra di elaborazione.</li><li>**Trasformazioni campo derivato**: tutte le funzioni campo derivato che fanno riferimento a contenitori utilizzano la finestra di elaborazione nelle esportazioni di feed di dati.</li></ul> |
| **Intervallo di tempo per la generazione del rapporto**<br/> Quali eventi sono inclusi in un rapporto o feed | Come nell’intervallo di reporting. | Diverso dalla finestra di elaborazione. <p>L’intervallo di tempo su cui eseguire il rapporto è la finestra di frequenza, che può essere una singola ora o un singolo giorno alla fine della finestra di elaborazione.</p> |

>[!BEGINSHADEBOX]

**Esempio**

L’esempio seguente illustra come le differenze tra l’intervallo di reporting e l’intervallo di elaborazione possono causare discrepanze di dati tra i rapporti di Workspace e le consegne di feed di dati.

Un utente è qualificato per un segmento con un contenitore Persona 45 giorni fa e ha oggi un evento. Un rapporto di Workspace con una finestra di reporting di 30 giorni include l’evento dell’utente, perché per impostazione predefinita i segmenti possono estendersi oltre la finestra di reporting. La consegna di feed di dati per oggi non include l’evento, perché la qualificazione del segmento è limitata alla finestra di elaborazione di 30 giorni.

<!-- update the following graphic -->

![Differenze di dati tra l&#39;area di lavoro e i feed di dati](assets/data-feed-data-differences.png)


>[!ENDSHADEBOX]

## Stitching delle riproduzioni

Ogni volta che viene eseguita una ripetizione di unione, i dati di identità storici vengono aggiornati retroattivamente.

I feed di dati e Analysis Workspace trattano le ripetizioni di unione in modo diverso, come segue:

* **Feed dati**: riflette l&#39;identità unita solo al momento dell&#39;esportazione. I risultati della ripetizione non vengono applicati retroattivamente ai file esportati.

* **Analysis Workspace**: visualizza i dati uniti più recenti, aggiornati retroattivamente ogni volta che viene eseguita una ripetizione. I dati storici cambiano dopo ogni ripetizione, pertanto Workspace riflette sempre la risoluzione dell’identità più recente.

## Eventi in arrivo

In un feed di dati, gli eventi possono arrivare dopo la chiusura della finestra di esportazione del feed di dati.

I feed di dati e Analysis Workspace funzionano in modo diverso rispetto agli eventi passati, come segue:

* **Feed di dati**: esporta i dati entro un intervallo di tempo fisso in base al momento in cui vengono ricevuti gli eventi.

  Gli eventi che arrivano dopo la chiusura della finestra potrebbero non essere inclusi nell’esportazione. Questo è influenzato dal [ritardo di elaborazione](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay) scelto.

* **Analysis Workspace**: elabora i dati al momento del rapporto, in modo che gli eventi vengano inclusi nei rapporti indipendentemente da quando sono stati ricevuti.

## Batch di dati

A volte i dati vengono inviati in un batch che si estende su un periodo di tempo prolungato.

I feed di dati e Analysis Workspace funzionano in modo diverso per quanto riguarda i dati in batch, come segue:

* **Feed dati**: distribuisce i dati in batch per ogni giorno o ora in base ai timestamp originali. Ad esempio, un batch contenente 30 giorni di dati viene distribuito su 30 giorni di esportazioni, quindi solo una piccola sezione viene visualizzata in una singola esportazione.

* **Analysis Workspace**: visualizza tutti i dati in un batch non appena sono completamente elaborati, indipendentemente dall&#39;intervallo di tempo incluso nel batch.

