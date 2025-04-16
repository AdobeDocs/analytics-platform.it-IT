---
description: Il Generatore di metriche calcolate fornisce un’area di lavoro per trascinare dimensioni, metriche, filtri e funzioni e creare metriche personalizzate in base alla logica gerarchica del contenitore, alle regole e agli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o metriche calcolate avanzate complesse.
title: Generare metriche calcolate
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: 53069702055e0adf7abf9061c592fb15772ded73
workflow-type: tm+mt
source-wordcount: '1536'
ht-degree: 7%

---

# Generare metriche calcolate {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Compatibilità prodotto"
>abstract="Indica dove in Customer Journey Analytics può essere utilizzata la metrica calcolata, ad esempio in Analysis Workspace, Report Builder e così via. Alcune metriche calcolate non possono essere utilizzate con la sperimentazione."
>additional-url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="Utilizzare le metriche calcolate nella sperimentazione"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="ID esterno"
>abstract="La modifica dell’ID esterno potrebbe influire sul modo in cui la metrica calcolata appare nelle origini esterne, come gli strumenti di business intelligence"

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics fornisce un’area di lavoro per trascinare e rilasciare dimensioni, metriche, segmenti e funzioni per creare metriche personalizzate in base alla logica gerarchica dei contenitori, alle regole e agli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o complesse.

## Inizio della creazione di una metrica calcolata

Puoi utilizzare il generatore di metriche calcolate per creare o modificare le metriche calcolate. Quando vengono create in questo modo, le metriche calcolate sono disponibili nell’elenco dei componenti e possono quindi essere utilizzate nei progetti di tutta l’organizzazione. In alternativa, è possibile creare rapidamente una metrica calcolata disponibile solo per il progetto in cui è stata creata, come descritto in [Creare metriche calcolate per un singolo progetto](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) in [Metriche](/help/components/apply-create-metrics.md).

Accedi al generatore di metriche calcolate per iniziare a creare una metrica calcolata disponibile nell’elenco dei componenti.

1. Accedi al generatore di metriche calcolate in uno dei seguenti modi:

   * In Analysis Workspace, apri un progetto, quindi seleziona **[!UICONTROL Components]** > **[!UICONTROL Create metric]**.
   * In Analysis Workspace, apri un progetto, quindi seleziona l&#39;icona **Plus** accanto alla sezione [!UICONTROL **Metriche**] nella barra a sinistra.
   * In [!DNL Customer Journey Analytics], vai a **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**, quindi seleziona **[!UICONTROL + Add]** nella parte superiore della pagina Metriche calcolate.

1. Continua con [Aree del generatore di metriche calcolate](#areas-of-the-calculated-metrics-builder).

## Aree del generatore di metriche calcolate

La finestra di dialogo **[!UICONTROL Calculated metric builder]** viene utilizzata per creare nuove metriche calcolate o per modificare quelle esistenti. La finestra di dialogo si chiama **[!UICONTROL New calculated metric]** o **[!UICONTROL Edit calculated metric]** per le metriche create o gestite dal gestore [[!UICONTROL Calculated metrics]](/help/components/calc-metrics/cm-workflow/cm-manager.md).

>[!BEGINTABS]

>[!TAB Generatore di metrica calcolata]

![Finestra dei dettagli delle metriche calcolate che mostra i campi e le opzioni descritti nella sezione successiva.](assets/calculated-metric-builder.png)

>[!TAB Crea o modifica metrica calcolata]

![Finestra dei dettagli delle metriche calcolate che mostra i campi e le opzioni descritti nella sezione successiva.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. Specifica i dettagli seguenti (![Obbligatorio](/help/assets/icons/Required.svg) indica i dati obbligatori):

   | Elemento | Descrizione |
   | --- | --- |
   | **[!UICONTROL Data view]** | Puoi selezionare la visualizzazione dati per la metrica calcolata.  La metrica calcolata definita è disponibile nei progetti Workspace in base alla visualizzazione dati selezionata. |
   | **[!UICONTROL Project-only metric]** | Nella parte superiore di questa finestra di dialogo viene visualizzata una casella di informazioni quando si modifica una metrica calcolata creata per un singolo progetto, come descritto in [Creare metriche calcolate per un singolo progetto](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project). <p>Se si desidera rendere disponibile questa metrica calcolata per tutti i progetti, selezionare l&#39;opzione **[!UICONTROL Make this metric available to all your projects and add it to your component list]**.</p> |
   | **[!UICONTROL Title]** ![Obbligatorio](/help/assets/icons/Required.svg) | Denomina la metrica calcolata, ad esempio `Conversion Rate`. |
   | **[!UICONTROL External ID]** ![Obbligatorio](/help/assets/icons/Required.svg) | Il nome della metrica calcolata quando si utilizza uno strumento BI esterno e l’estensione BI. Il valore viene automaticamente definito come `undefined_xxx` a meno che non venga ignorato. |
   | **[!UICONTROL Description]** | Fornire una descrizione per il segmento, ad esempio `Calculated metric to define the conversion rate.` Non è necessario descrivere la formula per la metrica calcolata in quanto la formula è già disponibile automaticamente in [!UICONTROL Summary]. |
   | **[!UICONTROL Format]** | Selezionare un formato per la metrica calcolata: è possibile selezionare tra **[!UICONTROL Decimal]**, **[!UICONTROL Time]**, **[!UICONTROL Percent]** e **[!UICONTROL Currency]**. |
   | **[!UICONTROL Decimal places]** | Specifica il numero di posizioni decimali per il formato selezionato. Abilitato solo se il formato selezionato è Decimale, Valuta e Percentuale. |
   | **[!UICONTROL Show upward trend as]** | Specificare se una tendenza verso l&#39;alto della metrica calcolata viene visualizzata come ▲ **[!UICONTROL Good (Green)]** o come ▼ **[!UICONTROL Bad (Red)]**. |
   | **[!UICONTROL Currency]** | Specifica la valuta della metrica calcolata. Abilitato solo se il formato selezionato è Valuta. |
   | **[!UICONTROL Tags]** | Organizza la metrica calcolata creando o applicando uno o più tag. Inizia a digitare per trovare i tag esistenti che puoi selezionare. Oppure premi **[!UICONTROL ENTER]** per aggiungere un nuovo tag. Seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un tag. |
   | **[!UICONTROL Preview]** | L’anteprima copre gli ultimi 90 giorni ed è un modo per verificare se la metrica è stata definita correttamente. |
   | **[!UICONTROL Summary]** | Visualizza un riepilogo della definizione della metrica calcolata. <br/>Ad esempio: ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Total Orders]** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]**. |
   | **[!UICONTROL Definition]** ![Obbligatorio](/help/assets/icons/Required.svg) | Definisci il segmento utilizzando il [Generatore di definizioni](#definition-builder). |

1. Per verificare se la definizione della metrica calcolata è corretta, utilizza **[!UICONTROL Preview]** costantemente aggiornato dei risultati della metrica calcolata. **[!UICONTROL Preview]** copre gli ultimi 90 giorni e valuta continuamente la definizione della metrica calcolata.

   **[!UICONTROL Product compatibility]** indica se la metrica calcolata può essere utilizzata nella sperimentazione. I valori possibili sono:
   * **[!UICONTROL Everywhere in Customer Journey Analytics]**: la metrica calcolata può essere utilizzata in tutto Customer Journey Analytics.
   * **[!UICONTROL Everywhere in Customer Journey Analytics (excluding experimentation)]**: la metrica calcolata può essere utilizzata in tutto Customer Journey Analytics, eccetto nel pannello Sperimentazione.

1. Seleziona:
   * **[!UICONTROL Save]** per salvare la metrica calcolata.
   * **[!UICONTROL Save As]** per salvare una copia della metrica calcolata.
   * **[!UICONTROL Cancel]** per annullare le modifiche apportate alla metrica calcolata o per annullare la creazione di una nuova metrica calcolata.


## Generatore di definizioni

Utilizza il Generatore di definizioni per trascinare e rilasciare dimensioni, metriche, segmenti e funzioni per creare metriche personalizzate in base alla logica gerarchica dei contenitori, alle regole e agli operatori. In questa costruzione puoi utilizzare metriche standard, metriche definite da Adobe, metriche calcolate, segmenti, dimensioni e funzioni. Tutti questi componenti sono disponibili dal pannello dei componenti nel generatore di metriche calcolate. Inoltre, puoi utilizzare operatori e contenitori nella definizione.

![Crea metrica calcolata](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

Solo le metriche sono definite come singoli componenti nell&#39;area **[!UICONTROL Definition]**. Tutti gli altri componenti sono definiti come contenitore, metriche di wrapping o altri contenitori. Per ulteriori informazioni, vedere [Contenitori](#containers).

### Metriche

Per aggiungere una metrica:

* Trascina un componente ![Eventi](/help/assets/icons/Event.svg) **[!UICONTROL Metrics]** dal pannello dei componenti in **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. Puoi usare ![Cerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare componenti specifici.

Quando utilizzi una metrica calcolata come parte della definizione, la metrica calcolata viene espansa.

Per modificare una metrica:

1. Selezionare ![Impostazione](/help/assets/icons/Setting.svg) in un componente metrica nell&#39;area **[!UICONTROL Definition]**.
1. Nella finestra di dialogo a comparsa puoi definire il tipo di metrica e un modello di attribuzione. Vedi [Tipo di metrica e attribuzione](m-metric-type-alloc.md).

Per eliminare una metrica:

* Selezionare ![Chiudi](/help/assets/icons/Close.svg) nella metrica.

### Operatori

Gli operatori consentono di specificare l’operatore tra componenti o contenitori. Gli operatori vengono visualizzati automaticamente tra

* due o più metriche in un contenitore,
* due o più contenitori in un contenitore,
* una o più metriche e uno o più contenitori in un contenitore.

Puoi selezionare:

| Simbolo | Operatore |
|:---:|---|
| ![Dividi](/help/assets/icons/Divide.svg) | Dividi (impostazione predefinita) |
| ![Chiudi](/help/assets/icons/Close.svg) | Moltiplica |
| ![Rimuovi](/help/assets/icons/Remove.svg) | Sottrai |
| ![Aggiungi](/help/assets/icons/Add.svg) | Add |

### Numero statico

Puoi aggiungere un numero statico alla definizione della metrica calcolata. Per aggiungere un numero statico:

* Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** dall&#39;interno di un contenitore.
* Seleziona **[!UICONTROL Static number]**. Viene visualizzato un contenitore di numeri statico.
* Selezionare [!UICONTROL *Fare clic per aggiungere un valore*] e digitare un valore.


### Contenitori

Puoi aggiungere dimensioni, segmenti e funzioni come contenitori a una definizione di metrica calcolata. Puoi anche aggiungere un contenitore generico. I contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. Qualsiasi elemento all’interno di un contenitore viene elaborato prima del componente o del contenitore successivo.


#### Contenitore di segmenti

Utilizza il concetto di contenitore di segmenti per creare una [metrica segmentata](metrics-with-segments.md). Puoi creare un contenitore di segmenti utilizzando un segmento o un segmento creato da una dimensione.

* Per aggiungere un contenitore di segmenti da una dimensione:

   1. Trascina un componente ![Dimensions](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimensions]** dal pannello dei componenti in **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. Puoi usare ![Cerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare componenti specifici.
   1. Nel popup **[!UICONTROL Create Filter from Dimension]**, definisci la condizione per il segmento. Selezionate un valore dall&#39;elenco degli operatori e selezionate un valore oppure immettete un valore. Ad esempio, **[!UICONTROL Month]** **[!UICONTROL equals]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`.
   1. Seleziona **[!UICONTROL Done]**. Contenitore di segmenti aggiunto a **[!UICONTROL Definition]**.


* Per aggiungere un contenitore di segmenti da un segmento, puoi utilizzare:

   * Trascina e rilascia un componente ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]** dal pannello dei componenti in **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. Puoi usare ![Cerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare segmenti specifici.
Automaticamente un contenitore di segmenti viene aggiunto a **[!UICONTROL Definition]**, utilizzando il nome del segmento.

   * Trascina e rilascia un componente ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filters]** dal pannello dei componenti in un contenitore generico. Il contenitore viene modificato in un contenitore di segmenti.

   * Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** dall&#39;interno di un contenitore:

      1. Seleziona **[!UICONTROL Filter]**. Contenitore di segmenti aggiunto a **[!UICONTROL Definition]**.
      1. Nel nuovo contenitore di segmenti, seleziona un segmento dal menu a discesa [!UICONTROL *Seleziona...*].

  >[!TIP]
  >
  >Puoi aggiungere più segmenti a un contenitore.

  I segmenti nel contenitore sono denominati in base al componente del segmento. Ad esempio, ![Segmentazione](/help/assets/icons/Segmentation.svg) **[!UICONTROL Web sessions]**. Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per visualizzare un popup con i dettagli sul segmento. Nel popup, seleziona ![Modifica](/help/assets/icons/Edit.svg) per modificare la definizione del segmento.

Per rimuovere un segmento da un contenitore:

* Seleziona ![Chiudi](/help/assets/icons/Close.svg) accanto al nome del segmento.

Per ulteriori dettagli ed esempi, vedi [Metriche filtrate](metrics-with-segments.md).

#### Contenitore di funzioni

Per aggiungere un contenitore di funzioni, puoi utilizzare:

* Trascina:

   1. Trascina un componente ![Function](/help/assets/icons/Effect.svg) **[!UICONTROL Functions]** dal pannello dei componenti in **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. Puoi usare ![Cerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare funzioni specifiche.
   1. Automaticamente un contenitore di funzioni viene aggiunto a **[!UICONTROL Definition]** utilizzando il nome della funzione.

* Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** dall&#39;interno di un contenitore:

   1. Seleziona **[!UICONTROL Function]**.
   1. Nel contenitore, selezionare una funzione dal menu a discesa [!UICONTROL *Seleziona...*].

Il contenitore di funzioni prende il nome dal componente di funzione. Ad esempio, ![Funzione](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT (metric)]**. Selezionare ![InfoOutline](/help/assets/icons/InfoOutline.svg) per visualizzare un popup con i dettagli sulla funzione. Selezionare **[!UICONTROL Learn more]** per ulteriori informazioni sulla funzione.

Per informazioni dettagliate su come utilizzare le funzioni e quali funzioni sono disponibili per creare una metrica calcolata, vedere [Utilizzare le funzioni](cm-using-functions.md).


#### Contenitore generico

Per aggiungere un contenitore generico:

* Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** da un contenitore
* Seleziona **[!UICONTROL Container]**. Un nuovo contenitore generico vuoto è stato aggiunto a **[!UICONTROL Definition]**. Puoi utilizzare un contenitore generico per nidificare o creare una gerarchia nella definizione della metrica calcolata.


#### Eliminare un contenitore

Per eliminare un contenitore, selezionare ![Chiudi](/help/assets/icons/Close.svg) a livello di contenitore.

>[!MORELIKETHIS]
>
>[Usare le funzioni](cm-using-functions.md)
>[Filtri](/help/components/filters/filters-overview.md)
>

