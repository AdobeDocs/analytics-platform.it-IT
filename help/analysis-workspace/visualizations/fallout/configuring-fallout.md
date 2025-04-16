---
description: Scopri come specificare i punti di contatto per creare una sequenza di abbandono multidimensionale.
title: Configurare una visualizzazione dell’abbandono
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 770320a0b16d26e0755203a3524b000db30cac82
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 35%

---

# Configurare una visualizzazione dell’abbandono {#configure-fallout-visualization}


Puoi specificare i punti di contatto per creare una sequenza di abbandono multidimensionale. In genere, un punto di contatto è una pagina del sito. Tuttavia, i punti di contatto non sono limitati alle pagine. Ad esempio, puoi aggiungere eventi, come unità di misura, persone univoche e visite di ritorno. Puoi anche aggiungere dimensioni, ad esempio una categoria, un tipo di browser e un termine di ricerca interna.

Puoi perfino aggiungere segmenti all’interno di un punto di contatto. Ad esempio, potrebbe essere utile confrontare segmenti, come gli utenti di iOS e Android™. Trascina i segmenti desiderati nella parte superiore della sezione Abbandono per aggiungere al rapporto le informazioni su tali segmenti. Se desideri visualizzare solo tali segmenti, puoi rimuovere la linea di base Tutte le visite.

Non esiste alcun limite al numero di passaggi che è possibile aggiungere o al numero di dimensioni utilizzate.

Puoi eseguire la tracciatura di percorsi per dimensioni, metriche e segmenti. Ad esempio, supponiamo che qualcuno stia guardando &quot;scarpe, camicie&quot; su una pagina e che nella pagina successiva guardi &quot;camicie, calze&quot;. il prossimo rapporto di flusso dei prodotti da “scarpe” sarà “camicie” e “calze” e NON “camicie”.

## Utilizzo

1. Aggiungi una visualizzazione ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Fallout]**. Vedi [Aggiungere una visualizzazione a un pannello](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Trascina una pagina, ad esempio Home, dalla dimensione Pagina al menu a discesa *Aggiungi punto di contatto*.

   ![La home page dalla dimensione Home page è stata trascinata nel campo Aggiungi punto di contatto.](assets/fallout-drag.png)

   Passa il puntatore del mouse su un punto di contatto per vedere l’abbandono e altre informazioni su tale livello, come il nome del punto di contatto e il numero di persone a quel punto. E osserva il tasso di successo per quel punto di contatto (nonché confronta il tasso di successo con altri punti di contatto).

   I numeri cerchiati nella porzione grigia della barra mostrano l’abbandono tra i punti di contatto (non l’abbandono complessivo per quel punto). **[!UICONTROL Touchpoint %]** mostra l&#39;abbandono riuscito dal passaggio precedente al passaggio corrente nel report sull&#39;abbandono.

   Puoi anche aggiungere una sola pagina al rapporto di abbandono, invece che l’intera dimensione. Fare clic sulla freccia destra ![ChevronRight](/help/assets/icons/ChevronRight.svg) nella dimensione pagina per scegliere una pagina specifica da aggiungere al report Abbandono.

1. Continua ad aggiungere punti di contatto fino a completare la sequenza.

   Puoi **combinare più punti di contatto** trascinando uno o più componenti aggiuntivi su un punto di contatto.

   >[!NOTE]
   >
   >Per unire più segmenti si usa l’operatore AND; per unire più elementi, ad esempio elementi dimensione, si usa l’operatore OR.

   ![Pagina:CamerRoll o Pagina: punti di contatto fotocamera evidenziati.](assets/fallout-or.png)

1. Puoi anche **vincolare singoli punti di contatto all&#39;evento successivo** (anziché *alla fine*) all&#39;interno del percorso. Sotto ogni punto di contatto è presente un selettore con le opzioni **[!UICONTROL Eventual path]** e **[!UICONTROL Next event]**, come illustrato di seguito:

   ![La vista Tutte le visite mostra l&#39;opzione Percorso finale evidenziata. ](assets/fallout-nexthit.png)

   | Opzione | Descrizione |
   |---|---|
   | **[!UICONTROL Eventual path]** (predefinito) | Vengono conteggiate le persone che *alla fine* approderanno sulla pagina successiva del percorso, ma non necessariamente sull&#39;evento successivo. |
   | **[!UICONTROL Next event]** | Vengono conteggiate le persone che arriveranno alla pagina successiva del percorso nel prossimo evento. |


## Impostazioni {#settings}

>[!CONTEXTUALHELP]
>id="workspace_fallout_container"
>title="Contenitore Abbandono"
>abstract="Seleziona un contenitore per analizzare i percorsi. Questa selezione consente di comprendere il coinvolgimento e vincola l’analisi al contenitore selezionato."

Come parte della visualizzazione, sono disponibili impostazioni specifiche.

| Contenitore Abbandono | Descrizione |
|--- |--- |
| **[!UICONTROL Session]** o **[!UICONTROL Person]** | Passa da [!UICONTROL Session] a [!UICONTROL Person] per analizzare il percorso della persona. Il valore predefinito è [!UICONTROL Person]. Queste impostazioni consentono di comprendere il coinvolgimento di persone a livello di persona singola (attraverso più sessioni) o di limitare l’analisi a una singola sessione. |


## Menu di scelta rapida

Come parte della visualizzazione, sono disponibili opzioni di menu di scelta rapida specifiche.

![Opzioni di abbandono](assets/fallout-options.png)

| Opzione | Descrizione |
|--- |--- |
| **[!UICONTROL Trend touchpoint]** | I dati di tendenza di un punto di contatto sono rappresentati in un grafico a linee, con alcuni dati di rilevamento anomalie pregenerati. |
| **[!UICONTROL Trend touchpoint (%)]** | Visualizza la tendenza della percentuale di abbandono totale. |
| **[!UICONTROL Trend all touchpoints (%)]** | Genera tendenze su tutte le percentuali dei punti di contatto nell&#39;abbandono (tranne **[!UICONTROL All People]**, se incluso) nello stesso grafico. |
| **[!UICONTROL Break down fallthrough at this touchpoint]** | Puoi vedere cosa hanno fatto le persone tra due punti di contatto (questo e quello successivo) se hanno continuato fino al punto di contatto successivo. Viene creata una tabella a forma libera in cui sono riportate le dimensioni. Puoi sostituire le dimensioni e altri elementi della tabella. |
| **[!UICONTROL Break down fallout at this touchpoint]** | Puoi vedere cosa hanno fatto, immediatamente dopo il passaggio selezionato, i visitatori che hanno abbandonato. |
| **[!UICONTROL Create segment from touchpoint]** | Crea un nuovo segmento dal punto di contatto selezionato. |

>[!MORELIKETHIS]
>
>[Aggiungi una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Impostazioni visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu di scelta rapida visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

