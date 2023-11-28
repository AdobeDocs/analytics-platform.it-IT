---
description: Il dizionario dei dati in Analysis Workspace consente agli utenti di catalogare e tenere traccia dei vari componenti in Analysis Workspace, incluso l’uso previsto, quali sono approvati, quali sono duplicati e così via.
title: Modificare le voci nel dizionario dei dati
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 69%

---

# Modificare le voci dei componenti nel dizionario dei dati

Gli amministratori di Customer Journey Analytics possono modificare le voci dei componenti nel dizionario dati per una determinata visualizzazione dati. Tutte le modifiche apportate sono visibili a tutti gli utenti della visualizzazione dati.

Per modificare un componente nel dizionario dei dati:

1. Vai al progetto Analysis Workspace che contiene il componente da modificare.

1. Seleziona l’icona **Dizionario dei dati** nella barra a sinistra di Analysis Workspace. I modi alternativi per accedere al dizionario dati sono descritti in “Accedere al dizionario dei dati” in [Panoramica del dizionario dei dati](/help/components/data-dictionary/data-dictionary-overview.md).

Viene visualizzata la finestra Dizionario dei dati.

![Vista dell’amministratore del dizionario dati che mostra l’integrità del dizionario](assets/data-dictionary-admin.png)

1. Verifica che nel menu a discesa sia selezionata la visualizzazione dati corretta. Per impostazione predefinita, viene visualizzata la visualizzazione dati in cui si è già connessi.

1. (Facoltativo) Nel campo di ricerca, inizia a digitare il nome del componente che desideri modificare.

Il tipo di componente può essere identificato sia dal colore che dall’icona. **Dimension** ![Icona Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sono arancioni, **Filtri** ![Icona del segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sono blu, **Intervalli di date** ![Icona Intervallo date](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sono viola, e **Metriche** ![Icona della metrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sono verdi. L’icona Adobe indica un modello di metrica calcolata o un modello di filtro, e l’icona del calcolatore ![Icona Calcolatrice](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una metrica calcolata creata da un amministratore Analytics della tua organizzazione.

{{dd-filter-criteria}}

1. (Facoltativo) Seleziona l’icona **Ordina** ![icona Ordina componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) e quindi una delle seguenti opzioni per filtrare l’elenco dei componenti:

{{components-sort-options}}

1. Dall’elenco dei componenti, seleziona il componente da modificare.

1. Seleziona l’icona **Modifica** ![icona Modifica dizionario dei dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) accanto al nome del componente.

1. Modifica una delle seguenti informazioni sul componente:

{{dd-component-information}}

1. Fai clic sull’icona **Salva** ![icona Salva del dizionario dei dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) per salvare le modifiche.
