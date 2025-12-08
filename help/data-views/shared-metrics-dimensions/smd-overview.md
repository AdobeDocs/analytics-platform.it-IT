---
title: Panoramica delle metriche e delle dimensioni condivise
description: Utilizza lo stesso riferimento a dimensione o metrica in più visualizzazioni dati.
exl-id: 998a9f9b-cfa7-4b97-b32b-d50e35d01b39
source-git-commit: 1de8b8f40a7e1be0de0e6cbed5cc57ff834f2377
workflow-type: tm+mt
source-wordcount: '1282'
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

## Gestione [!UICONTROL Metriche e dimensioni condivise]

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Visualizzazioni dati]** > **[!UICONTROL Metriche e dimensioni condivise]**

L’accesso a questa interfaccia utente mostra tutte le dimensioni e le metriche correnti disponibili per la condivisione tra più visualizzazioni dati. La parte in alto a destra contiene due pulsanti per aggiungere componenti a questa interfaccia:

* **[!UICONTROL Importa]**: apre una finestra modale che consente di selezionare una visualizzazione dati e quindi di selezionare i componenti da rendere disponibili per la condivisione.
* **[!UICONTROL Crea nuovo]**: apre [Editor componenti condivisi](shared-component-editor.md).

Direttamente sotto questi due pulsanti, sono visibili quattro schede panoramiche:

![Anteprima schede panoramica](assets/overview-cards.png)

* **Metriche**: numero totale di metriche disponibili per la condivisione tra le visualizzazioni dati per questa connessione. Ogni connessione può contenere fino a 10.000 metriche condivise.
* **Dimensioni**: numero totale di dimensioni disponibili per la condivisione tra le visualizzazioni dati per questa connessione. Ogni connessione può contenere fino a 10.000 dimensioni condivise.
* **Componenti duplicati da rivedere**: quando si importano componenti in più visualizzazioni dati, alcune dimensioni o metriche potrebbero condividere lo stesso ID componente. Il numero in questa scheda panoramica mostra il numero totale di componenti che hanno lo stesso ID ma impostazioni di componenti diverse. Selezionando **[!UICONTROL Revisione]** si abilita un filtro che consente di selezionare il componente desiderato come origine di verità per tutti gli altri componenti con lo stesso ID.
* **Componenti disponibili per l&#39;unione**: se una dimensione o una metrica condivide lo stesso ID componente e le stesse impostazioni del componente, sono effettivamente identiche e pronte per la deduplicazione. Selezionando **[!UICONTROL Revisione]** si abilita un filtro che consente di unire tutti i componenti con lo stesso ID componente in un&#39;unica dimensione o metrica condivisa.

Tutte le dimensioni e le metriche condivise sono visualizzate sotto le quattro schede di panoramica.

![Anteprima dimensioni e metriche disponibili](assets/shared-metrics-dimensions.png)

* **Filtro**: seleziona l&#39;icona ![Icona filtro](../../assets/icons/Filter.svg) per mostrare o nascondere i filtri disponibili. Sono disponibili i seguenti filtri:
   * **[!UICONTROL Tipo di componente]**: visualizza solo dimensioni o solo metriche.
   * **[!UICONTROL Set di dati]**: visualizza solo i componenti in cui il set di dati è incluso nelle visualizzazioni dati in cui è condiviso un componente.
   * **[!UICONTROL Visualizzazione dati]**: visualizza solo i componenti condivisi con tale visualizzazione dati.
   * **[!UICONTROL Creato da]**: visualizza solo i componenti creati da un utente specifico.
   * **[!UICONTROL Duplicati]**: visualizza solo i componenti con lo stesso ID componente di un altro componente. Questi filtri sono identici alla revisione dei componenti tramite le schede di panoramica.
* **Ricerca**: utilizza l&#39;icona ![Icona Ricerca](../../assets/icons/Search.svg) per cercare un componente in base al nome.
* **[!UICONTROL Connessione]**: un menu a discesa che modifica la [connessione](/help/connections/overview.md). Le dimensioni e le metriche condivise sono sempre specifiche per una singola connessione.
* **[!UICONTROL Personalizza tabella]**: selezionare l&#39;icona ![Personalizza tabella](/help/assets/icons/ColumnSetting.svg) per mostrare o nascondere le colonne nella tabella. Le opzioni disponibili includono:
   * **[!UICONTROL Nome campo]**: nome della dimensione o della metrica condivisa. Questo campo è sempre visibile.
   * **[!UICONTROL Tipo]**: indica se il componente è una dimensione o una metrica. Questo campo è sempre visibile.
   * **[!UICONTROL Tipo di set di dati]**: il tipo di set di dati. La maggior parte dei set di dati sono set di dati evento.
   * **[!UICONTROL Condiviso nella visualizzazione dati]**: tutte le visualizzazioni dati a cui è condiviso questo componente. Questo campo è sempre visibile. Seleziona il collegamento per aprire un modale che elenca tutte le visualizzazioni dati in cui è disponibile questo componente.
   * **[!UICONTROL Set di dati]**: tutti i set di dati inclusi in ogni visualizzazione dati a cui è condiviso questo componente. Seleziona il collegamento per aprire un modale che elenca tutti i set di dati per il componente.
   * **[!UICONTROL Creato da]**: nome dell&#39;utente che ha creato o importato il componente nell&#39;interfaccia delle metriche e delle dimensioni condivise.
   * **[!UICONTROL Tipo di schema]**: formato in cui sono memorizzati i dati. Alcuni esempi includono `string`, `double` o `boolean`.
   * **[!UICONTROL ID componente]**: ID componente della dimensione o metrica. Tutti i componenti che condividono lo stesso ID componente in questa interfaccia devono essere rivisti e deduplicati.
   * **[!UICONTROL Schema]**: il percorso dello schema per la dimensione o la metrica. Ad esempio: `web.webPageDetails.URL`.
   * **[!UICONTROL Descrizione]**: [descrizione](/help/data-views/component-settings/overview.md) del componente.
   * **[!UICONTROL Etichette di contesto]**: [etichette di contesto](/help/data-views/component-settings/overview.md) per il componente.
   * **[!UICONTROL Includi/Escludi valori]**: elenca il numero di regole specificato in [Includi/escludi valori](/help/data-views/component-settings/include-exclude-values.md).
   * **[!UICONTROL Etichette di utilizzo dati]**: [Etichette di utilizzo dati](https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/overview) per il campo schema.
   * **[!UICONTROL Obsoleto]**: indica se il flag obsoleto è impostato.
   * **[!UICONTROL Formato]**: il formato in cui vengono visualizzati i valori. I booleani vengono in genere visualizzati come `True | False`, le metriche come `Decimal` e così via.
   * **[!UICONTROL Deduplicazione delle metriche]**: le impostazioni di [deduplicazione delle metriche](/help/data-views/component-settings/metric-deduplication.md) del componente.
   * **[!UICONTROL Comportamento]**: impostazioni [Comportamento](/help/data-views/component-settings/behavior.md) del componente.
   * **[!UICONTROL Attribuzione]**: impostazioni [Attribuzione](/help/data-views/component-settings/attribution.md) del componente.
   * **[!UICONTROL Nessuna opzione di valore]**: [Nessuna opzione di valore](/help/data-views/component-settings/no-value-options.md) del componente.
   * **[!UICONTROL Creazione di contenitori di valori]**: impostazioni [Creazione di contenitori di valori](/help/data-views/component-settings/value-bucketing.md) del componente.
   * **[!UICONTROL Persistenza]**: impostazioni [Persistenza](/help/data-views/component-settings/persistence.md) del componente.
   * **[!UICONTROL Minuscolo]**: indica se il componente è abilitato per le lettere minuscole in base alle impostazioni [Comportamento](/help/data-views/component-settings/behavior.md) del componente.
   * **[!UICONTROL Substring]**: impostazioni [Substring](/help/data-views/component-settings/substring.md) del componente.
   * **[!UICONTROL Gruppo di dati di riepilogo]**: le impostazioni del [Gruppo di dati di riepilogo](/help/data-views/component-settings/summary-data-group.md) del componente.
   * **[!UICONTROL Data di creazione]**: la data di creazione o importazione del componente.
   * **[!UICONTROL Ultima modifica]**: se il componente è stato modificato dopo la creazione, la data dell&#39;ultima modifica.
* **[!UICONTROL Cronologia processi]**: se importi o condividi un numero elevato di componenti, viene creato automaticamente un processo. Seleziona l&#39;icona ![Icona Cronologia](/help/assets/icons/History.svg) per aprire una finestra modale che mostra tutte le istanze di importazione di dimensioni e metriche da singole visualizzazioni dati. Se nessuna delle azioni di importazione o condivisione è sufficientemente grande da attivare un processo, questo pulsante non viene visualizzato.

## Modificare i componenti o condividerli con le visualizzazioni dati

Utilizza la casella di controllo accanto a un componente per visualizzare tutte le azioni disponibili che puoi eseguire. Sono supportate selezioni multiple.

![Anteprima delle azioni disponibili](assets/smd-actions.png)

* ![Icona matita](/help/assets/icons/Edit.svg) **[!UICONTROL Modifica]**: apri le dimensioni e le metriche selezionate nell&#39;[editor di componenti condivisi](shared-component-editor.md), che ti consente di modificare le [impostazioni dei componenti](/help/data-views/component-settings/overview.md). Quando selezioni più componenti da modificare, questi vengono tutti aperti nell’editor dei componenti. Per modificare lo stesso campo per più componenti, nell’editor componenti puoi fare clic sui componenti tenendo premuto Maiusc.
* ![Icona Condivisione](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Condividi su visualizzazioni dati]**: apre una finestra che mostra tutte le visualizzazioni dati disponibili nella connessione selezionata. Selezionare la casella di controllo per ogni visualizzazione dati in cui si desidera rendere disponibile il componente, quindi selezionare **[!UICONTROL Condividi]**.
* ![Icona Annulla condivisione](/help/assets/icons/SaveTo.svg) **[!UICONTROL Annulla condivisione da visualizzazioni dati]**: apre una finestra che mostra tutte le visualizzazioni dati con cui questo componente è attualmente condiviso. Selezionare la casella di controllo per ogni visualizzazione dati da cui si desidera rimuovere la disponibilità del componente, quindi selezionare **[!UICONTROL Annulla condivisione]**.
* ![Icona duplicato](/help/assets/icons/Copy.svg) **[!UICONTROL Duplicato]**: crea una copia dei componenti selezionati. Per i componenti duplicati viene generato un nuovo ID componente.
* ![Icona Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Elimina]**: rimuove i componenti selezionati dall&#39;interfaccia. Se i componenti selezionati sono condivisi con una visualizzazione dati, non sono condivisi.
