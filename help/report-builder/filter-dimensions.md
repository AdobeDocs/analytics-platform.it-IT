---
title: Filtrare le dimensioni in Report Builder
description: Descrive come utilizzare le dimensioni filtro in Report Builder for Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 5730d5f3-de76-429f-81f5-ebe6b62a9480
solution: Customer Journey Analytics
source-git-commit: 97c3b05d4d9661aabcb1b06db7fdf44671a29394
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 31%

---


# Filtra dimensioni

Per impostazione predefinita, ogni elemento dimensione nella tabella restituisce i primi 10 elementi per tale dimensione.

Per modificare gli elementi dimensionali restituiti per ogni dimensione:

1. Seleziona una cella nel blocco di dati.

1. Selezionare ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit data block]** nel pannello **[!UICONTROL Commands]**.

1. Selezionare **[!UICONTROL Next]** per visualizzare la scheda **[!UICONTROL Dimensions]**.

1. Seleziona ![AltroPiccolo](/help/assets/icons/MoreSmall.svg) accanto al nome di un componente nella tabella.

   ![Opzioni per l&#39;icona con i puntini di sospensione.](./assets/image27.png){zoomable="yes"}

1. Selezionare **[!UICONTROL Filter dimension]** nel menu popup per visualizzare il riquadro **[!UICONTROL Filter dimension]**.

1. Seleziona **Most popular** o **Specific** come **[!UICONTROL Type]**.

   ![Opzione specifica selezionata nel riquadro Dimensione filtro.](./assets/image28.png){zoomable="yes"}

1. Selezionare le opzioni appropriate in base al tipo di filtro [selezionato](#filter-type).

1. Selezionare **[!UICONTROL Apply]** per aggiungere il filtro.

1. In Report Builder viene visualizzata la conferma del filtro aggiunto.

Per visualizzare i filtri applicati, passa il puntatore su una dimensione. Le dimensioni con filtri applicati visualizzano un&#39;icona di filtro ![Filtro](/help/assets/icons/Filter.svg) accanto al nome della dimensione.

## Modificare il filtro e l’ordinamento

Accanto alla metrica utilizzata per filtrare e ordinare il blocco di dati viene visualizzato un ![ArrowUp](/help/assets/icons/ArrowUp.svg) o ![ArrowDown](/help/assets/icons/ArrowDown.svg). La direzione della freccia indica se la metrica è in ordine crescente o decrescente.

Per modificare l&#39;ordinamento:

- Seleziona ![ArrowUp](/help/assets/icons/ArrowUp.svg) o ![ArrowDown](/help/assets/icons/ArrowDown.svg) accanto alla metrica per attivare/disattivare l&#39;ordinamento.

Per modificare la metrica utilizzata per filtrare e ordinare il blocco di dati:

1. Passa il puntatore sul componente di metrica desiderato nel generatore di tabelle per visualizzare altre opzioni.

2. Selezionare ![ArrowDown](/help/assets/icons/ArrowDown.svg) per la metrica preferita.

   ![Generatore di tabelle e metriche.](./assets/image30.png){zoomable="yes"}



## Tipo di filtro

Esistono due modi per filtrare gli elementi dimensionali: [Most popular](#most-popular) e [Specific](#specific-filtering)

### **[!UICONTROL Most popular]**

L&#39;opzione **[!UICONTROL Most popular]** consente di filtrare dinamicamente gli elementi dimensionali in base ai valori delle metriche. Most popular (Più popolari) restituisce gli elementi dimensionali con classificazione più elevata in base ai valori delle metriche. Per impostazione predefinita, sono elencati i primi 10 elementi dimensione, ordinati in base alla prima metrica aggiunta al blocco di dati.

![L&#39;opzione più comune.](./assets/image29.png){zoomable="yes"}


#### Opzioni Page (Pagina) e Rows (Righe)

Utilizzare i campi **[!UICONTROL Page]** e **[!UICONTROL Rows]** per suddividere i dati in pagine o gruppi sequenziali. Questa funzione consente di inserire nel rapporto valori di riga diversi dai primi valori. Ed è particolarmente utile per richiamare dati oltre il limite di 50.000 righe.

L&#39;impostazione predefinita per la pagina è `1` e per le righe è `10`. Queste impostazioni predefinite implicano che ogni pagina abbia 10 righe di dati. La pagina 1 restituisce i primi 10 elementi, la pagina 2 restituisce i successivi 10 elementi e così via.

La tabella seguente riporta alcuni esempi di valori di pagina e riga e dell’output risultante.

| Pagina | Riga | Output |
|------|--------|----------------------|
| 1 | 10 | Primi 10 elementi |
| 2 | 10 | Elementi da 11 a 20 |
| 1 | 100 | Primi 100 elementi |
| 2 | 100 | Elementi da 101 a 200 |
| 2 | 50.000 | Elementi da 50.001 a 100.000 |

Nella tabella seguente sono elencati i valori minimo e massimo per pagina e righe.

|       | Valori minimi | Valori massimi |
|-------|---------------:|---------------:|
| Pagina iniziale | 1 | 50 milioni |
| Numero di righe | 1 | 50.000 |


#### Includi “Nessun valore“

In Customer Journey Analytics, alcune dimensioni raccolgono una voce *Nessun valore*. L&#39;impostazione **[!UICONTROL Include "No value"]** consente di escludere questi valori dai report. Ad esempio, puoi creare una classificazione “Nome prodotto” in base al codice SKU del prodotto. Se uno SKU di prodotto specifico non è stato impostato con la relativa classificazione Nome prodotto specifica, il relativo valore Nome prodotto è impostato su *Nessun valore*.

**[!UICONTROL Include "No value"]** è selezionato per impostazione predefinita. Per escludere le voci prive di valore, deseleziona questa opzione.

#### Filtrare per criterio

Puoi filtrare gli elementi dimensione che soddisfano o meno tutti i criteri o qualsiasi criterio.

Per impostare i criteri di filtro:

1. Seleziona un operatore dal menu a discesa operatore. Per impostazione predefinita **[!UICONTROL Contains the phrase]** è selezionato

   ![Elenco degli operatori.](./assets/image31.png){zoomable="yes"}

1. Immettere un termine di ricerca.

1. Seleziona ![Aggiungi](/help/assets/icons/Add.svg) **[!UICONTROL Add row]** per confermare la selezione e aggiungere un altro elemento di criteri.

1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un elemento di criteri.

Puoi includere fino a 10 elementi di criteri.

### **[!UICONTROL  Specific]**

L&#39;opzione **[!UICONTROL Specific]** consente di creare un elenco fisso di elementi dimensionali per ogni dimensione. Utilizza il tipo di filtro **[!UICONTROL Specific]** per specificare gli elementi dimensionali esatti da includere nel filtro. Puoi selezionare gli elementi da un elenco o da un intervallo di celle.

![Opzioni specifiche ed elementi selezionati.](./assets/image32.png){zoomable="yes"}

#### From list (Da elenco)

1. Selezionare l&#39;opzione **[!UICONTROL From list]** per cercare e selezionare gli elementi dimensione.

   Quando selezioni l&#39;opzione **From list**, l&#39;elenco **[!UICONTROL Dimension items]** viene compilato con elementi dimensionali ordinati per numero di eventi.

   ![Opzione From List ed elementi disponibili.](./assets/image33.png){zoomable="yes"}

1. Immetti un termine di ricerca in ![Ricerca](/help/assets/icons/Search.svg) **[!UICONTROL _Aggiungi elemento_]** per eseguire la ricerca nell&#39;elenco.

1. Per cercare un elemento non incluso negli ultimi 90 giorni di dati, selezionare **[!UICONTROL Show items for the last 6 months]** per estendere la ricerca. Dopo il caricamento dei dati degli ultimi 6 mesi, Report Builder aggiorna il collegamento a **[!UICONTROL Show items for last 18 months]**.

1. Per eliminare un elemento dall&#39;elenco **[!UICONTROL Selected items]**, selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg).

1. Per spostare un elemento nell&#39;elenco **[!UICONTROL Selected items]**, trascinare e rilasciare l&#39;elemento oppure selezionare ![AltroPiccolo](/help/assets/icons/MoreSmall.svg) per visualizzare il menu di scelta rapida e selezionare le opzioni di spostamento.

1. Seleziona **[!UICONTROL Apply]**.

Report Builder aggiorna l’elenco in base al filtro specifico applicato.

#### From range of cells (Da intervallo di celle)

Selezionare l&#39;opzione **From range of cells** per scegliere un intervallo di celle contenente l&#39;elenco degli elementi delle dimensioni da trovare.

![Opzione e campo From range of cells (Da intervallo di celle) per selezionare un intervallo di celle.](./assets/image37.png){zoomable="yes"}

Quando selezioni un intervallo di celle, considera le seguenti restrizioni:

- L’intervallo deve avere almeno una cella.
- L’intervallo non può avere più di 50.000 celle.
- L’intervallo deve trovarsi in una singola riga o colonna ininterrotta.

La selezione può contenere celle vuote o con valori che non corrispondono a un elemento dimensione specifico.


### Filtrare rapidamente una dimensione

Per filtrare una dimensione per la quale al momento non è applicato alcun filtro:

1. Selezionare ![ChevronRight](/help/assets/icons/ChevronRight.svg) per una dimensione. Ad esempio: **[!UICONTROL Interaction channel]**.

1. Seleziona due volte gli elementi dimensione da aggiungere al filtro. In alternativa, seleziona uno o più elementi dimensione e trascina la selezione nella sezione ![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]**.

   ![Scheda Dimensioni e elenco delle dimensioni.](./assets/quickly-filter.png){zoomable="yes"}

