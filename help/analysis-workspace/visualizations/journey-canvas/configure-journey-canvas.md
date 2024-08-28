---
description: Configurare una visualizzazione area di lavoro Percorso
title: Area di lavoro percorso
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: e06793a0ce73fa8d6aa9b798209bfc044e696931
workflow-type: tm+mt
source-wordcount: '4087'
ht-degree: 1%

---

# Configurare una visualizzazione area di lavoro Percorso

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

   Aggiungere una visualizzazione dell&#39;area di lavoro del Percorso in uno dei modi descritti nella sezione [Aggiungere visualizzazioni a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) in [Panoramica delle visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Specifica le seguenti informazioni di base:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Metrica primaria**] | La metrica principale influisce sui seguenti aspetti della visualizzazione dell’area di lavoro del Percorso:  <ul><li>Definisce il modo in cui le persone si spostano nel percorso.</li><li>Numero totale visualizzato su ciascun nodo.<p>Ad esempio, se Persone è la metrica principale, ogni nodo mostra il numero di persone che hanno raggiunto quel nodo nel percorso.</p></li><li>La percentuale visualizzata su ciascun nodo. Una volta creata la visualizzazione, puoi scegliere di mostrare la percentuale del totale o del nodo iniziale.</li><p>Ad esempio, se Persone è la metrica principale, ogni nodo mostra la percentuale di persone che hanno raggiunto quel nodo nel percorso (la percentuale del totale o del nodo iniziale).</p></li><li>Quando una dimensione viene aggiunta alla visualizzazione, vengono aggiunti i primi 3 nodi della visualizzazione, in base alla metrica principale.</li></ul> |
   | [!UICONTROL **Metrica secondaria**] | La metrica secondaria è facoltativa. Quando ne è selezionato uno, le seguenti informazioni vengono visualizzate su ciascun nodo sotto la metrica principale: <ul><li>Numero totale<p>Ad esempio, se Sessioni è la metrica secondaria, ogni nodo mostra il numero di sessioni che hanno raggiunto quel nodo nel percorso.</p></li><li>La percentuale (dopo aver creato la visualizzazione, puoi scegliere di mostrare la percentuale del totale o del nodo iniziale).</li><p>Ad esempio, se Sessioni è la metrica secondaria, ogni nodo mostra la percentuale di sessioni che hanno raggiunto tale nodo nel percorso (la percentuale del totale o del nodo iniziale).</p></li></ul> |
   | [!UICONTROL **percorso Journey Optimizer**]<!-- name? --> | Seleziona il percorso Journey Optimizer da utilizzare come base per l’analisi nell’area di lavoro del Percorso. In alternativa, puoi lasciare vuota questa opzione se desideri un’area di lavoro vuota da cui generare l’analisi in Analysis Workspace.</p> <p>Quando si analizza un percorso Journey Optimizer nell&#39;area di lavoro del Percorso, il percorso viene visualizzato con l&#39;ordine, la sequenza e la struttura di Journey Optimizer. Per ulteriori informazioni, vedere [Analizzare i percorsi Journey Optimizer](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) in [Panoramica area di lavoro Percorsi](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Nota**: questa opzione viene visualizzata solo quando vengono rilevati dati Journey Optimizer nella visualizzazione dati selezionata nel pannello Analysis Workspace in cui si sta aggiungendo la visualizzazione. Per informazioni sulla modifica della visualizzazione dati in un pannello di Analysis Workspace, vedi [Panoramica di Analysis Workspace](/help/analysis-workspace/home.md).</p> |

1. (Facoltativo) Seleziona [!UICONTROL **Mostra impostazioni avanzate**], quindi specifica le seguenti informazioni:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **contenitore area di lavoro Percorsi**] | Scegli il contenitore su cui concentrarti in tutto il percorso. Il contenitore scelto determina le statistiche visualizzate nella visualizzazione. Se i nomi dei contenitori sono diversi da quelli predefiniti mostrati di seguito, significa che sono stati personalizzati nella visualizzazione dati.<ul><li>**Sessioni:** limita le statistiche della visualizzazione in modo che rientrino in una singola sessione definita per una determinata persona. Ciò significa che i numeri e le percentuali visualizzati su ciascun nodo (che sono basati sulle metriche primaria e secondaria) devono verificarsi all’interno di una singola sessione per ogni persona.</li><li>**Persone:** consente alle statistiche della visualizzazione di coprire più sessioni per una determinata persona. Ciò significa che i numeri e le percentuali visualizzati su ciascun nodo (che sono basati sulle metriche primaria e secondaria) possono verificarsi in qualsiasi numero di sessioni, purché le sessioni appartengano alla stessa persona. Questa è l&#39;impostazione predefinita.</li></ul> |

1. Seleziona [!UICONTROL **Build**].

   Se avete selezionato un percorso Journey Optimizer Journey Optimizer, il percorso viene visualizzato con lo stesso ordine, la stessa sequenza e la stessa struttura di Journey Optimizer.

   <!-- add screen shot -->

   Se non disponi di Journey Optimizer o se non hai selezionato un percorso Journey Optimizer, viene visualizzata un’area di lavoro vuota in cui puoi iniziare a popolare il percorso.

   <!-- add screen shot -->

1. Sia che si crei una nuova analisi da un&#39;area di lavoro vuota che si stia analizzando un percorso Journey Optimizer, è possibile configurare il percorso come descritto in [Configurare una visualizzazione dell&#39;area di lavoro Percorso](#begin-building-a-journey-canvas-visualization).


## Configurare una visualizzazione area di lavoro Percorso

Devi [iniziare a creare una visualizzazione dell&#39;area di lavoro del Percorso](#begin-building-a-journey-canvas-visualization) prima di configurarla come descritto nelle sezioni seguenti.

### Configurare le impostazioni

1. In Analysis Workspace, apri una visualizzazione dell&#39;area di lavoro del Percorso esistente oppure [creane una nuova](#begin-building-a-journey-canvas-visualization).

1. Configura una delle seguenti impostazioni visualizzate nella parte superiore della visualizzazione:

   | Impostazione | Funzione |
   |---------|----------|
   | [!UICONTROL **Tipo di nodo**] | Consente di configurare quali tipi di nodo vengono visualizzati nella visualizzazione. Per nascondere un tipo di nodo dalla visualizzazione, seleziona il (x) accanto al tipo di nodo oppure deselezionalo dal menu a discesa. Per visualizzare un tipo di nodo nascosto, selezionalo dal menu a discesa. <p>A seconda del contenuto della visualizzazione, i possibili tipi di nodo includono:</p><ul><li>[!UICONTROL **Leggi segmento**]</li><li>[!UICONTROL **Fine**]</li><li>[!UICONTROL **Dimensione**]</li><li>[!UICONTROL **Metrica**]</li></ul><p>**Nota**: quando utilizzi questo campo, considera quanto segue:</p><ul><li>Questa opzione viene visualizzata solo quando i dati di Journey Optimizer vengono rilevati nella visualizzazione dati selezionata nel pannello Analysis Workspace in cui stai aggiungendo la visualizzazione. Per informazioni sulla modifica della visualizzazione dati in un pannello di Analysis Workspace, vedi [Panoramica di Analysis Workspace](/help/analysis-workspace/home.md).</li><li>Dopo aver modificato un percorso Journey Optimizer nell’area di lavoro del Percorso, questa opzione non è più disponibile. Per ulteriori informazioni, vedere [Differenze visive dopo la modifica di un percorso nell&#39;area di lavoro del Percorso](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#visual-differences-after-modifying-a-journey-in-journey-canvas)</li></ul></p> |
   | [!UICONTROL **Valore percentuale**] | Scegli tra le seguenti opzioni: <ul><li>[!UICONTROL **Percentuale del totale**]: la percentuale di tutte le persone incluse nella visualizzazione dati nell&#39;intervallo di date del pannello.</li><li>[!UICONTROL **Percentuale del nodo iniziale**]: la percentuale di tutte le persone incluse nel nodo iniziale.<p>Questa opzione è disponibile solo se si dispone di un singolo nodo iniziale. Se disponi di più nodi iniziali, l’opzione è nascosta.</p></li></ul> |
   | [!UICONTROL **Impostazioni freccia**] | Scegli tra le seguenti opzioni:<ul><li>[!UICONTROL **Nessuno**]: </li><li>[!UICONTROL **Condizione**]: </li><li>[!UICONTROL **Tutte le etichette**]: </li></ul><p>**Nota**: questa opzione viene visualizzata solo quando vengono rilevati dati Journey Optimizer nella visualizzazione dati selezionata nel pannello Analysis Workspace in cui si sta aggiungendo la visualizzazione. Per informazioni sulla modifica della visualizzazione dati in un pannello di Analysis Workspace, vedi [Panoramica di Analysis Workspace](/help/analysis-workspace/home.md).</p> |
   | [!UICONTROL **Mostra abbandono**] | Visualizza i dati di abbandono per ciascun nodo, mostrando il numero e la percentuale di persone che hanno abbandonato il percorso in un determinato nodo. |

1. Continua con [Aggiungi un nodo](#add-a-node).

### Aggiungi un nodo

I nodi in una visualizzazione dell’area di lavoro di un Percorso rappresentano gli eventi o le azioni di un percorso di utenti. Per creare i nodi, trascina i componenti Workspace dalla barra a sinistra all’area di lavoro.

Per aggiungere un nodo a una visualizzazione dell’area di lavoro del Percorso:

1. In Analysis Workspace, apri una visualizzazione dell&#39;area di lavoro del Percorso esistente oppure [creane una nuova](#begin-building-a-journey-canvas-visualization).

1. Trascina metriche, dimensioni, elementi dimensionali, filtri o intervalli di date dalla barra a sinistra all’area di lavoro. Metriche calcolate non supportate. Inoltre, le metriche o dimensioni basate su un [set di dati di riepilogo](/help/data-views/summary-data.md) non sono supportate.

   Per selezionare più componenti nella barra a sinistra, tieni premuto Maiusc oppure tieni premuto Comando (su Mac) o Ctrl (su Windows).

   La visualizzazione viene aggiornata come segue, a seconda del tipo di componente e dell’area di lavoro in cui la inserisci:

   | Tipo di componente | Posizionamento del componente | La visualizzazione viene aggiornata dopo l’aggiunta del nodo |
   |---------|----------|----------|
   | Metrica | Area vuota dell’area di lavoro | Il nodo visualizza il punto in cui il componente è stato rilasciato, senza connessione con alcun nodo esistente. |
   | Metrica | Un nodo esistente | Il componente viene combinato automaticamente con il nodo esistente. (Vedi [Combina nodi](#combine-nodes) per ulteriori informazioni.)</p> |
   | Metrica | Una freccia tra 2 nodi esistenti | Il nodo viene visualizzato tra i due nodi esistenti in cui il componente è stato rilasciato ed è connesso a entrambi i nodi esistenti. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p> |
   | Dimensione | Area vuota dell’area di lavoro | Vengono creati 3 nodi per i primi 3 elementi dimensionali in cui il componente è stato rilasciato, senza alcuna connessione con i nodi esistenti. (**Nota:** se vengono visualizzati solo 1 o 2 nodi, significa che i dati sono disponibili solo per 1 o 2 degli elementi dimensionali. Se non vengono visualizzati nodi, significa che i dati non sono disponibili per nessuno degli elementi dimensionali. In questo caso, prova ad aggiungerlo a un punto diverso del percorso, a regolare l’intervallo di date della visualizzazione o a scegliere una dimensione diversa.<p>Quando rilasci la dimensione nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerla come nodo singolo con 3 elementi dimensionali.</p><p></p> |
   | Dimensione | Un nodo esistente | Al nodo viene applicato automaticamente un raggruppamento con i primi 5 elementi dimensionali visualizzati.<!--what happens if you hold Shift?--> |
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
   | Più componenti | Area vuota dell&#39;area di lavoro | **Se nessuno dei componenti sono dimensioni:**<p>Ogni componente viene visualizzato come un nodo separato in cui i componenti sono stati eliminati, senza alcuna connessione con i nodi esistenti.</p><p>Quando rilasci i componenti nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerli come un nodo combinato. </p><p>**Se uno dei componenti che stai aggiungendo sono dimensioni:**</p><p>Ogni componente viene visualizzato come un nodo separato in cui i componenti sono stati eliminati, senza alcuna connessione con i nodi esistenti.</p><p>È possibile aggiungere una sola dimensione alla volta e vengono creati 3 nodi per i primi 3 elementi dimensionali in cui il componente è stato rilasciato.</p><p>Quando rilasci i componenti nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerli come un nodo combinato. I primi 3 elementi dimensionali sono combinati con ciascun nodo. (Vedi [Combina nodi](#combine-nodes) per ulteriori informazioni.)</p> |
   | Più componenti | Un nodo esistente | Tutti i componenti sono combinati con il nodo esistente.<p>Se uno dei componenti che stai aggiungendo sono dimensioni, i primi 3 elementi dimensionali vengono combinati con il nodo.</p> <p>È possibile aggiungere una sola dimensione alla volta.</p> |
   | Più componenti | Una freccia che connette 2 nodi esistenti | **Se nessuno dei componenti sono dimensioni:**<p>Ogni componente viene visualizzato come un nodo separato in cui i componenti sono stati eliminati e ogni nodo è connesso a entrambi i nodi esistenti. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p><p>Quando rilasci i componenti nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerli come un nodo combinato. I componenti devono essere dello stesso tipo per essere combinati in un singolo nodo. (Vedi [Combina nodi](#combine-nodes) per ulteriori informazioni.)</p><p>**Se uno dei componenti che stai aggiungendo sono dimensioni:**</p><p>Ogni componente viene visualizzato come un nodo separato in cui i componenti sono stati eliminati e ogni nodo è connesso a entrambi i nodi esistenti.</p><p>È possibile aggiungere una sola dimensione alla volta e vengono creati 3 nodi per i primi 3 elementi della dimensione che seguono il primo evento dopo il primo nodo (di persone/sessioni che alla fine raggiungono il secondo nodo). Ogni nodo è connesso a entrambi i nodi esistenti. (Vedi [Connetti nodi](#connect-nodes) per ulteriori informazioni.)</p><p>Quando rilasci i componenti nell’area di lavoro, tieni premuto il tasto Maiusc per aggiungerli come un nodo combinato. I primi 3 elementi dimensionali sono combinati con ciascun nodo e ogni nodo è connesso a entrambi i nodi esistenti. (Vedi [Combina nodi](#combine-nodes) per ulteriori informazioni.)</p> |

   I nodi vengono visualizzati come una casella rettangolare con le seguenti informazioni:

   * Nome componente

   * Il tipo di componente (ad esempio metrica o dimensione)

   * Statistiche delle metriche primarie (totale e percentuale)

   * Statistiche metriche secondarie (totale e percentuale)

1. Ripeti questa procedura per continuare ad aggiungere nodi per creare il percorso.

1. Continuate a personalizzare il percorso come descritto nelle sezioni seguenti. Puoi connettere nodi, rinominare nodi, applicare suddivisioni, creare tipi di pubblico, aggiungere vincoli di tempo e altro ancora.

### Aggiungere i nodi principali in base ai nodi esistenti

Puoi aggiungere automaticamente i nodi principali in base ai nodi già presenti nell’area di lavoro.

Questa opzione è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

* La freccia tra i nodi

#### Aggiungi nodi principali dopo un nodo esistente

Puoi selezionare un nodo e aggiungere al percorso i primi 3 nodi successivi.

1. Fare clic con il pulsante destro del mouse sul nodo in cui si desidera aggiungere i primi 3 nodi successivi nel percorso.

   Questo nodo non può avere nodi esistenti che ne escano nel percorso.

1. Seleziona [!UICONTROL **Aggiungi nodi principali dopo questo nodo**].

   Vengono aggiunti i primi 3 nodi che seguono questo nodo nel percorso e ciascuno di essi è connesso al nodo selezionato come ramo separato.

#### Aggiungi nodi principali prima di un nodo esistente

Puoi aggiungere i primi 3 nodi che precedono un nodo esistente nel percorso.

1. Fare clic con il pulsante destro del mouse sul nodo in cui si desidera aggiungere i primi 3 nodi che lo precedono nel percorso.

   Questo nodo non può contenere nodi esistenti che entrano in esso nel percorso.

1. Seleziona [!UICONTROL **Aggiungi nodi principali prima di questo nodo**].

   Vengono aggiunti i primi 3 nodi che precedono questo nodo nel percorso e ciascuno di essi è connesso al nodo selezionato come ramo separato.

#### Aggiungi nodi principali tra nodi esistenti

Puoi aggiungere i primi 3 nodi compresi tra 2 nodi esistenti:

1. Fare clic con il pulsante destro del mouse sulla freccia tra i due nodi in cui si desidera aggiungere i primi tre nodi del percorso.

1. Seleziona [!UICONTROL **Aggiungi nodi principali**].<!-- I don't think this should have the word "next" in the UI option, because it's both next and previous. It's in between. Just "Get top nodes" sounds better to me.-->

   I primi 3 nodi vengono aggiunti tra i 2 nodi esistenti e ciascuno di essi viene connesso come ramo separato.

### Ridisponi nodi

I percorsi nell’area di lavoro del Percorso sono costituiti da un grafico flessibile di nodi e frecce che rappresentano qualsiasi combinazione di eventi, elementi dimensionali e filtri.

Puoi trascinare i nodi nell’area di lavoro per ridisporre gli eventi e le condizioni del percorso. Come fai tu, i dati vengono aggiornati di conseguenza.

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
| DIMENSION + DIMENSION | Unito con OR |
| Filtro + Filtro | Unito con AND |
| Dimension + metrica, intervallo di date o filtro | Unito con AND |
| Intervallo di date + Metrica, Filtro o Dimension | Unito con AND |
| Filtro + metrica, intervallo di date o Dimension | Unito con AND |

### Connetti nodi

È possibile connettere nodi già presenti nell&#39;area di lavoro oppure un nodo quando lo si aggiunge all&#39;area di lavoro.

#### Connetti nodi esistenti

La freccia tra i nodi nell&#39;area di lavoro del Percorso determina la sequenza di eventi nel percorso.

Per connettere i nodi nell&#39;area di lavoro del Percorso:

1. Nell’area di lavoro, passa il cursore del mouse sul nodo che si trova per primo nella sequenza di percorso che desideri connettere a un altro nodo.

   Su ogni lato del nodo selezionato vengono visualizzati 4 punti blu.

1. Trascinate uno dei 4 punti blu su uno dei 4 lati del nodo a cui desiderate connettervi.

   Viene visualizzata una freccia che collega i 2 nodi. La freccia indica la direzione di spostamento delle persone nel percorso.

#### Connetti nodi durante l’aggiunta di un nodo

Quando aggiungi un nodo all’area di lavoro, puoi posizionarlo tra due nodi connessi. Il nodo viene aggiunto al flusso del percorso tra i due nodi esistenti.

Per ulteriori informazioni, vedere [Aggiungere un nodo](#add-a-node).

### Modificare il colore di un nodo o di una freccia

Puoi modificare il colore di un nodo o di una freccia nell’area di lavoro.

L’opzione per modificare il colore è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

* La freccia tra i nodi

Per modificare il colore di un nodo o di una freccia:

1. Fare clic con il pulsante destro del mouse sul nodo o sulla freccia di cui si desidera modificare il colore.

1. Seleziona [!UICONTROL **Cambia colore**]. <!--make sure "color" isn't capitalized. It is in the req doc-->

1. Seleziona il colore desiderato.

   Sono disponibili i colori seguenti: <!--look into this interaction and color list-->

### Rinominare un nodo o una freccia

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

### Applicare un raggruppamento a uno o più nodi o frecce

1. Seleziona uno o più nodi in cui desideri applicare un raggruppamento, quindi fai clic con il pulsante destro del mouse su uno dei nodi selezionati.

   Oppure

   Seleziona una o più frecce tra 2 nodi in cui desideri applicare il raggruppamento, quindi fai clic con il pulsante destro del mouse su una delle frecce selezionate.

1. Seleziona [!UICONTROL **Raggruppamento**].

### Applicare un raggruppamento a un singolo nodo

Puoi trascinare una dimensione dalla barra a sinistra sul nodo dell’area di lavoro in cui desideri applicare il raggruppamento.

Per ulteriori informazioni, vedere [Aggiungere un nodo](#add-a-node).

### Creazione di un pubblico

L’opzione per creare un pubblico è disponibile per i seguenti oggetti nell’area di lavoro:

* Singoli nodi

* Più nodi

* La freccia tra i nodi

* Più frecce tra nodi

Per creare un pubblico:

1. Seleziona uno o più nodi in cui desideri creare un pubblico, quindi fai clic con il pulsante destro del mouse su uno dei nodi selezionati.

   Oppure

   Seleziona una o più frecce tra 2 nodi in cui desideri creare un pubblico, quindi fai clic con il pulsante destro del mouse su una delle frecce selezionate.

1. Seleziona [!UICONTROL **Crea pubblico**].

1. Continuare a creare e pubblicare il pubblico come descritto in [Creare e pubblicare tipi di pubblico](/help/components/audiences/publish.md).

### Visualizza dati tendenza

È possibile visualizzare i dati delle tendenze in un grafico a linee per gli oggetti nell&#39;area di lavoro del Percorso. &lt;!—, con alcuni dati di rilevamento delle anomalie predefiniti (questa è la definizione in Abbandono)>

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

### Nodi duplicati

L’opzione per duplicare è disponibile per i seguenti oggetti nell’area di lavoro:

* Più nodi

Per duplicare i nodi:

1. Selezionare più nodi da duplicare.

1. Fare clic con il pulsante destro del mouse su uno dei nodi selezionati, quindi selezionare [!UICONTROL **Duplica**].


### Aggiungere un vincolo di tempo tra i nodi

È possibile impostare un vincolo temporale tra i nodi. Quando è presente un vincolo di tempo, se una persona segue il percorso definito ma impiega più tempo del periodo di tempo assegnato per spostarsi tra i nodi, si considera che sia uscita dal percorso.

L’opzione per aggiungere un vincolo temporale è disponibile per i seguenti oggetti nell’area di lavoro:

* La freccia tra i nodi

Per aggiungere un vincolo di tempo:

1. Fare clic con il pulsante destro del mouse sulla freccia tra due nodi, quindi selezionare [!UICONTROL **Aggiungi vincolo di tempo**].

<!-- 

from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon). 
1. Choose from the following options: 

-->

### Creare un filtro basato su un nodo o una freccia

Puoi creare un nuovo filtro basato su un nodo o una freccia all’interno di un percorso. Una volta creato il filtro, puoi utilizzarlo ovunque in Analysis Workspace.

I filtri creati dall&#39;area di lavoro del Percorso utilizzano [il filtro sequenziale](/help/components/filters/seg-sequential-build.md). Questo significa che il filtro utilizza l’operatore THEN per collegare la sequenza di eventi (ovvero il percorso) attraversati dalle persone, che porta al nodo o alla freccia selezionati. Tutti gli eventi che corrispondono al nodo o alla freccia selezionati sono inclusi nel filtro.

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

