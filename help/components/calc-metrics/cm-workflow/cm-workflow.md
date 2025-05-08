---
description: Scopri come creare metriche calcolate.
title: Creare metriche calcolate
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: c183a5013cbc5ff3765cc4926a308d0c4563a097
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 7%

---

# Creare metriche calcolate

Per impostazione predefinita, solo gli amministratori possono creare metriche calcolate. Gli utenti dispongono delle autorizzazioni per visualizzare le metriche calcolate, in modo analogo a come visualizzano altri componenti (come segmenti, annotazioni e altro ancora).

Tuttavia, gli amministratori possono assegnare l&#39;autorizzazione **[!UICONTROL Calculated Metric Creation]** per **[!UICONTROL Reporting Tools]** in **[!UICONTROL Edit permissions for CJA Workspace Access]** agli utenti tramite [Admin Console](/help/technotes/access-control.md#user-level-access).


Puoi creare una metrica calcolata nei seguenti modi:

![Modalità di creazione di una metrica](assets/create-metric.png)

* **A**. Nell&#39;interfaccia principale, selezionare **[!UICONTROL Components]** e selezionare **[!UICONTROL Calculated metrics]**. Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] dal gestore [[!UICONTROL Calculated metrics]](/help/components/calc-metrics/cm-workflow/cm-manager.md).
* **B**. In un progetto Workspace, dal pannello a sinistra Componenti, seleziona ![Aggiungi](/help/assets/icons/Add.svg) in ![Evento](/help/assets/icons/Event.svg) **Metriche**.
* **C**. In un progetto Workspace, dal menu di scelta rapida nell&#39;intestazione di colonna delle metriche, selezionare **[!UICONTROL Create metric from selection]**. Dal sottomenu, è possibile selezionare una funzione o selezionare **[!UICONTROL Open in calculated metric builder]**. <br/>Se selezioni una funzione, la metrica calcolata viene definita come metrica solo progetto. Quando successivamente modifichi questa metrica, tramite il popup [Informazioni componente](/help/components/use-components-in-workspace.md#component-info), viene visualizzata una notifica nel [Generatore di metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
* **D**. In un progetto Workspace, selezionare **[!UICONTROL Components]** dal menu e selezionare **[!UICONTROL Create metric]**.
* **E**. In un progetto Workspace, utilizzare il collegamento **[!UICONTROL shift+cmd+c]** (macOS) o **[!UICONTROL shift+ctrl+c]** (Windows).

Per definire la nuova metrica calcolata, utilizzare il generatore di metriche calcolate [&#128279;](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

Scopri come creare metriche calcolate.

| Attività flusso di lavoro | Descrizione |
| --- | --- |
| Pianificare le metriche calcolate | Soprattutto per le metriche che verranno ufficialmente &quot;approvate&quot;, ha senso delineare quali metriche calcolate saranno ampiamente utilizzate e come saranno definite. |
| [Genera](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) Metriche Calcolate | Genera e modifica metriche calcolate e calcolate avanzate da utilizzare nei componenti [!DNL Customer Journey Analytics]. |
| [Tag](cm-tagging.md) Metriche calcolate | Assegna tag alle metriche calcolate per semplificarne l’organizzazione e la condivisione. Scopri come pianificare e assegnare tag per ricerche e organizzazioni semplici e avanzate. |
| [Approva](cm-approving.md) Metriche Calcolate | Approva le metriche calcolate per renderle canoniche. |
| Applicare le metriche calcolate | È possibile applicare le metriche direttamente da un report, dal selettore delle metriche (per accedervi, fare clic su [!UICONTROL Show Metrics]). |
| Filtrare le metriche calcolate | Nel selettore delle metriche, fare clic su [!UICONTROL Advanced Selection] e filtrare in base a tag, proprietari e altri filtri (Mostra tutto, Personali, Condivisi con me, Preferiti e Approvati). |
| Contrassegna metriche calcolate come [Preferiti](cm-finding.md) | Contrassegnare le metriche come preferite è un altro modo per organizzarle in modo semplice e intuitivo. |

