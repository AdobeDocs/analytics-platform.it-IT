---
description: 'null'
title: Ottimizzare le prestazioni di Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 97%

---


# Ottimizzare le prestazioni di Analysis Workspace

>[!NOTE]
>
>Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Alcuni fattori possono influenzare le prestazioni di un progetto in Analysis Workspace. È importante sapere cosa sono questi contributi prima di iniziare a creare un progetto, in modo da essere in grado di pianificare e creare il progetto nel modo migliore. Di seguito è riportato un elenco di fattori che influiranno sulle prestazioni e sulle tecniche consigliate per l’ottimizzazione dei tuoi progetti. Le prestazioni di Analysis Workspace rappresentano una delle principali priorità di Adobe e un aspetto che continuiamo a migliorare giorno dopo giorno.

## Complessità della logica dei segmenti

Segmenti complessi possono avere un impatto significativo sulle prestazioni del progetto. I fattori che aggiungono complessità a un segmento (in ordine approssimativo di impatto) includono:

* Operatori di “contiene”, “contiene”, “contiene qualsiasi di”, “corrisponde”, “inizia con” o “finisce con”
* La segmentazione sequenziale avviene specialmente quando si utilizzano restrizioni delle dimensioni (entro/dopo)
* Numero di elementi di dimensione unica, compresa nelle dimensioni utilizzate nel segmento, (ad es. Pagina = “A” quando la Pagina ha 10 elementi unici sarà più veloce della Pagina = “A” quando la Pagina ha 100.000 elementi unici)
* Numero di diverse dimensioni utilizzate (ad es. Pagina = “Home” e Pagina = “Risultati della ricerca” sarà più veloce di eVar 1 = “rosso” ed eVar 2 = “blu”)
* Molti operatori OR (invece di AND)
* Contenitori nidificati di vario ambito (ad es., “Hit” all’interno di “Visita” all’interno di “Visitatore”)

**Procedure consigliate per la complessità logica**

Mentre alcuni dei fattori di complessità non possono essere evitati, pensa alle opportunità di ridurre la complessità dei tuoi segmenti. In generale, più si può essere specifici con i propri criteri di segmento, meglio è. Ad esempio:

* Con i contenitori, l’utilizzo di un singolo contenitore nella parte superiore del segmento sarà più veloce di una serie di contenitori nidificati
* Con l’utilizzo degli operatori, “uguale a” sarà più veloce di “contiene” e “uguale a qualsiasi di” sarà più veloce di “contiene qualsiasi di”
* Con molti criteri, gli operatori AND saranno più veloci di una serie di operatori OR. Inoltre, cerca opportunità per ridurre molte istruzioni OR in un’unica istruzione “uguale a qualsiasi di”

Inoltre, l’uso delle [classificazioni](https://docs.adobe.com/content/help/en/analytics/components/classifications/c-classifications.html) può aiutare a consolidare più valori in gruppi compatti, dai quali è possibile creare dei segmenti. La segmentazione dei gruppi di classificazione offre vantaggi in termini di prestazioni, in particolare per i segmenti che contengono numerose istruzioni OR o criteri “contiene”.

## Intervallo dei dati richiesti

L’intervallo dei dati richiesti nell’ambito di un progetto influenzerà le prestazioni di Analysis Workspace.

**Procedure consigliate per l’intervallo di dati**

Dove possibile, non inserire più dati del necessario.

Ricorda che gli intervalli di date (componenti viola) ignorano l’intervallo date del pannello. Come risultato, se stai utilizzando diversi intervalli di date come colonne (ad es. colonne ultimo mese, ultima settimana e ieri), il pannello intervallo date non deve estendere tutti gli intervalli date delle colonne. Può essere impostato semplicemente su domani, in quanto gli intervalli di date utilizzati nella tabella a forma libera ignoreranno il pannello. Per ulteriori informazioni sulle attività con gli intervalli di date in Analysis Workspace, guarda [questo video](https://www.youtube.com/watch?v=ybmv6EBmhn0).

Usa [opzioni di confronto date](/help/components/date-ranges/time-comparison.md) per richiamare gli specifici periodi di tempo dei dati che desideri confrontare. Ad esempio, se vuoi visualizzare i dati del mese scorso rispetto ai dati dello stesso mese dello scorso anno, invece di impostare il pannello sugli ultimi 13 mesi di dati, puoi semplicemente utilizzare l’opzione di confronto di periodi di tempo per mostrare le prestazioni anno-su-anno.

## Numero di visualizzazioni

Il numero di visualizzazioni di grafico contenute in un progetto influenzeranno la responsività complessiva di Analysis Workspace.

**Procedure consigliate per il numero di visualizzazioni**

Diminuisci il numero di visualizzazioni nel tuo progetto. Analysis Workspace effettua un gran numero di elaborazioni in background per ogni visualizzazione che aggiungi; pertanto dai priorità alle visualizzazioni più importanti per l’utilizzatore del rapporto e, se necessario, suddividi le visualizzazioni di supporto in progetti separati e più dettagliati.

## Complessità delle visualizzazioni (segmenti, metriche, filtri)

Il tipo di visualizzazione (ad es. abbandono rispetto a una tabella a forma libera) aggiunta a un progetto di per sé non influenza molto le prestazioni del progetto. È la complessità della visualizzazione che influenzerà il tempo di elaborazione. Fattori che aggiungono complessità a una visualizzazione includono:

* Intervallo dei dati richiesti, così come riportato sopra
* Numero di segmenti applicati; ovvero segmenti utilizzati come righe di una tabella a forma libera
* Utilizzo di segmenti complessi
* Righe o colonne statiche di elementi in tabelle a forma libera
* Filtri applicati a righe in tabelle a forma libera
* Numero di metriche incluse, in particolare metriche calcolate che utilizzano segmenti

**Procedure consigliate per la complessità delle visualizzazioni**

Se noti che i tuoi progetti non si caricano rapidamente tanto quanto vorresti, prova a sostituire alcuni segmenti con eVar e filtri, ove possibile.

Se utilizzi costantemente segmenti e metriche calcolate per punti dati importanti per la tua azienda, puoi prendere in considerazione il miglioramento della tua implementazione per acquisire questi punti dati in modo più diretto. L’utilizzo di un gestore di tag come Adobe Experience Platform Launch e delle regole di elaborazione di Adobe possono rendere le modifiche di implementazione veloci e facili da applicare. Per capire meglio come semplificare i segmenti più complessi, vedi “Complessità della logica dei segmenti” sopra.

## Numero di pannelli

Un pannello può contenere diverse visualizzazioni e, come risultato, il numero di pannelli può influire anche sulla responsività globale di Analysis Workspace.

**Procedure consigliate per il numero di pannelli**

Non cercare di aggiungere tutti gli elementi a un progetto; piuttosto crea progetti diversi per uno scopo preciso o per un determinato gruppo di soggetti interessati. Utilizza i tag per organizzare i progetti in temi chiave e condividi i progetti correlati con i soggetti interessati.

Se desideri progetti più organizzati, ricorda che il [collegamento diretto](https://www.youtube.com/watch?v=6IOEewflG2U) al tuo prodotto potrebbe rappresentare una possibilità. Crea un indice interno di progetti in modo che i soggetti interessati possano trovare più facilmente ciò di cui hanno bisogno.

Se sono necessari più pannelli in Workspace, comprimili prima di salvare e condividere. Al caricamento di un progetto, Analysis Workspace caricherà solo i contenuti dei pannelli espansi. I pannelli compressi vengono caricati solo se l’utente li espande. Questo approccio è utile in due modi:

* I pannelli compressi consentono di ridurre il tempo di caricamento complessivo di un progetto
* I pannelli compressi sono molto utili per organizzare i progetti in modo logico per l’utente del rapporto

## Dimensione della suite di rapporti

La dimensione della suite di rapporti può sembrare un fattore fondamentale, ma in realtà riveste un’importanza limitata per via del modo in cui Adobe gestisce l’elaborazione dati.

## Diversi utenti accedono simultaneamente ad Analysis Workspace

Il numero di utenti che accede contemporaneamente ad Analysis Workspace o agli specifici progetti non ha un effetto sostanziale sulle prestazioni di Analysis Workspace a patto che gli utenti vi accedano da suite di rapporti diverse. Se gli utenti accedono contemporaneamente dalla stessa suite di rapporti, le prestazioni risulteranno compromesse.

## Messaggi di errore comuni in Analysis Workspace

È possibile che si verifichino errori durante l’interazione con Analysis Workspace. Gli errori possono verificarsi per diversi motivi. Di seguito sono elencati i più comuni.

| Messaggio di errore | Perché si verifica? |
|---|---|
| `The report suite is experiencing unusually heavy reporting. Please try again later.` | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una suite di rapporti specifica. Questo errore è causato da richieste API, progetti pianificati, rapporti pianificati, avvisi pianificati e utenti simultanei che eseguono richieste di generazione di rapporti. È consigliato distribuire in modo più uniforme nel corso della giornata le richieste e le pianificazioni per la suite di rapporti. |
| `A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.` | Adobe sta riscontrando un problema da risolvere. È consigliato inviare il codice di errore tramite una richiesta dell’Assistenza clienti. |
| `The request is too complex.` | La richiesta di generazione rapporti è troppo grande e non può essere eseguita. Questo errore è causato da timeout dovuti alla dimensione della richiesta, troppi elementi associati in un segmento o un filtro di ricerca, inclusione di troppe metriche, combinazioni di dimensioni e metriche incompatibili, ecc. È consigliato semplificare la richiesta. |
| `One of the segments or the search in this visualization contains a text search that returned too many results.` | È consigliato restringere i criteri di testo di ricerca e riprovare. |
| `This dimension does not currently support non-default attribution models.` | È consigliato sostituire la dimensione nella tabella con una compatibile con [Attribution IQ](../attribution/overview.md). |
| `Your request failed as a result of too many columns or pre-configured rows.` | È consigliato rimuovere alcune colonne o righe oppure suddividerle in visualizzazioni separate. |
