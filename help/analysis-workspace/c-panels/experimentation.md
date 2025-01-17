---
description: Scopri come analizzare i risultati dei test A/B nel pannello Sperimentazione di Customer Journey Analytics.
title: Pannello Sperimentazione
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: bf5853a1d23d6e648024016a64dc67d09da3fbb4
workflow-type: tm+mt
source-wordcount: '2130'
ht-degree: 20%

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
>abstract="Confronta diverse varianti di esperienza utente, marketing o messaggistica per determinare quale sia meglio per determinare un risultato specifico.<br/><br/>**Parametri **<br/>**Esperimento**: l’esperimento che verrà analizzato.<br>**Variante di controllo**: variante di controllo per l’esperimento selezionato.<br/>**Metrica di successo**: fino a 5 metriche di successo standard (non calcolate) per analizzare l’esperimento.<br/>**Metrica di normalizzazione**: persone, sessioni o eventi. Questa metrica (detta anche metodologia di conteggio) diventa il denominatore del calcolo dell’incremento. Questa metrica influisce anche sul modo in cui i dati vengono aggregati prima dell’applicazione del calcolo del valore di affidabilità."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*Questo articolo documenta il pannello Sperimentazione in **Customer Journey Analytics**.<br/>Consulta il [pannello Analytics for Target](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/a4t-panel) per informazioni su come analizzare le attività e le esperienze Adobe Target in **Adobe Analytics**.*

>[!ENDSHADEBOX]


Il pannello **[!UICONTROL Experimentation]** consente agli analisti di confrontare diverse esperienze utente, varianti di marketing o di messaggistica per determinare quale sia meglio per determinare un risultato specifico. Puoi valutare l’incremento e l’affidabilità di qualsiasi esperimento A/B da qualsiasi piattaforma di sperimentazione: online, offline, da soluzioni Adobe come Target o Journey Optimizer e persino da dati BYO (risorse disponibili).

Ulteriori informazioni sull&#39;integrazione [tra Adobe Customer Journey Analytics e Adobe Target](https://experienceleague.adobe.com/it/docs/target/using/integrate/cja/target-reporting-in-cja).

## Controllo degli accessi {#access}

Il pannello Sperimentazione è disponibile per l’uso da parte di tutti gli utenti del Customer Journey Analytics. Non sono necessari diritti di amministratore o altre autorizzazioni. Tuttavia, i prerequisiti richiedono azioni che solo gli amministratori possono eseguire.

## Funzioni nelle metriche calcolate

Sono disponibili due funzioni avanzate: Lift e Confidence (Incremento e affidabilità). Per ulteriori informazioni, consulta [Riferimento - Funzioni avanzate](/help/components/calc-metrics/cm-adv-functions.md).

## Prerequisiti

Per utilizzare il pannello di sperimentazione, assicurati di seguire i seguenti prerequisiti:

### Creare una connessione ai set di dati dell’esperimento

Lo schema di dati consigliato prevede che i dati della sperimentazione siano in un [array di oggetti](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/array) che contiene i dati dell&#39;esperimento e della variante in due dimensioni separate. Entrambe le dimensioni devono trovarsi in un array di oggetti **single**. Se i dati della sperimentazione sono inclusi in una singola dimensione (con dati di esperimento e variante in una stringa delimitata), puoi utilizzare l&#39;impostazione [substring](/help/data-views/component-settings/substring.md) nelle visualizzazioni dati per suddividere la dimensione in due e utilizzarla nel pannello.


Dopo che i dati della sperimentazione sono stati [acquisiti](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) in Adobe Experience Platform, [crea una connessione nel Customer Journey Analytics](/help/connections/create-connection.md) a uno o più set di dati dell&#39;esperimento.

### Aggiungere etichette di contesto nelle visualizzazioni dati

Nelle impostazioni delle visualizzazioni dati di Customer Journey Analytics, gli amministratori possono aggiungere [etichette di contesto](/help/data-views/component-settings/overview.md) a una dimensione o a una metrica e i servizi di Customer Journey Analytics come il pannello [!UICONTROL Experimentation] possono utilizzare queste etichette per i loro scopi. Per il pannello Sperimentazione vengono utilizzate due etichette predefinite:

* [!UICONTROL Experimentation Experiment]
* [!UICONTROL Experimentation Variant]

Nella visualizzazione dati che contiene dati di sperimentazione, scegli due dimensioni, una con i dati di sperimentazione e una con i dati della variante. Quindi assegna a queste dimensioni le etichette **[!UICONTROL Experimentation Experiment]** e **[!UICONTROL Experimentation Variant]**.

![Opzioni etichetta contesto per Variante sperimentazione e sperimentazione.](assets/context-label.png)

Se queste etichette non sono presenti, il pannello Sperimentazione non funziona, in quanto non ci saranno esperimenti su cui lavorare.

## Utilizzo

Per utilizzare un pannello **[!UICONTROL Experimentation]**:

1. Crea un pannello **[!UICONTROL Experimentation]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).


1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.

   >[!IMPORTANT]
   >
   >Se la configurazione necessaria nelle visualizzazioni dati del Customer Journey Analytics non è stata completata, prima di poter procedere riceverai un messaggio: [!UICONTROL Please configure the experiment and variant dimensions in Data views].
   >

### Input del pannello

Per utilizzare il pannello Sperimentazione:

1. Configura le impostazioni di input del pannello:

   ![Il pannello Sperimentazione è stato trascinato in un progetto.](assets/experiment-input.png)

   | Impostazione | Definizione |
   | --- | --- |
   | **[!UICONTROL Date Range]** | L’intervallo di date per il pannello Sperimentazione viene impostato automaticamente in base al primo evento ricevuto nel Customer Journey Analytics per l’esperimento selezionato. Se necessario, puoi limitare o espandere l’intervallo di date a un arco temporale più specifico. |
   | **[!UICONTROL Experiment]** | Un set di varianti di un’esperienza che sono state esposte agli utenti finali per determinare quale è meglio mantenere per sempre. Un esperimento è costituito da due o più varianti, una delle quali è considerata la variante di controllo. Questa impostazione è precompilata con le dimensioni a cui è stata applicata l&#39;etichetta **[!UICONTROL Experiment]** nelle visualizzazioni dati e i dati relativi alla sperimentazione degli ultimi 3 mesi. |
   | **[!UICONTROL Control variant]** | Una delle due o più modifiche nell’esperienza di un utente finale che vengono confrontate allo scopo di identificare l’alternativa migliore. Una variante deve essere selezionata come controllo; una sola variante può essere considerata come variante di controllo. Questa impostazione è precompilata con le dimensioni a cui è stata applicata l&#39;etichetta **[!UICONTROL Variant]** nelle visualizzazioni dati. Questa impostazione richiama i dati delle varianti associati all’esperimento. |
   | **[!UICONTROL Success metrics]** utenti | La metrica o le metriche con cui un utente confronta le varianti. La variante con il risultato più auspicabile per la metrica di conversione (massimo o minimo) è dichiarata la *variante con le prestazioni migliori* di un esperimento. Puoi aggiungere fino a 5 metriche. |
   | **[!UICONTROL Normalizing metric]** | Base ([!UICONTROL People], [!UICONTROL Sessions] o [!UICONTROL Events]) su cui viene eseguito un test. Ad esempio, un test può confrontare i tassi di conversione di diverse varianti in cui **[!UICONTROL Conversion rate]** è calcolato come Visualizzazione pagina |
   | **[!UICONTROL Include confidence upper/lower bounds]** | Abilita questa opzione per mostrare i limiti superiori e inferiori per i livelli di affidabilità. |


1. Seleziona **[!UICONTROL Build]**.

### Output del pannello

Il pannello Sperimentazione restituisce set completi di dati e visualizzazioni per consentirti di comprendere meglio le prestazioni degli esperimenti. Nella parte superiore del pannello, vengono fornite [visualizzazioni di riepilogo delle modifiche](../visualizations/summary-number-change.md) per ricordarti le impostazioni del pannello selezionate. In qualsiasi momento, puoi modificare il pannello selezionando l’icona Modifica a forma di matita in alto a destra.

Viene inoltre visualizzato un riepilogo testuale che indica se l’esperimento è conclusivo o meno e riassume il risultato. La conclusione si basa sulla significatività statistica (vedi [Metodologia statistica](#adobes-statistical-methodology)). Puoi visualizzare i numeri di riepilogo per la variante con le prestazioni migliori, con l&#39;incremento e l&#39;affidabilità più elevati.

Per ogni metrica di successo selezionata, vengono visualizzate una visualizzazione [tabella a forma libera](../visualizations/freeform-table/freeform-table.md) e un tasso di conversione [riga](../visualizations/line.md).

![L&#39;output della sperimentazione mostra una tabella a forma libera e una tendenza del tasso di conversione.](assets/experiment-output.png)


>[!NOTE]
>
>Al momento questo pannello non supporta l’analisi dei test A/A.

#### Interpretare i risultati

1. **L&#39;esperimento è conclusivo**: ogni volta che visualizzi il rapporto sulla sperimentazione, vengono analizzati i dati accumulati nell&#39;esperimento fino a questo punto. L&#39;analisi dichiara che un esperimento è conclusivo quando l&#39;affidabilità valida *anytime* supera una soglia del 95% per *almeno una* delle varianti. Con più di due bracci, viene applicata una correzione di Benjamini-Hochberg per la correzione per test di ipotesi multiple.

2. **Variante con prestazioni migliori**: quando un esperimento è dichiarato conclusivo, la variante con il tasso di conversione più alto è etichettata come la variante con le prestazioni migliori. Questa variante deve essere la variante di controllo o linea di base oppure una delle varianti che supera la soglia di affidabilità valida del 95% *anytime* (con correzioni Benjamini-Hochberg applicate).

3. **Tasso di conversione**: il tasso di conversione visualizzato è un rapporto tra il valore della metrica di successo e il valore della metrica di normalizzazione, vale a dire il valore della metrica di successo, il valore della funzione. Nota che questo valore può essere maggiore di 1, se la metrica non è binaria (1 o 0 per ogni unità nell’esperimento)

4. **Incremento**: il riepilogo del rapporto Esperimento mostra l&#39;Incremento rispetto alla linea di base, che è una misura del miglioramento percentuale del tasso di conversione di una determinata variante rispetto alla linea di base. Più precisamente, rappresenta la differenza di prestazioni tra una determinata variante e la linea di base, divisa per le prestazioni della linea di base, espressa in percentuale.

5. **Affidabilità**: l&#39;affidabilità valida mostrata ogni volta è una misura probabilistica della quantità di prove che dimostrano che una determinata variante è uguale alla variante di controllo. Una maggiore affidabilità indica meno prove dell’ipotesi che le varianti di controllo e non di controllo abbiano prestazioni uguali. L’affidabilità è la probabilità (espressa in percentuale) che tu abbia osservato una differenza minore nei tassi di conversione tra una determinata variante e il controllo. Mentre in realtà non vi è alcuna differenza nei veri tassi di conversione sottostanti. In termini di valori *p*, l’affidabilità visualizzata è 1 - valore *p*.

>[!NOTE]
>
>Una descrizione completa dei risultati dovrebbe considerare tutte le prove disponibili (ad esempio la progettazione dell’esperimento, le dimensioni del campione, i tassi di conversione, l’affidabilità e altri) e non solo la dichiarazione conclusiva o meno. Anche quando un risultato non è ancora conclusivo, ci possono essere prove convincenti che una variante sia diversa da un’altra (ad esempio, gli intervalli di affidabilità sono quasi non sovrapposti). Idealmente, tutte le prove statistiche, interpretate su uno spettro continuo, dovrebbero informare il processo decisionale.

## Metodologia statistica di Adobe {#statistics}

Per fornire un’inferenza statistica facilmente interpretabile e sicura, Adobe ha adottato una metodologia statistica basata sulle [sequenze di affidabilità valide in qualsiasi momento](https://arxiv.org/abs/2103.06476).

Una sequenza di affidabilità è un analogo *sequenziale* di un intervallo di affidabilità. Per capire quale sia una sequenza di affidabilità, immaginate di ripetere un esperimento cento volte. E calcola una stima della metrica di business media (ad esempio il tasso di apertura di un&#39;e-mail) e della sequenza di affidabilità al 95% associata per *ogni nuovo utente* che entra nell&#39;esperimento.

Una sequenza con affidabilità del 95% include il valore &quot;true&quot; della metrica di business in 95 dei 100 esperimenti eseguiti. (Un intervallo di affidabilità del 95% può essere calcolato una sola volta per esperimento per fornire la stessa garanzia di copertura del 95%; non con ogni nuovo utente). Le sequenze di affidabilità consentono quindi di monitorare gli esperimenti in modo continuo, senza aumentare i tassi di errore di tipo falso positivo, ovvero permettono di &quot;sbirciare&quot; nei risultati.

## Interpretare dimensioni non randomizzate {#non-randomized}

Il Customer Journey Analytics consente agli analisti di selezionare qualsiasi dimensione come esperimento. Ma come si interpreta un&#39;analisi in cui la dimensione scelta come esperimento non è quella per cui le persone sono randomizzate?

Ad esempio, considera un annuncio visualizzato da una persona. Puoi essere interessato a misurare la modifica in alcune metriche (ad esempio, ricavi medi) se decidi di mostrare le persone *ad B* invece di *ad A*. L’effetto causale della visualizzazione dell’ad B, invece dell’ad A, è di fondamentale importanza per giungere alla decisione di marketing. Questo effetto causale può essere misurato come reddito medio sull’intera popolazione, se hai sostituito lo status quo di visualizzazione dell’annuncio A con la strategia alternativa di visualizzazione dell’annuncio B.

Il test A/B è il gold standard all&#39;interno del settore per misurare obiettivamente gli effetti di tali interventi. La ragione fondamentale per cui un test A/B dà luogo a una stima causale è dovuta alla randomizzazione delle persone a ricevere una delle possibili varianti.

Consideriamo ora una dimensione che non si ottiene con la randomizzazione, per esempio, lo stato americano della persona. Le persone provengono principalmente da due stati, New York e California. I ricavi medi delle vendite di un marchio di abbigliamento invernale possono essere diversi nei due Stati a causa delle differenze nelle condizioni climatiche regionali. In una situazione del genere, le condizioni meteorologiche possono essere il vero fattore causale delle vendite di abbigliamento invernale, e non il fatto che gli stati geografici delle persone siano diversi.

Il pannello di sperimentazione nel Customer Journey Analytics consente di analizzare i dati come differenza media di ricavi per stato delle persone. In una situazione del genere, la produzione non ha un’interpretazione causale. Tuttavia, tale analisi può essere ancora interessante. Esso fornisce una stima (insieme a misure di incertezza) della differenza tra le entrate medie degli Stati delle persone.  Questo valore viene anche indicato come *Test di ipotesi statistica*. L’output di questa analisi può essere interessante, ma non necessariamente actionable. Semplicemente perché non hai randomizzato e talvolta non puoi randomizzare le persone a uno dei possibili valori della dimensione.

La figura seguente contrasta queste situazioni:

![Diagramma che mostra i dati osservazionali e l&#39;esperimento randomizzato.](assets/randomize.png)

Quando si vuole misurare l&#39;impatto dell&#39;intervento X sull&#39;esito Y, è possibile che la vera causa di entrambi sia il fattore confondente C. Se i dati non vengono ottenuti randomizzando le persone su X, l&#39;impatto è più difficile da misurare, e l&#39;analisi rende esplicitamente conto di C. La randomizzazione interrompe la dipendenza di X da C, permettendoci di misurare l&#39;effetto di X su Y senza doverci preoccupare di altre variabili.

## Utilizzare le metriche calcolate nella sperimentazione {#use-in-experimentation}

>[!NOTE]
>
>Per le organizzazioni che utilizzano sia Customer Journey Analytics che Adobe Journey Optimizer, le informazioni contenute in questa sezione si applicano anche alle funzioni di sperimentazione in Journey Optimizer.

Non tutte le metriche calcolate sono compatibili con il pannello Sperimentazione.

Le metriche calcolate che includono una delle metriche o costanti seguenti non sono compatibili con il pannello Sperimentazione:

* Metriche di base da un [set di dati di riepilogo](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/summary-data)
* Metriche di base divise o moltiplicate tra loro (ad esempio, `Revenue`/`Orders`)
* Costanti aggiunte o sottratte da una metrica di base (ad esempio, `Revenue+50`)
* Una delle metriche di base seguenti:
   * Persone

Le metriche calcolate non compatibili con il pannello Sperimentazione hanno il valore [!UICONTROL **Ovunque nel Customer Journey Analytics (esclusa la sperimentazione)**] nel campo [!UICONTROL **Compatibilità prodotto**] durante la creazione della metrica calcolata. Per informazioni sulla creazione di una metrica calcolata, vedere [Genera metriche](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

## Utilizzare le metriche calcolate nel pannello Sperimentazione

Consulta questo post di blog per informazioni sull&#39;utilizzo di [metriche calcolate nel pannello Sperimentazione](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).
