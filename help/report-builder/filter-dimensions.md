---
title: Come filtrare le dimensioni in Report Builder
description: Descrive come utilizzare le dimensioni filtro in Report Builder for Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 5730d5f3-de76-429f-81f5-ebe6b62a9480
solution: Customer Journey Analytics
source-git-commit: 56ac1c5a6d13a972aed90cab79cbc5f794cedc9e
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 71%

---


# Dimensioni filtro

Per impostazione predefinita, ogni elemento dimensione nella tabella restituisce i primi 10 elementi per tale dimensione.

Per modificare gli elementi dimensione restituiti per ogni dimensione:

1. Seleziona un blocco di dati e fai clic su Modifica blocco di dati nel pannello COMANDI.

1. Selezionare **[!UICONTROL Next]** per visualizzare la scheda Dimensioni.

1. Seleziona ![AltroPiccolo](/help/assets/icons/MoreSmall.svg) accanto al nome di un componente nella tabella.

   ![Opzioni per l&#39;icona con i puntini di sospensione.](./assets/image27.png)

1. Seleziona **Filter dimension** (Dimensione filtro) nel menu a comparsa per visualizzare il riquadro **Filter dimension** (Dimensione filtro).

1. Seleziona **Most popular** o **Specific**.

   ![Opzione specifica selezionata nel riquadro Dimensione filtro.](./assets/image28.png)

1. Seleziona le opzioni appropriate in base al tipo di filtro scelto.

1. Fai clic su **Applica** per aggiungere il filtro.

   In Report Builder viene visualizzata la conferma del filtro aggiunto.

Per visualizzare i filtri applicati, passa il cursore su una dimensione. Le dimensioni con filtri applicati visualizzano un&#39;icona di filtro ![Filtro](/help/assets/icons/Filter.svg) accanto al nome del Dimension.

## Modificare il filtro e l’ordinamento

Accanto alla metrica utilizzata per filtrare e ordinare il blocco di dati viene visualizzata una freccia. La direzione della freccia indica se la metrica è in ordine crescente o decrescente.

Per cambiare la direzione di ordinamento, seleziona la freccia accanto alla metrica.

Per cambiare la metrica utilizzata per filtrare e ordinare il blocco di dati:

1. Passa il puntatore sul componente di metrica desiderato nel generatore di tabelle per visualizzare altre opzioni.

2. Seleziona la freccia sulla metrica preferita.

   ![Generatore di tabelle e metriche.](./assets/image30.png)



## Tipo di filtro

Esistono due modi per filtrare gli elementi dimensionali: Most popular (Più popolari) e Specific (Specifici).

### Most popular (Più popolari)

L’opzione Most popular (Più popolari) consente di filtrare dinamicamente gli elementi dimensione in base ai valori delle metriche. Il filtro Most popular (Più popolari) restituisce gli elementi dimensione con classificazione più elevata in base ai valori delle metriche. Per impostazione predefinita, sono elencati i primi 10 elementi dimensione, ordinati in base alla prima metrica aggiunta al blocco di dati.

![L&#39;opzione più comune.](./assets/image29.png)


**Opzioni Page e Rows**

Puoi utilizzare i campi **Page** (Pagina) e **Rows** (Righe) per suddividere i dati in pagine o gruppi sequenziali o pagine. Questo consente di inserire nel rapporto valori di riga diversi dai primi valori. Questa funzione è particolarmente utile per richiamare dati oltre il limite di 50.000 righe.

Il valore predefinito per Pagina è 1 e per Righe è 10. Queste impostazioni predefinite implicano che ogni pagina abbia 10 righe di dati. La pagina 1 restituisce i primi 10 elementi, la pagina 2 restituisce i successivi 10 elementi e così via.

La tabella seguente riporta alcuni esempi di valori di pagina e riga e dell’output risultante.

| Pagina | Riga | Output |
|------|--------|----------------------|
| 1 | 10 | Primi 10 elementi |
| 2 | 10 | Elementi da 11 a 20 |
| 1 | 100 | Primi 100 elementi |
| 2 | 100 | Elementi da 101 a 200 |
| 2 | 50.000 | Elementi da 50.001 a 100.000 |

I valori minimo e massimo sono:

- Pagina iniziale: Min = 1, Max: 50 milioni
- Numero di righe: Min = 1, Max: 50.000

### Includi “Nessun valore“

In Customer Journey Analytics, alcune dimensioni raccolgono una voce &quot;No value&quot; (Nessun valore). Con questo filtro puoi escludere tali valori dai rapporti. Ad esempio, puoi creare una classificazione “Nome prodotto” in base al codice SKU del prodotto. Se per uno SKU di prodotto non è stata impostata una classificazione Nome prodotto specifica, il valore Nome prodotto viene impostato su “No value” (Nessun valore).

**[!UICONTROL Include "No value"]** è selezionato per impostazione predefinita. Per escludere le voci prive di valore, deseleziona questa opzione.

### Filtrare per criterio

Puoi filtrare gli elementi dimensione che soddisfano o meno tutti i criteri o qualsiasi criterio.

Per impostare i criteri da filtrare:

1. Seleziona un operatore dall’elenco a discesa.

   ![Elenco degli operatori.](./assets/image31.png)

1. Immetti un valore nel campo di ricerca.

1. Seleziona ![Aggiungi](/help/assets/icons/Add.svg) **[!UICONTROL Add row]** per confermare la selezione e aggiungere un altro elemento di criteri.

1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un elemento di criteri.

   Puoi includere fino a 10 elementi di criteri.

### Filtri specifici

L’opzione Specific (Specifici) consente di creare un elenco di elementi dimensione per ogni dimensione. Utilizza il tipo di filtro **Specific** (Specifici) per specificare gli elementi dimensione esatti da includere nel filtro. Puoi selezionare gli elementi da un elenco o da un intervallo di celle.

![Opzioni specifiche ed elementi selezionati.](./assets/image32.png)

#### From list (Da elenco)

1. Seleziona l’opzione **From list** (Da un elenco) per cercare e selezionare gli elementi dimensione.

   Quando selezioni l’opzione **From List** (Da elenco), l’elenco viene compilato con gli elementi dimensione che hanno il maggior numero di eventi.

   ![Opzione From List ed elementi disponibili.](./assets/image33.png)

   L’elenco **Available items** (Elementi disponibili) è ordinato dagli elementi dimensione con il maggior numero di eventi a quelli con il minore numero.

1. Immetti un termine di ricerca nel campo **Add item** (Aggiungi elemento) per eseguire una ricerca nell’elenco.

1. Per estendere la ricerca agli elementi non incluso negli ultimi 90 giorni di dati, fai clic su **Show items for the last 6 months** (Mostra elementi degli ultimi 6 mesi).

   ![Mostra elementi dell&#39;elenco degli ultimi 6 mesi.](./assets/image34.png)

   Dopo il caricamento dei dati degli ultimi 6 mesi, Report Builder aggiorna il collegamento a **Show items for last 18 months** (Mostra elementi degli ultimi 18 mesi).

1. Seleziona un elemento dimensione.

   Gli elementi dimensione selezionati vengono aggiunti automaticamente all’elenco **Selected items** (Elementi selezionati).

   ![](./assets/image35.png)

   Per rimuovere un elemento dall’elenco, fai clic sull’icona Elimina.

   Per spostare un elemento nell’elenco, trascinalo o fai clic su ... per visualizzare il menu di spostamento.

   ![Elenco degli elementi dimensione.](./assets/image36.png)

1. Fai clic su **Apply** (Applica)

   Report Builder aggiorna l’elenco in base al filtro specifico applicato.

#### From range of cells (Da intervallo di celle)

Seleziona l’opzione **From range of cells** (Da intervallo di celle) per scegliere un intervallo di celle contenente l’elenco degli elementi dimensione che ti interessano.

![Opzione e campo From range of cells (Da intervallo di celle) per selezionare un intervallo di celle.](./assets/image37.png)

Quando selezioni un intervallo di celle, considera le seguenti restrizioni:

- L’intervallo deve avere almeno una cella.
- L’intervallo non può avere più di 50.000 celle.
- L’intervallo deve trovarsi in una singola riga o colonna ininterrotta.

La selezione può contenere celle vuote o con valori che non corrispondono a un elemento dimensione specifico.

### Nella scheda Dimensions (Dimensioni) del generatore di tabelle

Nella scheda **Dimensions** (Dimensioni), fai clic sulla freccia accanto al nome di una dimensione per visualizzare l’elenco degli elementi dimensione.

![Scheda Dimensioni e elenco delle dimensioni.](./assets/dimensions_chevron.png)

Puoi trascinare gli elementi sulla **tabella**, oppure puoi fare doppio clic sul nome di un elemento per aggiungerlo al generatore di **tabelle**.
