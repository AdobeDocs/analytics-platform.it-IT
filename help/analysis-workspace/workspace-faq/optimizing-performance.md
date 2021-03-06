---
description: Fattori che incidono sulle prestazioni e possibili ottimizzazioni di Workspace
title: Fattori prestazionali e ottimizzazione di Analysis Workspace
feature: FAQ
exl-id: ad00e476-6f19-462b-ba53-d72ddd949802
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '1718'
ht-degree: 100%

---

# Ottimizzare [!UICONTROL Analysis Workspace] prestazioni

Alcuni fattori possono incidere sulle prestazioni di un progetto in Analysis Workspace. È importante conoscere tali fattori prima di iniziare a creare un progetto, in modo da pianificare e creare il progetto nel modo migliore. Questa pagina include un elenco di fattori che incideranno sulle prestazioni, e possibili ottimizzazioni per garantire prestazioni di picco in Analysis Workspace.

## [!UICONTROL Help] > [!UICONTROL Performance] in Analysis Workspace

In **Analysis Workspace > [!UICONTROL Help] >[!UICONTROL Performance]** puoi vedere quali fattori influiscono sulle prestazioni del progetto, compresi rete, browser e fattori del progetto. Per ottenere risultati più precisi, aspetta che il progetto sia stato caricato completamente prima di aprire la pagina Prestazioni.

* La colonna Progetto corrente presenta i risultati per il progetto corrente e l’ambiente utente.
* La colonna Linee guida presenta la soglia consigliata da Adobe per ciascun fattore.

Puoi anche **Download as CSV** (Scaricare come CSV) i contenuti delle prestazioni, per condividerli facilmente con l’Assistenza clienti di Adobe o con il tuo team IT interno.

>[!NOTE]
>
>Le informazioni nella pagina Prestazioni variano ogni volta che viene aperta questa finestra modale, in quanto i fattori sono soggetti a modifiche. Inoltre, Adobe continuerà a perfezionare le linee guida fornite man mano che diventano disponibili ulteriori dati.

![](assets/performance-modal.png)

## Fattori di rete

I fattori di rete in [!UICONTROL Help] > [!UICONTROL Performance] includono:

| Fattore | Definizione | Influenzato da | Ottimizzazione |
| --- | --- | --- | --- |
| Connessione ad Adobe | Adobe invia 10 chiamate di test all’apertura della pagina Prestazioni. Rappresenta la percentuale delle chiamate ad Adobe che hanno esito positivo. | Su questo fattore incidono problemi di rete locale o problemi della rete Adobe. | Visita status.adobe.com per verificare se esistono problemi di servizio noti. Quindi, controlla la tua connessione di rete locale. |
| Larghezza di banda Internet | Disponibile solo per Google Chrome. Stima della larghezza di banda fornita dal browser in uso. La soglia consigliata è 2,0 MB/s. | Su questo fattore incide la connessione di rete locale. | Controlla la tua connessione di rete locale. |
| Latenza Internet | Adobe invia 10 chiamate di test all’apertura della pagina Prestazioni. La latenza corrisponde al tempo medio necessario affinché ogni richiesta arrivi ad Adobe e venga quindi restituita. In altre parole, indica la velocità di Internet tra la tua posizione e Adobe. La soglia consigliata è &lt; 1 secondo. | Su questo fattore incidono problemi di rete locale, la presenza di numerose schede aperte nel browser o problemi della rete Adobe. | Visita status.adobe.com per verificare se esistono problemi di servizio noti. Quindi, controlla la tua connessione di rete locale e chiudi le schede del browser che non inutilizzi. |

## Fattori del browser

I fattori del browser in [!UICONTROL Help] > [!UICONTROL Performance] includono:

| Fattore | Definizione | Influenzato da | Ottimizzazione |
| --- | --- | --- | --- |
| Velocità di calcolo | Velocità del computer per l’esecuzione di un test di elaborazione. La soglia consigliata è &lt; 750 ms. | Su questo fattore incidono l’hardware e i programmi in esecuzione allo stesso tempo. | Apri Gestione attività (PC) o Monitor attività (Mac) per determinare se è possibile chiudere alcuni dei programmi aperti. Quindi, chiudi le schede del browser inutilizzate o altri programmi. <br><br>Se tali azioni non migliorano le prestazioni, rivolgiti al tuo team IT per valutare i dettagli hardware. |
| Memoria utilizzata | Disponibile solo per Google Chrome. Ogni scheda di Workspace in un browser Google Chrome condivide 4 GB di memoria in totale. Questo valore indica la percentuale di tale quota di memoria che viene effettivamente utilizzata dal progetto corrente. La soglia consigliata è di 3500 MB; oltre tale valore, Workspace inizierà a presentare errori di memoria. | Se si lavora con più schede o si scaricano 50000 righe di dati, verrà utilizzata più memoria. | Se ricevi un errore di memoria, chiudi le altre schede di Workspace e/o esegui un download di 50000 righe alla volta. |
| Archiviazione locale utilizzata | Dati memorizzati localmente sul computer da utilizzare nel browser. Ciascuna origine (ad esempio experience.adobe.com) dispone di un limite di 10 MB. | Analysis Workspace utilizza l’archiviazione locale per diverse funzioni, quali l’archiviazione dei salvataggi automatici di progetti esistenti, le impostazioni utente e i flag delle funzioni. | Per evitare l’interruzione delle funzioni di Analysis Workspace, cancella l’archiviazione locale per il dominio experience.adobe.com. |
| Velocità di rendering | FPS è l’acronimo di frame al secondo, ossia quante volte al secondo il browser disegna la pagina sullo schermo. L’occhio può osservare 24 fps; se il valore fps è inferiore a 24, in Workspace saranno visibili problemi di rendering. | Il valore fps è influenzato dal multitasking in molti progetti Workspace allo stesso tempo e dalle dimensioni del progetto visualizzato. È influenzato inoltre dall’esecuzione di altri programmi sul computer, come streaming, scanner in background, ecc. Anche l’hardware incide su questo fattore. | Apri Gestione attività (PC) o Monitor attività (Mac) per determinare se è possibile chiudere alcuni dei programmi aperti. Quindi, chiudi le schede del browser inutilizzate o altri programmi. <br><br>Se tali azioni non migliorano le prestazioni, rivolgiti al tuo team IT per valutare i dettagli hardware. |

## Fattori del progetto

I fattori del progetto in [!UICONTROL Help] > [!UICONTROL Performance] includono:

| Fattore | Definizione | Ottimizzazione |
| --- | --- | --- |
| Numero di query | Numero totale di query (richieste) inviate ad Adobe per recuperare i dati da visualizzare nel progetto. Le query includono richieste con classificazione per tabelle, rilevamento di anomalie, grafici sparkline, componenti visualizzati nella barra a sinistra e altri ancora. Non sono invece inclusi le visualizzazioni e i pannelli compressi. La soglia consigliata è 100. | Semplifica il progetto laddove possibile, suddividendo i dati in diversi progetti in base a uno scopo specifico o a un gruppo di soggetti interessati. Utilizza i tag per organizzare i progetti in temi e utilizza [collegamenti diretti](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=it) per creare un sommario interno che consenta agli interessati di trovare facilmente ciò di cui hanno bisogno. |
| Pannelli espansi (sul totale dei pannelli) | Numero di pannelli espansi rispetto al numero totale di pannelli nel progetto. La soglia consigliata è 5. | Dopo aver semplificato il progetto, comprimi i pannelli che non è necessario visualizzare al momento del caricamento. All’apertura di un progetto, vengono elaborati solo i pannelli espansi. I pannelli compressi vengono caricati solo quando l’utente li espande. |
| Visualizzazioni espanse (sul totale delle visualizzazioni) | Numero di tabelle e visualizzazioni espanse rispetto al totale nel progetto, incluse le origini dati nascoste. La soglia consigliata è 15. | Dopo aver semplificato il progetto, comprimi le visualizzazioni che non è necessario visualizzare al momento del caricamento. Dai priorità agli elementi visivi più importanti per chi userà il rapporto e, se necessario, suddividi gli elementi visivi di supporto in un pannello o un progetto separato e più dettagliato. |
| Numero di celle a forma libera | Numero totale di celle di tabella a forma libera nel progetto, calcolato come righe * colonne per tutte le tabelle. Sono escluse le origini di dati nascosti. La soglia consigliata è 4000. | Riduci il numero di colonne nella tabella, includendo solo i punti dati più rilevanti. Riduci il numero di righe nella tabella, regolando il numero di righe visualizzate, applicando un filtro tabella o applicando un filtro. |
| Componenti utilizzati | Numero totale di componenti utilizzati nel progetto. La soglia consigliata è 100. | Il numero di componenti utilizzati non influisce direttamente sulle prestazioni. Tuttavia, la complessità di tali componenti contribuirà alle prestazioni del progetto. Consulta le ottimizzazioni nella sezione “Altri fattori”, di seguito. |
| Intervallo di date più lungo | Questo fattore visualizza l’intervallo di date più lungo utilizzato nel progetto. La soglia consigliata è 1 anno. | Dove possibile, non inserire più dati del necessario. Limita il calendario del pannello alle date pertinenti per l’analisi o utilizza i componenti per intervallo di date (componenti viola) nelle tabelle a forma libera. Gli intervalli di date utilizzati in una tabella prevalgono sull’intervallo di date del pannello. Ad esempio, puoi aggiungere alle colonne della tabella Mese scorso, Settimana scorsa e Ieri, per richiedere tali intervalli di dati specifici. Per ulteriori informazioni sulle attività con gli intervalli di date in Analysis Workspace, guarda [questo video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html?lang=it). <br><br>Inoltre, riduci al minimo il numero di confronti su base annua utilizzati nel progetto. Quando viene calcolato un confronto su base annua, vengono esaminati 13 mesi di dati tra i mesi di interesse. Questo ha lo stesso impatto di un intervallo di date del pannello impostato sugli ultimi 13 mesi. |

## Altri fattori

Altri fattori non inclusi in Aiuto > Prestazioni:

| Fattore | Definizione | Influenzato da | Ottimizzazione |
| --- | --- | --- | --- |
| Complessità del filtro | Filtri complessi possono avere un impatto significativo sulle prestazioni del progetto. | I fattori che aggiungono complessità a un filtro (in ordine decrescente di impatto) includono: <ul><li>Operatori di “contains”, “contains any of”, “matches”, “starts with” o “ends with” </li><li>Il filtro sequenziale avviene specialmente quando si utilizzano restrizioni delle dimensioni (entro/dopo) </li><li>Numero di elementi di dimensione univoca, compresa nelle dimensioni utilizzate nel filtro, (ad es. Pagina = “A” quando la Pagina ha 10 elementi univoci sarà più veloce della Pagina = “A” quando la Pagina ha 100.000 elementi univoci) </li><li>Numero di diverse dimensioni utilizzate (ad es. Pagina = “Home” e Pagina = “Search results” sarà più veloce di eVar 1 = “red” ed eVar 2 = “blue”)</li><li>Molti operatori OR (invece di AND)</li><li>Contenitori nidificati di vario ambito (ad es., “Hit” all’interno di “Visita” all’interno di “Visitatore”)</li></ul> | Mentre alcuni dei fattori di complessità non possono essere evitati, cerca di individuare le opportunità di riduzione della complessità dei filtri. In generale, più si può essere specifici con i propri criteri di filtro, meglio è. Ad esempio:<ul><li>Con i contenitori, l’utilizzo di un singolo contenitore nella parte superiore del segmento sarà più veloce di una serie di contenitori nidificati.</li><li>Con l’utilizzo degli operatori, “equals” sarà più veloce di “contains” e “equals any of” sarà più veloce di “contains any of”.</li><li>Con molti criteri, gli operatori AND saranno più veloci di una serie di operatori OR.</li></ul> Inoltre, prova a ridurre numerose istruzioni OR in un’unica istruzione “equals any of”. <br> |
| Complessità della visualizzazione (filtri, metriche, filtri) | Il tipo di visualizzazione (ad es. abbandono o tabella a forma libera) aggiunta a un progetto di per sé non influenza molto le prestazioni del progetto. È la complessità della visualizzazione che influenzerà il tempo di elaborazione. | Fattori che aggiungono complessità a una visualizzazione includono:<ul><li>Intervallo dei dati richiesti</li><li>Numero di filtri applicati; ovvero filtri utilizzati come righe di una tabella a forma libera</li><li>Utilizzo di filtri complessi</li><li>Righe o colonne [statiche di elementi](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) in tabelle a forma libera</li><li>Filtri applicati a righe in tabelle a forma libera</li><li>Numero di metriche incluse, in particolare metriche calcolate che utilizzano filtri</li></ul> | Se noti che i tuoi progetti non si caricano rapidamente tanto quanto vorresti, prova a sostituire alcuni filtri con eVar e filtri, ove possibile.<br><br>Se utilizzi sempre filtri e metriche calcolate per punti dati importanti per la tua azienda, puoi migliorare la tua implementazione per acquisire questi punti dati in modo più diretto. L’utilizzo di un gestore di tag come Adobe Experience Platform Launch e delle regole di elaborazione di Adobe può rendere le modifiche di implementazione veloci e facili da applicare. |
| Capacità del centro dati | Capacità di generazione dei rapporti condivisa da te e altri clienti all’interno di un data center di Adobe. | È influenzata dal numero di query simultanee effettuate dalla tua organizzazione e da altre organizzazioni all’interno del centro dati. | La tua organizzazione ha diritto a una determinata capacità e, se il carico del sistema è leggero, Adobe ti allocherà una maggiore capacità, oltre il limite determinato. |
