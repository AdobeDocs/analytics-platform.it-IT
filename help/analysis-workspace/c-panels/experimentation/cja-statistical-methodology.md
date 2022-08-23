---
source-git-commit: 99b190e1afe7068d11fd9d53c5be72008958a9c2
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---
# Introduzione alla metodologia statistica nel pannello Sperimentazione di CJA

Questo articolo descrive i calcoli statistici utilizzati dal Pannello di sperimentazione in CJA. CJA utilizza metodi statistici avanzati per il calcolo **fiducia** che è valido in qualsiasi momento, consentendoti di eseguire gli esperimenti per tutto il tempo desiderato e di monitorare continuamente i risultati.

Questo articolo descrive il funzionamento dei test A/B e fornisce un’introduzione intuitiva al Adobe ***Qualsiasi Sequenza Di Affidabilità Valida***. Per gli utenti esperti, i dettagli tecnici e i riferimenti sono inclusi alla fine.

## Test A/B e casualità

I test A/B sono spesso descritti come &quot;gold standard&quot; nella valutazione dell&#39;impatto causale di un certo tipo di &quot;intervento&quot;. Si tratta di test randomizzati, che nel contesto dei test online, significa che esponiamo alcuni utenti selezionati in modo casuale a una determinata variante di un sito web, un messaggio o e-mail, e un altro gruppo selezionato in modo casuale di utenti ad altri **variante** o **trattamento**. Dopo l&#39;esposizione, misuriamo il risultato **metriche** siamo interessati (ad esempio aperture di e-mail, abbonamenti o acquisti).

Come illustrato nell’immagine seguente, il fatto che gli utenti siano stati assegnati casualmente a ogni gruppo di varianti significa che in media i gruppi condivideranno le stesse caratteristiche. Pertanto, qualsiasi differenza di risultati può essere interpretata come dovuta alle differenze nelle varianti ricevute, cioè siamo in grado di stabilire un **causale** collegamento tra i nostri interventi e i risultati a cui siamo interessati. Questo ti consente di prendere decisioni rigorose, spiegabili e basate sui dati per ottimizzare i tuoi obiettivi aziendali, e quindi il test A/B è una parte fondamentale del toolkit di qualsiasi operatore di personalizzazione moderna.

<p style="text-align:center;"><img width="75%" src="img/causal-inference-cartoon.png" alt="causale-inf"></p>


Ora, una domanda importante è se le differenze osservate siano &quot;effetti reali&quot;, o sorgano a causa della casualità. Intuitivamente, se c&#39;è solo una piccola differenza nelle metriche dei risultati tra i gruppi, allora questo potrebbe essere stato osservato per caso, mentre le differenze più grandi sono più probabilità di essere &quot;reali&quot;. Il termine tecnico qui è che le nostre misurazioni sono *stime* dei valori reali della media per ogni gruppo di varianti. Le tecniche di deduzione statistica ci forniscono modi per quantificare la quantità di incertezza nelle nostre stime - qui è dove i concetti di **valori p** e **Intervalli di affidabilità** sorgono, ma per comprenderli, dobbiamo prima capire gli errori statistici.

## Test statistici e controllo degli errori

Molte metodologie di deduzione statistica sono progettate per controllare due tipi di errori: **Falso positivo** (errori di tipo I) e **Falso negativo** (Errori di tipo II). Questi sono illustrati nella tabella seguente.


<p style="text-align:center;"><img width="50%" src="img/contingency_table_stats_errors.png" alt="ContingencyTable"></p>


Un falso positivo è un rifiuto errato dell&#39;ipotesi null, quando in realtà è vero. Nel contesto dei test A/B online, ciò significa che (falsamente) concludiamo che il risultato della metrica di business è diverso tra le braccia diverse, quando in realtà era lo stesso. Prima di eseguire l&#39;esperimento, tipicamente scegliamo una soglia *α*. Dopo l&#39;esecuzione dell&#39;esperimento, la *p*-value viene calcolato e viene rifiutato il valore null se *p &lt; α*. Una soglia comunemente utilizzata è *α*= 0,05, il che significa che a lungo termine, ci aspettiamo 5 esperimenti su 100 siano falsi positivi.

Nel frattempo, un falso negativo significa che non si riesce a respingere l&#39;ipotesi null quando in realtà è falsa. Per il test A/B, ciò significa che non respingiamo l&#39;ipotesi null (ricordiamo, l&#39;ipotesi null afferma che la metrica di business dei risultati è la stessa tra i bracci variante), quando in realtà è diversa. Per controllare questo tipo di errore, generalmente abbiamo bisogno di abbastanza utenti nel nostro esperimento per garantire un certo **Potenza**, definito come 1-*β* (cioè uno meno la probabilità di un errore di tipo II).

La maggior parte delle tecniche di deduzione statistica richiederà di correggere anticipatamente la dimensione del campione in base alla dimensione dell’effetto che si desidera determinare, nonché alla tolleranza di errore (*α* e *β*) in anticipo. Tuttavia, la metodologia di Adobe è progettata per consentire di esaminare continuamente i risultati, per qualsiasi dimensione del campione.



## Metodologia statistica del Adobe: _Sequenze di affidabilità valide in qualsiasi momento_

Per fornire un’inferenza statistica facilmente interpretabile e sicura, l’Adobe ha adottato una metodologia statistica basata sui [_Sequenze di affidabilità valide in qualsiasi momento_](https://doi.org/10.48550/arXiv.2103.06476).

Una sequenza di affidabilità è un analogico &quot;sequenziale&quot; di un intervallo di affidabilità. Per capire quale sia una sequenza di affidabilità, immagina di ripetere i tuoi esperimenti cento volte e di calcolare una stima della metrica media di business (ad esempio il tasso di apertura di un’e-mail) e della sequenza di affidabilità al 95% associata per *ogni nuovo utente* entra nell&#39;esperimento. Una sequenza di affidabilità del 95% includerà il valore &quot;true&quot; della metrica di business in 95 dei 100 esperimenti eseguiti. (Un intervallo di affidabilità del 95% può essere calcolato una sola volta per esperimento al fine di fornire la stessa garanzia di copertura del 95%; non con ogni nuovo utente). Le sequenze di affidabilità consentono quindi di monitorare continuamente gli esperimenti, senza aumentare i tassi di errore falsi positivi, ovvero permettono di &quot;sbirciare&quot; nei risultati.

La differenza tra le sequenze di affidabilità e gli intervalli di affidabilità per un singolo esperimento è mostrata nell&#39;animazione seguente:

<p style="text-align:center;"><img width="75%" src="img/confidence-sequence-evolution-comparison.gif" alt="CSGIF"></p>


Notiamo che le sequenze di affidabilità spostano l’attenzione dei test A/B su *stima* piuttosto che il test di ipotesi, vale a dire, concentrandosi su una stima accurata della differenza di mezzi tra i trattamenti, piuttosto che sulla possibilità o meno di respingere un&#39;ipotesi nulla basata su una soglia di rilevanza statistica.

Tuttavia, in modo simile alla relazione tra i valori $p$ (o Confidence) e gli intervalli di affidabilità, esiste anche una relazione tra le Sequenze di affidabilità e ogni volta valori $p$ validi (o in qualsiasi momento Confidence valida). Data la familiarità delle quantità come la Affidabilità, CJA fornisce la fiducia valida in qualsiasi momento nelle sue relazioni.

Le basi teoriche delle Sequenze di Fiducia provengono dallo studio di sequenze di variabili casuali note come martingales. Alcuni risultati principali sono inclusi per i lettori esperti di seguito, ma le offerte per i professionisti sono chiare:


> Le sequenze di affidabilità possono essere interpretate come analoghi sequenziali &quot;sicuri&quot; di intervalli di affidabilità: puoi guardare e interpretare i dati nel test A/B in qualsiasi momento e interrompere o continuare gli esperimenti in modo sicuro. Confidenza valida in qualsiasi momento (o *p*-value) è anche sicuro da interpretare.

È importante notare che, poiché la metodologia statistica è &quot;sempre valida&quot;, sarà più conservativa di una metodologia a orizzonte fisso applicata alla stessa dimensione del campione. Ciò significa che il &quot;valido in qualsiasi momento&quot; *p*-i valori saranno generalmente più grandi dell&#39;orizzonte fisso corrispondente *p*-valori (ovvero, se la confidenza valida in qualsiasi momento è minore)

## Interpretazione dei risultati

1. **L&#39;esperimento è conclusivo**: Ogni volta che visualizzi il rapporto sulla sperimentazione, l&#39;Adobe analizza i dati accumulati nell&#39;esperimento fino a questo punto e dichiarerà un esperimento &quot;Conclusivo&quot; quando la fiducia valida supera una soglia del 95% per *almeno uno* delle varianti (con una correzione Bonferonni applicata quando ci sono più di due bracci, per correggere per test di ipotesi multiple).

2. **Variante con prestazioni migliori**: Quando un esperimento è dichiarato conclusivo, la variante con il tasso di conversione più alto è etichettata come la &quot;variante con le prestazioni migliori&quot;. Questa variante deve essere la variante di controllo o linea di base oppure una delle varianti che supera il 95% ogni volta che viene applicata una soglia di affidabilità valida (con le correzioni Bonferonni).

3. **Tasso di conversione**: Il tasso di conversione mostrato è un rapporto tra il valore della metrica di successo e il valore della metrica di normalizzazione. Tieni presente che a volte questo può essere maggiore di 1, se la metrica non è binaria (1 o 0 per ogni unità nell’esperimento)

4. **Lift**: Il riepilogo del rapporto Esperimento mostra l’Incremento rispetto alla linea di base, che è una misura del miglioramento percentuale del tasso di conversione di una determinata variante rispetto alla linea di base. Definito con precisione, è la differenza di prestazioni tra una determinata variante e la linea di base, divisa per le prestazioni della linea di base, espressa in percentuale.

5. **Affidabilità**: La confidenza valida per ogni tempo mostrata è una misura probabilistica della quantità di prove che dimostrano che una data variante è la stessa della variante di controllo. Una maggiore affidabilità indica meno prove dell&#39;ipotesi che la variante di controllo e non di controllo abbiano prestazioni uguali. Più precisamente, l’affidabilità visualizzata è una probabilità (espressa in percentuale) che avremmo osservato una differenza minore nei tassi di conversione tra una data variante e il controllo, se in realtà non c’è differenza nei veri tassi di conversione sottostanti. In termini di *p*-valori, l&#39;affidabilità visualizzata è 1 - *p*-value.

Si noti tuttavia che una descrizione completa dei risultati dovrebbe considerare tutte le prove disponibili (ad esempio la progettazione di esperimenti, le dimensioni dei campioni, i tassi di conversione, la fiducia, ecc.) e non solo la dichiarazione conclusiva o meno. Anche quando un risultato non è ancora &quot;conclusivo&quot;, ci possono essere prove convincenti che una variante sia diversa da un&#39;altra (ad esempio, gli intervalli di affidabilità sono quasi non sovrapposti). Idealmente, il processo decisionale dovrebbe essere informato da tutte le prove statistiche, interpretate su uno spettro continuo.
