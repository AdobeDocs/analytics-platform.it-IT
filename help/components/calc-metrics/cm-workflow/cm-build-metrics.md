---
description: Scopri il generatore di metriche calcolate, che fornisce un’area di lavoro per trascinare dimensioni, metriche, segmenti e funzioni e creare metriche personalizzate in base alla logica gerarchica dei contenitori, alle regole e agli operatori.
title: Creare metriche
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1613'
ht-degree: 60%

---

# Generare metriche calcolate {#build-metrics}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Compatibilità prodotto"
>abstract="Indica dove in Customer Journey Analytics può essere utilizzata la metrica calcolata, ad esempio in Analysis Workspace, Report Builder e così via. Alcune metriche calcolate non possono essere utilizzate con la sperimentazione."
>additional-url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="Utilizzare le metriche calcolate nella sperimentazione"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="ID esterno"
>abstract="La modifica dell’ID esterno potrebbe influire sul modo in cui la metrica calcolata appare nelle origini esterne, come gli strumenti di business intelligence"

Customer Journey Analytics fornisce un’area di lavoro in cui trascinare dimensioni, metriche, segmenti e funzioni per creare metriche personalizzate basate su logica gerarchica, regole e operatori del contenitore. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o complesse.

Puoi utilizzare il generatore di metriche calcolate per creare o modificare le metriche calcolate. Quando vengono create in questo modo, le metriche calcolate sono disponibili nell’elenco dei componenti e possono quindi essere utilizzate nei progetti di tutta l’organizzazione. In alternativa, è possibile creare rapidamente una metrica calcolata disponibile solo per il progetto in cui è stata creata, nel modo descritto in [Creare metriche calcolate per un singolo progetto](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) in [Metriche](/help/components/apply-create-metrics.md).

[Creare una metrica calcolata](cm-workflow.md) descrive le diverse opzioni disponibili per creare una nuova metrica calcolata.

## Aree del generatore di metriche calcolate

La finestra di dialogo **[!UICONTROL Generatore di metriche calcolate]** viene utilizzata per creare o modificare metriche calcolate esistenti. La finestra di dialogo si chiama **[!UICONTROL Nuova metrica calcolata]** o **[!UICONTROL Modifica metrica calcolata]** per le metriche create o gestite dal gestore [[!UICONTROL Metriche calcolate]](/help/components/calc-metrics/cm-workflow/cm-manager.md).

>[!BEGINTABS]

>[!TAB Generatore di metrica calcolata]

![Finestra dei dettagli della metrica calcolata con i campi e le opzioni descritti nella sezione successiva.](assets/calculated-metric-builder.png)

>[!TAB Crea o modifica metrica calcolata]

![Finestra dei dettagli della metrica calcolata con i campi e le opzioni descritti nella sezione successiva.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. Specifica i dettagli seguenti (![Obbligatorio](/help/assets/icons/Required.svg) indica i dati obbligatori):

   | Elemento | Descrizione |
   | --- | --- |
   | **[!UICONTROL Visualizzazione dati]** | Puoi selezionare la visualizzazione dati per la metrica calcolata.  La metrica calcolata definita è disponibile nei progetti Workspace in base alla visualizzazione dati selezionata. |
   | **[!UICONTROL Metrica solo progetto]** | Nella parte superiore di questa finestra di dialogo, quando modifichi una metrica calcolata per un singolo progetto, viene visualizzata una casella di informazioni, come descritto in [Creare metriche calcolate per un singolo progetto](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project). <p>Se desideri rendere disponibile questa metrica calcolata per tutti i progetti, seleziona l&#39;opzione, **[!UICONTROL Rendi questa metrica disponibile per tutti i tuoi progetti e aggiungilo all&#39;elenco dei componenti]**.</p> |
   | **[!UICONTROL Titolo]** ![Obbligatorio](/help/assets/icons/Required.svg) | Assegna un nome alla metrica calcolata, ad esempio `Conversion Rate`. |
   | **[!UICONTROL ID esterno]** ![Richiesto](/help/assets/icons/Required.svg) | Il nome della metrica calcolata quando si utilizza uno strumento BI esterno e l’estensione BI. Il valore viene automaticamente definito come `undefined_xxx` a meno che non venga ignorato. |
   | **[!UICONTROL Descrizione]** | Fornisci una descrizione per il segmento, ad esempio `Calculated metric to define the conversion rate.` Non è necessario descrivere la formula per la metrica calcolata in quanto la formula è già disponibile automaticamente in [!UICONTROL Riepilogo]. |
   | **[!UICONTROL Formato]** | Selezionare un formato per la metrica calcolata: è possibile selezionare tra **[!UICONTROL Decimal]**, **[!UICONTROL Time]**, **[!UICONTROL Percent]** e **[!UICONTROL Currency]**. |
   | **[!UICONTROL Cifre decimali]** | Specifica il numero di posizioni decimali per il formato selezionato. Questa opzione è abilitata solo se il formato selezionato è Decimale, Valuta e Percentuale. |
   | **[!UICONTROL Mostra tendenza verso l&#39;alto come]** | Specifica se una tendenza verso l&#39;alto della metrica calcolata viene visualizzata come ▲ **[!UICONTROL Buona (verde)]** o come ▼ **[!UICONTROL Buona (rossa)]**. |
   | **[!UICONTROL Valuta]** | Specifica la valuta della metrica calcolata. Questa opzione è abilitata solo se il formato selezionato è Valuta. |
   | **[!UICONTROL Tag]** | Organizza la metrica calcolata creando o applicando uno o più tag. Inizia a digitare per trovare i tag esistenti che puoi selezionare. Oppure premi **[!UICONTROL INVIO]** per aggiungere un nuovo tag. Seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un tag. |
   | **[!UICONTROL Anteprima]** | L’anteprima copre gli ultimi 90 giorni ed è un modo per verificare se la metrica è stata definita correttamente. |
   | **[!UICONTROL Riepilogo]** | Visualizza un riepilogo della definizione della metrica calcolata. <br/>Ad esempio: ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Ordini totali]** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sessioni]**. |
   | **[!UICONTROL Definizione]** ![Obbligatorio](/help/assets/icons/Required.svg) | Definisci il segmento utilizzando il [Generatore di definizioni](#definition-builder). |

1. Per verificare se la definizione della metrica calcolata è corretta, utilizza la **[!UICONTROL Anteprima]** costantemente aggiornata dei risultati della metrica calcolata. **[!UICONTROL Anteprima]** copre gli ultimi 90 giorni e valuta continuamente la definizione della metrica calcolata.

   La **[!UICONTROL Compatibilità del prodotto]** indica se la metrica calcolata può essere utilizzata nella sperimentazione. I valori possibili sono:
   * **[!UICONTROL Ovunque in Customer Journey Analytics]**: la metrica calcolata può essere utilizzata in tutto Customer Journey Analytics.
   * **[!UICONTROL Ovunque in Customer Journey Analytics (esclusa la sperimentazione)]**: la metrica calcolata può essere utilizzata in tutto Customer Journey Analytics, eccetto nel pannello Sperimentazione.

1. Seleziona:
   * **[!UICONTROL Salva]** per salvare la metrica calcolata.
   * **[!UICONTROL Salva con nome]** per salvare una copia della metrica calcolata.
   * **[!UICONTROL Annulla]** per annullare eventuali modifiche apportate alla metrica calcolata o per annullare la creazione di una nuova metrica calcolata.


## Generatore di definizioni

Il Generatore di definizioni consente di trascinare dimensioni, metriche, segmenti e funzioni per creare metriche personalizzate basate su logica gerarchica, regole e operatori del contenitore. In tale struttura, puoi utilizzare metriche standard, metriche definite da Adobe, metriche calcolate, segmenti, dimensioni e funzioni. Tutti questi componenti sono disponibili accedendo al pannello dei componenti del generatore di metriche calcolate. Puoi inoltre inserire operatori e contenitori nella definizione.

![Creare una metrica calcolata](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

Solo le metriche sono definite come singoli componenti nell&#39;area **[!UICONTROL Definizione]**. Tutti gli altri componenti sono definiti come contenitore, metriche di wrapping o altri contenitori. Per ulteriori informazioni, consulta [Contenitori](#containers).

### Metriche

Per aggiungere una metrica:

* Trascina e rilascia un componente ![Eventi](/help/assets/icons/Event.svg) **[!UICONTROL Metriche]** dal pannello dei componenti in **[!UICONTROL Trascina e rilascia qui]** metriche, dimensioni, elementi dimensionali, segmenti e/o funzioni. Puoi usare l’opzione ![Cerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare componenti specifici.

Quando utilizzi una metrica calcolata nell’ambito della definizione, la metrica calcolata viene espansa.

Per modificare una metrica:

1. Selezionare ![Impostazione](/help/assets/icons/Setting.svg) in un componente metrica nell&#39;area **[!UICONTROL Definizione]**.
1. Nella finestra di dialogo popup puoi definire il tipo di metrica e un modello di attribuzione. Consulta [Tipo di metrica e attribuzione](m-metric-type-alloc.md).

Per eliminare una metrica:

* Seleziona ![Chiudi](/help/assets/icons/Close.svg) nella metrica.

### Operatori

Gli operatori consentono di specificare l’operatore desiderato tra componenti o contenitori. Gli operatori vengono visualizzati automaticamente tra

* due o più metriche in un contenitore,
* due o più contenitori in un contenitore,
* una o più metriche e uno o più contenitori in un contenitore.

È possibile selezionare:

| Simbolo | Operatore |
|:---:|---|
| ![Dividi](/help/assets/icons/Divide.svg) | Dividi (predefinito) |
| ![Chiudi](/help/assets/icons/Close.svg) | Moltiplica |
| ![Rimuovi](/help/assets/icons/Remove.svg) | Sottrai |
| ![Aggiungi](/help/assets/icons/Add.svg) | Add |

### Numero statico

Puoi aggiungere un numero statico alla definizione della metrica calcolata. Per aggiungere un numero statico:

* Seleziona ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) **[!UICONTROL Aggiungi]** dall&#39;interno di un contenitore.
* Selezionare **[!UICONTROL Numero statico]**. Viene visualizzato un contenitore di numeri statici.
* Seleziona [!UICONTROL *Fai clic per aggiungere un valore*] e digita un valore.


### Contenitori

Puoi aggiungere dimensioni, segmenti e funzioni come contenitori a una definizione di metrica calcolata. Puoi anche aggiungere un contenitore generico. I contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. Qualsiasi elemento all’interno di un contenitore viene elaborato prima del componente o del contenitore successivo.


#### Contenitore di segmenti

Utilizza il concetto di un contenitore di segmenti per creare una [metrica segmentata](metrics-with-segments.md). Puoi creare un contenitore di segmenti utilizzando un segmento o un segmento creato da una dimensione.

* Per aggiungere un contenitore di segmenti da una dimensione:

   1. Trascina e rilascia un componente ![Dimensioni](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimensioni]** dal pannello dei componenti in **[!UICONTROL Trascina e rilascia qui]** metriche, dimensioni, elementi dimensionali, segmenti e/o funzioni. Puoi usare ![Ricerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare componenti specifici.
   1. Nel popup **[!UICONTROL Crea segmento da Dimension]**, definisci la condizione per il segmento. Seleziona dall’elenco degli operatori un valore oppure immetti un valore. Ad esempio, **[!UICONTROL Mese]** **[!UICONTROL è uguale a]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`.
   1. Seleziona **[!UICONTROL Fine]**. Contenitore di segmenti aggiunto alla **[!UICONTROL Definizione]**.


* Per aggiungere un contenitore di segmenti da un segmento, puoi:

   * Trascina e rilascia un componente ![Segmentazione](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmenti]** dal pannello dei componenti in **[!UICONTROL Trascina e rilascia qui]** metriche, dimensioni, elementi dimensionali, segmenti e/o funzioni. Puoi utilizzare ![Ricerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare segmenti specifici.
Automaticamente un contenitore di segmenti viene aggiunto alla **[!UICONTROL Definizione]**, utilizzando il nome del segmento.

   * Trascina un componente ![Segmentazione](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmento]** dal pannello dei componenti in un contenitore generico. Il contenitore viene modificato in un contenitore di segmenti.

   * Seleziona ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) **[!UICONTROL Aggiungi]** dall&#39;interno di un contenitore:

      1. Seleziona **[!UICONTROL Segmento]**. Contenitore di segmenti aggiunto alla **[!UICONTROL Definizione]**.
      1. Nel nuovo contenitore di segmenti, seleziona un segmento dal menu a discesa [!UICONTROL *Seleziona...*].

  >[!TIP]
  >
  >Puoi aggiungere più di un segmento a un contenitore.

  I segmenti nel contenitore prendono il nome dal componente del segmento. Ad esempio, ![Segmentazione](/help/assets/icons/Segmentation.svg) **[!UICONTROL Sessioni Web]**. Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per visualizzare un popup con i dettagli sul segmento. Nel popup, seleziona ![Modifica](/help/assets/icons/Edit.svg) per modificare la definizione del segmento.

Per rimuovere un filtro da un contenitore:

* Seleziona ![Chiudi](/help/assets/icons/Close.svg) accanto al nome del segmento.

Per ulteriori dettagli ed esempi, vedi [Metriche segmentate](metrics-with-segments.md).

#### Contenitore funzione

Per aggiungere un contenitore funzione, puoi utilizzare:

* Trascina:

   1. Trascina e rilascia un componente ![Funzione](/help/assets/icons/Effect.svg) **[!UICONTROL Funzioni]** dal pannello dei componenti in **[!UICONTROL Trascina e rilascia qui]** metriche, dimensioni, elementi dimensionali, segmenti e/o funzioni. Puoi usare ![Ricerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare funzioni specifiche.
   1. Automaticamente un contenitore di funzioni viene aggiunto alla **[!UICONTROL Definizione]** utilizzando il nome della funzione.

* Seleziona ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) **[!UICONTROL Aggiungi]** dall&#39;interno di un contenitore:

   1. Selezionare **[!UICONTROL Funzione]**.
   1. Nel contenitore, selezionare una funzione dal menu a discesa [!UICONTROL *Seleziona...*].

Il contenitore funzione prende il nome dal componente funzione. ![Funzione](/help/assets/icons/Effect.svg) **[!UICONTROL RADICE QUADRATA (metrica)]**. Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per visualizzare un popup con ulteriori dettagli sulla funzione. Selezionare **[!UICONTROL Ulteriori informazioni]** per ulteriori informazioni sulla funzione.

Per informazioni dettagliate su come utilizzare le funzioni e quali funzioni sono disponibili per creare una metrica calcolata, consulta [Utilizzare le funzioni](cm-using-functions.md).


#### Contenitore generico

Per aggiungere un contenitore generico:

* Seleziona ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) **[!UICONTROL Aggiungi]** da un contenitore
* Seleziona **[!UICONTROL Contenitore]**. Un nuovo contenitore generico vuoto è stato aggiunto alla **[!UICONTROL Definizione]**. Puoi utilizzare un contenitore generico per nidificare o creare una gerarchia nella definizione della metrica calcolata.


#### Eliminare un contenitore

Per eliminare un contenitore, seleziona ![Close](/help/assets/icons/Close.svg) a livello di contenitore.

>[!MORELIKETHIS]
>
>[Usare le funzioni](cm-using-functions.md)
>[Segmenti](/help/components/segments/seg-overview.md)
>
