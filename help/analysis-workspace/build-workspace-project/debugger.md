---
description: Scopri come utilizzare il debugger per risolvere i problemi relativi al progetto in Analysis Workspace.
keywords: Analysis Workspace
feature: Workspace Basics
title: Debugger progetto
role: User
exl-id: 1335ec1f-5597-4e23-8228-3d477534de43
TQID: https://experienceleague.adobe.com/IJCJ64hNUdZu4PHlSu6-tBcjSFVF2QajpfnLp0wbrYQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 476
ht-degree: 4%

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

1. Selezionare **[!UICONTROL Guida]** > **[!UICONTROL Abilita debugger]** dal menu Progetto di Analysis Workspace.
1. Selezionare **[!UICONTROL OK]** nella finestra di dialogo **[!UICONTROL Abilita debugger]**.
1. Conferma quando il browser richiede di ricaricare la pagina o il sito.


## Usa debugger

Dopo aver abilitato il debugger, tutte le visualizzazioni nel progetto presentano un&#39;ulteriore icona ![Bug](/help/assets/icons/Bug.svg).

Per utilizzare il debugger per una visualizzazione specifica:

1. Seleziona ![Bug](/help/assets/icons/Bug.svg) nella parte superiore della visualizzazione.

   ![Menu di scelta rapida debugger](assets/debugger-context-menu.png)

1. Selezionare l&#39;azione appropriata dal menu di scelta rapida. Le azioni disponibili dipendono dalla visualizzazione e indicano il tipo di debug che desideri eseguire. Ad esempio, se selezioni **[!UICONTROL Anomalie]**, vuoi eseguire il debug della funzionalità delle anomalie nella visualizzazione.
1. Dal sottomenu, selezionare un timestamp.
1. Viene visualizzata una finestra di debug **[!UICONTROL XML Oberon]** con i dettagli delle funzionalità specifiche eseguite dalla visualizzazione. Di seguito è riportato un esempio dell’output di una richiesta di anomalie.

   ![Richiesta di debug output](assets/debugger-oberon.png)

   I dettagli sono i seguenti:

   * **[!UICONTROL Timestamp richiesta]**
   * **[!UICONTROL Timestamp risposta]**
   * **[!UICONTROL Ora richiesta]**
   * **[!UICONTROL Ora coda]**
   * **[!UICONTROL Tempo di elaborazione server]**
   * **[!UICONTROL Ora di ricerca]**
   * **[!UICONTROL Complessità]**
   * **[!UICONTROL Limiti del mese]**
   * **[!UICONTROL Colonne]**
   * **[!UICONTROL Segmenti]**
   * **[!UICONTROL XML]** **[!UICONTROL Richiesta]** e **[!UICONTROL Risposta]**
   * **[!UICONTROL richiesta cURL]**
   * **[!UICONTROL JSON]** **[!UICONTROL Richiesta]** e **[!UICONTROL Risposta]**

1. Utilizza ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copia tutto il campo negli Appunti]** per copiare tutte le informazioni di debug negli Appunti. Incolla le informazioni nell’editor o nello strumento preferito. Le informazioni consistono in:

   * XML (richiesta)
   * XML (risposta)
   * JSON (richiesta)
   * JSON (risposta)
   * Richiesta cURL

1. Utilizza ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copia negli Appunti]** sotto **[!UICONTROL richiesta cURL]** per copiare la richiesta negli Appunti.
1. Passa il puntatore del mouse su una delle **[!UICONTROL aree di testo Richiesta]** o **[!UICONTROL Risposta]** per visualizzare e selezionare ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copia negli Appunti]** per copiare il contenuto dell&#39;area di testo (XML o JSON) negli Appunti.

1. Scambia le informazioni copiate e richieste dal supporto Adobe per la risoluzione dei problemi relativi alle visualizzazioni nel progetto Analysis Workspace.

1. Seleziona **[!UICONTROL Annulla]** per chiudere la finestra di debug **[!UICONTROL XML Oberon]** e tornare al progetto.

Ripeti i passaggi precedenti per qualsiasi altra visualizzazione che desideri risolvere.

## Disabilita debugger

>[!IMPORTANT]
>
>Prima di disabilitare il debugger, salva le modifiche apportate al progetto e desideri mantenerle durante l’esercizio di debug.
>

Per disattivare il debugger:

1. Selezionare **[!UICONTROL Guida]** > **[!UICONTROL Disabilita debugger]** dal menu Progetto di Analysis Workspace.
1. Selezionare **[!UICONTROL OK]** nella finestra di dialogo **[!UICONTROL Disattiva debugger]**.
1. Conferma quando il browser richiede di ricaricare la pagina o il sito.
