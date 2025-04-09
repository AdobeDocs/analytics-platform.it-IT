---
description: Configurare una visualizzazione area di lavoro del percorso
title: Area di lavoro percorso
feature: Visualizations
role: User
exl-id: 53984934-6fba-4f15-aeeb-d91039260553
source-git-commit: 2b291c4aabfd6857dc29af0338760be80f179384
workflow-type: tm+mt
source-wordcount: '6204'
ht-degree: 1%

---

# Configurare una visualizzazione area di lavoro del percorso

La visualizzazione area di lavoro Percorso consente di analizzare e ottenere informazioni approfondite sui percorsi forniti a utenti e clienti.

![Area di lavoro Percorsi](assets/journey-canvas.png)

## Panoramica dell’area di lavoro del percorso

Per ulteriori informazioni sull&#39;area di lavoro di Percorso, vedere [Panoramica sull&#39;area di lavoro di Percorso](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md), tra cui:

* Funzioni chiave

* Potenziali informazioni

* Differenze tra area di lavoro del Percorso e Abbandono

* Dettagli sull&#39;analisi dei percorsi di Journey Optimizer

* E altro ancora

## Iniziare a creare una visualizzazione canvas Journey

1. Aggiungi un pannello vuoto al progetto, seleziona l&#39;icona [!UICONTROL **Visualizzazioni**] nella barra sinistra, quindi trascina la ![visualizzazione canvas **]GraphPathing](/help/assets/icons/Branch3.svg)[!UICONTROL ** Journey nel pannello.

   Oppure

   Aggiungi una visualizzazione area di lavoro Percorso in uno dei modi descritti nella sezione [Aggiungere visualizzazioni a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) in [Panoramica delle visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

   ![Configurazione area di lavoro Percorsi](assets/journey-canvas-configure.png)

1. Specificare le informazioni di base seguenti per configurare l&#39;area di lavoro del Percorso:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Metrica principale**] | Determina la metrica utilizzata per calcolare i valori percentuali e numerici su ciascun nodo del percorso.<p>**Nota**: l&#39;ambito dei dati inclusi in ogni valore percentuale e numerico è determinato dalla metrica scelta nel campo **[!UICONTROL Journey canvas container]**. Se ad esempio **[!UICONTROL Person]** è impostato come contenitore, le statistiche visualizzate nel percorso si estendono su più sessioni per una determinata persona. Se **[!UICONTROL Session]** è impostato come contenitore, le statistiche mostrate nel percorso sono vincolate a una singola sessione definita per una determinata persona.</p><p>Considera gli esempi seguenti di come la metrica primaria influisce sui valori percentuali e numerici di ciascun nodo:</p><ul><li>Se _Persone_ è la metrica principale e _Persona_ è il contenitore, solo le persone che hanno un evento che corrisponde ai criteri di ogni nodo successivo nel percorso si spostano in tutto il percorso. L’abbandono si verifica su un nodo quando una persona non è mai arrivata a nessuno dei nodi immediatamente successivi nel percorso. Potrebbero aver eseguito altre azioni sul sito, ma non soddisfano i criteri definiti da nessuno dei nodi che seguono immediatamente.</li><li>Se _Persone_ è la metrica principale e _Sessione_ è il contenitore, solo le persone che hanno un evento che corrisponde ai criteri di ogni nodo del percorso all&#39;interno di una singola sessione si spostano in tutto il percorso. L’abbandono si verifica su un nodo quando una persona non è mai arrivata a nessuno dei nodi immediatamente successivi nel percorso all’interno di una singola sessione. Potrebbero aver eseguito altre azioni sul sito all’interno della sessione, ma non soddisfano i criteri definiti da nessuno dei nodi che seguono immediatamente.</li></ul> <p>La metrica principale influisce sui seguenti aspetti della visualizzazione dell’area di lavoro del Percorso:</p><ul><li>Numero totale visualizzato su ciascun nodo.  <p>Ad esempio, se Eventi è la metrica principale, ogni nodo mostra il numero di persone che hanno avuto un evento che corrisponde ai criteri di quel nodo (e di ogni nodo precedente che lo precede nel percorso).</p></li><li>La percentuale visualizzata su ciascun nodo. Una volta creata la visualizzazione, è possibile utilizzare il menu a discesa **[!UICONTROL Percentage value]** per scegliere di visualizzare la percentuale del totale, la percentuale del nodo precedente o la percentuale del nodo iniziale.<p>Ad esempio, se Eventi è la metrica principale, ogni nodo mostra la percentuale di persone che hanno avuto un evento che corrisponde ai criteri di quel nodo (e di ogni nodo precedente che lo precede nel percorso).</p></li><li>Quando una dimensione viene aggiunta alla visualizzazione, vengono aggiunti i primi 3 nodi della visualizzazione, in base alla metrica principale.</li></ul> |
   | [!UICONTROL **Metrica secondaria**] | Determina la metrica secondaria utilizzata per calcolare i valori percentuali e numerici su ciascun nodo del percorso. La metrica secondaria è facoltativa. <p>**Nota**: l&#39;ambito dei dati inclusi in ogni valore percentuale e numerico è determinato dalla metrica scelta nel campo **[!UICONTROL Journey canvas container]**. Se ad esempio **[!UICONTROL Person]** è impostato come contenitore, le statistiche visualizzate nel percorso si estendono su più sessioni per una determinata persona. Se **[!UICONTROL Session]** è impostato come contenitore, le statistiche mostrate nel percorso sono vincolate a una singola sessione definita per una determinata persona.</p><p>La configurazione di una metrica secondaria influisce sui seguenti aspetti della visualizzazione dell’area di lavoro del Percorso:</p><ul><li>Il numero totale visualizzato su ciascun nodo sotto la metrica principale. <p>Ad esempio, se Account è la metrica secondaria, il numero di account viene visualizzato sul nodo per tutte le persone che hanno raggiunto tale nodo nel percorso.</p></li><li>La percentuale visualizzata su ciascun nodo sotto la metrica principale. Una volta creata la visualizzazione, puoi scegliere di mostrare la percentuale del totale o del nodo iniziale.</li><p>Ad esempio, se Sessioni è la metrica secondaria, ogni nodo mostra la percentuale di sessioni che hanno raggiunto tale nodo nel percorso (la percentuale del totale o del nodo iniziale).</p></li></ul> |
   | [!UICONTROL **percorso Journey Optimizer**]<!-- name? --> | Seleziona il percorso Journey Optimizer da utilizzare come base per l’analisi nell’area di lavoro del Percorso. Sono disponibili percorsi con uno dei seguenti stati: Live, Arrestato o Finito <p>In alternativa, puoi lasciare vuota questa opzione se desideri un’area di lavoro vuota da cui generare l’analisi in Analysis Workspace.</p> <p>Quando si analizza un percorso Journey Optimizer nell&#39;area di lavoro del Percorso, il percorso viene visualizzato con l&#39;ordine, la sequenza e la struttura di Journey Optimizer. Per ulteriori informazioni, vedere [Analizzare i percorsi Journey Optimizer](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) in [Panoramica area di lavoro Percorsi](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Nota**: questa opzione viene visualizzata solo quando i dati di Journey Optimizer vengono rilevati nella stessa visualizzazione dati selezionata nel pannello Analysis Workspace in cui si sta aggiungendo la visualizzazione. Per informazioni sulla modifica della visualizzazione dati in un pannello di Analysis Workspace, vedi [Panoramica di Analysis Workspace](/help/analysis-workspace/home.md).</p> |

1. (Facoltativo) Seleziona [!UICONTROL **Mostra impostazioni avanzate**], quindi specifica le seguenti informazioni:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **contenitore area di lavoro Percorsi**] | Scegli il contenitore su cui concentrarti in tutto il percorso. Il contenitore scelto determina l’ambito dei dati acquisiti nel percorso. Questo influisce sulle statistiche visualizzate nella visualizzazione. Se i nomi dei contenitori sono diversi da quelli predefiniti mostrati di seguito, significa che sono stati personalizzati nella visualizzazione dati.<ul><li>**Sessione:** limita le statistiche della visualizzazione in modo che rientrino in una singola sessione definita per una persona specificata. Ciò significa che i numeri e le percentuali visualizzati su ciascun nodo (che sono basati sulle metriche primaria e secondaria) devono verificarsi all’interno di una singola sessione per ogni persona. In altre parole, una persona può essere rappresentata più volte in un singolo percorso.<p>Questo contenitore utilizza la metrica Sessioni.</p></li><li>**Persona:** (impostazione predefinita) consente alle statistiche della visualizzazione di occupare più sessioni per una determinata persona. Ciò significa che i numeri e le percentuali visualizzati su ciascun nodo (che sono basati sulle metriche primaria e secondaria) possono verificarsi in qualsiasi numero di sessioni, purché le sessioni appartengano alla stessa persona. In altre parole, una persona può essere rappresentata una sola volta in un singolo percorso.<p>Questo contenitore utilizza la metrica Persone.</p></li></ul> |

1. Seleziona [!UICONTROL **Build**].

   Se avete selezionato un percorso Journey Optimizer, il percorso viene visualizzato con lo stesso ordine, sequenza e struttura di Journey Optimizer. (Solo gli utenti con accesso a Ottimizzatore Percorso possono selezionare un percorso Journey Optimizer).

   <!-- add screen shot -->

   Se non hai selezionato un percorso Journey Optimizer, viene visualizzata un’area di lavoro vuota in cui puoi iniziare ad aggiungere nodi al percorso. (Solo gli utenti con accesso a Ottimizzatore Percorso possono selezionare un percorso Journey Optimizer).

   <!-- add screen shot -->

1. Sia che si crei una nuova analisi da un&#39;area di lavoro vuota o che si analizzi un percorso Journey Optimizer, è possibile configurare il percorso come descritto in [Configurare le impostazioni di visualizzazione](#configure-visualization-settings).


## Configurare le impostazioni di visualizzazione

Nell&#39;intestazione dell&#39;area di lavoro Journey sono disponibili varie opzioni di configurazione.

Per configurare le impostazioni per la visualizzazione dell&#39;area di lavoro Viaggio:

1. In Analysis Workspace, apri una visualizzazione canvas Journey esistente o [inizia a crearne una nuova](#begin-building-a-journey-canvas-visualization).

   Opzioni che consentono di configurare la visualizzazione canvas Journey sono disponibili nell&#39;intestazione:

   ![Opzioni intestazione Journey Canvas](assets/journey-canvas-header.png)

1. Configura una delle seguenti impostazioni visualizzate nella parte superiore della visualizzazione:

   | Impostazione | Funzione |
   |---------|----------|
   | [!UICONTROL **Valore percentuale**] | Il valore percentuale mostrato su ciascun nodo nel percorso.<p>![valore percentuale](assets/journey-canvas-percentage.png)</p> <p>Quando configuri i valori percentuali visualizzati sui nodi del percorso, considera quanto segue:</p><ul><li>Su ogni nodo viene visualizzata una percentuale per la metrica principale. Viene visualizzata anche una percentuale per la metrica secondaria, se ne è stata configurata una. Per ulteriori informazioni sulle impostazioni delle metriche primaria e secondaria, vedere [Inizia a creare una visualizzazione dell&#39;area di lavoro di Percorso](#begin-building-a-journey-canvas-visualization).</li><li>Le percentuali includono tutte le persone o le sessioni incluse nella visualizzazione dati all’interno dell’intervallo di date del pannello. L&#39;utilizzo di _persone_ o _sessioni_ dipende dall&#39;impostazione del contenitore. Per ulteriori informazioni sull&#39;impostazione del contenitore, vedere [Inizia a creare una visualizzazione dell&#39;area di lavoro di Percorso](#begin-building-a-journey-canvas-visualization).</li></ul> <p>Scegli tra le seguenti opzioni:</p> <ul><li>[!UICONTROL **Percentuale del nodo iniziale**]: calcola le percentuali visualizzate in ogni nodo in relazione al nodo iniziale. Le percentuali si basano sulla metrica principale e secondaria selezionata. <p>Un nodo _start_ è un nodo che non ha nodi connessi che lo precedono.</p><p>Un percorso può contenere più nodi iniziali. Tuttavia, viene utilizzato il [!UICONTROL **Percentuale del totale**] se il percorso contiene 2 o più nodi iniziali che conducono a un nodo comune. Se desideri utilizzare il [!UICONTROL **Percentuale del nodo iniziale**], aggiorna il percorso in modo che ogni nodo del percorso possa essere ricondotto a un singolo nodo iniziale.</p></li><li>[!UICONTROL **Percentuale del nodo precedente**]: calcola le percentuali visualizzate in ogni nodo in relazione al nodo precedente. Le percentuali si basano sulla metrica principale e secondaria selezionata.</li><li>[!UICONTROL **Percentuale del totale**]: calcola le percentuali visualizzate in ogni nodo in relazione a tutti i dati nella visualizzazione dati. Le percentuali si basano sulla metrica principale e secondaria selezionata.</li></ul> |
   | [!UICONTROL **Impostazioni freccia**] | Le frecce visualizzate tra i nodi nell’area di lavoro del Percorso possono essere configurate per mostrare etichette e valori personalizzati. <p>![impostazioni freccia](assets/journey-canvas-arrow-settings.png)</p><p>_Le etichette_ sono nomi personalizzati visualizzati sulle frecce. Su una determinata freccia viene visualizzata una sola etichetta. Le etichette possono essere una qualsiasi delle seguenti e sono visualizzate in questo ordine di preferenza:</p><ol><li>Nome personalizzato aggiunto dall&#39;area di lavoro del Percorso (come descritto in [Aggiungere o aggiornare un&#39;etichetta su una freccia](#add-or-update-a-label-on-an-arrow))</li><li>Etichetta Journey Optimizer</li><li>Una condizione Journey Optimizer</li></ol><p>_I valori_ sono i numeri e le percentuali visualizzati sulle frecce e indicano le persone o le sessioni che si sono spostate da un nodo al nodo successivo nel percorso. (In altre parole, coloro che non sono usciti dal percorso in un determinato momento). </p><p>Le seguenti opzioni sono disponibili per i percorsi che non provengono da Journey Optimizer e per i percorsi Journey Optimizer che non sono stati modificati in modo significativo nell’area di lavoro del Percorso: (le modifiche più importanti includono l’aggiunta o la rimozione di nodi, l’aggiunta o la rimozione di frecce o la modifica dei componenti di un nodo).</p><ul><li>[!UICONTROL **Nessuna etichetta**]: nessuna etichetta visualizzata sulle frecce del percorso. </br> Questa opzione è disponibile solo se il percorso è stato modificato in </li><li>[!UICONTROL **Solo etichette**]: le etichette sono visualizzate sulle frecce del percorso.</li></ul><p>Per i percorsi Journey Optimizer che sono stati modificati in modo significativo nell&#39;area di lavoro del Percorso sono disponibili le seguenti opzioni: (le modifiche significative includono l&#39;aggiunta o la rimozione di nodi, l&#39;aggiunta o la rimozione di frecce o la modifica dei componenti di un nodo.)(**Nota**: queste opzioni vengono visualizzate solo quando i dati di Journey Optimizer vengono rilevati nella stessa visualizzazione dati selezionata nel pannello Analysis Workspace in cui si sta aggiungendo la visualizzazione. Per informazioni sulla modifica della visualizzazione dati in un pannello di Analysis Workspace, vedi [Panoramica di Analysis Workspace](/help/analysis-workspace/home.md).)</p><ul><li>[!UICONTROL **Nessuna etichetta o valore**]: nessuna etichetta o valore visualizzato sulle frecce del percorso.</li><li>[!UICONTROL **Solo etichette**]: solo le etichette sono visualizzate sulle frecce del percorso. I valori non vengono visualizzati.</li><li>[!UICONTROL **Solo valori**]: nelle frecce del percorso vengono visualizzati solo i valori. Le etichette non vengono visualizzate.</li><li>[!UICONTROL **Valori ed etichette**]: le etichette e i valori sono visualizzati su frecce nel percorso.</li></ul> |
   | [!UICONTROL **Mostra abbandono**] | I dati di fallout mostrano una percentuale e un numero che non rientrano in ciascun nodo del percorso. I dati di fallout si basano sulla metrica associata alle impostazioni del contenitore del percorso; non si basano sulla metrica principale o secondaria. <p>![abbandono](assets/journey-canvas-fallout.png)</p><p>Per impostazione predefinita, il contenitore è _Persona_, quindi la metrica utilizzata per i dati di fallout è _Persone_. Se il contenitore viene modificato in _Sessione_, la metrica utilizzata per i dati di fallout è _Sessioni_ e così via.</p><p>Se, ad esempio, l&#39;impostazione del contenitore è _Persona_, l&#39;abbandono mostra la percentuale e il numero di persone in ogni nodo del percorso che non sono mai arrivate ai nodi immediatamente successivi. Potrebbero aver eseguito altre azioni sul sito, ma non soddisfano i criteri definiti da nessuno dei nodi che seguono immediatamente.</p> <p>Per ulteriori informazioni sull&#39;impostazione del contenitore Area di lavoro di Percorso, vedere [Inizia a creare una visualizzazione Area di lavoro di Percorso](#begin-building-a-journey-canvas-visualization). |
   | **Controlli zoom** | Nell’angolo superiore destro dell’area di lavoro sono disponibili i seguenti controlli di zoom:<ul><li>**Zoom in** ![icona Zoom in](assets/zoom-in-icon.png): ingrandisce aree specifiche della visualizzazione.<p>È inoltre possibile utilizzare i controlli del mouse, ad esempio il pizzicamento su un trackpad.</p></li><li>**Zoom indietro** ![icona Zoom indietro](assets/zoom-out-icon.png): riduce la visualizzazione per consentire più spazio nell&#39;area di lavoro.<p>È inoltre possibile utilizzare i controlli del mouse, ad esempio il pizzicamento su un trackpad.</p></li><li>**Adatta schermo** ![icona Adatta schermo](assets/fill-screen-icon.png): regola le impostazioni correnti di zoom e scorrimento per riempire lo schermo con la visualizzazione completa.</li></ul><p>Per spostarsi nell&#39;area di lavoro dopo aver eseguito lo zoom avanti o indietro, fare clic con il mouse e trascinare nella posizione desiderata.</p> |

1. Continua con [Aggiungi nodi](#add-nodes).

## Aggiungi nodi

I nodi in una visualizzazione canvas Journey rappresentano gli eventi o le azioni di un percorso utente.

Puoi creare i nodi nei seguenti modi: trascinando Area di lavoro componenti dal barra sinistro all&#39;area di lavoro; consentendo a Journey canvas di scegliere i nodi successivi o precedenti in alto in base ai nodi esistenti; o duplicando nodi esistenti.

### Trascina i componenti dalla barra a sinistra

1. In Analysis Workspace, apri una visualizzazione dell&#39;area di lavoro del Percorso esistente oppure [creane una nuova](#begin-building-a-journey-canvas-visualization).

1. Trascina metriche, dimensioni, elementi dimensionali, filtri o intervalli di date dalla barra a sinistra all’area di lavoro. Sono supportate le metriche basate su un [campo derivato](/help/data-views/derived-fields/derived-fields.md). Tuttavia, le metriche calcolate, nonché le metriche o le dimensioni basate su un [set di dati](/help/data-views/summary-data.md) di riepilogo, non sono supportate.

   Puoi selezionare più componenti nel barra sinistro tenendo premuto Maiusc o tenendo premuto Comando (su Mac) o Ctrl (su Windows).

   La visualizzazione viene aggiornata in base alla metrica primaria, come segue (a seconda del tipo di componente e dell&#39;area dell&#39;area dell&#39;area in cui lo posizionate):

   | Tipo di componente | Posizionamento del componente | La visualizzazione viene aggiornata dopo l’aggiunta del nodo |
   |---------|----------|----------|
   | Metrica | Area vuota dell’area di lavoro | Il nodo visualizza il punto in cui il componente è stato rilasciato, senza connessione con alcun nodo esistente. |
   | Metrica | Un nodo esistente | Il componente viene combinato automaticamente con il nodo esistente. (Vedi [Combina nodi](#combine-nodes) per ulteriori informazioni.)</p> |
   | Metrica | Una freccia tra 2 nodi esistenti | Il nodo viene visualizzato tra i due nodi esistenti in cui il componente è stato rilasciato ed è connesso a entrambi i nodi esistenti. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p> |
   | Dimensione | Area vuota dell’area di lavoro | Vengono creati 3 nodi per i primi 3 elementi dimensionali in cui il componente è stato rilasciato, senza alcuna connessione con i nodi esistenti. (**Nota:** se vengono visualizzati solo 1 o 2 nodi, significa che i dati sono disponibili solo per 1 o 2 degli elementi dimensionali. Se non vengono visualizzati nodi, significa che i dati non sono disponibili per nessuno degli elementi dimensionali. In questo caso, prova ad aggiungerlo a un punto diverso del percorso, a regolare l’intervallo di date della visualizzazione o a scegliere una dimensione diversa.<p>Quando rilasci la dimensione nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerla come nodo singolo con 3 elementi dimensionali.</p><p></p> |
   | Dimensione | Un nodo esistente | Al nodo viene applicato automaticamente un raggruppamento con i primi 5 elementi dimensionali visualizzati.<!--what happens if you hold Shift?--><p>Per visualizzare il raggruppamento in una nuova visualizzazione di tabella a forma libera, seleziona il collegamento [!UICONTROL **Apri in una tabella a forma libera**] sul nodo.</p> |
   | Dimensione | Una freccia che connette 2 nodi esistenti | Vengono creati 3 nodi per i primi 3 elementi dimensionali che seguono il primo evento dopo il primo nodo (di persone/sessioni che alla fine raggiungono il secondo nodo). I nodi vengono visualizzati tra i due nodi esistenti in cui il componente è stato rilasciato e ogni nodo è connesso a entrambi i nodi esistenti. (**Nota:** se vengono visualizzati solo 1 o 2 nodi, significa che i dati sono disponibili solo per 1 o 2 degli elementi dimensionali. Se non vengono visualizzati nodi, significa che i dati non sono disponibili per nessuno degli elementi dimensionali. In questo caso, prova ad aggiungerlo a un punto diverso del percorso, a regolare l’intervallo di date della visualizzazione o a scegliere una dimensione diversa.<p>Quando rilasci la dimensione nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerla come nodo singolo con 3 elementi dimensionali. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p> |
   | Elemento dimensione | Area vuota dell’area di lavoro | Il nodo visualizza il punto in cui il componente è stato rilasciato, senza connessione con alcun nodo esistente. |
   | Elemento dimensione | Un nodo esistente | Il componente viene combinato automaticamente con il nodo esistente. |
   | Elemento dimensione | Una freccia che connette 2 nodi esistenti | Il nodo viene visualizzato tra i due nodi esistenti in cui il componente è stato rilasciato ed è connesso a entrambi i nodi esistenti. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p> |
   | Filtro | Area vuota dell’area di lavoro | Il nodo mostra dove il componente è stato rilasciato senza essere connesso con altri nodi.<p>Il numero e la percentuale visualizzati sul nodo includono il totale della metrica principale, filtrato in base al filtro selezionato.</p> <p>Ad esempio, se Persone è selezionata come metrica principale per il percorso, l’aggiunta di un filtro Oggi a un’area vuota dell’area di lavoro mostra tutte le persone che hanno avuto un evento oggi.</p> |
   | Filtro | Un nodo esistente | Applica il filtro al nodo esistente. |
   | Filtro | Una freccia che connette 2 nodi | Il nodo viene visualizzato tra i due nodi esistenti in cui il componente è stato rilasciato ed è connesso a entrambi i nodi esistenti. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p><p>Applica il filtro al punto del percorso in cui è stato rilasciato il componente.</p> |
   | Intervallo date | Area vuota dell&#39;area di lavoro | Il nodo mostra dove è stato rilasciato il componente, non connesso con altri nodi.<p>Il numero e la percentuale visualizzati sul nodo includono il totale della metrica primaria, filtrato in base all&#39;intervallo di date selezionato.</p> <p>Ad esempio, se si seleziona Persone come metrica principale per il percorso, l&#39;aggiunta di un intervallo di date di Questo mese a un&#39;area vuota dell&#39;area di lavoro mostra tutte le persone che hanno avuto un evento durante il mese corrente.</p> |
   | Intervallo date | Un nodo esistente | Applica l&#39;intervallo di date al nodo esistente. |
   | Intervallo date | Una freccia che connette 2 nodi | Il nodo viene visualizzato tra i due nodi esistenti in cui il componente è stato rilasciato ed è connesso a entrambi i nodi esistenti. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p><p>Applica l’intervallo di date al punto del percorso in cui è stato rilasciato il componente.</p> |
   | Più componenti | Area vuota dell&#39;area di lavoro | **Se nessuno dei componenti sono dimensioni:**<p>Ogni componente viene visualizzato come un nodo separato in cui i componenti sono stati eliminati, senza alcuna connessione con i nodi esistenti.</p><p>Quando rilasci i componenti nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerli come un nodo combinato. </p><p>**Se uno dei componenti che stai aggiungendo sono dimensioni:**</p><p>Ogni componente viene visualizzato come un nodo separato in cui i componenti sono stati eliminati, senza alcuna connessione con i nodi esistenti.</p><p>È possibile aggiungere una sola dimensione alla volta. Quando si aggiunge la dimensione, vengono creati 3 nodi per i primi 3 elementi dimensionali in cui il componente è stato rilasciato.</p><p>Quando rilasci i componenti nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerli come un nodo combinato. I primi 3 elementi dimensionali sono combinati con ciascun nodo. (Vedi [Combina nodi](#combine-nodes) per ulteriori informazioni.)</p> |
   | Più componenti | Un nodo esistente | Tutti i componenti sono combinati con il nodo esistente.<p>Se uno dei componenti che stai aggiungendo sono dimensioni, i primi 3 elementi dimensionali vengono combinati con il nodo.</p> <p>È possibile aggiungere una sola dimensione alla volta.</p> |
   | Più componenti | Una freccia che connette 2 nodi esistenti | **Se nessuno dei componenti sono dimensioni:**<p>Ogni componente viene visualizzato come un nodo separato in cui i componenti sono stati eliminati e ogni nodo è connesso a entrambi i nodi esistenti. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p><p>Quando rilasci i componenti nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerli come un nodo combinato. I componenti devono essere dello stesso tipo per essere combinati in un singolo nodo. Per ulteriori informazioni, vedere [Combinare nodi](#combine-nodes).</p><p>**Se uno dei componenti che stai aggiungendo sono dimensioni:**</p><p>Ogni componente viene visualizzato come un nodo separato in cui i componenti sono stati eliminati e ogni nodo è connesso a entrambi i nodi esistenti.</p><p>È possibile aggiungere una sola dimensione alla volta. Quando si aggiunge la dimensione, vengono creati 3 nodi per i primi 3 elementi della dimensione che seguono il primo evento dopo il primo nodo (di persone o sessioni che alla fine raggiungono il secondo nodo). Ogni nodo è connesso a entrambi i nodi esistenti. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p><p>Quando rilasci i componenti nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerli come un nodo combinato. I primi 3 elementi dimensionali sono combinati con ciascun nodo e ogni nodo è connesso a entrambi i nodi esistenti. (Vedi [Combina nodi](#combine-nodes) per ulteriori informazioni.)</p> |

   I nodi vengono visualizzati come una casella rettangolare con le seguenti informazioni:

   * Nome componente

   * Il tipo di componente (ad esempio metrica o dimensione)

   * Statistiche delle metriche primarie (totale e percentuale)

   * Statistiche metriche secondarie (totale e percentuale)

   Un nodo pulsato o luminoso indica che i dati sono in fase di caricamento per quel nodo.

1. Ripeti questa procedura per continuare ad aggiungere nodi per creare il percorso.

1. Continuate a personalizzare il percorso come descritto nelle sezioni seguenti. Puoi connettere nodi, rinominare nodi, applicare suddivisioni, creare tipi di pubblico, aggiungere vincoli di tempo e altro ancora.

### Mostra i nodi principali in base ai nodi esistenti

Puoi visualizzare automaticamente i nodi principali in base ai nodi già presenti nell’area di lavoro. Puoi aggiungere i nodi principali all’area di lavoro del Percorso o visualizzarli in una tabella a forma libera.

L’area di lavoro di percorso utilizza la metrica principale per determinare quali nodi visualizzare.

Questa opzione è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

* La freccia tra i nodi

#### Mostra nodi principali dopo un nodo esistente

Puoi selezionare un nodo e visualizzare gli elementi dimensionali principali che seguono nel percorso. È possibile aggiungere i primi 3 elementi dimensionali all’area di lavoro del Percorso come nodi separati, oppure visualizzare tutti gli elementi dimensionali principali in una tabella a forma libera.

1. Fai clic con il pulsante destro del mouse sul nodo in cui desideri visualizzare gli elementi dimensionali principali che seguono nel percorso.

   Il nodo non può avere nodi esistenti che ne escano nel percorso.

1. Seleziona [!UICONTROL **Mostra nodi principali dopo questo nodo**].

1. Seleziona il punto in cui desideri visualizzare gli elementi dimensionali:

   * [!UICONTROL **Nell&#39;area di lavoro del Percorso**]: aggiunge i primi 3 nodi all&#39;area di lavoro che segue questo nodo nel percorso. Ogni nodo è connesso al nodo selezionato come ramo separato nell’area di lavoro.

   * [!UICONTROL **In una tabella a forma libera**]: crea una visualizzazione di tabella a forma libera che mostra tutti gli elementi dimensionali principali che seguono questo nodo nel percorso.

1. Selezionate la quota desiderata dall&#39;elenco delle quote.

   A seconda di quanto scelto nel passaggio precedente, i primi 3 elementi dimensionali vengono aggiunti all’area di lavoro come 3 nodi separati, oppure tutti gli elementi dimensionali principali vengono visualizzati in una tabella a forma libera.

#### Mostra nodi principali prima di un nodo esistente

Puoi selezionare un nodo e visualizzare gli elementi dimensionali principali che lo precedono nel percorso. È possibile aggiungere i primi 3 elementi dimensionali all’area di lavoro del Percorso come nodi separati, oppure visualizzare tutti gli elementi dimensionali principali in una tabella a forma libera.

1. Fai clic con il pulsante destro del mouse sul nodo in cui desideri visualizzare gli elementi dimensionali principali che lo precedono nel percorso.

   Questo nodo non può contenere nodi esistenti che entrano in esso nel percorso.

1. Seleziona [!UICONTROL **Mostra nodi principali prima di questo nodo**].

1. Seleziona il punto in cui desideri visualizzare gli elementi dimensionali:

   * [!UICONTROL **Nell&#39;area di lavoro del Percorso**]: aggiunge i primi 3 nodi all&#39;area di lavoro che precede questo nodo nel percorso. Ogni nodo è connesso al nodo selezionato come ramo separato nell’area di lavoro.

   * [!UICONTROL **In una tabella a forma libera**]: crea una visualizzazione di tabella a forma libera che mostra tutti gli elementi dimensionali principali che precedono questo nodo nel percorso.

1. Selezionate la quota desiderata dall&#39;elenco delle quote.

   A seconda di quanto scelto nel passaggio precedente, i primi 3 elementi dimensionali vengono aggiunti all’area di lavoro come 3 nodi separati, oppure tutti gli elementi dimensionali principali vengono visualizzati in una tabella a forma libera.

#### Mostra nodi principali tra nodi esistenti

Puoi selezionare una freccia e visualizzare gli elementi dimensionali principali compresi tra 2 nodi esistenti nel percorso. È possibile aggiungere i primi 3 elementi dimensionali all’area di lavoro del Percorso come nodi separati, oppure visualizzare tutti gli elementi dimensionali principali in una tabella a forma libera.

1. Fai clic con il pulsante destro del mouse sulla freccia tra i due nodi in cui desideri visualizzare gli elementi dimensionali principali.

1. Selezionare [!UICONTROL **Mostra nodi principali tra questi nodi**].

1. Seleziona il punto in cui desideri visualizzare gli elementi dimensionali:

   * [!UICONTROL **Nell&#39;area di lavoro di Percorso**]: aggiunge i primi 3 nodi all&#39;area di lavoro che si trovano tra i 2 nodi esistenti. Ogni nodo è connesso ai nodi circostanti come ramo separato nell’area di lavoro.

   * [!UICONTROL **In una tabella a forma libera**]: crea una visualizzazione di tabella a forma libera che mostra tutti gli elementi dimensionali principali compresi tra i 2 nodi esistenti.

1. Selezionate la quota desiderata dall&#39;elenco delle quote.

   A seconda di quanto scelto nel passaggio precedente, i primi 3 elementi dimensionali vengono aggiunti all’area di lavoro come 3 nodi separati, oppure tutti gli elementi dimensionali principali vengono visualizzati in una tabella a forma libera.

### Nodi duplicati

L’opzione per duplicare è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

* Più nodi

Per duplicare i nodi:

1. Selezionare uno o più nodi da duplicare.

   Per selezionare più nodi, tenere premuto Comando (su Mac) o Ctrl (su Windows).

1. Fare clic con il pulsante destro del mouse su uno dei nodi selezionati, quindi selezionare [!UICONTROL **Duplica**].

## Progettare il percorso

L’ordine dei nodi e le connessioni tra di essi influiscono sui dati dell’area di lavoro del Percorso. I percorsi devono riflettere in modo visivo e accurato la sequenza di eventi su cui desideri creare un rapporto.

Dopo aver aggiunto i nodi all’area di lavoro, puoi ridisporli, combinarli, collegarli e aggiungere vincoli di tempo tra di essi.

### Ridisponi nodi

I percorsi nell’area di lavoro del Percorso sono costituiti da un grafico flessibile di nodi e frecce che rappresentano qualsiasi combinazione di eventi, elementi dimensionali e filtri.

Puoi trascinare i nodi nell’area di lavoro per ridisporre gli eventi e le condizioni del percorso.

Quando ridisponi l’ordine dei nodi nel percorso, i dati vengono aggiornati di conseguenza.

### Combinare nodi

Un nodo combinato nell’area di lavoro del Percorso è un singolo punto nel percorso di utenti (nodo) che contiene 2 o più componenti uniti tra loro tramite la logica.

#### Creare nodi combinati

Per combinare i nodi nell&#39;area di lavoro del Percorso, è possibile eseguire una delle operazioni seguenti:

* Dalla barra a sinistra, trascina un singolo componente su un nodo dell’area di lavoro.

* Dalla barra a sinistra, trascina più componenti simultaneamente su un nodo dell’area di lavoro.

* Dalla barra a sinistra, trascina più componenti simultaneamente su un’area vuota dell’area di lavoro tenendo premuto il tasto Maiusc.

<!-- * On the canvas, select the nodes that you want to combine, right-click one of the selected nodes, then select **Combine**. Is there a limit on how many you can combine? -->

#### Logica durante la combinazione dei nodi

La logica applicata ai nodi quando vengono combinati varia a seconda dei tipi di componenti che si stanno combinando, come segue:

>[!TIP]
>
>Puoi visualizzare la logica di un nodo combinato facendo clic con il pulsante destro del mouse sul nodo e selezionando [!UICONTROL **Crea filtro dal nodo**]. La logica è illustrata nella sezione [!UICONTROL **Definizione**].


| Tipi di componenti da combinare | Logica (operatore) utilizzata |
|---------|----------|
| Metrica + Metrica | Unito con OR |
| Elemento Dimension + Elemento Dimension (dalla stessa dimensione padre) | Unito con OR |
| Elemento Dimension + Elemento Dimension (da dimensioni padre diverse) | Unito con AND |
| Filtro + Filtro | Unito con AND |
| Dimension + metrica, intervallo di date o filtro | Unito con AND |
| Intervallo di date + Metrica, Filtro o Dimension | Unito con AND |
| Filtro + metrica, intervallo di date o Dimension | Unito con AND |

### Connetti nodi

È possibile connettere nodi già presenti nell&#39;area di lavoro oppure un nodo quando lo si aggiunge all&#39;area di lavoro.

I nodi vengono collegati per definire la sequenza di eventi del percorso.

#### Frecce tra nodi

I nodi sono collegati da una freccia. Sia la direzione della freccia che la larghezza hanno un significato:

* **Direzione**: indica la sequenza di eventi del percorso

* **Larghezza**: indica il volume percentuale da un nodo all&#39;altro

  ![Direzione e larghezza della freccia](assets/journey-canvas-arrow-width.png)

#### Logica durante la connessione dei nodi

Quando si connettono nodi nell&#39;area di lavoro del Percorso, questi vengono connessi utilizzando l&#39;operatore THEN. Questa operazione è nota anche come [filtro sequenziale](/help/components/filters/seg-sequential-build.md).

I nodi sono connessi come un &quot;percorso finale&quot;, il che significa che i visitatori vengono conteggiati purché alla fine si spostino da un nodo all’altro, indipendentemente da eventuali eventi che si verificano tra i 2 nodi. Il tempo assegnato agli utenti per spostarsi lungo il percorso è determinato dall’impostazione del contenitore. <!-- It can also be controlled by [adding a time constraint](#add-a-time-constraint-between-nodes). -->

È possibile visualizzare la logica dei nodi connessi facendo clic con il pulsante destro del mouse sul nodo e selezionando [!UICONTROL **Crea filtro dal nodo**]. La logica è illustrata nella sezione [!UICONTROL **Definizione**].

#### Connetti nodi esistenti

I percorsi non possono essere circolari e tornare ai nodi connessi in precedenza.

Per connettere i nodi nell&#39;area di lavoro del Percorso:

1. In una visualizzazione area di lavoro Percorso, passa il cursore sul nodo che si trova per primo nella sequenza di percorso che desideri connettere a un altro nodo.

   Su ogni lato del nodo selezionato vengono visualizzati 4 punti blu.

1. Trascinate uno dei 4 punti blu su uno dei 4 lati del nodo a cui desiderate connettervi.

   Viene visualizzata una freccia che collega i 2 nodi. Per ulteriori informazioni, vedere [Frecce tra nodi](#arrows-between-nodes).

#### Connetti nodi durante l’aggiunta di un nodo

Quando aggiungi un nodo all’area di lavoro, puoi posizionarlo tra due nodi connessi. Il nodo viene aggiunto al flusso del percorso tra i due nodi esistenti.

Per ulteriori informazioni, vedere [Aggiungere nodi](#add-nodes).

<!--

### Add a time constraint between nodes

>[!AVAILABILITY]
>
>This feature is not yet available.

You can set a time constraint between nodes. When a time constraint is in place, people are considered to have fallen out of the journey if they follow the defined journey but take longer than the allotted time period to move between the nodes.

The option to add a time constraint is available for the following objects on the canvas:

* The arrow between nodes

To add a time constraint:

1. In a Journey canvas visualization, right-click the arrow between 2 nodes, then select [!UICONTROL **Add time constraint**].

from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon). 
1. Choose from the following options: 

-->

## Gestire nodi o frecce

<!--

### Change the color of a node or arrow

>[!AVAILABILITY]
>
>This feature is not yet available.

You can visually customize a journey by changing the color of any node or arrow on the canvas. For example, you could adjust colors to indicate a desirable or undesirable event.

The option to change the color is available for the following objects on the canvas:

* Individual nodes

* The arrow between nodes

To change the color of a node or arrow:

1. In a Journey canvas visualization, right-click the node or arrow whose color you want to change.

1. Select [!UICONTROL **Change color**]. 

1. Select the desired color. 

   The following colors are available: 

-->

### Rinominare un nodo

Quando trascini un componente in una visualizzazione area di lavoro Percorsi, viene creato un nodo con lo stesso nome del nome del componente. Puoi rinominare il nodo in modo che corrisponda meglio al passaggio del percorso rappresentato dal nodo.

L’opzione per rinominare è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

Per rinominare un nodo:

1. In una visualizzazione dell’area di lavoro del Percorso, fai clic con il pulsante destro del mouse sul nodo che desideri rinominare.

1. Selezionare [!UICONTROL **Rinomina**].

1. Specificare un nuovo nome, quindi premere Invio.<!--is that right?-->

### Aggiungere o aggiornare un&#39;etichetta su una freccia

Le frecce visualizzate tra i nodi nell’area di lavoro del Percorso possono essere configurate per mostrare etichette e valori personalizzati.

Le etichette sono nomi personalizzati visualizzati sulle frecce. Su una determinata freccia viene visualizzata una sola etichetta.

Per ulteriori informazioni sulle etichette e i valori visualizzati sulle frecce, vedere &quot;Impostazioni freccia&quot; in [Configurare le impostazioni di visualizzazione](#configure-visualization-settings).

L’opzione per aggiungere o aggiornare un’etichetta è disponibile per i seguenti oggetti nell’area di lavoro:

* La freccia tra i nodi

Per aggiungere un&#39;etichetta a una freccia:

1. In una visualizzazione dell’area di lavoro del Percorso, fai clic con il pulsante destro del mouse sulla freccia in cui desideri aggiungere un’etichetta.

1. Seleziona **[!UICONTROL Add label]**.

1. Specificare un nome per l&#39;etichetta, quindi premere Invio.

   Se le impostazioni della freccia sono attualmente configurate per nascondere le etichette, viene visualizzato un messaggio che richiede di mostrare le etichette.

Per aggiornare un&#39;etichetta esistente su una freccia:

1. In una visualizzazione dell’area di lavoro del Percorso, fai clic con il pulsante destro del mouse sulla freccia in cui desideri aggiungere un’etichetta.

1. Seleziona **[!UICONTROL Update label]**.

1. Specificare un nome per l&#39;etichetta, quindi premere Invio.

   Se le impostazioni della freccia sono attualmente configurate per nascondere le etichette, viene visualizzato un messaggio che richiede di mostrare le etichette.

### Applicare un raggruppamento

L’opzione per applicare un raggruppamento ai dati è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

* Più nodi

* La freccia tra i nodi

* Più frecce tra nodi

Quando applichi una suddivisione, tieni presente quanto segue:

* I raggruppamenti vengono applicati alla metrica principale. La metrica secondaria non è interessata.

* L’applicazione di un raggruppamento non modifica il percorso. Al contrario, mostra semplicemente un raggruppamento dei dati per il nodo in cui viene applicato.

* Se un nodo presenta già un raggruppamento, l’applicazione di un nuovo raggruppamento sostituisce quello esistente.

* I dati di raggruppamento vengono aggiornati se vengono apportate modifiche in un punto precedente del percorso.

#### Applicare un raggruppamento a uno o più nodi o frecce

1. In una visualizzazione area di lavoro Percorso, seleziona uno o più nodi in cui desideri applicare un raggruppamento, quindi fai clic con il pulsante destro del mouse su uno dei nodi selezionati.

   Oppure

   In una visualizzazione area di lavoro Percorso, seleziona una o più frecce tra 2 nodi in cui desideri applicare il raggruppamento, quindi fai clic con il pulsante destro del mouse su una delle frecce selezionate.

   Per selezionare più nodi o frecce, tenere premuto Comando (su Mac) o Ctrl (su Windows).

1. Seleziona [!UICONTROL **Raggruppamento**].

1. Scegli dove visualizzare il raggruppamento:

   * [!UICONTROL **Nell&#39;area di lavoro del Percorso**]

   * [!UICONTROL **Tabella a forma libera**]

1. Seleziona la dimensione da utilizzare per il raggruppamento.

   Se hai scelto di visualizzare il raggruppamento nell’area di lavoro del Percorso, sul nodo vengono visualizzati i primi 5 elementi dimensionali. Sul nodo è disponibile un’opzione per aprire il raggruppamento in una tabella a forma libera.

   Se hai scelto di visualizzare il raggruppamento in una tabella a forma libera, gli elementi dimensionali principali vengono visualizzati in una nuova tabella a forma libera immediatamente sopra la visualizzazione dell’area di lavoro del Percorso.

#### Applicare un raggruppamento a un singolo nodo

Puoi trascinare una dimensione dalla barra a sinistra sul nodo dell’area di lavoro in cui desideri applicare il raggruppamento.

Per ulteriori informazioni, vedere [Aggiungere nodi](#add-nodes).

#### Rimuovere un raggruppamento

Per rimuovere un raggruppamento applicato:

1. Fai clic con il pulsante destro del mouse sul nodo a cui è applicato il raggruppamento.

1. Seleziona **[!UICONTROL Remove breakdown]**.

### Creazione di un pubblico

L’opzione per creare un pubblico è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

* Più nodi

* La freccia tra i nodi

* Più frecce tra nodi

Quando crei un pubblico da più nodi o frecce, questi vengono uniti con l’operatore OR.

Per creare un pubblico:

1. In una visualizzazione area di lavoro Percorso, seleziona uno o più nodi in cui vuoi creare un pubblico, quindi fai clic con il pulsante destro del mouse su uno dei nodi selezionati.

   Oppure

   In una visualizzazione area di lavoro Percorso, seleziona una o più frecce tra due nodi in cui desideri creare un pubblico, quindi fai clic con il pulsante destro del mouse su una delle frecce selezionate.

   Per selezionare più nodi o frecce, tenere premuto Comando (su Mac) o Ctrl (su Windows).

   >[!NOTE]
   >
   >I tipi di pubblico non possono includere metriche calcolate o metriche basate su un [set di dati di riepilogo](/help/data-views/summary-data.md). Se tenti di creare un pubblico da una qualsiasi area dell’area di lavoro del Percorso che contiene una metrica calcolata o una metrica basata su un set di dati di riepilogo, la metrica calcolata non verrà inclusa nella definizione del pubblico.

1. Seleziona [!UICONTROL **Crea pubblico dal nodo**] o [!UICONTROL **Crea pubblico dalla freccia**].

1. Continuare a creare e pubblicare il pubblico come descritto in [Creare e pubblicare tipi di pubblico](/help/components/audiences/publish.md).

### Visualizza dati tendenza

È possibile visualizzare i dati delle tendenze in un grafico a linee per gli oggetti nell&#39;area di lavoro del Percorso. <!--, with some prebuilt anomaly detection data (this is the definition in Fallout) -->

L’opzione di tendenza è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

* Più nodi

* Frecce tra i nodi

* Più frecce tra nodi

Per visualizzare i dati di tendenza:

1. In una visualizzazione area di lavoro Percorso, seleziona uno o più nodi per i quali vuoi visualizzare i dati sulle tendenze, quindi fai clic con il pulsante destro del mouse su uno dei nodi selezionati.

   Oppure

   In una visualizzazione area di lavoro Percorso, seleziona una o più frecce tra 2 nodi per i quali desideri visualizzare i dati delle tendenze, quindi fai clic con il pulsante destro del mouse su una delle frecce selezionate.

   Per selezionare più nodi o frecce, tenere premuto Comando (su Mac) o Ctrl (su Windows).

1. Seleziona [!UICONTROL **Tendenza**].

### Creare un filtro basato su un nodo o una freccia

Puoi creare un nuovo filtro basato su un nodo o una freccia all’interno di un percorso. Una volta creato il filtro, puoi utilizzarlo ovunque in Analysis Workspace.

I filtri creati dall&#39;area di lavoro del Percorso utilizzano [il filtro sequenziale](/help/components/filters/seg-sequential-build.md). Questo significa che il filtro utilizza l’operatore THEN per collegare la sequenza di eventi (il percorso) attraversati dalle persone, che porta al nodo o alla freccia selezionati. Tutti gli eventi che corrispondono al nodo o alla freccia selezionati sono inclusi nel filtro.

Se crei un filtro basato su un nodo che include più percorsi, tutti i percorsi vengono inclusi nel filtro. I percorsi separati vengono uniti con l&#39;operatore OR.

Per creare un filtro:

1. In una visualizzazione con area di lavoro Percorso, fai clic con il pulsante destro del mouse sul nodo o sulla freccia che desideri utilizzare per creare il filtro.

1. Selezionare [!UICONTROL **Crea filtro dal nodo**] o [!UICONTROL **Crea filtro dalla freccia**].

   Viene visualizzato il Generatore di filtri. Nella sezione [!UICONTROL **Definition**], la definizione del filtro viene creata in base al nodo o alla freccia selezionati e al relativo contesto all&#39;interno del percorso.

1. Specifica un titolo per il filtro e apporta eventuali altre modifiche. Per ulteriori informazioni sulla creazione di un filtro, vedere [Generatore di filtri](/help/components/filters/filter-builder.md).

1. Seleziona [!UICONTROL **Salva**] per salvare il filtro.

### Elimina nodi

È possibile eliminare uno o più nodi alla volta all&#39;interno di un percorso. Quando si elimina un nodo connesso tra 2 nodi all&#39;interno del percorso, i 2 nodi rimanenti diventano connessi direttamente.

Per eliminare i nodi nell&#39;area di lavoro del Percorso:

1. In una visualizzazione area di lavoro Percorso, seleziona uno o più nodi da eliminare, quindi fai clic con il pulsante destro del mouse su uno dei nodi selezionati.

1. Seleziona [!UICONTROL **Elimina**].

### Elimina frecce tra nodi

È possibile eliminare una o più frecce alla volta all&#39;interno di un percorso. Quando si elimina una freccia tra due nodi, i nodi non sono più connessi. Se la freccia faceva parte di un percorso più lungo, il percorso viene disconnesso.

Per eliminare le frecce tra i nodi nell&#39;area di lavoro del Percorso:

1. In una visualizzazione area di lavoro Percorso, seleziona una o più frecce tra due nodi da eliminare, quindi fai clic con il pulsante destro del mouse su una delle frecce selezionate.

1. Seleziona [!UICONTROL **Elimina**].

## Apri un percorso da Journey Optimizer

Quando visualizzi un percorso in Journey Optimizer, puoi scegliere di visualizzarlo nell’area di lavoro del Percorso.

1. In Journey Optimizer, apri il percorso che desideri analizzare nell’area di lavoro del Percorso.

1. Seleziona [!UICONTROL **Analizza in CJA**]. <!-- ?? -->
