---
description: Un pannello è una raccolta di tabelle e visualizzazioni
title: Panoramica dei pannelli
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 5%

---

# Panoramica dei pannelli

Un [!UICONTROL panel] è un insieme di tabelle e visualizzazioni. Puoi accedere ai pannelli dall’icona in alto a sinistra in Workspace o da un [pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md). I pannelli sono utili quando desideri organizzare i progetti in base a periodi di tempo, visualizzazioni dati o casi di utilizzo dell’analisi. In Analysis Workspace sono disponibili i seguenti tipi di pannelli:

| Nome pannello | Descrizione |
| --- | --- |
| [Pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md) | Scegli tra i pannelli e le visualizzazioni disponibili per avviare l’analisi. |
| [Pannello Quick Insights](quickinsight.md) | Crea rapidamente una tabella a forma libera e una relativa visualizzazione per analizzare e individuare più rapidamente le informazioni. |
| [Pannello Attribution](attribution.md) | Confronta e visualizza rapidamente qualsiasi numero di modelli di attribuzione utilizzando qualsiasi dimensione e metrica di conversione. |
| [Pannello Freeform](freeform-panel.md) | Esegui confronti illimitati e suddivisioni, quindi aggiungi visualizzazioni per raccontare una storia ricca di dati. |

![](assets/panel-overview.png)

[!UICONTROL Quick Insights],  [!UICONTROL Blank] e  [!UICONTROL Freeform] i pannelli sono luoghi ideali per avviare l’analisi e si prestano  [!UICONTROL Attribution IQ] ad analisi più avanzate. Nei progetti è disponibile un pulsante `"+"` che consente di aggiungere pannelli vuoti in qualsiasi momento.

Il pannello iniziale predefinito è il pannello [!UICONTROL Freeform], ma puoi impostare come predefinito anche il pannello [vuoto](/help/analysis-workspace/c-panels/blank-panel.md) .

## Calendario {#calendar}

Il calendario del pannello controlla l’intervallo di reporting per tabelle e visualizzazioni all’interno di un pannello.

Nota: Se un componente intervallo di date (viola) viene utilizzato all’interno di una zona di rilascio di una tabella, una visualizzazione o un pannello, questo sovrascriverà il calendario del pannello.

![](assets/panel-calendar.png)

## Zona di rilascio {#dropzone}

La zona di rilascio del pannello consente di applicare filtri e filtri a discesa a tutte le tabelle e visualizzazioni all’interno di un pannello. Puoi applicare uno o più filtri a un pannello. Per modificare il titolo sopra ogni filtro, fai clic sulla matita di modifica oppure fai clic con il pulsante destro del mouse per rimuoverlo completamente.

### Filtri

Trascina i filtri dalla barra a sinistra nella zona di rilascio del pannello per iniziare a filtrare il pannello.

![](assets/segment-filter.png)

### Filtri ad hoc

I componenti non filtranti possono anche essere trascinati direttamente nella zona di rilascio per creare filtri ad hoc, risparmiando tempo e fatica nell’utilizzo del Generatore di filtri. I filtri creati in questo modo vengono automaticamente definiti come filtri a livello di hit. Per modificare questa definizione, fai clic sull’icona delle informazioni (i) accanto al filtro, quindi sull’icona di modifica a forma di matita e modificala nel Generatore di filtri.

I filtri ad hoc sono locali per il progetto e non verranno visualizzati nella barra a sinistra se non li rendi pubblici.

![](assets/adhoc-segment-filter.png)

### Filtri a discesa {#dropdown-filter}

Oltre ai filtri, i filtri a discesa consentono di interagire con i dati in modo controllato. Ad esempio, puoi aggiungere un filtro a discesa per i tipi di dispositivi mobili in modo da filtrare il pannello in base a Tablet, Telefono cellulare o Desktop.

I filtri a discesa possono essere utilizzati per consolidare più progetti in un unico insieme. Ad esempio, se disponi di più versioni dello stesso progetto con diversi filtri Paese applicati, puoi consolidare tutte le versioni in un unico progetto e aggiungere un filtro a discesa Paese .

![](assets/dropdown-filter-intro.png)

Per creare filtri a discesa:

1. Per creare un filtro a discesa utilizzando [!UICONTROL Dimension items], ad esempio valori all’interno della dimensione [!UICONTROL Marketing Channel], fai clic sull’icona a forma di freccia destra accanto alla dimensione nella barra a sinistra. Verranno esposti tutti gli elementi disponibili. Seleziona uno o più elementi componenti dalla barra a sinistra e rilasciali nella zona di rilascio del pannello **tenendo premuto il tasto Maiusc**. Questo trasforma i componenti in un filtro a discesa, anziché in un singolo filtro.
1. Per creare un filtro a discesa utilizzando un altro componente, ad esempio metriche, filtri o intervalli di date, selezionalo da un tipo di componente nella barra a sinistra e rilascialo nella zona di rilascio del pannello **tenendo premuto il tasto Maiusc**.
1. Seleziona una delle opzioni dal menu a discesa per modificare i dati nel pannello . Puoi anche scegliere di non filtrare nessuno dei dati del pannello selezionando **[!UICONTROL No filter]**.

![](assets/create-dropdown.png)

[Guarda il ](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html) video per ulteriori informazioni su come aggiungere filtri a discesa al progetto.

## Menu di scelta rapida {#right-click}

Ulteriori funzionalità per un pannello sono disponibili facendo clic con il pulsante destro del mouse sull’intestazione del pannello.

![](assets/right-click-menu.png)

Sono disponibili le seguenti impostazioni:

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Insert Copied Panel/Visualization] | Consente di incollare (&quot;inserire&quot;) un pannello o una visualizzazione copiati in un’altra posizione all’interno del progetto o in un progetto completamente diverso. |
| [!UICONTROL Copy Panel] | Consente di fare clic con il pulsante destro del mouse e copiare un pannello in modo da poterlo inserire in un’altra posizione all’interno del progetto o in un progetto completamente diverso. |
| [!UICONTROL Duplicate Panel] | Crea un duplicato esatto del pannello corrente, che potrai quindi modificare. |
| [!UICONTROL Collapse/Expand all Panels] | Comprime ed espande tutti i pannelli del progetto. |
| [!UICONTROL Collapse/Expand all Visualizations in Panel] | Comprime ed espande tutte le visualizzazioni nel pannello corrente. |
| [!UICONTROL Edit Description] | Aggiungi (o modifica) una descrizione di testo per il pannello. |
| [!UICONTROL Get Panel Link] | Consente di indirizzare un utente a uno specifico pannello in un progetto. Quando fai clic sul collegamento, al destinatario verrà richiesto di effettuare l’accesso prima di essere indirizzato al pannello esatto a cui è collegato. |
