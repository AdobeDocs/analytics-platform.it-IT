---
description: Il dizionario dati in Analysis Workspace consente agli utenti di catalogare e tenere traccia dei vari componenti in Analysis Workspace, compreso l’uso previsto, che sono approvati, che sono duplicati, e così via.
title: Modificare le voci nel dizionario dati
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: d431e781eb18eb3f4904094972c218a9e80980d9
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# Modificare le voci dei componenti nel dizionario dati

Gli amministratori di Customer Journey Analytics possono modificare le voci dei componenti nel dizionario dati per una data visualizzazione dati. Tutte le modifiche apportate sono visibili a tutti gli utenti della visualizzazione dati.

Per modificare un componente nel dizionario dati:

1. Vai al progetto Analysis Workspace che contiene il componente da modificare.

1. Seleziona la **Dizionario dati** nella barra a sinistra di Analysis Workspace. (I modi alternativi per accedere al dizionario dati sono descritti in &quot;Accedere al dizionario dati&quot; in [Panoramica sul dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md).)

   Viene visualizzata la finestra del dizionario dati.

   ![Visualizzazione amministratore del dizionario dati](assets/data-dictionary-admin.png)

1. Assicurati che nel menu a discesa sia selezionata la visualizzazione dati corretta. Per impostazione predefinita, viene visualizzata la visualizzazione dati già in uso.

1. (Facoltativo) Nel campo di ricerca, inizia a digitare il nome del componente da modificare.

   Il tipo di componente può essere identificato sia dal colore che dall’icona. **Dimension** ![Icona Dimension](assets/dimension-icon.png) sono arancioni, **Segmenti** ![Icona Segmento](assets/segment-icon.png) sono blu, **Intervalli di date** ![Icona Intervallo date](assets/date-range-icon.png) sono viola, e **Metriche** ![Icona della metrica](assets/default-metric-icon.png) sono verdi. Icona Adobe ![Icona Adobe](assets/default-calc-metric-icon.png) indica un modello di metrica calcolata o un modello di segmento e l’icona del calcolatore ![Icona Calcolatore](assets/calculated-metric-icon-created.png) indica una metrica calcolata creata da un amministratore di Analytics nella tua organizzazione.

{{dd-filter-criteria}}

1. (Facoltativo) Seleziona la **Ordinare** icona ![Icona Ordina componenti](assets/component-sort-icon.png), quindi seleziona una delle seguenti opzioni di filtro per ordinare l’elenco dei componenti:

   {{components-sort-options}}

1. Dall’elenco dei componenti, seleziona il componente da modificare.

1. Seleziona la **Modifica** icona ![Icona Modifica dizionario dati](assets/data-dictionary-edit-icon.png) accanto al nome del componente.

1. Modifica una delle seguenti informazioni sul componente:

   {{dd-component-information}}

1. Fai clic sul pulsante **Salva** icona ![Icona Salva dizionario dati](assets/data-dictionary-save-icon.png) per salvare le modifiche.
