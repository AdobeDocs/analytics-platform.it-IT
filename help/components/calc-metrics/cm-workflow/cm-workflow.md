---
description: Scopri come creare metriche calcolate.
title: Creare metriche calcolate
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
TQID: https://experienceleague.adobe.com/8xHrnqI8ZUf3qwy4Im3Qa-ESAokGMs3XPOYmpFF6Dx0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 384
ht-degree: 4%

---

# Creare metriche calcolate

Per impostazione predefinita, solo gli amministratori possono creare metriche calcolate. Gli utenti dispongono delle autorizzazioni per visualizzare le metriche calcolate, in modo analogo a come visualizzano altri componenti (come segmenti, annotazioni e altro ancora).

Tuttavia, gli amministratori possono assegnare l&#39;autorizzazione **[!UICONTROL Creazione metrica calcolata]** per **[!UICONTROL Strumenti di reporting]** in **[!UICONTROL Modifica autorizzazioni per CJA Workspace Access]** agli utenti tramite [Admin Console](/help/technotes/access-control.md#user-level-access).


Puoi creare una metrica calcolata nei seguenti modi:

![Modalità di creazione di una metrica](assets/create-metric.png)

* **A**. Nell&#39;interfaccia principale, selezionare **[!UICONTROL Componenti]** e **[!UICONTROL Metriche calcolate]**. Seleziona ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Aggiungi]**] dal gestore [[!UICONTROL Metriche calcolate]](/help/components/calc-metrics/cm-workflow/cm-manager.md).
* **B**. In un progetto Workspace, dal pannello a sinistra Componenti, seleziona ![Aggiungi](/help/assets/icons/Add.svg) in ![Evento](/help/assets/icons/Event.svg) **Metriche**.
* **C**. In un progetto Workspace, dal menu di scelta rapida nell&#39;intestazione della colonna Metrics, selezionare **[!UICONTROL Create metric from selection]**. Dal sottomenu, puoi selezionare una funzione o selezionare **[!UICONTROL Apri nel generatore di metriche calcolate]**. <br/>Se selezioni una funzione, la metrica calcolata viene definita come metrica solo progetto. Quando successivamente modifichi questa metrica, tramite il popup [Informazioni componente](/help/components/use-components-in-workspace.md#component-info), viene visualizzata una notifica nel [Generatore di metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
* **D**. In un progetto di Workspace, seleziona **[!UICONTROL Componenti]** dal menu, quindi seleziona **[!UICONTROL Crea metrica]**.
* **E**. In un progetto Workspace, utilizza il collegamento **[!UICONTROL shift+cmd+c]** (macOS) o **[!UICONTROL shift+ctrl+c]** (Windows).

Per definire la nuova metrica calcolata, utilizzare il generatore di metriche calcolate [](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).


## Flusso di lavoro

Prima di creare le metriche calcolate, considera attentamente il seguente flusso di lavoro:

| Attività flusso di lavoro | Descrizione |
| --- | --- |
| Pianificare le metriche calcolate | Soprattutto per le metriche che verranno approvate ufficialmente, la pianificazione ha senso delineare quali metriche calcolate verranno ampiamente utilizzate e come verranno definite. |
| [Genera](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) metriche calcolate | Genera e modifica metriche calcolate e calcolate avanzate da utilizzare nei componenti [!DNL Customer Journey Analytics]. |
| [Tag](cm-tagging.md) metriche calcolate | Assegna tag alle metriche calcolate per semplificarne l’organizzazione e la condivisione. Scopri come pianificare e assegnare tag per ricerche e organizzazioni semplici e avanzate. |
| [Approva](cm-approving.md) metriche calcolate | Approva le metriche calcolate per renderle canoniche. |
| Utilizzare le metriche calcolate | Utilizza le metriche calcolate nei progetti. |
| [Condividi](cm-sharing.md) metriche calcolate | Condividere le metriche calcolate con altri individui, gruppi o organizzazioni. |
| [Filtro](cm-filter.md) metriche calcolate | Filtrare le metriche calcolate per tag, proprietari e altri filtri (Mostra tutto, Personali, Condivisi con me, Preferiti e Approvati). |
| Contrassegna metriche calcolate come [preferiti](cm-finding.md) | Contrassegnare le metriche come preferite è un altro modo per organizzarle in modo semplice e intuitivo. |

