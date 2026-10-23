---
description: Scopri come collegare le visualizzazioni a un’origine dati da tabella a forma libera.
keywords: Analysis Workspace, sincronizzazione di una visualizzazione con un’origine dati
title: Gestire le origini dati delle visualizzazioni in Analysis Workspace
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
autotag-review: '2026-05-19T08:30:43.942Z'
TQID: 'https://experienceleague.adobe.com/UU1RlISeu-NOFAttolNcjV-p2EgtxBPFy3w7ZrLz-vY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: f7d853a3b658328f952b675f838ce314b7c30fb1
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 17%
---
# Gestione delle origini dati {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Blocca selezione"
>abstract="Abilita questa impostazione per bloccare la visualizzazione nelle posizioni o gli elementi selezionati nell’origine dati."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Mostra tabella"
>abstract="Selezionando **[!UICONTROL Mostra tabella]** viene generata una nuova origine dati per la visualizzazione corrente, separata dall&#39;origine dati originale."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Mostra tabella"
>abstract="Seleziona **[!UICONTROL Mostra tabella]** per generare una nuova origine dati per la visualizzazione corrente, separata dall’origine dei dati originale."

Ogni visualizzazione in Analysis Workspace si basa su un’origine di dati, in genere una tabella a forma libera. La sincronizzazione delle visualizzazioni consente di controllare quale tabella a forma libera o origine dati corrisponde a una visualizzazione e se la visualizzazione rimane bloccata su righe specifiche della tabella.

>[!TIP]
>
>Puoi individuare le visualizzazioni correlate dal colore del ![StatusOrange](/help/assets/icons/StatusOrange.svg) accanto al titolo delle visualizzazioni. Colori uguali indicano che le visualizzazioni si basano sulla stessa origine dati.
>

## Configurare le impostazioni dell’origine dati {#configure}

1. In Analysis Workspace, vai alla visualizzazione di cui desideri configurare le impostazioni di origine dati o blocco.

1. Passa il puntatore del mouse sulla visualizzazione, quindi seleziona l&#39;icona **[!UICONTROL Impostazioni]** ![Impostazioni](/help/assets/icons/Setting.svg).

1. Selezionare la scheda **[!UICONTROL Origine dati]**.

   ![Scheda Origine dati che mostra l&#39;origine dati, la visualizzazione collegata e le impostazioni di blocco della selezione.](assets/lock-selection.png)

1. Configura una delle seguenti impostazioni:

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Origine dati]** | Seleziona l’origine dati su cui si basa la visualizzazione. |
   | **[!UICONTROL Visualizzazioni collegate]** | Elenca tutte le visualizzazioni collegate all’origine dati (tabella a forma libera). |
   | **[!UICONTROL Mostra origine dati]** | Mostra o nascondi l’origine dati (tabella a forma libera) corrispondente alla visualizzazione. |
   | **[!UICONTROL Blocca selezione]** | Blocca la visualizzazione alle righe attualmente selezionate nell&#39;origine dati, quindi seleziona **[!UICONTROL Posizioni selezionate]** o **[!UICONTROL Elementi selezionati]**. Vedi [Blocca selezione](#lock-selection). |

## Blocca selezione {#lock-selection}

Il blocco della selezione mantiene una visualizzazione incentrata sulle righe selezionate nell’origine dati, anche quando la tabella cambia. Ad esempio, la tabella cambia quando la ordini o filtri, ne modifichi l’intervallo di date o applichi un segmento. Una visualizzazione bloccata mostra ![LockClosed](/help/assets/icons/LockClosed.svg) accanto al titolo.

Se i segmenti, le dimensioni o le metriche nell&#39;origine dati cambiano e i dati bloccati non sono più visibili, selezionare **[!UICONTROL Mostra tabella]** per generare una nuova origine dati per la visualizzazione, separata dall&#39;origine dati originale.

Quando bloccate la selezione, scegliete una delle seguenti opzioni:

| Opzione | Descrizione |
| --- | --- |
| **[!UICONTROL Posizioni selezionate]** | Blocca la visualizzazione alle **posizioni** delle righe selezionate nell&#39;origine dati. Queste posizioni continuano a essere visualizzate, anche se gli elementi in esse contenuti cambiano. Ad esempio, seleziona questa opzione per mostrare sempre i primi cinque nomi di campagna nell’origine dati, indipendentemente dalle campagne in cui si trovano.<br><br>Se blocchi le righe di suddivisione e queste non sono più nella tabella, la visualizzazione non viene visualizzata. Per visualizzarla nuovamente, aggiorna la tabella (ad esempio l’intervallo di date, i segmenti o i filtri) o la selezione dei blocchi. |
| **[!UICONTROL Elementi selezionati]** | Blocca la visualizzazione agli **elementi** specifici selezionati nell&#39;origine dati. Questi elementi continuano a essere visualizzati, anche se la loro classificazione nella tabella cambia. Ad esempio, seleziona questa opzione per mostrare sempre gli stessi cinque nomi di campagna, indipendentemente dalla loro classificazione. |
