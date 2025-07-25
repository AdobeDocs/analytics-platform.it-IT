---
description: Il dizionario dei dati in Analysis Workspace consente agli utenti di catalogare e tenere traccia dei vari componenti in Analysis Workspace, incluso l’uso previsto, quali sono approvati, quali sono duplicati e così via.
title: Modifica voci componente
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: f940e5cba11df0ff158093a503213ff1641b1c5d
workflow-type: tm+mt
source-wordcount: '1182'
ht-degree: 64%

---

# Modifica voci componente

Gli amministratori di Customer Journey Analytics possono modificare le voci dei componenti nel dizionario dati per una determinata visualizzazione dati. Tutte le modifiche apportate sono visibili a tutti gli utenti della visualizzazione dati.

Per modificare un componente nel dizionario dei dati:

1. Vai al progetto Analysis Workspace che contiene il componente da modificare.

1. Seleziona l&#39;icona **Dizionario dati** nel pannello dei pulsanti di Analysis Workspace. I modi alternativi per accedere al dizionario dati sono descritti in “Accedere al dizionario dei dati” in [Panoramica del dizionario dei dati](/help/components/data-dictionary/data-dictionary-overview.md).

   Viene visualizzata la finestra Dizionario dei dati.

   ![Visualizzazione dell&#39;amministratore del dizionario dati con stato del dizionario](assets/data-dictionary-admin.png)

1. Verifica che nel menu a discesa sia selezionata la visualizzazione dati corretta. Per impostazione predefinita, viene visualizzata la visualizzazione dati in cui si è già connessi.

1. (Facoltativo) Nel campo di ricerca, inizia a digitare il nome del componente che desideri modificare.

   Il tipo di componente può essere identificato sia dal colore che dall’icona. **Dimensioni** ![icona Dimensione](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sono arancioni, **Segmenti** ![icona Segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sono blu, **Intervalli di date** ![icona Intervallo di date](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sono viola, e **Metriche** ![icona Metrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sono verdi. L’icona Adobe indica un modello di metrica calcolata o un modello di segmento, e l’icona della calcolatrice ![icona Calcolatrice](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una metrica calcolata creata da un amministratore Analytics della tua organizzazione.

1. (Facoltativo) Seleziona l’icona **Filtro** ![icona Filtro dizionario dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) e quindi una delle seguenti opzioni per filtrare l’elenco dei componenti:

   | Opzione | Funzione |
   |---------|----------|
   | **[!UICONTROL Approved]** | Mostra solo i componenti contrassegnati come approvati da un amministratore. |
   | **[!UICONTROL Favorites]** | Mostra solo i componenti inclusi nell’elenco dei Preferiti. Per informazioni sull’aggiunta di componenti all’elenco dei preferiti, consulta [Panoramica dei componenti](/help/components/overview.md). |
   | **[!UICONTROL Dimensions]** | Mostra solo i componenti che sono Dimensioni. Questa opzione è disponibile anche nella scheda **[!UICONTROL Quick segments]** quando si accede per la prima volta al dizionario dati. |
   | **[!UICONTROL Metrics]** | Mostra solo i componenti che sono Metriche. Questa opzione è disponibile anche nella scheda **[!UICONTROL Quick segments]** quando si accede per la prima volta al dizionario dati. |
   | **[!UICONTROL Segments]** | Mostra solo i componenti che sono Segmenti. Questa opzione è disponibile anche nella scheda **[!UICONTROL Quick segments]** quando si accede per la prima volta al dizionario dati. |
   | **[!UICONTROL Date ranges]** | Mostra solo i componenti che sono Intervalli di date. Questa opzione è disponibile anche nella scheda **[!UICONTROL Quick segments]** quando si accede per la prima volta al dizionario dati. |
   | **[!UICONTROL Show all]** | Mostra tutti i componenti. Questa opzione è disponibile solo per gli amministratori. |
   | **[!UICONTROL Unapproved]** | Mostra solo i componenti non ancora contrassegnati come approvati da un amministratore. In qualità di amministratore, questo è utile per identificare i componenti che richiedono la revisione e l’approvazione. Questa opzione è disponibile solo per gli amministratori. |
   | **[!UICONTROL Missing Description]** | Mostra solo i componenti che non dispongono ancora di una descrizione nel campo apposito. Questa opzione è disponibile solo per gli amministratori. |
   | **[!UICONTROL Show duplicates]** | Mostra solo i componenti con lo stesso nome o la stessa descrizione di un altro componente nella visualizzazione dati selezionata. Sono inclusi i componenti creati e quelli forniti da Adobe. I nomi o le descrizioni devono avere corrispondenze esatte per poter essere visualizzati come duplicati. Questa opzione è disponibile solo per gli amministratori. |
   | **[!UICONTROL No recent data]** | Mostra solo i componenti che non hanno raccolto dati negli ultimi 90 giorni. Questa opzione è disponibile solo per gli amministratori. |
   | **[!UICONTROL Created by Adobe]** <!-- I don't see this option--> | Mostra solo i componenti creati da Adobe. Ad esempio, **[!UICONTROL Adobe Target]**. I componenti creati da un amministratore o da un altro utente dell’organizzazione non vengono visualizzati. |

   {style="table-layout:auto"}

1. (Facoltativo) Seleziona l&#39;icona **Ordina** ![Ordina icona componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), quindi seleziona una delle seguenti opzioni di segmento per ordinare l&#39;elenco dei componenti:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Consigliato**] | Ordina i componenti a partire da quelli consigliati. I componenti utilizzati più di frequente e più di recente da te o da altri nella tua organizzazione vengono visualizzati più in alto nell’elenco. |
   | [!UICONTROL **Alfabetico**] | Ordina alfabeticamente i componenti. |
   | [!UICONTROL **Per categorie**] | Ordina i componenti in base al tipo (dimensione, metrica, segmento, intervallo di date). |

   {style="table-layout:auto"}

1. Dall’elenco dei componenti, seleziona il componente da modificare.

1. Seleziona l’icona **Modifica** ![icona Modifica dizionario dei dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) accanto al nome del componente.

1. Modifica una delle seguenti informazioni sul componente:

   | Opzione | Funzione |
   |---------|----------|
   | **[!UICONTROL Approved]** | <p>Indica che il componente è stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano un&#39;opzione per **[!UICONTROL Unapprove]**. Selezionando questa opzione, il componente viene contrassegnato come &quot;Non approvato&quot; per gli utenti.</p> |
   | **[!UICONTROL Not approved]** | <p>Indica che il componente non è ancora stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano un&#39;opzione per **[!UICONTROL Approve]**. Selezionando questa opzione, il componente viene visualizzato dagli utenti come “Approvato”.</p> |
   | **[!UICONTROL Description]** | Descrive la funzione prevista del componente. (Queste informazioni vengono aggiunte dall’amministratore di Analytics, come descritto in [Aggiungi descrizioni dei componenti](/help/components/add-component-descriptions.md).) |
   | **[!UICONTROL Frequently used with]** | <p>Mostra i componenti più comunemente utilizzati insieme a quello che stai visualizzando.</p><p>Tra i 5 tipi di componenti principali, ne sono mostrati fino a 5: Metrica, Metrica calcolata, Dimensione, Segmento e Intervallo di date.</p><p>Questo elenco è basato sui dati degli ultimi 90 giorni. Vengono mostrati solo i componenti a cui hai accesso alla visualizzazione.</p><p>Gli amministratori possono curare i componenti visualizzati in questa sezione selezionando i componenti desiderati nei campi a discesa **[!UICONTROL Always Include]** e **[!UICONTROL Always Exclude]**. Prima di curare i componenti visualizzati dagli utenti, applica il segmento **Mostra tutto** per assicurarti di visualizzare eventuali componenti non condivisi con te che potrebbero essere stati aggiunti da un altro amministratore.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p> |
   | **[!UICONTROL Similar to]** | <p>Mostra i componenti con nomi simili al componente che stai visualizzando.</p><p>Tra i 5 tipi di componenti principali, ne sono mostrati fino a 5: Metrica, Metrica calcolata, Dimensione, Segmento e Intervallo di date.</p><p>Vengono mostrati solo i componenti a cui hai accesso alla visualizzazione.</p><p>Tutti i componenti duplicati nella visualizzazione dati verranno visualizzati qui. Gli amministratori di Analytics devono identificare e rimuovere tutti i componenti duplicati, come descritto in [Monitorare l’integrità del dizionario dati](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Gli amministratori possono curare i componenti visualizzati in questa sezione selezionando i componenti desiderati nei campi a discesa **[!UICONTROL Always Include]** e **[!UICONTROL Always Exclude]**. Prima di curare i componenti visualizzati dagli utenti, applica il segmento **Mostra tutto** per assicurarti di visualizzare eventuali componenti non condivisi con te che potrebbero essere stati aggiunti da un altro amministratore.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p><p>**NOTA:** attualmente, la sezione **Simile a** include solo i componenti che hai creato e non quelli forniti da Adobe. I componenti forniti da Adobe verranno aggiunti in una versione futura.</p> |
   | **[!UICONTROL Product compatibility]** | Indica dove può essere utilizzata questa metrica calcolata in Customer Journey Analytics. <p>I valori possibili sono:</p><ul><li>**[!UICONTROL Everywhere in Customer Journey Analytics]**: la metrica calcolata può essere utilizzata in tutto Customer Journey Analytics, incluso in Analysis Workspace, Report Builder e così via.</li><li>**[!UICONTROL Everywhere in Customer Journey Analytics (excluding experimentation)]**: la metrica calcolata può essere utilizzata in tutte le parti di Customer Journey Analytics, ad eccezione del pannello Sperimentazione.</li> <p>Per informazioni sui criteri che determinano se una metrica calcolata può essere utilizzata con la sperimentazione, vedere [Utilizzare le metriche calcolate nel pannello Sperimentazione](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) in [Pannello Sperimentazione](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
   | **[!UICONTROL Tags]** | Mostra tutti i tag applicati al componente. Gli utenti con accesso amministratore possono aggiungere tag durante la modifica del componente. |
   | **[!UICONTROL Component type]** | Elenca il tipo di componente, che si tratti di Dimensione, Metrica, Segmento o Intervallo di date. |
   | **[!UICONTROL Created by]** | Mostra il nome dell’utente che ha creato il componente. |
   | **[!UICONTROL Preview]** | Mostra un’anteprima dell’aspetto del componente in Analysis Workspace. |
   | **[!UICONTROL Date last modified]** | Mostra il giorno dell’ultima modifica apportata al componente. Questa sezione viene visualizzata quando si visualizzano segmenti, metriche, metriche calcolate e intervalli di date. |

   {style="table-layout:auto"}

1. Fai clic sull’icona **Salva** ![icona Salva del dizionario dei dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) per salvare le modifiche.
