---
description: Panoramica sull’utilizzo dei modelli predefiniti in Analysis Workspace.
title: Utilizzare i modelli
feature: Workspace Basics
role: User, Admin
hide: true
hidefromtoc: true
exl-id: 23cdf02f-56a1-4465-ae7f-b3a1bcad28af
source-git-commit: 27ce8f565688dc23a3f069a10078de55cd6da395
workflow-type: tm+mt
source-wordcount: '1427'
ht-degree: 2%

---

# Creare e gestire i modelli

Gli amministratori possono creare modelli e salvarli per l’utilizzo da parte di altri nella società di accesso.

Gli utenti della società di accesso possono utilizzare questi modelli aziendali come descritto in [Utilizzare i modelli](/help/analysis-workspace/templates/use-templates.md).

## Creare un modello

Per creare un nuovo modello utilizzabile dalle persone della società di accesso:

1. In Analysis Workspace, crea un progetto con lo stato desiderato.

1. Seleziona [!UICONTROL **Progetto**] > **[!UICONTROL Save as template…]**.

   ![Modello aziendale](assets/company-template-save.png)

1. Specificare le informazioni seguenti nella finestra di dialogo [!UICONTROL Save as template]:

   | Campo | Descrizione |
   |---------|----------|
   | **[!UICONTROL Name]** | Fornisci un nome descrittivo per il modello. |
   | **[!UICONTROL Description]** | Fornire una breve descrizione del modello che ne descriva gli usi previsti. |
   | **[!UICONTROL Why use this template]** | Fornisci una breve spiegazione per informare le persone dell’organizzazione su come potrebbe essere utilizzato questo modello. Questa spiegazione viene visualizzata nella pagina Anteprima del modello. |
   | **[!UICONTROL Channels]** | Scegli tutti i canali applicabili a questo modello. È possibile selezionare più canali: **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL Cross-channel]**, **[!UICONTROL Call center]** e **[!UICONTROL In-store]**.<p>Le selezioni selezionate determinano la posizione di visualizzazione del modello e i filtri applicabili agli utenti che vi accedono dalla pagina Modelli organizzazione.</p> |
   | **[!UICONTROL Use cases]** | Scegli eventuali casi d’uso applicabili a questo modello. È possibile selezionare più casi d&#39;uso: **[!UICONTROL Engagement]**, **[!UICONTROL Conversion]**, **[!UICONTROL Audience]**, **[!UICONTROL Acquisition]** e **[!UICONTROL Journey Optimizer]**. <p>Le selezioni selezionate determinano la posizione del modello nella pagina Modelli organizzazione. Gli utenti possono passare al modello o filtrare l’elenco in base al caso d’uso. </p><p>**Nota:** la scelta di **[!UICONTROL Journey Optimizer]** rende il modello disponibile anche in Adobe Journey Optimizer. In Journey Optimizer, nella pagina **[!UICONTROL Reports]** è disponibile un menu a discesa che consente agli utenti di selezionare questo modello o quello predefinito. Per ulteriori informazioni, consulta [Introduzione all&#39;esperienza di reporting aggiornata](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) nella documentazione di Journey Optimizer. |
   | **[!UICONTROL Journey Optimizer activity type]** | Scegliere il tipo di attività Journey Optimizer da associare al modello: **[!UICONTROL Campaigns]**, **[!UICONTROL Journeys]**, **[!UICONTROL Landing pages]**, **[!UICONTROL Reports]** o **[!UICONTROL Subscriptions]**. <p>Lascia vuoto questo campo se vuoi che questo modello sia associato a tutti i tipi di attività.</p><p>Questo campo viene visualizzato solo se nel campo **[!UICONTROL Use cases]** è selezionato **[!UICONTROL Journey Optimizer]**.</p> |
   | **[!UICONTROL Journey Optimizer activity]** | Scegli l’attività Journey Optimizer da associare a questo modello. <p>Lascia vuoto questo campo se vuoi che questo modello sia associato a tutte le attività del tipo di attività selezionato.</p><p>Questo campo viene visualizzato solo se nel campo **[!UICONTROL Use cases]** è selezionato **[!UICONTROL Journey Optimizer]**.</p> |
   | **[!UICONTROL Tags]** | Specifica i tag da applicare al modello. Gli utenti possono filtrare l’elenco dei modelli in base ai tag aggiunti. |

1. Seleziona [!UICONTROL **Salva come modello**].

Per informazioni su come gli utenti possono creare un progetto basato su un modello, vedere [Creare un progetto basato su un modello](/help/analysis-workspace/templates/use-templates.md#create-a-project-based-on-a-template) in [Utilizzare i modelli](/help/analysis-workspace/templates/use-templates.md).

## Modificare o eliminare un modello

Gli amministratori possono modificare o eliminare i modelli aziendali.

1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**], quindi in **[!UICONTROL Templates]** nella barra a sinistra seleziona **[!UICONTROL _login_company_name _modelli]**.

1. Se visualizzi i modelli in una vista a colonne ![icona vista a colonne](assets/column-view-icon.png):

   1. Vai al modello da modificare o eliminare, seleziona l’icona delle informazioni accanto al nome del modello.

      ![Informazioni modello società](assets/company-template-info.png)

   1. Seleziona **[!UICONTROL Preview]**.

   1. Selezionare l&#39;icona Altro, quindi selezionare **[!UICONTROL Edit]** o **[!UICONTROL Delete]**.

      ![Modifica o elimina modello](assets/company-template-edit-delete.png)

1. Se visualizzi i modelli in una vista a schede ![icona di vista a schede](assets/card-view-icon.png):

   1. Individuare il modello che si desidera modificare o eliminare.

      ![Visualizzazione scheda modello società](assets/company-template-cards.png)

   1. Passa il puntatore del mouse sul modello, quindi seleziona **[!UICONTROL Preview]**.

   1. Selezionare l&#39;icona Altro, quindi selezionare **[!UICONTROL Edit]** o **[!UICONTROL Delete]**.

      ![Modifica o eliminazione scheda modello aziendale](assets/company-template-card-edit-delete.png)

1. Se stai modificando un modello, apporta le modifiche desiderate, quindi seleziona [!UICONTROL **Progetto**] > **[!UICONTROL Save as template…]**.

   ![Modello aziendale](assets/company-template-save.png)

1. Specificare le informazioni seguenti nella finestra di dialogo [!UICONTROL Save as template]:

   | Campo | Descrizione |
   |---------|----------|
   | **[!UICONTROL Name]** | Fornisci un nome descrittivo per il modello. |
   | **[!UICONTROL Description]** | Fornire una breve descrizione del modello che ne descriva gli usi previsti. |
   | **[!UICONTROL Why use this template]** | Fornisci una breve spiegazione per informare le persone dell’organizzazione su come potrebbe essere utilizzato questo modello. Questa spiegazione viene visualizzata nella pagina Anteprima del modello. |
   | **[!UICONTROL Channels]** | Scegli tutti i canali applicabili a questo modello. È possibile selezionare più canali: **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL Cross-channel]**, **[!UICONTROL Call center]** e **[!UICONTROL In-store]**. Se non è selezionato alcun canale, il modello verrà incluso con tutti i canali.<p>Le selezioni selezionate determinano la posizione di visualizzazione del modello e i filtri applicabili agli utenti che vi accedono dalla pagina Modelli organizzazione.</p> |
   | **[!UICONTROL Use cases]** | Scegli eventuali casi d’uso applicabili a questo modello. È possibile selezionare più casi d&#39;uso: **[!UICONTROL Engagement]**, **[!UICONTROL Conversion]**, **[!UICONTROL Audience]**, **[!UICONTROL Acquisition]** e **[!UICONTROL Journey Optimizer]**. <p>Le selezioni selezionate determinano la posizione del modello nella pagina Modelli organizzazione. Gli utenti possono passare al modello o filtrare l’elenco in base al caso d’uso. </p><p>**Nota:** la scelta di **[!UICONTROL Journey Optimizer]** rende il modello disponibile anche in Adobe Journey Optimizer. In Journey Optimizer, nella pagina **[!UICONTROL Reports]** è disponibile un menu a discesa che consente agli utenti di selezionare questo modello o quello predefinito. Per ulteriori informazioni, consulta [Introduzione all&#39;esperienza di reporting aggiornata](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) nella documentazione di Journey Optimizer. |
   | **[!UICONTROL Journey Optimizer activity type]** | Scegliere il tipo di attività Journey Optimizer da associare al modello: **[!UICONTROL Campaigns]**, **[!UICONTROL Journeys]**, **[!UICONTROL Landing pages]**, **[!UICONTROL Reports]** o **[!UICONTROL Subscriptions]**. <p>Lascia vuoto questo campo se vuoi che questo modello sia associato a tutti i tipi di attività.</p><p>Questo campo viene visualizzato solo se nel campo **[!UICONTROL Use cases]** è selezionato **[!UICONTROL Journey Optimizer]**.</p> |
   | **[!UICONTROL Journey Optimizer activity]** | Scegli l’attività Journey Optimizer da associare a questo modello. <p>Lascia vuoto questo campo se vuoi che questo modello sia associato a tutte le attività del tipo di attività selezionato.</p><p>Questo campo viene visualizzato solo se nel campo **[!UICONTROL Use cases]** è selezionato **[!UICONTROL Journey Optimizer]**.</p> |
   | **[!UICONTROL Tags]** | Specifica i tag da applicare al modello. Gli utenti possono filtrare l’elenco dei modelli in base ai tag aggiunti. |

1. Seleziona [!UICONTROL **Salva come modello**].

## Rinominare, assegnare tag o approvare i modelli

Gli amministratori possono rinominare, assegnare tag e approvare i modelli aziendali.

1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**], quindi seleziona **[!UICONTROL Projects tab]** nella barra a sinistra.

1. Seleziona l’icona del filtro per filtrare l’elenco dei progetti.

1. Nella barra dei filtri, seleziona **ALTRI FILTRI**, quindi seleziona **Modelli società**.

   Viene visualizzato un elenco dei modelli aziendali. Tutti i progetti regolari non vengono visualizzati, a meno che non siano fissati.

   I modelli aziendali possono essere identificati dall&#39;icona ![modelli](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg) che precede il nome del modello.

   ![Visualizza filtri modelli società](assets/company-templates-filter.png)

1. Fare clic sull&#39;icona con i puntini di sospensione **...** accanto a un modello per visualizzare le opzioni disponibili.

   ![Azioni modello società](assets/company-templates-actions.png)

1. Seleziona **[!UICONTROL Rename]**, **[!UICONTROL Tag]**, or **[!UICONTROL Approve]**.

   È inoltre possibile eliminare un modello oppure eliminare un modello come descritto in [Modifica o elimina modelli](#edit-or-delete-templates).

1. (Facoltativo) Per tornare alla visualizzazione normale, nella barra dei filtri, deselezionare **[!UICONTROL Company templates]**.

## Aggiungere componenti mancanti alla visualizzazione dati per un determinato modello

Per impostazione predefinita, alcuni modelli forniti da Adobe non funzionano perché contengono componenti non presenti nella visualizzazione dati.

Per ogni componente mancante, nella visualizzazione dati è disponibile un’etichetta di contesto corrispondente. È necessario aggiungere l’etichetta di contesto corrispondente a un componente già presente nella visualizzazione dati, oppure è necessario aggiungere un nuovo componente alla visualizzazione dati e aggiungervi l’etichetta di contesto.

Per aggiungere componenti mancanti a un modello:

1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**], quindi in **[!UICONTROL Templates]** nella barra a sinistra, seleziona **[!UICONTROL Adobe templates]**.

1. Seleziona l’icona del filtro per filtrare l’elenco dei modelli.

1. Selezionare **[!UICONTROL Not ready for use]** per visualizzare i modelli che richiedono componenti non presenti nella visualizzazione dati.

   ![Usa un modello senza componenti](assets/template-not-ready.png)

1. Individua un modello non ancora pronto per l’utilizzo con la visualizzazione dati.

1. Effettuare una delle seguenti operazioni:

   * **Se visualizzi modelli in una vista a colonne** ![icona vista a colonne](assets/column-view-icon.png):

      1. Vai al modello che non è ancora pronto per l’uso con la visualizzazione dati, quindi seleziona l’icona info accanto al nome del modello.

         ![Informazioni modello società](assets/company-template-info.png)

      1. Seleziona **[!UICONTROL Preview]**.

         ![Pagina anteprima modello](assets/template-preview.png)

   * **Se visualizzi modelli in una visualizzazione a schede** ![icona di visualizzazione a schede](assets/card-view-icon.png):

      1. Individua il modello non ancora pronto per l’utilizzo con la visualizzazione dati.

         ![Visualizzazione scheda modello società](assets/company-template-cards.png)

      1. Passa il puntatore del mouse sul modello, quindi seleziona **[!UICONTROL Preview]**.

         ![Pagina anteprima modello](assets/template-preview.png)

1. Nella sezione **[!UICONTROL Missing components]** viene visualizzato un elenco di componenti mancanti nella visualizzazione dati. Seleziona **[!UICONTROL Add these components to your data view]**.

   La pagina di configurazione per la visualizzazione dati viene visualizzata in una nuova scheda.

1. Selezionare la scheda **[!UICONTROL Components]** per la visualizzazione dati.

   ![Scheda dei componenti della visualizzazione dati](assets/template-dataview.png)

1. Per ogni componente elencato come mancante nel modello, eseguire una delle operazioni seguenti nella scheda **[!UICONTROL Components]**:

   * Nella sezione **[!UICONTROL Included components]** selezionare un componente già incluso nella visualizzazione dati che si desidera utilizzare per il componente mancante.

   * Aggiungi un nuovo componente alla visualizzazione dati che desideri utilizzare per il componente mancante, quindi seleziona il componente.

     Per aggiungere un nuovo componente alla visualizzazione dati, cercare nell&#39;elenco dei campi dello schema, quindi trascinarlo nella sezione **[!UICONTROL Included components]**.

1. Con il componente selezionato, individuare il menu a discesa **[!UICONTROL Context labels]** nella colonna di destra.

   ![Scheda dei componenti della visualizzazione dati](assets/template-dataview-context-label.png)

1. Nel menu a discesa **[!UICONTROL Context labels]**, selezionare l&#39;etichetta di contesto con lo stesso nome del componente mancante.

1. Seleziona **[!UICONTROL Save and continue]**.

1. Per ogni componente mancante, ripeti il processo di aggiunta dell’etichetta di contesto corrispondente a un componente nella visualizzazione dati.


## Accedere a un modello aziendale

Come per i modelli forniti da Adobe, gli utenti dell’organizzazione possono accedere ai modelli creati dagli amministratori.

Per informazioni su come accedere a un modello aziendale, vedere [Accedere ed eseguire un modello](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) in [Utilizzare i modelli](/help/analysis-workspace/templates/use-templates.md).
