---
description: Configurare una visualizzazione area di lavoro del percorso
title: Area di lavoro percorso
feature: Visualizations
role: User
hide: true
hidefromtoc: true
exl-id: 53984934-6fba-4f15-aeeb-d91039260553
source-git-commit: 90180e1231ab8b50f1f6b8552e00d1c251d10a2f
workflow-type: tm+mt
source-wordcount: '5408'
ht-degree: 1%

---

# Configurare una visualizzazione area di lavoro del percorso

{{release-limited-testing}}

La visualizzazione area di lavoro Percorso consente di analizzare e ottenere informazioni approfondite sui percorsi forniti a utenti e clienti.

## Panoramica dell’area di lavoro del percorso

Per ulteriori informazioni sull&#39;area di lavoro di Percorso, vedere [Panoramica sull&#39;area di lavoro di Percorso](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md), tra cui:

* Funzioni chiave

* Potenziali informazioni

* Differenze tra area di lavoro del Percorso e Abbandono

* Dettagli sull’analisi dei percorsi Journey Optimizer

* E altro ancora

## Inizia a creare una visualizzazione area di lavoro Percorso

1. Aggiungi un pannello vuoto al progetto, seleziona l&#39;icona [!UICONTROL **Visualizzazioni**] nella barra a sinistra, quindi trascina la visualizzazione [!UICONTROL **Area di lavoro Percorsi**] nel pannello.

   Oppure

   Aggiungi una visualizzazione area di lavoro Percorso in uno dei modi descritti nella sezione [Aggiungere visualizzazioni a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) in [Panoramica delle visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Specifica le seguenti informazioni di base:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Metrica primaria**] | La metrica principale influisce sui seguenti aspetti della visualizzazione dell’area di lavoro del Percorso:  <ul><li>Definisce il modo in cui le persone si spostano nel percorso.</li><li>Numero totale visualizzato su ciascun nodo.<p>Ad esempio, se Persone è la metrica principale, ogni nodo mostra il numero di persone che hanno raggiunto quel nodo nel percorso.</p></li><li>La percentuale visualizzata su ciascun nodo. Una volta creata la visualizzazione, puoi scegliere di mostrare la percentuale del totale o del nodo iniziale.</li><p>Ad esempio, se Persone è la metrica principale, ogni nodo mostra la percentuale di persone che hanno raggiunto quel nodo nel percorso (la percentuale del totale o del nodo iniziale).</p></li><li>Quando una dimensione viene aggiunta alla visualizzazione, vengono aggiunti i primi 3 nodi della visualizzazione, in base alla metrica principale.</li></ul> |
   | [!UICONTROL **Metrica secondaria**] | La metrica secondaria è facoltativa. Quando ne è selezionato uno, le seguenti informazioni vengono visualizzate su ciascun nodo sotto la metrica principale: <ul><li>Numero totale<p>Ad esempio, se Sessioni è la metrica secondaria, ogni nodo mostra il numero di sessioni che hanno raggiunto quel nodo nel percorso.</p></li><li>La percentuale (dopo aver creato la visualizzazione, puoi scegliere di mostrare la percentuale del totale o del nodo iniziale).</li><p>Ad esempio, se Sessioni è la metrica secondaria, ogni nodo mostra la percentuale di sessioni che hanno raggiunto tale nodo nel percorso (la percentuale del totale o del nodo iniziale).</p></li></ul> |
   | [!UICONTROL **percorso Journey Optimizer**]<!-- name? --> | Seleziona il percorso Journey Optimizer da utilizzare come base per l’analisi nell’area di lavoro del Percorso. In alternativa, puoi lasciare vuota questa opzione se desideri un’area di lavoro vuota da cui generare l’analisi in Analysis Workspace.</p> <p>Quando si analizza un percorso Journey Optimizer nell&#39;area di lavoro del Percorso, il percorso viene visualizzato con l&#39;ordine, la sequenza e la struttura di Journey Optimizer. Per ulteriori informazioni, vedere [Analizzare i percorsi Journey Optimizer](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) in [Panoramica area di lavoro Percorsi](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Nota**: questa opzione viene visualizzata solo quando i dati di Journey Optimizer vengono rilevati nella stessa visualizzazione dati selezionata nel pannello Analysis Workspace in cui si sta aggiungendo la visualizzazione. Per informazioni sulla modifica della visualizzazione dati in un pannello di Analysis Workspace, vedi [Panoramica di Analysis Workspace](/help/analysis-workspace/home.md).</p> |

1. (Facoltativo) Seleziona [!UICONTROL **Mostra impostazioni avanzate**], quindi specifica le seguenti informazioni:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **contenitore area di lavoro Percorsi**] | Scegli il contenitore su cui concentrarti in tutto il percorso. Il contenitore scelto determina le statistiche visualizzate nella visualizzazione. Se i nomi dei contenitori sono diversi da quelli predefiniti mostrati di seguito, significa che sono stati personalizzati nella visualizzazione dati.<ul><li>**Sessioni:** limita le statistiche della visualizzazione in modo che rientrino in una singola sessione definita per una determinata persona. Ciò significa che i numeri e le percentuali visualizzati su ciascun nodo (che sono basati sulle metriche primaria e secondaria) devono verificarsi all’interno di una singola sessione per ogni persona.</li><li>**Persone:** consente alle statistiche della visualizzazione di coprire più sessioni per una determinata persona. Ciò significa che i numeri e le percentuali visualizzati su ciascun nodo (che sono basati sulle metriche primaria e secondaria) possono verificarsi in qualsiasi numero di sessioni, purché le sessioni appartengano alla stessa persona. Questa è l&#39;impostazione predefinita.</li></ul> |

1. Seleziona [!UICONTROL **Build**].

   Se avete selezionato un percorso Journey Optimizer Journey Optimizer, il percorso viene visualizzato con lo stesso ordine, la stessa sequenza e la stessa struttura di Journey Optimizer.

   <!-- add screen shot -->

   Se non disponi di Journey Optimizer o se non hai selezionato un percorso Journey Optimizer, viene visualizzata un’area di lavoro vuota in cui puoi iniziare a popolare il percorso.

   <!-- add screen shot -->

1. Sia che si crei una nuova analisi da un&#39;area di lavoro vuota o che si analizzi un percorso Journey Optimizer, è possibile configurare il percorso come descritto in [Configurare le impostazioni di visualizzazione](#configure-visualization-settings).


## Configurare le impostazioni di visualizzazione

Nell’intestazione dell’area di lavoro del Percorso sono disponibili varie opzioni di configurazione.

Per configurare le impostazioni per la visualizzazione Area di lavoro Percorso:

1. In Analysis Workspace, apri una visualizzazione dell&#39;area di lavoro del Percorso esistente oppure [creane una nuova](#begin-building-a-journey-canvas-visualization).

   Le opzioni che consentono di configurare la visualizzazione area di lavoro Percorso sono disponibili nell’intestazione:

   ![Opzioni intestazione area di lavoro Percorso](assets/journey-canvas-header.png)

1. Configura una delle seguenti impostazioni visualizzate nella parte superiore della visualizzazione:

   | Impostazione | Funzione |
   |---------|----------|
   | [!UICONTROL **Tipo di nodo**] | Consente di configurare quali tipi di nodo vengono visualizzati nella visualizzazione.<p>Per nascondere un tipo di nodo dalla visualizzazione, seleziona il (x) accanto al tipo di nodo oppure deselezionalo dal menu a discesa. Per visualizzare un tipo di nodo nascosto, selezionalo dal menu a discesa. I nodi non vengono eliminati dal percorso quando vengono nascosti. Per informazioni su come eliminare un nodo, vedere [Eliminare i nodi](#delete-nodes).)</p><p>Questo campo può contenere tipi di nodo di Journey Optimizer ([!UICONTROL **Leggi segmento**], [!UICONTROL **Fine**] e così via) e tipi di nodo componente ([!UICONTROL **Dimension**], [!UICONTROL **Metrica**], [!UICONTROL **Filtro**] e [!UICONTROL **Intervallo date**]), come segue: </p><ul><li>**Vengono visualizzati solo i tipi di nodo di Journey Optimizer** se il percorso è un percorso di Journey Optimizer che non è stato modificato nell&#39;area di lavoro del Percorso con una delle seguenti modifiche:<ul><li>Nodi aggiunti o rimossi</li><li>Frecce aggiunte o rimosse</li><li>Sono stati modificati i componenti su un nodo</li></ul></li><li>**Vengono visualizzati sia i tipi di nodo Journey Optimizer che i tipi di nodo componente** se il percorso è un percorso Journey Optimizer che è stato modificato nell&#39;area di lavoro del Percorso con una delle seguenti modifiche:<ul><li>Nodi aggiunti o rimossi</li><li>Frecce aggiunte o rimosse</li><li>Sono stati modificati i componenti su un nodo</li></ul></li><li>**Vengono visualizzati solo i tipi di nodo del componente** se il percorso non è un percorso Journey Optimizer.</li></ul></p> |
   | [!UICONTROL **Valore percentuale**] | Il valore percentuale visualizzato su ciascun nodo del percorso. Questa percentuale include solo le persone incluse nella visualizzazione dati all’interno dell’intervallo di date del pannello. <p>Scegli tra le seguenti opzioni:</p> <ul><li>[!UICONTROL **Percentuale del nodo iniziale**]: la percentuale di tutte le persone che soddisfano i criteri di un nodo iniziale nel percorso. <p>Un nodo _start_ è un nodo che non ha nodi connessi che lo precedono.</p><p>Un percorso può contenere più nodi iniziali. Tuttavia, viene utilizzato il [!UICONTROL **Percentuale del totale**] se il percorso contiene 2 o più nodi iniziali che conducono a un nodo comune. Se desideri utilizzare il [!UICONTROL **Percentuale del nodo iniziale**], aggiorna il percorso in modo che ogni nodo del percorso possa essere ricondotto a un singolo nodo iniziale.</p></li><li>[!UICONTROL **Percentuale del nodo precedente**]: la percentuale di tutte le persone del nodo precedente.</li><li>[!UICONTROL **Percentuale del totale**]: la percentuale di tutte le persone incluse nella visualizzazione dati all&#39;interno dell&#39;intervallo di date del pannello.</li></ul> |
   | [!UICONTROL **Impostazioni freccia**] | Le frecce visualizzate tra i nodi nell’area di lavoro del Percorso possono essere configurate per mostrare etichette e valori personalizzati. <p>_Le etichette_ sono nomi personalizzati visualizzati sulle frecce. Su una determinata freccia viene visualizzata una sola etichetta. Le etichette possono essere una qualsiasi delle seguenti e sono visualizzate in questo ordine di preferenza:</p><ol><li>Un nome personalizzato aggiunto dall&#39;area di lavoro del Percorso (come descritto in [Rinominare un nodo o una freccia](#rename-a-node-or-arrow))</li><li>Etichetta Journey Optimizer</li><li>Una condizione Journey Optimizer</li></ol><p>_I valori_ sono i numeri e le percentuali visualizzati sulle frecce e indicano le persone o le sessioni che si sono spostate da un nodo al nodo successivo nel percorso. (In altre parole, coloro che non sono usciti dal percorso in un determinato momento). </p><p>Le seguenti opzioni sono disponibili per i percorsi che non provengono da Journey Optimizer e per i percorsi Journey Optimizer che non sono stati modificati in modo significativo nell’area di lavoro del Percorso: (le modifiche più importanti includono l’aggiunta o la rimozione di nodi, l’aggiunta o la rimozione di frecce o la modifica dei componenti di un nodo).</p><ul><li>[!UICONTROL **Nessuna etichetta**]: nessuna etichetta visualizzata sulle frecce del percorso. </br> Questa opzione è disponibile solo se il percorso è stato modificato in </li><li>[!UICONTROL **Solo etichette**]: le etichette sono visualizzate sulle frecce del percorso.</li></ul><p>Per i percorsi Journey Optimizer che sono stati modificati in modo significativo nell&#39;area di lavoro del Percorso sono disponibili le seguenti opzioni: (le modifiche significative includono l&#39;aggiunta o la rimozione di nodi, l&#39;aggiunta o la rimozione di frecce o la modifica dei componenti di un nodo.)(**Nota**: queste opzioni vengono visualizzate solo quando i dati di Journey Optimizer vengono rilevati nella stessa visualizzazione dati selezionata nel pannello Analysis Workspace in cui si sta aggiungendo la visualizzazione. Per informazioni sulla modifica della visualizzazione dati in un pannello di Analysis Workspace, vedi [Panoramica di Analysis Workspace](/help/analysis-workspace/home.md).)</p><ul><li>[!UICONTROL **Nessuna etichetta o valore**]: nessuna etichetta o valore visualizzato sulle frecce del percorso.</li><li>[!UICONTROL **Solo etichette**]: solo le etichette sono visualizzate sulle frecce del percorso. I valori non vengono visualizzati.</li><li>[!UICONTROL **Solo valori**]: nelle frecce del percorso vengono visualizzati solo i valori. Le etichette non vengono visualizzate.</li><li>[!UICONTROL **Valori ed etichette**]: le etichette e i valori sono visualizzati su frecce nel percorso.</li></ul> |
   | [!UICONTROL **Mostra abbandono**] | Visualizza i dati di fallout per ciascun nodo. Mostra il numero e la percentuale di persone che hanno abbandonato il percorso dopo un determinato nodo. <p>Le persone che non rientrano nel percorso potrebbero aver eseguito altre azioni sul sito, ma non hanno mai soddisfatto i criteri definiti dal nodo successivo nel percorso.</p> |
   | **Controlli zoom** | Nell’angolo superiore destro dell’area di lavoro sono disponibili i seguenti controlli di zoom:<ul><li>**Zoom in** ![icona Zoom in](assets/zoom-in-icon.png): ingrandisce aree specifiche della visualizzazione.<p>È inoltre possibile utilizzare i controlli del mouse, ad esempio il pizzicamento su un trackpad.</p></li><li>**Zoom indietro** ![icona Zoom indietro](assets/zoom-out-icon.png): riduce la visualizzazione per consentire più spazio nell&#39;area di lavoro.<p>È inoltre possibile utilizzare i controlli del mouse, ad esempio il pizzicamento su un trackpad.</p></li><li>**Adatta schermo** ![icona Adatta schermo](assets/fill-screen-icon.png): regola le impostazioni correnti di zoom e scorrimento per riempire lo schermo con la visualizzazione completa.</li></ul><p>Per spostarsi nell&#39;area di lavoro dopo aver eseguito lo zoom avanti o indietro, fare clic con il mouse e trascinare nella posizione desiderata.</p> |

1. Continua con [Aggiungi nodi](#add-nodes).

## Aggiungi nodi

I nodi in una visualizzazione dell’area di lavoro di un Percorso rappresentano gli eventi o le azioni di un percorso di utenti.

Per creare i nodi, trascina i componenti Workspace dalla barra a sinistra all’area di lavoro, consentendo all’area di lavoro del Percorso di scegliere i nodi superiori successivi o precedenti in base ai nodi esistenti oppure duplicando i nodi esistenti.

### Trascina i componenti dalla barra a sinistra

1. In Analysis Workspace, apri una visualizzazione dell&#39;area di lavoro del Percorso esistente oppure [creane una nuova](#begin-building-a-journey-canvas-visualization).

1. Trascina metriche, dimensioni, elementi dimensionali, filtri o intervalli di date dalla barra a sinistra all’area di lavoro. Sono supportate le metriche basate su un [campo derivato](/help/data-views/derived-fields/derived-fields.md). Tuttavia, le metriche calcolate e quelle basate su un [set di dati di riepilogo](/help/data-views/summary-data.md) non sono supportate.

   Per selezionare più componenti nella barra a sinistra, tieni premuto Maiusc oppure tieni premuto Comando (su Mac) o Ctrl (su Windows).

   La visualizzazione viene aggiornata come segue, a seconda del tipo di componente e dell’area di lavoro in cui la inserisci:

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
   | Intervallo date | Area vuota dell’area di lavoro | Il nodo visualizza il punto in cui il componente è stato rilasciato, senza connessione con altri nodi.<p>Il numero e la percentuale visualizzati nel nodo includono il totale della metrica principale, filtrato per l’intervallo di date selezionato.</p> <p>Se ad esempio si seleziona Persone come metrica principale per il percorso, l’aggiunta di un intervallo di date Questo mese a un’area vuota dell’area di lavoro mostra tutte le persone che hanno avuto un evento nel corso del mese corrente.</p> |
   | Intervallo date | Un nodo esistente | Applica l’intervallo di date al nodo esistente. |
   | Intervallo date | Una freccia che connette 2 nodi | Il nodo viene visualizzato tra i due nodi esistenti in cui il componente è stato rilasciato ed è connesso a entrambi i nodi esistenti. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p><p>Applica l’intervallo di date al punto del percorso in cui è stato rilasciato il componente.</p> |
   | Più componenti | Area vuota dell&#39;area di lavoro | **Se nessuno dei componenti sono dimensioni:**<p>Ogni componente viene visualizzato come un nodo separato in cui i componenti sono stati eliminati, senza alcuna connessione con i nodi esistenti.</p><p>Quando rilasci i componenti nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerli come un nodo combinato. </p><p>**Se uno dei componenti che stai aggiungendo sono dimensioni:**</p><p>Ogni componente viene visualizzato come un nodo separato in cui i componenti sono stati eliminati, senza alcuna connessione con i nodi esistenti.</p><p>È possibile aggiungere una sola dimensione alla volta. Quando si aggiunge la dimensione, vengono creati 3 nodi per i primi 3 elementi dimensionali in cui il componente è stato rilasciato.</p><p>Quando rilasci i componenti nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerli come un nodo combinato. I primi 3 elementi dimensionali sono combinati con ciascun nodo. (Vedi [Combina nodi](#combine-nodes) per ulteriori informazioni.)</p> |
   | Più componenti | Un nodo esistente | Tutti i componenti sono combinati con il nodo esistente.<p>Se uno dei componenti che stai aggiungendo sono dimensioni, i primi 3 elementi dimensionali vengono combinati con il nodo.</p> <p>È possibile aggiungere una sola dimensione alla volta.</p> |
   | Più componenti | Una freccia che connette 2 nodi esistenti | **Se nessuno dei componenti sono dimensioni:**<p>Ogni componente viene visualizzato come un nodo separato in cui i componenti sono stati eliminati e ogni nodo è connesso a entrambi i nodi esistenti. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p><p>Quando rilasci i componenti nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerli come un nodo combinato. I componenti devono essere dello stesso tipo per essere combinati in un singolo nodo. (Vedi [Combina nodi](#combine-nodes) per ulteriori informazioni.)</p><p>**Se uno dei componenti che stai aggiungendo sono dimensioni:**</p><p>Ogni componente viene visualizzato come un nodo separato in cui i componenti sono stati eliminati e ogni nodo è connesso a entrambi i nodi esistenti.</p><p>È possibile aggiungere una sola dimensione alla volta. Quando si aggiunge la dimensione, vengono creati 3 nodi per i primi 3 elementi della dimensione che seguono il primo evento dopo il primo nodo (di persone/sessioni che alla fine raggiungono il secondo nodo). Ogni nodo è connesso a entrambi i nodi esistenti. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p><p>Quando rilasci i componenti nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerli come un nodo combinato. I primi 3 elementi dimensionali sono combinati con ciascun nodo e ogni nodo è connesso a entrambi i nodi esistenti. (Vedi [Combina nodi](#combine-nodes) per ulteriori informazioni.)</p> |

   I nodi vengono visualizzati come una casella rettangolare con le seguenti informazioni:

   * Nome componente

   * Il tipo di componente (ad esempio metrica o dimensione)

   * Statistiche delle metriche primarie (totale e percentuale)

   * Statistiche metriche secondarie (totale e percentuale)

1. Ripeti questa procedura per continuare ad aggiungere nodi per creare il percorso.

1. Continuate a personalizzare il percorso come descritto nelle sezioni seguenti. Puoi connettere nodi, rinominare nodi, applicare suddivisioni, creare tipi di pubblico, aggiungere vincoli di tempo e altro ancora.

### Mostra i nodi principali in base ai nodi esistenti

>[!AVAILABILITY]
>
>Questa funzione non è ancora disponibile.

Puoi visualizzare automaticamente i nodi principali in base ai nodi già presenti nell’area di lavoro. Puoi aggiungere i nodi principali all’area di lavoro del Percorso o visualizzarli in una tabella a forma libera.

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

>[!AVAILABILITY]
>
>Questa funzione non è ancora disponibile.

L’opzione per duplicare è disponibile per i seguenti oggetti nell’area di lavoro:

* Più nodi

Per duplicare i nodi:

1. Selezionare più nodi da duplicare.

1. Fare clic con il pulsante destro del mouse su uno dei nodi selezionati, quindi selezionare [!UICONTROL **Duplica**].

## Progettare il percorso

L’ordine dei nodi e le connessioni tra di essi influiscono sui dati dell’area di lavoro del Percorso. I percorsi devono riflettere in modo visivo e accurato la sequenza di eventi su cui desideri creare un rapporto.

Dopo aver aggiunto i nodi all’area di lavoro, puoi ridisporli, combinarli, collegarli e aggiungere vincoli di tempo tra di essi.

### Ridisponi nodi

I percorsi nell’area di lavoro del Percorso sono costituiti da un grafico flessibile di nodi e frecce che rappresentano qualsiasi combinazione di eventi, elementi dimensionali e filtri.

Puoi trascinare i nodi nell’area di lavoro per ridisporre gli eventi e le condizioni del percorso. È possibile selezionare più nodi tenendo premuto Comando (su Mac) o Ctrl (su Windows).

Quando ridisponi l’ordine dei nodi nel percorso, i dati vengono aggiornati di conseguenza.

### Combinare nodi

Un nodo combinato nell’area di lavoro del Percorso è un singolo punto nel percorso di utenti (nodo) che contiene 2 o più componenti uniti tra loro tramite la logica.

#### Creare nodi combinati

Per creare un nodo combinato nell&#39;area di lavoro del Percorso, è possibile eseguire una delle operazioni seguenti:

* Dalla barra a sinistra, trascina un singolo componente su un nodo dell’area di lavoro.

* Dalla barra a sinistra, trascina più componenti simultaneamente su un nodo dell’area di lavoro.

* Dalla barra a sinistra, trascina più componenti simultaneamente su un’area vuota dell’area di lavoro tenendo premuto il tasto Maiusc.

* Nell&#39;area di lavoro selezionare i nodi da combinare, fare clic con il pulsante destro del mouse su uno dei nodi selezionati, quindi selezionare **Combina**.<!--Is there a limit on how many you can combine? -->

#### Logica durante la combinazione dei nodi

La logica applicata ai nodi quando vengono combinati varia a seconda dei tipi di componenti che si stanno combinando, come segue:

>[!TIP]
>
>Puoi visualizzare la logica di un nodo combinato facendo clic con il pulsante destro del mouse sul nodo e selezionando [!UICONTROL **Crea filtro dal nodo**]. La logica è illustrata nella sezione [!UICONTROL **Definizione**].


| Tipi di componenti da combinare | Logica (operatore) utilizzata |
|---------|----------|
| Metrica + Metrica | Unito con OR |
| Elemento Dimension + elemento Dimension (dalla stessa dimensione padre) | Unito con OR |
| Elemento Dimension + elemento Dimension (da diverse dimensioni padre) | Unito con AND |
| Filtro + Filtro | Unito con AND |
| Dimension + metrica, intervallo di date o filtro | Unito con AND |
| Intervallo di date + Metrica, Filtro o Dimension | Unito con AND |
| Filtro + metrica, intervallo di date o Dimension | Unito con AND |

### Connetti nodi

È possibile connettere nodi già presenti nell&#39;area di lavoro oppure un nodo quando lo si aggiunge all&#39;area di lavoro.

#### Frecce tra nodi

I nodi sono collegati da una freccia. Sia la direzione della freccia che la larghezza hanno un significato:

* **Direzione**: indica la sequenza di eventi del percorso

* **Larghezza**: indica il volume percentuale da un nodo all&#39;altro

#### Logica durante la connessione dei nodi

Quando si connettono nodi nell&#39;area di lavoro del Percorso, questi vengono connessi utilizzando l&#39;operatore THEN. Questa operazione è nota anche come [filtro sequenziale](/help/components/filters/seg-sequential-build.md).

I nodi sono connessi come un &quot;percorso finale&quot;, il che significa che i visitatori vengono conteggiati purché alla fine si spostino da un nodo all’altro, indipendentemente da eventuali eventi che si verificano tra i 2 nodi.

È possibile visualizzare la logica dei nodi connessi facendo clic con il pulsante destro del mouse sul nodo e selezionando [!UICONTROL **Crea filtro dal nodo**]. La logica è illustrata nella sezione [!UICONTROL **Definizione**].

#### Connetti nodi esistenti

I percorsi non possono essere circolari e tornare ai nodi connessi in precedenza.

Per connettere i nodi nell&#39;area di lavoro del Percorso:

1. Nell’area di lavoro, passa il cursore del mouse sul nodo che si trova per primo nella sequenza di percorso che desideri connettere a un altro nodo.

   Su ogni lato del nodo selezionato vengono visualizzati 4 punti blu.

1. Trascinate uno dei 4 punti blu su uno dei 4 lati del nodo a cui desiderate connettervi.

   Viene visualizzata una freccia che collega i 2 nodi. Per ulteriori informazioni, vedere [Frecce tra nodi](#arrows-between-nodes).

#### Connetti nodi durante l’aggiunta di un nodo

Quando aggiungi un nodo all’area di lavoro, puoi posizionarlo tra due nodi connessi. Il nodo viene aggiunto al flusso del percorso tra i due nodi esistenti.

Per ulteriori informazioni, vedere [Aggiungere nodi](#add-nodes).

### Aggiungere un vincolo di tempo tra i nodi

>[!AVAILABILITY]
>
>Questa funzione non è ancora disponibile.

È possibile impostare un vincolo temporale tra i nodi. Quando è presente un vincolo di tempo, le persone vengono considerate escluse dal percorso se seguono il percorso definito ma impiegano più tempo del periodo di tempo assegnato per spostarsi tra i nodi.

L’opzione per aggiungere un vincolo temporale è disponibile per i seguenti oggetti nell’area di lavoro:

* La freccia tra i nodi

Per aggiungere un vincolo di tempo:

1. Fare clic con il pulsante destro del mouse sulla freccia tra due nodi, quindi selezionare [!UICONTROL **Aggiungi vincolo di tempo**].

<!-- 

from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon). 
1. Choose from the following options: 

-->

## Gestire nodi o frecce

### Modificare il colore di un nodo o di una freccia

>[!AVAILABILITY]
>
>Questa funzione non è ancora disponibile.

Puoi personalizzare visivamente un percorso modificando il colore di qualsiasi nodo o freccia nell’area di lavoro. Ad esempio, è possibile regolare i colori per indicare un evento desiderato o indesiderato.

L’opzione per modificare il colore è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

* La freccia tra i nodi

Per modificare il colore di un nodo o di una freccia:

1. Fare clic con il pulsante destro del mouse sul nodo o sulla freccia di cui si desidera modificare il colore.

1. Seleziona [!UICONTROL **Cambia colore**]. <!--make sure "color" isn't capitalized. It is in the req doc-->

1. Seleziona il colore desiderato.

   Sono disponibili i colori seguenti: <!--look into this interaction and color list-->

### Rinominare un nodo o una freccia

>[!AVAILABILITY]
>
>Questa funzione non è ancora disponibile.

Quando trascini un componente in una visualizzazione area di lavoro Percorsi, viene creato un nodo con lo stesso nome del nome del componente. Puoi rinominare il nodo in modo che corrisponda meglio al passaggio del percorso rappresentato dal nodo.

L’opzione per rinominare è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

* La freccia tra i nodi

Per rinominare un nodo:

1. Fare clic con il pulsante destro del mouse sul nodo da rinominare.

1. Selezionare [!UICONTROL **Rinomina**].

1. Specificare un nuovo nome, quindi premere Invio.<!--is that right?-->

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

>[!AVAILABILITY]
>
>Questa funzione non è ancora disponibile.

1. Seleziona uno o più nodi in cui desideri applicare un raggruppamento, quindi fai clic con il pulsante destro del mouse su uno dei nodi selezionati.

   Oppure

   Seleziona una o più frecce tra 2 nodi in cui desideri applicare il raggruppamento, quindi fai clic con il pulsante destro del mouse su una delle frecce selezionate.

1. Seleziona [!UICONTROL **Raggruppamento**].

<!-- 1. Choose where you want to view the breakdown:

        * [!UICONTROL **In Journey canvas**]

        * [!UICONTROL **In a freeform table**]

-->

#### Applicare un raggruppamento a un singolo nodo

Puoi trascinare una dimensione dalla barra a sinistra sul nodo dell’area di lavoro in cui desideri applicare il raggruppamento.

Per ulteriori informazioni, vedere [Aggiungere nodi](#add-nodes).

### Creazione di un pubblico

L’opzione per creare un pubblico è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

* Più nodi

* La freccia tra i nodi

* Più frecce tra nodi

Quando crei un pubblico da più nodi o frecce, questi vengono uniti con l’operatore OR.

Per creare un pubblico:

1. Seleziona uno o più nodi in cui desideri creare un pubblico, quindi fai clic con il pulsante destro del mouse su uno dei nodi selezionati.

   Oppure

   Seleziona una o più frecce tra 2 nodi in cui desideri creare un pubblico, quindi fai clic con il pulsante destro del mouse su una delle frecce selezionate.

1. Seleziona [!UICONTROL **Crea pubblico**].

<!-- 1. Choose where you want to create the audience:

        * [!UICONTROL **In Journey canvas**]

        * [!UICONTROL **In a freeform table**]

-->

1. Continuare a creare e pubblicare il pubblico come descritto in [Creare e pubblicare tipi di pubblico](/help/components/audiences/publish.md).

### Visualizza dati tendenza

>[!AVAILABILITY]
>
>Questa funzione non è ancora disponibile.

È possibile visualizzare i dati delle tendenze in un grafico a linee per gli oggetti nell&#39;area di lavoro del Percorso. <!--, with some prebuilt anomaly detection data (this is the definition in Fallout) -->

L’opzione di tendenza è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

* Più nodi

* Frecce tra i nodi

* Più frecce tra nodi

Per visualizzare i dati di tendenza:

1. Selezionare uno o più nodi per i quali si desidera visualizzare i dati sulle tendenze, quindi fare clic con il pulsante destro del mouse su uno dei nodi selezionati.

   Oppure

   Selezionare una o più frecce tra 2 nodi per i quali si desidera visualizzare i dati di tendenza, quindi fare clic con il pulsante destro del mouse su una delle frecce selezionate.

1. Seleziona [!UICONTROL **Tendenza**].

### Creare un filtro basato su un nodo o una freccia

Puoi creare un nuovo filtro basato su un nodo o una freccia all’interno di un percorso. Una volta creato il filtro, puoi utilizzarlo ovunque in Analysis Workspace.

I filtri creati dall&#39;area di lavoro del Percorso utilizzano [il filtro sequenziale](/help/components/filters/seg-sequential-build.md). Questo significa che il filtro utilizza l’operatore THEN per collegare la sequenza di eventi (il percorso) attraversati dalle persone, che porta al nodo o alla freccia selezionati. Tutti gli eventi che corrispondono al nodo o alla freccia selezionati sono inclusi nel filtro.

Se crei un filtro basato su un nodo che include più percorsi, tutti i percorsi vengono inclusi nel filtro. I percorsi separati vengono uniti con l&#39;operatore OR.

Per creare un filtro:

1. Nell’area di lavoro, fai clic con il pulsante destro del mouse sul nodo o sulla freccia che desideri utilizzare per creare il filtro.

1. Selezionare [!UICONTROL **Crea filtro dal nodo**] o [!UICONTROL **Crea filtro dalla freccia**].

   Viene visualizzato il Generatore di filtri. Nella sezione [!UICONTROL **Definition**], la definizione del filtro viene creata in base al nodo o alla freccia selezionati e al relativo contesto all&#39;interno del percorso.

1. Specifica un titolo per il filtro e apporta eventuali altre modifiche. Per ulteriori informazioni sulla creazione di un filtro, vedere [Generatore di filtri](/help/components/filters/filter-builder.md).

1. Seleziona [!UICONTROL **Salva**] per salvare il filtro.

### Elimina nodi

È possibile eliminare uno o più nodi alla volta all&#39;interno di un percorso. Quando si elimina un nodo connesso tra 2 nodi all&#39;interno del percorso, i 2 nodi rimanenti diventano connessi direttamente.

Per eliminare i nodi nell&#39;area di lavoro del Percorso:

1. Selezionare uno o più nodi da eliminare, quindi fare clic con il pulsante destro del mouse su uno dei nodi selezionati.

1. Seleziona [!UICONTROL **Elimina**].

### Elimina frecce tra nodi

È possibile eliminare una o più frecce alla volta all&#39;interno di un percorso. Quando si elimina una freccia tra due nodi, i nodi non sono più connessi. Se la freccia faceva parte di un percorso più lungo, il percorso viene disconnesso.

Per eliminare le frecce tra i nodi nell&#39;area di lavoro del Percorso:

1. Selezionare una o più frecce tra 2 nodi da eliminare, quindi fare clic con il pulsante destro del mouse su una delle frecce selezionate.

1. Seleziona [!UICONTROL **Elimina**].


<!-- Delete this after I decide I don't want to do it this way. Will probably use sections like I hav above.

### Manage existing nodes

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Right-click an **individual node** on the canvas, then select any of the following options:
   
   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Create segment**] | B1 |
   | [!UICONTROL **Publish audience**] | B2 |
   | [!UICONTROL **Trend**] | B3 | 
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Get top next ...**] | B2 |
   | [!UICONTROL **Change color**] | B2 |
   | [!UICONTROL **Rename**] | B2 |
   | [!UICONTROL **Delete**] | B2 |

1. Select **multiple nodes** on the canvas, right-click one of the selected nodes, then select any of the following options:

   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Combine**] | B1 |
   | [!UICONTROL **Delete**] | B2 |
   | [!UICONTROL **Duplicate**] | B3 | 
   | [!UICONTROL **Trend**] | B2 |
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Create segment**] | B2 |
   | [!UICONTROL **Publish audience**] | B2 |

   -->


## Apri un percorso da Journey Optimizer


In Journey Optimizer, apri il percorso che desideri analizzare nell’area di lavoro del Percorso.

1. Seleziona [!UICONTROL **Analizza in CJA**]. <!-- ?? -->