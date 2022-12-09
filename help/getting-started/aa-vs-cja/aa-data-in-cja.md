---
title: Utilizzo dei dati della suite di rapporti di Adobe Analytics nel Customer Journey Analytics
description: Come configurare le suite di rapporti Adobe Analytics per l’acquisizione in AEP e CJA
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 13%

---

# Utilizzo dei dati della suite di rapporti di Adobe Analytics nel Customer Journey Analytics

I clienti Adobe Analytics possono facilmente sfruttare le loro suite di rapporti in Adobe Experience Platform e nel Customer Journey Analytics utilizzando [Connettore sorgente di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). La discussione seguente spiega come farlo.

## Preparazione

Quando ti prepari a iniziare a utilizzare le suite di rapporti Adobe Analytics in AEP e CJA, puoi prendere in considerazione diverse iniziative da intraprendere per preparare i dati per un passaggio semplice al Customer Journey Analytics. Per ulteriori informazioni, consulta la pagina seguente:

* [Evoluzione da Adobe Analytics a Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Configurare le suite di rapporti per l’acquisizione in Adobe Experience Platform e CJA

Dopo aver preparato i dati, puoi iniziare a configurare le suite di rapporti da utilizzare in AEP e CJA.

1. **Crea un flusso di dati per ogni suite di rapporti che desideri utilizzare in AEP e CJA.** La [Connettore sorgente di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en) è lo strumento che consente di: [creare una connessione](/help/connections/create-connection.md) (anche flusso di dati) tra Adobe Analytics e AEP. Puoi utilizzare il connettore di origine per creare un flusso di dati per ogni suite di rapporti che desideri utilizzare in AEP. Il flusso di dati crea una copia dei dati della suite di rapporti in cui lo schema è stato convertito  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=it) per il consumo da parte di applicazioni AEP, compresa CJA. Ogni suite di rapporti configurata con un flusso di dati tramite il connettore di origine viene memorizzata come set di dati separato in AEP Data Lake. 13 mesi di dati storici suite di rapporti verranno automaticamente inclusi con ogni flusso di dati e i nuovi dati fluiranno in AEP su base continuativa. Con il connettore di origine di Analytics non è necessario preoccuparsi di creare lo schema in anticipo. Viene automaticamente creato uno schema standardizzato specifico per Adobe Analytics. Tuttavia, AEP [Preparazione dei dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) lo strumento può essere utilizzato per migliorare questo schema prima che i dati vengano memorizzati in Data Lake e resi disponibili a CJA. Tieni presente che alcuni tipi di dati sono filtrati fuori dal connettore di origine e non saranno presenti nel set di dati in AEP Data Lake. Altre righe possono essere filtrate tra Data Lake e CJA. Vedi [Confrontare i dati di Adobe Analytics con i dati CJA](/help/troubleshooting/compare.md) per ulteriori dettagli.
1. **Utilizza Data Prep per aiutarti a combinare le suite di rapporti in CJA.** È possibile utilizzare Data Prep per molti tipi di trasformazione dei dati, e un utilizzo comune per i dati Adobe Analytics consiste nel risolvere le differenze nelle mappature prop e/o eVar tra più suite di rapporti in modo che le suite di rapporti possano essere facilmente combinate all’interno di CJA. Vedi [combinare suite di rapporti con schemi diversi](/help/use-cases/aa-data/combine-report-suites.md) per ulteriori dettagli.
1. **Abilitare analisi cross-channel** se necessario. Quando si combinano più set di dati in CJA, le funzionalità di unione delle identità di Cross-Channel Analytics possono aiutare a risolvere diversi namespace ID in un singolo ID vincolato per una singola visualizzazione del cliente su dispositivi e canali diversi. Vedi [Panoramica di Analytics tra canali](/help/connections/cca/overview.md) per ulteriori dettagli.
1. **Crea una o più connessioni CJA.** Una volta che i set di dati per le suite di rapporti sono disponibili in AEP Data Lake, puoi crearne uno o più [Connessioni CJA](/help/connections/overview.md) per inserire tali set di dati in CJA. All’interno di una connessione, i dati della suite di rapporti possono essere combinati con altri tipi di dati, consentendoti di creare una visualizzazione effettiva cross-channel delle esperienze dei clienti.
1. **Crea una o più visualizzazioni dati CJA.** A [visualizzazione dati](/help/data-views/data-views.md) è un contenitore specifico del Customer Journey Analytics che consente di determinare come interpretare i dati da una connessione CJA. Le visualizzazioni dati sono molte [opzioni di configurazione](/help/data-views/create-dataview.md) per personalizzare i dati presentati agli utenti in [Analysis Workspace](/help/analysis-workspace/home.md).

## Confronto tra Customer Journey Analytics e Adobe Analytics

Customer Journey Analytics e Adobe Analytics hanno una serie di somiglianze. Ad esempio, sia CJA che Adobe Analytics offrono la potenza di Analysis Workspace per l’analisi freeform della velocità del pensiero. Tuttavia, poiché CJA è un’applicazione all’interno di Adobe Experience Platform e utilizza AEP per l’inserimento dei dati, CJA e Adobe Analytics differiscono in diversi modi importanti. I seguenti articoli sono utili per comprendere queste differenze:

* [Confrontare i dati di Adobe Analytics con i dati CJA](/help/troubleshooting/compare.md)
* [Supporto delle funzioni di Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Confronto della terminologia per i dati di Analytics trasmessi tramite il connettore di origine di Analytics](/help/getting-started/aa-vs-cja/terminology.md)
* [Confrontare l’elaborazione dei dati nelle funzioni di reporting di Adobe Analytics e CJA](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Suite di rapporti virtuali, visualizzazioni dati, sandbox di AEP e il connettore di origine di Analytics](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Regole di elaborazione, VISTA e classificazioni rispetto alla preparazione dati](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID e il connettore di origine di Analytics](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
