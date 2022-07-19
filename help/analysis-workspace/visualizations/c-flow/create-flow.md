---
description: Utilizza la visualizzazione di flusso in un progetto Workspace.
title: Configurare una visualizzazione di flusso
feature: Visualizations
role: User, Admin
exl-id: c2fdcc96-81ac-4d3b-b255-ff805b6ff0ea
source-git-commit: 702d03b95b6689e1441fbdd8b2ef3a5a3fcfbad0
workflow-type: ht
source-wordcount: '1258'
ht-degree: 100%

---

# Configurare una visualizzazione di flusso

La visualizzazione Flusso aggiornata ti consente di comprendere il percorso che deriva da o precede un evento di conversione specifico sul tuo sito web o sulla tua app. Traccia un percorso attraverso le dimensioni (e gli elementi dimensionali) o le metriche. Flusso consente di configurare l’inizio o la fine del percorso desiderato o di analizzare tutti i percorsi che passano attraverso una dimensione o un elemento dimensionale.

La nuova esperienza di [!UICONTROL flow] migliora il flusso di lavoro in diversi modi:

* Ora puoi scegliere di iniziare o terminare il percorso con la combinazione di una metrica e una dimensione di percorso.
* Contiene [!UICONTROL Advanced Settings] per personalizzare ulteriormente il [!UICONTROL flow].
* Il nuovo pulsante “Genera” consente di risparmiare tempo nell’analisi permettendoti di configurare il percorso in una sola volta, quindi di eseguire una query e di creare automaticamente più colonne e nodi contemporaneamente.

![nuova interfaccia utente di Flusso](assets/new-flow.png)

## Passaggi di configurazione {#configure}

1. Per iniziare a creare un diagramma di flusso, aggiungi un pannello vuoto al progetto e fai clic sull’icona delle visualizzazioni nella barra a sinistra. Quindi trascina la visualizzazione Flusso nel pannello oppure trascina la visualizzazione [!UICONTROL Flow] in un progetto esistente.

1. Aggancia la visualizzazione Flusso tramite una delle tre opzioni seguenti:

   * [!UICONTROL Starts with] (metriche, dimensioni o elementi), oppure
   * [!UICONTROL Contains] (dimensioni o elementi), oppure
   * [!UICONTROL Ends with] (metriche, dimensioni o elementi)

   Ogni categoria è visualizzata come una “zona di rilascio”. Puoi popolare la zona di rilascio in tre modi:

   * Utilizza il menu a discesa per selezionare metriche o dimensioni.
   * Trascina gli elementi dall’elenco delle dimensioni o delle metriche.
   * Utilizza la ricerca per trovare le metriche o la dimensione che stai cercando.

   Ad esempio, supponiamo che tu desideri tracciare tutto ciò che porta a un evento di pagamento. Trascinerai una dimensione o una metrica relativa al pagamento (ad esempio [!UICONTROL Order exists]) nella zona di rilascio **[!UICONTROL Ends with]**.

1. Se scegli una metrica, devi anche fornire una [!UICONTROL Pathing Dimension], come mostrato qui, che utilizzerai per creare il percorso. Il valore predefinito è [!UICONTROL Page].

   ![dimensione del percorso](assets/pathing-dim.png)

   >[!IMPORTANT]
   >
   >Le metriche calcolate non possono essere rilasciate nelle zone di rilascio **[!UICONTROL Starts with]** o **[!UICONTROL Ends with]**.

1. (Facoltativo) Fai clic su **[!UICONTROL Show Advanced Settings]** per configurare le impostazioni avanzate:

   ![impostazioni avanzate](assets/adv-settings.png)

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Wrap labels]** | Di norma, le etichette degli elementi di Flusso vengono troncate per risparmiare spazio sullo schermo, ma selezionando questa casella puoi rendere visibile l’intera etichetta.  Impostazione predefinita = non selezionata. |
   | **[!UICONTROL Include repeat instances]** | Le visualizzazioni di Flusso si basano su istanze di una dimensione. Questa impostazione offre la possibilità di includere o escludere istanze ripetute, ad esempio i ricaricamenti delle pagine. Tuttavia, le ripetizioni non possono essere rimosse dalle visualizzazioni Flusso che includono dimensioni con più valori, come listVars, listProp, s.product, eVar di merchandising, ecc. Impostazione predefinita = non selezionata. |
   | **[!UICONTROL Limit to first/last occurrence]** | Limita i percorsi a quelli che iniziano/terminano con la prima/ultima occorrenza di una dimensione/elemento/metrica. Per una spiegazione più dettagliata, consulta la sezione sottostante intitolata “Scenario di esempio per “limit to first/last occurrence” (limita alla prima/ultima occorrenza)”. |
   | **[!UICONTROL Number of Columns]** | Determina il numero di colonne desiderato nel diagramma di Flusso. |
   | **[!UICONTROL Items expanded per Column]** | Il numero di elementi che desideri inserire in ogni colonna. |
   | **[!UICONTROL Flow Container]** | <ul><li>Visita</li><li>Visitatore</li></ul> Consente di passare da Visita a Visitatore per analizzare il percorso dei visitatori. Queste impostazioni consentono di comprendere il coinvolgimento dei visitatori a livello dei singoli visitatori (attraverso più visite) o di limitare l’analisi a una singola visita. |

1. Fai clic su **[!UICONTROL Build]**.

## Visualizzare e modificare l’output di Flusso {#output}

![output di flusso](assets/flow-output.png)

Nella parte superiore del diagramma viene visualizzato un riepilogo della configurazione di Flusso. I percorsi nel diagramma sono proporzionali. I percorsi con maggiore attività sono più spessi.

Per approfondire ulteriormente i dati, hai a disposizione diverse opzioni:

* Il diagramma di flusso è interattivo. Passa il cursore del mouse sul diagramma per cambiare i dettagli visualizzati.

* Quando fai clic su un nodo nel diagramma, vengono visualizzati i dettagli per tale nodo. Fai di nuovo clic sul nodo per chiuderlo.

   ![dettagli-nodo](assets/node-details.png)

* Puoi filtrare una colonna per visualizzare solo alcuni risultati, ad esempio puoi includere ed escludere, specificare criteri, ecc.

* Fai clic sul segno più (+) a sinistra per espandere una colonna.

* Utilizza le opzioni di clic con il pulsante destro del mouse illustrate di seguito per personalizzare ulteriormente l’output.

* Fai clic sull’icona a forma di matita accanto al riepilogo di configurazione per modificare ulteriormente il flusso o ricrearlo con opzioni diverse.

* Puoi anche esportare e analizzare ulteriormente il diagramma di flusso come parte del file .CSV di un progetto, da **[!UICONTROL Project]** (Progetto) > **[!UICONTROL Download CSV]** (Scarica CSV).

## Filtro

Sopra ogni colonna viene visualizzato un filtro al passaggio del mouse. Facendo clic sul filtro, si ottiene la stessa finestra di dialogo del filtro attualmente presente nella tabella a forma libera. Questo filtro funziona come nella tabella a forma libera.

* Utilizza le impostazioni avanzate per includere o escludere determinati criteri con il nostro elenco di operatori.
* Dopo aver filtrato un elemento dall’elenco, quella colonna specifica rifletterà il filtro. Il filtro riduce la colonna di modo che mostri solo l’elemento consentito nel filtro, oppure rimuove tutti gli elementi eccetto quello desiderato nel filtro.
* Tutte le colonne upstream e downstream dovrebbero persistere, purché sia presente un flusso di dati nei nodi rimanenti.
* Una volta applicato, l’icona del filtro viene visualizzata in blu sopra la colonna che sta filtrando.
* Per rimuovere un filtro, fai clic sull’icona di filtro per aprire il menu dei filtri. Rimuovi i filtri applicati e fai clic su **[!UICONTROL Save]**. Il flusso dovrebbe tornare allo stato precedente non filtrato.

## Opzioni di clic con il pulsante destro {#right-click}

| Opzione | Descrizione |
|--- |--- |
| [!UICONTROL Focus on this node] | Rende attivo il nodo selezionato. Il nodo attivo è visualizzato al centro del diagramma di flusso. |
| [!UICONTROL Start Over] | Si torna al generatore di diagrammi a forma libera dove è possibile generare un nuovo diagramma di flusso. |
| [!UICONTROL Create Segment from this point in flow] | Crea un segmento. Viene aperto il Generatore di segmenti, dove è possibile configurare il nuovo segmento. |
| [!UICONTROL Breakdown] | Suddivide il nodo per dimensioni, metriche o ora. |
| [!UICONTROL Trend] | Crea un diagramma di tendenza per il nodo. |
| [!UICONTROL Expand entire column] | Espande una colonna per mostrare tutti i nodi. Per impostazione predefinita, vengono visualizzati solo i primi cinque nodi. |
| [!UICONTROL Collapse entire column] | Nasconde tutti i nodi di una colonna. |
| [!UICONTROL Exclude Item]/[!UICONTROL Restore Excluded Items] | Rimuove un nodo specifico dalla colonna e lo crea automaticamente come filtro nella parte superiore della colonna. Per ripristinare l’elemento escluso, fai di nuovo clic con il pulsante destro del mouse e seleziona **[!UICONTROL Restore Excluded Item]**. Puoi anche aprire il filtro nella parte superiore della colonna e rimuovere la casella con l’elemento appena escluso. |

## Scenario di esempio per “limit to first/last occurrence” (limita alla prima/ultima occorrenza)

Quando utilizzi questa opzione, tieni presente che:

* **[!UICONTROL Limit to first/last occurrence]** conta solo la prima/ultima occorrenza della serie. Tutte le altre occorrenze del criterio **[!UICONTROL Starts with]** o **[!UICONTROL Ends with]** vengono ignorate.
* Se utilizzata con un flusso **[!UICONTROL Starts with]**, è inclusa solo la prima occorrenza corrispondente ai criteri di inizio.
* Se utilizzata con un flusso **[!UICONTROL Ends with]**, verrà inclusa solo l’ultima occorrenza corrispondente ai criteri di fine.
* La serie utilizzata varia in base al contenitore. Se utilizzi il contenitore **[!UICONTROL Visit]**, la serie di hit corrisponderà alla sessione. Se utilizzi il contenitore **[!UICONTROL Visitor]**, la serie di hit sarà costituita da tutti gli hit di un dato utente nell’intervallo di date specificato.
* Quando si utilizza una metrica o un elemento dimensionale nei campi “Inizia con” o “Termina con”, l’opzione **[!UICONTROL Limit to first/last occurrence]** può essere configurata nelle impostazioni avanzate.

Serie di hit di esempio:

Home > Prodotti > Aggiungi al carrello > Prodotti > Aggiungi al carrello > Fatturazione > Conferma d’ordine

### Considerare un’analisi di flusso utilizzando le seguenti impostazioni:

* Inizia con[!UICONTROL  Add to cart] (elemento dimensionale)
* Dimensione del percorso [!UICONTROL Page]
* Contenitore [!UICONTROL Visit]

Se “Limit to first/last occurrence” (Limita alla prima/ultima occorrenza) è disabilitato, questa singola serie di hit conterà due occorrenze di “Aggiungi al carrello”.
Output di flusso previsto:
“Aggiungi al carrello” (2) —> “Prodotti” (1)
-> “Fatturazione” (1)

Tuttavia, se “Limit to first/last occurrence” (Limita alla prima/ultima occorrenza) è abilitato, nell’analisi verrà inclusa solo la prima occorrenza di “Aggiungi al carrello”.
Output di flusso previsto: “Aggiungi al carrello” (1) —> “Prodotti” (1)

### Considera la stessa serie di hit, ma utilizzando le seguenti impostazioni:

* Termina con [!UICONTROL Add to cart] (elemento dimensionale)
* Dimensione del percorso [!UICONTROL Page]
* Contenitore [!UICONTROL Visit]

Se **[!UICONTROL Limit to first/last occurrence]** è *disattivato*, questa singola serie di hit conterà due occorrenze di “Aggiungi al carrello”.
Flusso previsto: “Prodotti” (2) &lt;— “Aggiungi al carrello” (2)

Tuttavia, se **[!UICONTROL Limit to first/last occurrence]** è *abilitato*, nell’analisi verrà inclusa solo l’ultima occorrenza di [!UICONTROL Add to cart].
Flusso previsto: “Prodotti” (1) &lt;— “Aggiungi al carrello” (1)
