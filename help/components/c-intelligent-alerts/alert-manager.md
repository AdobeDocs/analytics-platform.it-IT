---
description: Crea, modifica o elimina gli avvisi.
title: Gestisci avvisi
feature: Workspace Basics
role: User, Admin
exl-id: 174c3ebd-a77b-4403-ae9a-bb0cff4bcca6
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 18%

---

# Gestire gli avvisi


È possibile filtrare, assegnare tag, eliminare, rinominare, copiare, abilitare, disabilitare gli avvisi di rinnovo ed esportare gli avvisi da un&#39;interfaccia di gestione centrale di [!UICONTROL Alerts]. Per gestire gli avvisi:

* Seleziona **[!UICONTROL Components]** nell’interfaccia principale, quindi seleziona **[!UICONTROL Alerts]**.

La gestione avvisi è strutturata come la [gestione segmenti](/help/components/filters/manage-filters.md) e la [gestione metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-manager.md).


## Gestione avvisi

Gestione avvisi dispone dei seguenti elementi dell’interfaccia:

![Interfaccia filtri](assets/alerts-manager.png)

### Elenco avvisi

Nell&#39;elenco avvisi vengono visualizzati tutti gli avvisi di cui sei proprietario, quelli che hanno un ambito per tutti i tuoi progetti e quelli condivisi con te. L’elenco dispone delle seguenti colonne:

| Colonna | Descrizione |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Seleziona questa opzione per favorire ![Star](/help/assets/icons/Star.svg) o per non favorire ![StarOutline](/help/assets/icons/StarOutline.svg) un avviso. |
| **[!UICONTROL Title and description]** | Per modificare l&#39;avviso, selezionare il collegamento del titolo, che apre il generatore di [avvisi](alert-builder.md#alert-builder). |
| **[!UICONTROL Type]** | Indica se l&#39;avviso è un avviso di dati di Customer Journey Analytics o un avviso di utilizzo di chiamate al server. |
| **[!UICONTROL Enabled]** | Indica se l&#39;avviso è abilitato o disabilitato. |
| **[!UICONTROL Data view]** | Visualizzazioni dati a cui si applica questo avviso. |
| **[!UICONTROL Owner]** | Proprietario dell&#39;avviso. In qualità di non amministratore, puoi visualizzare solo gli avvisi di tua proprietà o che sono condivisi con te. |
| **[!UICONTROL Tags]** | Tag per l&#39;avviso. |
| **[!UICONTROL Expiration Date]** | La data e l’ora in cui l’avviso è impostato per scadere. |
| **[!UICONTROL Date modified]** | Data e ora dell’ultima modifica apportata all’avviso. |

<!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

Utilizza ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per specificare quali colonne vuoi visualizzare.

### Barra delle azioni

È possibile eseguire azioni sugli avvisi utilizzando la barra delle azioni di. La barra delle azioni contiene le azioni seguenti:

| Icona | Azione | Descrizione |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Add]** | Aggiungere un altro avviso utilizzando [Generatore di avvisi](alert-builder.md#alert-builder). |
| ![Ricerca](/help/assets/icons/Search.svg) | [!UICONTROL *Ricerca per titolo*] | Se nell&#39;elenco non è selezionato alcun avviso, cercare gli avvisi utilizzando questo campo di ricerca. |
| ![Etichetta](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Assegna tag agli avvisi selezionati. Nella finestra di dialogo **[!UICONTROL Tag Alert]**, seleziona o deseleziona i tag per gli avvisi selezionati. Selezionare **[!UICONTROL Save]** per salvare i tag per gli avvisi selezionati. |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina gli avvisi selezionati. Viene richiesta una conferma. |
| ![Modifica](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Rinominare un singolo avviso selezionato. Se questa opzione è selezionata, è possibile rinominare l&#39;avviso in linea. |
| ![Copia](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Copia l’avviso selezionato. Vengono creati nuovi avvisi con lo stesso nome e suffisso `(Copy)`. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Enable]** o **[!UICONTROL Disable]** | Attiva o disattiva gli avvisi selezionati. |
| ![Aggiorna](/help/assets/icons/Refresh.svg) | **[!UICONTROL Renew]** | Rinnova la data di scadenza dell’avviso. La data di scadenza si estende per 1 anno dal giorno in cui è stata selezionata questa opzione, indipendentemente dalla data di scadenza originale. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Esporta gli avvisi in un file `Alerts List.csv`. |


### Barra dei filtri attivi

La barra dei filtri mostra i filtri attivi applicati dal pannello dei filtri all’elenco degli avvisi (se presenti). Puoi rimuovere rapidamente un filtro utilizzando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se sono specificati più filtri, puoi rimuoverli tutti utilizzando **[!UICONTROL Remove all]**.


### Pannello dei filtri

È possibile filtrare l&#39;elenco degli avvisi utilizzando il ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** pannello sinistro di controllo. Nel pannello dei filtri viene visualizzato il tipo di filtro e il numero di avvisi che rispettano il filtro specifico.

{{filterspanel}}


#### Sezione filtro tag

{{tagfiltersection}}


#### Sezione filtro visualizzazione dati

{{dataviewfiltersection}}


#### Sezione filtro Proprietari

{{ownerfiltersection}}


#### Sezione filtro di stato abilitato

{{enabledstatusfiltersection}}


#### Digita la sezione del filtro

{{typefiltersection}}


#### Sezione filtro Altri filtri

{{otherfiltersfiltersection}}



## Modifica avvisi

È possibile modificare un avviso

* Nell&#39;elenco [[!UICONTROL Alert]](#alerts-list), selezionare il titolo dell&#39;avviso.

Per modificare l&#39;avviso, utilizzare [Generatore di avvisi](alert-builder.md#alert-builder).

## Risolvere i problemi relativi a un avviso

Durante la risoluzione di un problema relativo a un avviso, fornisci il numero JID (Job Instance ID) al supporto Adobe. Il numero JID si trova in fondo alla notifica e-mail di avviso ricevuta.

![E-mail avviso](assets/alerts-email.PNG)
