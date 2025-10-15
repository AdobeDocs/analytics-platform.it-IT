---
description: Scopri come utilizzare il debugger per risolvere i problemi relativi al progetto in Analysis Workspace.
keywords: Analysis Workspace
feature: Workspace Basics
title: Debugger progetto
role: User
exl-id: 1335ec1f-5597-4e23-8228-3d477534de43
source-git-commit: 695d5f686d10fc39b1b3d717a19fd6e874d81b33
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 2%

---

# Debugger progetto

Il debugger del progetto consente a te e al Supporto Adobe di risolvere i problemi relativi ai progetti in Analysis Workspace. Il supporto Adobe potrebbe richiedere di abilitare il debugger per la risoluzione dei problemi dei ticket generati con il supporto Adobe. Esempi di problemi sono il tempo di caricamento delle visualizzazioni o i componenti interrotti nelle visualizzazioni.

>[!NOTE]
>
>Per utilizzare il debugger, è necessario avere accesso **Modifica** o **Copia** [al progetto](https://experienceleague.adobe.com/it/docs/experience-cloud-kcs/kbarticles/ka-25744).
>


## Abilita debugger

>[!IMPORTANT]
>
>Salva il progetto prima di abilitare il debugger.
>

Per abilitare il debugger:

1. Selezionare **[!UICONTROL Help]** > **[!UICONTROL Enable debugger]** dal menu del progetto Analysis Workspace.
1. Selezionare **[!UICONTROL OK]** nella finestra di dialogo **[!UICONTROL Enable Debugger]**.
1. Conferma quando il browser richiede di ricaricare la pagina o il sito.


## Usa debugger

Dopo aver abilitato il debugger, tutte le visualizzazioni nel progetto presentano un&#39;ulteriore icona ![Bug](/help/assets/icons/Bug.svg).

Per utilizzare il debugger per una visualizzazione specifica:

1. Seleziona ![Bug](/help/assets/icons/Bug.svg) nella parte superiore della visualizzazione.

   ![Menu di scelta rapida debugger](assets/debugger-context-menu.png)

1. Selezionare l&#39;azione appropriata dal menu di scelta rapida. Le azioni disponibili dipendono dalla visualizzazione e indicano il tipo di debug che desideri eseguire. Ad esempio, se selezioni **[!UICONTROL Anomalies]**, vuoi eseguire il debug della funzionalità delle anomalie nella visualizzazione.
1. Dal sottomenu, selezionare un timestamp.
1. Viene visualizzata una finestra di debug **[!UICONTROL Oberon XML]** con i dettagli delle funzionalità specifiche eseguite dalla visualizzazione. Di seguito è riportato un esempio dell’output di una richiesta di anomalie.

   ![Richiesta di debug output](assets/debugger-oberon.png)

   I dettagli sono i seguenti:

   * **[!UICONTROL Request timestamp]**
   * **[!UICONTROL Response timestamp]**
   * **[!UICONTROL Request time]**
   * **[!UICONTROL Queue time]**
   * **[!UICONTROL Server processing time]**
   * **[!UICONTROL Lookup time]**
   * **[!UICONTROL Complexity]**
   * **[!UICONTROL Month boundaries]**
   * **[!UICONTROL Columns]**
   * **[!UICONTROL Segments]**
   * **[!UICONTROL XML]** **[!UICONTROL Request]** e **[!UICONTROL Response]**
   * **[!UICONTROL cURL Request]**
   * **[!UICONTROL JSON]** **[!UICONTROL Request]** e **[!UICONTROL Response]**

1. Utilizza ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copy all field to clipboard]** per copiare tutte le informazioni di debug negli Appunti. Incolla le informazioni nell’editor o nello strumento preferito. Le informazioni consistono in:

   * XML (richiesta)
   * XML (risposta)
   * JSON (richiesta)
   * JSON (risposta)
   * Richiesta curl

1. Utilizza ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copy to clipboard]** sotto **[!UICONTROL cURL Request]** per copiare la richiesta negli Appunti.
1. Passa il puntatore del mouse su una delle **[!UICONTROL Request]** o **[!UICONTROL Response]** aree di testo per visualizzare e selezionare ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copy to clipboard]** per copiare il contenuto di tale area di testo (XML o JSON) negli Appunti.

1. Scambia le informazioni copiate e richieste dal supporto Adobe per la risoluzione dei problemi relativi alle visualizzazioni nel progetto Analysis Workspace.

1. Selezionare **[!UICONTROL Cancel]** per chiudere la finestra di debug **[!UICONTROL Oberon XML]** e tornare al progetto.

Ripeti i passaggi precedenti per qualsiasi altra visualizzazione che desideri risolvere.

## Disabilita debugger

>[!IMPORTANT]
>
>Prima di disabilitare il debugger, salva le modifiche apportate al progetto e desideri mantenerle durante l’esercizio di debug.
>

Per disattivare il debugger:

1. Selezionare **[!UICONTROL Help]** > **[!UICONTROL Disable debugger]** dal menu del progetto Analysis Workspace.
1. Selezionare **[!UICONTROL OK]** nella finestra di dialogo **[!UICONTROL Disable debugger]**.
1. Conferma quando il browser richiede di ricaricare la pagina o il sito.
