---
description: Utilizza i sottotitoli intelligenti per generare informazioni in linguaggio naturale utili a delineare le tendenze nelle visualizzazioni.
title: Didascalie intelligenti
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 7d103e9d709ec076519360a4b43af44f061171e9
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 2%

---

# Didascalie intelligenti {#intelligent-captions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_area"
>title="Sottotitoli intelligenti: area"
>abstract="Genera informazioni approfondite sotto forma di linguaggio naturale per comprendere e interpretare più facilmente i dati per questa visualizzazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_bar"
>title="Sottotitoli intelligenti: barra"
>abstract="Genera informazioni approfondite sotto forma di linguaggio naturale per comprendere e interpretare più facilmente i dati per questa visualizzazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_donut"
>title="Didascalie intelligenti: Anello"
>abstract="Genera informazioni approfondite sotto forma di linguaggio naturale per comprendere e interpretare più facilmente i dati per questa visualizzazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_horizontalbar"
>title="Sottotitoli intelligenti: barra orizzontale"
>abstract="Genera informazioni approfondite sotto forma di linguaggio naturale per comprendere e interpretare più facilmente i dati per questa visualizzazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_line"
>title="Sottotitoli intelligenti: linea"
>abstract="Genera informazioni approfondite sotto forma di linguaggio naturale per comprendere e interpretare più facilmente i dati per questa visualizzazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_fallout"
>title="Sottotitoli intelligenti: Abbandono"
>abstract="Genera informazioni approfondite sotto forma di linguaggio naturale per comprendere e interpretare più facilmente i dati per questa visualizzazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_flow"
>title="Sottotitoli intelligenti: Flusso"
>abstract="Genera informazioni approfondite sotto forma di linguaggio naturale per comprendere e interpretare più facilmente i dati per questa visualizzazione."

<!-- markdownlint-enable MD034 -->

La funzionalità Intelligent Captions utilizza la funzione di intelligenza artificiale generativa avanzata per fornire insights chiave per le visualizzazioni di Workspace più utilizzate nel linguaggio naturale.

I sottotitoli intelligenti sono orientati verso:

* Analisti, che hanno bisogno di narrazioni da condividere con altri utenti. Gli analisti hanno bisogno di queste informazioni per fornire contesto ai loro utenti.
* Utenti aziendali che desiderano scoprire rapidamente soluzioni di alto livello.

## Avvia sottotitoli intelligenti {#launch}

Per avviare i sottotitoli intelligenti generati automaticamente per una visualizzazione, seleziona ![Sottotitoli intelligenti](/help/assets/icons/AI.svg) in alto a destra. Questa selezione genera informazioni sul linguaggio naturale.

![Finestra di analisi del lancio che mostra i sottotitoli intelligenti per la tendenza delle visualizzazioni del prodotto. ](assets/intelligent-captions.gif)


Aspetti da considerare:

* Sono necessari almeno 3 punti dati per generare correttamente le didascalie. In caso contrario, potrebbe verificarsi un errore come **[!UICONTROL Not enough data to analyze]**.

* Le didascalie vengono generate ogni volta che i dati selezionati sottostanti cambiano nella tabella che attiva la visualizzazione.

* Se una tabella a forma libera associata contiene più metriche, le didascalie vengono generate solo per la prima metrica o per la metrica attualmente selezionata dall’utente. Tuttavia, è possibile generare didascalie per più metriche per le visualizzazioni Linee e Area.

* Se salvi il progetto in un punto specifico e lo ricarichi in un secondo momento, i sottotitoli vengono aggiornati automaticamente con i nuovi dati. Lo stesso vale per i progetti programmati e i file PDF esportati da un progetto.


## Visualizzazioni {#visualizations}

I sottotitoli intelligenti sono supportati nelle seguenti visualizzazioni:

* [Riga](line.md) (incluse più righe)
* [Barre](bar.md)
* [Barre orizzontali](horizontal-bar.md)
* [Area](area.md) (incluse più linee di area)
* [Ad anello](donut.md)
* [Fallout (abbandono)](fallout/fallout-flow.md)
* [Flusso](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## Azioni

È possibile eseguire le azioni seguenti sulle didascalie intelligenti:

### Copia negli Appunti {#copy}

È possibile copiare i sottotitoli negli Appunti e incollarli in PowerPoint o in altri strumenti. È possibile copiare singoli sottotitoli nella visualizzazione una per una oppure tutti i sottotitoli contemporaneamente nella visualizzazione dei sottotitoli espansi.

* Per copiare i sottotitoli, seleziona ![Copia sottotitoli negli Appunti](/help/assets/icons/Copy.svg) in alto a destra nella finestra di dialogo dei sottotitoli.

### Mostra tutti o singoli sottotitoli intelligenti  {#show-all-or-individual}

È possibile mostrare tutte le didascalie intelligenti contemporaneamente in una visualizzazione espansa, oppure è possibile mostrare singole didascalie intelligenti in una visualizzazione singola.

* Per visualizzare tutti i sottotitoli intelligenti, selezionare ![Mostra tutti i sottotitoli intelligenti](/help/assets/icons/Maximize.svg).
* Per visualizzare singole didascalie intelligenti, una per una, selezionare ![Mostra singole didascalie intelligenti](/help/assets/icons/Minimize.svg).

### Modifica visualizzazione {#edit}

Puoi modificare la visualizzazione dei sottotitoli, ad esempio per nascondere o rendere visibile una particolare categoria di informazioni.

1. Seleziona ![Modifica visibilità dei sottotitoli intelligenti](/help/assets/icons/EditInLight.svg) nella finestra di dialogo Sottotitoli intelligenti.

1. Attiva/disattiva ![Attiva/disattiva visibilità](/help/assets/icons/Visibility.svg) per visualizzare informazioni specifiche (ad esempio **[!UICONTROL Min]**) oppure ![Attiva/disattiva visibilità](/help/assets/icons/VisibilityOff.svg) per nascondere informazioni specifiche (ad esempio **[!UICONTROL Spike]**).

   ![Modifica didascalie intelligenti](assets/edit-intelligent-captions.png)

1. Seleziona **[!UICONTROL Apply]**.


### Fornire feedback

Puoi fornire un feedback sulle didascalie intelligenti generate (il feedback può essere fornito solo nella vista didascalia espansa).

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

* **Accesso contrattuale**: se non sei in grado di utilizzare i sottotitoli intelligenti, contatta l&#39;amministratore della tua organizzazione o il rappresentante dell&#39;account Adobe (amministratore). Prima di poter utilizzare i sottotitoli intelligenti nell’organizzazione, devi accettare alcuni termini legali relativi all’intelligenza artificiale generativa.

* **Autorizzazioni**: in [!UICONTROL Adobe Admin Console], l&#39;autorizzazione [!UICONTROL Reporting Tools] **[!UICONTROL Intelligent Captions]** determina l&#39;accesso. Un [amministratore del profilo di prodotto](https://helpx.adobe.com/it/enterprise/using/manage-product-profiles.html) deve seguire questi passaggi in [!UICONTROL Admin Console]:
   1. Passa a **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**.
   1. Seleziona il titolo del profilo di prodotto per il quale desideri fornire accesso ai sottotitoli intelligenti.
   1. Nel profilo di prodotto specifico, selezionare **[!UICONTROL Permissions]**.
   1. Seleziona ![Modifica](/help/assets/icons/Edit.svg) per modificare **[!UICONTROL Reporting Tools]**.
   1. Seleziona ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) per aggiungere **Didascalie intelligenti** a **[!UICONTROL Included permission items]**.

      ![Aggiungi autorizzazione](./assets/intelligent-captions-permissions.png)

   1. Selezionare **[!UICONTROL Save]** per salvare le autorizzazioni.

Per ulteriori informazioni, vedere [Controllo dell&#39;accesso](/help/technotes/access-control.md#access-control).
