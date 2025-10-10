---
title: Confrontare i dati del connettore Source di Analytics con Adobe Analytics
description: Comprendi le differenze nei dati quando visualizzi rapporti simili in Adobe Analytics e Customer Journey Analytics.
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: servizio query;servizio Query;sintassi SQL
source-git-commit: d96404479aabe6020566e693245879b5ad4fad9c
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 4%

---

# Confrontare i dati del connettore Source di Analytics con Adobe Analytics

Quando la tua organizzazione adotta Customer Journey Analytics, è possibile notare alcune differenze nei dati tra Adobe Analytics e Customer Journey Analytics. Queste differenze sono normali e possono verificarsi per diversi motivi. Customer Journey Analytics è progettato per consentirti di migliorare alcune delle limitazioni sui dati in Adobe Analytics. Questa flessibilità può causare alcune differenze nel modo in cui Customer Journey Analytics interpreta i dati. Usa questo articolo per comprendere le potenziali differenze nel modo in cui Customer Journey Analytics e Adobe Analytics gestiscono i tuoi dati.

In questa pagina si presuppone che si acquisiscano dati di Adobe Analytics in Adobe Experience Platform utilizzando il [connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it), quindi che siano state create una [connessione](/help/connections/overview.md) e una [visualizzazione dati](/help/data-views/data-views.md) in Customer Journey Analytics.

![Il flusso di dati da Adobe Analytics attraversa il connettore dati verso Adobe Experience Platform e Customer Journey Analytics utilizzando le connessioni di quest’ultimo.](assets/compare.png)

Considera i seguenti possibili motivi per cui i dati potrebbero differire tra le piattaforme di reporting:

* **Set di dati o suite di rapporti diversi**: assicurati che la suite di rapporti in Adobe Analytics e quella da cui il connettore Source deriva i dati siano le stesse.
* **Impostazioni calendario**: le suite di rapporti in Adobe Analytics contengono un fuso orario e altre impostazioni del calendario che è possibile configurare. Analogamente, le visualizzazioni dati in Customer Journey Analytics dispongono di un&#39;impostazione separata che è possibile controllare. Assicurati che queste impostazioni corrispondano tra i prodotti, se desideri la parità.
* **Set di dati aggiuntivi**: Customer Journey Analytics offre la possibilità di includere più set di dati all&#39;interno di una singola connessione. Queste differenze includono set di dati evento aggiuntivi, set di dati di profilo o set di dati di ricerca. Questa funzionalità è un fattore chiave per differenziare Adobe Analytics da Customer Journey Analytics, consentendo ad insight di raccogliere dati su più canali.
* **Set di dati uniti**: Adobe consente di analizzare gli ID persona tra due set di dati, creando un nuovo set di dati contenente ID uniti. Questi [set di dati uniti](/help/stitching/overview.md) contengono dati aggiuntivi oltre a quelli offerti da una suite di rapporti di Adobe Analytics.
* **Origini dati**: Customer Journey Analytics non include alcun tipo di [Origini dati](https://experienceleague.adobe.com/it/docs/analytics/import/data-sources/overview) caricate in una suite di rapporti di Adobe Analytics, incluse origini dati di riepilogo o ID transazione.
* **Impostazioni Dimension e metriche**: all&#39;interno di una visualizzazione dati, ogni dimensione e metrica contiene le proprie impostazioni che possono essere modificate dall&#39;organizzazione. Queste modifiche si applicano al momento dell’esecuzione del rapporto e sono quindi applicate retroattivamente. Le impostazioni di Dimension e metriche in Adobe Analytics modificano il modo in cui i dati vengono raccolti, rendendo tali modifiche applicabili da quel momento in poi. Se hai modificato le impostazioni dei componenti in uno dei due prodotti, possono creare differenze di reporting. Se ti concentri su una dimensione specifica, assicurati che le impostazioni di attribuzione e persistenza corrispondano tra Adobe Analytics e Customer Journey Analytics.

  >[!TIP]
  >
  >Adobe consiglia vivamente che le dimensioni in Adobe Analytics utilizzino un&#39;allocazione di &#39;[!UICONTROL Most recent (last)]&#39;. Questa impostazione di allocazione consente una maggiore flessibilità di attribuzione in Customer Journey Analytics.

* **Definizione di visita**: oltre alle singole impostazioni di dimensione e metriche, la visualizzazione dati stessa contiene impostazioni che modificano radicalmente il modo in cui vengono interpretati i dati dei visitatori. Ad esempio, puoi applicare un segmento a un&#39;intera visualizzazione dati (simile a una [suite di rapporti virtuale](https://experienceleague.adobe.com/it/docs/analytics/components/virtual-report-suites/vrs-about) in Adobe Analytics). Puoi anche modificare la definizione di durata di una visita o avviare automaticamente una nuova visita in base all’evento desiderato. Ognuna di queste impostazioni può avere un impatto notevole sulle differenze di reporting tra Customer Journey Analytics e Adobe Analytics.

## Verifica del conteggio dei record tra prodotti

Se tutte le impostazioni precedenti sono simili e si desidera convalidare almeno il numero di record tra i prodotti, è possibile utilizzare la procedura seguente:

1. In Adobe Experience Platform [Query Services](https://experienceleague.adobe.com/it/docs/experience-platform/query/home), esegui la seguente query Record totali per marca temporale:

   ```sql
   SELECT
     Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) AS Day,
     Count(_id) AS Records
   FROM  {dataset}
   WHERE   timestamp >= from_utc_timestamp('{fromDate}','UTC')
     AND timestamp < from_utc_timestamp('{toDate}','UTC')
     AND timestamp IS NOT NULL
     AND enduserids._experience.aaid.id IS NOT NULL
   GROUP BY Day
   ORDER BY Day;
   ```

1. In Adobe Analytics [Feed dati](https://experienceleague.adobe.com/it/docs/analytics/export/analytics-data-feed/data-feed-overview), genera file di feed per l&#39;intervallo di date desiderato. Conteggia il numero di righe all’interno di ciascun file, identificando ed escludendo le seguenti righe:

   * `exclude_hit` non è `0` (dati esclusi da Analysis Workspace in entrambi i prodotti)
   * `hit_source` è `0`, `3`, `5`, `7`, `8`, `9` o `10` (Origini dati e altri dati non hit)
   * `page_event` è `53` o `63` (hit keep-alive per contenuti multimediali in streaming)

   Le righe che corrispondono a uno dei criteri di cui sopra sono escluse dal flusso di lavoro di acquisizione del connettore Source di Analytics e devono pertanto essere escluse anche durante il conteggio delle righe del feed di dati.

1. I record totali in Query Services devono corrispondere al numero di righe in un feed di dati per lo stesso periodo di tempo.
