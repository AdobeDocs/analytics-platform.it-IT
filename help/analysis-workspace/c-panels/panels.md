---
description: I pannelli sono raccolte di tabelle e visualizzazioni.
title: Panoramica dei pannelli
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1259'
ht-degree: 47%

---

# Panoramica dei pannelli

Un [!UICONTROL panel] è una raccolta di tabelle e visualizzazioni. Puoi accedere ai pannelli dall’icona in alto a sinistra in Workspace o da una [pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md). I pannelli sono utili per organizzare i progetti in base a specifici periodi di tempo, viste dati o casi di utilizzo di analisi.

## Tipi di pannello

In Analysis Workspace sono disponibili i seguenti tipi di pannello per [!UICONTROL Customer Journey Analytics]:

| Nome pannello | Descrizione |
| --- | --- |
| [Pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md) | Per iniziare a eseguire analisi, scegli tra i pannelli e le visualizzazioni disponibili. |
| [Pannello Quick Insights](quickinsight.md) | Crea una tabella a forma libera e una relativa visualizzazione per analizzare e individuare più rapidamente le informazioni. |
| [Pannello Attribution](attribution.md) | Confronta e visualizza rapidamente più modelli di attribuzione utilizzando qualsiasi dimensione e metrica di conversione. |
| [Pannello a forma libera](freeform-panel.md) | Esegui confronti illimitati e raggruppamenti, quindi aggiungi visualizzazioni per raccontare una storia ricca di dati. |
| [Pannello Visualizzatori simultanei di contenuti multimediali](media-concurrent-viewers.md) | Analizza i visualizzatori simultanei nel tempo, con dettagli sui picchi di concorrenza e con la possibilità di suddividerli e confrontarli. |
| [Pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali)](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | L’analisi del tempo di riproduzione consente di comprendere dove si è verificato il picco di concorrenza o dove si è verificato il calo. |

![Pannello Customer Journey Analytics in cui sono elencati i tipi di pannello disponibili.](assets/panel-overview.png)

I pannelli [!UICONTROL Quick Insights], [!UICONTROL Blank] e [!UICONTROL Freeform] sono ideali per iniziare con le attività di analisi, mentre [!UICONTROL Attribution IQ] si presta ad analisi più avanzate. Nei progetti è disponibile un pulsante `"+"` che consente di aggiungere pannelli vuoti in qualsiasi momento.

Il pannello iniziale predefinito è [!UICONTROL Freeform], ma puoi impostare come predefinito il [pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md).

## Calendario {#calendar}

Il calendario del pannello controlla l’intervallo di reporting per tabelle e visualizzazioni all’interno di un pannello.

Nota: se un componente di intervallo date (viola) viene utilizzato all’interno di una tabella, di una visualizzazione o di una zona di rilascio di un pannello, questo sovrascriverà il calendario del pannello.

![Finestra del calendario che mostra l’intervallo di date selezionato.](assets/panel-calendar.png)

Puoi applicare un intervallo di date a livello di minuto nelle impostazioni avanzate del calendario del pannello. Se esegui rapporti su un intervallo di date che dura molti giorni, l’ora di inizio si applica al primo giorno e l’ora di fine si applica all’ultimo giorno dell’intervallo.

## Zona di rilascio {#dropzone}

La zona di rilascio del pannello consente di applicare filtri e filtri a discesa a tutte le tabelle e visualizzazioni di un pannello. Puoi applicare uno o più filtri a un pannello. Per modificare il titolo sopra ogni filtro, fai clic sull’icona della matita (Modifica); per rimuoverlo, fai clic con il pulsante destro del mouse.

### Filtri

Per iniziare a filtrare il pannello, trascina un filtro dalla barra a sinistra fino alla zona di rilascio del pannello.

![La barra a sinistra mostra le metriche disponibili e la metrica Cliente mobile trascinata nella zona di rilascio del pannello.](assets/segment-filter.png)

### Filtri ad hoc

Puoi anche trascinare componenti diversi da filtri direttamente nella zona di rilascio, per creare filtri ad hoc in modo più rapido e senza dover passare al Generatore di filtri. I filtri creati in questo modo vengono automaticamente definiti come filtri a livello di evento. Puoi modificarli come di consueto facendo clic sull’icona delle informazioni (i) accanto al filtro, quindi sull’icona Modifica a forma di matita per accedere al Generatore di filtri.

I filtri ad hoc sono un tipo di filtro rapido e sono locali per il progetto. Non vengono visualizzati nella barra a sinistra, a meno che non li rendi pubblici.

Per ulteriori informazioni, consulta [Filtri rapidi](/help/components/filters/quick-filters.md).

![Filtri ad hoc resi pubblici e rilasciati nella zona di rilascio.](assets/adhoc-segment-filter.png)

### Filtri a discesa statici

I filtri a discesa consentono di interagire con i dati in modo controllato. Ad esempio, puoi aggiungere un filtro a discesa per i tipi di dispositivi mobili, in modo da filtrare il pannello per Tablet, Telefono cellulare o Desktop.

I filtri a discesa possono essere utilizzati per consolidare più progetti in un progetto unico. Ad esempio, se hai creato più versioni dello stesso progetto, assegnando a ciascuna un filtro Paese diverso, puoi consolidarle tutte in un unico progetto e aggiungere un filtro a discesa Paese.

![Filtri a discesa statici che mostrano il filtro &quot;Diretto&quot; del canale di mercato evidenziato. ](assets/dropdown-filter-intro.png)

Per creare un filtro a discesa statico:

* Per i filtri a discesa che utilizzano elementi dimensionali, fai clic sull’icona a forma di freccia destra accanto alla dimensione desiderata nella barra a sinistra. Questa azione espone tutti gli elementi dimensionali disponibili. Seleziona più elementi dimensione da questo elenco tramite `[Shift + Click]` o `[Ctrl + Click]`, quindi rilasciale nella zona di rilascio del pannello **durante la tenuta`[Shift]`**.
* Per i filtri a discesa che utilizzano altri componenti, come metriche, filtri o intervalli di date, seleziona più componenti utilizzando `[Shift + Click]` o `[Ctrl + Click]`. Rilascia la selezione nella zona di rilascio del pannello **durante la tenuta`[Shift]`**. In questo contesto, tutti i tipi di componenti vengono trattati come filtri.
* Un singolo filtro a discesa può contenere solo un singolo tipo di componente. Se nella selezione includi più tipi di componente, viene creato un filtro a discesa separato per ciascun tipo di componente. Ad esempio, se includi nella selezione sia le metriche che gli elementi dimensionali, vengono creati due filtri a discesa separati. Un filtro a discesa include gli elementi dimensionali, l’altro le metriche.

Seleziona una delle opzioni dall’elenco a discesa per modificare i dati nel pannello. Puoi anche scegliere di non filtrare nessuno dei dati del pannello selezionando **[!UICONTROL No filter]**.

![Per rilasciare un filtro a discesa statico, è disponibile la finestra del pannello con il campo del segmento del cliente di Mobile. ](assets/create-dropdown.png)

Facendo clic con il pulsante destro del mouse su un filtro a discesa sono disponibili le seguenti opzioni:

* **[!UICONTROL Add label]**: quando aggiungi un filtro a discesa a un progetto, un’etichetta viene impostata automaticamente sul nome del componente. Se elimini l’etichetta, puoi aggiungerla nuovamente con questa opzione.
* **[!UICONTROL Delete label]**: rimuovi il testo sopra un filtro a discesa.
* **[!UICONTROL Delete drop-down filter]**: rimuove il filtro a discesa dal pannello.

Per ulteriori informazioni su come aggiungere filtri a discesa a un progetto, [guarda questo video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=it).

### Filtri a discesa dinamici

I filtri a discesa dinamici consentono di determinare i valori disponibili in base ai dati all’interno dell’intervallo di reporting del pannello e ai valori in altri filtri a discesa. Ad esempio, puoi creare due elenchi a discesa dinamici utilizzando una dimensione Paesi e una dimensione Città. Quando selezioni un paese dall’elenco a discesa UICONTROL Paesi, l’elenco a discesa Città si adatta in modo dinamico per mostrare solo le città all’interno di quel paese.

Lo stesso concetto si applica a tutte le dimensioni; sono visibili solo gli elementi dimensionali che compaiono nell’intervallo di date del pannello e i filtri selezionati. Gli elementi Dimension selezionati nei filtri a discesa statici influiscono sui valori disponibili nei filtri a discesa dinamici. Tuttavia, l’inverso non è vero; gli elementi di Dimension selezionati nei filtri a discesa dinamici non influiscono sui valori disponibili nei filtri a discesa statici.

La selezione manuale degli elementi dimensionali è disponibile se prevedi che un determinato elemento dimensionale verrà raccolto in futuro. È inoltre possibile cancellare un filtro a discesa dinamico in modo che non contenga un valore, consentendo ad altri filtri a discesa dinamici di contenere più valori. Seleziona **[!UICONTROL Reset all]** per cancellare la selezione da tutti i filtri a discesa per quel pannello.

Per creare un filtro a discesa dinamico:

* Trascina una singola dimensione nella zona di rilascio del pannello **durante la tenuta`[Shift]`**.
* I filtri a discesa dinamici non sono disponibili per metriche, filtri o intervalli di date.
* Fai clic con il pulsante destro del mouse su un filtro a discesa e seleziona (Confronta periodi di tempo) **[!UICONTROL Delete filter]** per eliminarlo.

Facendo clic con il pulsante destro del mouse su un filtro a discesa dinamico, è possibile visualizzare le stesse opzioni disponibili per i filtri a discesa statici.

## Menu di scelta rapida {#right-click}

Ulteriori funzionalità per un pannello sono disponibili nel menu di scelta rapida che compare quando fai clic con il pulsante destro del mouse sull’intestazione del pannello.

![Le opzioni disponibili nel menu di scelta rapida per l’intestazione di un pannello.](assets/right-click-menu.png)

Sono disponibili le seguenti impostazioni:

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Insert Copied Panel/Visualization] | Consente di incollare (&quot;inserire&quot;) un pannello o una visualizzazione copiata in un’altra posizione all’interno del progetto o in un altro progetto. |
| [!UICONTROL Copy Panel] | Consente di fare clic con il pulsante destro del mouse e copiare un pannello, in modo da poterlo inserire in un’altra posizione all’interno del progetto o in un altro progetto. |
| [!UICONTROL Duplicate Panel] | Crea un duplicato esatto del pannello corrente, che potrai quindi modificare. |
| [!UICONTROL Collapse/Expand all Panels] | Comprime ed espande tutti i pannelli del progetto. |
| [!UICONTROL Collapse/Expand all Visualizations in Panel] | Comprime ed espande tutte le visualizzazioni nel pannello corrente. |
| [!UICONTROL Edit Description] | Aggiungi (o modifica) un testo descrittivo per il pannello. |
| [!UICONTROL Get Panel Link] | Consente di indirizzare un utente a uno specifico pannello in un progetto. Quando fai clic sul collegamento, al destinatario verrà richiesto di effettuare l’accesso prima di essere indirizzato al pannello a cui è collegato. |
