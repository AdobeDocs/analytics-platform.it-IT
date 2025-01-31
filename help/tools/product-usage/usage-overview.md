---
title: Panoramica sull’utilizzo del prodotto
description: Visualizzare approfondimenti e rapporti sul modo in cui l’organizzazione utilizza il Customer Journey Analytics.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Panoramica sull’utilizzo del prodotto

L’utilizzo del prodotto consente all’organizzazione di visualizzare i dati analitici sul modo in cui l’organizzazione utilizza il Customer Journey Analytics. È disponibile per tutte le organizzazioni che utilizzano Customer Journey Analytics. Una volta abilitati, i seguenti componenti Adobe Experience Platform vengono creati e collegati automaticamente. Questi componenti sono tutti di proprietà del sistema, sono di sola lettura e non possono essere modificati.

* Uno schema in Adobe Experience Platform
* Un set di dati in Adobe Experience Platform
* Una connessione nel Customer Journey Analytics
* Una visualizzazione dati nel Customer Journey Analytics

Una volta abilitata, la raccolta e l’impostazione dei dati vengono configurate automaticamente. Ogni volta che un utente esegue un’azione in Analysis Workspace, questa viene tracciata e disponibile per i rapporti.

>[!IMPORTANT]
>
>Questa funzione conta per i limiti di riga contrattuali in Adobe Experience Platform. Assicurati che la tua organizzazione possa inserire i dati generati da questa funzione prima di abilitarla.

## Abilita utilizzo prodotto

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]**

Passando a questa sezione dell&#39;interfaccia nel Customer Journey Analytics, puoi passare a [Impostazioni dati](data-settings.md), dove puoi abilitare questa funzione.

## Dimensioni disponibili

Quando abiliti l’utilizzo del prodotto, sono disponibili le seguenti dimensioni. Se desideri modificare le impostazioni di dimensione, crea una copia della visualizzazione dati di proprietà del sistema e utilizza la visualizzazione dati copiata in Analysis Workspace.

* **[!UICONTROL Action Name]**: tipo di azione eseguita dall&#39;utente. Puoi utilizzare questa dimensione come qualsiasi metrica desiderata creando una copia nelle impostazioni della visualizzazione dati. Gli elementi del Dimension includono:
   * [!UICONTROL Add attribution]
   * [!UICONTROL Add component]
   * [!UICONTROL Add panel]
   * [!UICONTROL Add visualization]
   * [!UICONTROL Create new guided analysis]
   * [!UICONTROL Create new project]
   * [!UICONTROL Curate components]
   * [!UICONTROL Download CSV]
   * [!UICONTROL Download PDF]
   * [!UICONTROL Load guided analysis]
   * [!UICONTROL Load project]
   * [!UICONTROL New scorecard loaded]
   * [!UICONTROL Open data dictionary]
   * [!UICONTROL Open intelligent captions]
   * [!UICONTROL Project share]
   * [!UICONTROL Run Experimentation panel]
   * [!UICONTROL Save project]
   * [!UICONTROL Scorecard saved]
   * [!UICONTROL Send file]
   * [!UICONTROL Send file on schedule]
   * [!UICONTROL Share project with anyone]
   * [!UICONTROL Share project with Workspace users]
* **[!UICONTROL Attribution Model Used]**: tipo di modello di attribuzione utilizzato dal componente. Gli elementi del Dimension includono:
   * [!UICONTROL Last touch]
   * [!UICONTROL First touch]
   * [!UICONTROL Linear]
   * [!UICONTROL Participation]
   * [!UICONTROL Same touch]
   * [!UICONTROL U shaped]
   * [!UICONTROL J curve]
   * [!UICONTROL Inverse J]
   * [!UICONTROL Time decay]
   * [!UICONTROL Custom]
   * [!UICONTROL Algorithmic]
* **[!UICONTROL Component Name]**: nome del componente aggiunto, rimosso o modificato.
* **[!UICONTROL Component Type]**: tipo di componente aggiunto, rimosso o modificato. Gli elementi del Dimension includono:
   * [!UICONTROL Dimension]
   * [!UICONTROL Metric]
   * [!UICONTROL Filter]
   * [!UICONTROL Calculated metric]
   * [!UICONTROL Date range]
   * [!UICONTROL Annotation]
   * [!UICONTROL Alert]
* **[!UICONTROL Login User]**: utente che ha eseguito l&#39;azione.
* **[!UICONTROL Panel Used]**: pannello in cui il componente è stato aggiunto, rimosso o modificato. Gli elementi del Dimension includono:
   * [!UICONTROL Attribution]
   * [!UICONTROL Blank panel]
   * [!UICONTROL Experimentation]
   * [!UICONTROL Freeform]
   * [!UICONTROL Next or previous item]
   * [!UICONTROL Quick insights]
   * [!UICONTROL Trends]
   * [!UICONTROL Funnel]
   * [!UICONTROL User growth]
   * [!UICONTROL Impact]
   * [!UICONTROL User stream]
   * [!UICONTROL Retention]
   * [!UICONTROL Feature matrix]
* **[!UICONTROL Project Name]**: nome descrittivo del progetto.
* **[!UICONTROL Project Type]**: tipo di progetto. Gli elementi del Dimension includono:
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL Visualization Used]**: visualizzazione aggiunta, rimossa o modificata. Gli elementi del Dimension includono:
   * [!UICONTROL Freeform table]
   * [!UICONTROL Cohort table]
   * [!UICONTROL Fallout]
   * [!UICONTROL Flow]
   * [!UICONTROL Journey Canvas reportlet]
   * [!UICONTROL Area]
   * [!UICONTROL Area stacked]
   * [!UICONTROL Bar]
   * [!UICONTROL Bar stacked]
   * [!UICONTROL Bullet]
   * [!UICONTROL Combo]
   * [!UICONTROL Donut]
   * [!UICONTROL Histogram]
   * [!UICONTROL Horizontal bar]
   * [!UICONTROL Horizontal bar stacked]
   * [!UICONTROL Key metric summary]
   * [!UICONTROL Line]
   * [!UICONTROL Map]
   * [!UICONTROL Scatter]
   * [!UICONTROL Section header]
   * [!UICONTROL Summary change]
   * [!UICONTROL Summary number]
   * [!UICONTROL Text]
   * [!UICONTROL Treemap]
   * [!UICONTROL Venn]

L’utilizzo del prodotto non tiene traccia dei singoli componenti del progetto quando un progetto viene semplicemente aperto o visualizzato. Tuttavia, viene tenuta traccia dell’azione dell’utente di apertura di un progetto.
