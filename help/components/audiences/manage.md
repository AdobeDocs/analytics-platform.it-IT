---
title: Scopri come gestire i tipi di pubblico creati in Customer Journey Analytics
description: Scopri come gestire i tipi di pubblico in Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 8676497c9341e3ff74d1b82ca79bc1e73caf514f
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 18%

---

# Gestire i tipi di pubblico

I tipi di pubblico possono essere gestiti in Customer Journey Analytics utilizzando **[!UICONTROL Components]** > **[!UICONTROL Audiences]**.

La gestione dei tipi di pubblico creati in precedenza consente di:

* **pianificare o annullare la pianificazione** dell’aggiornamento automatico del pubblico (la scadenza massima della pianificazione è di un anno);
* **Rinnovare una pianificazione di aggiornamento del pubblico** quando sta per scadere. I tipi di pubblico in scadenza vengono trattati in modo simile ai rapporti pianificati in scadenza: l’amministratore riceve un’e-mail un mese prima della scadenza della pianificazione.
* Visualizza l&#39;**intervallo di aggiornamento** e l&#39;**ultimo aggiornamento di un pubblico**
* Ottieni informazioni sul **tempo necessario per produrre un pubblico** dal Customer Journey Analytics. E il tempo necessario per far apparire il pubblico in Real-time Customer Platform a scopo di attivazione.
* Verifica se i tipi di pubblico nel Customer Journey Analytics sono **utilizzati attivamente da Real-time Customer Platform**. Oppure (idealmente) qualsiasi applicazione Experience Platform che utilizzi i tipi di pubblico creati dal Customer Journey Analytics.

Se disponi dell&#39;accesso [Visualizzazione pubblico](/help/technotes/access-control.md#user-level-access), puoi visualizzare i tipi di pubblico. Se disponi dell&#39;accesso [Creazione pubblico](/help/technotes/access-control.md#user-level-access), puoi modificare ed eliminare i tipi di pubblico. L&#39;[elenco tipi di pubblico](#audiences-list) mostra i tipi di pubblico.

## Elenco tipi di pubblico

Nell&#39;elenco Tipi di pubblico vengono visualizzate le colonne relative a:

| Colonna | Descrizione |
| --- | --- |
| ![CasellaSelezione](/help/assets/icons/SelectBox.svg) | Quando sono selezionati uno o più tipi di pubblico, nella parte inferiore dell’interfaccia Tipi di pubblico viene visualizzata una barra blu delle azioni. Vedi [Azioni](#actions) per ulteriori dettagli. |
| **[!UICONTROL Title & Description]** | Il titolo e la descrizione immessi al momento della creazione del pubblico. |
| **[!UICONTROL Data view]** | La visualizzazione dati in cui è stato creato il pubblico. |
| **[!UICONTROL Audience size]** | Il numero totale di persone nel pubblico. |
| **[!UICONTROL Owner]** | Proprietario del pubblico: la persona che ha creato il pubblico. |
| **[!UICONTROL Refresh frequency]** | L’intervallo di aggiornamento configurato al momento della creazione del pubblico. |
| **[!UICONTROL Tags]** | Eventuali tag applicati a questo pubblico. |
| **[!UICONTROL Publishing status]** | Può mostrare ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Ready]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL In progress]** o ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Error]**. |
| **[!UICONTROL Last refreshed]** | Timestamp dell’ultimo aggiornamento del pubblico. |
| **[!UICONTROL Last modified]** | Timestamp dell’ultima modifica o modifica del pubblico. |

È possibile utilizzare ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per configurare le colonne da visualizzare. Cerca un pubblico utilizzando ![Ricerca](/help/assets/icons/Search.svg).

Per modificare un pubblico:

1. Seleziona il titolo del pubblico. Utilizza la finestra di dialogo **[!UICONTROL Edit audience project]** per aggiornare il pubblico. Per ulteriori dettagli, consulta [Generatore di pubblico](publish.md#audience-builder).

1. Seleziona **[!UICONTROL Republish]** per ripubblicare il pubblico.


## Azioni

Di seguito sono riportate le azioni più comuni di Gestione progetti programmati. Puoi selezionare le azioni dal menu di scelta rapida:

| Icona | Azione | Descrizione |
|:---:|---|---|
| ![Etichette](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Assegna tag ai tipi di pubblico selezionati. Nella finestra di dialogo **[!UICONTROL Update tags: *nome pubblico *]**, seleziona i tag dal menu a discesa o digita uno o più nuovi tag. Selezionare **[!UICONTROL Save]**per salvare. |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina il pubblico selezionato. |
| ![Modifica](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Rinomina il pubblico selezionato. Utilizza la finestra di dialogo **[!UICONTROL Rename: *nome pubblico *]**per rinominare il pubblico e selezionare **[!UICONTROL Save]**da salvare. |

Quando selezioni uno o più progetti pianificati, dalla barra delle azioni blu sono disponibili le seguenti azioni.

| Icona | Azione | Descrizione |
|:---:|---|---|
| ![Chiudi](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selezionato]** | Seleziona per deselezionare i tipi di pubblico selezionati. |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina il pubblico selezionato. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Esporta i tipi di pubblico selezionati in un file denominato `audiences.csv`. |

## Filtro

Puoi filtrare l&#39;[elenco Tipi di pubblico](#audiences-list) utilizzando il pannello dei filtri Per mostrare o nascondere il pannello dei filtri, utilizza ![Filtro](/help/assets/icons/Filter.svg).

Il pannello dei filtri è costituito dalle sezioni seguenti.

### Visualizzazione dati

| Visualizzazione dati | Descrizione |
|---|---|
| ![Proprietari](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | La sezione **[!UICONTROL Data view]** consente di filtrare le visualizzazioni dati. <ul><li>![Cerca](/help/assets/icons/Search.svg) per cercare le visualizzazioni dati da utilizzare per filtrare.</li><li>Puoi selezionare più di una visualizzazione dati.</li></ul> |

### Proprietari

| Proprietario | Descrizione |
|---|---|
| ![Proprietari](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | La sezione **[!UICONTROL Owner]** consente di filtrare in base ai proprietari. <ul><li>![Cerca](/help/assets/icons/Search.svg) per cercare i proprietari da utilizzare per filtrare.</li><li>È possibile selezionare più di un proprietario. </li></ul> |

## Refresh frequency (Frequenza di aggiornamento)

| Refresh frequency (Frequenza di aggiornamento) | Descrizione |
|---|---|
| ![Frequenza di aggiornamento](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | La sezione **[!UICONTROL Refresh frequency]** consente di filtrare in base alla frequenza di aggiornamento. <ul><li>![Cerca](/help/assets/icons/Search.svg) per cercare la frequenza di aggiornamento da utilizzare per filtrare.</li><li>Solo le frequenze di aggiornamento definite per i tipi di pubblico<br/> nell&#39;elenco [Tipi di pubblico](#audiences-list) sono visualizzate come opzioni disponibili.</li></ul> |


### Tag

| Tag | Descrizione |
|---|---|
| ![Tag](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | La sezione **[!UICONTROL Tags]** consente di filtrare i tag. <ul><li>![Cerca](/help/assets/icons/Search.svg) per cercare i tag da utilizzare per filtrare. |
