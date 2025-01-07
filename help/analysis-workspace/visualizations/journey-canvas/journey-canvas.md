---
description: Panoramica dell’area di lavoro del percorso
title: Area di lavoro percorso
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 05e1b5e26d5a1dc1e46a675131185f0927c65f22
workflow-type: tm+mt
source-wordcount: '1759'
ht-degree: 3%

---

# Panoramica dell’area di lavoro del percorso {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="Area di lavoro percorso"
>abstract="Mostra come le persone procedono attraverso o cadono da una serie di punti di contatto. Da utilizzare per percorsi con più punti di ingresso e percorsi o per analizzare percorsi creati in Journey Optimizer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="Area di lavoro percorso"
>abstract="Analizzare il modo in cui le persone procedono attraverso un percorso definito o ne escono. Crea analisi dei percorsi degli utenti creando un grafico flessibile con nodi e frecce che rappresentano qualsiasi combinazione di eventi, elementi dimensionali e filtri. Trascina i nodi nell’area di lavoro per ridisporre gli eventi e le condizioni del percorso. Come fai tu, i dati vengono aggiornati di conseguenza. <br/><br/>I clienti con accesso a Adobe Journey Optimizer possono analizzare i percorsi Journey Optimizer esistenti"

<!-- markdownlint-enable MD034 -->



La visualizzazione area di lavoro Percorso consente di analizzare e ottenere informazioni approfondite sui percorsi forniti a utenti e clienti. Consente di definire un percorso da zero o visualizzarne uno da Journey Optimizer, quindi di vedere in che modo le persone hanno abbandonato (abbandonato) o continuato (proseguito) il percorso.

È possibile [creare analisi di percorsi di utenti](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) utilizzando qualsiasi combinazione di eventi, elementi dimensionali, filtri e intervalli di date per creare nodi di percorso. Connetti i nodi per creare il flusso del percorso e includi più percorsi e punti decisionali. Trascina i nodi nell’area di lavoro per ridisporre gli eventi e le condizioni del percorso. I dati vengono aggiornati in tempo reale man mano che apporti modifiche.

[I nodi sono connessi](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) come &quot;percorso finale&quot;, il che significa che i visitatori vengono conteggiati finché passano da un nodo all&#39;altro, indipendentemente dagli eventi che si verificano tra i due nodi. Il tempo assegnato agli utenti per spostarsi lungo il percorso è determinato dall’impostazione del contenitore.

![Area di lavoro Percorsi](assets/journey-canvas.png)

## Funzioni chiave

Le funzioni chiave della visualizzazione Area di lavoro del Percorso includono:

* Analisi approfondita dell’abbandono e dell’abbandono per soddisfare i percorsi di utenti più complessi.

* Area di lavoro per la mappatura e la visualizzazione dei vari punti di ingresso, nodi e percorsi di un percorso di utenti.

* Interazioni tramite trascinamento per l’aggiunta di componenti all’area di lavoro e il riposizionamento dei nodi esistenti.

* Opzione per creare analisi di percorsi di utenti all’interno dell’area di lavoro del Percorso o per crearli automaticamente in base ai percorsi Journey Optimizer.

## Potenziali informazioni

L’area di lavoro percorso fornisce informazioni fruibili per i percorsi più complessi.

### Percorso con il tasso di conversione più alto {#conversion-rate-caption}

L’informazione più importante nell’area di lavoro del Percorso viene visualizzata come una didascalia nella parte superiore dell’area stessa.

Questa didascalia riassume quale di tutti i percorsi nel percorso ha avuto il più alto tasso di conversione.

Se il percorso contiene più nodi iniziali, la didascalia avrà l&#39;aspetto seguente:

![Didascalia approfondimento area di lavoro Percorsi](assets/journey-canvas-caption.png)

Quando il percorso contiene un singolo nodo iniziale, la didascalia si presenta così:

![didascalia di approfondimento area di lavoro Percorso nodo single start](assets/journey-canvas-caption-singlestart.png)

Quando interpreti questa didascalia, tieni presente quanto segue:

* Un _percorso_ è definito come un nodo iniziale connesso tramite frecce a un nodo finale, con un numero qualsiasi di nodi connessi tra loro.

* Il calcolo del tasso di conversione dipende dal tipo di percorso (il numero di nodi iniziali e finali contenuti nel percorso e se i percorsi si intersecano tra loro).

  La tabella seguente descrive come vengono calcolati i tassi di conversione in base al tipo di percorso:

  | Tipo di percorso | Calcolo del tasso di conversione | Esempio |
  |---------|----------|---------|
  | **Un singolo nodo iniziale e un singolo nodo finale** | Il tasso di conversione viene calcolato dividendo il numero del nodo finale per quello del nodo iniziale. | ![Percorso con più avvii che convergono in un nodo comune](assets/journey-canvas-single-path.png) |
  | **Un singolo nodo iniziale e più nodi finali** | Il tasso di conversione viene calcolato individuando il nodo finale con il numero più alto e dividendo tale numero per quello del nodo iniziale. | ![Percorso con più avvii che convergono in un nodo comune](assets/journey-canvas-singlestart-multiend.png) |
  | **Più percorsi autonomi, ognuno contenente un singolo nodo iniziale e un singolo nodo finale** | Il tasso di conversione viene calcolato dividendo il numero del nodo finale per quello del nodo iniziale. Il percorso con il tasso di conversione più alto è descritto nella didascalia. | ![Percorso con più avvii che convergono in un nodo comune](assets/journey-canvas-multi-start-separate.png) |
  | **Più nodi iniziali che in qualsiasi punto del percorso convergono in un nodo comune** | Il tasso di conversione viene calcolato individuando il nodo finale con il numero più alto e dividendo tale numero per quello del nodo iniziale con il numero più basso. | ![Percorso con più avvii che convergono in un nodo comune](assets/journey-canvas-multi-start-converge.png) |

### Abbandono, Abbandono e altro ancora

Di seguito sono riportati alcuni esempi di altre informazioni che l’area di lavoro del Percorso può fornire. Puoi scegliere se queste informazioni si basano su tutte le persone nella visualizzazione dati, su tutte le persone che hanno avviato il percorso o su tutte le persone del nodo precedente del percorso.

#### Fallthrough

* Numero e percentuale di persone che hanno completato il percorso (arrivate al nodo finale)

* Numero e percentuale di persone arrivate a un determinato nodo del percorso

* Il passaggio più comune che è arrivato dopo o prima di un dato nodo del percorso

#### Fallout (abbandono)

* I nodi del percorso in cui le persone più comunemente cadevano dal percorso (non sono mai arrivate ai nodi immediatamente successivi)

#### Dati aggiuntivi per ogni nodo

* Aggiungi una dimensione di raggruppamento su qualsiasi nodo del percorso per visualizzare dati aggiuntivi per quel nodo specifico

## Scegli tra le visualizzazioni Area di lavoro Percorso, Abbandono o Flusso

La visualizzazione dell&#39;area di lavoro del Percorso presenta analogie con la [visualizzazione Abbandono](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) e la [visualizzazione Flusso](/help/analysis-workspace/visualizations/c-flow/flow.md), ma con differenze importanti.

### Comprendere le differenze

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Quando utilizzare l’area di lavoro del Percorso

L’area di lavoro del percorso è essenziale per:

* Analisi dell’abbandono che coinvolge percorsi con più punti di ingresso e percorsi.

* Percorsi non lineari con più punti di ingresso e percorsi, con una sequenza di pagine predefinita.

* Analisi esplorativa ad hoc basata su un percorso predefinito.

* Analisi che richiede una metrica primaria diversa da Sessione, Persona o Occorrenze.

* Analisi più approfondita dei percorsi originati in Adobe Journey Optimizer.

Utilizza [la tabella precedente](#understand-the-differences) per comprendere le differenze tra le visualizzazioni Area di lavoro Percorso, Abbandono e Flusso.

## Analizzare percorsi Journey Optimizer

>[!NOTE]
>
>Se la tua organizzazione non ha accesso a Journey Optimizer, puoi comunque [generare analisi nell&#39;area di lavoro del Percorso](#build-analyses-in-customer-journey-analytics).

L’analisi dei percorsi Journey Optimizer nell’area di lavoro del Percorso fornisce informazioni approfondite e fruibili sul modo in cui le persone interagiscono con un percorso.

Quando si analizza un percorso Journey Optimizer nell&#39;area di lavoro del Percorso, il percorso viene visualizzato con l&#39;ordine, la sequenza e la struttura di Journey Optimizer. Se si apportano modifiche significative a un percorso nell&#39;area di lavoro del Percorso, [le modifiche non verranno più sincronizzate da Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas).

### Vantaggi dell&#39;analisi dei percorsi Journey Optimizer con l&#39;area di lavoro del Percorso

L’area di lavoro percorso fornisce un’analisi approfondita e approfondita che non è possibile eseguire in Journey Optimizer.

L’utilizzo dell’area di lavoro Percorso per analizzare i percorsi creati in Journey Optimizer offre diversi vantaggi:

* Crea eventi utilizzando qualsiasi dimensione di Customer Journey Analytics, metrica, filtro o intervallo di date.

  In Journey Optimizer, un utente tecnico deve creare un evento prima di poterlo aggiungere a un percorso.

* Crea tipi di pubblico in base a un nodo personalizzato creato (avvia il Generatore di pubblico di Customer Journey Analytics).

  In Journey Optimizer, puoi creare tipi di pubblico solo per attività predefinite.

* Analizzare fallthrough e fallout

* Suddividere gli eventi con qualsiasi dimensione

* Combinare gli eventi

* Eventi di connessione

* Rinominare ed eliminare gli eventi

* Molto di più

### Sincronizzazione tra Journey Optimizer e l’area di lavoro del Percorso

Dopo aver creato un&#39;analisi di un percorso Journey Optimizer nell&#39;area di lavoro del Percorso, i dati vengono sincronizzati in una sola direzione, da Journey Optimizer all&#39;area di lavoro del Percorso. Ciò significa che le modifiche apportate a un percorso nell’area di lavoro del Percorso non vengono mai applicate in Journey Optimizer.

Inoltre, le modifiche apportate a un percorso in Journey Optimizer vengono sincronizzate con l&#39;area di lavoro del Percorso [solo se il percorso non è stato modificato in modo significativo nell&#39;area di lavoro del Percorso](#differences-after-modifying-a-journey-in-journey-canvas). Dopo aver modificato un percorso nell&#39;area di lavoro del Percorso, tutte le modifiche apportate al percorso in Journey Optimizer non vengono riportate nell&#39;area di lavoro del Percorso. Per visualizzare le modifiche nell&#39;area di lavoro del Percorso, è possibile eliminare e [ricreare il percorso nell&#39;area di lavoro del Percorso](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Differenze dopo la modifica di un percorso nell’area di lavoro del Percorso {#differences-after-modifying}

Dopo aver modificato un percorso Journey Optimizer nell’area di lavoro del Percorso, possono verificarsi modifiche nell’elaborazione dei dati, nelle funzioni disponibili e nel comportamento di sincronizzazione.

Se apporti una modifica significativa a un percorso Journey Optimizer nell’area di lavoro del Percorso, possono verificarsi modifiche nell’elaborazione dei dati, nelle funzioni disponibili e nel comportamento di sincronizzazione. Una modifica significativa include uno dei seguenti elementi:

* Aggiunta o rimozione di un nodo

* Aggiunta o rimozione di una freccia tra nodi

* Modifica dei componenti su un nodo

Se si apportano altre modifiche a un percorso Journey Optimizer nell’area di lavoro del Percorso, ad esempio se si trascina un nodo o si aggiunge un raggruppamento, le differenze descritte nelle sezioni seguenti non sono applicabili.

>[!NOTE]
>
>Per ripristinare lo stato originale del percorso, è possibile premere Ctrl+z dopo aver apportato la prima modifica nell&#39;area di lavoro del Percorso. In alternativa, è possibile eliminare e [ricreare il percorso nell&#39;area di lavoro del Percorso](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### Differenze nell’elaborazione dei dati

Dopo aver modificato un percorso Journey Optimizer nell’area di lavoro del Percorso, potresti notare delle modifiche ai dati se il percorso contiene metriche con modelli di attribuzione non predefiniti.

Questo perché, a differenza di Journey Optimizer, l’area di lavoro del Percorso consente di applicare più dimensioni all’interno di un singolo percorso. Questa funzionalità indica che [attribuzione metrica](/help/data-views/component-settings/attribution.md) non è supportata.

#### Differenze nelle funzioni

Dopo aver modificato un percorso Journey Optimizer nell&#39;area di lavoro del Percorso, le opzioni disponibili nel campo a discesa [!UICONTROL **Impostazioni freccia**] variano a seconda delle modifiche apportate. Per ulteriori informazioni, vedere [Configurare le impostazioni](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

Il campo [!UICONTROL **Tipo di nodo**] è disponibile solo in Journey Optimizer. Non è disponibile quando si visualizza un percorso Journey Optimizer nell’area di lavoro del Percorso, indipendentemente dal fatto che si apportino modifiche al percorso nell’area di lavoro del Percorso.

#### Differenze di sincronizzazione

Le modifiche apportate a un percorso in Journey Optimizer vengono sincronizzate con l&#39;area di lavoro del Percorso solo se il percorso rimane invariato nell&#39;area di lavoro del Percorso.

Dopo aver modificato un percorso Journey Optimizer nell&#39;area di lavoro del Percorso, tutte le modifiche apportate al percorso in Journey Optimizer non vengono applicate nell&#39;area di lavoro del Percorso. Per visualizzare le modifiche nell&#39;area di lavoro del Percorso, è possibile eliminare e [ricreare il percorso nell&#39;area di lavoro del Percorso](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Differenze terminologiche tra Journey Optimizer e Customer Journey Analytics

Certi termini che significano una cosa in Journey Optimizer significano qualcos&#39;altro in Customer Journey Analytics. Quando si utilizza l’area di lavoro del Percorso, vengono utilizzati i termini del Customer Journey Analytics.

| Termine | Area di lavoro percorso | Journey Optimizer |
|---------|----------|---------|
| **Evento** | Una delle diverse metriche standard disponibili in Customer Journey Analytics. Questa metrica conta elementi come ricavi, abbonamenti o lead generati. | La categoria di attività che attiva un percorso personalizzato, ad esempio un acquisto online. |

### Analizzare un percorso Journey Optimizer nell’area di lavoro del Percorso

Per informazioni sull&#39;analisi di un percorso Journey Optimizer nell&#39;area di lavoro Percorso, vedere [Configurare una visualizzazione dell&#39;area di lavoro Percorso](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Generare analisi nell’area di lavoro del Percorso

Puoi creare analisi nell’area di lavoro del Percorso basate su qualsiasi dimensione o metrica disponibile in Analysis Workspace. In alternativa, è possibile analizzare i percorsi creati in Journey Optimizer. Per ulteriori informazioni, vedere [Configurare una visualizzazione dell&#39;area di lavoro di Percorso](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).
