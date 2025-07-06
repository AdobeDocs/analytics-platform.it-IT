---
description: Ottieni insight in fattori che influiscono sulle prestazioni di Analysis Workspace e sulle ottimizzazioni possibili
title: Ottimizzare le prestazioni di Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: 226afef7-00da-4ac2-be4e-e19995621c61
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '2441'
ht-degree: 42%

---

# Ottimizzare le prestazioni di Analysis Workspace

Vari fattori influenzano le prestazioni di un progetto in Analysis Workspace.  Per comprendere questi fattori, è utile pianificare e creare i progetti nel modo più ottimale.

Per ottenere informazioni sulle prestazioni di insight in Analysis Workspace:

1. Seleziona **[!UICONTROL Help]>[!UICONTROL Performance]**.

   Puoi visualizzare una finestra di dialogo modale con fattori che influiscono sulle prestazioni del progetto, compresi quelli relativi alla rete, al browser e al progetto. Per ottenere risultati più precisi, carica il progetto prima di

   * La colonna **[!UICONTROL Current Project]** visualizza i risultati per il progetto corrente e l&#39;ambiente utente.
   * La colonna **[!UICONTROL Guideline]** visualizza la soglia consigliata da Adobe per ciascun fattore.

1. Seleziona **[!UICONTROL Download as CSV]** per scaricare il rapporto sulle prestazioni in modo da poterlo condividere all&#39;interno dell&#39;organizzazione interna o con il supporto di Adobe.

>[!NOTE]
>
>Le informazioni nella pagina Prestazioni variano ogni volta che viene aperta questa finestra modale, in quanto i fattori sono soggetti a modifiche. Inoltre, Adobe continua a perfezionare le linee guida fornite man mano che diventano disponibili più dati.

![](assets/cja-performance.png)

## Fattori di rete

I fattori di rete includono:

| Fattore | Definizione | Influenzato da | Ottimizzazione |
| --- | --- | --- | --- |
| Connessione ad Adobe | Adobe invia 10 chiamate di test all’apertura della pagina Prestazioni. Queste chiamate rappresentano la percentuale di chiamate ad Adobe che hanno esito positivo. | Su questo fattore incidono problemi di rete locale o problemi di Adobe. | Visita status.adobe.com per verificare se esistono problemi di servizio noti. Quindi, controlla la tua connessione di rete locale. |
| Larghezza di banda Internet | Disponibile solo per Google Chrome. Stima della larghezza di banda fornita dal browser in uso. La soglia consigliata è 2,0 MB/s. | Su questo fattore incide la connessione di rete locale. | Controlla la tua connessione di rete locale. |
| Latenza Internet | Adobe invia 10 chiamate di test all’apertura della pagina Prestazioni. Queste chiamate rappresentano il tempo medio necessario a una richiesta per raggiungere Adobe e tornare. In altre parole, indica la velocità di Internet tra la tua posizione e Adobe. La soglia consigliata è &lt; 1 secondo. | Su questo fattore incidono problemi di rete locale, la presenza di numerose schede aperte nel browser o problemi con Adobe. | Visita status.adobe.com per verificare se esistono problemi di servizio noti. Quindi, controlla la tua connessione di rete locale e chiudi le schede del browser che non inutilizzi. |

## Fattori del browser

I fattori del browser includono:

| Fattore | Definizione | Influenzato da | Ottimizzazione |
| --- | --- | --- | --- |
| Velocità di calcolo | Velocità del computer per l’esecuzione di un test di elaborazione. La soglia consigliata è inferiore a 750 millisecondi. | Su questo fattore incidono l&#39;hardware e i programmi simultanei. | Apri Gestione attività (PC) o Monitoraggio attività (Mac) per determinare se è possibile chiudere alcuni dei programmi aperti. Quindi, chiudi le schede del browser inutilizzate o altri programmi. <br><br>Se tali azioni non migliorano le prestazioni, rivolgiti al tuo team IT per valutare i dettagli hardware. |
| Memoria utilizzata | Disponibile solo per Google Chrome. Ogni scheda di Workspace in un browser Google Chrome condivide 4 GB di memoria in totale. La memoria utilizzata rappresenta la percentuale di tale quota di memoria utilizzata dal progetto corrente. La soglia consigliata è di 3500 MB, ovvero il punto in cui Workspace inizia a presentare errori di memoria. | L’utilizzo di più schede o il download di 50000 righe di dati contribuisce a un maggiore utilizzo della memoria. | Se ricevi un errore di memoria, chiudi le altre schede di Workspace e/o esegui un download di 50000 righe alla volta. |
| Archiviazione locale utilizzata | I dati archiviati localmente nel computer per l&#39;utilizzo nel browser. Ogni origine (ad esempio, experience.adobe.com) dispone di una tolleranza di 10 MB. | Analysis Workspace utilizza l’archiviazione locale per diverse funzioni, quali l’archiviazione dei salvataggi automatici di progetti esistenti, le impostazioni utente e i flag delle funzioni. | Per evitare l’interruzione delle funzionalità di Analysis Workspace, cancella l’archiviazione locale per il dominio experience.adobe.com. |
| Velocità di rendering | FPS è l’acronimo di Frame al secondo, ossia quante volte al secondo il browser disegna la pagina sullo schermo. L’occhio può osservare 24 FPS; se il valore FPS è inferiore a 24 FPS, in Workspace si osservano problemi di rendering. | FPS è influenzato dal multitasking in molti progetti Workspace contemporaneamente e dalle dimensioni del progetto visualizzato. È influenzato inoltre dall’esecuzione di altri programmi sul computer, come streaming, scanner in background, ecc. Inoltre, l&#39;hardware influisce su questo fattore. | Apri Gestione attività (PC) o Monitoraggio attività (Mac) per determinare se è possibile chiudere alcuni dei programmi aperti. Quindi, chiudi le schede del browser inutilizzate o altri programmi. <br><br>Se tali azioni non migliorano le prestazioni, rivolgiti al tuo team IT per valutare i dettagli hardware. |

## Fattori del progetto

I fattori del progetto includono:

| Fattore | Definizione | Ottimizzazione |
| --- | --- | --- |
| Numero di richieste | Numero totale di richieste effettuate ad Adobe per recuperare i dati visualizzati nel progetto. Le query includono richieste con classificazione per tabelle, rilevamento di anomalie, grafici sparkline, componenti visualizzati nella barra a sinistra e altri ancora. Questo numero esclude i pannelli e le visualizzazioni compressi. La soglia consigliata è 100. | Semplifica il progetto laddove possibile, suddividendo i dati in diversi progetti in base a uno scopo specifico o a un gruppo di soggetti interessati. Utilizza i tag per organizzare i progetti in temi e utilizza [collegamenti diretti](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links) per creare un sommario interno che consenta agli interessati di trovare facilmente ciò di cui hanno bisogno. |
| Pannelli espansi (sul totale dei pannelli) | Numero di pannelli espansi rispetto al numero totale di pannelli nel progetto. La soglia consigliata è 5. | Dopo aver semplificato il progetto, comprimi i pannelli che non è necessario visualizzare al momento del caricamento. Quando il progetto viene aperto, vengono elaborati solo i pannelli espansi. I pannelli compressi vengono elaborati solo quando l’utente li espande. |
| Visualizzazioni espanse (sul totale delle visualizzazioni) | Numero di tabelle e visualizzazioni espanse rispetto al totale nel progetto, incluse le origini dati nascoste. La soglia consigliata è 15. | Dopo aver semplificato il progetto, comprimi le visualizzazioni che non è necessario visualizzare al momento del caricamento. Dai priorità agli elementi visivi più importanti per chi userà il rapporto e, se necessario, suddividi gli elementi visivi di supporto in un pannello o un progetto separato e più dettagliato. |
| Numero di celle a forma libera | Numero totale di celle di tabella a forma libera nel progetto, calcolato come righe * colonne per tutte le tabelle. Questo numero esclude le origini dati nascoste. La soglia consigliata è 4000. | Riduci il numero di colonne nella tabella, includendo solo i punti dati più rilevanti. Riduci il numero di righe nella tabella, regolando il numero di righe visualizzate, applicando un filtro tabella o applicando un segmento. |
| Componenti disponibili | Numero totale di componenti recuperati nella barra a sinistra del progetto, per tutte le suite di rapporti presenti nel progetto. Questo numero influisce sulla velocità di caricamento della barra a sinistra e sulla velocità con cui vengono restituiti i risultati della ricerca al suo interno. La soglia consigliata è 2000. | Rivolgiti all’amministratore del prodotto per creare una suite di rapporti virtuale specifica con un set di componenti più mirato. |
| Componenti utilizzati | Numero totale di componenti utilizzati nel progetto. La soglia consigliata è 100. | Il numero di componenti utilizzati non influisce direttamente sulle prestazioni. Tuttavia, la complessità di tali componenti contribuisce alle prestazioni del progetto. Vedi le ottimizzazioni nella sezione A[Fattori aggiuntivi](#additional-factors) di seguito. |
| Intervallo di date più lungo | Questo fattore visualizza l’intervallo di date più lungo utilizzato nel progetto. La soglia consigliata è 1 anno. | Dove possibile, non inserire più dati del necessario. Limita il calendario del pannello alle date pertinenti per l’analisi. In alternativa, utilizza i componenti intervallo di date (componenti viola) nelle tabelle a forma libera. Gli intervalli di date utilizzati in una tabella prevalgono sull’intervallo di date del pannello. Ad esempio, puoi aggiungere alle colonne della tabella Mese scorso, Settimana scorsa e Ieri, per richiedere tali intervalli di dati specifici. Per ulteriori informazioni sulle attività con gli intervalli di date in Analysis Workspace, guarda [questo video](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-date-ranges-and-comparisons-in-analysis-workspace). <br><br>Inoltre, riduci al minimo il numero di confronti su base annua utilizzati nel progetto. Quando viene calcolato un confronto su base annua, il confronto esamina tutti i 13 mesi di dati tra i mesi di interesse. Questo confronto ha lo stesso impatto di un intervallo di date del pannello impostato sugli ultimi 13 mesi. |

## Fattori di richiesta

Fattori di richiesta

Utilizza il diagramma e i termini seguenti per scoprire come vengono elaborate le richieste e i vari fattori che influenzano i tempi di elaborazione:

>[!NOTE]
>
>Le linee guida consigliate per questi fattori si basano su un punteggio di complessità del mezzo per le richieste di reporting.


### Diagramma di elaborazione delle richieste

![Elaborazione richiesta](assets/request-processing.png)

### Richiedi termini di elaborazione

| Fattore | Definizione | Ottimizzazione |
| --- | --- | --- |
| [!UICONTROL **Tempo medio di richiesta**] | Il tempo necessario dall’avvio della richiesta al completamento. La soglia consigliata è 15 secondi. <p>Nel diagramma [Elaborazione richiesta](#request-processing-diagram) riportato sopra, il tempo di richiesta rappresenta l&#39;intero processo, da **Richiesta Analysis Workspace avviata** a **Richiesta Analysis Workspace completata**.</p> |  |
| [!UICONTROL **Tempo di richiesta più lungo**] | Il tempo necessario dall’avvio della richiesta al completamento. <p>Nel diagramma [Elaborazione richiesta](#request-processing-diagram) riportato sopra, il tempo di richiesta rappresenta l&#39;intero processo, da **Richiesta Analysis Workspace avviata** a **Richiesta Analysis Workspace completata**.</p> |  |
| [!UICONTROL **Tempo medio di ricerca**] | Poiché Analysis Workspace memorizza solo l&#39;hash per le stringhe utilizzate in qualsiasi segmento, ogni volta che si elabora un progetto vengono eseguite **ricerche** per far corrispondere gli hash con i valori appropriati. La soglia consigliata è inferiore a 2 secondi.<p>Queste ricerche possono richiedere molte risorse, a seconda del numero di valori che potrebbero potenzialmente corrispondere all’hash. </p><p>Nel diagramma [Elaborazione richiesta](#request-processing-diagram) riportato sopra, il tempo di ricerca è rappresentato nella fase **Ricerche** (al momento della fase **Elaborazione motore di richiesta**).</p> | Se le richieste rallentano qui, è probabile che il problema sia dovuto al fatto che nel progetto sono presenti troppi segmenti di stringa o stringhe con valori eccessivamente generici con troppe potenziali corrispondenze. |
| [!UICONTROL **Tempo medio coda**] | Tempo totale di attesa nella coda prima dell’elaborazione delle richieste. La soglia consigliata è di 5 secondi.<p>Nel diagramma [Elaborazione richiesta](#request-processing-diagram) riportato sopra, il tempo di coda è rappresentato nella fase **Coda motore di richiesta** e nella fase **Coda server**.</p> | Se le richieste rallentano qui, la causa potrebbe essere un numero eccessivo di richieste in esecuzione simultaneamente nell’organizzazione. Prova a eseguire la richiesta in un orario non di punta. |
| [!UICONTROL **Tempo medio di elaborazione del server**] | Il tempo medio necessario per elaborare la richiesta.<p>Nel diagramma [Elaborazione richiesta](#request-processing-diagram) riportato sopra, il tempo medio di elaborazione del server è rappresentato nella fase **Coda server** e nella fase **Elaborazione server**. La soglia consigliata è 10 secondi | Se le richieste di rallentano qui, è probabile che il progetto abbia intervalli di date eccessivamente lunghi o visualizzazioni complesse. Prova a ridurre l’intervallo di date del progetto per ridurre i tempi di elaborazione. |
| [!UICONTROL **Complessità**] | Il tempo di elaborazione non è uguale per tutte le richieste. La complessità delle richieste può essere utile per avere un’idea generale sul tempo necessario per elaborarle. La soglia consigliata è Medium o inferiore. <p>I valori possibili includono:</p> <ul><li>[!UICONTROL **Basso**]</li><li>[!UICONTROL **Medio**]</li><li>[!UICONTROL **Alto**]</li></ul>Questo valore è influenzato dai valori delle colonne seguenti:<ul><li>[!UICONTROL **Limiti del mese**]</li><li>[!UICONTROL **Colonne**]</li><li>[!UICONTROL **Segmenti**]</li></ul> |  |
| [!UICONTROL **Limiti del mese**] | Il numero di mesi inclusi in una richiesta. La complessità della richiesta è dovuta all’aumento dei limiti di mese. La soglia consigliata è pari o inferiore a 6. | Se le richieste rallentano qui, è possibile che i limiti dei mesi nel progetto siano troppo grandi. Prova a ridurre il numero di mesi. |
| [!UICONTROL **Colonne**] | Il numero di metriche e raggruppamenti nella richiesta. Altre colonne aumentano la complessità della richiesta. La soglia consigliata è pari o inferiore a 10. | Se le richieste rallentano qui, è possibile che il progetto contenga troppe colonne. Prova a ridurre il numero di colonne. |
| [!UICONTROL **Segmenti**] | Il numero di segmenti applicati alla richiesta. Altri segmenti aumentano la complessità della richiesta. La soglia consigliata è pari o inferiore a 5. | Se le richieste rallentano qui, è possibile che il progetto contenga troppi segmenti. Prova a ridurre il numero di segmenti. |

## Altri fattori

Altri fattori non inclusi in Guida > Prestazioni:

| Fattore | Definizione | Influenzato da | Ottimizzazione |
| --- | --- | --- | --- |
| Complessità del segmento | Segmenti complessi possono avere un impatto significativo sulle prestazioni del progetto. | I fattori che aggiungono complessità a un segmento (in ordine approssimativo di impatto) includono: <ul><li>Operatori di **[!UICONTROL contains]**, **[!UICONTROL contains any of]**, **[!UICONTROL matches]**, **[!UICONTROL starts with]** o **[!UICONTROL ends with]**/ </li><li>La segmentazione sequenziale avviene specialmente quando si utilizzano restrizioni delle dimensioni (entro/dopo) </li><li>Numero di elementi dimensionali univoci all’interno delle dimensioni utilizzate nel segmento (ad esempio, Pagina = &quot;A&quot; quando Pagina con 10 elementi univoci è più veloce di Pagina = &quot;A&quot; quando Pagina con 100000 elementi univoci) </li><li>Il numero di diverse dimensioni utilizzate (ad esempio, Pagina = &quot;Home&quot; e Pagina = &quot;Risultati ricerca&quot; sono più veloci di eVar 1 = &quot;rosso&quot; e eVar 2 = &quot;blu&quot;)</li><li>Molti operatori O (invece di E)</li><li>Contenitori nidificati di vario ambito (ad esempio, Hit all’interno di Visita all’interno di Visitatore)</li></ul> | Mentre alcuni dei fattori di complessità non possono essere evitati, cerca di individuare le opportunità di riduzione della complessità dei segmenti. In generale, più si può essere specifici con i propri criteri di segmento, meglio è. Ad esempio:<ul><li>Con i contenitori, l’utilizzo di un singolo contenitore nella parte superiore del segmento è più veloce di una serie di contenitori nidificati.</li><li>Con gli operatori, **[!UICONTROL equals]** sono più veloci di **[!UICONTROL contains]** e **[!UICONTROL equals any of]** più veloci di **[!UICONTROL contains any of]**.</li><li>Con molti criteri, gli operatori AND sono più veloci di una serie di operatori OR.</li></ul> Cercare opportunità per ridurre molte istruzioni OR in un&#39;unica istruzione **[!UICONTROL equals any of]**. |
| Complessità della visualizzazione (segmenti, metriche, filtri) | Il tipo di visualizzazione (ad esempio, abbandono rispetto a una tabella a forma libera) non influenza molto le prestazioni del progetto. La complessità della visualizzazione aumenta il tempo di elaborazione. | Fattori che aggiungono complessità a una visualizzazione includono:<ul><li>Intervallo dei dati richiesti</li><li>Numero di segmenti applicati; ovvero segmenti utilizzati come righe di una tabella a forma libera</li><li>Utilizzo di segmenti complessi</li><li>Righe o colonne [statiche di elementi](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows) in tabelle a forma libera</li><li>Filtri applicati a righe in tabelle a forma libera</li><li>Numero di metriche incluse, in particolare metriche calcolate che utilizzano segmenti</li></ul> | Se noti che i tuoi progetti non si caricano rapidamente tanto quanto vorresti, prova a sostituire alcuni segmenti con eVar e filtri, ove possibile.<br><br>Se utilizzi sempre segmenti e metriche calcolate per punti dati importanti per la tua azienda, puoi migliorare la tua implementazione per acquisire questi punti dati in modo più diretto. L’utilizzo dei tag in Adobe Experience Platform e delle regole di elaborazione di Adobe può velocizzare le modifiche e facilitarne l’implementazione. |
| Dimensione della suite di rapporti | Quantità di dati raccolti nella suite di rapporti. | - | Rivolgiti al team addetto all’implementazione o a un esperto Adobe per determinare se sia possibile migliorare l’implementazione al fine di migliorare l’esperienza complessiva in Adobe Analytics. |
| Query simultanee | Il numero di query che vengono richieste contemporaneamente dall’organizzazione ad Adobe. Ciascuna organizzazione ha diritto a un minimo di 5 query simultanee. | Se un rapporto richiede molto tempo, si trova in coda con altri rapporti, il che significa che l’organizzazione sta tentando di eseguire molte richieste simultanee su una specifica suite di rapporti. Le query possono provenire da richieste API, interfacce per la generazione di rapporti (Analysis Workspace, Report Builder), progetti pianificati, rapporti pianificati, avvisi pianificati e utenti simultanei che eseguono richieste di reporting. | Distribuisci le richieste e le pianificazioni per la suite di rapporti in modo più uniforme durante l’intera giornata. Inoltre, se possibile, rimanda le tue richieste a orari fuori picco. Lunedì mattina, martedì mattina e il primo di ogni mese sono solitamente momenti di picco per la generazione di rapporti. |

## Suggerimenti per aumentare la produttività in Analysis Workspace


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Suggerimenti per aumentare la produttività](https://video.tv.adobe.com/v/35895?quality=12&learn=on&captions=ita){target="_blank"} per un video demo.

>[!ENDSHADEBOX]
