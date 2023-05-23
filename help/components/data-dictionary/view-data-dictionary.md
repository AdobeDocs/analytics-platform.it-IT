---
description: Il dizionario dati in Analysis Workspace consente agli utenti di catalogare e tenere traccia dei vari componenti in Analysis Workspace, incluso l’uso previsto, che vengono approvati, che sono duplicati e così via.
title: Visualizzare il dizionario dati
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: b38b5b54ebbf301a3e59156d484bf5d69974b4a4
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 2%

---

# Visualizzare le informazioni sui componenti nel dizionario dati

Il dizionario dati consente di visualizzare informazioni su un componente, tra cui la descrizione del componente, componenti simili, altri componenti con cui un componente è utilizzato di frequente e altro ancora.

Per visualizzare informazioni su un componente nel dizionario dati:

1. Vai al progetto Analysis Workspace che contiene il componente che desideri visualizzare.

1. Seleziona la [!UICONTROL **Dizionario dati**] nella barra a sinistra di Analysis Workspace. (I modi alternativi per accedere al dizionario dati sono descritti in &quot;Accedere al dizionario dati&quot; in [Panoramica del dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md).)

   Viene visualizzata la finestra Dizionario dati.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Assicurati che la visualizzazione dati contenente il componente che desideri visualizzare sia selezionata nel menu a discesa. Per impostazione predefinita, viene visualizzata la visualizzazione dati in cui si è già connessi.

1. (Facoltativo) Nel campo di ricerca, inizia a digitare il nome del componente che desideri visualizzare.

   Il tipo di componente può essere identificato sia dal colore che dall’icona. **Dimension** ![Icona Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sono arancioni, **Segmenti** ![Icona del segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sono blu, **Intervalli di date** ![Icona Intervallo date](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sono viola, e **Metriche** ![Icona della metrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sono verdi. Icona Adobe ![Icona Adobe](assets/default-calc-metric-icon.png) indica un modello di metrica calcolata o un modello di segmento e l’icona della calcolatrice ![Icona Calcolatrice](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una metrica calcolata creata da un amministratore Analytics della tua organizzazione.

{{dd-filter-criteria}}

1. (Facoltativo) Seleziona la **Ordina** icona ![Icona Ordina componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), quindi seleziona una delle seguenti opzioni di filtro per ordinare l’elenco dei componenti:

   {{components-sort-options}}

1. Dall’elenco dei componenti, seleziona il componente che desideri visualizzare.

   Vengono visualizzate le seguenti informazioni sul componente:

   {{dd-component-information}}

1. (Facoltativo) Trascina un componente dal dizionario dati ad Analysis Workspace.
