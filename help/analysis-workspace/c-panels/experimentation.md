---
description: Scopri come analizzare i risultati dei test A/B nel pannello Sperimentazione di CJA.
title: Pannello Sperimentazione
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '1785'
ht-degree: 74%

---

# Pannello Sperimentazione

Il pannello **[!UICONTROL Experimentation]** consente agli analisti di confrontare diverse varianti di esperienza utente, marketing o messaggistica per determinare quale sia meglio per determinare un risultato specifico. Puoi valutare l’incremento e l’affidabilità di qualsiasi esperimento A/B da qualsiasi piattaforma di sperimentazione: online, offline, dalle soluzioni di Adobe, Adobe Journey Optimizer e persino da dati BYO (risorse disponibili).

>[!IMPORTANT]
>
>A questo punto, i dati di [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=it) (A4T) introdotti in Adobe Experience Platform tramite il connettore di origine di Analytics **non possono** essere analizzati nel pannello [!UICONTROL Experimentation]. Prevediamo una soluzione a questo limite nel 2023.

## Controllo degli accessi {#access}

Il pannello Sperimentazione è disponibile per l’utilizzo da parte di tutti gli utenti di Customer Journey Analytics (CJA). Non sono necessari diritti di amministratore o altre autorizzazioni. Tuttavia, la configurazione (passaggi 1 e 2 di seguito) richiede azioni che solo gli amministratori possono eseguire.

## Nuove funzioni nelle metriche calcolate {#functions}

Sono state aggiunte due nuove funzioni avanzate: [!UICONTROL Lift] e [!UICONTROL Confidence]. Per ulteriori informazioni, consulta [Riferimento - Funzioni avanzate](/help/components/calc-metrics/cm-adv-functions.md).

## Passaggio 1: creare una connessione per i set di dati dell’esperimento {#connection}

Lo schema di dati consigliato prevede che i dati dell’esperimento siano in un [array Oggetto](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/array.html?lang=it) che contiene i dati dell’esperimento e della variante in due dimensioni separate. Se i dati dell’esperimento sono inclusi in una singola dimensione con dati di esperimento e variante in una stringa delimitata, puoi utilizzare l’impostazione [sottostringa](/help/data-views/component-settings/substring.md) nelle visualizzazioni dati per dividerle in due e utilizzarle nel pannello.

Dopo che i dati dell’esperimento sono stati [acquisiti](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=it) in Adobe Experience Platform, [crea una connessione in CJA](/help/connections/create-connection.md) a uno o più set di dati per l’esperimento.

## Passaggio 2: aggiungere etichette di contesto alle visualizzazioni dati {#contect-labels}

Nelle impostazioni delle visualizzazioni dati di CJA, gli amministratori possono aggiungere [etichette di contesto](/help/data-views/component-settings/overview.md) a una dimensione o a una metrica e i servizi CJA come il pannello [!UICONTROL Experimentation] possono utilizzare tali etichette per i loro scopi. Per il pannello Sperimentazione vengono utilizzate due etichette predefinite:

* [!UICONTROL Experimentation Experiment]
* [!UICONTROL Experimentation Variant]

Nella visualizzazione dati che contiene dati di sperimentazione, scegli due dimensioni, una con i dati di sperimentazione e una con i dati della variante. Quindi assegna a queste dimensioni le etichette **[!UICONTROL Experiment]** e **[!UICONTROL Variant]**.

![etichetta di contesto](assets/context-label.png)

Se queste etichette non sono presenti, il pannello Sperimentazione non funziona, in quanto non ci saranno esperimenti su cui lavorare.

## Passaggio 3: configurare il pannello Sperimentazione {#configure}

1. Nell’area di lavoro di CJA, trascina il pannello Sperimentazione in un progetto.

![pannello sperimentazione](assets/experiment.png)

>[!IMPORTANT]
>Se la configurazione necessaria nelle visualizzazioni dati di CJA non è stata completata, prima di poter procedere riceverai un messaggio: “[!UICONTROL Please configure the experiment and variant dimensions in Data Views]”.

1. Configura le impostazioni di input del pannello.

   | Impostazione | Definizione |
   | --- | --- |
   | **[!UICONTROL Experiment]** | Un set di varianti di un’esperienza che sono state esposte agli utenti finali per determinare quale è meglio mantenere per sempre. Un esperimento è costituito da due o più varianti, una delle quali è considerata la variante di controllo. Questa impostazione è precompilata con le dimensioni a cui è stata applicata l’etichetta **[!UICONTROL Experiment]** nelle visualizzazioni dati e i dati relativi all’esperimento degli ultimi 3 mesi. |
   | **[!UICONTROL Control Variant]** | Una delle due o più modifiche nell’esperienza di un utente finale che vengono confrontate allo scopo di identificare l’alternativa migliore. Una variante deve essere selezionata come controllo; una sola variante può essere considerata come variante di controllo. Questa impostazione è precompilata con le dimensioni a cui è stata applicata l’etichetta **[!UICONTROL Variant]** nelle visualizzazioni dati. Questa impostazione richiama i dati delle varianti associati all’esperimento. |
   | **[!UICONTROL Success Metrics]** | La metrica o le metriche con cui un utente confronta le varianti. La variante con il risultato più auspicabile per la metrica di conversione (più alto o più basso) è indicata come la “variante con le prestazioni migliori” di un esperimento. Puoi aggiungere fino a 5 metriche. |
   | **[!UICONTROL Normalizing Metric]** | La base ([!UICONTROL People], [!UICONTROL Sessions] oppure [!UICONTROL Events]) su cui verrà eseguito un test. Ad esempio, un test può confrontare i tassi di conversione di diverse varianti in cui il valore **[!UICONTROL Conversion rate]** è calcolato come **[!UICONTROL Conversions per session]** o **[!UICONTROL Conversions per person]**. |
   | **[!UICONTROL Date Range]** | L’intervallo di date viene impostato automaticamente in base al primo evento ricevuto in CJA per l’esperimento selezionato. Se necessario, puoi limitare o espandere l’intervallo di date a un intervallo temporale più specifico. |

1. Fai clic su **[!UICONTROL Build]**.

## Passaggio 4: visualizzare l’output del pannello {#view}

Il pannello Sperimentazione restituisce set completi di dati e visualizzazioni per consentirti di comprendere meglio le prestazioni degli esperimenti. Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni selezionate per il pannello. In qualsiasi momento, puoi modificare il pannello facendo clic sull’icona Modifica a forma di matita, in alto a destra.

Viene inoltre visualizzato un riepilogo testuale che indica se l’esperimento è conclusivo o meno e riassume il risultato. La conclusione si basa sulla rilevanza statistica. Vedi “Metodologia statistica” di seguito. Puoi visualizzare i numeri di riepilogo per la variante con le prestazioni migliori, con i valori di incremento e affidabilità più elevati.

Per ogni metrica di successo selezionata, verrà visualizzata una tabella a forma libera e una tendenza del tasso di conversione.

![output dell’esperimento](assets/exp-output1.png)

Il grafico [!UICONTROL Line] fornisce le prestazioni di [!UICONTROL Control] rispetto a [!UICONTROL Control Variant]:

![output grafico a linee](assets/exp-output2.png)

>[!NOTE]
>
>Al momento questo pannello non supporta l’analisi dei test A/A.

## Passaggio 5: interpretare i risultati {#interpret}

1. **L’esperimento è conclusivo**: ogni volta che visualizzi il rapporto sulla sperimentazione, Adobe analizza i dati accumulati nell’esperimento fino a questo punto e dichiarerà un esperimento “Conclusivo” se la soglia di affidabilità valida supera il 95% per *almeno una* delle varianti (applicando una correzione Bonferroni in presenza di più di due bracci, per test con più ipotesi).

2. **Variante con prestazioni migliori**: quando un esperimento è dichiarato conclusivo, la variante con il tasso di conversione più alto è etichettata come la “variante con le prestazioni migliori”. Questa variante deve essere la variante di controllo o linea di base oppure una delle varianti che supera la soglia del 95% di affidabilità valida in qualsiasi momento (con correzioni Bonferroni).

3. **Tasso di conversione**: il tasso di conversione mostrato è un rapporto tra il valore della metrica di successo e il valore della metrica di normalizzazione. Tieni presente che a volte questo può essere maggiore di 1, se la metrica non è binaria (1 o 0 per ogni unità nell’esperimento)

4. **Incremento**: il riepilogo del rapporto Esperimento mostra l’Incremento rispetto alla linea di base, che è una misura del miglioramento percentuale del tasso di conversione di una determinata variante rispetto alla linea di base. Più precisamente, rappresenta la differenza di prestazioni tra una determinata variante e la linea di base, divisa per le prestazioni della linea di base, espressa in percentuale.

5. **Affidabilità**: il valore presentato di affidabilità valida per qualsiasi momento è una misura probabilistica della quantità di prove che dimostrano che una data variante è uguale alla variante di controllo. Una maggiore affidabilità indica meno prove dell’ipotesi che le varianti di controllo e non di controllo abbiano prestazioni uguali. Più precisamente, l’affidabilità visualizzata rappresenta la probabilità (espressa in percentuale) di osservare una differenza minore nei tassi di conversione tra una data variante e il controllo, se in realtà non vi è alcuna differenza negli effettivi tassi di conversione sottostanti. In termini di valori *p*, l’affidabilità visualizzata è 1 - valore *p*.

>[!NOTE]
>
>Una descrizione completa dei risultati dovrebbe considerare tutte le prove disponibili (ad esempio la progettazione di esperimenti, le dimensioni dei campioni, i tassi di conversione, la fiducia, ecc.), e non solo la dichiarazione conclusiva o meno. Anche quando un risultato non è ancora “conclusivo”, ci possono essere prove convincenti che una variante sia diversa da un’altra (ad esempio, intervalli di affidabilità quasi non sovrapposti). Idealmente, il processo decisionale dovrebbe essere informato da tutte le prove statistiche, interpretate su uno spettro continuo.

## Metodologia statistica di Adobe {#statistics}

Per fornire un’inferenza statistica facilmente interpretabile e sicura, Adobe ha adottato una metodologia statistica basata sulle [sequenze di affidabilità valide in qualsiasi momento](https://doi.org/10.48550/arXiv.2103.06476).

Una sequenza di affidabilità è un analogico “sequenziale” di un intervallo di affidabilità. Per capire quale sia una sequenza di affidabilità, immagina di ripetere un esperimento cento volte e di calcolare una stima della metrica di business media (ad esempio il tasso di apertura di un’e-mail) e della relativa sequenza con affidabilità al 95% per *ogni nuovo utente* che entra nell’esperimento.

Una sequenza con affidabilità del 95% includerà il valore “true” della metrica di business in 95 dei 100 esperimenti eseguiti. (Un intervallo di affidabilità del 95% può essere calcolato una sola volta per esperimento al fine di fornire la stessa garanzia di copertura del 95%; non con ogni nuovo utente). Le sequenze di affidabilità consentono quindi di monitorare continuamente gli esperimenti, senza aumentare i tassi di errore di tipo falso positivo, ovvero permettono di “sbirciare” nei risultati.

## Interpretare dimensioni non randomizzate {#non-randomized}

CJA consente agli analisti di selezionare qualsiasi dimensione come &quot;esperimento&quot;. Ma come si interpreta un&#39;analisi in cui la dimensione scelta come esperimento non è quella per cui le persone sono randomizzate?

Ad esempio, considera un annuncio visualizzato da una persona. Se decidi di mostrare le persone &quot;ad B&quot; invece di &quot;ad A&quot;, potresti essere interessato a misurare la variazione di alcune metriche (ad es., ricavi medi). L’effetto causale della visualizzazione dell’annuncio B al posto dell’annuncio A è di fondamentale importanza per giungere alla decisione di marketing. Questo effetto causale può essere misurato come il reddito medio sull&#39;intera popolazione, se sostituiamo lo status quo di mostrare l&#39;annuncio A con la strategia alternativa di mostrare l&#39;annuncio B.

Il test A/B è il gold standard all&#39;interno del settore per misurare obiettivamente gli effetti di tali interventi. La ragione fondamentale per cui un test A/B dà luogo a una stima causale è dovuta alla randomizzazione delle persone a ricevere una delle possibili varianti.

Consideriamo ora una dimensione che non si ottiene con la randomizzazione, per esempio, lo stato americano della persona. Diciamo che le nostre persone provengono principalmente da due stati, New York e California. I ricavi medi delle vendite di un marchio di abbigliamento invernale possono essere diversi nei due Stati a causa delle differenze nelle condizioni climatiche regionali. In una situazione del genere, le condizioni meteorologiche possono essere il vero fattore causale delle vendite di abbigliamento invernale, e non il fatto che gli stati geografici delle persone siano diversi.

Il pannello di sperimentazione nel Customer Journey Analytics consente di analizzare i dati come differenza media di ricavi per stato delle persone. In una situazione del genere, la produzione non ha un’interpretazione causale. Tuttavia, tale analisi può essere ancora interessante. Esso fornisce una stima (insieme a misure di incertezza) della differenza tra le entrate medie degli Stati delle persone. Questo è anche noto come &quot;Test di ipotesi statistica&quot;. L’output di questa analisi può essere interessante, ma non necessariamente actionable, poiché non abbiamo e a volte non possiamo randomizzare le persone a uno dei possibili valori della dimensione.

La figura seguente contrasta queste situazioni:

![esperimento randomizzato](assets/randomize.png)

Quando si vuole misurare l&#39;impatto dell&#39;intervento X sull&#39;esito Y, è possibile che la vera causa di entrambi sia il fattore confondente C. Se i dati non vengono ottenuti randomizzando le persone su X, l&#39;impatto è più difficile da misurare e l&#39;analisi terrà esplicitamente conto di C. La randomizzazione interrompe la dipendenza di X da C, permettendoci di misurare l&#39;effetto di X su Y senza doverci preoccupare di altre variabili.
