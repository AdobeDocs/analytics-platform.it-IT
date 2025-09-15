---
description: Scopri come utilizzare i sottotitoli intelligenti per generare informazioni in linguaggio naturale per far emergere le tendenze nelle visualizzazioni.
title: Didascalie intelligenti
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 97%

---

# Didascalie intelligenti {#intelligent-captions}

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions"
>title="Didascalie intelligenti"
>abstract="Genera informazioni approfondite sotto forma di linguaggio naturale per aiutarti a comprendere e interpretare più facilmente i dati per questa visualizzazione."


La funzionalità Didascalie intelligenti utilizza la funzione di intelligenza artificiale generativa avanzata per fornire informazioni chiave aprofondite per le visualizzazioni di Workspace più utilizzate nel linguaggio naturale.

Le didascalie intelligenti sono destinate a:

* Analisti che necessitano di descrizioni da condividere con altri utenti. Gli analisti necessitano di queste informazioni approfondite per poter fornire contesto agli utenti.
* Utenti aziendali che desiderano scoprire rapidamente soluzioni di alto livello.

>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Didascalie intelligenti](https://video.tv.adobe.com/v/3420131/?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


## Avviare didascalie intelligenti {#launch}

Per avviare le didascalie intelligenti generate automaticamente per una visualizzazione, seleziona ![Didascalie intelligenti](/help/assets/icons/AI.svg) in alto a destra della visualizzazione. Questa selezione genera informazioni approfondite sul linguaggio naturale.

![Finestra di avvio analisi che mostra le didascalie intelligenti per la tendenza delle visualizzazioni del prodotto. ](assets/intelligent-captions.gif)


Tieni presente che:

* Sono necessari almeno 3 punti di dati per generare correttamente le didascalie. In caso contrario, potrebbe verificarsi un errore come **[!UICONTROL Not enough data to analyze]**.

* Le didascalie vengono generate ogni volta che i dati selezionati sottostanti cambiano nella tabella che attiva la visualizzazione.

* Se una tabella a forma libera associata contiene più metriche, le didascalie vengono generate solo per la prima metrica o per la metrica attualmente selezionata dall’utente. Tuttavia, è possibile generare didascalie per più metriche per le visualizzazioni A linee ed Area.

* Se salvi il progetto in un punto specifico e lo ricarichi in un secondo momento, le didascalie vengono aggiornate automaticamente con i nuovi dati. Lo stesso vale per i progetti pianificati e i file PDF esportati da un progetto.


## Visualizzazioni {#visualizations}

Le didascalie intelligenti sono supportate nelle seguenti visualizzazioni:

* [A linee](line.md) (incluse più linee)
* [A barre](bar.md)
* [A barre orizzontali](horizontal-bar.md)
* [Area](area.md) (incluse più linee di area)
* [Ad anello](donut.md)
* [Abbandono](fallout/fallout-flow.md)
* [Flusso](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## Azioni

È possibile eseguire le azioni seguenti sulle didascalie intelligenti:

### Copia negli Appunti {#copy}

È possibile copiare le didascalie negli Appunti e incollarle in un PowerPoint o in altri strumenti. Puoi copiare singole didascalie visualizzandole una per una oppure tutte le didascalie contemporaneamente nella visualizzazione delle didascalie espanse.

* Per copiare le didascalie, seleziona ![Copia didascalie negli appunti](/help/assets/icons/Copy.svg) in alto a destra nella finestra di dialogo delle didascalie.

### Mostra tutte o le singole didascalie intelligenti  {#show-all-or-individual}

Puoi mostrare tutte le didascalie intelligenti contemporaneamente in una visualizzazione espansa oppure singole didascalie intelligenti una alla volta.

* Per visualizzare tutte le didascalie intelligenti, seleziona ![Mostra tutte le didascalie intelligenti](/help/assets/icons/Maximize.svg).
* Per visualizzare singole didascalie intelligenti, una alla volta, seleziona ![Mostra singole didascalie intelligenti](/help/assets/icons/Minimize.svg).

### Modifica visualizzazione {#edit}

Puoi modificare la visualizzazione delle didascalie, ad esempio per nascondere o rendere visibile una particolare categoria di informazioni.

1. Seleziona ![Modifica visibilità delle didascalie intelligenti](/help/assets/icons/EditInLight.svg) nella finestra di dialogo Didascalie intelligenti.

1. Utilizza ![Attiva/disattiva visibilità](/help/assets/icons/Visibility.svg) per visualizzare informazioni specifiche (ad esempio **[!UICONTROL Min]**) oppure ![Attiva/disattiva visibilità](/help/assets/icons/VisibilityOff.svg) per nascondere informazioni specifiche (ad esempio **[!UICONTROL Spike]**).

   ![Modificare didascalie intelligenti](assets/edit-intelligent-captions.png)

1. Seleziona **[!UICONTROL Apply]**.


### Fornire feedback

Puoi fornire un feedback sulle didascalie intelligenti generate (il feedback può essere fornito solo nella vista didascalie espanse).

1. Seleziona ![Altre azioni](/help/assets/icons/More.svg) nella finestra di dialogo Didascalie intelligenti.

1. Seleziona ![Risposta valida](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL Good response]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL Bad response]** o ![Flag](/help/assets/icons/Flag.svg) **[!UICONTROL Report]**.

1. Nella finestra di dialogo **[!UICONTROL Thank you for your feedback]**, fornisci il tuo feedback e seleziona **[!UICONTROL Submit]** per inviarlo.

### Esportare {#export}

Puoi esportare didascalie intelligenti come parte di un PDF, purché il progetto venga salvato con le didascalie intelligenti generate.

### Disattivare {#toggle}

Se preferisci non visualizzare le didascalie intelligenti, puoi disattivare questa funzione.

1. Passa a [Preferenze di visualizzazione](/help/analysis-workspace/user-preferences.md#visualizations-preferences)
1. Deseleziona **[!UICONTROL Show intelligent captions]**.

   ![Opzioni di visualizzazione linee che mostrano l’opzione per deselezionare Mostra didascalie intelligenti.](assets/toggle-captions.png)

1. Seleziona **[!UICONTROL Save]** per salvare le modifiche.


## Didascalie intelligenti nelle scorecard per dispositivi mobili

Le didascalie intelligenti sono disponibili anche nelle [scorecard per dispositivi mobili](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) di Customer Journey Analytics.

## Accesso alle funzioni

I seguenti parametri regolano l’accesso alle didascalie intelligenti:

* **Accesso alla soluzione**: la funzione Didascalie intelligenti è disponibile in Customer Journey Analytics, ma non in Adobe Analytics.

* **Accesso contrattuale**: se non sei in grado di utilizzare Didascalie intelligenti, contatta l’amministratore della tua organizzazione o il rappresentante dell’account Adobe (Admin). Prima di poter utilizzare le didascalie intelligenti nell’organizzazione, devi accettare alcuni termini legali relativi all’intelligenza artificiale generativa.

* **Autorizzazioni**: in [!UICONTROL Adobe Admin Console], l’autorizzazione [!UICONTROL Reporting Tools] **[!UICONTROL Intelligent Captions]** determina l’accesso. Un [amministratore del profilo di prodotto](https://helpx.adobe.com/it/enterprise/using/manage-product-profiles.html) deve seguire questi passaggi in [!UICONTROL Admin Console]:
   1. Passa a **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**.
   1. Seleziona il titolo del profilo di prodotto per il quale desideri fornire accesso alle didascalie intelligenti.
   1. Nel profilo di prodotto specifico, seleziona **[!UICONTROL Permissions]**.
   1. Seleziona ![Modifica](/help/assets/icons/Edit.svg) per modificare **[!UICONTROL Reporting Tools]**.
   1. Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) per aggiungere **Didascalie intelligenti** a **[!UICONTROL Included permission items]**.

      ![Aggiungi autorizzazione](./assets/intelligent-captions-permissions.png)

   1. Seleziona **[!UICONTROL Save]** per salvare le modifiche.

Per ulteriori informazioni, consulta [Controllo degli accessi](/help/technotes/access-control.md#access-control).
