---
title: Importare dati web e call center
description: Scopri come creare un set di dati che collega i dati del call center e del sito web.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 4%

---

# Importare dati web e call center

Il Customer Journey Analytics offre la funzionalità solida e valida per combinare set di dati di origini diverse in un unico progetto Workspace. Utilizza questa guida per capire come la tua organizzazione può combinare i dati del sito web con i dati del call center. Ad esempio, puoi capire quali azioni intraprende un cliente, quali contenuti visualizza e quali termini cerca prima di contattare l’assistenza clienti. Puoi quindi determinare i contenuti e gli strumenti self-service da migliorare in modo che i clienti possano risolvere meglio i problemi da soli senza dover effettuare l’accesso.

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

Importa i dati in Adobe Experience Platform. Consulta [Creare uno schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it) e [Inserire dati](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=it) nella documentazione di Adobe Experience Platform.

Durante l’importazione di dati in Platform, seguire questi suggerimenti può aiutare a migliorare le informazioni nei rapporti risultanti:

* Assicurati che l&#39;identificatore utilizzato per collegare insieme i dati del call center e dei dati web sia formattato in modo simile.
* Includi l’origine dati in ogni set di dati. Ad esempio, includi un `data_source` in ogni schema e imposta il valore di ogni evento su `"Web"` o `"Call center"`, rispettivamente. <!--mapper-->

## Unisci gli ID persona

CJA richiede un identificatore comune per generare un [set di dati combinato](/help/connections/combined-dataset.md).

* Se i set di dati hanno già un identificatore comune su ogni evento in entrambi i set di dati, puoi saltare questo passaggio e procedere alla creazione di una connessione.
* Se uno dei set di dati ha un identificatore comune solo per alcuni eventi, puoi unire i dati utilizzando Cross-Channel Analytics. Vedi [Panoramica di Analytics tra canali](/help/cca/overview.md) per i passaggi per abilitare CCA per questi due set di dati.

## Creare una connessione in CJA

[Creare una connessione](/help/connections/create-connection.md) in CJA.

* Se si utilizza CCA, è disponibile un nuovo set di dati uniti da utilizzare. Utilizza il campo ID unione appena creato come ID persona.
* In caso contrario, è possibile selezionare sia i set di dati web originali che quelli del call center da utilizzare nella connessione.

## Creare una visualizzazione dati

Dopo aver creato una connessione, è possibile [Creare una visualizzazione dati](/help/data-views/create-dataview.md) da utilizzare in Analysis Workspace. I componenti utili includono:

* Una dimensione di pagina con l’ultimo contatto e la persistenza della sessione. Puoi collegare le metriche del call center all’ultima pagina visualizzata da un cliente prima di effettuare l’accesso.
* Una metrica di chiamate che utilizza un campo schema &quot;Motivo del call center&quot; per aumentare le occorrenze. Utilizzo [Deduplicazione delle metriche](/help/data-views/component-settings/metric-deduplication.md) aumenta solo una volta per sessione.

## Creare visualizzazioni

Le seguenti visualizzazioni possono essere utilizzate per ottenere informazioni dal set di dati uniti.

### Sovrapposizione set di dati

Questa visualizzazione ti aiuta a capire come CCA unisce i dati.

1. Crea due filtri. La variabile utilizzata in questi due filtri è la stessa variabile menzionata in precedenza che riflette l&#39;origine dei dati di ciascun evento. Vedi [Creare un filtro](/help/components/filters/create-filters.md) per ulteriori informazioni.
   * Contenitore persona in cui l’ID del set di dati è uguale ai dati web
   * Contenitore di persone in cui l’ID del set di dati è uguale ai dati del call center
2. In Analysis Workspace, trascina un [Venn](/help/analysis-workspace/visualizations/venn.md) visualizzazione nell’area di lavoro.
3. Trascina i due filtri appena creati nella sezione **[!UICONTROL Add Filter]** e la metrica Persone nel **[!UICONTROL Add Metric]** area.

La visualizzazione Venn risultante mostra il numero di persone nel set di dati che contengono sia dati del web che dei call center. Maggiore è la sovrapposizione, più persone sono rimaste unite con successo. Le aree che non si sovrappongono rappresentano le persone che risiedono esclusivamente in un set di dati o nell’altro.

### Eventi del call center degli attributi alle pagine web

Questa tabella a forma libera consente di visualizzare le pagine principali che contribuiscono agli eventi del call center. In primo luogo, accertati che le dimensioni e le metriche desiderate abbiano il modello di attribuzione corretto:

1. Trascina la dimensione che contiene i nomi delle pagine web in una visualizzazione Tabella a forma libera.
1. Sostituisci la metrica con la metrica del call center desiderata che desideri misurare.
1. Fai clic sull’icona a forma di ingranaggio vicino all’intestazione della metrica. Fai clic su **[!UICONTROL Use non-default attribution model]**.
1. Imposta il valore desiderato [Modello di attribuzione](/help/analysis-workspace/attribution/models.md). Ad esempio, un modello Decadimento nel tempo con emivita di 15 minuti e un intervallo di lookback della sessione. Questo modello di attribuzione attribuisce il merito alle pagine che precedono la chiamata al call center.

Il rapporto risultante mostra le pagine principali che inviano le chiamate al call center. <!-- use case behind what we use these pages for -->

<!-- Complement with donut visualization -->

Puoi aumentare ulteriormente le informazioni con questa tabella suddividendo le chiamate per motivo o categoria.

1. Fai clic sulla freccia destra sotto la dimensione &quot;Motivo della chiamata&quot; nell’elenco dei componenti. Questa azione mostra singoli valori di dimensione.
2. Trascina i valori di dimensione desiderati sotto la metrica &quot;Chiamate&quot;, che filtra la metrica in base a ogni rispettivo motivo di chiamata.
3. Ripeti l&#39;operazione per ogni motivo di chiamata che desideri approfondire. Utilizza il filtro &quot;Tutte le sessioni&quot; per visualizzare il totale aggregato.

<!-- screenshot -->

### Visualizzazione del flusso

Puoi ottenere informazioni approfondite sulle operazioni che un cliente stava tentando di eseguire prima di utilizzare il canale del call center. Questa visualizzazione di flusso consente di comprendere i percorsi più frequenti utilizzati da un cliente per raggiungere il call center. Queste informazioni consentono di determinare i miglioramenti più efficaci che puoi apportare al tuo sito in modo che i clienti abbiano meno probabilità di effettuare l’accesso.

1. Fai clic sul pulsante **[!UICONTROL Visualizations]** a sinistra e trascina una visualizzazione di flusso sull’area di lavoro.
2. Fai clic sul pulsante **[!UICONTROL Components]** a sinistra e individua la dimensione &quot;Motivo della chiamata&quot;.
3. Fai clic sulla freccia destra accanto a questa dimensione. Questa azione mostra singoli valori di dimensione.
4. Trascina l’elemento dimensione del motivo della chiamata desiderato nella posizione centrale della visualizzazione del flusso.
5. La visualizzazione di flusso popola automaticamente i motivi di chiamata precedenti e successivi. Sostituisci il motivo della chiamata precedente con la dimensione della pagina del sito web.
6. Fai clic sull’icona a forma di ingranaggio in alto a destra della visualizzazione di flusso e modifica il contenitore di flusso in **[!UICONTROL Session]**.

### Istogramma

Quanti clienti hanno chiamato una volta, chiamato due volte o chiamato 6+? Alcune di queste persone non visitano mai il sito web. Utilizza la visualizzazione Istogramma per determinare quante persone rientrano in ciascun bucket. Per le persone che non visitano mai il sito web, vedi come possiamo incoraggiarle a self service.

1. Fai clic sul pulsante **[!UICONTROL Visualizations]** a sinistra e trascina una visualizzazione istogramma nell’area di lavoro.
2. Fai clic sul pulsante **[!UICONTROL Components]** a sinistra e trascina la metrica delle chiamate nella visualizzazione Istogramma.
3. Fai clic su **[!UICONTROL Show advanced settings]** al centro della visualizzazione e personalizza i blocchi desiderati.
4. Fai clic su **[!UICONTROL Build]**.

<!--
### Web to call, call to web

### Fallout

Fallout sessions - session

All sessions > page views metric > calls metric

All sessions > calls metric > page views

Orrr we could also use dataset ID

step 1: all sessions
step 2: 


### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential filters, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
