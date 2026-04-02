---
description: Scopri come configurare e specificare i punti di contatto per creare una sequenza di abbandono multidimensionale.
title: Configurare Una Visualizzazione Abbandono
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 295e4c9b3b9dff5ba650456c3f62817b30fe1e3d
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 12%

---

# Configurare una visualizzazione dell’abbandono {#configure-fallout-visualization}


Puoi specificare **punti di contatto** per creare una sequenza di abbandono multidimensionale. In molti casi, un punto di contatto è una pagina del sito. Tuttavia, i punti di contatto non sono limitati alle pagine. Ad esempio, puoi aggiungere eventi, come unità di misura, persone univoche e visite di ritorno. Puoi anche aggiungere dimensioni, come una categoria, un tipo di browser o un termine di ricerca interno.

Puoi anche aggiungere segmenti all’interno di un punto di contatto. Ad esempio, potrebbe essere utile confrontare segmenti, come gli utenti di iOS e Android. Trascina i segmenti desiderati nella parte superiore dell’abbandono per aggiungere al rapporto le informazioni su di essi. Se si desidera visualizzare solo tali segmenti, è possibile rimuovere la linea di base Tutte le persone.

Le visualizzazioni di fallout non hanno limiti sul numero di punti di contatto che puoi aggiungere o sul numero di componenti che puoi utilizzare.

Puoi eseguire la tracciatura di percorsi per dimensioni, metriche e segmenti. Si supponga, ad esempio, che un utente stia guardando `shoes, shirt` in una pagina e che nella pagina successiva guardi `shirt, socks`. il prossimo rapporto di flusso dei prodotti da “scarpe” sarà “camicie” e “calze” e NON “camicie”.

## Utilizzo

1. Aggiungi una visualizzazione ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Fallout]**. Consulta [Aggiungere una visualizzazione a un pannello](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Trascina un componente nel menu a discesa **[!UICONTROL Aggiungi punto di contatto]**.

   >[!TIP]
   >
   >Puoi aggiungere una singola pagina al rapporto di abbandono, anziché l’intera dimensione. Fare clic sulla freccia destra ![ChevronRight](/help/assets/icons/ChevronRight.svg) nella dimensione pagina per scegliere una pagina specifica, ad esempio **[!UICONTROL home]**, da aggiungere al report Abbandono.

   ![La home page dalla dimensione Home page è stata trascinata nel campo Aggiungi punto di contatto.](assets/fallout-drag.png)

1. Continua ad aggiungere punti di contatto fino al completamento della sequenza.

   I numeri cerchiati nella porzione grigia della barra mostrano l’abbandono tra i punti di contatto (non l’abbandono complessivo per quel punto). I numeri cerchiati nella parte verde della barra mostrano il passaggio riuscito dal punto di contatto precedente al punto di contatto corrente.

   ![Visualizzazione Abbandono](assets/fallout-visualization.png)

   Quando aggiungi punti di contatto, puoi effettuare una delle seguenti operazioni:

   * Combina più componenti trascinando uno o più componenti aggiuntivi su un singolo punto di contatto.

     >[!NOTE]
     >
     >Per unire più segmenti si usa l’operatore AND; per unire più elementi, ad esempio elementi dimensione, si usa l’operatore OR.

   * Riordina i punti di contatto trascinandoli a un livello diverso all’interno della gerarchia di abbandono.

   * Combinare due punti di contatto trascinandone uno su un altro. Elimina il punto di contatto quando viene visualizzata la parola **[!UICONTROL Combina]**.

   * Vincola singoli punti di contatto all&#39;evento successivo (anziché *alla fine*) all&#39;interno del percorso. Sotto ogni punto di contatto è presente un selettore con le opzioni **[!UICONTROL Percorso finale]** e **[!UICONTROL Evento successivo]**, come illustrato di seguito:

     | Opzione | Descrizione |
     |---|---|
     | **[!UICONTROL Percorso finale]** (predefinito) | Vengono conteggiate le persone che *alla fine* approderanno sulla pagina successiva del percorso, ma non necessariamente sull&#39;evento successivo. |
     | **[!UICONTROL Prossimo evento]** | Vengono conteggiate le persone che arriveranno alla pagina successiva del percorso nel prossimo evento. |

   * Passa il puntatore del mouse su un punto di contatto per visualizzare l’abbandono e altre informazioni su tale livello. Le informazioni includono il nome del punto di contatto, il conteggio delle persone e la percentuale di successo. Puoi anche confrontare il tasso di successo con altri punti di contatto.

## Impostazioni {#settings}

>[!CONTEXTUALHELP]
>id="workspace_fallout_container"
>title="Contenitore Fallout"
>abstract="Seleziona un contenitore per analizzare il percorso. Questa selezione ti consente di comprendere il tipo di coinvolgimento e vincola l’analisi al contenitore selezionato."

Come parte della visualizzazione, sono disponibili impostazioni specifiche.

| Contenitore Fallout | Descrizione |
|--- |--- |
| **[!UICONTROL Sessione]** o **[!UICONTROL Persona]** | Passa da [!UICONTROL Sessione] a [!UICONTROL Persona] per analizzare il percorso della persona. Il valore predefinito è [!UICONTROL Persona]. Queste impostazioni consentono di comprendere il coinvolgimento di persone a livello di persona singola (attraverso più sessioni) o di limitare l’analisi a una singola sessione. |


## Menu di scelta rapida

Come parte della visualizzazione, sono disponibili opzioni di menu di scelta rapida specifiche.

### Accedere al menu di scelta rapida

È possibile accedere al menu di scelta rapida in uno dei modi seguenti:

* Passa il puntatore del mouse su un punto di contatto nella visualizzazione, quindi seleziona **[!UICONTROL Fai clic per analizzare]**.

  ![Accedi al menu di scelta rapida dal passaggio del mouse](assets/fallout-tooltip-analyze.png)

* Fai clic con il pulsante destro del mouse su un punto di contatto nella visualizzazione.

  ![Opzioni di abbandono](assets/fallout-options.png)

### Opzioni del menu di scelta rapida

Sono disponibili le seguenti opzioni del menu di scelta rapida:

| Opzione | Descrizione |
|--- |--- |
| **[!UICONTROL Punto di contatto tendenza]** | Vedi i dati di tendenza per un punto di contatto in un grafico a linee, con alcuni dati predefiniti di rilevamento delle anomalie. |
| **[!UICONTROL Punto di contatto tendenza (%)]** | Genera tendenze sulla percentuale di abbandono totale. |
| **[!UICONTROL Tendenza di tutti i punti di contatto (%)]** | Genera tendenze su tutte le percentuali dei punti di contatto nell&#39;abbandono (tranne **[!UICONTROL Tutte le persone]**, se incluso) nello stesso grafico. |
| **[!UICONTROL Suddividi fallthrough in questo punto di contatto]** | Puoi vedere cosa hanno fatto le persone tra due punti di contatto (questo e quello successivo) se hanno continuato fino al punto di contatto successivo. In questo modo viene creata una tabella a forma libera che mostra le dimensioni. Potete sostituire le quote e altri elementi della tabella. Ad esempio, una tabella etichettata **[!UICONTROL Fallthrough: All People > Page è uguale a qualsiasi di home]** e contiene **[!UICONTROL Page]** come dimensione e **[!UICONTROL People]** segmentato dal [segmento rapido solo progetto](/help/components/segments/seg-quick.md) **[!UICONTROL Fallthrough: All People > Page è uguale a qualsiasi di home]** come metrica. Ispeziona il segmento per capire come viene determinato il segmento di fallthrough. |
| **[!UICONTROL Suddividere l&#39;abbandono in questo punto di contatto]** | Puoi vedere cosa hanno fatto, immediatamente dopo il passaggio selezionato, gli utenti che non hanno partecipato al passaggio in funnel. In questo modo viene creata una tabella a forma libera che mostra le dimensioni. Potete sostituire le quote e altri elementi della tabella. Ad esempio, una tabella etichettata **[!UICONTROL Abbandono: Persone > Pagina è uguale a qualsiasi di home]** e contiene **[!UICONTROL Pagina]** come dimensione e **[!UICONTROL Persone]** segmentate dal [segmento rapido solo progetto](/help/components/segments/seg-quick.md) **[!UICONTROL Abbandono: tutti i visitatori > Pagina è uguale a qualsiasi di home]** segmento come metrica. Ispeziona il segmento per capire come viene determinato il segmento di abbandono. |
| **[!UICONTROL Crea segmento da punto di contatto]** | Crea un nuovo segmento dal punto di contatto selezionato. |

>[!MORELIKETHIS]
>
>[Aggiungere una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Impostazioni di visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu di scelta rapida della visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

