---
description: Scopri come analizzare i risultati dei test A/B nel pannello Sperimentazione di Customer Journey Analytics.
title: Pannello Sperimentazione
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: 7e32ae7aa757a8ca47732416f0f883033611ea94
workflow-type: tm+mt
source-wordcount: '2129'
ht-degree: 97%

---

# Pannello Sperimentazione {#experimentation-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_experimentation_button"
>title="Sperimentazione"
>abstract="Crea un pannello per confrontare diverse esperienze utente, varianti di marketing o di messaggistica. E per determinare quale variazione è meglio per guidare un risultato specifico."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_experimentation_panel"
>title="Sperimentazione"
>abstract="Confronta diverse varianti di esperienze utente, marketing o messaggistica per determinare quale sia la migliore per determinare un risultato specifico. Specifica l’esperimento, la variante di controllo da confrontare, la metrica di successo e la metrica di normalizzazione. Facoltativamente, imposta il limite superiore e inferiore per l’affidabilità."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo descrive il pannello Sperimentazione in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Consulta il [pannello Analytics for Target](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/panels/a4t-panel) per informazioni su come analizzare le attività e le esperienze Adobe Target in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._

>[!ENDSHADEBOX]


Il pannello **[!UICONTROL Experimentation]** consente agli analisti di confrontare diverse varianti di esperienza utente, marketing o messaggistica per determinare quale sia meglio per determinare un risultato specifico. Puoi valutare l’incremento e l’affidabilità di ogni esperimento A/B da qualsiasi piattaforma di sperimentazione: online, offline, dalle soluzioni di Adobe, come Target o Journey Optimizer e persino da dati BYO (risorse disponibili).

Ulteriori informazioni sull’[integrazione tra Adobe Customer Journey Analytics e Adobe Target](https://experienceleague.adobe.com/it/docs/target/using/integrate/cja/target-reporting-in-cja).

## Controllo degli accessi {#access}

Il pannello Sperimentazione è disponibile per l’utilizzo da parte di tutti gli utenti di Customer Journey Analytics (CJA). Non sono necessari diritti di amministratore o altre autorizzazioni. Tuttavia, i prerequisiti richiedono azioni che solo gli amministratori possono eseguire.

## Funzioni nelle metriche calcolate

Sono disponibili due funzioni avanzate: Incremento e Affidabilità. Per ulteriori informazioni, consulta [Riferimento - Funzioni avanzate](/help/components/calc-metrics/cm-adv-functions.md).

## Prerequisiti

Per utilizzare il pannello di sperimentazione, assicurati di seguire i seguenti prerequisiti:

### Creare una connessione ai set di dati dell’esperimento

Lo schema di dati consigliato prevede che i dati dell’esperimento siano in un [array di oggetti](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/array) che contiene i dati dell’esperimento e della variante in due dimensioni separate. Entrambe le dimensioni devono trovarsi in un **singolo** array di oggetti. Se i dati dell’esperimento sono inclusi in una singola dimensione (con dati di esperimento e variante in una stringa delimitata), puoi utilizzare l’impostazione [sottostringa](/help/data-views/component-settings/substring.md) nelle visualizzazioni dati per dividerla in due per l’utilizzo nel pannello.


Dopo che i dati dell’esperimento sono stati [acquisiti](https://experienceleague.adobe.com/it/docs/experience-platform/ingestion/home) in Adobe Experience Platform, [crea una connessione in Customer Journey Analytics](/help/connections/create-connection.md) a uno o più set di dati dell’esperimento.

### Aggiungere etichette di contesto alle visualizzazioni dati

Nelle impostazioni delle visualizzazioni dati di Customer Journey Analytics, gli amministratori possono aggiungere a una dimensione o a una metrica [etichette di contesto](/help/data-views/component-settings/overview.md) che i servizi Customer Journey Analytics come il pannello [!UICONTROL Experimentation] possono utilizzare per i loro scopi. Per il pannello Sperimentazione vengono utilizzate due etichette predefinite:

* [!UICONTROL Experimentation Experiment]
* [!UICONTROL Experimentation Variant]

Nella visualizzazione dati che contiene dati di sperimentazione, scegli due dimensioni, una con i dati di sperimentazione e una con i dati della variante. Quindi assegna a queste dimensioni le etichette **[!UICONTROL Experimentation Experiment]** e **[!UICONTROL Experimentation Variant]**.

![Opzioni etichetta di contesto per Sperimentazione e Variante sperimentazione.](assets/context-label.png)

Se queste etichette non sono presenti, il pannello Sperimentazione non funziona, in quanto non ci saranno esperimenti su cui lavorare.

## Utilizzo

Per usare un pannello **[!UICONTROL Experimentation]**:

1. Crea un pannello **[!UICONTROL Experimentation]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).


1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.

   >[!IMPORTANT]
   >
   >Se la configurazione necessaria nelle visualizzazioni dati di Customer Journey Analytics non è stata completata, prima di poter procedere riceverai questo messaggio: [!UICONTROL Please configure the experiment and variant dimensions in Data views].
   >

### Input del pannello

Per utilizzare il pannello Sperimentazione:

1. Configura le impostazioni di input del pannello:

   ![Il pannello Sperimentazione trascinato in un progetto.](assets/experiment-input.png)

   | Impostazione | Definizione |
   | --- | --- |
   | **[!UICONTROL Date Range]** | L’intervallo di date del pannello Sperimentazione viene impostato automaticamente in base al primo evento ricevuto in Customer Journey Analytics per l’esperimento selezionato. Se necessario, puoi limitare o espandere l’intervallo di date a un arco temporale più specifico. |
   | **[!UICONTROL Experiment]** | Un set di varianti di un’esperienza che sono state esposte agli utenti finali per determinare quale è meglio mantenere. Un esperimento è costituito da due o più varianti, una delle quali è considerata la variante di controllo. Questa impostazione è precompilata con le dimensioni a cui è stata applicata l’etichetta **[!UICONTROL Experiment]** nelle visualizzazioni dati e i dati relativi alla sperimentazione degli ultimi 3 mesi. |
   | **[!UICONTROL Control variant]** | Una delle due o più modifiche nell’esperienza di un utente finale che vengono confrontate allo scopo di identificare l’alternativa migliore. Una variante deve essere selezionata come controllo; una sola variante può essere considerata come variante di controllo. Questa impostazione è precompilata con le dimensioni a cui è stata applicata l’etichetta **[!UICONTROL Variant]** nelle visualizzazioni dati. Questa impostazione richiama i dati delle varianti associati all’esperimento. |
   | **[!UICONTROL Success metrics]** ➊ | La metrica o le metriche con cui un utente confronta le varianti. La variante con il risultato più auspicabile per la metrica di conversione (più alto o più basso) è indicata come la *variante con le prestazioni migliori* di un esperimento. Puoi aggiungere fino a 5 metriche. |
   | **[!UICONTROL Normalizing metric]** ➋ | Base (**[!UICONTROL Global Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Buying Group]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL People]**, **[!UICONTROL Sessions]** o **[!UICONTROL Events]**) su cui viene eseguito un test. Ad esempio, un test può confrontare i tassi di conversione di diverse varianti in cui **[!UICONTROL Conversion rate]** è calcolato come Visualizzazione pagina. |
   | **[!UICONTROL Include confidence upper/lower bounds]** | Abilita questa opzione per mostrare i limiti superiori e inferiori per i livelli di affidabilità. |


1. Seleziona **[!UICONTROL Build]**.

### Output del pannello

Il pannello Sperimentazione restituisce set completi di dati e visualizzazioni per consentirti di comprendere meglio le prestazioni degli esperimenti. Nella parte superiore del pannello trovi le visualizzazioni [Variazione di riepilogo](../visualizations/summary-number-change.md) che ti ricordano le impostazioni del pannello selezionate. In qualsiasi momento, puoi modificare il pannello selezionando l’icona Modifica a forma di matita, in alto a destra.

Viene inoltre visualizzato un riepilogo testuale che indica se l’esperimento è conclusivo o meno e riassume il risultato. La conclusione si basa sulla rilevanza statistica (consulta [Metodologia statistica](#adobes-statistical-methodology)). Puoi visualizzare i numeri di riepilogo per la variante con le prestazioni migliori, con l’incremento e l’affidabilità più elevati.

Per ogni metrica di successo selezionata, vengono mostrate una visualizzazione [tabella a forma libera](../visualizations/freeform-table/freeform-table.md) e una [riga](../visualizations/line.md) per il tasso di conversione.

![L’output della sperimentazione mostra una tabella a forma libera e una tendenza del tasso di conversione.](assets/experiment-output.png)


>[!NOTE]
>
>Al momento questo pannello non supporta l’analisi dei test A/A.

#### Interpretare i risultati

1. **L’esperimento è conclusivo**: ogni volta che visualizzi il rapporto sulla sperimentazione, vengono analizzati i dati accumulati nell’esperimento fino a quel punto. L’analisi dichiara che un esperimento è conclusivo quando l’affidabilità valida *per qualsiasi momento* supera una soglia del 95% per *almeno una* delle varianti. Con più di due bracci, viene applicata una correzione di Benjamini-Hochberg per la regolazione dei test a ipotesi multiple.

2. **Variante con prestazioni migliori**: quando un esperimento è dichiarato conclusivo, la variante con il tasso di conversione più alto è etichettata come la “variante con le prestazioni migliori”. Tieni presente che questa variante deve essere la variante di controllo o linea di base oppure una delle varianti che supera la soglia del 95% di affidabilità valida *per qualsiasi momento* (con correzioni Benjamini-Hochberg).

3. **Tasso di conversione**: il tasso di conversione mostrato è un rapporto tra il valore della metrica di successo ➊ e il valore della metrica di normalizzazione ➋. Tieni presente che a volte questo valore può essere maggiore di 1, se la metrica non è binaria (1 o 0 per ogni unità nell’esperimento)

4. **Incremento**: il riepilogo del rapporto Esperimento mostra l’incremento rispetto alla linea di base, che è una misura del miglioramento percentuale del tasso di conversione di una determinata variante rispetto alla linea di base. Più precisamente, rappresenta la differenza di prestazioni tra una determinata variante e la linea di base, divisa per le prestazioni della linea di base, espressa in percentuale.

5. **Affidabilità**: il valore presentato di affidabilità valida per qualsiasi momento è una misura probabilistica della quantità di prove che dimostrano che una data variante è uguale alla variante di controllo. Una maggiore affidabilità indica meno prove dell’ipotesi che le varianti di controllo e non di controllo abbiano prestazioni uguali. L’affidabilità è la probabilità (espressa in percentuale) che tu abbia osservato una differenza minore nei tassi di conversione tra una determinata variante e il controllo. Mentre in realtà non vi è alcuna differenza nei veri tassi di conversione sottostanti. In termini di valori *p*, l’affidabilità visualizzata è 1 - valore *p*.

>[!NOTE]
>
>Una descrizione completa dei risultati dovrebbe considerare tutte le prove disponibili (ad esempio la progettazione di esperimenti, le dimensioni dei campioni, i tassi di conversione, l’affidabilità, ecc.), e non solo la dichiarazione conclusiva o meno. Anche quando un risultato non è ancora conclusivo, ci possono essere prove convincenti che una variante sia diversa da un’altra (ad esempio, intervalli di affidabilità quasi non sovrapposti). Idealmente, tutte le prove statistiche, interpretate su uno spettro continuo, dovrebbero informare il processo decisionale.

## Metodologia statistica di Adobe {#statistics}

Per fornire un’inferenza statistica facilmente interpretabile e sicura, Adobe ha adottato una metodologia statistica basata sulle [sequenze di affidabilità valide in qualsiasi momento](https://arxiv.org/abs/2103.06476).

Una sequenza di affidabilità è un analogico *sequenziale* di un intervallo di affidabilità. Per capire quale sia una sequenza di affidabilità, immagina di ripetere gli esperimenti cento volte. Poi, calcola una stima della metrica di business media (ad esempio il tasso di apertura di un’e-mail) e la relativa sequenza associata di affidabilità al 95% per *ogni nuovo utente* che entra nell’esperimento.

Una sequenza con affidabilità al 95% includerà il valore “vero” relativo alla metrica di business in 95 dei 100 esperimenti eseguiti. (Un intervallo di affidabilità al 95% può essere calcolato una sola volta per esperimento al fine di fornire la stessa garanzia di copertura al 95% e non con ogni singolo nuovo utente). Le sequenze di affidabilità consentono quindi di monitorare continuamente gli esperimenti, senza aumentare i tassi di errore di tipo falso positivo, ovvero permettono di “sbirciare” nei risultati.

## Interpretare dimensioni non randomizzate {#non-randomized}

Customer Journey Analytics consente agli analisti di selezionare qualsiasi dimensione come esperimento. Tuttavia, come viene interpretata un’analisi in cui la dimensione scelta come esperimento non è quella per cui le persone sono randomizzate?

Ad esempio, considera un annuncio visualizzato da una persona. Potresti essere interessato a misurare il cambiamento di una metrica (ad esempio, il ricavo medio) se decidi di mostrare alle persone *annuncio B* invece di *annuncio A*. L’effetto causale della visualizzazione dell’annuncio B invece che dell’annuncio A, è di fondamentale importanza per giungere a una decisione di marketing. Questo effetto causale può essere misurato come il ricavo medio sull’intera popolazione, se sostituisci lo status quo di mostrare l’annuncio A con la strategia alternativa di mostrare l’annuncio B.

Il test A/B è lo standard d’oro all’interno del settore per misurare obiettivamente gli effetti di tali interventi. La ragione fondamentale per cui un test A/B dà luogo a una stima causale è dovuta alla randomizzazione delle persone nel ricevere una delle possibili varianti.

Ora, considera una dimensione che non viene ottenuta tramite la randomizzazione, per esempio, lo Stato USA di una persona. Le persone provengono principalmente da due stati, New York e California. I ricavi medi delle vendite di un marchio di abbigliamento invernale relativi ai due Stati possono essere diversi a causa delle differenze climatiche di tali aree geografiche. In una situazione del genere, le condizioni climatiche possono essere il vero fattore causale delle vendite di abbigliamento invernale e non il fatto che gli stati di tali aree geografiche delle persone siano diversi.

Il pannello di sperimentazione in Customer Journey Analytics ti permette di analizzare dati come la differenza dei ricavi medi in base agli stati delle persone. In una situazione del genere, il risultato non ha un’interpretazione causale. Tuttavia, tale analisi può essere ancora interessante. Può fornire una stima (insieme a misure di incertezza) della differenza tra i ricavi medi in base agli stati delle persone.  Questo valore viene anche indicato come *Test dell’ipotesi statistica*. Il risultato di questa analisi può essere interessante, ma non necessariamente fruibile. Semplicemente perché non hai randomizzato e talvolta non puoi randomizzare le persone a uno dei possibili valori della dimensione.

L’illustrazione seguente contrasta queste situazioni:

![Un diagramma che mostra i dati di osservazione e l’esperimento randomizzato.](assets/randomize.png)

Quando desideri misurare l’impatto dell’intervento X sull’esito Y, è possibile che la vera causa di entrambi sia il fattore di confondimento C. Se i dati non vengono ottenuti randomizzando le persone su X, l’impatto è più difficile da misurare e l’analisi tiene esplicitamente conto di C. La randomizzazione interrompe la dipendenza di X da C permettendo di misurare l’effetto di X su Y, senza dover essere preoccupati sulle altre variabili.

## Utilizzare le metriche calcolate nella sperimentazione {#use-in-experimentation}

>[!NOTE]
>
>Per le organizzazioni che utilizzano sia Customer Journey Analytics che Adobe Journey Optimizer, le informazioni contenute in questa sezione vengono applicate anche alle funzioni di sperimentazione all’interno di Journey Optimizer.

Non tutte le metriche calcolate sono compatibili con il pannello Sperimentazione.

Le metriche calcolate che includono una delle metriche o costanti seguenti non sono compatibili con il pannello Sperimentazione:

* Metriche di base da un [set di dati di riepilogo](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/summary-data)
* Metriche di base divise tra loro o moltiplicate insieme (ad esempio, `Revenue`/`Orders`)
* Costanti aggiunte o sottratte da una metrica di base (ad esempio, `Revenue+50`)
* Una qualsiasi delle metriche di base seguenti:
   * Persone

Le metriche calcolate non compatibili con il pannello Sperimentazione hanno il valore [!UICONTROL **Ovunque in Customer Journey Analytics (esclusa la sperimentazione)**] nel campo [!UICONTROL **Compatibilità prodotto**] durante la creazione della metrica calcolata. Per informazioni sulla creazione di una metrica calcolata, consulta [Genera metriche](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

## Utilizzare le metriche calcolate nel pannello Sperimentazione

Consulta questo post di blog per informazioni sull’[utilizzo di metriche calcolate nel pannello Sperimentazione](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).

>[!MORELIKETHIS]
>[Padroneggiare la sperimentazione in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/mastering-adobe-customer-journey-analytics-experimentation-your/ba-p/732338)
>
