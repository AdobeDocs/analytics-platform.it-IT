---
description: Scopri come creare un progetto in Analysis Workspace.
title: Creare progetti
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
TQID: https://experienceleague.adobe.com/DWTWJ2Bd9iEPO2awiiOLcUzUGPc-clZul3dNFcyWvxk
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: fa6ac035-8403-478b-9ce1-3fe29d211fca
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 459
ht-degree: 85%

---

# Creare progetti {#create-projects}


I [progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace consentono di creare e visualizzare le analisi business-critical.  Queste analisi possono essere condivise con gli stakeholder all’interno o all’esterno dell’organizzazione.

1. In Customer Journey Analytics, selezionare **[!UICONTROL Workspace]**.

1. Seleziona **[!UICONTROL Progetti]** nel pannello a sinistra, quindi seleziona **[!UICONTROL Crea progetto]**.

1. Seleziona **Progetto Workspace vuoto** per creare il tuo progetto Workspace utilizzando un browser.

   Consulta [Scorecard per dispositivi mobili vuota](/help/mobile-app/curator.md) per ulteriori informazioni su come creare un progetto scorecard per dispositivi mobili che puoi condividere con gli altri stakeholder utilizzando un’app per dispositivi mobili. Per ulteriori informazioni sulle varie opzioni disponibili per creare il tuo progetto di analisi guidata, consulta [Analisi guidata](/help/guided-analysis/overview.md).

1. Seleziona [!UICONTROL **Crea**].


Dopo aver creato un progetto Workspace vuoto, assicurati di avere familiarità con l’interfaccia utente di [Analysis Workspace](/help/analysis-workspace/home.md). Una volta acquisita la familiarità necessaria, puoi creare il progetto. A tale scopo, effettua le seguenti operazioni:

![Progetto di esempio](assets/example-project.png)

* Aggiungi dei [pannelli](/help/analysis-workspace/c-panels/panels.md) al progetto. Ad esempio, **[!DNL Example Panel]** ➊.

* Aggiungi [visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ai pannelli. Ad esempio:
  * **[!DNL Line Graph]** Visualizzazione [a linee](/help/analysis-workspace/visualizations/line.md) ➋
  * **[!DNL Countries]** Visualizzazione [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ➌
* Aggiungi [componenti](/help/components/overview.md) alle visualizzazioni. Ad esempio:
  * **[!DNL Store Country]** [Dimensione](/help/components/dimensions/overview.md) ➍
  * **[!DNL People]** [Metrica](/help/components/apply-create-metrics.md) ➎
  * **[!DNL Avg Order Value]** [Metrica calcolata](/help/components/calc-metrics/calc-metr-overview.md) ➏
  * **[!DNL Mobile App Sessions]** [Segmento](/help/components/segments/seg-overview.md) ➐
  * **[!DNL Last Month]** [Intervallo di date](/help/components/date-ranges/overview.md) ➑
  * **[!DNL Example]** [Annotazione](/help/components/annotations/overview.md) ➒


## Informazioni e impostazioni progetto {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Conta istanze ripetute"
>abstract="Specifica se nei rapporti vengono conteggiate le istanze ripetute.<br/><br/>Nota: questa impostazione non viene applicata alle visualizzazioni Flusso o Fallout."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Numero di istanze ripetute"
>abstract="Specifica se nei rapporti vengono conteggiate le istanze ripetute.<br/>Nota: questa impostazione non viene applicata alle visualizzazioni Flusso o Fallout."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Consenti commenti"
>abstract="Quando questa opzione è abilitata, nella barra a destra del progetto in Analysis Workspace è disponibile un’area commenti."


Impostazioni progetto offre informazioni a livello di progetto sul progetto attualmente attivo.

![Finestra Informazioni e impostazioni progetto.](./assets/projectinfo.png)

Le impostazioni includono:

| Impostazione | Descrizione |
|---|---|
| Nome progetto | Nome assegnato al progetto. È possibile fare doppio clic sul nome per modificarlo. |
| Proprietario | Nome del proprietario del progetto. |
| Ultima modifica | Data dell’ultima modifica al progetto. |
| Tag | Elenca tutti i tag applicati a un progetto per facilitarne la classificazione. |
| Descrizione | Una descrizione è utile per chiarire lo scopo di un progetto. Puoi fare doppio clic sulla descrizione per modificarla. |
| Conta istanze ripetute | Specifica se le istanze ripetute sono conteggiate o meno nei rapporti. Nota: questa impostazione non si applica alle visualizzazioni Flusso o Abbandono. |
| Mostra annotazioni | Specifica se le annotazioni per questo progetto sono visualizzate o meno. |
| [Palette dei colori del progetto](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Per cambiare la palette di colori utilizzata per le categorie in Workspace, puoi scegliere una delle palette predefinite ottimizzate per il daltonismo o specificarne una personalizzata. Questa funzione interessa numerosi elementi in Workspace, compresa la maggior parte delle visualizzazioni. |
| [Densità di visualizzazione](/help/analysis-workspace/build-workspace-project/view-density.md) | Consente di visualizzare più dati nella schermata riducendo la spaziatura verticale del pannello a sinistra, delle tabelle a forma libera e delle tabelle a coorte. |
| Consenti commenti | Quando questa opzione è abilitata, nella barra a destra del progetto in Analysis Workspace è disponibile un’area commenti. Per ulteriori informazioni, consulta [Aggiungere e gestire i commenti nei progetti](/help/analysis-workspace/build-workspace-project/comment-projects.md). |



