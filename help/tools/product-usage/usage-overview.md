---
title: Panoramica di utilizzo del prodotto
description: Visualizza approfondimenti e rapporti sull’utilizzo di Customer Journey Analytics da parte della tua organizzazione.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: a4615907f61b4d63393a9481fdd7b45b7b9b6262
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 86%

---

# Panoramica di utilizzo del prodotto

Utilizzo del prodotto consente all’organizzazione di visualizzare i dati analitici relativi al modo in cui utilizza Customer Journey Analytics. È disponibile per tutte le organizzazioni che utilizzano Customer Journey Analytics. Una volta abilitata la funzionalità, vengono creati e collegati automaticamente i seguenti componenti Adobe Experience Platform. Questi componenti sono tutti di proprietà del sistema, sono di sola lettura e non possono essere modificati.

* Schema in Adobe Experience Platform
* Set di dati in Adobe Experience Platform
* Connessione in Customer Journey Analytics
* Visualizzazione dati in Customer Journey Analytics

Una volta abilitate, tutte le raccolte e le impostazioni dei dati vengono configurate automaticamente. Ogni volta che un utente esegue un’azione in Analysis Workspace, questa viene tracciata ed è disponibile per i rapporti.

>[!IMPORTANT]
>
>Questa funzione conta per i limiti di riga contrattuali in Adobe Experience Platform. Assicurati che la tua organizzazione possa inserire i dati generati da questa funzione prima di abilitarla.

## Abilita Utilizzo del prodotto

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]**

Passando a questa sezione dell’interfaccia in Customer Journey Analytics arrivi a [Impostazioni dati](data-settings.md), dove puoi abilitare la funzione.

## Dimensioni disponibili

Quando abiliti Utilizzo del prodotto, sono disponibili le seguenti dimensioni. Se desideri modificare le impostazioni di dimensione, crea una copia della visualizzazione dati di proprietà del sistema e utilizza la visualizzazione dati copiata in Analysis Workspace.

* **[!UICONTROL Action Name]**: tipo di azione eseguita dall’utente. Puoi utilizzare questa dimensione come qualsiasi metrica desiderata creando una copia nelle impostazioni della visualizzazione dati. Gli elementi domensionali includono:
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
* **[!UICONTROL Attribution Model Used]**: tipo di modello di attribuzione utilizzato dal componente. Gli elementi domensionali includono:
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
* **[!UICONTROL Component Type]**: tipo di componente aggiunto, rimosso o modificato. Gli elementi domensionali includono:
   * [!UICONTROL Dimension]
   * [!UICONTROL Metric]
   * [!UICONTROL Segment]
   * [!UICONTROL Calculated metric]
   * [!UICONTROL Date range]
   * [!UICONTROL Annotation]
   * [!UICONTROL Alert]
* **[!UICONTROL Login User]**: utente che ha eseguito l’azione.
* **[!UICONTROL Panel Used]**: pannello in cui il componente è stato aggiunto, rimosso o modificato. Gli elementi domensionali includono:
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
* **[!UICONTROL Project Type]**: tipo di progetto. Gli elementi domensionali includono:
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL Visualization Used]**: visualizzazione aggiunta, rimossa o modificata. Gli elementi domensionali includono:
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

L’utilizzo del prodotto non tiene traccia dei singoli componenti del progetto quando questo viene semplicemente aperto o visualizzato. Tuttavia, viene tenuta traccia dell’azione dell’utente di apertura di un progetto.

## Modello disponibile

È disponibile un [modello Adobe](/help/analysis-workspace/templates/use-templates.md) che utilizza i componenti generati automaticamente da questa funzionalità.

**[!UICONTROL Adobe templates]** > **[!UICONTROL Other]** > **[!UICONTROL Product usage overview]**

Selezionare la visualizzazione dati creata automaticamente dall&#39;utilizzo del prodotto nel selettore della visualizzazione dati, quindi selezionare il modello **[!UICONTROL Product usage overview]**. Seleziona **[!UICONTROL Preview]** per vedere quali pannelli utilizza il modello e quali sono i casi d&#39;uso ideali, oppure seleziona **[!UICONTROL Use template]** per aprirlo in Analysis Workspace.
