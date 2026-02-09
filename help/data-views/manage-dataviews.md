---
title: Gestire le visualizzazioni dati
description: Scopri come gestire le visualizzazioni dati.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: cb5baf2ec8d3ad4449a9b08d0a025a2d39a11425
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 11%

---


# Gestire le visualizzazioni dati


Dopo aver [creato o modificato una o più visualizzazioni dati](/help/data-views/create-dataview.md), puoi gestirle in **[!UICONTROL Visualizzazioni dati]**.

Seleziona **[!UICONTROL Gestione dati]** > **[!UICONTROL Visualizzazioni dati]** dalla barra dei menu principale in Customer Journey Analytics.

L&#39;interfaccia **[!UICONTROL Visualizzazioni dati]** mostra una tabella di tutte le visualizzazioni dati disponibili.

![Interfaccia delle visualizzazioni dati](/help/data-views/assets/data-views.png)

Nella tabella sono disponibili le colonne e le icone seguenti:

| Colonna o icona | Descrizione |
| --- | --- |
| **[!UICONTROL Nome]** | Nome della visualizzazione dati. |
| ![Informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Per visualizzare informazioni sulla visualizzazione dati, selezionare ![InfoOutline](/help/assets/icons/InfoOutline.svg) accanto al nome della visualizzazione dati.<br/>In una finestra popup vengono visualizzati i dettagli relativi alla visualizzazione dati. |
| ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Seleziona ![Altro](/help/assets/icons/More.svg) per aprire un menu di scelta rapida. Puoi selezionare:<br/>![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Modifica]** per [modificare](#edit-data-views) una visualizzazione dati.<br/>![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copia]** in [Copia una visualizzazione dati](#copy-data-views).<br/>![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Elimina]** per [eliminare](#delete-data-views) una visualizzazione dati.<br/>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Esporta in CSV]** per [esportare i dettagli della visualizzazione dati in un file CSV](#export-data-views-to-csv).<br/>![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Crea progetto]** per [creare un nuovo progetto Workspace](#create-project-from-data-views) per la visualizzazione dati. |
| **[!UICONTROL Connessione]** | Nome della connessione associata alla visualizzazione dati. |
| **[!UICONTROL Sandbox]** | Nome della sandbox associata alla visualizzazione dati. |
| **[!UICONTROL Proprietario]** | Proprietario della visualizzazione dati. |
| **[!UICONTROL Data Insights Agent]** ![InfoStruttura](/help/assets/icons/InfoOutline.svg) | Indica se [Data Insights Agent](/help/data-analysis-ai.md) è **[!UICONTROL Enabled]** o **[!UICONTROL Disabled]** per la visualizzazione dati. <br/>Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per visualizzare un popup con **[!UICONTROL Stato Data Insights Agent]** nelle visualizzazioni dati. <br/>![Utilizzo di Data Insights Agent](/help/data-views/assets/data-views-dia-status.png) |
| **[!UICONTROL Integrazioni]** | Elencare le integrazioni con altre soluzioni. Ad esempio: Adobe Audience Analysis, Content Analytics, Brand Concierge, Journey Optimizer, GenStudio e Usage Analytics. |
| **[!UICONTROL Utilizza in CJA]** | Indica se la visualizzazione dati viene utilizzata in Customer Journey Analytics. Questo valore è solo **[!UICONTROL disattivato]** per le visualizzazioni dati generate automaticamente come parte dell&#39;integrazione di Adobe Journey Optimizer. |
| **[!UICONTROL Data creazione]** | La marca temporale in cui è stata creata la visualizzazione dati. |
| **[!UICONTROL Ultima modifica]** | Il timestamp in cui la visualizzazione dati è stata modificata più di recente. |

Per configurare le colonne da visualizzare nella tabella, selezionare ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). Nella finestra di dialogo **[!UICONTROL Personalizza tabella]**, seleziona le colonne da visualizzare. Quindi selezionare **[!UICONTROL Applica]**.


## Ricerca visualizzazioni dati

Puoi cercare rapidamente una visualizzazione dati utilizzando la casella Cerca ![Ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

## Filtrare le visualizzazioni dati

Per applicare un filtro all&#39;elenco di visualizzazioni dati, selezionare l&#39;icona ![Filtro](/help/assets/icons/Filter.svg), quindi selezionare una delle opzioni di filtro seguenti:

| Opzione filtro | Descrizione |
|---------|----------|
| **[!UICONTROL Connessioni]** | Vengono visualizzate solo le visualizzazioni dati associate alle connessioni selezionate. |
| **[!UICONTROL Proprietario]** | Vengono visualizzate solo le visualizzazioni dati di proprietà delle persone selezionate. |
| **[!UICONTROL Sandbox]** | Vengono visualizzate solo le visualizzazioni dati disponibili nelle sandbox selezionate. |
| **[!UICONTROL Integrazioni]** | Vengono visualizzate solo le visualizzazioni dati con integrazioni selezionate. |
| **[!UICONTROL Utilizza in CJA]** | Selezionare **[!UICONTROL Il]** per visualizzare solo le visualizzazioni dati abilitate per l&#39;utilizzo con Customer Journey Analytics. Seleziona **[!UICONTROL Disattivato]** per visualizzare solo le visualizzazioni dati non ancora abilitate per l&#39;utilizzo con Customer Journey Analytics. |


## Creare una visualizzazione dati

Per [creare una nuova visualizzazione dati](/help/data-views/create-dataview.md), selezionare **[!UICONTROL Crea nuova visualizzazione dati]**.


## Modificare le visualizzazioni dati

Se si desidera [modificare una visualizzazione dati](/help/data-views/create-dataview.md):

1. Seleziona ![Altro](/help/assets/icons/More.svg) accanto al nome della visualizzazione dati.
1. Seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Modifica]** dal menu di scelta rapida.

In alternativa, puoi:

1. Selezionare la riga della visualizzazione dati.
1. Seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Modifica]** dalla barra delle azioni blu.


## Copiare le visualizzazioni dati

Se desideri copiare una visualizzazione dati:

1. Seleziona ![Altro](/help/assets/icons/More.svg) accanto al nome della visualizzazione dati.
1. Seleziona ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copia]** dal menu di scelta rapida.

In alternativa, puoi:

1. Seleziona una o più righe della visualizzazione dati.
1. Seleziona ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copia]** dalla barra delle azioni blu.

La visualizzazione dati viene copiata e aggiunta all&#39;elenco con **[!UICONTROL (Copia)]** aggiunto al nome.


## Eliminare le visualizzazioni dati

Se si desidera eliminare una visualizzazione dati:

1. Seleziona ![Altro](/help/assets/icons/More.svg) accanto al nome della visualizzazione dati.
1. Selezionare ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Elimina]** dal menu di scelta rapida.

In alternativa, puoi:

1. Seleziona una o più righe della visualizzazione dati.
1. Seleziona ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Elimina]** dalla barra delle azioni blu.

Quando elimini una o più visualizzazioni dati, un pannello **[!UICONTROL Elimina visualizzazione dati]** indica i progetti interessati.

![Elimina visualizzazione dati](/help/data-views/assets/delete-data-view.png)


* In ➊ **[!UICONTROL Conferma]** sono visualizzate le implicazioni dell&#39;eliminazione delle visualizzazioni dati.
* Seleziona **[!UICONTROL Elimina]** per eliminare definitivamente le visualizzazioni dati. Seleziona **[!UICONTROL Annulla]** per annullare.


## Esportare le visualizzazioni dati in formato CSV

Puoi esportare una visualizzazione dati in un file CSV.

1. Seleziona ![Altro](/help/assets/icons/More.svg) accanto al nome della visualizzazione dati.
1. Seleziona ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Esporta in CSV]** dal menu di scelta rapida.

In alternativa, puoi:

1. Seleziona una o più righe della visualizzazione dati.
1. Seleziona ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Esporta in CSV]** dalla barra delle azioni blu.

I dettagli delle visualizzazioni dati selezionate vengono esportati in un file CSV denominato `Data views List (x).csv` nella cartella Download del browser.


## Creare un progetto dalle visualizzazioni dati

Puoi creare un progetto Workspace direttamente dall’interfaccia delle visualizzazioni dati.

1. Seleziona ![Altro](/help/assets/icons/More.svg) accanto al nome della visualizzazione dati.
1. Selezionare ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Crea progetto]** dal menu di scelta rapida.

In alternativa, puoi:

1. Selezionare una riga della visualizzazione dati.
1. Seleziona ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Crea progetto]** dalla barra delle azioni blu.


## Attivare o disattivare le visualizzazioni dati per Data Insights Agent

È possibile abilitare o disabilitare una visualizzazione dati per [Data Insights Agent](/help/data-analysis-ai.md).

1. Seleziona ![Altro](/help/assets/icons/More.svg) accanto al nome della visualizzazione dati.
1. Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Abilita per Data Insights Agent]** o ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disabilita per Data Insights Agent]** dal menu di scelta rapida.

In alternativa, puoi:

1. Seleziona una o più righe della visualizzazione dati disabilitate o abilitate per Data Insights Agent.
1. Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Abilita per Data Insights Agent]** o ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disabilita per Data Insights Agent]** dalla barra delle azioni blu.

