---
description: La sincronizzazione delle visualizzazioni consente di individuare la tabella dati o l’origine dati corrispondente a una visualizzazione.
keywords: Analysis Workspace, sincronizzazione di una visualizzazione con un’origine dati
title: Gestione delle origini dati
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: 388e008f4ee092dd8224bfacd020cdf762d4fb82
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 17%

---

# Gestione delle origini dati {#manage-data-sources}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_lockselection"
>title="Blocca selezione"
>abstract="Abilita questa impostazione per bloccare la visualizzazione nelle posizioni selezionate o negli elementi selezionati nell’origine dati."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_lockselection_showtable"
>title="Mostra tabella"
>abstract="Selezionando **[!UICONTROL Show table]** verrà generata una nuova origine dati per la visualizzazione corrente, separata dall&#39;origine dati originale."

<!-- markdownlint-enable MD034 -->



La sincronizzazione delle visualizzazioni consente di individuare la tabella dati o l’origine dati corrispondente a una visualizzazione.

>[!TIP]
>
>Puoi individuare le visualizzazioni correlate dal colore di ![StatusOrange](/help/assets/icons/StatusOrange.svg) accanto al titolo delle visualizzazioni. Colori uguali indicano che le visualizzazioni si basano sulla stessa origine dati.
>

È possibile visualizzare o nascondere l&#39;origine dati. È inoltre possibile bloccare la selezione in base alle posizioni o agli elementi selezionati. Queste impostazioni determinano in che modo la visualizzazione cambia o meno con l’arrivo di nuovi dati.

![La finestra di dialogo delle opzioni di Data Source mostra le opzioni descritte nella sezione successiva.](assets/lock-selection.png)


| Opzione | Descrizione |
|--- |--- |
| **[!UICONTROL Data source]** | Dal menu a discesa, seleziona l’origine dati su cui si basa la visualizzazione. |
| **[!UICONTROL Linked visualizations]** | Elenca tutte le visualizzazioni collegate. Si applica all’origine dati (tabella a forma libera). |
| **[!UICONTROL Show data source]** | Consente di mostrare o nascondere l’origine dati (tabella a forma libera) corrispondente alla visualizzazione. |
| **[!UICONTROL Lock Selection]** | Selezionare questa opzione per bloccare la visualizzazione ![BloccaChiusa](/help/assets/icons/LockClosed.svg) ai dati attualmente selezionati nella tabella di dati corrispondente. Una volta abilitata, seleziona tra:  <ul><li>**Posizioni selezionate**: la visualizzazione è bloccata sulle **posizioni** selezionate nella tabella di dati corrispondente. Queste posizioni continuano a essere visualizzate, anche se gli elementi specifici in queste posizioni cambiano (ad esempio a causa di ordinamenti o filtri). Ad esempio, seleziona questa opzione se desideri visualizzare sempre i primi cinque nomi di campagna elencati nell’origine dati di questa visualizzazione. Indipendentemente dai nomi delle campagne visualizzati.</li> <li>**Elementi selezionati**: la visualizzazione è bloccata su **elementi** specifici attualmente selezionati nella tabella di dati corrispondente. Questi elementi continuano a essere visualizzati, anche se modificano la classificazione tra gli elementi della tabella. Ad esempio, seleziona questa opzione se desideri visualizzare sempre gli stessi cinque nomi di campagna specifici elencati nell’origine dati di questa visualizzazione. Indipendentemente dalla classificazione di quei nomi di campagna.</li></ul>Se la visualizzazione è bloccata su dati che non sono più visibili nella tabella di dati connessa, puoi generare una nuova tabella. Seleziona **[!UICONTROL Show table]** per generare una nuova origine dati per la visualizzazione corrente, separata dall&#39;origine dati originale. |
