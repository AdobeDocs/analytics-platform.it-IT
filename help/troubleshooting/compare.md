---
title: Confrontare i dati del connettore di origine di Analytics con Adobe Analytics
description: Informazioni sulle differenze nei dati durante la visualizzazione di rapporti simili in Adobe Analytics e Customer Journey Analytics.
role: Developer, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: servizio query;servizio Query;sintassi SQL
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 97%

---

# Confrontare i dati del connettore di origine di Analytics con Adobe Analytics

Quando la tua organizzazione adotta Customer Journey Analytics, noterai alcune differenze nei dati tra Adobe Analytics e Customer Journey Analytics. Queste differenze sono normali e possono verificarsi per diversi motivi. Customer Journey Analytics è progettato per consentirti di migliorare alcune delle limitazioni ai dati in Adobe Analytics. Questa flessibilità può causare alcune differenze nel modo in cui Customer Journey Analytics interpreta i dati. Utilizza questo articolo per comprendere le potenziali differenze nel modo in cui Customer Journey Analytics e Adobe Analytics gestiscono i tuoi dati.

Questa pagina presuppone che tu acquisisca i dati di Adobe Analytics in Adobe Experience Platform utilizzando il [connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) e che in seguito vengano create una [connessione](/help/connections/overview.md) e una [visualizzazione dati](/help/data-views/data-views.md) in Customer Journey Analytics.

![I dati fluiscono da Adobe Analytics attraverso il connettore dati verso Adobe Experience Platform e Customer Journey Analytics utilizzando le connessioni di quest’ultimo.](assets/compare.png)

Considera i seguenti possibili motivi per cui i dati potrebbero differire tra le piattaforme di reporting:

* **Set di dati o suite di rapporti diversi**: assicurati che la suite di rapporti in Adobe Analytics e quella da cui il connettore di origine ricava i dati siano le stesse.
* **Impostazioni calendario**: le suite di rapporti in Adobe Analytics contengono un fuso orario e altre impostazioni del calendario che è possibile configurare. Analogamente, le visualizzazioni dati in Customer Journey Analytics dispongono di un’impostazione separata che è possibile controllare. Assicurati che queste impostazioni corrispondano tra i prodotti, se desideri la parità.
* **Set di dati aggiuntivi**: Customer Journey Analytics offre la possibilità di includere più set di dati all’interno di una singola connessione. Queste differenze includono set di dati aggiuntivi relativi a eventi, profili o ricerche. Questa funzionalità è un fattore chiave per differenziare Adobe Analytics da Customer Journey Analytics, consentendo agli insight di raccogliere dati su più canali.
* **Set di dati di identità unite**: Adobe consente di analizzare gli ID persona tra due set di dati, creando un nuovo set di dati contenente ID di identità unite. Questi [set di dati di identità unite](/help/stitching/overview.md) contengono dati aggiuntivi oltre a quelli offerti da una suite di rapporti di Adobe Analytics.
* **Origini dati**: Customer Journey Analytics non include alcun tipo di [origini dati](https://experienceleague.adobe.com/it/docs/analytics/import/data-sources/overview) caricate in una suite di rapporti di Adobe Analytics, incluse origini dati di riepilogo o ID di transazione.
* **Impostazioni di dimensione e metriche**: all’interno di una visualizzazione dati, ogni dimensione e metrica contiene le proprie impostazioni che possono essere modificate dall’organizzazione. Queste modifiche si applicano al momento dell’esecuzione del rapporto e sono quindi applicate retroattivamente. Le impostazioni di dimensione e metriche in Adobe Analytics modificano il modo in cui i dati vengono raccolti, rendendo tali modifiche applicabili a partire dal quel momento. Se hai modificato le impostazioni dei componenti in uno dei due prodotti, potrebbero verificarsi differenze nel reporting. Se ti concentri su una dimensione specifica, assicurati che le impostazioni di attribuzione e persistenza corrispondano tra Adobe Analytics e Customer Journey Analytics.

  >[!TIP]
  >
  >Adobe consiglia vivamente che le dimensioni in Adobe Analytics utilizzino un&#39;allocazione di &#39;[!UICONTROL Most Recent (last)]&#39; (Più recente, ultimo). Questa impostazione di allocazione consente una maggiore flessibilità di attribuzione in Customer Journey Analytics.

* **Definizione di visita**: oltre alle singole impostazioni di dimensione e metriche, la visualizzazione dati stessa contiene impostazioni che modificano radicalmente il modo in cui vengono interpretati i dati dei visitatori. Ad esempio, puoi applicare un segmento a un’intera visualizzazione dati (simile a una [suite di rapporti virtuale](https://experienceleague.adobe.com/it/docs/analytics/components/virtual-report-suites/vrs-about) in Adobe Analytics). Puoi anche modificare la definizione di durata di una visita o avviare automaticamente una nuova visita in base all’evento desiderato. Ciascuna di queste impostazioni può avere un impatto notevole sulle differenze di reporting tra Customer Journey Analytics e Adobe Analytics.

## Verifica del numero di record tra prodotti

Se tutte le impostazioni precedenti sono simili e desideri convalidare almeno il numero di record tra i prodotti, puoi utilizzare la procedura seguente:

1. In [Servizi di query](https://experienceleague.adobe.com/it/docs/experience-platform/query/home) di Adobe Experience Platform, esegui la query Totale record in base alla marca temporale seguente:

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

1. In [Feed di dati](https://experienceleague.adobe.com/it/docs/analytics/export/analytics-data-feed/data-feed-overview) di Adobe Analytics, genera file di feed per l’intervallo di date desiderato. Conteggia il numero di righe all’interno di ciascun file, identificando ed escludendo le seguenti righe:

   * `exclude_hit` non è `0` (dati esclusi da Analysis Workspace in entrambi i prodotti)
   * `hit_source` è `0`, `3`, `5`, `7`, `8`, `9` o `10` (origini dati e altri dati non hit)
   * `page_event` è `53` o `63` (hit keep-alive per contenuti multimediali in streaming)

   Le righe che corrispondono a uno dei criteri precedenti sono escluse dal flusso di lavoro di acquisizione del connettore di origine di Analytics e devono pertanto essere escluse anche durante il conteggio delle righe del feed di dati.

1. I record totali nei Servizi di query devono corrispondere al numero di righe in un feed di dati per lo stesso periodo di tempo.
