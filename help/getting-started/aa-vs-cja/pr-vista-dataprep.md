---
title: Regole di elaborazione, VISTA e classificazioni rispetto alla preparazione dati per il connettore di origine di Analytics
description: Scopri la trasformazione dei dati utilizzando le regole di elaborazione e VISTA rispetto all’utilizzo della preparazione dati
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
feature: Basics
source-git-commit: ff71d21235bd37da73c0b6c628c395da6cda7659
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 80%

---

# Regole di elaborazione, VISTA e classificazioni rispetto alla preparazione dati

Le [regole di elaborazione e le regole VISTA](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=it) di Adobe Analytics forniscono un mezzo per trasformare e manipolare i dati trasmessi nella [raccolta dati](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=it) di Adobe Analytics. Queste trasformazioni si verificano come parte dell’elaborazione dei dati di Adobe prima che i dati vengano memorizzati a scopo di reporting e analisi in Adobe Analytics.

La [preparazione dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) è uno strumento che consente di applicare mappature e trasformazioni basate su righe ai dati acquisiti in [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=it). Successivamente, i dati sono messi a disposizione delle applicazioni per la produzione di Experienci Platform, tra cui il Customer Journey Analytics e altri. La preparazione dati è integrata con molti dei [connettori di origine](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=it) di Platform, nonché con il [connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it). Questo connettore consente di inserire i dati della suite di rapporti da Adobe Analytics a Platform.

## Ulteriore trasformazione tramite la preparazione dati {#data-prep}

I dati raccolti da Adobe Analytics e in esso memorizzati possono essere trasformati tramite regole di elaborazione o regole VISTA oppure entrambe. Tuttavia, le suite di rapporti che vengono successivamente inoltrate a Platform tramite il connettore di origine di Analytics possono essere trasformate un’altra volta utilizzando la preparazione dati. Ciò può essere opportuno per una serie di scopi:

* **Risoluzione delle differenze di schema tra le suite di rapporti per l’utilizzo in Customer Journey Analytics e/o RTCDP**. Ad esempio, supponiamo che la suite di rapporti A definisca `eVar1` come “Termine di ricerca” e la suite di rapporti B definisca `eVar2` come “Termine di ricerca”. È possibile utilizzare la preparazione dati per mappare le due diverse eVar in un campo comune che contiene i dati di entrambe le eVar. Questo consente di: [combinare suite di rapporti con schemi diversi](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=it) in un [Connessione Customer Journey Analytics](/help/connections/overview.md) o per l’utilizzo in [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=it).
* **Mappatura dei campi `eVars` con nomi significativi dal punto di vista semantico**. `eVars` e `props` provenienti dal connettore di origine di Analytics sono mappati su campi come _\_experience.analytics.customDimensions.eVars.eVar1_. La preparazione dati può essere utilizzata per mappare i campi `eVar` e `prop` su nuovi campi con nomi più significativi per gli utenti o corrispondenti ai nomi provenienti da altre origini dati. Questa operazione può essere eseguita anche con altri metodi, ad esempio rinominando i campi in una [Visualizzazione dati Customer Journey Analytics](/help/data-views/create-dataview.md).)
* **Trasformazione generale dei dati**. La preparazione dati dispone di centinaia di funzioni di mappatura che possono essere utilizzate per calcolare nuovi campi in base ai dati provenienti dal connettore di origine di Analytics. Puoi suddividere i campi delimitati in campi separati, combinare i campi, manipolare le stringhe, estrarre informazioni da un campo basato su espressioni regolari e molto altro.

## Preparazione dati e classificazione {#classifications}

In alcune situazioni, la preparazione dati ha un crossover con le [classificazioni](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=it).

Ad esempio, in un campo delimitato puoi utilizzare la preparazione dati per suddividere tale campo in più campi singoli senza utilizzare le classificazioni. In genere, le classificazioni sono un modo per aggiungere metadati a un campo caricando un file di ricerca fornito al di fuori del flusso degli eventi di Analytics in arrivo.

Ad esempio, puoi caricare un file di classificazione che raggruppa le SKU in &quot;dimensioni&quot;, &quot;marchio&quot;, &quot;colore&quot;, ecc. Un’altra differenza tra le classificazioni e la preparazione dati è che le classificazioni si applicano ai dati _sia storicamente che in futuro_. Le mappature della preparazione dati, invece, sono applicate ai dati _in futuro_ dal momento in cui viene creata la mappatura.
