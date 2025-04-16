---
description: Scopri come creare un progetto in Analysis Workspace
title: Creare progetti
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 191693bc970fcf59ee51706365abde0ee30e3d3d
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 95%

---

# Creare progetti {#create-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Conta istanze ripetute"
>abstract="Specifica se le istanze ripetute vengono conteggiate o meno nei rapporti.<br/><br/>Nota: questa impostazione non si applica alle visualizzazioni Flusso o Fallout."

<!-- markdownlint-enable MD034 -->


I [progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace consentono di creare e visualizzare le analisi business-critical.  Queste analisi possono essere condivise con gli stakeholder all’interno o all’esterno dell’organizzazione.

1. In Customer Journey Analytics, seleziona **[!UICONTROL Workspace]**.

1. Seleziona **[!UICONTROL Projects]** nel pannello a sinistra, quindi seleziona **[!UICONTROL Create project]**.

1. Seleziona **Progetto Workspace vuoto** per creare il tuo progetto Workspace utilizzando un browser.

   Consulta [Scorecard per dispositivi mobili vuota](/help/mobile-app/curator.md) per ulteriori informazioni su come creare un progetto scorecard per dispositivi mobili che puoi condividere con gli altri stakeholder utilizzando un’app per dispositivi mobili. Per ulteriori informazioni sulle varie opzioni disponibili per creare il tuo progetto di analisi guidata, consulta [Analisi guidata](/help/guided-analysis/overview.md).

1. Seleziona [!UICONTROL **Crea**].


Dopo aver creato un progetto Workspace vuoto, assicurati di avere familiarità con l’interfaccia utente di [Analysis Workspace](/help/analysis-workspace/home.md). Una volta acquisita la familiarità necessaria, puoi creare il progetto. A tale scopo, effettua le seguenti operazioni:

![Progetto di esempio](assets/example-project.png)

* Aggiungi dei [pannelli](/help/analysis-workspace/c-panels/panels.md) al progetto. Ad esempio, **[!DNL Example Panel]** ➊.

* Aggiungi [visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ai pannelli. Ad esempio:
   * Visualizzazione [a linee](/help/analysis-workspace/visualizations/line.md) **[!DNL Line Graph]** ➋
   * Visualizzazione [Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) **[!DNL Countries]** ➌
* Aggiungi [componenti](/help/components/overview.md) alle visualizzazioni. Ad esempio:
   * [Dimensione](/help/components/dimensions/overview.md) **[!DNL Store Country]** ➍
   * [Metrica](/help/components/apply-create-metrics.md) **[!DNL People]** ➎
   * [Metrica calcolata](/help/components/calc-metrics/calc-metr-overview.md) **[!DNL Avg Order Value]** ➏
   * **[!DNL Mobile App Sessions]** [segmento](/help/components/filters/filters-overview.md) ➐
   * [Intervallo di date](/help/components/date-ranges/overview.md) **[!DNL Last Month]** ➑
   * [Annotazione](/help/components/annotations/overview.md) **[!DNL Example]** ➒


## Informazioni e impostazioni progetto {#project-info-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Conta istanze ripetute"
>abstract="Specifica se le istanze ripetute vengono conteggiate o meno nei rapporti.<br/>Nota: questa impostazione non si applica alle visualizzazioni Flusso o Fallout."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Consenti commenti"
>abstract="Quando questa opzione è abilitata, nella barra a destra del progetto in Analysis Workspace è disponibile un’area commenti."

<!-- markdownlint-enable MD034 -->


Impostazioni progetto offre informazioni a livello di progetto sul progetto attualmente attivo.

![Finestra Informazioni e impostazioni progetto.](./assets/projectinfo.png)

Le impostazioni includono:

| Impostazione | Descrizione |
|---|---|
| Nome progetto | Nome assegnato al progetto. Puoi fare doppio clic sul nome per modificarlo. |
| Proprietario | Nome del proprietario del progetto. |
| Ultima modifica | Data dell’ultima modifica apportata al progetto. |
| Tag | Elenca eventuali tag applicati a un progetto per facilitarne la categorizzazione. |
| Descrizione | La descrizione è utile per chiarire lo scopo di un progetto. Puoi fare doppio clic sulla descrizione per modificarla. |
| Conta istanze ripetute | Specifica se le istanze ripetute sono conteggiate o meno nei rapporti. Nota: questa impostazione non si applica alle visualizzazioni Flusso o Abbandono. |
| Mostra annotazioni | Specifica se le annotazioni per questo progetto sono visualizzate o meno. |
| [Palette dei colori del progetto](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Per cambiare la palette di colori utilizzata per le categorie in Workspace, puoi scegliere una delle palette predefinite ottimizzate per il daltonismo o specificarne una personalizzata. Questa funzione interessa numerosi elementi in Workspace, compresa la maggior parte delle visualizzazioni. |
| [Densità di visualizzazione](/help/analysis-workspace/build-workspace-project/view-density.md) | Consente di visualizzare più dati nella schermata riducendo la spaziatura verticale del pannello a sinistra, delle tabelle a forma libera e delle tabelle a coorte. |

<!--

Add this to the table above - exchange - for pipe: (End of April, 2025 when project commenting is GA)

Allow commenting - When this option is enabled, a comments area is available in the right rail of the project in Analysis Workspace. For more information, see [Add and manage comments in projects](/help/analysis-workspace/build-workspace-project/comment-projects.md). 

-->



