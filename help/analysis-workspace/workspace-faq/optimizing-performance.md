---
description: Fattori che influiscono sulle prestazioni di Workspace e sulle ottimizzazioni consigliate
title: ' fattori di prestazione e ottimizzazione Analysis Workspace'
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: 21bf268600c12dbf1db24dbc10028a0c29fc48a7
workflow-type: tm+mt
source-wordcount: '1939'
ht-degree: 15%

---


#  fattori di prestazione e ottimizzazione Analysis Workspace

Diversi fattori possono influenzare le prestazioni di un progetto in  Analysis Workspace. È importante sapere quali sono questi contributi prima di iniziare a creare un progetto in modo da poter pianificare e creare il progetto nel modo migliore. Questa pagina include un elenco di fattori che influiranno sulle prestazioni e le ottimizzazioni consigliate che potete effettuare per garantire prestazioni di picco in  Analysis Workspace.

>[!IMPORTANT]
>
>La pagina Prestazioni in  Analysis Workspace è in versione limitata. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/analytics/landing/an-releases.html)

## Aiuto > Prestazioni in  Analysis Workspace

Sotto **[!UICONTROL Analysis Workspace > Help > Performance]**, puoi vedere i fattori che influiscono sulle prestazioni del progetto, compresi rete, browser e fattori del progetto. Per ottenere i risultati più precisi, consentite che il progetto venga caricato completamente prima di aprire la pagina Prestazioni. Inoltre, potete **Scarica come CSV** i contenuti prestazionali da condividere con &#39;Assistenza clienti o con i team IT interni Adobe.

>[!NOTE]
>
>Le informazioni nella pagina Prestazioni variano ogni volta che si apre il modale, in quanto i fattori sono soggetti a modifiche. Inoltre,  Adobe continuerà a perfezionare le soglie consigliate non appena saranno disponibili ulteriori dati.

![](assets/performance-modal.png)

## Fattori di rete

**[!UICONTROL Help > Performance]** i fattori di rete includono:

| Factor | Definizione | Influenzato da | Ottimizzazione |
| --- | --- |--- | --- |
| Connessione al Adobe  |  Adobe invia 10 chiamate di test all&#39;apertura della pagina delle prestazioni. Rappresenta la percentuale di tali chiamate al Adobe  che hanno successo. | Problemi di rete locale o problemi  Adobe avranno un impatto su questo fattore. | Controllate status.adobe.com per verificare se esistono problemi noti relativi al servizio. Quindi, convalidare la connessione di rete locale. |
| Larghezza di banda Internet | La stima della larghezza di banda fornita dal browser in uso, verificata solo per Google Chrome. La soglia consigliata è 2,0 MB/s. | La connessione di rete locale influirà su questo fattore. | Convalida la connessione di rete locale. |
| Latenza Internet |  Adobe invia 10 chiamate di test all&#39;apertura della pagina delle prestazioni. Questo rappresenta il tempo medio impiegato per ogni richiesta per andare  Adobe e per essere restituita. Più semplicemente, è una misura di quanto velocemente internet è tra la vostra posizione e  Adobe. La soglia consigliata è &lt; 1 secondo. | Problemi di rete locali, molte schede del browser aperte o problemi  Adobe avranno un impatto su questo fattore. | Controllate status.adobe.com per verificare se esistono problemi noti relativi al servizio. Quindi, convalidate la connessione di rete locale e chiudete le schede del browser inutilizzate. |

## Fattori browser

**[!UICONTROL Help > Performance]** i fattori del browser includono:

| Factor | Definizione | Influenzato da | Ottimizzazione |
| --- | --- | --- | --- |
| Velocità di calcolo | Velocità di esecuzione di un test di elaborazione da parte del computer. La soglia consigliata è &lt; 750 ms. | L&#39;hardware e i programmi simultanei avranno un impatto su questo fattore. | Aprite Task Manager (PC) o Monitor attività (Mac) del computer per determinare se è possibile chiudere eventuali programmi. Quindi, chiudere le schede del browser inutilizzate o altri programmi. <br><br>Se tali azioni non sono di aiuto, parlate dei dettagli hardware con il team IT. |
| Memoria utilizzata | Ogni scheda Workspace in un browser Google Chrome condivide 4 GB di memoria in totale (Firefox ha una soglia più alta). Rappresenta la percentuale della quantità di memoria utilizzata dal progetto corrente. La soglia consigliata è 3500 MB, ovvero il punto in cui Workspace inizierà a presentare errori di memoria. | L&#39;utilizzo di più schede o il download di 50000 righe di dati contribuirà ad aumentare l&#39;utilizzo della memoria. | Se si riceve un errore di memoria, si consiglia di chiudere altre schede Workspace e/o di eseguire 50000 download di righe uno alla volta. |
| Archiviazione locale utilizzata | Dati memorizzati localmente sul computer per l&#39;utilizzo nel browser. Ciascuna origine (ad esempio experience.adobe.com) dispone di un limite di 10 MB. |  Analysis Workspace utilizza lo storage locale per diverse funzioni, tra cui l&#39;archiviazione di progetti salvati automaticamente (esistenti), le impostazioni utente e i flag di funzione. | Per evitare che  funzioni Analysis Workspace vengano interrotte, cancellare la memorizzazione locale per il dominio experience.adobe.com. |
| Velocità di rendering | &quot;FPS&quot; sta per &quot;Frame al secondo&quot;, ossia quante volte al secondo il browser disegna la pagina sullo schermo. 24 FPS è comunemente ciò che l&#39;occhio umano può osservare; se FPS è inferiore a questo, in Workspace verranno osservati i problemi di rendering. | FPS è influenzato dal multitasking in molti progetti Workspace contemporaneamente e dalle dimensioni del progetto visualizzato. Altri programmi in esecuzione sul computer possono avere un impatto, come streaming, scanner di fondo, ecc. Inoltre, l&#39;hardware influenzerà questo fattore. | Aprite Task Manager (PC) o Monitor attività (Mac) del computer per determinare se è possibile chiudere eventuali programmi. Quindi, chiudere le schede del browser inutilizzate o altri programmi. <br><br>Se tali azioni non sono di aiuto, parlate dei dettagli hardware con il team IT. |

## Fattori del progetto

**[!UICONTROL Help > Performance]** i fattori di progetto includono:

| Factor | Definizione | Ottimizzazione |
| --- | --- | --- |
| Numero di query | Il numero totale di query (richieste) effettuate  Adobe per recuperare i dati visualizzati nel progetto. Le query includono richieste classifica per tabelle, rilevamento di anomalie, grafici sparkline, componenti visualizzati nella barra a sinistra e altro ancora. Esclude i pannelli e le visualizzazioni compressi. La soglia consigliata è 100. | Semplificate il progetto laddove possibile suddividendo i dati in diversi progetti destinati a uno scopo specifico o a un gruppo di soggetti interessati. Utilizzare i tag per organizzare i progetti in temi e utilizzare [collegamento diretto](/help/analysis-workspace/curate-share/shareable-links.md) creare un sommario interno in modo che gli interessati possano trovare più facilmente ciò di cui hanno bisogno. |
| Pannelli espansi (dal totale dei pannelli) | Numero di pannelli espansi rispetto al numero totale di pannelli nel progetto. La soglia consigliata è 5. | Dopo aver effettuato i passaggi necessari per semplificare il progetto, comprimete i pannelli nel progetto che non devono essere visualizzati al momento del caricamento. Quando il progetto viene aperto, vengono elaborati solo i pannelli espansi. I pannelli compressi non vengono elaborati finché l’utente li espande. |
| Visualizzazioni estese (fuori dal totale delle visualizzazioni) | Numero di tabelle e visualizzazioni espanse rispetto al totale del progetto. Esclude le origini dati nascoste. La soglia consigliata è 15. | Dopo aver effettuato i passaggi necessari per semplificare il progetto, comprimi le visualizzazioni nel progetto che non è necessario visualizzare al momento del caricamento. Definite le priorità per gli elementi visivi più importanti per il consumatore del rapporto e suddividete gli elementi visivi di supporto in un pannello o progetto separato e più dettagliato, se necessario. |
| Numero di celle a forma libera | Il numero totale di celle di tabella a forma libera nel progetto, calcolato da righe * colonne in tutte le tabelle. Esclude le origini dati nascoste. La soglia consigliata è 4000. | Ridurre il numero di colonne nella tabella fino ai punti dati più rilevanti. Ridurre il numero di righe nella tabella regolando il numero di righe visualizzate, applicando un filtro tabella o applicando un segmento. |
| Componenti disponibili | Il numero totale di componenti recuperati nella parte sinistra del progetto, in tutte le suite di rapporti nel progetto. La soglia consigliata è 2000. | Parla con l&#39;amministratore del prodotto per creare una suite di rapporti virtuale specifica con un set di componenti più personalizzato. |
| Componenti utilizzati | Numero totale di componenti utilizzati nel progetto. La soglia consigliata è 100. | Il numero di componenti utilizzati non influisce direttamente sulle prestazioni. Tuttavia, la complessità di tali componenti contribuirà alle prestazioni del progetto. Consultate le ottimizzazioni consigliate nella sezione &quot;Fattori aggiuntivi&quot; di seguito. |
| Intervallo di date più lungo | Questo fattore visualizza l&#39;intervallo di date più lungo utilizzato nel progetto. La soglia consigliata è di 1 anno. | Dove possibile, non inserire più dati del necessario. Limita il calendario del pannello alle date pertinenti per l’analisi o utilizza i componenti dell’intervallo di date (componenti viola) nelle tabelle a forma libera. Gli intervalli di date utilizzati in una tabella prevalgono sull’intervallo di date del pannello. Ad esempio, è possibile aggiungere il mese scorso, la settimana scorsa e il giorno precedente alle colonne della tabella per richiedere tali intervalli di dati specifici. Per ulteriori informazioni sulle attività con gli intervalli di date in Analysis Workspace, guarda [questo video](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html). <br><br>Inoltre, riducete al minimo il numero di confronti su base annua utilizzati nel progetto. Quando viene calcolato un confronto tra un anno e l&#39;altro, il confronto tra i 13 mesi di dati viene eseguito tra i mesi di interesse. Questo ha lo stesso impatto di un&#39;eventuale modifica dell&#39;intervallo di date del pannello fino a 13 mesi. |

## Altri fattori

Altri fattori non inclusi in Aiuto > Prestazioni:

| Factor | Definizione | Influenzato da | Ottimizzazione |
| --- | --- | --- | --- |
| Complessità del filtro | Filtri intricati possono avere un impatto significativo sulle prestazioni del progetto. | Fattori che aggiungono complessità a un filtro (in ordine decrescente di impatto) includono: <ul><li>Operatori di “contiene”, “contiene”, “contiene qualsiasi di”, “corrisponde”, “inizia con” o “finisce con” </li><li>Filtri sequenziali, in particolare quando vengono utilizzate le limitazioni di dimensione (Within/After) </li><li>Numero di elementi di dimensione unica, compresa nelle dimensioni utilizzate nel segmento, (ad es. Pagina = “A” quando la Pagina ha 10 elementi unici sarà più veloce della Pagina = “A” quando la Pagina ha 100.000 elementi unici) </li><li>Numero di diverse dimensioni utilizzate (ad es. Pagina = “Home” e Pagina = “Risultati della ricerca” sarà più veloce di eVar 1 = “rosso” ed eVar 2 = “blu”)</li><li>Molti operatori OR (invece di AND)</li><li>Contenitori nidificati di vario ambito (ad es., “Hit” all’interno di “Visita” all’interno di “Visitatore”)</li></ul> | Non è possibile evitare alcuni fattori di complessità, ma cercare le opportunità per ridurre la complessità dei filtri. In generale, quanto più specifici possono essere i criteri di filtro, tanto meglio è. Ad esempio:<ul><li>Con i contenitori, l’utilizzo di un singolo contenitore nella parte superiore del segmento sarà più veloce di una serie di contenitori nidificati</li><li>Con l’utilizzo degli operatori, “uguale a” sarà più veloce di “contiene” e “uguale a qualsiasi di” sarà più veloce di “contiene qualsiasi di”</li><li>Con molti criteri, gli operatori AND saranno più veloci di una serie di operatori OR.</li><li>Cercare le opportunità per ridurre molte istruzioni OR in un&#39;unica istruzione &quot;uguale a qualsiasi&quot;.</li></ul> |
| Complessità della visualizzazione (filtri, metriche) | Il tipo di visualizzazione (ad esempio abbandono rispetto a una tabella a forma libera) aggiunta a un progetto non influenza di per sé molto le prestazioni del progetto. È la complessità della visualizzazione ad aumentare il tempo di elaborazione. | Fattori che aggiungono complessità a una visualizzazione includono:<ul><li>Intervallo dei dati richiesti</li><li>numero di filtri applicati; ad esempio, filtri utilizzati come righe di una tabella a forma libera</li><li>Utilizzo di filtri complessi</li><li>[Righe o colonne statiche di elementi in tabelle a forma libera](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md)</li><li>Filtri applicati a righe in tabelle a forma libera</li><li>Numero di metriche incluse, in particolare metriche calcolate che utilizzano i filtri</li></ul> | Se notate che i vostri progetti non si caricano rapidamente come desiderate, provate a sostituire alcuni filtri con eVar e filtri, dove possibile.<br><br>Se utilizzi continuamente segmenti e metriche calcolate per punti dati importanti per la tua attività, puoi prendere in considerazione la possibilità di migliorare l&#39;implementazione per acquisire questi punti dati in modo più diretto. L&#39;utilizzo di un gestore di tag come  Adobe Experience Platform Launch e  regole di elaborazione  Adobe può rendere le modifiche di implementazione veloci e facili da implementare. |

## Messaggi di errore comuni

È possibile che si verifichino errori durante l&#39;interazione con  Analysis Workspace che influiscono anche sulle prestazioni. Di seguito sono elencati i tipi di errore più comuni, il motivo per cui si verificano e le ottimizzazioni che possono essere effettuate.

| Messaggio di errore | Perché si verifica? | Ottimizzazione |
| --- | --- | --- |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una suite di rapporti specifica. Questo errore è causato da richieste API, progetti pianificati, rapporti pianificati, avvisi pianificati e utenti simultanei che eseguono richieste di generazione di rapporti. | Distribuite le richieste e le pianificazioni per la suite di rapporti in modo più uniforme durante l&#39;intera giornata. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe sta riscontrando un problema da risolvere. | Invia il codice di errore all&#39;Assistenza clienti. |
| [!UICONTROL The request is too complex.] | La richiesta di generazione rapporti è troppo grande e non può essere eseguita. Questo errore è causato da timeout dovuti alla dimensione della richiesta, troppi elementi associati in un segmento o un filtro di ricerca, inclusione di troppe metriche, combinazioni di dimensioni e metriche incompatibili, ecc. | Semplificate la richiesta rimuovendo alcune colonne o righe nella tabella oppure prendete in considerazione la possibilità di suddividere la tabella in richieste separate. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Il criterio del segmento o il filtro del report è troppo ampio. | Limita i criteri di ricerca e riprova la richiesta. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | L&#39;attribuzione non predefinita non è supportata per la dimensione in uso. | Sostituire la dimensione nella tabella con una che sia compatibile con [Attribution IQ ](/help/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Nella tabella sono presenti troppe celle a forma libera (riga * colonne). | Rimuovere colonne o righe nella tabella oppure suddividere la tabella in richieste separate. |
