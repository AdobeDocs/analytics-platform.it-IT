---
title: Importazione di dati web e call center
description: Scopri come creare un set di dati che collega i dati del call center e del sito web.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 0%

---

# Importazione di dati web e call center

Il Customer Journey Analytics offre la funzionalità solida e valida per combinare set di dati di origini diverse in un unico progetto Workspace. Utilizza questa guida per capire come la tua organizzazione può combinare i dati del sito web con i dati del call center.

## Prerequisiti

* Il componente più importante per combinare questi due set di dati è un identificatore comune tra ciascuna origine di dati. Gli esempi includono un ID cliente, un&#39;e-mail con hash, nome utente di accesso o numero di telefono.
* Accesso a Adobe Experience Platform e Customer Journey Analytics
* Se il set di dati include i registri di un sistema di risposta vocale interattivo, Adobe consiglia di elaborare i dati in modo da includere solo interazioni immediate prima di importarli in Platform.
* Se il set di dati include i registri di chiamata, l’Adobe consiglia di includere le colonne seguenti:
   * Data/ora di inizio della chiamata
   * Motivo della chiamata
   * ID del call center
   * ID agente del call center
   * Durata della chiamata
   * Esito della chiamata
   * Costo della chiamata (se disponibile)
   * Eventuali metadati di chiamata aggiuntivi che la tua organizzazione desidera includere

## Importare dati web e call center in Platform

Importa i dati in Adobe Experience Platform. Consulta [Creare uno schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html) e [Inserire dati](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html) nella documentazione di Adobe Experience Platform.

Durante l’importazione di dati in Platform, seguire questi suggerimenti può aiutare a migliorare le informazioni nei rapporti risultanti:

* Assicurati che l&#39;identificatore utilizzato per collegare insieme i dati del call center e dei dati web sia formattato in modo simile.
* Includi l’origine dati in ogni set di dati. Ad esempio, includi una colonna `data_source` in ogni schema e imposta il valore di ogni evento rispettivamente su `"Web"` o `"Call center"`. <!--mapper-->

## Unisci gli ID persona

CJA richiede un identificatore comune per generare un [set di dati combinato](../connections/combined-dataset.md).

* Se i set di dati hanno già un identificatore comune su ogni evento in entrambi i set di dati, puoi saltare questo passaggio e procedere alla creazione di una connessione.
* Se uno dei set di dati ha un identificatore comune solo per alcuni eventi, puoi unire i dati utilizzando Cross-Channel Analytics. Consulta [Panoramica di Analytics cross-channel](/help/connections/cca/overview.md) per i passaggi per abilitare CCA per questi due set di dati.

## Creare una connessione in CJA

[Creare una ](/help/connections/create-connection.md) connessione in CJA.

* Se si utilizza CCA, è disponibile un nuovo set di dati uniti da utilizzare. Utilizza il campo ID unione appena creato come ID persona.
* In caso contrario, è possibile selezionare sia i set di dati web originali che quelli del call center da utilizzare nella connessione.

## Creare una visualizzazione dati

Dopo aver creato una connessione, è possibile [Creare una visualizzazione dati](/help/data-views/create-dataview.md) da utilizzare in Analysis Workspace. <!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## Creare visualizzazioni

Le seguenti visualizzazioni possono essere utilizzate per ottenere informazioni dal set di dati uniti.

### Sovrapposizione set di dati

Questa visualizzazione ti aiuta a capire come CCA unisce i dati.

1. Crea due filtri. La variabile utilizzata in questi due filtri è la stessa variabile menzionata in precedenza che riflette l&#39;origine dei dati di ciascun evento. Per ulteriori informazioni, consulta [Creare un filtro](/help/components/filters/create-filters.md) .
   * Contenitore persona in cui l’ID del set di dati è uguale ai dati web
   * Contenitore di persone in cui l’ID del set di dati è uguale ai dati del call center
2. In Analysis Workspace, trascina una visualizzazione [Venn](/help/analysis-workspace/visualizations/venn.md) sull’area di lavoro.
3. Trascina i due filtri appena creati nell’area **[!UICONTROL Add Filter]** e la metrica Persone nell’area **[!UICONTROL Add Metric]** .

La visualizzazione Venn risultante mostra il numero di persone nel set di dati che contengono sia dati del web che dei call center. Maggiore è la sovrapposizione, più persone sono rimaste unite con successo. Le aree che non si sovrappongono rappresentano le persone che risiedono esclusivamente in un set di dati o nell’altro.

### Eventi del call center degli attributi alle pagine web

Questa tabella a forma libera consente di visualizzare le pagine principali che contribuiscono agli eventi del call center. In primo luogo, accertati che le dimensioni e le metriche desiderate abbiano il modello di attribuzione corretto:

1. Trascina la dimensione che contiene i nomi delle pagine web in una visualizzazione Tabella a forma libera.
1. Sostituisci la metrica con la metrica del call center desiderata che desideri misurare la conversione.
1. Fai clic sull’icona a forma di ingranaggio vicino all’intestazione della metrica. Fai clic su **[!UICONTROL Use non-default attribution model]**.
1. Imposta il [modello di attribuzione](/help/data-views/configure-dataviews.md#Attribution-model) desiderato.

Il rapporto risultante mostra la metrica principale dai dati del call center. <!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: 

Orrr we could also use dataset ID

### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential filters, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
