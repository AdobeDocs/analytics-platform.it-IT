---
description: Panoramica dell’area di lavoro del percorso
title: Area di lavoro percorso
feature: Visualizations
role: User
hide: true
hidefromtoc: true
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 5d65f2cee34741d985ae7b85ad62f65a68c6289a
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 2%

---

# Panoramica dell’area di lavoro del percorso

{{release-limited-testing}}

La visualizzazione area di lavoro Percorso consente di analizzare e ottenere informazioni approfondite sui percorsi forniti a utenti e clienti. Consente di definire un percorso da zero o visualizzarne uno da Journey Optimizer, quindi di vedere in che modo le persone hanno abbandonato (abbandonato) o continuato (proseguito) il percorso.

È possibile [creare analisi di percorsi di utenti](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) utilizzando qualsiasi combinazione di eventi, elementi dimensionali, filtri e intervalli di date per creare nodi di percorso. Connetti i nodi per creare il flusso del percorso e includi più percorsi e punti decisionali. Trascina i nodi nell’area di lavoro per ridisporre gli eventi e le condizioni del percorso. I dati vengono aggiornati in tempo reale man mano che apporti modifiche.

## Funzioni chiave

Le funzioni chiave della visualizzazione Area di lavoro del Percorso includono:

* Analisi approfondita dell’abbandono e dell’abbandono per soddisfare i percorsi di utenti più complessi.

* Area di lavoro per la mappatura e la visualizzazione dei vari punti di ingresso, nodi e percorsi di un percorso di utenti.

* Interazioni tramite trascinamento per l’aggiunta di componenti all’area di lavoro e il riposizionamento dei nodi esistenti.

* Opzione per creare analisi di percorsi di utenti all’interno dell’area di lavoro del Percorso o per crearli automaticamente in base ai percorsi Journey Optimizer.

## Potenziali informazioni

Di seguito sono riportati alcuni esempi dei tipi di approfondimenti che l’area di lavoro del Percorso può fornire. Puoi scegliere se queste informazioni si basano su tutte le persone nella visualizzazione dati o su tutte le persone che hanno iniziato il percorso.

**Abbandono**

* Numero e percentuale di persone che hanno completato il percorso (arrivate al nodo finale)

* Numero e percentuale di persone arrivate a un determinato punto (nodo) del percorso

* Passaggio più comune successivo o precedente a un determinato punto (nodo) del percorso

**Fallout**

* Punti (nodi) del percorso in cui le persone più comunemente abbandonano il percorso

**Altre**

* Dati aggiuntivi per qualsiasi nodo del percorso (aggiungendo una dimensione di raggruppamento per il nodo)


## Scegli tra l’area di lavoro del Percorso e le visualizzazioni Abbandono

Le visualizzazioni dell&#39;area di lavoro percorso sono simili alle [Visualizzazioni di abbandono](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), in quanto entrambe le visualizzazioni mostrano dove le persone hanno lasciato (abbandonato) e continuato (proseguito) attraverso una sequenza di pagine predefinita.

Tuttavia, ci sono importanti differenze.

### Comprendere le differenze

La tabella seguente mostra i tipi di analisi supportati nella visualizzazione Area di lavoro del Percorso e nella visualizzazione Abbandono:

| Funzione | Visualizzazione area di lavoro percorso | Visualizzazione del fallout |
|---------|----------|---------|
| Percorsi lineari | Sì | Sì |
| Percorsi non lineari con più punti di ingresso e percorsi | Sì | No |
| percorsi Adobe Journey Optimizer | Sì | No |
| Metrica principale | Qualsiasi metrica, comprese quelle calcolate | Può utilizzare solo la metrica Sessione o Utente |
| Metrica secondaria | Sì<p>Qualsiasi metrica, comprese quelle calcolate</p> | No |
| Confronta filtri | No | Sì<p>Confronta un [numero illimitato di filtri](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md#compare-filters-in-fallout)</p> |

### Scegli la visualizzazione da utilizzare

Prima di scegliere se utilizzare l&#39;area di lavoro del Percorso o Fallout, assicurati di [comprendere le differenze tra i due](#understand-the-differences).

Se l&#39;analisi dell&#39;abbandono coinvolge solo un percorso lineare con un solo inizio e una sola fine noti, è consigliabile utilizzare una [Visualizzazione di abbandono](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) come opzione più semplice per questi percorsi di utenti più semplici.

L’area di lavoro percorso è essenziale per l’analisi dell’abbandono che coinvolge percorsi con più punti di ingresso e percorsi o per l’analisi dei percorsi creati in Journey Optimizer.

## Analizzare percorsi Journey Optimizer

>[!NOTE]
>
>Se la tua organizzazione non ha accesso a Journey Optimizer, puoi comunque [generare analisi nell&#39;area di lavoro del Percorso](#build-analyses-in-customer-journey-analytics).

L’analisi dei percorsi Journey Optimizer nell’area di lavoro del Percorso fornisce informazioni approfondite e fruibili sul modo in cui le persone interagiscono con un percorso.

Quando si analizza un percorso Journey Optimizer nell&#39;area di lavoro del Percorso, il percorso viene visualizzato con l&#39;ordine, la sequenza e la struttura di Journey Optimizer. Se è possibile apportare modifiche a un percorso nell&#39;area di lavoro del Percorso, [le modifiche non verranno più sincronizzate da Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas).

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

Inoltre, le modifiche apportate a un percorso in Journey Optimizer vengono sincronizzate con l’area di lavoro del Percorso solo se il percorso rimane invariato nell’area di lavoro del Percorso. Dopo aver modificato un percorso nell&#39;area di lavoro del Percorso, tutte le modifiche apportate al percorso in Journey Optimizer non vengono riportate nell&#39;area di lavoro del Percorso. Per visualizzare le modifiche nell&#39;area di lavoro del Percorso, è possibile eliminare e [ricreare il percorso nell&#39;area di lavoro del Percorso](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

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

Dopo aver modificato un percorso Journey Optimizer nell’area di lavoro del Percorso, la funzionalità potrebbe cambiare per le seguenti funzioni, a seconda delle modifiche:

* I valori visualizzati nel campo [!UICONTROL **Tipo di nodo**] cambiano.

* Le opzioni disponibili nel campo a discesa [!UICONTROL **Impostazioni freccia**] cambiano.

Per ulteriori informazioni su questi campi, vedere [Configurare le impostazioni](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

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
