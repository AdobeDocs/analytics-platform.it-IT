---
title: Importare dati Web e call center
description: Scopri come creare un set di dati che collega i dati dei call center e dei siti Web.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: fd5d7ae51b51e6f608428a032319a4d7d1f45a97
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 100%

---

# Importare dati Web e call center

Customer Journey Analytics offre la preziosa e solida capacità di combinare in un unico progetto Workspace set di dati provenienti da origini diverse. Utilizza questa guida per capire come la tua organizzazione può combinare i dati dei siti Web con i dati dei call center. Ad esempio, puoi capire quali azioni intraprende un cliente, quali contenuti visualizza e quali termini cerca prima di contattare l’assistenza clienti. Puoi quindi determinare i contenuti e gli strumenti self-service da migliorare in modo che i clienti possano risolvere meglio i problemi in autonomia senza dover contattare l’assistenza.

## Prerequisiti

* Il componente più importante per combinare questi due set di dati è un identificatore comune tra ciascuna origine dati. Gli esempi includono un ID cliente, un’e-mail con hash, nome utente di accesso o numero di telefono.
* Accedere ad Adobe Experience Platform e Customer Journey Analytics
* Se il set di dati include i registri di un sistema di risposta vocale interattivo, Adobe consiglia di elaborare i dati in modo da includere solo interazioni immediate prima di importarli in Platform.
* Se il set di dati include i registri di chiamata, Adobe consiglia di includere le colonne seguenti:
   * Data/ora di inizio della chiamata
   * Motivo della chiamata
   * ID del call center
   * ID agente del call center
   * Durata della chiamata
   * Esito della chiamata
   * Costo della chiamata (se disponibile)
   * Eventuali metadati della chiamata aggiuntivi che la tua organizzazione desidera includere

## Importare dati Web e call center in Platform

Importare i dati in Adobe Experience Platform. Consulta [Creare uno schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it) e [Inserire dati](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=it) nella documentazione di Adobe Experience Platform.

Durante l’importazione dei dati in Platform, seguire questi suggerimenti può aiutarti a migliorare le informazioni nei rapporti risultanti:

* Assicurati che l’identificatore utilizzato per collegare insieme i dati del call center e i dati Web sia formattato in modo simile.
* Includi l’origine dati in ogni set di dati. Ad esempio, includi una colonna `data_source` in ogni schema e imposta il valore di ogni evento rispettivamente su `"Web"` o `"Call center"`. <!--mapper-->

## Unisci gli ID persona

CJA richiede un identificatore comune per generare un [set di dati combinato](/help/connections/combined-dataset.md).

* Se i set di dati hanno già un identificatore comune su ogni evento in entrambi i set di dati, puoi saltare questo passaggio e procedere alla creazione di una connessione.
* Se uno dei set di dati ha un identificatore comune solo per alcuni eventi, puoi unire i dati utilizzando l’Analisi cross-channel. Per i passaggi su come abilitare CCA per questi due set di dati, consulta la sezione [Panoramica dell’Analisi cross-channel](/help/cca/overview.md).

## Creare una connessione in CJA

[Crea una connessione](/help/connections/create-connection.md) in CJA.

* Se utilizzi CCA, è disponibile un nuovo set di dati uniti da utilizzare. Utilizza il campo ID unito appena creato come ID persona.
* In caso contrario, puoi selezionare sia i set di dati Web originali che quelli del call center da utilizzare nella connessione.

## Creare una visualizzazione dati

Dopo aver creato una connessione, puoi [creare una visualizzazione dati](/help/data-views/create-dataview.md) da utilizzare in Analysis Workspace. I componenti utili includono:

* Una dimensione della pagina con l’ultimo contatto e la persistenza della sessione. Puoi collegare le metriche del call center all’ultima pagina visualizzata da un cliente prima di effettuare l’accesso.
* Una metrica delle chiamate che utilizza un campo dello schema “Motivo del call center” per aumentare le occorrenze. Utilizza [Metric deduplication](/help/data-views/component-settings/metric-deduplication.md) (Deduplica delle metriche) in modo che aumenti solo una volta per sessione.

## Creare visualizzazioni

Le seguenti visualizzazioni possono essere utilizzate per ottenere informazioni dal set di dati uniti.

### Sovrapposizione del set di dati

Questa visualizzazione ti aiuta a capire come CCA unisce i dati.

1. Crea due filtri. La variabile utilizzata in questi due filtri è la stessa variabile menzionata in precedenza che riflette l’origine dati di ciascun evento. Per ulteriori informazioni, consulta la sezione [Creare un filtro](/help/components/filters/create-filters.md).
   * Contenitore Persona in cui l’ID del set di dati è uguale ai dati Web
   * Contenitore Persone in cui l’ID del set di dati è uguale ai dati del call center
2. In Analysis Workspace, trascina una visualizzazione [Venn](/help/analysis-workspace/visualizations/venn.md) nell’area di lavoro di Workspace.
3. Trascina i due filtri appena creati nell’area **[!UICONTROL Add Filter]** (Aggiungi filtro) e la metrica People (Persone) nell’area **[!UICONTROL Add Metric]** (Aggiungi metrica).

La visualizzazione Venn risultante mostra il numero di persone nel set di dati che contengono sia dati Web che i dati call center. Maggiore è la sovrapposizione, più persone sono state unite correttamente. Le aree che non si sovrappongono rappresentano le persone che risiedono esclusivamente in un set di dati o nell’altro.

### Attribuire eventi del call center alle pagine Web

Questa tabella a forma libera consente di visualizzare le pagine principali che contribuiscono agli eventi del call center. In primo luogo, accertati che le dimensioni e le metriche desiderate abbiano il modello di attribuzione corretto:

1. Trascina la dimensione che contiene i nomi delle pagine Web in una visualizzazione tabella a forma libera.
1. Sostituisci la metrica con la metrica del call center desiderata da misurare.
1. Fai clic sull’icona a forma di ingranaggio vicino all’intestazione della metrica. Fai clic su **[!UICONTROL Use non-default attribution model]** (Usa modello di attribuzione non predefinito).
1. Imposta il valore desiderato per [Attribution model](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) (modello di attribuzione) desiderato. Ad esempio, un modello Time decay (Obsolescenza) con emivita di 15 minuti e una finestra di ricerca posticipata della sessione. Questo modello di attribuzione attribuisce il merito alle pagine che precedono la chiamata al call center.

Il rapporto risultante mostra le pagine principali che inviano le chiamate al call center. <!-- use case behind what we use these pages for -->

<!-- Complement with donut visualization -->

Puoi aumentare ulteriormente le informazioni con questa tabella suddividendo le chiamate per motivo o categoria.

1. Fai clic sulla freccia destra sotto la dimensione “Call reason” (Motivo della chiamata) nell’elenco dei componenti. Questa azione mostra singoli valori dimensionali.
2. Trascina i valori dimensionali desiderati sotto la metrica “Calls” (Chiamate), che filtra la metrica in base a ogni rispettivo motivo della chiamata.
3. Ripeti l’operazione per ogni motivo della chiamata che desideri approfondire. Utilizza il filtro “All sessions” (Tutte le sessioni) per visualizzare il totale aggregato.

<!-- screenshot -->

### Visualizzazione del flusso

Puoi ottenere informazioni approfondite sulle operazioni che un cliente stava tentando di eseguire prima di utilizzare il canale del call center. Questa visualizzazione del flusso consente di comprendere i percorsi più frequenti utilizzati da un cliente per mettersi in contatto con il call center. Queste informazioni consentono di determinare i miglioramenti più efficaci che puoi apportare al tuo sito in modo che i clienti abbiano meno probabilità di rivolgersi al call center.

1. Fai clic sulla scheda **[!UICONTROL Visualizations]** (Visualizzazioni) a sinistra e trascina una visualizzazione di flusso sull’area di lavoro di Workspace.
2. Fai clic sul pulsante **[!UICONTROL Components]** (Componenti) a sinistra e individua la dimensione “Call reason” (Motivo della chiamata).
3. Fai clic sulla freccia destra accanto a questa dimensione. Questa azione mostra singoli valori dimensionali.
4. Trascina l’elemento dimensionale del motivo della chiamata desiderato nella posizione centrale della visualizzazione del flusso.
5. La visualizzazione di flusso popola automaticamente i motivi della chiamata precedenti e successivi. Sostituisci il motivo della chiamata precedente con la dimensione della pagina del sito Web.
6. Fai clic sull’icona a forma di ingranaggio in alto a destra della visualizzazione di flusso e modifica il contenitore del flusso in **[!UICONTROL Session]** (Sessione).

### Istogramma

Quanti clienti hanno chiamato una volta, due volte o più di 6 volte? Alcune di queste persone non visitano mai il sito Web. Utilizza la visualizzazione a istogramma per determinare quante persone rientrano in ciascun bucket. Per le persone che non visitano mai il sito Web, scopri come possiamo incoraggiarle a risolvere autonomamente.

1. Fai clic sulla scheda **[!UICONTROL Visualizations]** (Visualizzazioni) a sinistra e trascina una visualizzazione a istogramma sull’area di lavoro di Workspace.
2. Fai clic sul pulsante **[!UICONTROL Components]** (Componenti) a sinistra e trascina la metrica delle chiamate nella visualizzazione a istogramma.
3. Fai clic su **[!UICONTROL Show advanced settings]** (Mostra impostazioni avanzate) al centro della visualizzazione e personalizza i bucket desiderati.
4. Fai clic su **[!UICONTROL Build]** (Usa modello di attribuzione non predefinito).

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
