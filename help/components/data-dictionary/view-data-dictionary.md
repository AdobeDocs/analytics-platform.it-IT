---
description: Il dizionario dei dati in Analysis Workspace consente agli utenti di catalogare e tenere traccia dei vari componenti in Analysis Workspace, incluso l’uso previsto, quali sono approvati, quali sono duplicati e così via.
title: Visualizza informazioni sul componente
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: 4bfa32ba3a7902d31edefab17a00206f922a8382
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 53%

---

# Visualizza informazioni sul componente

Il dizionario dei dati consente di visualizzare informazioni su un componente, tra cui la sua descrizione, componenti simili, altri componenti con cui viene utilizzato di frequente e altro ancora.

Per visualizzare informazioni su un componente nel dizionario dei dati:

1. Vai al progetto Analysis Workspace che contiene il componente che desideri visualizzare.

1. Seleziona l&#39;icona [!UICONTROL **Dizionario dati**] nel pannello a sinistra di Analysis Workspace. I modi alternativi per accedere al dizionario dati sono descritti in “Accedere al dizionario dei dati” in [Panoramica del dizionario dei dati](/help/components/data-dictionary/data-dictionary-overview.md).

   Viene visualizzata la finestra Dizionario dei dati.

   ![Finestra del dizionario dati con segmenti rapidi per dimensioni, metriche, segmenti e intervalli di date](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Assicurati che la visualizzazione dati contenente il componente che desideri visualizzare sia selezionata nel menu a discesa. Per impostazione predefinita, viene visualizzata la visualizzazione dati in cui si è già connessi.

1. (Facoltativo) Nel campo di ricerca, inizia a digitare il nome del componente che desideri visualizzare.

   Il tipo di componente può essere identificato sia dal colore che dall’icona. **Le dimensioni** ![icona Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sono arancioni, **Filtri** ![icona segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sono blu, **Intervalli di date** ![icona intervallo di date](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sono viola e **Metriche** ![icona metrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sono verdi. L&#39;icona Adobe ![icona Adobe](assets/default-calc-metric-icon.png) indica un modello di metriche calcolate o un modello di segmento e l&#39;icona calcolatrice ![icona calcolatrice](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una metrica calcolata creata da un amministratore Analytics dell&#39;organizzazione.

1. (Facoltativo) Seleziona l&#39;icona **Filtro** ![Icona Filtro dizionario dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), quindi seleziona una delle seguenti opzioni di segmento per segmentare l&#39;elenco dei componenti:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Approvato**] | Mostra solo i componenti contrassegnati come approvati da un amministratore. |
   | [!UICONTROL **Preferiti**] | Mostra solo i componenti inclusi nell’elenco dei Preferiti. Per informazioni sull’aggiunta di componenti all’elenco dei preferiti, consulta [Panoramica dei componenti](/help/components/overview.md). |
   | [!UICONTROL **Dimensioni**] | Mostra solo i componenti che sono Dimensioni. Questa opzione è disponibile anche nella scheda [!UICONTROL **Segmenti rapidi**] quando si accede per la prima volta al dizionario dati. |
   | [!UICONTROL **Metriche**] | Mostra solo i componenti che sono Metriche. Questa opzione è disponibile anche nella scheda [!UICONTROL **Segmenti rapidi**] quando si accede per la prima volta al dizionario dati. |
   | [!UICONTROL **Filtri**] | Mostra solo i componenti che sono filtri. Questa opzione è disponibile anche nella scheda [!UICONTROL **Segmenti rapidi**] quando si accede per la prima volta al dizionario dati. <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Intervalli di date**] | Mostra solo i componenti che sono Intervalli di date. Questa opzione è disponibile anche nella scheda [!UICONTROL **Segmenti rapidi**] quando si accede per la prima volta al dizionario dati. |
   | [!UICONTROL **Mostra tutti**] | Mostra tutti i componenti. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Non approvato**] | Mostra solo i componenti non ancora contrassegnati come approvati da un amministratore. In qualità di amministratore, questo è utile per identificare i componenti che richiedono la revisione e l’approvazione. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Descrizione mancante**] | Mostra solo i componenti che non dispongono ancora di una descrizione nel campo apposito. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Mostra duplicati**] | Mostra solo i componenti con lo stesso nome o la stessa descrizione di un altro componente nella visualizzazione dati selezionata. Sono inclusi i componenti creati e quelli forniti da Adobe. I nomi o le descrizioni devono avere corrispondenze esatte per poter essere visualizzati come duplicati. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Nessun dato recente**] | Mostra solo i componenti che non hanno raccolto dati negli ultimi 90 giorni. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Creato da Adobe**] <!-- I don't see this option--> | Mostra solo i componenti creati da Adobe. I componenti creati da un amministratore o da un altro utente dell’organizzazione non vengono visualizzati. |

   {style="table-layout:auto"}

1. (Facoltativo) Seleziona l&#39;icona **Ordina** ![Ordina icona componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), quindi seleziona una delle seguenti opzioni di segmento per ordinare l&#39;elenco dei componenti:

   {{components-sort-options}}

1. Dall’elenco dei componenti, seleziona il componente che desideri visualizzare.

   Vengono visualizzate le seguenti informazioni sul componente:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Approvato**] | <p>Indica che il componente è stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano un&#39;opzione per [!UICONTROL **annullare l&#39;approvazione**]. Selezionando questa opzione, il componente viene contrassegnato come &quot;Non approvato&quot; per gli utenti.</p> |
   | [!UICONTROL **Non approvato**] | <p>Indica che il componente non è ancora stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano l’opzione [!UICONTROL **Approva**]. Selezionando questa opzione, il componente viene visualizzato dagli utenti come “Approvato”.</p> |
   | [!UICONTROL **Etichetta contesto**] | Questo campo viene visualizzato solo se l’etichetta di contesto del componente è stata aggiornata nella visualizzazione dati. <p>Per ulteriori informazioni, vedere [Impostazioni dei componenti](/help/data-views/component-settings/overview.md). </p> |
   | [!UICONTROL **Descrizione**] | Descrive la funzione prevista del componente. (Queste informazioni vengono aggiunte dall’amministratore di Analytics, come descritto in [Aggiungi descrizioni dei componenti](/help/components/add-component-descriptions.md).) |
   | [!UICONTROL **Utilizzato di frequente con**] | <p>Mostra i componenti più comunemente utilizzati insieme a quello che stai visualizzando.</p><p>Vengono visualizzati fino a 5 componenti nei 5 tipi di componenti principali: Metrica, Metrica calcolata, Dimension, Filtro e Intervallo date.</p><p>Questo elenco è basato sui dati degli ultimi 90 giorni. Vengono mostrati solo i componenti a cui hai accesso alla visualizzazione.</p><p>Gli amministratori possono curare i componenti che gli utenti possono visualizzare in questa sezione, selezionandoli nei campi a discesa [!UICONTROL **Includi sempre**] e [!UICONTROL **Escludi sempre**]. Prima di curare i componenti visualizzati dagli utenti, applica il segmento **Mostra tutto** per assicurarti di visualizzare eventuali componenti non condivisi con te che potrebbero essere stati aggiunti da un altro amministratore.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p> |
   | [!UICONTROL **Simile a**] | <p>Mostra i componenti con nomi simili al componente che stai visualizzando.</p><p>Vengono visualizzati fino a 5 componenti nei 5 tipi di componenti principali: Metrica, Metrica calcolata, Dimension, Filtro e Intervallo date.</p><p>Vengono mostrati solo i componenti a cui hai accesso alla visualizzazione.</p><p>Tutti i componenti duplicati nella visualizzazione dati verranno visualizzati qui. Gli amministratori di Analytics devono identificare e rimuovere tutti i componenti duplicati, come descritto in [Monitorare l’integrità del dizionario dati](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Gli amministratori possono curare i componenti che gli utenti possono visualizzare in questa sezione, selezionandoli nei campi a discesa [!UICONTROL **Includi sempre**] ed [!UICONTROL **Escludi sempre**]. Prima di curare i componenti visualizzati dagli utenti, applica il segmento **Mostra tutto** per assicurarti di visualizzare eventuali componenti non condivisi con te che potrebbero essere stati aggiunti da un altro amministratore.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p><p>**NOTA:** attualmente, la sezione **Simile a** include solo i componenti che hai creato e non quelli forniti da Adobe. I componenti forniti da Adobe verranno aggiunti in una versione futura.</p> |
   | [!UICONTROL **Compatibilità del prodotto**] | Indica dove può essere utilizzata questa metrica calcolata in Customer Journey Analytics. <p>I valori possibili sono:</p><ul><li>[!UICONTROL **Ovunque in Customer Journey Analytics**]: la metrica calcolata può essere utilizzata in tutto Customer Journey Analytics, inclusi Analysis Workspace, Report Builder e così via.</li><li>[!UICONTROL **Ovunque in Customer Journey Analytics (esclusa la sperimentazione)**]: la metrica calcolata può essere utilizzata in tutto Customer Journey Analytics, eccetto nel pannello Sperimentazione.</li> <p>Per informazioni sui criteri che determinano se una metrica calcolata può essere utilizzata con la sperimentazione, vedere [Utilizzare le metriche calcolate nel pannello Sperimentazione](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) in [Pannello Sperimentazione](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
   | [!UICONTROL **Tag**] | Mostra tutti i tag applicati al componente. Gli utenti con accesso amministratore possono aggiungere tag durante la modifica del componente. |
   | [!UICONTROL **Tipo di componente**] | Elenca il tipo di componente, sia esso Dimension, Metrica, Filtro o Intervallo date. |
   | [!UICONTROL **Creato da**] | Mostra il nome dell’utente che ha creato il componente. |
   | [!UICONTROL **Anteprima**] | Mostra un’anteprima dell’aspetto del componente in Analysis Workspace. |
   | [!UICONTROL **Data ultima modifica**] | Mostra il giorno dell’ultima modifica apportata al componente. Questa sezione viene visualizzata quando si visualizzano Filtri, Metriche, Metriche calcolate e Intervalli di date. |

   {style="table-layout:auto"}

1. (Facoltativo) Trascina un componente dal dizionario dei dati ad Analysis Workspace.
