---
description: Descrive le funzioni della nuova pagina di destinazione.
title: Pagina di destinazione di Customer Journey Analytics
role: User, Admin
feature: Basics
exl-id: 65c7bc26-7160-4bba-b764-5b0fa8686fca
source-git-commit: 1741b2f3fc0588aaf0f403c6f3863ce837e376e9
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 29%

---

# Pagina di destinazione di Customer Journey Analytics

La pagina di destinazione di Customer Journey Analytics include le seguenti schede secondarie:

**[!UICONTROL Progetti]**: progettazioni personalizzate che combinano componenti dati, tabelle e visualizzazioni create dall&#39;utente o create e condivise da un altro utente. [!UICONTROL Progetti] fa riferimento anche a progetti vuoti e scorecard per dispositivi mobili vuote.

**[!UICONTROL Modelli]**: include i modelli forniti da Adobe e tutti i modelli specifici della tua organizzazione.

**[!UICONTROL Apprendimento]**: contiene presentazioni video pratiche, tutorial e collegamenti alla documentazione. Contiene inoltre informazioni sull’aggiornamento da Adobe Analytics a Customer Journey Analytics e uno strumento per generare in modo dinamico i passaggi di aggiornamento specifici dell’organizzazione.

![Barra a sinistra della pagina di destinazione di CJA](assets/cja-landing-page-left-rail.png)


>[!BEGINSHADEBOX]

Per un video demo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Pagina di destinazione in Analysis Workspace](https://experienceleague.adobe.com/it/docs/customer-journey-analytics-learn/tutorials/cja-basics/customer-journey-analytics-landing-page){target="_blank"}.

{{videoaa}}

>[!ENDSHADEBOX]


## Progetti

La sezione **[!UICONTROL Progetti]** nella barra a sinistra funge da home page per la scheda [!UICONTROL **Workspace**].

Per accedere ai progetti in Customer Journey Analytics:

1. Seleziona la scheda [!UICONTROL **Workspace**].

1. Seleziona [!UICONTROL **Progetti**] nella barra a sinistra.

La sezione Progetti mostra la cartella Azienda, tutte le cartelle personali create, i progetti Workspace e le scorecard per dispositivi mobili. In questa pagina puoi visualizzare, creare e modificare cartelle, progetti e scorecard per dispositivi mobili. Per ulteriori informazioni, consulta [Progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

I **[!UICONTROL progetti]** sono progettazioni personalizzate che combinano componenti dati, tabelle e visualizzazioni create dall&#39;utente o create e condivise da altri utenti. [!UICONTROL Progetti] fa riferimento anche a progetti vuoti e scorecard per dispositivi mobili vuote.

>[!NOTE]
>
>Molte delle seguenti impostazioni persistono nelle sessioni. Ad esempio, la scheda selezionata, i segmenti selezionati, le colonne selezionate e la direzione di ordinamento delle colonne. I risultati della ricerca non persistono.

Per ulteriori informazioni, consulta [Progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

## Modelli

Per accedere ai modelli in Customer Journey Analytics:

1. Seleziona la scheda [!UICONTROL **Workspace**].

1. Nella sezione [!UICONTROL **Modelli**] della barra a sinistra, puoi selezionare modelli Adobe o modelli aziendali.

Per informazioni sull’utilizzo dei modelli, consulta le risorse seguenti:

* [Utilizzare i modelli](/help/analysis-workspace/templates/use-templates.md)

* [Creare e gestire i modelli](/help/analysis-workspace/templates/create-templates.md)

<!--

### Customize table columns

To customize column widths, drag the vertical bar that separates each column. 

To add or remove columns from the list of projects, click the column icon (![Landing all](assets/select-column.png) ) in the top-right, then select or deselect column titles. 

The available columns are:

| Column name | Description |
|---------|----------|
| [!UICONTROL **Name**] | Identifies the name of the project. |
| [!UICONTROL **Type**] | Indicates whether this type is a Workspace project, a Mobile scorecard, or a folder. |
| [!UICONTROL **Tags**] | Tags projects to organize them into groups. |
| [!UICONTROL **Scheduled**] | Set to [!UICONTROL On] when a project is scheduled or [!UICONTROL Off] when it is not. Clicking the [!UICONTROL On] link lets you see information about the scheduled project. You can also [edit the project schedule](/help/analysis-workspace/export/t-schedule-report.md) if you are the project owner. |
| [!UICONTROL **Project role**] | Identifies the project roles: whether you are the project Owner and whether you have permissions to Edit or Duplicate the project. |
| [!UICONTROL **Report suite**] | Identifies the Report Suites that are associated with the project.<br>Tables and visualizations within a panel derive data from the report suite selected in the top right of the panel. The report suite also determines what components are available in the left rail. Within a project, you can use one or many report suites depending on your analysis use cases. The list of report suites is sorted on relevance. Adobe defines relevance based on how recently and frequently the suite has been used by the current user, and how frequently the suite is used within the organization. |
| [!UICONTROL **Owner**] | Identifies the person who created the project. |
| [!UICONTROL **Shared With**] | Shows who the project is currently shared with. |
| [!UICONTROL **Last Modified**] | The date and time when the project was last modified. |
| [!UICONTROL **Last Opened**] | Identifies the date that a project was last opened by the user who is currently viewing the Projects page. |
| [!UICONTROL **Last Used**] | Helps determine whether a project is valuable to users in your organization by showing the date and time when the project was last opened by any user within the organization.<p>Consider the following when viewing this column:</p><ul><li>Usage information is available starting in September 2023.</li><li>This column is available only to system administrators.</li></ul> |
| [!UICONTROL **Project ID**] | Can be used for debugging projects. |
| [!UICONTROL **Longest Date Range**] | Longer date ranges increase project complexity and may increase processing and load times. |
| [!UICONTROL **Number of queries**] | The total number of requests made to Analytics when the project loads. A higher number of project queries increases project complexity and may increase processing and load times. This data is available only after a project has loaded or a scheduled project was sent. |
| [!UICONTROL **Location**] | Shows the folder where the project is located. |

### Other UI elements on the Projects page

| UI element | Definition |
| --- | --- |
| Edit preferences | Lets you [!UICONTROL View Tutorials], and [Edit user preferences](/help/analysis-workspace/user-preferences.md). |
| [!UICONTROL Create new] | Opens the project modal where you can create a Workspace project or a Mobile scorecard or open a company template.  |
| [!UICONTROL Show less<br> Show more] | Toggles between not showing and showing the banner: ![Top banner](assets/top-banner.png) |
| [!UICONTROL Workspace project] | Creates a blank [Workspace project](/help/analysis-workspace/home.md) for you to  design and build. |
| [!UICONTROL Mobile scorecard] | Creates a blank [mobile scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html?lang=it) for you to design and build. |
| [!UICONTROL Open Training Tutorial] | Opens the Workspace training tutorial that guides you through the process of building a new starter project in a step-by-step tutorial.|
| [!UICONTROL Open release notes] | Opens the Adobe Analytics section of the latest Adobe Experience Cloud release notes. |
| Filter icon | Filters by tags, report suites, owners, types, and other filters (Mine, Shared with me, Favorites, and Approved)  |
| Search bar | Searches all columns in the table. |
| Selection box | Selects one or more projects to display the project management actions you can perform: **Delete**, **Share**, **Rename**, **Copy**, **Unpin**, **Move Up**, **Move Down**, **Tag**, **Approve**, **Export CSV**, and **Move to**. You may not have permissions to perform all listed actions. |
| [!UICONTROL Favorites] | Adds a star next to a favorite project or folder that can be used as a filter. |
| [!UICONTROL Name] | Identifies the name of the project. |
| Pin icon | Pins items so they always appear at the top of your list but you can re-adjust the order by moving them up or down in the order. Use the ellipsis option menu and select **Move Up** or **Move down** in the list. |
| Info (i) icon | Displays the following information about a project: Type, Project Role, Owner, Description, and who it is shared with. It also indicates who can [edit or duplicate](/help/analysis-workspace/curate-share/share-projects.md) this project. |
| Ellipsis (...) | Displays the project management actions you can perform: **Delete**, **Share**, **Rename**, **Copy**, **Unpin**, **Move Up**, **Move Down**, **Tag**, **Approve**, **Export CSV**, and **Move to**. You may not have permissions to perform all listed actions. |
| SHOW: Folders & Projects or All Projects | Changes the view setting on the table to show folders and projects according to your folder organization **or** show all of your projects in an unorganized list. |
| < (Back button) | Returns you to your most recent landing page configuration in a Workspace project or a report. The page configuration you had when you left the landing page will persist when you return. |

-->

## Apprendimento

La sezione **[!UICONTROL Apprendimento]** nella scheda [!UICONTROL **Workspace**] fornisce informazioni sulle funzioni principiante, intermedie o avanzate e sui casi d&#39;uso in Customer Journey Analytics. Fornisce inoltre informazioni su come effettuare l’aggiornamento da Adobe Analytics a Customer Journey Analytics.

### Percorsi di apprendimento

Per accedere alle informazioni sui percorsi di apprendimento in Customer Journey Analytics:

1. Seleziona la scheda [!UICONTROL **Workspace**].

1. Nella sezione [!UICONTROL **Apprendimento**] nella barra a sinistra, seleziona [!UICONTROL **Percorsi di apprendimento**].

   Questa pagina contiene presentazioni video pratiche, tutorial e collegamenti alla documentazione.


La pagina [!UICONTROL **Percorsi di apprendimento**] offre le seguenti caratteristiche:

* **Filtra contenuto:** Utilizza ![Filtra](/help/assets/icons/Filter.svg) per filtrare i contenuti di apprendimento in base a **[!UICONTROL Tipo]** (**[!UICONTROL Documento]**, **[!UICONTROL Video]** e **[!UICONTROL Visite e tutorial]**) e **[!UICONTROL Livello esperienza]** (**[!UICONTROL Principiante]**, **[!UICONTROL Intermedio]** o **[!UICONTROL Avanzate]**).
* **Traccia avanzamento:** Dopo aver selezionato un contenuto, viene visualizzato un tag ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Viewed]**. Questo tag consente di tenere traccia dei contenuti di apprendimento già visualizzati. Puoi selezionare il tag ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Viewed]** per rimuoverlo da un contenuto.
* **Visualizza contenuto aggiuntivo:** Durante la visualizzazione di qualsiasi video, seleziona **[!UICONTROL Ulteriori informazioni]** per visualizzare il contenuto della documentazione correlata su Experience League. In alternativa, dalla pagina Apprendimento, seleziona una delle seguenti opzioni per visualizzare contenuto aggiuntivo:
   * **[!UICONTROL Visita YouTube]:** Visualizza la playlist Analysis Workspace YouTube completa.
   * [!UICONTROL **Visita Experience League**]: consulta la suite completa della documentazione di Customer Journey Analytics su Experience League.
* **Nozioni di base per i nuovi utenti:** Per i nuovi utenti è consigliata la presentazione di [!UICONTROL Nozioni di base di Learning Workspace]. Questa presentazione consente di entrare direttamente in Workspace e di scoprire le azioni più comuni. Questa presentazione può anche essere riavviata in qualsiasi momento in Workspace tramite la descrizione dall’intestazione del [Pannello a forma libera](/help/analysis-workspace/c-panels/freeform-panel.md) o del [Pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md).

### Aggiornamento a Customer Journey Analytics

Per accedere alle informazioni sull&#39;aggiornamento a Customer Journey Analytics:

1. Seleziona la scheda [!UICONTROL **Workspace**].

1. Nella sezione [!UICONTROL **Apprendimento**] nella barra a sinistra, seleziona [!UICONTROL **Esegui l&#39;aggiornamento a Customer Journey Analytics**].

Questa pagina è destinata ai clienti che non hanno ancora effettuato l’aggiornamento completo da Adobe Analytics a Customer Journey Analytics. Fornisce un questionario che determina passaggi di aggiornamento generati in modo dinamico per le circostanze specifiche della tua organizzazione.

Per ulteriori informazioni, consulta [Generare dinamicamente i passaggi di aggiornamento per la tua organizzazione](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#dynamically-generate-upgrade-steps-for-your-organization) in [Eseguire l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

## Pagina di destinazione preferita

Puoi impostare la pagina di destinazione preferita. Per ulteriori informazioni, consulta [Preferenze dell’utente](/help/analysis-workspace/user-preferences.md#general-preferences).

<!--
## Landing page FAQ {#landing-faq}

| Question | Answer |
| --- | --- |
| Does the work I do in the beta program UI carry over to the production [!UICONTROL Workspace] experience? | Yes, any work done in the beta carries over to the old/current [!UICONTROL Workspace] experience. |
| Is there a maximum number of projects I can pin? | No, there is no limit on the number of projects you can pin. |
| Can admins designate this landing page for their users? | No, admins cannot designate the landing page on behalf of users. Individual users must turn on the toggle themselves. |
| Are all reports that currently exist in [!DNL Reports & Analytics] still available? | No, the following reports were phased out, based on overall usage data: <ul><li>Any custom eVars/props/events/classifications<li>My Recommended Reports</li><li>Hourly/Daily/Weekly/Monthly/Quarterly/Yearly unique visitors</li><li>DailyWeekly/Monthly/Quarterly/Yearly unique customers</li><li>Action name depth</li><li>Action name summary</li><li>Add dashboard</li><li>Age</li><li>Audio support</li><li>Billing information</li><li>Clicks to page</li><li>Color depth</li><li>Cookie support</li><li>Cookies</li><li>Connection types</li><li>Creative elements</li><li>Credit card type</li><li>Cross sell</li><li>Custom event funnels</li><li>Custom links</li><li>Customer ID</li><li>Day of week</li><li>Entry action name</li><li>Exit action name</li><li>Exit links</li><li>Fallout</li><li>File downloads</li><li>Find in store</li><li>Full paths</li><li>Gender</li><li>Hit ype VISTA rule</li><li>Image support</li><li>Java</li><li>JavaScript</li><li>JavaScript version</li><li>Manage bookmarks</li><li>Manage dashboards</li><li>Monitor color depth</li><li>Monitor resolutions</li><li>Newsletter signups</li><li>Next action name</li><li>Next action name flow</li><li>Null searches</li><li>Operating system</li><li>Order review</li><li>Page of day</li><li>Pages not found</li><li>Pathfinder</li><li>Path length</li><li>Previous action name</li><li>Previous action name flow</li><li>Product activity</li><li>Product cost</li><li>Product department</li><li>Product inventory category</li><li>Product name</li><li>Product reviews</li><li>Product season</li><li>Product shares</li><li>Product zooms</li><li>Reload</li><li>Searches</li><li>Servers</li><li>Single page visits</li><li>Shipping information</li><li>Site hierarchy</li><li>Social mentions</li><li>Time of day</li><li>Time spent on action name</li><li>Video support</li><li>Visitor state</li></ul> |
-->
