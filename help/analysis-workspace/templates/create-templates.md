---
description: Scopri come creare e gestire i modelli in Analysis Workspace.
title: Creare e gestire i modelli
feature: Workspace Basics
role: User, Admin
exl-id: 23cdf02f-56a1-4465-ae7f-b3a1bcad28af
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '1689'
ht-degree: 100%

---

# Creare e gestire i modelli

Gli amministratori possono creare modelli e salvarli affinché possano essere utilizzati da altri utenti dell’azienda da cui accedi

Gli utenti dell’azienda da cui accedi possono utilizzare questi modelli aziendali come descritto in [Utilizzare i modelli](/help/analysis-workspace/templates/use-templates.md).

## Creare un modello {#create-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="use-case-ajo-template"
>title="Utilizzare i modelli in Journey Optimizer"
>abstract="Quando utilizzi questo modello in Journey Optimizer, viene utilizzata la visualizzazione dati impostata come predefinita in Adobe Journey Optimizer, indipendentemente dalla visualizzazione dati selezionata con questo modello in Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

Per creare un nuovo modello utilizzabile dalle persone dell’azienda da cui accedi:

1. In Analysis Workspace, crea un progetto con lo stato desiderato.

1. Seleziona [!UICONTROL **Progetto**] > **[!UICONTROL Save as template…]**.

   ![Modello aziendale](assets/company-template-save.png)

1. Specifica le informazioni seguenti nella finestra di dialogo [!UICONTROL Save as template]:

   | Campo | Descrizione |
   |---------|----------|
   | **[!UICONTROL Name]** | Inserisci un nome descrittivo per il modello. |
   | **[!UICONTROL Description]** | Fornisci una breve descrizione del modello che ne indichi gli usi previsti. |
   | **[!UICONTROL Why use this template]** | Inserisci una breve spiegazione per indicare alle persone dell’organizzazione come potrebbe essere utilizzato questo modello. Questa spiegazione viene visualizzata nella pagina Anteprima del modello. |
   | **[!UICONTROL Channels]** | Scegli tutti i canali applicabili a questo modello. Puoi selezionare più canali: **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL Cross-channel]**, **[!UICONTROL Call center]** e **[!UICONTROL In-store]**.<p>Le selezioni effettuate determinano dove viene visualizzato il modello e quali segmenti sono applicabili per gli utenti che vi accedono dalla pagina Modelli organizzazione.</p> |
   | **[!UICONTROL Use cases]** | Scegli eventuali casi d’uso applicabili a questo modello. Puoi selezionare più casi d’uso: **[!UICONTROL Engagement]**, **[!UICONTROL Conversion]**, **[!UICONTROL Audience]**, **[!UICONTROL Acquisition]** e **[!UICONTROL Journey Optimizer]**. <p>Le selezioni effettuate determinano la posizione del modello nella pagina Modelli organizzazione. Gli utenti possono passare al modello o filtrare l’elenco in base al caso d’uso. </p><p>**Nota:** quando selezioni l’opzione **[!UICONTROL Journey Optimizer]**, il modello è disponibile per l’utilizzo in Adobe Journey Optimizer. In Journey Optimizer, nella pagina **[!UICONTROL Reports]** è disponibile un menu a discesa che consente agli utenti di selezionare questo modello o quello predefinito. Per ulteriori informazioni, consulta [Introduzione alla esperienza di reporting aggiornata](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) nella documentazione di Journey Optimizer.</p><p>Quando selezioni l’opzione Journey Optimizer, tieni presente quanto segue:</p><ul><li>Questa opzione è disponibile solo se i dati di Journey Optimizer sono presenti nella visualizzazione dati utilizzata in Customer Journey Analytics.</li><li>Quando utilizzi questo modello in Journey Optimizer, viene utilizzata la visualizzazione dati impostata come predefinita in Adobe Journey Optimizer, indipendentemente dalla visualizzazione dati selezionata con questo modello in Customer Journey Analytics. <br/>Per ulteriori informazioni sull’impostazione di una visualizzazione dati come predefinita in Journey Optimizer, consulta [Compatibilità](/help/data-views/create-dataview.md#compatibility) in [Creare o modificare una visualizzazione di dati](/help/data-views/create-dataview.md).</li></ul> |
   | **[!UICONTROL Journey Optimizer activity type]** | Scegli il tipo di attività Journey Optimizer da associare al modello: **[!UICONTROL Campaigns]**, **[!UICONTROL Journeys]**, **[!UICONTROL Landing pages]**, **[!UICONTROL Reports]** o **[!UICONTROL Subscriptions]**. <p>Lascia vuoto questo campo se vuoi che questo modello sia associato a tutti i tipi di attività.</p><p>Questo campo viene visualizzato solo se nel campo **[!UICONTROL Use cases]** è selezionato **[!UICONTROL Journey Optimizer]**.</p> |
   | **[!UICONTROL Journey Optimizer activity]** | Scegli l’attività Journey Optimizer da associare a questo modello. <p>Lascia vuoto questo campo se vuoi che questo modello sia associato a tutte le attività del tipo di attività selezionato.</p><p>Questo campo viene visualizzato solo se nel campo **[!UICONTROL Use cases]** è selezionato **[!UICONTROL Journey Optimizer]**.</p> |
   | **[!UICONTROL Tags]** | Specifica i tag da applicare al modello. Gli utenti possono filtrare l’elenco dei modelli in base ai tag aggiunti. |

1. Seleziona [!UICONTROL **Salva come modello**].

Per informazioni su come gli utenti possono creare un progetto basato su un modello, consulta [Creare un progetto basato su un modello](/help/analysis-workspace/templates/use-templates.md#create-a-project-based-on-a-template) in [Utilizzare i modelli](/help/analysis-workspace/templates/use-templates.md).

## Modificare o eliminare un modello

Gli amministratori possono modificare o eliminare i modelli aziendali.

1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**], quindi in **[!UICONTROL Templates]** nella barra a sinistra seleziona modelli **[!UICONTROL _login_company_name _]**.

1. Se visualizzi i modelli in una vista a colonne ![icona vista a colonne](assets/column-view-icon.png):

   1. Passa al modello da modificare o eliminare, seleziona l’icona delle informazioni accanto al nome del modello.

      ![Informazioni modello aziendale](assets/company-template-info.png)

   1. Seleziona **[!UICONTROL Preview]**.

   1. Seleziona l’icona Altro, quindi seleziona **[!UICONTROL Edit]** o **[!UICONTROL Delete]**.

      ![Modifica o elimina modello](assets/company-template-edit-delete.png)

1. Se visualizzi i modelli in una vista a schede ![icona di vista a schede](assets/card-view-icon.png):

   1. Individua il modello che desideri modificare o eliminare.

      ![Vista a schede dei modelli aziendali](assets/company-template-cards.png)

   1. Passa il puntatore sul modello, quindi seleziona **[!UICONTROL Preview]**.

   1. Seleziona l’icona Altro, quindi seleziona **[!UICONTROL Edit]** o **[!UICONTROL Delete]**.

      ![Modificare o eliminare scheda modello aziendale](assets/company-template-card-edit-delete.png)

1. Se stai modificando un modello, apporta le modifiche desiderate, quindi seleziona [!UICONTROL **Progetto**] > **[!UICONTROL Save as template…]**.

   ![Modello aziendale](assets/company-template-save.png)

1. Specifica le informazioni seguenti nella finestra di dialogo [!UICONTROL Save as template]:

   | Campo | Descrizione |
   |---------|----------|
   | **[!UICONTROL Name]** | Inserisci un nome descrittivo per il modello. |
   | **[!UICONTROL Description]** | Fornisci una breve descrizione del modello che ne indichi gli usi previsti. |
   | **[!UICONTROL Why use this template]** | Inserisci una breve spiegazione per indicare alle persone dell’organizzazione come potrebbe essere utilizzato questo modello. Questa spiegazione viene visualizzata nella pagina Anteprima del modello. |
   | **[!UICONTROL Channels]** | Scegli tutti i canali applicabili a questo modello. Puoi selezionare più canali: **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL Cross-channel]**, **[!UICONTROL Call center]** e **[!UICONTROL In-store]**. Se non è selezionato alcun canale, il modello viene incluso con tutti i canali.<p>Le selezioni effettuate determinano dove viene visualizzato il modello e quali sono i filtri applicabili per gli utenti che vi accedono dalla pagina Modelli aziendali.</p> |
   | **[!UICONTROL Use cases]** | Scegli eventuali casi d’uso applicabili a questo modello. Puoi selezionare più casi d’uso: **[!UICONTROL Engagement]**, **[!UICONTROL Conversion]**, **[!UICONTROL Audience]**, **[!UICONTROL Acquisition]** e **[!UICONTROL Journey Optimizer]**. <p>Le selezioni effettuate determinano la posizione del modello nella pagina Modelli organizzazione. Gli utenti possono passare al modello o filtrare l’elenco in base al caso d’uso. </p><p>**Nota:** quando selezioni l’opzione **[!UICONTROL Journey Optimizer]**, il modello è disponibile per l’utilizzo in Adobe Journey Optimizer. In Journey Optimizer, nella pagina **[!UICONTROL Reports]** è disponibile un menu a discesa che consente agli utenti di selezionare questo modello o quello predefinito. Per ulteriori informazioni, consulta [Introduzione alla esperienza di reporting aggiornata](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) nella documentazione di Journey Optimizer.</p><p>Quando selezioni l’opzione Journey Optimizer, tieni presente quanto segue:</p><ul><li>Questa opzione è disponibile solo se i dati di Journey Optimizer sono presenti nella visualizzazione dati utilizzata in Customer Journey Analytics.</li><li>Quando utilizzi questo modello in Journey Optimizer, viene utilizzata la visualizzazione dati impostata come predefinita in Adobe Journey Optimizer, indipendentemente dalla visualizzazione dati selezionata con questo modello in Customer Journey Analytics. <br/>Per ulteriori informazioni sull’impostazione di una visualizzazione dati come predefinita in Journey Optimizer, consulta [Compatibilità](/help/data-views/create-dataview.md#compatibility) in [Creare o modificare una visualizzazione di dati](/help/data-views/create-dataview.md).</li></ul> |
   | **[!UICONTROL Journey Optimizer activity type]** | Scegli il tipo di attività Journey Optimizer da associare al modello: **[!UICONTROL Campaigns]**, **[!UICONTROL Journeys]**, **[!UICONTROL Landing pages]**, **[!UICONTROL Reports]** o **[!UICONTROL Subscriptions]**. <p>Lascia vuoto questo campo se vuoi che questo modello sia associato a tutti i tipi di attività.</p><p>Questo campo viene visualizzato solo se nel campo **[!UICONTROL Use cases]** è selezionato **[!UICONTROL Journey Optimizer]**.</p> |
   | **[!UICONTROL Journey Optimizer activity]** | Scegli l’attività Journey Optimizer da associare a questo modello. <p>Lascia vuoto questo campo se vuoi che questo modello sia associato a tutte le attività del tipo di attività selezionato.</p><p>Questo campo viene visualizzato solo se nel campo **[!UICONTROL Use cases]** è selezionato **[!UICONTROL Journey Optimizer]**.</p> |
   | **[!UICONTROL Tags]** | Specifica i tag da applicare al modello. Gli utenti possono filtrare l’elenco dei modelli in base ai tag aggiunti. |

1. Seleziona [!UICONTROL **Salva come modello**].

## Rinominare, assegnare tag o approvare i modelli

Gli amministratori possono rinominare, assegnare tag e approvare i modelli aziendali.

1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**], quindi scegli la **[!UICONTROL Projects tab]** nella barra a sinistra.

1. Seleziona l’icona del filtro per filtrare l’elenco dei progetti.

1. Nella barra del filtro, seleziona **[!UICONTROL Other filters]**, quindi **[!UICONTROL Company templates]**.

   Viene visualizzato un elenco dei modelli aziendali. Tutti i progetti regolari non vengono visualizzati, a meno che non siano fissati.

   I modelli aziendali possono essere identificati dall’![icona modelli](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg) che precede il nome del modello.

   ![Visualizzare i filtri dei modelli aziendali](assets/company-templates-filter.png)

1. Fai clic sull’icona con i puntini di sospensione **...** accanto a un modello per visualizzare le opzioni disponibili.

   ![Azioni sui modelli aziendali](assets/company-templates-actions.png)

1. Seleziona **[!UICONTROL Rename]**, **[!UICONTROL Tag]**, or **[!UICONTROL Approve]**.

   Puoi inoltre eliminare un modello oppure eliminare un modello come descritto in [Modificare o eliminare i modelli](#edit-or-delete-templates).

1. (Facoltativo) Per tornare alla visualizzazione normale, nella barra dei filtri, deseleziona **[!UICONTROL Company templates]**.

## Aggiungere componenti mancanti alla visualizzazione dati per un determinato modello

Per impostazione predefinita, alcuni modelli forniti da Adobe non possono essere utilizzati perché contengono componenti non presenti nella visualizzazione dati.

Per ogni componente mancante, nella visualizzazione dati è disponibile un’etichetta di contesto corrispondente. Devi aggiungere l’etichetta di contesto corrispondente a un componente già presente nella visualizzazione dati oppure aggiungere un nuovo componente alla visualizzazione dati e aggiungervi l’etichetta di contesto.

Per aggiungere componenti mancanti a un modello:

1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**], quindi in **[!UICONTROL Templates]** nella barra a sinistra, seleziona **[!UICONTROL Adobe templates]**.

1. Seleziona l’icona del filtro per filtrare l’elenco dei modelli.

1. Seleziona **[!UICONTROL Not ready for use]** per visualizzare i modelli che richiedono componenti non presenti nella visualizzazione dati.

   ![Usa un modello al quale mancano componenti](assets/template-not-ready.png)

1. Individua un modello non ancora pronto per l’utilizzo con la visualizzazione dati.

1. Esegui una delle operazioni seguenti:

   * **Se visualizzi modelli in una vista a colonne** ![icona vista a colonne](assets/column-view-icon.png):

      1. Passa al modello che non è ancora pronto per l’uso con la visualizzazione dati, quindi seleziona l’icona info accanto al nome del modello.

         ![Informazioni modello aziendale](assets/company-template-info.png)

      1. Seleziona **[!UICONTROL Preview]**.

         ![Pagina anteprima modello](assets/template-preview.png)

   * **Se visualizzi modelli in una vista a schede** ![icona di vista a schede](assets/card-view-icon.png):

      1. Individua il modello non ancora pronto per l’utilizzo con la visualizzazione dati.

         ![Vista a schede modello aziendale](assets/company-template-cards.png)

      1. Passa il puntatore sul modello, quindi seleziona **[!UICONTROL Preview]**.

         ![Pagina anteprima modello](assets/template-preview.png)

1. Nella sezione **[!UICONTROL Missing components]** viene visualizzato un elenco di componenti mancanti nella visualizzazione dati. Seleziona **[!UICONTROL Add these components to your data view]**.

   La pagina di configurazione della visualizzazione dati viene mostrata in una nuova scheda.

1. Seleziona la scheda **[!UICONTROL Components]** per la visualizzazione dati.

   ![Scheda componenti della visualizzazione dati](assets/template-dataview.png)

1. Per ogni componente elencato come mancante nel modello, esegui una delle operazioni seguenti nella scheda **[!UICONTROL Components]**:

   * Nella sezione **[!UICONTROL Included components]** seleziona un componente già incluso nella visualizzazione dati che vuoi utilizzare per il componente mancante.

   * Aggiungi un nuovo componente alla visualizzazione dati che desideri utilizzare per il componente mancante, quindi seleziona il componente.

     Per aggiungere un nuovo componente alla visualizzazione dati, cerca l’elenco dei campi schema, quindi trascinalo nella sezione **[!UICONTROL Included components]**.

1. Con il componente selezionato, individua il menu a discesa **[!UICONTROL Context labels]** nella colonna a destra.

   ![Scheda componenti della visualizzazione dati](assets/template-dataview-context-label.png)

1. Nel menu a discesa **[!UICONTROL Context labels]**, seleziona l’etichetta di contesto con lo stesso nome del componente mancante.

1. Seleziona **[!UICONTROL Save and continue]**.

1. Per ogni componente mancante, ripeti il processo di aggiunta dell’etichetta di contesto corrispondente a un componente nella visualizzazione dati.


## Accedere a un modello aziendale

Come per i modelli forniti da Adobe, gli utenti dell’organizzazione possono accedere ai modelli creati dagli amministratori.

Per informazioni su come accedere a un modello aziendale, consulta [Accedere ed eseguire un modello](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) in [Utilizzare i modelli](/help/analysis-workspace/templates/use-templates.md).

## Nascondere la scheda Modelli

Gli amministratori possono nascondere la scheda Modelli per tutti gli utenti all’interno della propria organizzazione.

1. Passa a **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Preferences]** > **[!UICONTROL Company]**.
1. Seleziona l’opzione per **[!UICONTROL Hide Templates tab]**.
