---
description: Utilizza la visualizzazione di flusso in un progetto Workspace.
title: Configurare una visualizzazione di flusso
feature: Visualizations
role: User, Admin
source-git-commit: 62243ccd3d0f4b6ef09e57d850c0d7eb03f879e0
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 40%

---

# Configurare una visualizzazione di flusso

>[!NOTE]
>
>Questa nuova versione del [!UICONTROL Flow] la visualizzazione è attualmente in fase di test. Sarà rilasciato il 15 giugno 2022 .

La visualizzazione Flusso aggiornata ti consente di comprendere il percorso che deriva da o precede un evento di conversione specifico sul tuo sito web o sulla tua app. Traccia un percorso attraverso le dimensioni (e gli elementi dimensionali) o le metriche. Flusso consente di configurare l’inizio o la fine del percorso desiderato o di analizzare tutti i percorsi che passano attraverso una dimensione o un elemento dimensionale.

Il nuovo [!UICONTROL flow] esperienza migliora il flusso di lavoro in diversi modi:

* Ora puoi scegliere di iniziare o terminare il percorso con la combinazione di una metrica e una dimensione di percorso.
* Contiene [!UICONTROL Advanced Settings] per personalizzare ulteriormente [!UICONTROL flow].
* Il nuovo pulsante &quot;Genera&quot; consente di risparmiare tempo nell’analisi consentendo di configurare il percorso in una sola volta, quindi di eseguire una query e quindi di creare automaticamente più colonne e nodi contemporaneamente &#x200B;.

![nuova interfaccia utente Flusso](assets/new-flow.png)

## Passaggi di configurazione {#configure}

1. Per iniziare a creare un diagramma di flusso, aggiungi un pannello vuoto al progetto e fai clic sull’icona delle visualizzazioni nella barra a sinistra. Quindi trascina la visualizzazione Flusso nel pannello . Oppure trascina la [!UICONTROL Flow] visualizzazione in un progetto esistente.

1. Ancoraggio della visualizzazione Flusso tramite una delle tre opzioni seguenti:

   * [!UICONTROL Starts with] (metriche, dimensioni o elementi), oppure
   * [!UICONTROL Contains] (dimensioni o elementi), oppure
   * [!UICONTROL Ends with] (metriche, dimensioni o elementi)

   Ogni categoria è visualizzata come una “zona di rilascio”. Trascina gli elementi dall’elenco delle dimensioni o delle metriche nella zona di rilascio desiderata.

   Ad esempio, supponiamo che desideri tracciare tutto ciò che porta a un evento di pagamento. Trascina una dimensione o una metrica relativa al checkout (ad esempio [!UICONTROL Order exists]) nel **[!UICONTROL Ends with]** zona di rilascio.

1. Se scegli una metrica, devi anche fornire un [!UICONTROL Pathing Dimension], come mostrato qui, che utilizzerai per creare il percorso. Il valore predefinito è [!UICONTROL Page].

   ![dimensione del percorso](assets/pathing-dim.png)

   >[!IMPORTANT]
   >
   >Le metriche calcolate non possono essere rilasciate nel  **[!UICONTROL Starts with]** o **[!UICONTROL Ends with]** zone di rilascio.

1. (Facoltativo) Fai clic su **[!UICONTROL Show Advanced Settings]** per configurare le impostazioni avanzate:

   ![impostazioni avanzate](assets/adv-settings.png)

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Include repeat instances]** | Le visualizzazioni di Flusso si basano su istanze di una dimensione. Questa impostazione offre la possibilità di includere o escludere istanze ripetute, ad esempio i ricaricamenti delle pagine. Tuttavia, le ripetizioni non possono essere rimosse dalle visualizzazioni Flusso che includono dimensioni con più valori, come listVars, listProps, s.product, eVars di merchandising, ecc. Impostazione predefinita = non selezionata. |
   | **[!UICONTROL Wrap labels]** | Di norma, le etichette degli elementi di Flusso vengono troncate per risparmiare spazio sullo schermo, ma selezionando questa casella puoi rendere visibile l’intera etichetta.  Impostazione predefinita = non selezionata. |
   | **[!UICONTROL Limit to first/last occurrence]** | Limita i percorsi a quelli che iniziano/terminano con la prima/ultima occorrenza di una dimensione/elemento/metrica. |
   | **[!UICONTROL Number of Columns]** | Determina il numero di colonne desiderato nel diagramma di flusso. |
   | **[!UICONTROL Items expanded per Column]** | Quanti elementi desideri inserire in ogni colonna. |
   | **[!UICONTROL Flow Container]** | <ul><li>Visita</li><li>Visitatore</li></ul> Consente di passare da Visita a Visitatore per analizzare il percorso dei visitatori. Queste impostazioni consentono di comprendere il coinvolgimento dei visitatori a livello dei singoli visitatori (attraverso più visite) o di limitare l’analisi a una singola visita. |

1. Fai clic su **[!UICONTROL Build]**.

## Visualizza e modifica l’output Flusso {#output}

![uscita di flusso](assets/flow-output.png)

Nella parte superiore del diagramma viene visualizzato un riepilogo della configurazione del flusso. I percorsi nel diagramma sono proporzionali. I percorsi con maggiore attività sono più spessi.

Per approfondire ulteriormente i dati, hai a disposizione diverse opzioni:

* Il diagramma di flusso è interattivo. Passa il cursore del mouse sul diagramma per cambiare i dettagli visualizzati.

* Quando fai clic su un nodo nel diagramma, vengono visualizzati i dettagli per tale nodo. Fai di nuovo clic sul nodo per comprimerlo.

   ![node-details](assets/node-details.png)

* Puoi filtrare una colonna per visualizzare solo alcuni risultati, ad esempio includere ed escludere, specificare criteri, ecc.

* Fai clic sul segno più (+) a sinistra per espandere una colonna.

* Utilizza le opzioni di clic con il pulsante destro del mouse illustrate di seguito per personalizzare ulteriormente l’output.

* Fai clic sull’icona a forma di matita accanto al riepilogo della configurazione per modificare ulteriormente il flusso o ricrearlo con opzioni diverse.

* Puoi anche esportare e analizzare ulteriormente il diagramma di flusso come parte del file .CSV di un progetto, da **[!UICONTROL Project]** (Progetto) > **[!UICONTROL Download CSV]** (Scarica CSV).


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

>[!MORELIKETHIS]
>[Panoramica del flusso](/help/analysis-workspace/visualizations/c-flow/flow.md)


