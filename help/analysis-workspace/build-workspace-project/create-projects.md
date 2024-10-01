---
description: Scopri come creare un progetto in Analysis Workspace
title: Creare progetti
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 37%

---

# Creare progetti {#create-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_countrepeatinstances"
>title="Conta istanze ripetute"
>abstract="Specifica se nei rapporti vengono conteggiate le istanze ripetute.<br/><br/>Nota: questa impostazione non si applica alle visualizzazioni Flusso o Abbandono."

<!-- markdownlint-enable MD034 -->


I [progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace consentono di creare e visualizzare analisi business-critical.  Queste analisi possono essere condivise con le parti interessate all’interno o all’esterno dell’organizzazione.

1. In Customer Journey Analytics, selezionare **[!UICONTROL Workspace]**.

1. Seleziona **[!UICONTROL Projects]** nel pannello a sinistra, quindi seleziona **[!UICONTROL Create project]**.

1. Seleziona **Progetto Workspace vuoto** per creare il tuo progetto Workspace utilizzando un browser.

   Consulta [Scorecard per dispositivi mobili vuota](/help/mobile-app/curator.md) per ulteriori informazioni su come creare un progetto di scorecard per dispositivi mobili che puoi condividere con altre parti interessate utilizzando un&#39;app per dispositivi mobili. E consulta [Analisi guidata](/help/guided-analysis/overview.md) per ulteriori informazioni sulle varie opzioni disponibili per creare il tuo progetto di analisi guidata.

1. Seleziona [!UICONTROL **Crea**].


Dopo aver creato un progetto Workspace vuoto, assicurati di avere familiarità con l&#39;interfaccia utente di [Analysis Workspace](/help/analysis-workspace/home.md). Una volta fatto, puoi creare il progetto. Per eseguire questa operazione:

![Progetto di esempio](assets/example-project.png)

* Aggiungi [pannelli](/help/analysis-workspace/c-panels/panels.md) al progetto. Ad esempio, l&#39;elenco delle persone che hanno scelto **[!DNL Example Panel]**.

* Aggiungi [visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ai tuoi pannelli. Ad esempio:
   * **[!DNL Line Graph]** [Riga](/help/analysis-workspace/visualizations/line.md) visualizzazione
   * **[!DNL Countries]** [Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) visualizzazione, in corso...in corso...in corso...in corso...in corso...in corso...in corso...in corso...in corso...in corso...in corso...in corso...
* Aggiungi [componenti](/help/components/overview.md) alle visualizzazioni. Ad esempio:
   * **[!DNL Store Country]** [dimensione](/help/components/dimensions/overview.md)
   * **[!DNL People]** [metrica](/help/components/apply-create-metrics.md) ➎
   * **[!DNL Avg Order Value]** [metrica calcolata](/help/components/calc-metrics/calc-metr-overview.md) ➏
   * **[!DNL Mobile App Sessions]** [filtro](/help/components/filters/filters-overview.md) ➐
   * **[!DNL Last Month]** [intervallo di date](/help/components/date-ranges/overview.md) ➑
   * **[!DNL Example]** [annotazione](/help/components/annotations/overview.md) ➒


## Informazioni e impostazioni progetto {#project-info-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_repeatinstances"
>title="Conta istanze ripetute"
>abstract="Specifica se nei rapporti vengono conteggiate le istanze ripetute.<br/>Nota: questa impostazione non si applica alle visualizzazioni Flusso o Abbandono."

<!-- markdownlint-enable MD034 -->


Le impostazioni del progetto forniscono informazioni a livello di progetto sul progetto attualmente attivo.

![Finestra Informazioni e impostazioni progetto.](./assets/projectinfo.png)

Le impostazioni includono:

| Impostazione | Descrizione |
|---|---|
| Nome progetto | Nome assegnato al progetto. Puoi fare doppio clic sul nome per modificarlo. |
| Proprietario | Nome del proprietario del progetto. |
| Ultima modifica | Data dell’ultima modifica apportata al progetto. |
| Tag | Elenca eventuali tag applicati a un progetto per facilitarne la categorizzazione. |
| Descrizione | La descrizione è utile per chiarire lo scopo di un progetto. Puoi fare doppio clic sulla descrizione per modificarla. |
| Conta istanze ripetute | Specifica se nei rapporti vengono conteggiate le istanze ripetute. Nota: questa impostazione non si applica alle visualizzazioni Flusso o Abbandono. |
| Mostra annotazioni | Specifica se visualizzare o meno le annotazioni per questo progetto. |
| [Palette dei colori del progetto](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Per cambiare la palette di colori utilizzata per le categorie in Workspace, puoi scegliere una delle palette predefinite ottimizzate per il daltonismo o specificarne una personalizzata. Questa funzione interessa numerosi elementi in Workspace, compresa la maggior parte delle visualizzazioni. |
| [Densità di visualizzazione](/help/analysis-workspace/build-workspace-project/view-density.md) | Consente di visualizzare più dati sullo schermo riducendo la spaziatura verticale del pannello sinistro, tabelle a forma libera e tabelle a coorte. |



