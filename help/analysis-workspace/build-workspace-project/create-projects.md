---
description: Scopri come creare un progetto in Analysis Workspace
title: Creare progetti
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 53d367e51f739ebf324390ba4114ddb58138fac8
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 100%

---

# Creare progetti

I [progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace consentono di visualizzare le analisi business-critical che possono essere condivise con gli stakeholder all’interno o all’esterno dell’organizzazione.

Per informazioni generali su come iniziare a utilizzare Analysis Workspace, consulta [Panoramica di Analysis Workspace](/help/analysis-workspace/home.md).

Le sezioni seguenti descrivono come creare un progetto e iniziare ad aggiungere i blocchi predefiniti chiave per qualsiasi progetto Analysis Workspace: pannelli, visualizzazioni e componenti.

## Iniziare la creazione un progetto

1. In Adobe Analytics, seleziona [!UICONTROL **Workspace**].

1. Nella scheda [!UICONTROL **Workspace**], seleziona la scheda [!UICONTROL **Progetti**] sul lato sinistro della pagina, quindi seleziona [!UICONTROL **Crea progetto**].

1. Scegli se creare un progetto vuoto o una scorecard per dispositivi mobili vuota

   * **Progetto vuoto** se prevedi di condividere l’analisi dal browser
   * [**Scorecard per dispositivi mobili vuota**](/help/mobile-app/curator.md) se prevedi di condividere l’analisi dall’app mobile delle dashboard di Adobe Analytics.

1. Seleziona [!UICONTROL **Crea**].

1. Successivamente, è necessario aggiungere al progetto pannelli, visualizzazioni e componenti. Innanzitutto, aggiungi i pannelli al progetto in Analysis Workspace, come descritto in [Aggiungere pannelli al progetto](#add-panels-to-the-project). Puoi quindi aggiungere visualizzazioni a qualsiasi pannello. Infine, puoi aggiungere componenti a qualsiasi pannello o visualizzazione.

## Aggiungere pannelli al progetto {#panels}

I [pannelli](/help/analysis-workspace/c-panels/panels.md) sono alla base di qualsiasi progetto in Analysis Workspace. I pannelli vengono utilizzati per organizzare il contenuto (visualizzazioni e componenti) di un progetto.

Molti dei pannelli forniti in Analysis Workspace generano un intero set di analisi basate su alcuni input dell’utente.

Per aggiungere un pannello:

1. Seleziona l’icona [!UICONTROL **Pannelli**] nella barra a sinistra.

   ![Icona Seleziona pannelli ed elenco dei pannelli disponibili.](assets/build-panels.png)

1. Cerca il pannello da aggiungere. Quando viene visualizzato nella barra a sinistra, trascinalo nel progetto.

1. Aggiungi visualizzazioni al pannello, come descritto in [Aggiungere visualizzazioni al progetto](#add-visualizations-to-the-project).

   In alternativa, puoi aggiungere componenti direttamente a un pannello, come descritto in [Aggiungere componenti al progetto](#add-components-to-the-project).

## Aggiungere visualizzazioni al progetto

Le [visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), ad esempio una tabella a forma libera, un grafico a barre o a linee, possono essere utilizzate per mettere visivamente in risalto i dati.

>[!TIP]
>
>Le tabelle a forma libera sono il tipo di visualizzazione più comune e costituiscono la base per l’analisi interattiva dei dati. Per ulteriori dettagli sull’utilizzo delle tabelle a forma libera in Analysis Workspace, consulta [Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).

Per aggiungere una visualizzazione:

1. Seleziona l’icona **[!UICONTROL Visualizations]** nella barra a sinistra.

   ![Icona Visualizzazioni selezionata ed elenco delle visualizzazioni disponibili.](assets/build-visualizations.png)

1. Cerca la visualizzazione da aggiungere. Quando viene visualizzata nella barra a sinistra, trascinala su un pannello all’interno del progetto.

1. Aggiungi componenti alla visualizzazione, come descritto in [Aggiungere componenti al progetto](#add-components-to-the-project).

## Aggiungere componenti al progetto

I [componenti](/help/components/overview.md) costituiscono i dati effettivi di qualsiasi progetto. Puoi aggiungere componenti alle visualizzazioni o ai pannelli.

>[!TIP]
>
>Per informazioni su ciascun componente, seleziona l’icona Informazioni accanto al nome di un componente nella barra a sinistra, oppure consulta [Panoramica sui componenti](/help/components/overview.md).

Di seguito sono riportate informazioni di base su come aggiungere un componente a un progetto in Analysis Workspace. Per informazioni più dettagliate sull’aggiunta dei vari tipi di componenti (dimensioni, metriche, filtri e intervalli di date), consulta [Utilizzare i componenti in Analysis Workspace](/help/components/use-components-in-workspace.md).

Per aggiungere un componente a un progetto in Analysis Workspace:

1. Seleziona l’icona **[!UICONTROL Components]** nella barra a sinistra.

   ![Icona Componenti selezionata ed elenco delle dimensioni disponibili.](assets/build-components.png)

1. Scorri fino al componente da aggiungere oppure cercalo, quindi trascinalo su un pannello o su una visualizzazione all’interno del progetto.

   Ad esempio, puoi trascinare un filtro nella zona di rilascio del filtro nell’intestazione di un pannello.

   ![rilascia un filtro nella zona di rilascio](assets/filter-dropzone.png)

   Per ulteriori informazioni sull’aggiunta di componenti ai progetti, consulta [Utilizzare i componenti in Analysis Workspace](/help/components/use-components-in-workspace.md).

1. (Facoltativo) Condividi il progetto come descritto in [Salvare e condividere un progetto](#save-and-share-the-project).

## Salvare e condividere un progetto

Quando crei un’analisi in Analysis Workspace, il lavoro viene [salvato automaticamente](/help/analysis-workspace/build-workspace-project/save-projects.md).

Una volta completato il progetto e questo sta raccogliendo approfondimenti utili, il progetto è pronto per essere utilizzato da altri utenti. Puoi condividere il progetto con utenti e gruppi dell’organizzazione o anche con persone esterne a questa. Per informazioni sulla condivisione di un progetto, consulta [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).
