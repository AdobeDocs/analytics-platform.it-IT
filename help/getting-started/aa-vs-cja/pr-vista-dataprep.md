---
title: Regole di elaborazione, VISTA e classificazioni e preparazione dei dati per il connettore di origine di Analytics
description: Informazioni sulla trasformazione dei dati utilizzando le regole di elaborazione e VISTA rispetto all’utilizzo di Data Prep
source-git-commit: f6b8c5f1e8e82d0eb856b5cfed63b72c7ecfe3db
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 7%

---


# Regole di elaborazione, VISTA e classificazioni rispetto a Preparazione dati

Adobe Analytics [regole di elaborazione e regole VISTA](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) fornire un mezzo per trasformare e manipolare i dati trasmessi in Adobe Analytics [raccolta dati](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). Queste trasformazioni si verificano come parte dell’elaborazione dei dati di Adobe prima che i dati vengano memorizzati a scopo di reporting e analisi in Adobe Analytics.

[Preparazione dei dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) è uno strumento che consente di applicare mappature e trasformazioni basate su righe ai dati acquisiti in [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en). Successivamente, i dati vengono messi a disposizione delle applicazioni di Experience Platform, tra cui CJA e altri. La preparazione dei dati è integrata con molte delle piattaforme [connettori sorgente](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=it), nonché con [Connettore sorgente di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it). Questo connettore consente di acquisire i dati della suite di rapporti da Adobe Analytics a Platform.

## Ulteriore trasformazione utilizzando Data Prep {#data-prep}

I dati raccolti da e memorizzati in Adobe Analytics possono essere trasformati tramite regole di elaborazione o regole VISTA o entrambe. Tuttavia, le suite di rapporti che vengono quindi inoltrate a Platform tramite il connettore sorgente di Analytics possono essere trasformate un’altra volta utilizzando Data Prep. Ciò può essere auspicabile per una serie di scopi:

* **Risoluzione delle differenze di schema tra le suite di rapporti da utilizzare in CJA e/o RTCDP**. Ad esempio, supponiamo che la suite di rapporti A definisca `eVar1` come &quot;Termine di ricerca&quot; e la suite di rapporti B definisce `eVar2` come &quot;Termine di ricerca&quot;. È possibile utilizzare la preparazione dati per mappare i due diversi eVar in un campo comune che contiene i dati di entrambe le eVar. Ciò consente di [combinare suite di rapporti con schemi diversi](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) in [Connessione CJA](/help/connections/overview.md) o per l&#39;uso in [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=it).
* **Mappatura `eVars` campi per nomi significativi dal punto di vista semantico**. `eVars` e `props` i dati provenienti dal connettore origine di Analytics sono mappati su campi quali _\_experience.analytics.customDimensions.eVars.eVar1_. Preparazione dei dati può essere utilizzata per mappare `eVar` e `prop` campi in nuovi campi con nomi più significativi per gli utenti o con nomi corrispondenti provenienti da altre origini dati. (Questa operazione può essere eseguita anche con altri metodi, ad esempio rinominando i campi in un [Visualizzazione dati CJA](/help/data-views/create-dataview.md).)
* **Trasformazione generale dei dati**. Il Data Preparp dispone di centinaia di funzioni di mappatura che possono essere utilizzate per calcolare e calcolare nuovi campi in base ai dati provenienti dal connettore origine di Analytics. È possibile suddividere i campi delimitati in campi separati. È possibile combinare i campi. Puoi manipolare le stringhe. Puoi estrarre informazioni da un campo basato su espressioni regolari e molto altro.

## Preparazione e classificazione dei dati {#classifications}

Preparazione dei dati con crossover [classificazioni](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=it) in alcune situazioni.

Ad esempio, in un campo delimitato è possibile utilizzare Preparazione dati per suddividere tale campo in più campi singoli senza utilizzare le classificazioni. In genere, le classificazioni sono un modo per aggiungere metadati a un campo caricando un file di ricerca fornito al di fuori del flusso degli hit Analytics in arrivo.

Ad esempio, puoi caricare un file di classificazione che raggruppa gli SKU in &quot;size&quot;, &quot;brand&quot;, &quot;color&quot;, ecc. Un’altra differenza tra classificazioni e Preparazione dati è che le classificazioni si applicano ai dati _sia storicamente che in futuro_. Le mappature di Preparazione dei dati, invece, sono applicate _avanti_ ai dati dal momento in cui viene creata la mappatura.

