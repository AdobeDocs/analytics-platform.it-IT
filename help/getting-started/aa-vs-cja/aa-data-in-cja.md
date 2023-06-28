---
title: Utilizzare i dati della suite di rapporti di Adobe Analytics in Customer Journey Analytics
description: Come configurare le suite di rapporti di Adobe Analytics per l’acquisizione in Adobe Experience Platform e Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: cf6da1f126933f17e05fb458f52dff93c1601891
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 29%

---

# Utilizzare i dati della suite di rapporti di Adobe Analytics in Customer Journey Analytics

I clienti di Adobe Analytics possono facilmente sfruttare le loro suite di rapporti in Adobe Experience Platform e in Customer Journey Analytics utilizzando il [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). La discussione seguente spiega come farlo.

## Preparazione

Quando ti prepari a iniziare a utilizzare le suite di rapporti di Adobe Analytics in Adobe Experience Platform e Customer Journey Analytics, devi prendere in considerazione diverse azioni da intraprendere per preparare i dati per passare facilmente al Customer Journey Analytics. Per ulteriori informazioni, consulta la pagina seguente:

* [Evoluzione da Adobe Analytics a Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Configurare le suite di rapporti per l’acquisizione in Adobe Experience Platform e Customer Journey Analytics

Dopo aver preparato i dati, puoi iniziare a configurare le suite di rapporti da utilizzare in Adobe Experience Platform e Customer Journey Analytics.

1. **Crea un flusso di dati per ogni suite di rapporti che desideri utilizzare in Adobe Experience Platform e Customer Journey Analytics.** Il [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it) è lo strumento che consente di: [creare una connessione](/help/connections/create-connection.md) (alias flusso di dati) tra Adobe Analytics e Adobe Experience Platform. Puoi utilizzare il connettore di origine per creare un flusso di dati per ogni suite di rapporti che desideri utilizzare in Adobe Experience Platform. Il flusso di dati crea una copia dei dati della suite di rapporti in cui lo schema è stato convertito in  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=it) per l&#39;utilizzo da parte di applicazioni Adobe Experience Platform, incluso Customer Journey Analytics.<p>Ogni suite di rapporti configurata con un flusso di dati tramite il connettore di origine viene memorizzata come set di dati separato nel Data Lake di Adobe Experience Platform. 13 mesi di dati storici della suite di rapporti verranno inclusi automaticamente in ogni flusso di dati e i nuovi dati confluiranno in Adobe Experience Platform su base continuativa. A partire dal 26 aprile 2023, la retrocompilazione nelle sandbox non di produzione è limitata a 3 mesi. Con il connettore di origine di Analytics non è necessario preoccuparsi di creare preventivamente lo schema. Viene automaticamente creato uno schema standardizzato specifico per Adobe Analytics. Tuttavia, Adobe Experience Platform [Preparazione dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) può essere utilizzato per migliorare questo schema prima che i dati vengano memorizzati nel Data Lake e resi disponibili al Customer Journey Analytics. Tieni presente che alcuni tipi di dati vengono esclusi dal connettore di origine e non saranno presenti nel set di dati in Adobe Experience Platform Data Lake. Altre righe possono essere escluse tra Data Lake e Customer Journey Analytics. Consulta [Confrontare i dati di Adobe Analytics con i dati del Customer Journey Analytics](/help/troubleshooting/compare.md) per ulteriori dettagli.
1. **Utilizza Preparazione dati per aiutarti a combinare le suite di rapporti nel Customer Journey Analytics.** La preparazione dati può essere utilizzata per diversi tipi di trasformazione dati e, generalmente, i dati di Adobe Analytics vengono utilizzati per risolvere le differenze nelle mappature prop e/o eVar tra più suite di rapporti in modo che possano essere combinate facilmente all’interno del Customer Journey Analytics. Per maggiori informazioni, consulta [Combinazione di suite di rapporti con schemi diversi](/help/use-cases/aa-data/combine-report-suites.md).
1. **Abilita unione** secondo necessità. Quando si combinano più set di dati nel Customer Journey Analytics, le funzionalità di unione possono aiutare a risolvere diversi ID degli spazi di nomi in un singolo ID unito per una singola visualizzazione del cliente su dispositivi e canali diversi. Consulta [Panoramica sull’unione](../../stitching/overview.md) per ulteriori dettagli.
1. **Crea una o più connessioni di Customer Journey Analytics.** Una volta che i set di dati per le suite di rapporti sono disponibili nel Data Lake di Adobe Experience Platform, puoi crearne uno o più [Connessioni di Customer Journey Analytics](/help/connections/overview.md) per inserire tali set di dati nel Customer Journey Analytics. All’interno di una connessione, i dati della suite di rapporti possono essere combinati con altri tipi di dati, consentendoti di creare una visualizzazione cross-channel effettiva delle esperienze dei clienti.
1. **Crea una o più visualizzazioni dati del Customer Journey Analytics.** A [visualizzazione dati](/help/data-views/data-views.md) è un contenitore specifico del Customer Journey Analytics che consente di determinare come interpretare i dati di una connessione di Customer Journey Analytics. Le visualizzazioni dati presentano diverse [opzioni di configurazione](/help/data-views/create-dataview.md) potenti per la personalizzazione dei dati presentati agli utenti all’interno di [Analysis Workspace](/help/analysis-workspace/home.md).

## Confronto tra Customer Journey Analytics e Adobe Analytics

Customer Journey Analytics e Adobe Analytics hanno alcuni punti in comune. Ad esempio, sia Customer Journey Analytics che Adobe Analytics offrono la potenza di Analysis Workspace per l’analisi a forma libera della velocità del pensiero. Tuttavia, poiché Customer Journey Analytics è un’applicazione all’interno di Adobe Experience Platform e utilizza Adobe Experience Platform per l’acquisizione dei dati, Customer Journey Analytics e Adobe Analytics differiscono in diversi modi importanti. I seguenti articoli sono utili per comprendere tali differenze:

* [Confrontare i dati di Adobe Analytics con i dati del Customer Journey Analytics](/help/troubleshooting/compare.md)
* [Supporto delle funzioni di Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Confronto della terminologia per i dati di Analytics trasmessi tramite il connettore di origine di Analytics](/help/getting-started/aa-vs-cja/terminology.md)
* [Confrontare l’elaborazione dei dati nelle funzioni di reporting di Adobe Analytics e Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Suite di rapporti virtuali, visualizzazioni dati, sandbox di Adobe Experience Platform e il connettore di origine di Analytics](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Regole di elaborazione, VISTA e classificazioni rispetto alla preparazione dati](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID e il connettore di origine di Analytics](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
