---
description: Panoramica dei progetti Workspace con barra dei menu e impostazioni
keywords: Analysis Workspace
title: Panoramica dei progetti
feature: Workspace Basics
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
role: User
source-git-commit: 4942c83e34b129e3718084601d5a733bcebf4de9
workflow-type: ht
source-wordcount: '1487'
ht-degree: 100%

---

# Panoramica dei progetti

Con i progetti Workspace puoi combinare pannelli, visualizzazioni e componenti per preparare analisi da condividere con altri utenti nella tua organizzazione. Prima di iniziare il tuo primo progetto, scopri come poter accedere ai progetti, gestirli e sportarti al loro interno.

Per accedere a progetti in Customer Journey Analytics, seleziona **[!UICONTROL Workspace]**.  Gestione **[!UICONTROL Projects]** elenca tutti i progetti di tua proprietà o che sono stati condivisi con te. Gestione Progetti con l’elenco dei progetti costituisce anche la pagina di destinazione predefinita di Customer Journey Analytics, a meno che questa impostazione non sia stata configurata diversamente nelle Preferenze.

![Pagina di destinazione Progetti con l’elenco dei progetti.](assets/projects.png)


## Area del titolo

Dall’area del titolo ➊ puoi creare un progetto, creare una cartella, modificare le preferenze e mostrare o nascondere un pannello con riquadri aggiuntivi.

* Per mostrare o nascondere un pannello a sinistra che consente di selezionare tra **[!UICONTROL Projects]** e **[!UICONTROL Learning]**, seleziona ![Barra](/help/assets/icons/Rail.svg).
* Il titolo mostra Progetti, a cui può essere aggiunto un percorso alla cartella selezionata. Ad esempio: [!UICONTROL Projects] > **[!UICONTROL Company Folder]**. Selezionando una singola sottocartella, puoi passare direttamente alla cartella desiderata.
* Per visualizzare i riquadri disponibili per un [**[!UICONTROL Blank project]**](create-projects.md), [**[!UICONTROL Blank mobile scorecard]**](/help/mobile-app/create-scorecard.md), [**[!UICONTROL Guided analysis]**](/help/guided-analysis/overview.md), **[!UICONTROL Open the documentation]** e **[!UICONTROL Open release notes]**, seleziona ![ChevronDown](/help/assets/icons/ChevronDown.svg)**[!UICONTROL Show more]**. Per nascondere l’area con i riquadri, seleziona ![ChevronDown](/help/assets/icons/ChevronDown.svg)**[!UICONTROL Show less]**.
* In base a quello che hai scelto di visualizzare, utilizzando il selettore [Mostra](#show-selector) puoi modificare le preferenze ed eseguire azioni sulla cartella corrente visibile in **[!UICONTROL Projects]**:

  | Azione | Descrizione |
  |---|---|
  | **[!UICONTROL Create project]** | Seleziona per [creare un nuovo progetto](create-projects.md). |
  | **[!UICONTROL Create folder]** | Seleziona per [creare una nuova cartella](workspace-folders/create-folders.md). |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Edit preferences]** | [Modifica le preferenze](/help/analysis-workspace/user-preferences.md) per tutti i tuoi progetti. Quando la breadcrumb restituisce uno spazio limitato, questa azione fa parte del sottomenu ![Altro](/help/assets/icons/More.svg). |
  | **[!UICONTROL Add projects]** | Seleziona per [aggiungere progetti](workspace-folders/add-projects.md) alla cartella corrente. Quando la breadcrumb restituisce uno spazio limitato, questa azione fa parte del sottomenu ![Altro](/help/assets/icons/More.svg). |
  | **[!UICONTROL Rename folder]** | [Rinomina](workspace-folders/manage-folders.md#rename-folders) la cartella corrente. |
  | **[!UICONTROL Move folder]** | [Sposta](workspace-folders/manage-folders.md#move-folders) la cartella corrente. |
  | **[!UICONTROL Delete folder]** | [Elimina](workspace-folders/manage-folders.md#delete-folders) la cartella corrente. |




## Elenco dei progetti


L’elenco progetti ➋ mostra tutti i progetti di tua proprietà e che sono stati condivisi con te. L’elenco dispone delle seguenti colonne:

| Colonna | Descrizione |
| --- | --- | 
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Se sono selezionati uno o più progetti, nella parte bassa dell’interfaccia Progetti viene visualizzata una barra blu delle azioni. Per ulteriori dettagli, consulta [Azioni](#actions). |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Seleziona per contrassegnare come preferito ![Star](/help/assets/icons/Star.svg) o non preferito ![StarOutline](/help/assets/icons/StarOutline.svg) un progetto. |
| **[!UICONTROL Title and description]** | Per modificare il progetto, seleziona il collegamento del titolo, che apre il [progetto Workspace](/help/analysis-workspace/home.md). I progetti condivisi con te sono contrassegnati con l’icona ![Condividi](/help/assets/icons/ShareAlt.svg). Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per visualizzare un menu popup con ulteriori dettagli sul progetto. Seleziona ![Altro](/help/assets/icons/More.svg) per aprire un menu di scelta rapida con alcune azioni. Per ulteriori dettagli, consulta [Azioni](#actions). |
| **[!UICONTROL Type]** | Un progetto Workspace, una cartella ![FolderUser](/help/assets/icons/FolderUser.svg) o una [scorecard per dispositivi mobili](/help/mobile-app/home.md). |
| **[!UICONTROL Tags]** | I tag applicati al progetto. |
| Pianificato | Indica se un progetto è programmato per essere inviato tramite e-mail ai destinatari. Le opzioni sono ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL On]** o ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Off]**. Consulta [Inviare dati di progetto ad altri](/help/analysis-workspace/export/t-schedule-report.md). |
| **[!UICONTROL Shared link (anyone)]** | Se un progetto è condiviso con altri, anche con persone che non hanno accesso ad Analysis Workspace. Le opzioni sono ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Active]** o ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Inactive]**. Consulta [Condividere un progetto con qualcuno (accesso non richiesto)](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required) in [Condividere i progetti](/help/analysis-workspace/curate-share/share-projects.md) per ulteriori informazioni. |
| **[!UICONTROL Project Role]** | Il tuo ruolo nel progetto. Le opzioni sono: Modifica, Duplica, Visualizza. Consulta [Ruoli di progetto](/help/analysis-workspace/curate-share/curate.md) per ulteriori informazioni. |
| **[!UICONTROL Data view]** | La visualizzazione dati a cui è associato il progetto. |
| **[!UICONTROL Owner]** | Autore del progetto (tu o l’utente che ha condiviso con te il progetto). |
| **[!UICONTROL Shared with]** | Utenti con cui il progetto è stato condiviso. |
| **[!UICONTROL Last Modified]** | Data e ora dell’ultima volta che il progetto è stato modificato. |
| **[!UICONTROL Last Opened]** | Data e ora dell’ultima apertura del progetto. |
| **[!UICONTROL Project ID]** | L’ID del progetto. |
| **[!UICONTROL Longest Date Range]** | L’intervallo di date più lungo tra i pannelli o le visualizzazioni del progetto. |
| **[!UICONTROL Number of Queries]** | Il numero totale di query contenute nel progetto. |
| **[!UICONTROL Location]** | La cartella in cui risiede il progetto. |

Passa il puntatore del mouse su un’intestazione di colonna per visualizzare ![ChevronDown](/help/assets/icons/ChevronDown.svg) e seleziona dal menu di scelta rapida:

* **[!UICONTROL Sort Ascending]**
* **[!UICONTROL Sort Descending]**
* **[!UICONTROL Resize column]**. Viene visualizzata una linea blu che ti aiuta a ridimensionare la colonna.

### Azioni

Puoi eseguire azioni su uno o più progetti utilizzando il menu di scelta rapida ![Altro](/help/assets/icons/More.svg) o la barra delle azioni blu.

| Icona | Azione | Descrizione |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selezionato]** | Deseleziona i progetti e le cartelle selezionati e rimuovi la barra blu delle azioni. |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina uno o più progetti o cartelle. Viene richiesta una conferma. |
| ![Condividi](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Share]** | Condividi un progetto. Per ulteriori informazioni, consulta [Condividere un progetto](/help/analysis-workspace/curate-share/share-projects.md). |
| ![Modifica](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Rinomina un progetto. Si apre una finestra di dialogo **[!UICONTROL Rename: *del nome del progetto *]**. Immetti un nuovo nome e seleziona **[!UICONTROL Save]**. |
| ![Copia](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Copia uno o più progetti. Al progetto vengono assegnati lo stesso nome e suffisso `(Copy)`. |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL Pin]** o **[!UICONTROL Unpin]** | Fissa o sposta uno o più progetti o cartelle. I progetti e le cartelle fissati vengono visualizzati nella parte superiore dell’elenco e ignorano l’ordinamento specificato. |
| ![ArrowUp](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL Move up]** | Sposta un progetto o una cartella fissati verso l’alto nell’elenco dei progetti. |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL Move down]** | Sposta un progetto o una cartella fissati verso il basso nell’elenco dei progetti. |
| ![Etichetta](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Consente di assegnare tag a uno o più progetti o cartelle. Viene visualizzata la finestra di dialogo **[!UICONTROL Tag Components]** in cui è possibile selezionare uno o più tag. Seleziona **[!UICONTROL Save]** per salvare i tag per i progetti o le cartelle selezionate. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approve]** o **[!UICONTROL Unapprove]** | Consente di approvare o annullare l’approvazione di un progetto. Solo gli amministratori possono approvare i progetti. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export CSV]** | Consente di esportare i progetti selezionati in un file CSV denominato `Project List.csv`. |
| ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL Add Projects]** | Consente di aggiungere uno o più progetti a una cartella selezionata. In **[!UICONTROL Add Projects]** è possibile selezionare uno o più progetti. Seleziona **[!UICONTROL Add]** per aggiungere i progetti alla cartella. Per ulteriori informazioni, consulta [Aggiungere progetti alle cartelle](workspace-folders/add-projects.md#from-inside-a-folder). |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL Move to]** | Consente di spostare in una cartella uno o più progetti selezionati. In **[!UICONTROL Select Folder]** seleziona la cartella in cui spostare il progetto selezionato e seleziona **[!UICONTROL Move]**. Per ulteriori informazioni, consulta [Aggiungere progetti alle cartelle](workspace-folders/add-projects.md#from-the-project-list). |



## Mostra selettore

Puoi cambiare il look and feel dell’interfaccia Progetti utilizzando i selettori **[!UICONTROL Show]** ➌. Il selettore **[!UICONTROL Show]** consente di definire le opzioni disponibili nell’[area del titolo](#title-area) e le colonne visualizzate nell’[elenco dei progetti](#project-list).

* Per modificare le opzioni disponibili per l’[area del titolo](#title-area), seleziona **[!UICONTROL Show]** **[!UICONTROL All projects]** o **[!UICONTROL Show]** **[!UICONTROL Folders & Projects]**.

* Per definire le colonne da visualizzare nell’[elenco dei progetti](#project-list), seleziona ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) e nella finestra di dialogo **[!UICONTROL Customize table]** seleziona o deseleziona le colonne desiderate. Seleziona **[!UICONTROL Apply]** per applicare la personalizzazione. Per ulteriori dettagli sulle colonne, consulta [Elenco dei progetti](#project-list).

## Pannello dei filtri

Puoi filtrare i progetti e le cartelle presenti nell’[elenco dei progetti](#project-list) utilizzando il pannello dei filtri. Per mostrare o nascondere il pannello dei filtri, utilizza l’icona ![Filtro](/help/assets/icons/Filter.svg).

Il pannello dei filtri è costituito dalle sezioni seguenti.

### Tag

| Tag | Descrizione |
|---|---|
| ![Tag](/help/analysis-workspace/build-workspace-project/assets/projects-filters-tags.png){width="300"} | La sezione **[!UICONTROL Tags]** consente di filtrare in base ai tag. <ul><li>Puoi utilizzare ![Ricerca](/help/assets/icons/Search.svg) *Ricerca tag* per cercare i tag in base ai quali applicare il filtro.</li><li>Puoi selezionare più di un tag. I tag disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**2︎⃣**: numero di tag disponibili per i progetti, risultanti dal filtro corrente.</li><li>7︎⃣: numero di progetti associati al tag specifico.</li></ul></li></ul> |


### Visualizzazione dati

| Visualizzazione dati | Descrizione |
|---|---|
| ![Visualizzazioni dati](/help/analysis-workspace/build-workspace-project/assets/projects-filters-dataviews.png){width="300"} | La sezione **[!UICONTROL Data view]** consente di filtrare in base alle visualizzazioni dati. <ul><li>Puoi utilizzare ![Ricerca](/help/assets/icons/Search.svg) *Ricerca visualizzazioni dati* per cercare le visualizzazioni dati in base alle quali applicare il filtro.</li><li>Puoi selezionare più di una visualizzazione dati. Le visualizzazioni dati disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**3︎⃣**: numero di visualizzazioni dati disponibili per i progetti, risultanti dal filtro corrente.</li><li>4︎⃣: numero di progetti associati alla visualizzazione dati specifica.</li></ul></li></ul> |


### Proprietari

| Proprietario | Descrizione |
|---|---|
| ![Proprietari](/help/analysis-workspace/build-workspace-project/assets/projects-filters-owners.png){width="300"} | La sezione **[!UICONTROL Owner]** consente di filtrare in base ai proprietari. <ul><li>Puoi utilizzare ![Ricerca](/help/assets/icons/Search.svg) *Ricerca proprietari* per cercare i proprietari da utilizzare per filtrare.</li><li>Puoi selezionare più di un proprietario. I proprietari disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**3︎⃣**: numero di proprietari disponibili per i progetti, risultanti dal filtro corrente.</li><li>4︎⃣: numero di progetti associati al proprietario specifico.</li></ul></li></ul> |


### Tipo

| Tipo | Descrizione |
|---|---|
| ![Tipo](/help/analysis-workspace/build-workspace-project/assets/projects-filters-type.png){width="300"} | La sezione **[!UICONTROL Type]** consente di filtrare in base al tipo di progetti o cartelle.<ul><li>È possibile scegliere una o più delle opzioni seguenti:<ul><li> **[!UICONTROL folder]**</li><li>**[!UICONTROL Workspace project]**</li><li>**[!UICONTROL Mobile scorecard]**</li></ul> <li>Puoi selezionare più di un altro filtro. Gli altri filtri disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**5︎⃣**: numero di altri filtri disponibili per i progetti risultanti dal filtro corrente.</li><li>4︎⃣: numero di progetti associati all’altro filtro specifico.</li></ul></li></ul> |


### Altri filtri

| Altri filtri | Descrizione |
|---|---|
| ![Altri filtri](/help/analysis-workspace/build-workspace-project/assets/projects-filters-others.png){width="300"} | La sezione **[!UICONTROL Other filters]** ti consente di filtrare in base ad un altro filtro predefinito.<ul><li>È possibile scegliere una o più delle opzioni seguenti:<ul><li> **[!UICONTROL Show all]**</li><li>**[!UICONTROL Shared with me]**</li><li>**[!UICONTROL Mine]**</li><li>**[!UICONTROL Approved]**</li><li>**[!UICONTROL Favorites]**</li></ul> Ciò che puoi selezionare dipende dal tuo ruolo e dalle autorizzazioni.</li><li>Puoi selezionare più di un altro filtro. Gli altri filtri disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**5︎⃣**: numero di altri filtri disponibili per i progetti risultanti dal filtro corrente.</li><li>4︎⃣: numero di progetti associati all’altro filtro specifico.</li></ul></li></ul> |

## Ricerca

Utilizza l’area di ricerca ➎ per cercare progetti e cartelle utilizzando il campo ![Ricerca](/help/assets/icons/Search.svg). Inizia a digitare e l’[elenco progetti](#project-list) filtra automaticamente l’input della ricerca.

L’area Ricerca mostra anche i filtri applicati dal pannello Filtro.

* Per rimuovere un filtro, seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) nel filtro.
* Per rimuovere tutti i filtri, seleziona Cancella tutto.

Se lo spazio è limitato alla visualizzazione dei singoli filtri, visualizzerai **[!UICONTROL Filtering by *x *filtri]**.

* Per rimuovere un filtro:

   1. Utilizza **[!UICONTROL *x *filtri]**![ChevronDown](/help/assets/icons/ChevronDown.svg) per aprire un menu di scelta rapida in cui sono elencati i tipi di filtri e i singoli filtri.
   1. Seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un filtro.


<!--

The Projects page contains the following information: 

>[!NOTE]
>
>Some columns are not displayed by default. To customize the columns you see, click the **Customize table** icon ![Customize table](assets/projects-page-customize-columns-icon.png).

|  Element  | Description  |
|---|---|
| [Edit preferences](/help/analysis-workspace/user-preferences.md) | Manage settings for Analysis Workspace and its related components for all new projects or panels that you create.  |
| [Create folder](/help/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)  | Add a new folder or subfolder to the list of projects and folders. |
| [Create project](/help/analysis-workspace/build-workspace-project/create-projects.md)  | Start a new project from scratch.  |
|  Show more  |Reveals options for creating a blank project or mobile scorecard, [viewing training tutorials](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html), or [viewing release notes](/help/release-notes/latest.md).  |
| Show Folders & Projects| Choose whether to show the folder structure of projects. For more information, see [About Folders in Analytics](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
|  Customize table (icon)  | Allows you to customize the information that shows for each project on the Projects page.  |
|  Name  | Name of the Workspace project.  |
| Type | Indicates whether this is a Workspace Project, a folder, or a [Mobile Scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html). |
|  Tags  |Tags that were applied to the project.  |
| Scheduled | Indicates whether projects are scheduled to be emailed to recipients on a schedule. See [Send project data to others](/help/analysis-workspace/export/t-schedule-report.md). |
| Shared link (anyone) | Projects can be shared with anyone--even with people who don't have access to Analysis Workspace. This column shows whether projects have been shared in this way. See [Share a project with anyone (no login required)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Share projects](/help/analysis-workspace/curate-share/share-projects.md) for more information. |
| Data view | The data view that the project is associated with. |
| [Project Role](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | Indicates your role for the project - owners, edit, duplicate, view. |
|  Owner  | The person who created this project (either you or someone who shared the project with you.)  |
|  Shared with  | Users that the project has been shared with.  |
|  Last Modified  | Date and time when the project was last modified.  |
|  Last Opened  | Date and time when the project was last opened.  |
|  Project ID  | The ID of the project.  |
|  Longest Date Range  | The longest date range of the project.  |
|  Number of Queries  | The total number of queries contained in the project.  |
|  Location  | The folder where the project resides.  |

## Menu bar {#menu-bar}

Within a project, the menu provides options for managing your project, adding components, finding help, and more. Each menu option can also be accessed by keyboard [shortcuts](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![New Project options including the Project, Edit, Insert, Components, Share, and Help options.](assets/menu.png)

|  Menu item  | Description  |
|---|---|
|  Project  | Includes common actions for project management, including New, Open, Save, and Save As. You can also refresh the entire project to retrieve the most recent data and definitions by clicking Refresh Project. [Download project data](/help/analysis-workspace/export/download-send.md) options enable you to export data from Workspace. **Project Info & Settings** (see below) offers many options for managing your project.  |
|  Edit  | Undo or redo your last action. Clear All will reset your project to a blank starting point. |
|  Insert  | Insert new panels or visualizations from this menu. You can also insert new panels and visualizations from the left panel.  |
|  [Components](/help/components/overview.md)  | Create new filters, calculated metric, date range, or alert components from your project. You can also create new components from the left panel. If your component definitions have recently changed, Refresh Components will retrieve the latest definitions. |
|  [Share](/help/analysis-workspace/curate-share/send-schedule-files.md)  | Curate, share and schedule PDF/CSV projects to recipients in your organization.  |
|  Help  | Access help documentation, videos, and the Analytics [Experience League community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community). Manage the visibility of Workspace tips as well as the [debugger](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/apis/using-analysis-workspace-to-build-api-2-requests). Find details about Workspace and factors that impact project [performance](/help/technotes/optimizing-performance.md).  |
|  Share button or Owner  | If you are in an Own or Edit for the project, the Share button in the top-right gives you one-click access to manage your project recipients. If you are in a Duplicate or View role for the project, you will see the project owner's name. |

### Project Info & Settings {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project info & settings]** provides project-level information on the currently active project.

![The Project Info & Settings window.](assets/projectinfo.png)

Settings include:

|  Setting  | Description  |
|---|---|
|  Project Name  | The name given to the project. You can double-click the name to edit it.  |
|  Created By  | Project owner name  |
|  Last Modified  | Date of last modification to the project.  |
|  Tags  |Lists any tags applied to a project for easier categorization.  |
|  Description  | A description is useful for clarifying the purpose of a project. You can double-click the description to edit it.  |
|  Count repeat instances in project  | Specifies whether repeat instances are counted in reports. Note: this setting does not apply to Flow or Fallout visualizations.  |
|  [Project color palette](/help/analysis-workspace/build-workspace-project/color-palettes.md)  | You can change the categorical color palette used in Workspace, by choosing from out-of-the-box palettes that have been optimized for color blindness, or by specifying your custom palette. This feature affects many things in Workspace, including most visualizations.  |
| [View Density](/help/analysis-workspace/build-workspace-project/view-density.md) | Lets you see more data on the screen by reducing the vertical padding of the left panel, freeform tables and cohort tables. |

## Left panel

Within a project, various icons are available in the left panel, and each represents important parts of a project:

* [Panels](/help/analysis-workspace/c-panels/panels.md) ![panels icon](assets/panels-icon.png)

* [Visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)![visualizations icon](assets/visualizations-icon.png)

* [Components](/help/components/overview.md)![components icon](assets/components-icon.png)

* [Data dictionary](/help/components/data-dictionary/data-dictionary-overview.md)![data dictionary icon](assets/data-dictionary-icon.png)

* [Table of contents](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md) ![toc icon](assets/toc-icon.png)

Components (Dimensions, Metrics, Filters, Date Ranges) in the left panel relate to the active panel data view. The active panel is identified by the blue border that surrounds it, and the active data view is listed at the top of the component panel.

![The components relating to the active panel data view for Cross-Industry Demo Data data view.](assets/left-rail.png)

## Project canvas {#canvas}

The project canvas is where you bring together panels, tables, visualizations, and components to build your analysis. A project can contain many panels, and each panel can contain many tables and visualizations.

Panels are helpful when you want to organize your projects according to time periods, data views, or analysis use case. The active panel will have a blue border around it, and determines what components are available in the left panel.

Depending on the starting point you chose for your projects, you will either have a [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) or a [blank panel](/help/analysis-workspace/c-panels/blank-panel.md) in the canvas to begin with. The quickest way to start analyzing is to select one or many components and simply drag & drop them into the project canvas. A table of data will automatically be rendered for you. [Learn more](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) about the different options for building a table, or leverage our [training tutorial](/help/analysis-workspace/home.md) for more guidance on building your first project.

![A Freeform Table for the project.](assets/canvas.png)

## Project Manager {#manager}

Analysis Workspace projects can be managed under **Analytics > Components >  Projects**. The Project Manager shows the projects that a specific user created. You can transfer project ownership to a new user under Admin > Analytics Users & Assets > Transfer Assets.

In Projects Manager, you can add, tag, share, duplicate/copy, and more. Search for a project in the search bar or by using the filter options in the left panel. You can filter by tag, owners, project type and more.

![Project Manager Tags search field and Title search field.](assets/project-manager.png)

The following are common actions in the Projects manager, and can be taken on one or many projects at once:

|  Action  | Description  |
|---|---|
|  Add  | Create a new project from scratch.  |
|  Tag or Approve  | Choose "Tag" or "Approve" to organize your projects and make them easier to search for.  |
|  [Share](/help/analysis-workspace/curate-share/share-projects.md)  | Make a project available to other Analysis Workspace users in your organization.  |
|  Delete  | Delete your project.  |
|  Rename  | Edit the name of your project.  |
|  Copy  | Create a duplicate copy of your project. This creates a new project and project ID. Any shares or schedules tied to the original project will not be copied. |
|  Export to CSV  | Download your project as a CSV file, which includes plain-text data.  |

-->

