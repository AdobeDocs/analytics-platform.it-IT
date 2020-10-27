---
description: Fattori che influiscono sulle prestazioni di Workspace e sulle ottimizzazioni consigliate
title: Fattori prestazionali e ottimizzazione di Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: 3928307fb51d1bde628773a91d5f4e2d4e5c2a5c
workflow-type: tm+mt
source-wordcount: '1937'
ht-degree: 81%

---


# Ottimizzare le prestazioni di Analysis Workspace

Alcuni fattori possono incidere sulle prestazioni di un progetto in Analysis Workspace. È importante conoscere tali fattori prima di iniziare a creare un progetto, in modo da pianificare e creare il progetto nel modo migliore. Questa pagina include un elenco di fattori che influiranno sulle prestazioni e le ottimizzazioni consigliate che potete effettuare per garantire prestazioni di picco in  Analysis Workspace.

>[!IMPORTANT]
>
>La pagina Prestazioni in Analysis Workspace è in versione limitata. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/analytics/landing/an-releases.html)

## Aiuto > Prestazioni in Analysis Workspace

In **[!UICONTROL Analysis Workspace > Help > Performance]** puoi vedere quali fattori influiscono sulle prestazioni del progetto, compresi rete, browser e fattori del progetto. Per ottenere risultati più precisi, aspetta che il progetto sia stato caricato completamente prima di aprire la pagina Prestazioni. Puoi anche **scaricare come CSV** i contenuti delle prestazioni, per condividerli facilmente con l’Assistenza clienti di Adobe o con il tuo team IT interno.

>[!NOTE]
>
>Le informazioni nella pagina Prestazioni variano ogni volta che viene aperta questa finestra modale, in quanto i fattori sono soggetti a modifiche. Inoltre,  Adobe continuerà a perfezionare le soglie consigliate non appena saranno disponibili ulteriori dati.

![](assets/performance-modal.png)

## Fattori di rete

**[!UICONTROL Help > Performance]** i fattori di rete includono:

| Fattore | Definizione | Influenzato da | Ottimizzazione  |
| --- | --- |--- | --- |
| Connessione ad Adobe | Adobe invia 10 chiamate di test all’apertura della pagina Prestazioni. Rappresenta la percentuale delle chiamate ad Adobe che hanno esito positivo. | Su questo fattore incidono problemi di rete locale o problemi della rete Adobe. | Visita status.adobe.com per verificare se esistono problemi di servizio noti. Quindi, controlla la tua connessione di rete locale. |
| Larghezza di banda Internet | La stima della larghezza di banda fornita dal browser in uso, verificata solo per Google Chrome. La soglia consigliata è 2,0 MB/s. | Su questo fattore incide la connessione di rete locale. | Controlla la tua connessione di rete locale. |
| Latenza Internet | Adobe invia 10 chiamate di test all’apertura della pagina Prestazioni. La latenza corrisponde al tempo medio necessario affinché ogni richiesta arrivi ad Adobe e venga quindi restituita. In altre parole, indica la velocità di Internet tra la tua posizione e Adobe. La soglia consigliata è &lt; 1 secondo. | Su questo fattore incidono problemi di rete locale, la presenza di numerose schede aperte nel browser o problemi della rete Adobe. | Visita status.adobe.com per verificare se esistono problemi di servizio noti. Quindi, controlla la tua connessione di rete locale e chiudi le schede del browser che non inutilizzi. |

## Fattori del browser

**[!UICONTROL Help > Performance]** i fattori del browser includono:

| Fattore | Definizione | Influenzato da | Ottimizzazione  |
| --- | --- | --- | --- |
| Velocità di calcolo | Velocità del computer per l’esecuzione di un test di elaborazione. La soglia consigliata è &lt; 750 ms. | Su questo fattore incidono l’hardware e i programmi in esecuzione allo stesso tempo. | Apri Gestione attività (PC) o Monitor attività (Mac) per determinare se è possibile chiudere alcuni dei programmi aperti. Quindi, chiudi le schede del browser inutilizzate o altri programmi. <br><br>Se tali azioni non migliorano le prestazioni, rivolgiti al tuo team IT per valutare i dettagli hardware. |
| Memoria utilizzata | Ogni scheda Workspace in un browser Google Chrome condivide 4 GB di memoria in totale (Firefox ha una soglia più alta). Questo valore indica la percentuale di tale quota di memoria che viene effettivamente utilizzata dal progetto corrente. La soglia consigliata è 3500 MB, ovvero il punto in cui Workspace inizierà a presentare errori di memoria. | Se si lavora con più schede o si scaricano 50000 righe di dati, verrà utilizzata più memoria. | Se si riceve un errore di memoria, si consiglia di chiudere altre schede Workspace e/o di eseguire 50000 download di righe uno alla volta. |
| Archiviazione locale utilizzata | Dati memorizzati localmente sul computer da utilizzare nel browser. Ciascuna origine (ad esempio experience.adobe.com) dispone di un limite di 10 MB. | Analysis Workspace utilizza l’archiviazione locale per diverse funzioni, quali l’archiviazione dei salvataggi automatici di progetti esistenti, le impostazioni utente e i flag delle funzioni. | Per evitare l’interruzione delle funzioni di Analysis Workspace, cancella l’archiviazione locale per il dominio experience.adobe.com. |
| Velocità di rendering | &quot;FPS&quot; sta per &quot;Frame al secondo&quot;, ossia quante volte al secondo il browser disegna la pagina sullo schermo. L’occhio può osservare 24 fps; se il valore fps è inferiore a 24, in Workspace saranno visibili problemi di rendering. | Il valore fps è influenzato dal multitasking in molti progetti Workspace allo stesso tempo e dalle dimensioni del progetto visualizzato. È influenzato inoltre dall’esecuzione di altri programmi sul computer, come streaming, scanner in background, ecc. Anche l’hardware incide su questo fattore. | Apri Gestione attività (PC) o Monitor attività (Mac) per determinare se è possibile chiudere alcuni dei programmi aperti. Quindi, chiudi le schede del browser inutilizzate o altri programmi. <br><br>Se tali azioni non migliorano le prestazioni, rivolgiti al tuo team IT per valutare i dettagli hardware. |

## Fattori del progetto

**[!UICONTROL Help > Performance]** i fattori di progetto includono:

| Fattore | Definizione | Ottimizzazione  |
| --- | --- | --- |
| Numero di query | Numero totale di query (richieste) inviate ad Adobe per recuperare i dati da visualizzare nel progetto. Le query includono richieste con classificazione per tabelle, rilevamento di anomalie, grafici sparkline, componenti visualizzati nella barra a sinistra e altri ancora. Non sono invece inclusi le visualizzazioni e i pannelli compressi. La soglia consigliata è 100. | Semplifica il progetto laddove possibile, suddividendo i dati in diversi progetti in base a uno scopo specifico o a un gruppo di soggetti interessati. Utilizza i tag per organizzare i progetti in temi e utilizza [collegamenti diretti](/help/analysis-workspace/curate-share/shareable-links.md) per creare un sommario interno che consenta agli interessati di trovare facilmente ciò di cui hanno bisogno. |
| Pannelli espansi (sul totale dei pannelli) | Numero di pannelli espansi rispetto al numero totale di pannelli nel progetto. La soglia consigliata è 5. | Dopo aver semplificato il progetto, comprimi i pannelli che non è necessario visualizzare al momento del caricamento. All’apertura di un progetto, vengono elaborati solo i pannelli espansi. I pannelli compressi vengono caricati solo quando l’utente li espande. |
| Visualizzazioni espanse (sul totale delle visualizzazioni) | Numero di tabelle e visualizzazioni espanse rispetto al totale nel progetto. Sono escluse le origini di dati nascosti. La soglia consigliata è 15. | Dopo aver semplificato il progetto, comprimi le visualizzazioni che non è necessario visualizzare al momento del caricamento. Dai priorità agli elementi visivi più importanti per chi userà il rapporto e, se necessario, suddividi gli elementi visivi di supporto in un pannello o un progetto separato e più dettagliato. |
| Numero di celle a forma libera | Numero totale di celle di tabella a forma libera nel progetto, calcolato come righe * colonne per tutte le tabelle. Sono escluse le origini di dati nascosti. La soglia consigliata è 4000. | Riduci il numero di colonne nella tabella, includendo solo i punti dati più rilevanti. Riduci il numero di righe nella tabella, regolando il numero di righe visualizzate, applicando un filtro tabella o applicando un segmento. |
| Componenti disponibili | Numero totale di componenti recuperati nella barra a sinistra del progetto, per tutte le suite di rapporti presenti nel progetto. La soglia consigliata è 2000. | Rivolgiti all’amministratore del prodotto per creare una suite di rapporti virtuale specifica con un set di componenti più mirato. |
| Componenti utilizzati | Numero totale di componenti utilizzati nel progetto. La soglia consigliata è 100. | Il numero di componenti utilizzati non influisce direttamente sulle prestazioni. Tuttavia, la complessità di tali componenti contribuirà alle prestazioni del progetto. Consultate le ottimizzazioni consigliate nella sezione &quot;Fattori aggiuntivi&quot; di seguito. |
| Intervallo di date più lungo | Questo fattore visualizza l’intervallo di date più lungo utilizzato nel progetto. La soglia consigliata è di 1 anno. | Dove possibile, non inserire più dati del necessario. Limita il calendario del pannello alle date pertinenti per l’analisi o utilizza i componenti per intervallo di date (componenti viola) nelle tabelle a forma libera. Gli intervalli di date utilizzati in una tabella prevalgono sull’intervallo di date del pannello. Ad esempio, puoi aggiungere alle colonne della tabella Mese scorso, Settimana scorsa e Ieri, per richiedere tali intervalli di dati specifici. Per ulteriori informazioni sulle attività con gli intervalli di date in Analysis Workspace, guarda [questo video](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html). <br><br>Inoltre, riduci al minimo il numero di confronti su base annua utilizzati nel progetto. Quando viene calcolato un confronto su base annua, vengono esaminati 13 mesi di dati tra i mesi di interesse. Questo ha lo stesso impatto di un intervallo di date del pannello impostato sugli ultimi 13 mesi. |

## Altri fattori

Altri fattori non inclusi in Aiuto > Prestazioni:

| Fattore | Definizione | Influenzato da | Ottimizzazione  |
| --- | --- | --- | --- |
| Complessità del filtro | Filtri intricati possono avere un impatto significativo sulle prestazioni del progetto. | Fattori che aggiungono complessità a un filtro (in ordine decrescente di impatto) includono: <ul><li>Operatori di “contiene”, “contiene”, “contiene qualsiasi di”, “corrisponde”, “inizia con” o “finisce con” </li><li>Filtri sequenziali, in particolare quando vengono utilizzate le limitazioni di dimensione (Within/After) </li><li>Numero di elementi di dimensione unica, compresa nelle dimensioni utilizzate nel segmento, (ad es. Pagina = “A” quando la Pagina ha 10 elementi unici sarà più veloce della Pagina = “A” quando la Pagina ha 100.000 elementi unici) </li><li>Numero di diverse dimensioni utilizzate (ad es. Pagina = “Home” e Pagina = “Risultati della ricerca” sarà più veloce di eVar 1 = “rosso” ed eVar 2 = “blu”)</li><li>Molti operatori OR (invece di AND)</li><li>Contenitori nidificati di vario ambito (ad es., “Hit” all’interno di “Visita” all’interno di “Visitatore”)</li></ul> | Non è possibile evitare alcuni fattori di complessità, ma cercare le opportunità per ridurre la complessità dei filtri. In generale, quanto più specifici possono essere i criteri di filtro, tanto meglio è. Ad esempio:<ul><li>Con i contenitori, l’utilizzo di un singolo contenitore nella parte superiore del segmento sarà più veloce di una serie di contenitori nidificati</li><li>Con l’utilizzo degli operatori, “uguale a” sarà più veloce di “contiene” e “uguale a qualsiasi di” sarà più veloce di “contiene qualsiasi di”</li><li>Con molti criteri, gli operatori AND saranno più veloci di una serie di operatori OR.</li><li>Inoltre, prova a ridurre numerose istruzioni OR in un’unica istruzione “uguale a qualsiasi di”. </li></ul> |
| Complessità della visualizzazione (filtri, metriche) | Il tipo di visualizzazione (ad esempio abbandono rispetto a una tabella a forma libera) aggiunta a un progetto non influenza di per sé molto le prestazioni del progetto. È la complessità della visualizzazione ad aumentare il tempo di elaborazione. | Fattori che aggiungono complessità a una visualizzazione includono:<ul><li>Intervallo dei dati richiesti</li><li>numero di filtri applicati; ad esempio, filtri utilizzati come righe di una tabella a forma libera</li><li>Utilizzo di filtri complessi</li><li>[Righe o colonne statiche di elementi in tabelle a forma libera](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md)</li><li>Filtri applicati a righe in tabelle a forma libera</li><li>Numero di metriche incluse, in particolare metriche calcolate che utilizzano i filtri</li></ul> | Se notate che i vostri progetti non si caricano rapidamente come desiderate, provate a sostituire alcuni filtri con eVar e filtri, dove possibile.<br><br>Se utilizzi sempre segmenti e metriche calcolate per punti dati importanti per la tua azienda, puoi migliorare la tua implementazione per acquisire questi punti dati in modo più diretto. L’utilizzo di un gestore di tag come Adobe Experience Platform Launch e delle regole di elaborazione di Adobe può rendere le modifiche di implementazione veloci e facili da applicare. |

## Messaggi di errore comuni

È possibile che, durante l’interazione con Analysis Workspace, si verifichino errori che influiscono anche sulle prestazioni. Di seguito sono elencati i tipi di errore più comuni, il motivo per cui si verificano e le ottimizzazioni possibili.

| Messaggio di errore | Perché si verifica? | Ottimizzazione  |
| --- | --- | --- |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una suite di rapporti specifica. Questo errore è causato da richieste API, progetti pianificati, rapporti pianificati, avvisi pianificati e utenti simultanei che eseguono richieste di generazione di rapporti. | Distribuisci le richieste e le pianificazioni per la suite di rapporti in modo più uniforme durante l’intera giornata. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe sta riscontrando un problema da risolvere. | Invia il codice di errore all’Assistenza clienti. |
| [!UICONTROL The request is too complex.] | La richiesta di generazione rapporti è troppo grande e non può essere eseguita. Questo errore è causato da timeout dovuti alla dimensione della richiesta, troppi elementi associati in un segmento o un filtro di ricerca, inclusione di troppe metriche, combinazioni di dimensioni e metriche incompatibili, ecc. | Semplifica la richiesta rimuovendo alcune colonne o righe nella tabella oppure prova a suddividere la tabella in più richieste distinte. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Il criterio del segmento o il filtro del rapporto è troppo ampio. | Limita i criteri di testo di ricerca e riprova. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | L’attribuzione non predefinita non è supportata per la dimensione in uso. | Sostituisci la dimensione nella tabella con una che sia compatibile con [Attribution IQ](/help/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | La tabella contiene troppe celle a forma libera (righe * colonne). | Rimuovi alcune colonne o righe nella tabella oppure prova a suddividere la tabella in più richieste distinte. |
