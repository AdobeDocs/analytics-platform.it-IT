---
description: Il dizionario dati in Analysis Workspace consente agli utenti di catalogare e tenere traccia dei vari componenti in Analysis Workspace, compreso l’uso previsto, che sono approvati, che sono duplicati, e così via.
title: Modificare le voci nel dizionario dati
feature: Components
role: Admin
source-git-commit: 733e0e358aa34ce126687f01ffb6d89f9b0c4210
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Modificare le voci del componente nel dizionario dati

Gli amministratori di Customer Journey Analytics possono modificare le voci dei componenti nel dizionario dati per una determinata suite di rapporti. Tutte le modifiche apportate sono visibili a tutti gli utenti della suite di rapporti.

Per modificare un componente nel dizionario dati:

1. Vai al progetto Analysis Workspace che contiene il componente da modificare.

1. Seleziona la **Dizionario dati** nella barra a sinistra di Analysis Workspace. (I modi alternativi per accedere al dizionario dati sono descritti in &quot;Accedere al dizionario dati&quot; in [Panoramica sul dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md).)

   Viene visualizzata la finestra del dizionario dati.

   ![Visualizzazione amministratore del dizionario dati](assets/data-dictionary-admin.png)

1. Assicurati che nel menu a discesa sia selezionata la suite di rapporti corretta. Per impostazione predefinita, viene visualizzata la suite di rapporti già in uso.

1. (Facoltativo) Nel campo di ricerca, inizia a digitare il nome del componente da modificare.

   Il tipo di componente può essere identificato sia dal colore che dall’icona. **Dimension** ![Icona Dimension](assets/dimension-icon.png) sono arancioni, **Segmenti** ![Icona Segmento](assets/segment-icon.png) sono blu, **Intervalli di date** ![Icona Intervallo date](assets/date-range-icon.png) sono viola, e **Metriche** ![Icona della metrica](assets/default-metric-icon.png) sono verdi. Icona Adobe ![Icona Adobe](assets/default-calc-metric-icon.png) indica un modello di metrica calcolata o un modello di segmento e l’icona del calcolatore ![Icona Calcolatore](assets/calculated-metric-icon-created.png) indica una metrica calcolata creata da un amministratore di Analytics nella tua organizzazione.

{{dd-filter-criteria}}

1. Dall’elenco dei componenti, seleziona il componente da modificare.

1. Seleziona la **Modifica** icona ![Icona Modifica dizionario dati](assets/data-dictionary-edit-icon.png) accanto al nome del componente.

1. Modifica una delle seguenti informazioni sul componente:

   {{dd-component-information}}

1. Fai clic sul pulsante **Salva** icona ![Icona Salva dizionario dati](assets/data-dictionary-save-icon.png) per salvare le modifiche.
