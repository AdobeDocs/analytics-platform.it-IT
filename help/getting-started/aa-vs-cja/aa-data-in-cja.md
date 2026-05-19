---
title: Utilizzare la suite dati della suite di rapporti di Adobe Analytics in Customer Journey Analytics
description: Come configurare le suite di rapporti di Adobe Analytics per l’acquisizione in Adobe Experience Platform e Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
autotag-review: '2026-05-19T07:08:08.190Z'
TQID: 'https://experienceleague.adobe.com/jrPqS9duYpmQRlQlzurMAQzdtXvW-y-PAsTiyuVfd28'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: c38ed341-fab2-46df-9d72-88d8166edebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 883
ht-degree: 67%

---

# Utilizzare i dati della suite di rapporti di Adobe Analytics

I clienti Adobe Analytics possono facilmente sfruttare le loro suite di rapporti in Experience Platform e Customer Journey Analytics utilizzando il [connettore di origine Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). La discussione seguente spiega come farlo.

>[!IMPORTANT]
>
>Per eseguire l’analisi dei dati su più suite di rapporti, devi disporre del pacchetto **Seleziona**. In caso di dubbi sul pacchetto Customer Journey Analytics, contatta l’amministratore.

## Preparazione

Quando ti prepari a iniziare a utilizzare le suite di rapporti di Adobe Analytics in Adobe Experience Platform e Customer Journey Analytics, devi prendere in considerazione diverse azioni da intraprendere per preparare i dati per passare facilmente a Customer Journey Analytics. Per ulteriori informazioni, consulta la pagina seguente:

* [Evoluzione da Adobe Analytics a Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Configurare le suite di rapporti per l’acquisizione in Adobe Experience Platform e Customer Journey Analytics

Dopo aver preparato i dati, puoi iniziare a configurare le suite di rapporti da utilizzare in Adobe Experience Platform e Customer Journey Analytics.

1. **Crea un flusso di dati per ogni suite di rapporti che desideri utilizzare in Adobe Experience Platform e Customer Journey Analytics.** Il [connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it) è lo strumento che ti consente di [creare una connessione](/help/connections/create-connection.md) (ovvero un flusso di dati) tra Adobe Analytics e Adobe Experience Platform. Potrai utilizzare il connettore di origine per creare un flusso di dati per ogni suite di rapporti che desideri utilizzare in Adobe Experience Platform. Il flusso di dati crea una copia dei dati della suite di rapporti in cui lo schema è stato convertito in [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=it) per l’utilizzo da parte delle applicazioni Adobe Experience Platform, compreso Customer Journey Analytics.<p>Ogni suite di rapporti configurata con un flusso di dati tramite il connettore di origine viene memorizzata come set di dati separato nel Data Lake di Adobe Experience Platform. 13 mesi di dati storici della suite di rapporti verranno automaticamente inclusi in ogni flusso di dati e i nuovi dati confluiranno in Adobe Experience Platform su base continuativa. A partire dal 26 aprile 2023, la retrocompilazione nelle sandbox non di produzione è limitata a 3 mesi. Con il connettore di origine di Analytics non devi preoccuparti di creare lo schema in anticipo. Viene automaticamente creato uno schema standardizzato specifico per Adobe Analytics. Tuttavia, per migliorare tale schema, può essere utilizzato lo strumento [Preparazione dei dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) di Adobe Experience Platform prima che i dati vengano memorizzati nel Data Lake e resi disponibili in Customer Journey Analytics. Tieni presente che alcuni tipi di dati sono segmentati dal connettore di origine e non saranno presenti nel set di dati nel Data Lake di Adobe Experience Platform. Altre righe possono essere segmentate tra Data Lake e Customer Journey Analytics. Per maggiori dettagli, consulta [Confrontare i dati di Adobe Analytics con i dati Customer Journey Analytics](/help/troubleshooting/compare.md).
1. **Utilizza la preparazione dati per aiutarti a combinare le suite di rapporti in Customer Journey Analytics.** La preparazione dati può essere utilizzata per diversi tipi di trasformazione dati e, generalmente, i dati di Adobe Analytics vengono utilizzati per risolvere le differenze nelle mappature prop e/o eVar in più suite di rapporti in modo che possano essere combinate facilmente all’interno di Customer Journey Analytics. Per maggiori informazioni, consulta [Combinazione di suite di rapporti con schemi diversi](/help/use-cases/aa-data/combine-report-suites.md).
1. **Abilita unione** secondo necessità. Quando in Customer Journey Analytics si combinano più set di dati, le funzionalità di unione delle identità possono contribuire a risolvere ID con diversi spazi dei nomi in un singolo ID unito per una singola visualizzazione del cliente su dispositivi e canali diversi. Per maggiori informazioni, consulta [Panoramica sull’unione](../../stitching/overview.md).
1. **Creare una o più connessioni Customer Journey Analytics.** Una volta che i set di dati per le suite di rapporti sono disponibili nel Data Lake di Adobe Experience Platform, puoi creare una o più [connessioni Customer Journey Analytics](/help/connections/overview.md) per inserire tali set di dati in Customer Journey Analytics. All’interno di una connessione, i dati della suite di rapporti possono essere combinati con altri tipi di dati, consentendoti di creare una visualizzazione cross-channel effettiva delle esperienze clienti.
1. **Creare una o più visualizzazioni dati di Customer Journey Analytics.** Una [visualizzazione dati](/help/data-views/data-views.md) è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati di una connessione Customer Journey Analytics. Le visualizzazioni dati presentano diverse [opzioni di configurazione](/help/data-views/create-dataview.md) potenti per la personalizzazione dei dati presentati agli utenti all’interno di [Analysis Workspace](/help/analysis-workspace/home.md).

## Confronto tra Customer Journey Analytics e Adobe Analytics

Customer Journey Analytics e Adobe Analytics hanno alcuni punti in comune. Ad esempio, sia Customer Journey Analytics che Adobe Analytics offrono la potenza di Analysis Workspace per l’analisi a forma libera della velocità del pensiero. Tuttavia, poiché Customer Journey Analytics è un’applicazione all’interno di Adobe Experience Platform e utilizza quest’ultima per l’acquisizione dei dati, Customer Journey Analytics e Adobe Analytics differiscono in diversi modi. I seguenti articoli sono utili per comprendere tali differenze:

* [Confrontare i dati di Adobe Analytics con i dati Customer Journey Analytics](/help/troubleshooting/compare.md)
* [Supporto delle funzioni di Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Confronto della terminologia per i dati di Analytics trasmessi tramite il connettore di origine di Analytics](/help/getting-started/aa-vs-cja/terminology.md)
* [Confrontare l’elaborazione dei dati nelle funzioni di reporting di Adobe Analytics e Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Suite di rapporti virtuali, visualizzazioni dati, sandbox di Adobe Experience Platform e connettore di origine di Analytics](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Regole di elaborazione, VISTA e classificazioni rispetto alla preparazione dati](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID e il connettore di origine di Analytics](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
