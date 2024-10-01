---
title: Gestire le annotazioni
description: Come gestire le annotazioni in Workspace.
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: 01f862997503cb36502145eddb47873bc7cb28fe
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 5%

---

# Gestire le annotazioni

È possibile condividere, filtrare, assegnare tag, approvare, copiare, eliminare annotazioni e contrassegnarle come preferite da un&#39;interfaccia di gestione centrale di [!UICONTROL Annotations]. Per gestire le annotazioni:

* Seleziona **[!UICONTROL Components]** nell&#39;interfaccia principale, quindi seleziona **[!UICONTROL Annotations]**.


>[!NOTE]
>
>Le annotazioni create all&#39;interno di un progetto Workspace specifico non vengono visualizzate nel gestore [!UICONTROL Annotations], a meno che l&#39;annotazione non sia stata resa disponibile per tutti i progetti.
>

## Gestione annotazioni

Il gestore Annotazioni dispone dei seguenti elementi dell’interfaccia:

![Interfaccia Annotazioni](assets/annotations-manager.png)

### Elenco annotazioni

Nell’elenco delle annotazioni vengono visualizzate tutte le annotazioni di cui sei proprietario, quelle con ambito specifico per tutti i tuoi progetti e quelle condivise con te. L’elenco include le colonne seguenti:

| Colonna | Descrizione |
| --- | --- | 
| ![ContornoStella](/help/assets/icons/StarOutline.svg) | Seleziona questa opzione per favorire ![Star](/help/assets/icons/Star.svg) o per non favorire ![StarOutline](/help/assets/icons/StarOutline.svg) un&#39;annotazione. |
| **[!UICONTROL Title and description]** | Forniti nel generatore di annotazioni. Per modificare il titolo e la descrizione, seleziona il collegamento del titolo. Verrà aperto il generatore di [annotazioni](/help/components/annotations/create-annotations.md#annotation-builder). Un&#39;annotazione condivisa è indicata con ![Condividi](/help/assets/icons/Share.svg). |
| **[!UICONTROL Data view]** | Visualizzazioni dati a cui si applica questa annotazione. |
| **[!UICONTROL Owner]** | Proprietario dell’annotazione. In qualità di utente, puoi visualizzare solo le annotazioni di tua proprietà o quelle condivise con te. |
| **[!UICONTROL Applied date range]** | Data o intervallo di date a cui viene applicata l’annotazione. |
| **[!UICONTROL Tags]** | I tag per questa annotazione. |
| **[!UICONTROL Shared with]** | Gli individui o i gruppi con cui hai condiviso l’annotazione. Selezionare per aprire la finestra di dialogo **[!UICONTROL Share Component]**. |
| **[!UICONTROL Date modified]** | Visualizza la data e l’ora dell’ultima modifica apportata all’annotazione. |

{style="table-layout:auto"}

Utilizzare ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per specificare quali colonne si desidera visualizzare.

### Barra delle azioni

È possibile eseguire azioni sulle annotazioni utilizzando la barra delle azioni di. La barra delle azioni contiene le azioni seguenti:

| Azione | Descrizione |
|---|---|
| ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Aggiungere un&#39;altra annotazione utilizzando [Generatore di annotazioni](create-annotations.md#annotation-builder). |
| ![Cerca](/help/assets/icons/Search.svg) [!UICONTROL *Cerca per titolo*] | Se nell’elenco non è selezionata alcuna annotazione, cerca le annotazioni utilizzando questo campo di ricerca. |
| ![Etichetta](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Assegna tag alle annotazioni selezionate. Nella finestra di dialogo **[!UICONTROL Tag Component]**, seleziona o deseleziona i tag per le annotazioni selezionate. Selezionare **[!UICONTROL Save]** per salvare i tag per le annotazioni selezionate. |
| ![Condividi](/help/assets/icons/Share.svg) **[!UICONTROL Share]** | Condividi le annotazioni selezionate. Nella finestra di dialogo **[!UICONTROL Share Component]**, puoi ![Cercare](/help/assets/icons/Search.svg) *Cercare singoli utenti o gruppi* oppure selezionare **[!UICONTROL Organization]** o **[!UICONTROL Groups]**. Selezionare **[!UICONTROL Save]** per salvare i dettagli di condivisione per le annotazioni selezionate. Vedi [Condividi annotazioni](#share-annotations) per ulteriori dettagli. |
| ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Elimina le annotazioni selezionate. Viene richiesta una conferma. |
| ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Rinominare una singola annotazione selezionata. Se questa opzione è selezionata, è possibile rinominare l’annotazione in linea. |
| ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** | Copia le annotazioni selezionate. Le nuove annotazioni vengono create con lo stesso nome e suffisso (Copia) |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Esporta le annotazioni in un file `Annotations List.csv`. |

### Barra dei filtri attiva

La barra dei filtri mostra i filtri attivi (se presenti). È possibile rimuovere rapidamente un filtro utilizzando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se sono specificati più filtri, è possibile rimuovere tutti utilizzando **[!UICONTROL Remove all]**.

### Pannello Filtro

Puoi filtrare le annotazioni utilizzando il pannello sinistro ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]**. Nel pannello dei filtri viene visualizzato il tipo di filtro e il numero di annotazioni che lo rispettano. Seleziona ![Filtro](/help/assets/icons/Filter.svg) per attivare/disattivare la visualizzazione del pannello dei filtri.

Per filtrare l’elenco dei filtri:

1. Seleziona ![Filtro](/help/assets/icons/Filter.svg) per aprire il pannello Filtri. Se hai bisogno di più spazio per l&#39;elenco Filtri, puoi selezionare ancora ![Filtro](/help/assets/icons/Filter.svg) per chiudere il pannello.
1. Puoi filtrare le annotazioni utilizzando una qualsiasi delle [sezioni filtro](#filter-sections) disponibili.

   >[!INFO]
   >
   >*Elementi* fanno riferimento agli elementi di annotazione visualizzati nell&#39;elenco [Annotazioni](manage-annotations.md#annotations-list).
   > 

#### Filtra sezioni

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


L&#39;[elenco Annotazioni](manage-annotations.md#annotations-list) viene aggiornato automaticamente in base alla configurazione del filtro. Puoi visualizzare i filtri configurati nella [barra dei filtri attiva](manage-annotations.md#active-filter-bar).


## Modificare le annotazioni

È possibile modificare un’annotazione in due modi:

* In un progetto Workspace, utilizza l&#39;icona [Informazioni componente](/help/components/use-components-in-workspace.md#component-info).

* Nell&#39;elenco [[!UICONTROL Annotations]](#annotations-list), selezionare il titolo dell&#39;annotazione.

Per modificare l&#39;annotazione si utilizza il [Generatore di annotazioni](/help/components/annotations/create-annotations.md#annotation-builder).

## Condividere le annotazioni

Quando si condividono annotazioni o si utilizzano annotazioni condivise con l’utente, si applica quanto segue:

* Le annotazioni solo progetto in un progetto condiviso con altri utenti vengono visualizzate per tali utenti. Gli utenti non possono modificare o eliminare queste annotazioni solo progetto.
* Se salvi un’annotazione e la condividi direttamente con un utente, quest’ultimo può modificarla ed eliminarla solo se dispone dei diritti di amministratore.

* Se un progetto è condiviso con te, le annotazioni create in quel progetto vengono visualizzate solo in quel progetto. Se un’annotazione viene condivisa direttamente con te, viene visualizzata in tutti i progetti in cui è possibile visualizzarla.

## Annotazioni e fusi orari

Tutte le annotazioni vengono create con una marca temporale, ma non con informazioni sull’ora o sul fuso orario. Al momento del rapporto, viene utilizzato il fuso orario della visualizzazione dati configurata per il pannello.
