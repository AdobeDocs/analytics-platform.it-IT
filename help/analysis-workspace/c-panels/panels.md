---
description: I pannelli sono raccolte di tabelle e visualizzazioni.
title: Panoramica dei pannelli
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '811'
ht-degree: 100%

---

# Panoramica dei pannelli

Un [!UICONTROL panel] è una raccolta di tabelle e visualizzazioni. Puoi accedere ai pannelli dall’icona in alto a sinistra in Workspace o da un [pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md). I pannelli sono utili per organizzare i progetti in base a specifici periodi di tempo, viste dati o casi di utilizzo di analisi.

## Tipi di pannello

In Analysis Workspace sono disponibili i seguenti tipi di pannello per [!UICONTROL Customer Journey Analytics]:

| Nome pannello | Descrizione |
| --- | --- |
| [Pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md) | Per iniziare a eseguire analisi, scegli tra i pannelli e le visualizzazioni disponibili. |
| [Pannello Quick Insights](quickinsight.md) | Crea una tabella a forma libera e una relativa visualizzazione per analizzare e individuare più rapidamente le informazioni. |
| [Pannello Attribution](attribution.md) | Confronta e visualizza rapidamente più modelli di attribuzione utilizzando qualsiasi dimensione e metrica di conversione. |
| [Pannello Freeform](freeform-panel.md) | Esegui confronti illimitati e suddivisioni, quindi aggiungi visualizzazioni per raccontare una storia ricca di dati. |

![](assets/panel-overview.png)

I pannelli [!UICONTROL Quick Insights], [!UICONTROL Blank] e [!UICONTROL Freeform] sono ideali per iniziare con le attività di analisi, mentre [!UICONTROL Attribution IQ] si presta ad analisi più avanzate. Nei progetti è disponibile un pulsante `"+"` che consente di aggiungere pannelli vuoti in qualsiasi momento.

Il pannello iniziale predefinito è [!UICONTROL Freeform], ma puoi impostare come predefinito il [pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md).

## Calendario {#calendar}

Il calendario del pannello controlla l’intervallo di reporting per tabelle e visualizzazioni all’interno di un pannello.

Nota: se un componente di intervallo date (viola) viene utilizzato all’interno di una tabella, di una visualizzazione o di una zona di rilascio di un pannello, questo sovrascriverà il calendario del pannello.

![](assets/panel-calendar.png)

Puoi applicare un intervallo di date a livello di minuto nelle impostazioni avanzate del calendario del pannello. Se esegui rapporti su un intervallo di date che dura molti giorni, l’ora di inizio si applica al primo giorno e l’ora di fine si applica all’ultimo giorno dell’intervallo.

## Zona di rilascio {#dropzone}

La zona di rilascio del pannello consente di applicare filtri e filtri a discesa a tutte le tabelle e visualizzazioni di un pannello. Puoi applicare uno o più filtri a un pannello. Per modificare il titolo sopra ogni filtro, fai clic sull’icona della matita (Modifica); per rimuoverlo, fai clic con il pulsante destro del mouse.

### Filtri

Per iniziare a filtrare il pannello, trascina un filtro dalla barra a sinistra fino alla zona di rilascio del pannello.

![](assets/segment-filter.png)

### Filtri ad hoc

Puoi anche trascinare componenti diversi da filtri direttamente nella zona di rilascio, per creare filtri ad hoc in modo più rapido e senza dover passare al Generatore di filtri. I filtri creati in questo modo vengono automaticamente definiti come filtri a livello di hit. Puoi modificarli come di consueto facendo clic sull’icona delle informazioni (i) accanto al filtro, quindi sull’icona Modifica a forma di matita per accedere al Generatore di filtri.

I filtri ad hoc sono locali per il progetto e non verranno visualizzati nella barra a sinistra, a meno che non li rendi pubblici.

![](assets/adhoc-segment-filter.png)

### Filtri a discesa {#dropdown-filter}

Oltre ai filtri, i filtri a discesa consentono di interagire con i dati in modo controllato. Ad esempio, puoi aggiungere un filtro a discesa per i tipi di dispositivi mobili, in modo da filtrare il pannello per Tablet, Telefono cellulare o Desktop.

I filtri a discesa possono essere utilizzati per consolidare più progetti in un progetto unico. Ad esempio, se hai creato più versioni dello stesso progetto, assegnando a ciascuna un filtro Paese diverso, puoi consolidarle tutte in un unico progetto e aggiungere un filtro a discesa Paese.

![](assets/dropdown-filter-intro.png)

Per creare un filtro a discesa:

1. Per creare un filtro a discesa utilizzando [!UICONTROL Dimension items], ad esempio valori della dimensione [!UICONTROL Marketing Channel], fai clic sull’icona a forma di freccia verso destra accanto alla dimensione nella barra a sinistra. Verranno esposti tutti gli elementi disponibili. Seleziona uno o più elementi componenti nella barra a sinistra, **tieni premuto il tasto Maiusc** e trascinali nella zona di rilascio del pannello. I componenti diventano un filtro a discesa, anziché un singolo filtro.
1. Per creare un filtro a discesa utilizzando un altro componente, ad esempio metriche, filtri o intervalli di date, seleziona un tipo di componente nella barra a sinistra e rilascialo nella zona di rilascio del pannello mentre **tieni premuto il tasto Maiusc**.
1. Per cambiare i dati visualizzati nel pannello, seleziona una delle opzioni dal menu a discesa. Puoi anche scegliere di non filtrare nessuno dei dati del pannello, selezionando **[!UICONTROL No filter]**.

![](assets/create-dropdown.png)

Per ulteriori informazioni su come aggiungere filtri a discesa a un progetto, [guarda questo video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=it).

## Menu di scelta rapida {#right-click}

Ulteriori funzionalità per un pannello sono disponibili nel menu di scelta rapida che compare quandi fai clic con il pulsante destro del mouse sull’intestazione del pannello.

![](assets/right-click-menu.png)

Sono disponibili le seguenti impostazioni:

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Insert Copied Panel/Visualization] | Consente di incollare (inserire) l’elemento copiato altrove nello stesso progetto o in un altro progetto. |
| [!UICONTROL Copy Panel] | Consente di fare clic con il pulsante destro del mouse e copiare un pannello, in modo da poterlo inserire altrove nello stesso progetto o in un altro progetto. |
| [!UICONTROL Duplicate Panel] | Crea un duplicato esatto del pannello corrente, che potrai quindi modificare. |
| [!UICONTROL Collapse/Expand all Panels] | Comprime ed espande tutti i pannelli del progetto. |
| [!UICONTROL Collapse/Expand all Visualizations in Panel] | Comprime ed espande tutte le visualizzazioni nel pannello corrente. |
| [!UICONTROL Edit Description] | Aggiungi (o modifica) un testo descrittivo per il pannello. |
| [!UICONTROL Get Panel Link] | Consente di indirizzare un utente a uno specifico pannello in un progetto. Quando fai clic sul collegamento, al destinatario verrà richiesto di effettuare l’accesso prima di essere indirizzato al pannello a cui è collegato. |
