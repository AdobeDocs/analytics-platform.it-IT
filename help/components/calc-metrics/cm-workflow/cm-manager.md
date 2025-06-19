---
description: Il gestore delle metriche calcolate consente di condividere, filtrare, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferiti.
title: Gestore metriche calcolate
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: b3c7ceedec7b3f6a916e97bab38fd55f1d6c7f51
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 30%

---

# Gestire le metriche calcolate

È possibile condividere, filtrare, assegnare tag, approvare, rinominare, copiare, eliminare, esportare le metriche calcolate e contrassegnarle come preferite da un&#39;interfaccia di gestione centrale di [!UICONTROL Calculated metrics]. Per gestire le metriche calcolate:


* Seleziona **[!UICONTROL Components]** nell’interfaccia principale, quindi seleziona **[!UICONTROL Calculated metrics]**.


## Gestione metriche calcolate

Il gestore delle metriche calcolate dispone dei seguenti elementi dell’interfaccia:


![Interfaccia del gestore delle metriche calcolate](assets/calculated-metrics-manager.png)

### Elenco delle metriche calcolate

Nell&#39;elenco delle metriche calcolate ➊ vengono visualizzate tutte le metriche calcolate di tua proprietà o che sono state condivise con te. L’elenco dispone delle seguenti colonne:

<!-- I think this table incorrectly talks about quick calculated metrics -->

| Colonna | Descrizione |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Seleziona questa opzione per favorire ![Star](/help/assets/icons/Star.svg) o sfavorire ![StarOutline](/help/assets/icons/StarOutline.svg) una metrica calcolata. Vedi [Segna la metrica calcolata come preferita](/help/components/segments/seg-favorite.md) |
| **[!UICONTROL Title and description]** | Per modificare la metrica calcolata, selezionare il collegamento del titolo, che apre il generatore di metriche calcolate [](cm-build-metrics.md). Una metrica calcolata condivisa è indicata con ![Condividi](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Data view]** | Le visualizzazioni dati a cui si applica questa metrica calcolata. |
| **[!UICONTROL Owner]** | Proprietario della metrica calcolata. In quanto utente, puoi visualizzare solo le annotazioni che possiedi o quelle che sono state condivise con te. |
| **[!UICONTROL Tags]** | Elenca i tag per questa metrica calcolata. |
| **[!UICONTROL Shared with]** | Elenca con quanti singoli utenti o gruppi hai condiviso la metrica calcolata. Seleziona per aprire la finestra di dialogo **[!UICONTROL Share Calculated metric]**. Per ulteriori informazioni, vedere [Condividi metriche calcolate](cm-sharing.md). |
| **[!UICONTROL Date modified]** | La data e l’ora dell’ultima modifica apportata alla metrica calcolata. |
| **[!UICONTROL Used in]** | Mostra dove sono attualmente utilizzate le metriche calcolate e quante volte in ciascuna area. <p>Ad esempio, se la metrica calcolata viene utilizzata in 40 progetti e 2 avvisi, il valore di questa colonna viene visualizzato come [!UICONTROL **42 componenti**]. <p>Seleziona il valore in questa colonna per visualizzare il raggruppamento in cui vengono utilizzate le metriche calcolate (ad esempio, [!UICONTROL **Progetti (40)**], [!UICONTROL **Scorecard per dispositivi mobili (2)**]). Inoltre, puoi visualizzare l’elenco degli elementi in cui vengono utilizzate le metriche calcolate. Ad esempio, per visualizzare l’elenco dei progetti in cui vengono utilizzati, seleziona il collegamento [!UICONTROL **Progetti (40)**].</p><p>Ciascuna delle seguenti aree mostra il numero di istanze di metriche calcolate utilizzate in quell’area:</p> <ul><li>[!UICONTROL **Progetti**]<p>Contiene le metriche calcolate create [nel generatore di metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) e disponibili per tutti i progetti.</p></li><li>[!UICONTROL **Componenti ad hoc**]<p>Contiene le metriche calcolate create [come metriche calcolate rapide](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) e disponibili solo all&#39;interno di un singolo progetto.</p></li><li>[!UICONTROL **Progetti programmati**]</li><li>[!UICONTROL **Scorecard per dispositivi mobili**]</li><li>[!UICONTROL **Annotazioni**]</li><li>[!UICONTROL **Report Builder**]<p>Selezionando questa opzione viene scaricato un file CSV con le seguenti colonne di dati:</p><ul><li>Nome Report Builder</li><li>Ultimo accesso</li><li>ID utente IMS ultimo accesso</li><li>Nome utente ultimo accesso</li></ul></li></ul><p>Queste informazioni possono essere utili per determinare se un componente è utile per gli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato.</p><p>Quando visualizzi questa colonna, prendi in considerazione quanto segue:</p><ul><li>Questa informazione è disponibile solo per gli amministratori di sistema.</li><li>La colonna [!UICONTROL **Usato in**] non viene visualizzata per impostazione predefinita. Utilizza ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per configurare la visualizzazione di questa colonna.</li><li>Queste informazioni non includono l’utilizzo dall’API o da Data Warehouse.</li><li>Se nella colonna non sono presenti dati per un determinato componente ma è presente la data [!UICONTROL **Ultimo utilizzo**], è possibile che il componente sia stato utilizzato in un&#39;analisi senza essere stato salvato.</li><li>Le informazioni sull’utilizzo sono disponibili a partire da settembre 2023.</li></ul><p>Puoi utilizzare il [dizionario dei dati](/help/components/data-dictionary/data-dictionary-overview.md) insieme a queste informazioni per tenere traccia di come vengono utilizzati i componenti nell’organizzazione e per comprenderne meglio il funzionamento.</p> |
| **[!UICONTROL Last Used]** | Data dell’ultimo utilizzo della metrica calcolata. |

{style="table-layout:auto"}

Utilizza ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per specificare quali colonne vuoi visualizzare.

### Barra delle azioni

È possibile eseguire azioni sui filtri utilizzando la barra delle azioni ➋. La barra delle azioni contiene le azioni seguenti:

| Icona | Azione | Descrizione |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Add]** | Aggiungere un&#39;altra metrica calcolata utilizzando il generatore di metriche calcolate [](cm-build-metrics.md). |
| ![Ricerca](/help/assets/icons/Search.svg) | [!UICONTROL *Ricerca per titolo*] | Se nell’elenco non è selezionata alcuna metrica calcolata, cerca i filtri utilizzando questo campo di ricerca. |
| ![Etichetta](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Assegna tag alle metriche calcolate selezionate. Nella finestra di dialogo **[!UICONTROL Tag Calculated metric]**, seleziona o deseleziona i tag per la metrica calcolata selezionata. Selezionare **[!UICONTROL Save]** per salvare i tag per le metriche calcolate selezionate. Per ulteriori informazioni, vedere [Assegnare tag alle metriche calcolate](cm-tagging.md). |
| ![Condividi](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Share]** | Condividi le metriche calcolate selezionate. Nella finestra di dialogo **[!UICONTROL Share Calculated metrics]**, puoi effettuare una ![Ricerca](/help/assets/icons/Search.svg) *Ricerca di singoli utenti o gruppi* oppure puoi selezionare **[!UICONTROL Organization]** o **[!UICONTROL Groups]**. Selezionare **[!UICONTROL Save]** per salvare i dettagli di condivisione per le metriche calcolate selezionate. Per ulteriori informazioni, vedere [Condividi metriche calcolate](cm-sharing.md). |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina le metriche calcolate selezionate. Viene richiesta una conferma. |
| ![Modifica](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Rinomina una singola metrica calcolata selezionata. Se selezionata, puoi rinominare la metrica calcolata in linea. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approve]** | Approva le metriche calcolate selezionate. Vedi [Approvare le metriche calcolate](cm-approving.md). |
| ![Copia](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Copia le metriche calcolate selezionate. Le nuove metriche calcolate vengono create con lo stesso nome e suffisso `(Copy)` |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Esporta le metriche calcolate in un file `Calculated  metric List.csv`. |

### Barra dei filtri attivi

La barra dei filtri ➌ mostra i filtri attivi applicati dal pannello dei filtri all&#39;elenco delle metriche calcolate (se presenti). Puoi rimuovere rapidamente un filtro utilizzando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se sono specificati più filtri, puoi rimuoverli tutti utilizzando **[!UICONTROL Remove all]**.

### Pannello dei filtri

Puoi filtrare l&#39;elenco delle metriche calcolate utilizzando il ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** pannello sinistro ➍. Nel pannello dei filtri viene visualizzato il tipo di filtro e il numero di metriche calcolate che rispettano il filtro specifico. Seleziona ![Filtro](/help/assets/icons/Filter.svg) per attivare/disattivare la visualizzazione del pannello dei filtri.

Per ulteriori informazioni, vedere [Filtrare l&#39;elenco delle metriche calcolate](cm-filter.md).


<!-- OLD CONTENT 

The Calculated metric manager shows you all the filters you own and that have been shared with you. Admin-level users can see all custom metrics in the organization. This overview presents the user interface and the capabilities of the Calculated metric manager.

![Calculated metrics window showing available filters.](assets/calc-metric-manager.png)

## Access the Calculated metrics manager

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Calculated metrics**].

## Available actions in the Calculated metrics manager

In the Calculated metrics manager, you can:

* [Filter calculated metrics](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Approve calculated metrics](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Tag calculated metrics](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Share calculated metrics](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Export a calculated metric to a CSV file. 

* [Copy calculated metrics](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Delete calculated metrics

## Configure columns

You can configure the information displayed for each calculated metric in the Calculated metrics manager by configuring the columns that are displayed.

To configure the visible columns in the Calculated metrics manager:

1. In Customer Journey Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Calculated metrics]**. 

1. In the Calculated metrics manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Calculated metrics manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Favorites  | Displays star icons next to each calculated metric, allowing you to mark calculated metrics as favorites. For more information, see [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Title and description | These values are provided in the Calculated metric builder. To edit the title and description, select the title link to open the Calculated metric builder.  |
   | Report suite | Indicates in which report suite the metric was last saved.  |
   | Owner | Indicates who owns the custom metric. As a non-admin, you can see only metrics you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the metric, either by you or by people who shared the calculated metric with you.  |
   | Shared with | Lists individuals or groups (admin only) or All (admin only) that you shared the calculated metric with. <p>When a calculated metric is being shared, a share icon displays next to the calculated metric name.</p>  |
   | Date modified | Indicates the date when the custom metric was last modified.  |
   | Used in | Shows where calculated metrics are currently being used, and how many times they are being used in each area. <p>For example, if the calculated metric is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**]. <p>Select the value in this column to see the breakdown of where the calculated metrics are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Furthermore, you can view the list of items where the calculated metrics are being used. For example, to see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of calculated metrics being used in that area:</p> <ul><li>[!UICONTROL **Projects**]<p>Contains calculated metrics that were [created in the calculated metric builder](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains calculated metrics that were [created as quick calculated metrics ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a calculated metric includes another calculated metric in its definition, any use of that calculated metric is not shown in the [!UICONTROL **Used in**] column. If a calculated metric is included in the definition of another type of component (such as a segment), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p> |
   | Last used | Shows the date when the calculated metric was last used in any of the following component types: <ul><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, or whether it should be deleted.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |

   {style="table-layout:auto"}

-->