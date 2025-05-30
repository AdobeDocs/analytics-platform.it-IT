---
title: Gestire gli intervalli di date
description: Condividi, rinomina o elimina intervalli di date in Analysis Workspace.
feature: Calendar
exl-id: 694758c4-d740-4fd7-9fb0-3ff7f6b25a3d
role: User
source-git-commit: 6a279ac39e6b94200ff93ac1a3796d202e6349c7
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 9%

---

# Gestire gli intervalli di date


È possibile condividere, filtrare, assegnare tag, approvare, copiare, condividere ed eliminare intervalli di date e contrassegnarli come preferiti da un&#39;interfaccia di gestione centrale di [!UICONTROL Date ranges]. Per gestire gli intervalli di date:

* Seleziona **[!UICONTROL Components]** nell&#39;interfaccia principale, quindi seleziona **[!UICONTROL Date ranges]**.


## Gestione intervalli di date

Il gestore degli intervalli di date dispone dei seguenti elementi dell’interfaccia:

![Interfaccia intervalli date](assets/date-ranges-manager.png)

### Elenco intervalli di date

Nell’elenco degli intervalli di date vengono visualizzati tutti gli intervalli di date. L’elenco include le colonne seguenti:

| Colonna | Descrizione |
| --- | --- | 
| ![ContornoStella](/help/assets/icons/StarOutline.svg) | Seleziona questa opzione per favorire ![Star](/help/assets/icons/Star.svg) o per non favorire ![StarOutline](/help/assets/icons/StarOutline.svg) un intervallo di date. |
| **[!UICONTROL Title and description]** | Per modificare il titolo e la descrizione, seleziona il collegamento del titolo, che apre il generatore di intervalli di date [1&rbrace;.](/help/components/date-ranges/create.md#date-range-builder) |
| **[!UICONTROL Owner]** | Proprietario dell’intervallo di date. |
| **[!UICONTROL Tags]** | I tag per questo intervallo di date. |
| **[!UICONTROL Shared with]** | Gli individui o i gruppi con cui hai condiviso l’intervallo di date. Selezionare per aprire la finestra di dialogo **[!UICONTROL Share Date range]**. |
| **[!UICONTROL Date modified]** | Visualizza la data e l’ora dell’ultima modifica apportata all’intervallo di date. |

{style="table-layout:auto"}

Utilizzare ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per specificare quali colonne si desidera visualizzare.

### Barra delle azioni

È possibile eseguire azioni sugli intervalli di date utilizzando la barra delle azioni di. La barra delle azioni contiene le azioni seguenti:

| Icona | Azione | Descrizione |
|:---:|---|---|
| ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Add]** | Aggiungi un altro intervallo di date utilizzando il generatore di intervalli di date [1&rbrace;.](create.md#date-range-builder) |
| ![Ricerca](/help/assets/icons/Search.svg) | [!UICONTROL *Cerca per titolo*] | Se nell’elenco non è selezionato alcun intervallo di date, cerca gli intervalli di date utilizzando questo campo di ricerca. |
| ![Etichetta](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Assegna tag agli intervalli di date selezionati. Nella finestra di dialogo **[!UICONTROL Tag Date range]**, seleziona o deseleziona i tag per gli intervalli di date selezionati. Selezionare **[!UICONTROL Save]** per salvare i tag per gli intervalli di date selezionati. |
| ![Condividi](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Share]** | Condividi gli intervalli di date selezionati. Nella finestra di dialogo **[!UICONTROL Share Date range]**, puoi ![Cercare](/help/assets/icons/Search.svg) *Cercare singoli utenti o gruppi* oppure selezionare **[!UICONTROL Organization]** o **[!UICONTROL Groups]**. Selezionare **[!UICONTROL Save]** per salvare i dettagli di condivisione per gli intervalli di date selezionati. |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina gli intervalli di date selezionati. Viene richiesta una conferma. |
| ![Modifica](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Rinomina un singolo intervallo di date selezionato. Se questa opzione è selezionata, puoi rinominare l’intervallo di date in linea. |
| ![CerchioSegno di spunta](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approve]** | Approva gli intervalli di date selezionati. |
| ![Copia](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Copia gli intervalli di date selezionati. Vengono creati nuovi intervalli di date con lo stesso nome e suffisso (Copia) |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Esporta gli intervalli di date selezionati in un file `Date ranges List.csv`. |

### Barra dei filtri attiva

La barra dei filtri mostra i filtri attivi (se presenti). È possibile rimuovere rapidamente un filtro utilizzando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se sono specificati più filtri, utilizzare **[!UICONTROL Remove all]** per rimuovere tutti.

### Pannello Filtro

È possibile filtrare gli intervalli di date utilizzando il pannello sinistro di **[!UICONTROL Filter]** per i valori di data di inizio e fine del ciclo di vita. Nel pannello dei filtri viene visualizzato il tipo di filtro e il numero di intervalli di date che rispettano il filtro. Seleziona ![Filtro](/help/assets/icons/Filter.svg) per attivare/disattivare la visualizzazione del pannello dei filtri.

Per filtrare l’elenco dei filtri:

1. Seleziona ![Filtro](/help/assets/icons/Filter.svg) per aprire il pannello Filtri. Se hai bisogno di più spazio per l&#39;elenco Filtri, puoi selezionare ancora ![Filtro](/help/assets/icons/Filter.svg) per chiudere il pannello.
1. Puoi filtrare gli intervalli di date utilizzando una qualsiasi delle [sezioni filtro](#filter-sections) disponibili.

   >[!INFO]
   >
   >*Elementi* si riferiscono agli elementi dell&#39;intervallo di date visualizzati nell&#39;[Elenco intervalli di date](#date-ranges-list).
   > 

#### Filtra sezioni

{{tagfiltersection}}
{{ownerfiltersection}}
{{otherfiltersfiltersection}}


L&#39;[elenco di intervalli di date](#date-ranges-list) viene aggiornato automaticamente in base alla configurazione del filtro. Puoi visualizzare i filtri configurati nella [barra dei filtri attiva](#active-filter-bar).


## Modificare gli intervalli di date

È possibile modificare un intervallo di date in due modi:

* In un progetto Workspace, utilizza l&#39;icona [Informazioni componente](/help/components/use-components-in-workspace.md#component-info).

* Nell&#39;elenco [[!UICONTROL Date ranges]](#date-ranges-list), selezionare il titolo dell&#39;intervallo di date.

Utilizza il generatore di intervalli di date [1&rbrace; per modificare l&#39;intervallo di date.](/help/components/date-ranges/create.md#date-range-builder)




Utilizza il gestore degli intervalli di date per condividere, rinominare o eliminare intervalli di date. Per raggiungere il gestore delle date:

1. Accedi a [analytics.adobe.com](https://analytics.adobe.com) utilizzando le credenziali Adobe ID.
1. Passa a [!UICONTROL Components] > [!UICONTROL Date Ranges].


<!--

## Interface

![Date Ranges with Example range highlighted.](../assets/date-range-ui.png)

The date range manager includes the following options:

* **Add**: Create a new date range. See [create a date range](create.md) for more information.
* **Search by title**: Search for a date range by title. Results are filtered based on text entered here.
* **Filter**: Filter date ranges using the left column. You can filter by custom tag, owner, created by you, your favorites, approved, or shared with you. You can also search for desired filters.
* **Favorite**: Click the ![star](../assets/star.png) icon next to a date range to add it to your favorites.
* **Customize columns**: Click the ![columns](../assets/columns.png) icon to show or hide columns in the date range manager.

Click the checkbox next to one or more date ranges for more options.

* **Tag**: Apply a tag to all selected date ranges. Tags help you organize date ranges, and let you filter them using the left column.
* **Share**: Share a date range to other Experience Cloud users. If you are a product administrator, you can also share to the entire organization or groups. Date ranges that are shared to other users in your organization include a ![shared](../assets/shared.png) icon next to the title.
* **Delete**: Permanently delete the selected date range(s).
* **Rename**: If a single date range is selected, you can change its title.
* **Approve**: If you are a product admin, you can add a stamp of approval to a date range. Approved date ranges inform users in your organization that they are 'official', differentiating them from date ranges created by other users in your organization. Approved date ranges include a ![approved](../assets/approved.png) icon next to the title.
* **Unapprove**: If you are a product admin and select a date range that is already approved, you can unapprove it.
* **Copy**: Create a copy of the selected date range(s). Copying date ranges appends `(Copy)` to the end of the title of the newly copied date range(s).
* **Export to CSV**: Exports all selected date ranges into a CSV file. Columns in the resulting CSV file include all visible columns in the date range manager.
-->