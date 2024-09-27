---
description: Utilizza i sottotitoli intelligenti per generare informazioni in linguaggio naturale e far emergere rapidamente le tendenze nelle visualizzazioni.
title: Didascalie intelligenti
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 93b4426bc3e46540d3b4c9d6ae816a6d1f96f6ed
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 5%

---

# Didascalie intelligenti

Le didascalie intelligenti utilizzano l’apprendimento automatico avanzato e l’intelligenza artificiale generativa per fornire informazioni approfondite relative al linguaggio naturale per le visualizzazioni di Workspace. La versione iniziale fornisce informazioni generate automaticamente sulla visualizzazione [Riga](line.md). Seguiranno altre visualizzazioni.

I sottotitoli intelligenti sono orientati verso:

* Analisti, che hanno bisogno di narrazioni da condividere con altri utenti. Gli analisti hanno bisogno di queste informazioni per fornire contesto ai loro utenti.
* Utenti aziendali che desiderano scoprire rapidamente soluzioni di alto livello.

## Avvia sottotitoli intelligenti {#launch}

Per avviare i sottotitoli generati automaticamente per una visualizzazione delle linee, fai clic sull&#39;icona **[!UICONTROL Intelligent captions]** in alto a destra della visualizzazione.

![Finestra di analisi del lancio che mostra i sottotitoli intelligenti per la tendenza delle visualizzazioni del prodotto. ](assets/intell-caps-1.png)

Vengono ora generate informazioni sul linguaggio naturale.

Nota bene

* Sono necessari almeno 3 punti dati per generare correttamente le didascalie. In caso contrario, potrebbe verificarsi un errore come **[!UICONTROL Not enough data to analyze]**.

* Le didascalie vengono generate ogni volta che i dati selezionati sottostanti cambiano nella tabella che attiva la visualizzazione.

* Se la tabella contiene più metriche, le didascalie vengono generate solo per la prima metrica o per la metrica attualmente selezionata dall’utente.

* Se salvi il progetto in un punto specifico e lo ricarichi in un secondo momento, i sottotitoli vengono aggiornati automaticamente con i nuovi dati. Lo stesso vale per i progetti programmati e i file PDF esportati da un progetto.

Ecco un esempio di sottotitoli intelligenti:

![Sottotitoli intelligenti per la visualizzazione delle linee, inclusi Stagionalità, Min, Max, Picco e Rifiuto.](assets/captions.png)

## Azioni

È possibile eseguire le azioni seguenti sulle didascalie intelligenti:

### Copia negli Appunti {#copy}

È possibile copiare i sottotitoli negli Appunti e incollarli in PowerPoint o in altri strumenti. Seleziona ![Copia sottotitoli negli Appunti](/help/assets/icons/Copy.svg) in alto a destra nella finestra di dialogo sottotitoli.

### Modifica visualizzazione {#edit}

Puoi modificare la visualizzazione dei sottotitoli, ad esempio per nascondere o rendere visibile una particolare categoria di informazioni.

1. Selezionare ![Modifica didascalie intelligenti ](/help/assets/icons/EditInLight.svg) nella finestra di dialogo Didascalie intelligenti.

1. Passa da ![Visibilità](/help/assets/icons/Visibility.svg) per visualizzare informazioni specifiche (come **[!UICONTROL Min]**) a ![VisibilitàDisattivata](/help/assets/icons/VisibilityOff.svg) per nascondere informazioni specifiche (come **[!UICONTROL Spike]**).

   ![Modifica didascalie intelligenti](assets/edit-intelligent-captions.png)

1. Seleziona **[!UICONTROL Apply]**.


### Fornire feedback

Puoi fornire un feedback sulle didascalie intelligenti generate.

1. Seleziona ![Altre azioni](/help/assets/icons/More.svg) nella finestra di dialogo Sottotitoli intelligenti.

1. Seleziona ![Risposta valida](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL Good response]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL Bad response]** o ![Contrassegno](/help/assets/icons/Flag.svg) **[!UICONTROL Report]**.

1. Nella finestra di dialogo **[!UICONTROL Thank you for your feedback]**, fornisci il tuo feedback e seleziona **[!UICONTROL Submit]** per inviare il feedback.

### Esportazione {#export}

È possibile esportare sottotitoli intelligenti come parte di un PDF, purché il progetto venga salvato con i sottotitoli intelligenti generati.

### Disattiva {#toggle}

Se preferisci non visualizzare i sottotitoli intelligenti, puoi disattivare questa funzione.

1. Vai a [Preferenze visualizzazioni](/help/analysis-workspace/user-preferences.md#visualizations-preferences).
1. Deseleziona **[!UICONTROL Show intelligent captions]**.

   ![Opzioni di visualizzazione delle linee che mostrano l&#39;opzione per deselezionare Mostra sottotitoli intelligenti.](assets/toggle-captions.png)

1. Selezionare **[!UICONTROL Save]** per salvare la preferenza.


## Sottotitoli intelligenti nelle scorecard per dispositivi mobili

Le didascalie intelligenti sono disponibili anche nelle [scorecard per dispositivi mobili del Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions).

## Accesso alle funzioni

I seguenti parametri regolano l’accesso alle didascalie intelligenti:

* **Accesso alla soluzione**: la funzione Sottotitoli intelligenti è disponibile nel Customer Journey Analytics, ma non in Adobe Analytics.

* **Accesso contrattuale**: se non sei in grado di utilizzare i sottotitoli intelligenti, contatta l&#39;amministratore della tua organizzazione o il rappresentante dell&#39;account Adobe. Prima di poter utilizzare i sottotitoli intelligenti nella tua organizzazione, devi accettare alcuni termini legali relativi a GenAI.

* **Autorizzazioni**: in [!UICONTROL Adobe Admin Console], l&#39;autorizzazione [!UICONTROL Reporting Tools] **[!UICONTROL Intelligent Captions]** determina l&#39;accesso. Un [amministratore del profilo di prodotto](https://helpx.adobe.com/it/enterprise/using/manage-product-profiles.html) deve seguire questi passaggi in [!UICONTROL Admin Console]:
   1. Passa a **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**.
   1. Seleziona il titolo del profilo di prodotto per il quale desideri fornire accesso ai sottotitoli intelligenti.
   1. Nel profilo di prodotto specifico, selezionare **[!UICONTROL Permissions]**.
   1. Seleziona ![Modifica](/help/assets/icons/Edit.svg) per modificare **[!UICONTROL Reporting Tools]**.
   1. Seleziona ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) per aggiungere **Didascalie intelligenti** a **[!UICONTROL Included permission items]**.

      ![Aggiungi autorizzazione](./assets/intelligent-captions-permissions.png)

   1. Selezionare **[!UICONTROL Save]** per salvare le autorizzazioni.

Per ulteriori informazioni, vedere [Controllo dell&#39;accesso](/help/technotes/access-control.md#access-control).
