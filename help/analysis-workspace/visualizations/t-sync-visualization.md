---
description: Scopri come sincronizzare una tabella a forma libera o un’origine dati con la visualizzazione corrispondente.
keywords: Analysis Workspace, sincronizzazione di una visualizzazione con un’origine dati
title: Gestire le origini dati
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
autotag-review: '2026-05-19T08:30:43.942Z'
TQID: 'https://experienceleague.adobe.com/UU1RlISeu-NOFAttolNcjV-p2EgtxBPFy3w7ZrLz-vY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 83%

---

# Gestione delle origini dati {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Blocca selezione"
>abstract="Abilita questa impostazione per bloccare la visualizzazione nelle posizioni o gli elementi selezionati nell’origine dati."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Mostra tabella"
>abstract="Selezionando **[!UICONTROL Mostra tabella]** verrà generata una nuova origine dati per la visualizzazione corrente, separata dall’origine dei dati originale."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Mostra tabella"
>abstract="Seleziona **[!UICONTROL Mostra tabella]** per generare una nuova origine dati per la visualizzazione corrente, separata dall’origine dei dati originale."

La sincronizzazione delle visualizzazioni consente di controllare quale tabella a forma libera o origine dati corrisponde a una visualizzazione.

>[!TIP]
>
>Puoi individuare le visualizzazioni correlate dal colore del ![StatusOrange](/help/assets/icons/StatusOrange.svg) accanto al titolo delle visualizzazioni. Colori uguali indicano che le visualizzazioni si basano sulla stessa origine dati.
>

Puoi visualizzare o nascondere l’origine dati. Puoi inoltre bloccare la selezione in base alle posizioni o agli elementi selezionati. Queste impostazioni determinano in che modo la visualizzazione cambia o meno con l’arrivo di nuovi dati.

![La finestra di dialogo delle opzioni di origine dati mostra le opzioni descritte nella sezione successiva.](assets/lock-selection.png)


| Opzione | Descrizione |
|--- |--- |
| **[!UICONTROL Origine dati]** | Dal menu a discesa, seleziona l’origine dati su cui si basa la visualizzazione. |
| **[!UICONTROL Visualizzazioni collegate]** | Elenca tutte le visualizzazioni collegate. Si applica all’origine dati (tabella a forma libera). |
| **[!UICONTROL Mostra origine dati]** | Consente di mostrare o nascondere l’origine dati (tabella a forma libera) corrispondente alla visualizzazione. |
| **[!UICONTROL Blocca selezione]** | Seleziona questa opzione per bloccare la visualizzazione ![LockClosed](/help/assets/icons/LockClosed.svg) ai dati attualmente selezionati nella tabella di dati corrispondente. Dopo aver abilitato questa opzione, scegli tra:  <ul><li>**Posizioni selezionate**: la visualizzazione è bloccata sulle **posizioni** selezionate nella tabella di dati corrispondente. Queste posizioni continuano a essere visualizzate, anche se gli elementi specifici in queste posizioni cambiano (ad esempio a causa di ordinamento o filtri). Ad esempio, seleziona questa opzione se desideri visualizzare sempre i primi cinque nomi di campagna elencati nell’origine dati di questa visualizzazione. Indipendentemente dai nomi delle campagne visualizzati.</li> <li>**Elementi selezionati**: la visualizzazione è bloccata su **elementi** specifici attualmente selezionati nella tabella di dati corrispondente. Questi elementi continuano a essere visualizzati, anche se cambiano posizione nel ranking rispetto agli elementi della tabella. Ad esempio, seleziona questa opzione se desideri visualizzare sempre gli stessi cinque nomi di campagna specifici elencati nell’origine dati di questa visualizzazione. Indipendentemente dal ranking di quei nomi di campagna.</li></ul>Se la visualizzazione è bloccata su dati che non sono più visibili nella tabella di dati connessa, puoi generare una nuova tabella. Seleziona **[!UICONTROL Mostra tabella]** per generare una nuova origine dati per la visualizzazione corrente, separata dall&#39;origine dati originale. |
