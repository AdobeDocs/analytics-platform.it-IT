---
description: I pannelli sono raccolte di tabelle e visualizzazioni.
title: Panoramica dei pannelli
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
role: User
source-git-commit: 665dcd8edcfae6bbf3239c0812ce70843f2ce07c
workflow-type: tm+mt
source-wordcount: '1392'
ht-degree: 71%

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
| [Pannello a forma libera](freeform-panel.md) | Esegui confronti illimitati e raggruppamenti, quindi aggiungi visualizzazioni per raccontare una storia ricca di dati. |
| [Pannello Visualizzatori simultanei di contenuti multimediali](media-concurrent-viewers.md) | Analizza i visualizzatori simultanei nel tempo, con dettagli sui picchi di concorrenza e con la possibilità di suddividerli e confrontarli. |
| [Pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali)](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | L’analisi del tempo di riproduzione consente di comprendere dove si è verificato il picco di concorrenza o dove si è verificato il calo. |

![Pannello di Customer Journey Analytics in cui sono elencati i tipi di pannello disponibili.](assets/panel-overview.png)

I pannelli [!UICONTROL Quick Insights], [!UICONTROL Blank] e [!UICONTROL Freeform] sono ideali per iniziare con le attività di analisi, mentre [!UICONTROL Attribution IQ] si presta ad analisi più avanzate. Nei progetti è disponibile un pulsante `"+"` che consente di aggiungere pannelli vuoti in qualsiasi momento.

Il pannello iniziale predefinito è [!UICONTROL Freeform], ma puoi impostare come predefinito il [pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md).

## Calendario {#calendar}

Il calendario del pannello controlla l’intervallo di reporting per tabelle e visualizzazioni all’interno di un pannello.

Nota: se un componente di intervallo date (viola) viene utilizzato all’interno di una tabella, di una visualizzazione o di una zona di rilascio di un pannello, questo sovrascriverà il calendario del pannello.

![Finestra del calendario che mostra l’intervallo di date selezionato.](assets/panel-calendar.png)

Puoi applicare un intervallo di date a livello di minuto nelle impostazioni avanzate del calendario del pannello. Se esegui rapporti su un intervallo di date che dura molti giorni, l’ora di inizio si applica al primo giorno e l’ora di fine si applica all’ultimo giorno dell’intervallo.

## Zona di rilascio {#dropzone}

La zona di rilascio del pannello consente di applicare filtri e filtri a discesa a tutte le tabelle e visualizzazioni di un pannello. Puoi applicare uno o più filtri a un pannello.

### Filtri

Per iniziare a filtrare il pannello, trascina i filtri dalla barra a sinistra fino alla zona di rilascio del pannello. Ripeti questa procedura per aggiungere altri filtri al pannello. I filtri vengono visualizzati uno accanto all’altro nella parte superiore del pannello.

![La barra a sinistra mostra le metriche disponibili e la metrica Cliente mobile trascinata nella zona di rilascio del pannello.](assets/segment-filter.png)

### Filtri ad hoc

Puoi anche trascinare componenti diversi da filtri direttamente nella zona di rilascio, per creare filtri ad hoc in modo più rapido e senza dover passare al Generatore di filtri. I filtri creati in questo modo vengono automaticamente definiti come filtri a livello di evento. Puoi modificarli come di consueto facendo clic sull’icona delle informazioni (i) accanto al filtro, quindi sull’icona Modifica a forma di matita per accedere al Generatore di filtri.

I filtri ad hoc sono un tipo di filtro rapido e sono locali per il progetto. Non vengono visualizzati nella barra a sinistra, a meno che tu non li renda pubblici.

Per ulteriori informazioni, consulta [Filtri rapidi](/help/components/filters/quick-filters.md)

![Filtri ad hoc resi pubblici e rilasciati nella zona di rilascio.](assets/adhoc-segment-filter.png)

### Filtri a discesa statici

I filtri a discesa statici consentono di interagire con i dati in modo controllato. Ad esempio, puoi aggiungere un filtro a discesa per i tipi di dispositivi mobili, in modo da filtrare il pannello per Tablet, Telefono cellulare o Desktop.

I filtri a discesa statici possono essere utilizzati anche per consolidare più progetti in un unico progetto. Ad esempio, se hai creato più versioni dello stesso progetto, assegnando a ciascuna un filtro Paese diverso, puoi consolidarle tutte in un unico progetto e aggiungere un filtro a discesa Paese.

![Filtri a discesa statici che mostrano il filtro del canale di mercato “Diretto” evidenziato. ](assets/dropdown-filter-intro.png)

#### Creare filtri a discesa statici

* Per i filtri a discesa che utilizzano elementi dimensionali, seleziona una singola dimensione dalla barra a sinistra e rilasciala nella zona di rilascio del pannello **durante la tenuta`[Shift]`**. In questo modo viene creato un filtro a discesa con tutti gli elementi dimensionali associati a tale dimensione.

  Oppure, se desideri che il filtro a discesa includa solo elementi dimensionali specifici associati a una dimensione, fai clic sull’icona a forma di freccia verso destra accanto alla dimensione desiderata nella barra a sinistra. Questa azione espone tutti gli elementi dimensionali disponibili. Seleziona più elementi dimensione da questo elenco tramite `[Shift + Click]` o `[Ctrl + Click]`, quindi rilasciale nella zona di rilascio del pannello **durante la tenuta** `[Shift]`.

* Per i filtri a discesa che utilizzano un singolo tipo di componente (ad esempio, solo dimensioni, solo filtri o solo metriche), seleziona più elementi dello stesso tipo nella barra a sinistra utilizzando `[Shift + Click]` o `[Ctrl + Click]`, quindi rilasciale nella zona di rilascio del pannello **durante la tenuta`[Shift]`**.

  Viene creato un singolo filtro a discesa con i componenti selezionati.

* Per i filtri a discesa che utilizzano diversi tipi di componenti (ad esempio 2 metriche e 3 filtri), seleziona più componenti utilizzando `[Shift + Click]` o `[Ctrl + Click]`. Rilascia la selezione nella zona di rilascio del pannello **mentre tieni premuto`[Shift]`**. In questo contesto, tutti i tipi di componenti vengono trattati come filtri a discesa separati. Ad esempio, se nella selezione includi sia metriche che elementi dimensionali, vengono creati due filtri a discesa separati: uno include gli elementi dimensionali e l’altro include le metriche.

  ![Per rilasciare un filtro a discesa statico, è disponibile la finestra del pannello con il campo del segmento del Cliente mobile. ](assets/create-dropdown.png)

Facendo clic con il pulsante destro del mouse su un filtro a discesa sono disponibili le seguenti opzioni:

* **[!UICONTROL Delete drop-down]**: rimuove il filtro a discesa dal pannello.
* **[!UICONTROL Delete label]**: rimuovi il testo sopra un filtro a discesa. Per modificare l’etichetta, seleziona l’icona della matita.
* **[!UICONTROL Add label]**: quando aggiungi un filtro a discesa a un progetto, un’etichetta viene impostata automaticamente sul nome del componente. Se elimini l’etichetta, puoi aggiungerla nuovamente con questa opzione.
* **[!UICONTROL Require selection]**: richiede che nel pannello sia impostato un filtro.

Per ulteriori informazioni su come aggiungere filtri a discesa a un progetto, [guarda questo video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=it).

#### Utilizzare filtri a discesa statici

Per filtrare il pannello, gli utenti possono utilizzare il menu a discesa dei filtri in uno dei seguenti modi:

* Applica un singolo filtro al pannello selezionando il filtro dal filtro a discesa.

* Applica più filtri al pannello selezionando più filtri dal filtro a discesa. Il pannello viene filtrato per includere uno qualsiasi dei filtri selezionati.

  ![Seleziona più filtri](assets/dropdown-filter-multiselect.png)

### Creare filtri a discesa dinamici

I filtri a discesa dinamici consentono di determinare i valori disponibili in base ai dati all’interno dell’intervallo di reporting del pannello e ai valori in altri filtri a discesa. Ad esempio, puoi creare due menu a discesa dinamici utilizzando una dimensione Paesi e una dimensione Città. Quando selezioni un paese dall’elenco a discesa UICONTROL Paesi , l’elenco a discesa Città si adatta in modo dinamico per mostrare solo le città all’interno di quel paese.

Lo stesso concetto si applica a tutte le dimensioni: sono visibili solo gli elementi dimensionali che compaiono nell’intervallo di date del pannello e i filtri selezionati. Gli elementi dimensionali selezionati nei filtri a discesa statici influiscono sui valori disponibili nei filtri a discesa dinamici. Tuttavia, ciò non vale per il contrario: gli elementi dimensionali selezionati nei filtri a discesa dinamici non influiscono sui valori disponibili nei filtri a discesa statici.

La selezione manuale degli elementi dimensionali è disponibile se prevedi che un certo elemento dimensionale verrà raccolto in futuro. È inoltre possibile cancellare un filtro a discesa dinamico in modo che non contenga un valore, consentendo ad altri filtri a discesa dinamici di contenere più valori. Seleziona **[!UICONTROL Reset all]** per cancellare la selezione da tutti i filtri a discesa per quel pannello.

Per creare un filtro a discesa dinamico:

* trascina una singola dimensione nella zona di rilascio del pannello **mentre tieni premuto`[Shift]`**.
* I filtri a discesa dinamici non sono disponibili per metriche, filtri o intervalli di date.
* Fai clic con il pulsante destro del mouse su un filtro a discesa e seleziona **[!UICONTROL Delete filter]** per eliminarlo.

Facendo clic con il pulsante destro del mouse su un filtro a discesa dinamico, è possibile visualizzare le stesse opzioni disponibili per i filtri a discesa statici.

## Menu di scelta rapida {#right-click}

Ulteriori funzionalità per un pannello sono disponibili nel menu di scelta rapida che compare quando fai clic con il pulsante destro del mouse sull’intestazione del pannello.

![Opzioni disponibili dal menu di scelta rapida per l’intestazione di un pannello.](assets/right-click-menu.png)

Sono disponibili le seguenti impostazioni:

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Insert Copied Panel/Visualization] | Consente di incollare (“inserire”) un pannello o una visualizzazione copiati in un’altra posizione all’interno del progetto o in un progetto diverso. |
| [!UICONTROL Copy Panel] | Consente di fare clic con il pulsante destro del mouse e copiare un pannello, in modo da poterlo inserire in un’altra posizione all’interno di un progetto o in un progetto diverso. |
| [!UICONTROL Duplicate Panel] | Crea un duplicato esatto del pannello corrente, che potrai quindi modificare. |
| [!UICONTROL Collapse/Expand all Panels] | Comprime ed espande tutti i pannelli del progetto. |
| [!UICONTROL Collapse/Expand all Visualizations in Panel] | Comprime ed espande tutte le visualizzazioni nel pannello corrente. |
| [!UICONTROL Edit Description] | Aggiungi (o modifica) un testo descrittivo per il pannello. |
| [!UICONTROL Get Panel Link] | Consente di indirizzare un utente a uno specifico pannello in un progetto. Quando fai clic sul collegamento, al destinatario verrà richiesto di effettuare l’accesso prima di essere indirizzato al pannello a cui è collegato. |
