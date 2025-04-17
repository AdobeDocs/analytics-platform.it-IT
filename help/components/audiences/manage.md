---
title: Scopri come gestire i tipi di pubblico creato in Customer Journey Analytics
description: Scopri come gestire i tipi di pubblico in Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 65dcbf63d9e155cb7e04bf9a550151a37b8457e6
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 78%

---

# Gestire i tipi di pubblico

I tipi di pubblico possono essere gestiti in Customer Journey Analytics utilizzando **[!UICONTROL Components]** > **[!UICONTROL Audiences]**.

## Comprendere le attività di gestione dell’audience

La gestione dei tipi di pubblico creati in precedenza consente di:

* **pianificare o annullare la pianificazione** dell’aggiornamento automatico del pubblico (la scadenza massima della pianificazione è di un anno);
* **Rinnovare una pianificazione di aggiornamento del pubblico** quando sta per scadere. I tipi di pubblico in scadenza vengono trattati in modo simile ai rapporti pianificati in scadenza: l’amministratore riceve un’e-mail un mese prima della scadenza della pianificazione.
* Visualizzare l’**intervallo di aggiornamento** e l’**ultimo aggiornamento di un tipo di pubblico**
* Ottienere informazioni approfondite sul **tempo impiegato per produrre un tipo di pubblico** da Customer Journey Analytics. E sul tempo necessario perché il tipo di pubblico venga visualizzato nella Real-time Customer Platform a scopo di attivazione.
* Verificare che i tipi di pubblico in Customer Journey Analytics vengano **utilizzati attivamente da Real-time Customer Platform**. Oppure (idealmente) da qualsiasi applicazione Experience Platform che abbia accesso ai tipi di pubblico creati da Customer Journey Analytics.

Se disponi dei diritti di accesso [Visualizzazione pubblico](/help/technotes/access-control.md#user-level-access), puoi visualizzare i tipi di pubblico. Se disponi dell&#39;accesso [Creazione pubblico](/help/technotes/access-control.md#user-level-access), puoi modificare ed eliminare i tipi di pubblico.

## Visualizzare i tipi di pubblico nell’elenco Tipi di pubblico

Nell&#39;elenco Tipi di pubblico vengono visualizzati i tipi di pubblico esistenti.

![Audiences manager](assets/audiences-manager.png)

Per visualizzare l’elenco del pubblico:

1. In Customer Journey Analytics, selezionare **[!UICONTROL Components]** > **[!UICONTROL Audiences]**.

1. (Facoltativo) Utilizza ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per configurare le colonne da visualizzare.

1. (Facoltativo) Cerca un pubblico utilizzando ![Ricerca](/help/assets/icons/Search.svg).

   Sono disponibili le seguenti colonne con informazioni su ciascun pubblico:

   | Colonna | Descrizione |
   | --- | --- |
   | ![SelectBox](/help/assets/icons/SelectBox.svg) | Se sono selezionati uno o più tipi di pubblico, nella parte bassa dell’interfaccia di Tipi di pubblico viene visualizzata una barra blu delle azioni. Per ulteriori dettagli, consulta [Azioni](#actions). |
   | **[!UICONTROL Title & Description]** | Il titolo e la descrizione inseriti durante la creazione del tipo di pubblico. |
   | **[!UICONTROL Data view]** | La visualizzazione dati in cui è stato creato il pubblico. |
   | **[!UICONTROL Audience size]** | Il numero totale di persone nel pubblico. |
   | **[!UICONTROL Owner]** | Il proprietario del tipo di pubblico, ovvero la persona che lo ha creato. |
   | **[!UICONTROL Refresh frequency]** | L’intervallo di aggiornamento configurato al momento della creazione del tipo di pubblico. |
   | **[!UICONTROL Tags]** | Eventuali tag applicati a questo pubblico. |
   | **[!UICONTROL Publishing status]** | Può mostrare ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Ready]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL In progress]** o ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Error]**. |
   | **[!UICONTROL Last refreshed]** | La marca temporale dell’ultimo aggiornamento effettuato al tipo di pubblico. |
   | **[!UICONTROL Last modified]** | La marca temporale dell’ultima modifica apportata al tipo pubblico. |

## Modifica tipi di pubblico

Puoi modificare le impostazioni di un pubblico in qualsiasi momento. Quando modifichi un pubblico (pubblico una tantum o ricorrente), è necessaria una ripubblicazione.

Per modificare un tipo di pubblico:

1. In Customer Journey Analytics, selezionare **[!UICONTROL Components]** > **[!UICONTROL Audiences]**.

   Viene visualizzata la pagina Tipi di pubblico.

1. Seleziona il titolo del pubblico da modificare.

   Viene visualizzata la finestra di dialogo **[!UICONTROL Edit audience]**.

1. Puoi aggiornare uno qualsiasi dei campi disponibili per il pubblico. Per informazioni sui campi che puoi aggiornare, vedi [Generatore di pubblico](/help/components/audiences/publish.md#audience-builder) nell&#39;articolo [Creare e pubblicare tipi di pubblico](/help/components/audiences/publish.md).

1. Seleziona **[!UICONTROL Republish]**.

## Azioni

Di seguito sono riportate le azioni comuni di Gestione progetti programmati: Puoi selezionare le azioni dal menu di scelta rapida:

| Icona | Azione | Descrizione |
|:---:|---|---|
| ![Etichette](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Assegna tag ai tipi di pubblico selezionati. Nella finestra di dialogo **[!UICONTROL Update tags: *nome tipo di pubblico *]**, seleziona i tag dal menu a discesa o digita uno o più nuovi tag. Seleziona **[!UICONTROL Save]**per salvare. |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina i tipi di pubblico selezionati. |
| ![Modifica](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Rinomina il tipo di pubblico selezionato. Utilizza la finestra di dialogo **[!UICONTROL Rename: *nome tipo di pubblico *]**per rinominare il tipo di pubblico e selezionare **[!UICONTROL Save]**per salvare. |

Quando selezioni uno o più progetti pianificati, nella barra blu delle azioni sono disponibili le azioni seguenti.

| Icona | Azione | Descrizione |
|:---:|---|---|
| ![Chiudi](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selezionato]** | Consente di deselezionare i tipi di pubblico selezionati. |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina i tipi di pubblico selezionati. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Esporta i tipi di pubblico selezionati in un file denominato `audiences.csv`. |

## Filtrare l’elenco del pubblico

Puoi filtrare l&#39;[elenco Tipi di pubblico](#audiences-list) utilizzando il pannello dei filtri ➋. Per mostrare o nascondere il pannello dei filtri, utilizza l’icona ![Filtro](/help/assets/icons/Filter.svg).

![Audiences manager](assets/audiences-manager.png)

Il pannello dei filtri è costituito dalle sezioni seguenti.

### Visualizzazione dati

| Visualizzazione dati | Descrizione |
|---|---|
| ![Proprietari](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | La sezione **[!UICONTROL Data view]** consente di filtrare le visualizzazioni dati. <ul><li>Utilizzi ![Cerca](/help/assets/icons/Search.svg) per cercare le visualizzazioni dati da utilizzare per filtrare.</li><li>Puoi selezionare più di una visualizzazione dati.</li></ul> |

### Proprietari

| Proprietario | Descrizione |
|---|---|
| ![Proprietari](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | La sezione **[!UICONTROL Owner]** consente di filtrare in base ai proprietari. <ul><li>Utilizzi ![Cerca](/help/assets/icons/Search.svg) per cercare i proprietari da utilizzare per filtrare.</li><li>Puoi selezionare più di un proprietario. </li></ul> |

## Frequenza di aggiornamento

| Frequenza di aggiornamento | Descrizione |
|---|---|
| ![Frequenza di aggiornamento](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | La sezione **[!UICONTROL Refresh frequency]** consente di filtrare in base alla frequenza di aggiornamento. <ul><li>Utilizzi ![Cerca](/help/assets/icons/Search.svg) per cercare la frequenza di aggiornamento da utilizzare per filtrare.</li><li>Solo le frequenze di aggiornamento definite per i tipi di pubblico<br/> nell’[elenco Tipi di pubblico](#audiences-list) sono visualizzate come opzioni disponibili.</li></ul> |


### Tag

| Tag | Descrizione |
|---|---|
| ![Tag](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | La sezione **[!UICONTROL Tags]** consente di filtrare in base ai tag. <ul><li>Utilizzi ![Cerca](/help/assets/icons/Search.svg) per cercare i tag da utilizzare per filtrare. |
