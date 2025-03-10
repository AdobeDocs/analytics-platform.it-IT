---
title: Generazione di rapporti per l’analisi dei contenuti
description: Come creare rapporti su Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Panoramica reportistica di Content Analytics

>[!WARNING]
>
>Questo articolo è una bozza preliminare non ufficiale di una versione finale di prossima pubblicazione e fa parte della documentazione di Content Analytics. Tutti i contenuti sono soggetti a modifiche e nessun obbligo legale può essere derivato dalla versione corrente di questo articolo.
>

{{release-limited-testing}}

La generazione di rapporti sull’analisi dei contenuti viene eseguita all’interno di Analysis Workspace. È disponibile un [modello](#template) Workspace specifico, che consente di accedere immediatamente a un progetto Workspace precompilato con informazioni rilevanti sul contenuto.

Per iniziare a generare rapporti su Content Analytics da zero:

1. [Crea un nuovo](/help/analysis-workspace/build-workspace-project/create-projects.md) o [apri un progetto](/help/analysis-workspace/build-workspace-project/open-projects.md) esistente in Workspace.
1. Trascina una visualizzazione ![Tabella](/help/assets/icons/Table.svg) [Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) nell&#39;area di lavoro.
1. Utilizza [componenti specifici di Content Analytics](components.md) e altri [componenti](/help/components/overview.md) generici (come filtri, intervalli di date, annotazioni) per creare informazioni approfondite di Content Analytics.

## Miniature

In base alle dimensioni specifiche di Content Analytics che utilizzi nel progetto, vengono visualizzate le miniature per le risorse e le dimensioni.

![Miniature di Content Analytics](../assets/aca-thumbnails.png)

## Anteprime

Per le dimensioni che hanno miniature (come Nome risorsa, Nome esperienza e altre), puoi aprire una finestra a comparsa di anteprima.

Per aprire l&#39;anteprima con i dettagli seguenti:

* Selezionare ![InfoOutline](/help/assets/icons/InfoOutline.svg). Vengono visualizzati i dettagli seguenti.

  | Anteprima esperienza | Anteprima risorsa |
  |---|---|
  | ![Anteprima esperienza analisi contenuti](../assets/aca-experience-preview.png) | ![Anteprima risorse di analisi dei contenuti](../assets/aca-asset-preview.png) |
  | **[!UICONTROL Name of the experience]** | **[!UICONTROL Name of the asset]** |
  | **[!UICONTROL Impressions (all times)]**: numero di impression per l&#39;esperienza. | **[!UICONTROL Impressions (all mes)]**: numero di impression per la risorsa. |
  | **[!UICONTROL Assets]**: numero di risorse contenute in questa esperienza. Seleziona ![Raggruppamento](/help/assets/icons/Breakdown.svg) per esaminare le risorse. | **[!UICONTROL Experiences]**: numero di esperienze in cui questa risorsa viene visualizzata. [Raggruppamento](/help/assets/icons/Breakdown.svg) per esaminare le risorse. |
  | **[!UICONTROL First impression]**: data della prima impressione dell&#39;esperienza. | **[!UICONTROL First impression]**: data della prima impression della risorsa. |
  | **[!UICONTROL  Most recent impression]**: data dell&#39;impression più recente dell&#39;esperienza. | **[!UICONTROL Most recent impression]**: data dell&#39;impression più recente della risorsa. |
  | **[!UICONTROL Experience attributes]**: attributi dell&#39;esperienza. | **[!UICONTROL Asset attributes]**: attributi della risorsa. |


## Modello

Dettagli sui modelli...


>[!MORELIKETHIS]
>
>[Componenti di analisi dei contenuti](components.md)
>
