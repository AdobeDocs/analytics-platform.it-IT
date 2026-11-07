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
source-git-commit: 7f3fb46b9c1928f8b02ce2108b4e98b5cc8da766
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 0%
---
# Comprendere le discrepanze di dati tra i feed di dati e Analysis Workspace

{{release-limited-testing}}

I dati in un’esportazione di feed dati non sempre corrispondono esattamente ai dati visualizzati in Analysis Workspace. Le informazioni su questa pagina spiegano alcuni dei motivi principali.

Alcune di queste differenze derivano da comportamenti di Workspace che sono difficili da vedere solo nei rapporti di Workspace, perché i dati di Workspace sono aggregati. I feed di dati forniscono dati a livello di evento, pertanto questi comportamenti diventano evidenti quando si confrontano l’output dei feed di dati con i rapporti di Workspace.

## Finestra di elaborazione (feed di dati) e finestra di reporting (Analysis Workspace) {#processing-window}

Ogni consegna di feed di dati utilizza una finestra di elaborazione continua di 30 giorni. La finestra di elaborazione fornisce il contesto storico necessario per classificare gli eventi in una consegna di feed di dati. Per informazioni dettagliate sulla finestra di elaborazione, inclusi esempi, vedere [Comprendere la finestra di elaborazione](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window).

In questo senso, la finestra di elaborazione è simile alla finestra di reporting in Analysis Workspace (l’intervallo di date scelto per un rapporto). Tuttavia, esistono differenze fondamentali.

| Differenze chiave | Finestra di reporting (Analysis Workspace) | Finestra di elaborazione (feed dati) |
|---------|---------|----------|
| **Intervallo di tempo per la generazione del rapporto**<br/> Quali eventi sono inclusi in un rapporto o feed | Inizia il primo giorno del mese di calendario in cui inizia l’intervallo di reporting e termina alla fine dell’intervallo di reporting.<p>Ad esempio, un rapporto con un intervallo di reporting dal 6 ottobre al 5 novembre include anche gli eventi dal 1 ottobre al 5 ottobre. Poiché i dati di Workspace sono aggregati, questi eventi aggiuntivi possono essere difficili da notare.</p><!--SME CHECK: Confirm that every Workspace report includes events from the first day of the calendar month in which the reporting window starts (per Luke, Nov 5, 2026), including segment qualification for segments limited to the reporting window. Other docs (persistence.md Person Reporting Window row, analysis-workspace/attribution/models.md lookback window) don't describe this yet.--> | Diverso dalla finestra di elaborazione. <p>L’intervallo di tempo su cui eseguire il rapporto è la finestra di frequenza, che può essere una singola ora o un singolo giorno alla fine della finestra di elaborazione.</p> |
| **Limite dati**<br/> Se i dati esterni alla finestra vengono inclusi in un report o feed o influiscono su di essi | Flessibile<p>Gli eventi a partire dal primo giorno del mese di calendario in cui inizia l’intervallo di reporting sono inclusi in un rapporto di Workspace, anche se si trovano prima dell’intervallo di reporting. Per ulteriori informazioni, vedi **Intervallo di tempo per il reporting su** sopra.</p><p>Gli eventi che non rientrano nell’intervallo di reporting possono influenzare i dati di un rapporto Workspace anche attraverso uno dei seguenti fattori:</p><ul><li>**Persistenza Dimension**: può persistere oltre l&#39;intervallo di reporting quando si utilizza Sessione, Ora personalizzata o Metrica [Scadenza](/help/data-views/component-settings/persistence.md#expiration-settings).</li><li>**Qualificazione del segmento**: per impostazione predefinita, i segmenti possono estendersi oltre l&#39;intervallo di reporting.<p>Gli utenti possono scegliere di limitare il segmento all’intervallo di reporting quando creano il segmento. Anche in questo caso, la qualificazione del segmento considera gli eventi dal primo giorno del mese di calendario in cui inizia l’intervallo di reporting.</p></li><li>**Calcolo sessione**: le sessioni possono estendersi oltre l&#39;intervallo di reporting. </li><li>**Trasformazioni campo derivato**: tutte le funzioni campo derivato che fanno riferimento a contenitori utilizzano l&#39;intervallo di reporting.<!--SME CHECK: Confirm that Session- and Person-scoped derived field functions (Deduplicate, Next or Previous, Summarize, Date Math) are limited to the reporting window in Workspace, or whether Session scope can extend beyond it like session calculation. ALSO: In the Segment qualification bullet, add a link to the new docs about limiting a segment to the reporting window.--></li></ul> | Fisso<p>Solo gli eventi nella finestra di frequenza sono inclusi in un feed di dati. Per ulteriori informazioni, vedi **Intervallo di tempo per il reporting su** sopra.</p><p>Eventi che non rientrano nella finestra di frequenza ma che rientrano nella finestra di elaborazione possono influenzare i dati in un feed di dati. In genere, gli eventi che precedono la finestra di elaborazione non possono. La finestra di elaborazione limita i seguenti fattori:</p><ul><li>**Persistenza Dimension**: impossibile mantenere oltre la finestra di elaborazione quando si utilizza Sessione, Finestra di reporting persona o Metrica [Scadenza](/help/data-views/component-settings/persistence.md#expiration-settings). A differenza di Workspace, il lookback non si estende al primo giorno del mese. Può persistere oltre la finestra di elaborazione (fino a 90 giorni) quando si utilizza l&#39;ora personalizzata [scadenza](/help/data-views/component-settings/persistence.md#expiration-settings), come in Workspace. In Workspace e nei feed di dati, il lookback dell’ora personalizzata non si estende al primo giorno del mese.<p>**Nota:** Attualmente, anche la scadenza dell&#39;ora personalizzata è limitata alla finestra di elaborazione. Prossimamente sarà disponibile il supporto per orari personalizzati che vanno oltre la finestra di elaborazione.</p></li><li>**Qualificazione del segmento**: sempre limitata alla finestra di elaborazione. A differenza di Workspace, non si estende al primo giorno del mese.</li><li>**Calcolo sessione**: sempre limitato alla finestra di elaborazione.</li><li>**Trasformazioni campo derivato**: tutte le funzioni campo derivato che fanno riferimento a contenitori utilizzano la finestra di elaborazione nelle esportazioni di feed di dati.</li></ul> |

>[!BEGINSHADEBOX]

**Esempio**

Gli esempi seguenti illustrano come le differenze tra l’intervallo di reporting e l’intervallo di elaborazione possono causare discrepanze di dati tra i rapporti di Workspace e le consegne di feed di dati.

* **Intervallo di tempo per il reporting su**: un utente ha un evento il 1° ottobre che imposta un valore di dimensione e altri eventi più avanti nel mese di ottobre. Un report di Workspace con un intervallo di reporting che inizia il 6 ottobre include l’evento del 1° ottobre, perché Workspace include gli eventi dal primo giorno del mese. Il valore impostato il 1° ottobre può anche persistere negli eventi dell’utente nella finestra di reporting. Una consegna di feed di dati con una finestra di elaborazione che inizia il 6 ottobre non considera l’evento del 1 ottobre, pertanto il valore impostato non persiste per gli eventi dell’utente nella consegna.

* **Qualificazione del segmento**: un utente qualificato per un segmento con un contenitore Persona 45 giorni fa e ha un evento oggi. Un rapporto di Workspace con una finestra di reporting di 30 giorni include l’evento dell’utente, perché per impostazione predefinita i segmenti possono estendersi oltre la finestra di reporting. La consegna di feed di dati per oggi non include l’evento, perché la qualificazione del segmento è limitata alla finestra di elaborazione di 30 giorni.

<!-- update the following graphic: ![Data differences between workspace and data feeds](assets/data-feed-data-differences.png) -->

>[!ENDSHADEBOX]

## Stitching delle riproduzioni

Ogni volta che viene eseguita una ripetizione di unione, i dati di identità storici vengono aggiornati retroattivamente.

I feed di dati e Analysis Workspace trattano le ripetizioni di unione in modo diverso, come segue:

* **Feed dati**: riflette l&#39;identità unita solo al momento dell&#39;esportazione. I risultati della ripetizione non vengono applicati retroattivamente ai file esportati.

* **Analysis Workspace**: visualizza i dati uniti più recenti, aggiornati retroattivamente ogni volta che viene eseguita una ripetizione. I dati storici cambiano dopo ogni ripetizione, pertanto Workspace riflette sempre la risoluzione dell’identità più recente.

## Eventi in arrivo

In un feed di dati, gli eventi possono arrivare dopo la chiusura della finestra di esportazione del feed di dati.

I feed di dati e Analysis Workspace funzionano in modo diverso rispetto agli eventi passati, come segue:

* **Feed di dati**: esporta i dati entro un intervallo di tempo fisso (l&#39;ora o il giorno di ogni consegna), in base ai timestamp dell&#39;evento.

  Prima di elaborare ogni consegna, Customer Journey Analytics attende il [ritardo di elaborazione](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay) scelto. Gli eventi che arrivano durante il ritardo di elaborazione sono inclusi nella consegna. Gli eventi che arrivano dopo l’inizio dell’elaborazione non sono inclusi nel file di feed dati.

* **Analysis Workspace**: elabora i dati al momento del rapporto, in modo che gli eventi vengano inclusi nei rapporti indipendentemente da quando sono stati ricevuti.

## Batch di dati

A volte i dati vengono inviati in un batch che si estende su un periodo di tempo prolungato.

I feed di dati e Analysis Workspace funzionano in modo diverso per quanto riguarda i dati in batch, come segue:

* **Feed dati**: distribuisce i dati in batch per ogni giorno o ora in base ai timestamp originali. Ad esempio, un batch contenente 30 giorni di dati viene distribuito su 30 giorni di esportazioni, quindi solo una piccola sezione viene visualizzata in una singola esportazione.

* **Analysis Workspace**: visualizza tutti i dati in un batch non appena sono completamente elaborati, indipendentemente dall&#39;intervallo di tempo incluso nel batch.

