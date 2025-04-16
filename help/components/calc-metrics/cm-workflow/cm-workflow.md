---
description: Scopri come creare metriche calcolate.
title: Creare metriche calcolate
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: 53069702055e0adf7abf9061c592fb15772ded73
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 5%

---

# Creare metriche calcolate

Per impostazione predefinita, solo gli amministratori possono creare metriche calcolate. Gli utenti dispongono delle autorizzazioni per visualizzare le metriche calcolate, in modo analogo a come visualizzano altri componenti (come segmenti, annotazioni e altro ancora).

Tuttavia, gli amministratori possono assegnare l&#39;autorizzazione **[!UICONTROL Calculated Metric Creation]** per **[!UICONTROL Reporting Tools]** in **[!UICONTROL Edit permissions for CJA Workspace Access]** agli utenti tramite [Admin Console](/help/technotes/access-control.md#user-level-access).


Puoi creare una metrica calcolata nei seguenti modi:

![Modalità di creazione di un filtro](assets/create-metric.png)

* **A**. Nell&#39;interfaccia principale, selezionare **[!UICONTROL Components]** e selezionare **[!UICONTROL Calculated metrics]**. Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] dal gestore [[!UICONTROL Calculated metrics]](/help/components/calc-metrics/cm-workflow/cm-manager.md).
* **B**. In un progetto Workspace, dal pannello a sinistra Componenti, seleziona ![Aggiungi](/help/assets/icons/Add.svg) in ![Evento](/help/assets/icons/Event.svg) **Metriche**.
* **C**. In un progetto Workspace, dal menu di scelta rapida nell&#39;intestazione di colonna delle metriche, selezionare **[!UICONTROL Create metric from selection]**. Dal sottomenu, è possibile selezionare una funzione o selezionare **[!UICONTROL Open in calculated metric builder]**. <br/>Se selezioni una funzione, la metrica calcolata viene definita come metrica solo progetto. Quando successivamente modifichi questa metrica, tramite il popup [Informazioni componente](/help/components/use-components-in-workspace.md#component-info), viene visualizzata una notifica nel [Generatore di metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
* **D**. In un progetto Workspace, selezionare **[!UICONTROL Components]** dal menu e selezionare **[!UICONTROL Create metric]**.
* **E**. In un progetto Workspace, utilizzare il collegamento **[!UICONTROL shift+cmd+c]** (macOS) o **[!UICONTROL shift+ctrl+c]** (Windows).

Per definire la nuova metrica calcolata, utilizzare il generatore di metriche calcolate [](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

<!--

Learn about the steps to take for creating calculated metrics.

| Workflow Task | Description |
| --- | --- |
| Plan Calculated Metrics | Especially for metrics that are going to be officially "approved", it makes sense to outline which calculated metrics will be widely used and how they will be defined. |
| [Build](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) Calculated Metrics | Build and edit calculated and advanced calculated metrics for use in [!DNL Customer Journey Analytics] components. |
| [Tag](cm-tagging.md) Calculated Metrics | Tag calculated metrics for ease of organization and sharing. See how to plan and assign tags for simple and advanced searches and organization. |
| [Approve](cm-approving.md) Calculated Metrics | Approve calculated metrics to make them canonical. |
| Apply Calculated Metrics | You can apply metrics directly from a report, from the Metric Selector (to access it, click [!UICONTROL Show Metrics]). |
| Filter Calculated Metrics | In the Metric Selector, click [!UICONTROL Advanced Selection] and filter by tags, owners, and other filters (Show All, Mine, Shared With me, Favorites, and Approved.) |
| Mark Calculated Metrics as [Favorites](cm-finding.md) | Marking metrics as favorites is another way to organize them for ease of use.|

-->
