---
description: Il dizionario dati in Analysis Workspace consente agli utenti di catalogare e tenere traccia dei vari componenti in Analysis Workspace, compreso l’uso previsto, che sono approvati, che sono duplicati, e così via.
title: Visualizza dizionario dati
feature: Components
role: User, Admin
source-git-commit: 733e0e358aa34ce126687f01ffb6d89f9b0c4210
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Visualizzare le informazioni sui componenti nel dizionario dati

Il dizionario dati consente di visualizzare informazioni su un componente, inclusa la descrizione del componente, componenti simili, altri componenti con cui un componente viene spesso utilizzato e altro ancora.

Per visualizzare informazioni su un componente nel dizionario dati:

1. Vai al progetto Analysis Workspace che contiene il componente che desideri visualizzare.

1. Seleziona la [!UICONTROL **Dizionario dati**] nella barra a sinistra di Analysis Workspace. (I modi alternativi per accedere al dizionario dati sono descritti in &quot;Accedere al dizionario dati&quot; in [Panoramica sul dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md).)

   Viene visualizzata la finestra del dizionario dati.

   ![data-dizionario.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Assicurati che la suite di rapporti contenente il componente che desideri visualizzare sia selezionata nel menu a discesa. Per impostazione predefinita, viene visualizzata la suite di rapporti già in uso.

1. (Facoltativo) Nel campo di ricerca, inizia a digitare il nome del componente che desideri visualizzare.

   Il tipo di componente può essere identificato sia dal colore che dall’icona. **Dimension** ![Icona Dimension](assets/dimension-icon.png) sono arancioni, **Segmenti** ![Icona Segmento](assets/segment-icon.png) sono blu, **Intervalli di date** ![Icona Intervallo date](assets/date-range-icon.png) sono viola, e **Metriche** ![Icona della metrica](assets/default-metric-icon.png) sono verdi. Icona Adobe ![Icona Adobe](assets/default-calc-metric-icon.png) indica un modello di metrica calcolata o un modello di segmento e l’icona del calcolatore ![Icona Calcolatore](assets/calculated-metric-icon-created.png) indica una metrica calcolata creata da un amministratore di Analytics nella tua organizzazione.

{{dd-filter-criteria}}

1. Dall’elenco dei componenti, seleziona il componente da visualizzare.

   Vengono visualizzate le seguenti informazioni sul componente:

   {{dd-component-information}}

1. (Facoltativo) Trascina un componente dal dizionario dati in Analysis Workspace.