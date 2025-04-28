---
title: Panoramica delle metriche e delle dimensioni condivise
description: Utilizza lo stesso riferimento a dimensione o metrica in più visualizzazioni dati.
exl-id: 998a9f9b-cfa7-4b97-b32b-d50e35d01b39
source-git-commit: 4bb24fae7c7d53a0fde3bb2dc35ef27f91701d5a
workflow-type: tm+mt
source-wordcount: '1154'
ht-degree: 0%

---

# Panoramica delle metriche e delle dimensioni condivise

Le metriche e le dimensioni condivise forniscono una posizione centrale per gestire dimensioni e metriche che possono essere utilizzate in qualsiasi numero di visualizzazioni dati. Questi componenti sono particolarmente utili per le organizzazioni che utilizzano più visualizzazioni dati, soprattutto se tali visualizzazioni dati condividono le stesse impostazioni dei componenti. Le modifiche apportate alle metriche e alle dimensioni condivise si applicano istantaneamente in ogni visualizzazione dati a cui sono condivise. Durante la modifica di una singola visualizzazione dati, le dimensioni e le metriche condivise possono essere identificate da un&#39;icona ![Componente condiviso](/help/assets/icons/CCLibrary.svg) accanto al nome del componente.

Anche se le dimensioni e le metriche condivise consentono l’utilizzo di componenti comuni in più visualizzazioni dati, non possono essere condivise tra le connessioni.

## Flusso di lavoro

La maggior parte delle organizzazioni utilizza il seguente flusso di lavoro generale per deduplicare e gestire dimensioni e metriche nel tempo:

1. Importa componenti da ogni visualizzazione dati che potrebbero essere condivisi tra più visualizzazioni dati. Se la stessa dimensione o metrica esiste in più visualizzazioni dati, Adobe consiglia di importare tutte le istanze di quel componente. Anche se questa best practice importa duplicati, vengono importati in modo da poter essere deduplicati e mantenere i rispettivi riferimenti ai progetti Workspace.
1. Esamina tutti i componenti che utilizzano lo stesso ID componente ma con impostazioni diverse. Per ogni gruppo di componenti duplicati, seleziona le impostazioni di componente desiderate da applicare a tutti gli altri componenti che condividono tale ID componente.
1. Esamina tutti i componenti che utilizzano lo stesso ID componente e che hanno anche le stesse impostazioni. Queste dimensioni o metriche possono essere unite in modo semplice e sicuro.

## Manager [!UICONTROL Shared Metrics & Dimensions]

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Data views]** > **[!UICONTROL Shared Metrics & Dimensions]**

L’accesso a questa interfaccia utente mostra tutte le dimensioni e le metriche correnti disponibili per la condivisione tra più visualizzazioni dati. La parte in alto a destra contiene due pulsanti per aggiungere componenti a questa interfaccia:

* **[!UICONTROL Import]**: apre una finestra modale che consente di selezionare una visualizzazione dati e quindi di selezionare i componenti da rendere disponibili per la condivisione.
* **[!UICONTROL Create new]**: apre [l&#39;editor di componenti condivisi](shared-component-editor.md).

Direttamente sotto questi due pulsanti, sono visibili quattro schede panoramiche:

![Anteprima schede panoramica](assets/overview-cards.png)

* **Metriche**: numero totale di metriche disponibili per la condivisione tra le visualizzazioni dati per questa connessione. Ogni connessione può contenere fino a 10.000 metriche condivise.
* **Dimensioni**: numero totale di dimensioni disponibili per la condivisione tra le visualizzazioni dati per questa connessione. Ogni connessione può contenere fino a 10.000 dimensioni condivise.
* **Componenti duplicati da rivedere**: quando si importano componenti in più visualizzazioni dati, alcune dimensioni o metriche potrebbero condividere lo stesso ID componente. Il numero in questa scheda panoramica mostra il numero totale di componenti che hanno lo stesso ID ma impostazioni di componenti diverse. Selezionando **[!UICONTROL Review]** si abilita un filtro che consente di selezionare il componente desiderato come fonte di verità per tutti gli altri componenti con lo stesso ID.
* **Componenti disponibili per l&#39;unione**: se una dimensione o una metrica condivide lo stesso ID componente e le stesse impostazioni del componente, sono effettivamente identiche e pronte per la deduplicazione. Selezionando **[!UICONTROL Review]** si abilita un filtro che consente di unire tutti i componenti con lo stesso ID componente in un&#39;unica dimensione o metrica condivisa.

Tutte le dimensioni e le metriche condivise sono visualizzate sotto le quattro schede di panoramica.

![Anteprima dimensioni e metriche disponibili](assets/shared-metrics-dimensions.png)

* **Filtro**: seleziona l&#39;icona ![Icona filtro](../../assets/icons/Filter.svg) per mostrare o nascondere i filtri disponibili. Sono disponibili i seguenti filtri:
   * **[!UICONTROL Component type]**: visualizza solo dimensioni o solo metriche.
   * **[!UICONTROL Dataset]**: visualizza solo i componenti in cui il set di dati è incluso nelle visualizzazioni dati in cui è condiviso un componente.
   * **[!UICONTROL Data view]**: visualizza solo i componenti condivisi con tale visualizzazione dati.
   * **[!UICONTROL Created by]**: visualizza solo i componenti creati da un determinato utente.
   * **[!UICONTROL Duplicates]**: visualizza solo i componenti con lo stesso ID componente di un altro componente. Questi filtri sono identici alla revisione dei componenti tramite le schede di panoramica.
* **Ricerca**: utilizza l&#39;icona ![Icona Ricerca](../../assets/icons/Search.svg) per cercare un componente in base al nome.
* **[!UICONTROL Connection]**: elenco a discesa che modifica la [connessione](/help/connections/overview.md). Le dimensioni e le metriche condivise sono sempre specifiche per una singola connessione.
* **[!UICONTROL Customize table]**: selezionare l&#39;icona ![Personalizza icona tabella](/help/assets/icons/ColumnSetting.svg) per mostrare o nascondere le colonne nella tabella. Le opzioni disponibili includono:
   * **[!UICONTROL Field name]**: nome della dimensione o metrica condivisa. Questo campo è sempre visibile.
   * **[!UICONTROL Type]**: indica se il componente è una dimensione o una metrica. Questo campo è sempre visibile.
   * **[!UICONTROL Dataset type]**: tipo di set di dati. La maggior parte dei set di dati sono set di dati evento.
   * **[!UICONTROL Shared to data view]**: tutte le visualizzazioni dati a cui è condiviso questo componente. Questo campo è sempre visibile. Seleziona il collegamento per aprire un modale che elenca tutte le visualizzazioni dati in cui è disponibile questo componente.
   * **[!UICONTROL Datasets]**: tutti i set di dati inclusi in ogni visualizzazione dati a cui è condiviso questo componente. Seleziona il collegamento per aprire un modale che elenca tutti i set di dati per il componente.
   * **[!UICONTROL Created by]**: nome dell&#39;utente che ha creato o importato il componente nell&#39;interfaccia delle metriche e delle dimensioni condivise.
   * **[!UICONTROL Schema type]**: formato in cui sono memorizzati i dati. Alcuni esempi includono `string`, `double` o `boolean`.
   * **[!UICONTROL Component ID]**: ID componente della dimensione o metrica. Tutti i componenti che condividono lo stesso ID componente in questa interfaccia devono essere rivisti e deduplicati.
   * **[!UICONTROL Schema]**: percorso dello schema per la dimensione o la metrica. Ad esempio: `web.webPageDetails.URL`.
   * **[!UICONTROL Description]**: [descrizione](/help/data-views/component-settings/overview.md) del componente.
   * **[!UICONTROL Context labels]**: [etichette di contesto](/help/data-views/component-settings/overview.md) per il componente.
   * **[!UICONTROL Include/Exclude values]**: elenca il numero di regole specificato in [Includi/escludi valori](/help/data-views/component-settings/include-exclude-values.md).
   * **[!UICONTROL Data usage labels]**: [etichette di utilizzo dati](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) per il campo schema.
   * **[!UICONTROL Deprecated]**: indica se è impostato il flag obsoleto.
   * **[!UICONTROL Format]**: formato in cui vengono visualizzati i valori. I booleani vengono in genere visualizzati come `True | False`, le metriche come `Decimal` e così via.
   * **[!UICONTROL Metric deduplication]**: impostazioni di [deduplicazione delle metriche](/help/data-views/component-settings/metric-deduplication.md) del componente.
   * **[!UICONTROL Behavior]**: impostazioni [Comportamento](/help/data-views/component-settings/behavior.md) del componente.
   * **[!UICONTROL Attribution]**: impostazioni [Attribution](/help/data-views/component-settings/attribution.md) del componente.
   * **[!UICONTROL No value option]**: [Opzioni per nessun valore](/help/data-views/component-settings/no-value-options.md) del componente.
   * **[!UICONTROL Value bucketing]**: impostazioni del [bucket di valori](/help/data-views/component-settings/value-bucketing.md) del componente.
   * **[!UICONTROL Persistence]**: impostazioni [Persistenza](/help/data-views/component-settings/persistence.md) del componente.
   * **[!UICONTROL Lowercase]**: indica se il componente è abilitato per le lettere minuscole in base alle impostazioni [Comportamento](/help/data-views/component-settings/behavior.md) del componente.
   * **[!UICONTROL Substring]**: impostazioni [Substring](/help/data-views/component-settings/substring.md) del componente.
   * **[!UICONTROL Summary data group]**: impostazioni del [gruppo di dati di riepilogo](/help/data-views/component-settings/summary-data-group.md) del componente.
   * **[!UICONTROL Date created]**: data di creazione o importazione del componente.
   * **[!UICONTROL Last modified]**: se il componente è stato modificato dopo la creazione, la data dell&#39;ultima modifica.
* **[!UICONTROL Job history]**: selezionare l&#39;icona ![Icona Cronologia](/help/assets/icons/History.svg) per aprire una finestra modale che mostra tutte le istanze di importazione di dimensioni e metriche dalle singole visualizzazioni dati.

## Modificare i componenti o condividerli con le visualizzazioni dati

Utilizza la casella di controllo accanto a un componente per visualizzare tutte le azioni disponibili che puoi eseguire. Sono supportate selezioni multiple.

![Anteprima delle azioni disponibili](assets/smd-actions.png)

* ![Icona matita](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**: consente di aprire le dimensioni e le metriche selezionate nell&#39;[editor di componenti condivisi](shared-component-editor.md), modificando le impostazioni dei [componenti](/help/data-views/component-settings/overview.md). Quando selezioni più componenti da modificare, questi vengono tutti aperti nell’editor dei componenti. Per modificare lo stesso campo per più componenti, nell’editor componenti puoi fare clic sui componenti tenendo premuto Maiusc.
* ![Icona Condivisione](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share to data view(s)]**: apre una finestra che mostra tutte le visualizzazioni dati disponibili nella connessione selezionata. Selezionare la casella di controllo per ogni visualizzazione dati in cui si desidera rendere disponibile il componente, quindi selezionare **[!UICONTROL Share]**.
* ![Icona Annulla condivisione](/help/assets/icons/SaveTo.svg) **[!UICONTROL Unshare from data view(s)]**: apre una finestra che mostra tutte le visualizzazioni dati con cui questo componente è attualmente condiviso. Selezionare la casella di controllo per ogni visualizzazione dati da cui si desidera rimuovere la disponibilità del componente, quindi selezionare **[!UICONTROL Unshare]**.
* ![Icona duplicata](/help/assets/icons/Copy.svg) **[!UICONTROL Duplicate]**: crea una copia dei componenti selezionati. Per i componenti duplicati viene generato un nuovo ID componente.
* ![Icona Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]**: rimuove i componenti selezionati dall&#39;interfaccia. Se i componenti selezionati sono condivisi con una visualizzazione dati, non sono condivisi.
