---
title: Utilizzare i dati della suite di rapporti di Adobe Analytics in Customer Journey Analytics
description: Come configurare le suite di rapporti di Adobe Analytics per l’acquisizione in AEP e CJA
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 100%

---

# Utilizzare i dati della suite di rapporti di Adobe Analytics in Customer Journey Analytics

I clienti di Adobe Analytics possono facilmente sfruttare le loro suite di rapporti in Adobe Experience Platform e in Customer Journey Analytics utilizzando il [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). La discussione seguente spiega come farlo.

## Preparazione

Quando ti prepari a iniziare a utilizzare le suite di rapporti di Adobe Analytics in AEP e CJA, devi prendere in considerazione diverse azioni da intraprendere per preparare i dati per passare senza intoppi a Customer Journey Analytics. Per ulteriori informazioni, consulta la pagina seguente:

* [Evoluzione da Adobe Analytics a Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Configurare le suite di rapporti per l’acquisizione in Adobe Experience Platform e CJA

Dopo aver preparato i dati, puoi iniziare a configurare le suite di rapporti da utilizzare in AEP e CJA.

1. **Crea un flusso di dati per ogni suite di rapporti che desideri utilizzare in AEP e CJA.** Il [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it) è lo strumento che consente di [creare una connessione](/help/connections/create-connection.md) (ovvero un flusso di dati) tra Adobe Analytics e AEP. Potrai utilizzare il connettore di origine per creare un flusso di dati per ogni suite di rapporti che desideri utilizzare in AEP. Il flusso di dati crea una copia dei dati della suite di rapporti in cui lo schema è stato convertito in [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=it) per l’utilizzo da parte delle applicazioni AEP, compreso CJA. Ogni suite di rapporti configurata con un flusso di dati tramite il connettore di origine viene memorizzata come set di dati separato nel Data Lake di AEP. 13 mesi di dati storici della suite di rapporti verranno automaticamente inclusi in ogni flusso di dati e i nuovi dati confluiranno in AEP su base continuativa. Con il connettore di origine di Analytics non è necessario preoccuparsi di creare preventivamente lo schema. Viene automaticamente creato uno schema standardizzato specifico per Adobe Analytics. Tuttavia, per migliorare tale schema, può essere utilizzato lo strumento [Preparazione dei dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) di AEP prima che i dati vengano memorizzati nel Data Lake e resi disponibili in CJA. Tieni presente che alcuni tipi di dati sono esclusi dal connettore di origine e non saranno presenti nel set di dati nel Data Lake di AEP. Altre righe possono essere escluse tra il Data Lake e CJA. Per maggiori dettagli, consulta [Confrontare i dati di Adobe Analytics con i dati CJA.](/help/troubleshooting/compare.md).
1. **Utilizza Preparazione dei dati per aiutarti a combinare le suite di rapporti in CJA.** Preparazione dei dati può essere utilizzata per diversi tipi di trasformazione dati e, generalmente, i dati di Adobe Analytics sono utilizzati per risolvere le divergenze nelle mappature prop e/o eVar in più suite di rapporti in modo che possano essere combinate facilmente all’interno di CJA. Per maggiori informazioni, consulta [Combinazione di suite di rapporti con schemi diversi](/help/use-cases/aa-data/combine-report-suites.md).
1. **Abilita Cross-Channel Analytics** secondo necessità. Quando in CJA si combinano più set di dati, le funzionalità di unione delle identità di Cross-Channel Analytics possono contribuire a risolvere diversi ID degli spazi di nomi in un unico ID unito per una singola visualizzazione del cliente su dispositivi e canali diversi. Per maggiori informazioni, consulta [Panoramica di Cross-Channel Analytics](/help/cca/overview.md).
1. **Crea una o più connessioni CJA.** Una volta che i set di dati per le suite di rapporti sono disponibili nel Data Lake di AEP, puoi creare una o più [connessioni CJA](/help/connections/overview.md) per acquisire tali set di dati in CJA. All’interno di una connessione, i dati della suite di rapporti possono essere combinati con altri tipi di dati, consentendoti di creare una visualizzazione cross-channel effettiva delle esperienze dei clienti.
1. **Crea una o più visualizzazioni dati CJA.** Una [visualizzazione dati](/help/data-views/data-views.md) è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati di una connessione CJA. Le visualizzazioni dati presentano diverse [opzioni di configurazione](/help/data-views/create-dataview.md) potenti per la personalizzazione dei dati presentati agli utenti all’interno di [Analysis Workspace](/help/analysis-workspace/home.md).

## Confronto tra Customer Journey Analytics e Adobe Analytics

Customer Journey Analytics e Adobe Analytics hanno alcuni punti in comune. Ad esempio, sia CJA che Adobe Analytics offrono la potenza di Analysis Workspace per l’analisi a forma libera della velocità del pensiero. Tuttavia, poiché CJA è un’applicazione all’interno di Adobe Experience Platform e utilizza AEP per l’acquisizione dei dati, CJA e Adobe Analytics differiscono in diversi modi. I seguenti articoli sono utili per comprendere tali differenze:

* [Confrontare i dati di Adobe Analytics con i dati CJA](/help/troubleshooting/compare.md)
* [Supporto delle funzioni di Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Confronto della terminologia per i dati di Analytics trasmessi tramite il connettore di origine di Analytics](/help/getting-started/aa-vs-cja/terminology.md)
* [Confrontare l’elaborazione dei dati nelle funzioni di reporting di Adobe Analytics e CJA](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Suite di rapporti virtuali, visualizzazioni dati, sandbox di AEP e il connettore di origine di Analytics](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Regole di elaborazione, VISTA e classificazioni rispetto alla preparazione dati](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID e il connettore di origine di Analytics](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
