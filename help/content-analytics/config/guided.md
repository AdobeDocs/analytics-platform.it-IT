---
title: Configurazione guidata di Content Analytics
description: Come configurare Content Analytics utilizzando una configurazione guidata dell’onboarding
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: ht
source-wordcount: '2572'
ht-degree: 100%

---

# Configurazione guidata di Content Analytics

La configurazione guidata ti aiuta a configurare Content Analytics in modo rapido e semplice. La configurazione guidata utilizza una procedura guidata per impostare i requisiti necessari per configurare automaticamente Content Analytics per la tua organizzazione. Nella schermata **[!UICONTROL Configuration]** puoi creare una nuova configurazione o modificare una configurazione esistente.

>[!IMPORTANT]
>
>Nella tua organizzazione puoi avere una sola configurazione di Content Analytics per sandbox.

Per accedere alla configurazione di Content Analytics

* Seleziona **[!UICONTROL Data Management]** > **[!UICONTROL Content Analytics Configuration]** dal menu principale in Customer Journey Analytics.

Nella schermata **[!UICONTROL Content Analytics Configurations]** viene visualizzata una tabella delle configurazioni di Content Analytics esistenti.

![ContentAnalytics configurations](../assets/aca-configuration-table.png)
Per ogni configurazione, sono disponibili i seguenti dettagli:

| Colonna | Descrizione |
|---|---|
| **[!UICONTROL Name]** | Il nome della configurazione. |
| **[!UICONTROL Created by]** | L’account tecnico che ha creato la configurazione. |
| **[!UICONTROL Created on]** | La marca temporale in cui è stata creata la configurazione. |
| **[!UICONTROL Modified on]** | La marca temporale dell’ultima modifica apportata alla configurazione. |
| **[!UICONTROL Sandbox]** | La sandbox all’interno dell’organizzazione in cui Content Analytics è (dovrà essere) configurato e implementato. |
| **[!UICONTROL Status]** | Lo stato della configurazione. Lo stato può essere:<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Draft]**: configurazione salvata per un momento successivo e non implementata.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Failed]**: configurazione non riuscita. Seleziona **[!UICONTROL Edit]** per ottenere informazioni sull’errore. Adobe tratta in modo proattivo qualsiasi implementazione non riuscita. Puoi contattare l’Assistenza clienti per i dettagli.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**: configurazione completata e implementata correttamente. |

Puoi utilizzare ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per personalizzare la tabella. Seleziona le colonne da visualizzare nella finestra di dialogo **[!UICONTROL Customize table]** e seleziona **[!UICONTROL Apply]** per applicare le modifiche.

Dalla schermata **[!UICONTROL Configuration]** di Content Analytics puoi creare una nuova configurazione o modificare una configurazione esistente.

Per creare una nuova configurazione:

* Seleziona **[!UICONTROL Create configuration]**. Viene aperta la [configurazione guidata](#guided-configuration-wizard).

Per modificare una configurazione esistente:

* Seleziona ![More](/help/assets/icons/More.svg) e quindi ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** per una configurazione di Content Analytics esistente. Viene aperta la [configurazione guidata](#guided-configuration-wizard).

## Configurazione guidata

La configurazione guidata è costituita da quattro sezioni ([Dettagli](#details), [Visualizzazione dati](#data-view), [Acquisizione e definizione esperienza](#experience-capture-and-definition) e [Raccolta dati](#data-collection)), in ognuna delle quali dovrai inserire i dettagli necessari per la corretta configurazione di Content Analytics. Completa ogni sezione prima di passare a quella successiva, in quanto alcune impostazioni in una sezione potrebbero dipendere dai valori di configurazione delle sezioni precedenti.

### Dettagli {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Dettagli"
>abstract="Fornisci un nome per la connessione. Nelle sezioni **[!UICONTROL Data view]**, **[!UICONTROL Experience capture and definition]** e **[!UICONTROL Data collection]** vengono forniti ulteriori dettagli per garantire che Content Analytics possa essere configurato correttamente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Dettagli"
>abstract="Questa guida definisce i requisiti necessari per configurare Content Analytics. Specifica un nome per questa configurazione"

<!-- markdownlint-enable MD034 -->

Ogni configurazione richiede un nome univoco. Ad esempio, `Example Content Analytics configuration`. Il nome è necessario per salvare o implementare una configurazione.

![Dettagli di configurazione di Content Analytics](../assets/aca-configuration-details.png)


### Visualizzazione dati {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Visualizzazione dati"
>abstract="Per la configurazione di Content Analytics è necessario selezionare una visualizzazione dati esistente. In questo modo, puoi unire i dati di Content Analytics con altri dati."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Visualizzazione dati"
>abstract="Seleziona una visualizzazione dati esistente di Customer Journey Analytics con cui desideri unire i dati di Content Analytics."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Visualizzazione dati"
>abstract="Seleziona una visualizzazione dati esistente da Customer Journey Analytics con cui vuoi unire i dati di Content Analytics.<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="Nuova visualizzazione dati"
>abstract="Hai selezionato una nuova visualizzazione dati per questa configurazione. La nuova visualizzazione dati verrà aggiornata per includere le metriche e le dimensioni di Content Analytics. Queste metriche e dimensioni verranno rimosse dalla visualizzazione dati selezionata originariamente.<br/><br/>Se alla nuova visualizzazione dati è associata una connessione diversa, la connessione verrà aggiornata per includere i set di dati di Content Analytics. I set di dati di Content Analytics non vengono rimossi dalla connessione selezionata originariamente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="Pulizia della visualizzazione dati selezionata"
>abstract="Hai selezionato una visualizzazione dati per la quale è già stato eseguito il provisioning per Content Analytics. La configurazione di Content Analytics esistente viene rimossa e il provisioning della visualizzazione dati viene eseguito con la nuova configurazione."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Pulizia della visualizzazione dati precedente"
>abstract="Hai selezionato una nuova visualizzazione dati. La configurazione di Content Analytics per la visualizzazione dati selezionata in precedenza viene rimossa."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_new_dialog"
>title="Nuova visualizzazione dati"
>abstract="Hai selezionato una nuova visualizzazione dati per questa configurazione. La nuova visualizzazione dati verrà aggiornata per includere le metriche e le dimensioni di Content Analytics. Metriche e dimensioni simili verranno rimosse dalla visualizzazione dati esistente.<br/>Se alla nuova visualizzazione dati è associata una connessione diversa, la connessione verrà aggiornata per includere i set di dati di Content Analytics. I set di dati di Content Analytics non vengono rimossi dalla configurazione esistente."

<!-- markdownlint-enable MD034 -->

La configurazione richiede la selezione di una [Visualizzazione dati](/help/data-views/data-views.md).

1. Selezionare una visualizzazione dati

   * Per selezionare una nuova visualizzazione dati per una configurazione, utilizza ![Dati](/help/assets/icons/Data.svg) **[!UICONTROL Select Data view]**.

     ![Configurazione di Content Analytics di una visualizzazione dati](../assets/aca-configuration-dataview.png)

   * Per modificare una visualizzazione dati per una configurazione, seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**.

     ![Configurazione di Content Analytics di una visualizzazione dati](../assets/aca-configuration-dataview-edit.png)


   In entrambi gli scenari, viene visualizzata una finestra di dialogo **[!UICONTROL Data view]** in cui è possibile selezionare una visualizzazione dati per la configurazione.

   ![Configurazione di Content Analytics di una visualizzazione dati - tabella delle visualizzazioni dati](../assets/aca-configuration-dataview-dialog.png)

   Per una nuova configurazione, l’elenco mostra solo le visualizzazioni dati associate alle sandbox che non hanno una configurazione attiva. Inoltre, puoi visualizzare solo le visualizzazioni dati associate alle sandbox a cui hai accesso e le connessioni per le quali disponi dei diritti di modifica.

   Se modifichi una configurazione esistente, l’elenco mostra solo le visualizzazioni dati disponibili nella sandbox già associate alla configurazione esistente.

   Puoi eseguire le seguenti azioni:

   * Per cercare una visualizzazione dati specifica, utilizza il campo ![Ricerca](/help/assets/icons/Search.svg).
   * Per filtrare l’elenco delle visualizzazioni dati disponibili, seleziona ![Mostra filtri](/help/assets/icons/Filter.svg). È possibile filtrare l’elenco per [!UICONTROL Connection], [!UICONTROL Owner] e [!UICONTROL Sandbox].<br/>Utilizza ![Nascondi](/help/assets/icons/Filter.svg) **[!UICONTROL Hide segments]** per nascondere il riquadro dei segmenti.
   * Per definire le colonne da visualizzare nella tabella, seleziona ![Impostazioni colonna](/help/assets/icons/ColumnSetting.svg). Seleziona le colonne da visualizzare nella finestra di dialogo **[!UICONTROL Customize table]** e seleziona **[!UICONTROL Apply]** per applicare le modifiche.

1. Seleziona ![SelectBox](/help/assets/icons/SelectBox.svg) la visualizzazione dati che desideri utilizzare.
1. Seleziona **[!UICONTROL Save]** per confermare la visualizzazione dati selezionata. Seleziona **[!UICONTROL Cancel]** per annullare.


In Customer Journey Analytics, una [visualizzazione dati](/help/data-views/data-views.md) è associata a una [connessione](/help/connections/overview.md) di Customer Journey Analytics. Inoltre, una connessione è basata su una sandbox all’interno della tua organizzazione. Una volta salvata la configurazione, il campo **[!UICONTROL Sandbox]** viene automaticamente compilato con il nome della sandbox, in base alla visualizzazione dati selezionata.


### Acquisizione e definizione dell’esperienza {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Acquisizione e definizione dell’esperienza"
>abstract="Puoi selezionare e includere esperienze nei dati raccolti con Content Analytics. Quando questa opzione è selezionata, devi definire una o più combinazioni di un regex e parametri di query per definire gli URL per i quali desideri includere le esperienze."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Acquisizione e definizione dell’esperienza"
>abstract="Raccogli esperienze in Content Analytics"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="Acquisizione e definizione dell’esperienza"
>abstract="Specifica i parametri che determinano come il contenuto viene riprodotto sul tuo sito web."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_new_include_experiences"
>title="Acquisizione e definizione dell’esperienza"
>abstract="Quando questa opzione è abilitata, vengono raccolti i dati sull’esperienza, vengono generati gli attributi dell’esperienza e sono disponibili i rapporti sull’esperienza."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_include_experiences"
>title="Acquisizione e definizione dell’esperienza"
>abstract="Quando questa opzione è abilitata, vengono raccolti i dati sull’esperienza, vengono generati gli attributi dell’esperienza e sono disponibili i rapporti sull’esperienza. <br><br/>Utilizza ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** per modificare la configurazione della raccolta dati per le esperienze nella proprietà Tag associata alla configurazione corrente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Acquisizione e definizione dell’esperienza"
>abstract="È necessario modificare le impostazioni per la raccolta dati sull’esperienza nell’estensione Adobe Content Analytics."

<!-- markdownlint-enable MD034 -->

In questa sezione, puoi scegliere di includere le esperienze nei dati raccolti con Content Analytics.  Un’esperienza è tutto il testo di una pagina web riproducibile con l’URL utilizzato dall’utente che visita inizialmente quella pagina web.

Per impostazione predefinita, **[!UICONTROL Include experiences]** è disattivata. Quando viene selezionata, devi definire gli URL per i quali includere le esperienze.

È consigliabile includere le esperienze solo quando è possibile applicare quanto segue:

* Le pagine del sito devono essere riproducibili utilizzando l’URL della pagina.
* Il contenuto di testo visualizzato da un determinato utente può essere riprodotto utilizzando l’URL della pagina e non dipende da cookie o altri meccanismi di personalizzazione.

>[!IMPORTANT]
>
>Implementa il [controllo delle versioni di Content Analytics](manual.md#versioning) per raccogliere le modifiche apportate alle esperienze (pagine) soggette a Content Analytics.



#### Nuova configurazione {#new-experiences-configuration}

Per includere le esperienze in una configurazione nuova o non implementata:

![Acquisizione e definizione dell’esperienza nella configurazione di Content Analytics](../assets/aca-configuration-experience.png)

1. Abilita **[!UICONTROL Include experiences]**. Il pulsante di attivazione per abilitare le esperienze influisce su quanto segue:

   * Raccolta di dati nell’estensione Content Analytics
   * Processo che genera attributi esperienza dai dati evento di Content Analytics
   * Modello di reporting in Customer Journey Analytics.

1. Specifica i parametri che determinano come il contenuto viene riprodotto sul tuo sito web. I parametri sono zero o più combinazioni di **[!UICONTROL Domain regular expression]** e **[!UICONTROL Query parameters]**. I parametri di query indicano quali parametri influiscono sul contenuto della pagina. Questo input consente a Content Analytics di ignorare eventuali parametri che non influiscono sul contenuto della pagina durante la definizione di un’esperienza univoca.
   1. Immetti un’**[!UICONTROL Domain regular expression]**, ad esempio `/^(?!.*\b(store|help|admin)\b)/`. Assicurati di eseguire l’escape delle espressioni regolari, utilizzando `/`. L’espressione regolare del dominio indica a quali URL vengono applicati questi parametri. Ad esempio, se hai più siti, per ogni sito il contenuto può essere determinato da parametri diversi. Se i parametri di query vengono applicati a tutte le pagine, puoi utilizzare `.*` per indicare tutte le pagine.
   1. Specifica un elenco separato da virgole di **[!UICONTROL Query parameters,]**, ad esempio `outdoors, patio, kitchen`.
1. Seleziona **[!UICONTROL Remove]** se desideri rimuovere una combinazione di espressioni regolari di dominio e parametri di query.
1. Seleziona **[!UICONTROL Add Regex]** se desideri aggiungere un’altra combinazione di espressione regolare e parametri di query.


#### Configurazione implementata {#implemented-experiences-configuration}

Per modificare esperienze esistenti o includerne di nuove in una configurazione implementata:

![Acquisizione e definizione dell’esperienza nella configurazione di Content Analytics](../assets/aca-configuration-experience-edit.png)

* Attiva o disattiva **[!UICONTROL Include experiences]** per abilitare o disabilitare quanto segue:

   * Processo che genera attributi esperienza dai dati evento di Content Analytics
   * Modello di reporting in Customer Journey Analytics.

* Seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** per modificare ulteriormente la configurazione della raccolta dati per le esperienze in Content Analytics. Viene effettuato il reindirizzamento all’[estensione Adobe Content Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) nella proprietà Tag associata alla configurazione corrente.


### Raccolta dati {#onboarding-data-collection}

In questa sezione, puoi configurare il modo in cui raccogliere i dati di Content Analytics.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Raccolta dati"
>abstract="Definisci la proprietà dei tag da utilizzare o creane una nuova. Definisci inoltre le pagine e le risorse da includere o escludere utilizzando espressioni regolari."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Raccolta dati"
>abstract="**Specifica una proprietà dei tag**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="Raccolta dati"
>abstract="**Pagine da includere/escludere**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="Raccolta dati"
>abstract="Indica quali pagine devono essere **incluse** o **escluse** durante la raccolta dei dati per Content Analytics"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="Raccolta dati"
>abstract="**Risorse da includere/escludere**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="Raccolta dati"
>abstract="Indica quali risorse devono essere **incluse** o **escluse** durante la raccolta dei dati per Content Analytics"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="Raccolta dati"
>abstract="Puoi modificare le impostazioni per le pagine nell’estensione Adobe Content Analytics nella proprietà dei tag che è associata alla configurazione corrente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Raccolta dati"
>abstract="Puoi modificare le impostazioni per le risorse nell’estensione Adobe Content Analytics nella proprietà dei tag che è associata alla configurazione corrente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tags_disabled_description "
>title="Proprietà dei tag disabilitata"
>abstract="L’estensione Content Analytics è già attiva."

<!-- markdownlint-enable MD034 -->

#### Nuova configurazione {#new-configuration}

In una nuova configurazione, è necessario definire se desideri utilizzare una proprietà dei tag esistente o crearne una nuova. Inoltre, è necessario definire le pagine e le risorse da includere o escludere utilizzando espressioni regolari.

* Per utilizzare una proprietà dei tag esistente:

  ![Tag esistente nella raccolta dati di analisi dei contenuti](../assets/aca-configuration-datacollection-existingtag.png)

   1. Seleziona **[!UICONTROL Choose existing]**.
   2. Seleziona una proprietà esistente dal menu a discesa **[!UICONTROL Tags property]**. Puoi iniziare a digitare per cercare e limitare le opzioni disponibili. Non puoi selezionare una proprietà dei tag già utilizzata da un’altra configurazione di Content Analytics implementata.


* Per creare una nuova proprietà dei tag:

  ![Nuovo Tag per la raccolta dati di analisi dei contenuti](../assets/aca-configuration-datacollection-newtag.png)

   1. Seleziona **[!UICONTROL Create new]**.
   1. Specifica un **[!UICONTROL Tags name]**, ad esempio `ACA Test for Documentation`.
   1. Specifica un **[!UICONTROL Domains]**, ad esempio `example.com`.

* Indica quali pagine devono essere incluse o escluse durante la raccolta dei dati per Content Analytics.

  Specifica una stringa di espressione regolare per **[!UICONTROL Pages to include / exclude]**. <br/>Ad esempio: `^(?!.*documentation).*` per escludere tutte le pagine della documentazione da Content Analytics.

* Indica quali risorse devono essere incluse o escluse durante la raccolta dati per Content Analytics.

  Specifica una stringa di espressione regolare per **[!UICONTROL Assets to include / exclude]**. <br/>Ad esempio: `^(?!.*(logo\.jpg)).*$` per escludere tutte le immagini JPEG con logo da Content Analytics.

>[!IMPORTANT]
>
>Rimuovi manualmente l’estensione automatica inclusa di Web SDK dalla proprietà dei tag appena creata nel caso in cui sia presente un’implementazione di Web SDK esistente che utilizza la [libreria JavaScript](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/install/library) anziché l’[estensione di tag](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration).
>



#### Configurazione esistente {#existing-configuration}

In una configurazione esistente non puoi modificare la proprietà dei tag. Per gli aggiornamenti a una proprietà Tag associata a una configurazione esistente, utilizza la [configurazione dell’estensione tag di Content Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview).

Tuttavia, puoi modificare le pagine e le risorse da includere o escludere.

* Per modificare le pagine da includere o escludere durante la raccolta dati per Content Analytics, seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** sotto **[!UICONTROL Experience]**. Verrà effettuato il reindirizzamento all’[estensione Adobe Content Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) associata alla proprietà dei tag per la configurazione corrente di Content Analytics. Puoi modificare l’espressione regolare per includere o escludere le pagine. Assicurati di [pubblicare](#publish) le modifiche.

* Per modificare le risorse da includere o escludere durante la raccolta dati per Content Analytics, seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** sotto **[!UICONTROL Asset]**. Verrà effettuato il reindirizzamento all’[estensione Adobe Content Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) associata alla proprietà dei tag per la configurazione corrente di Content Analytics. Puoi modificare l’espressione regolare per includere o escludere le risorse. Assicurati di [pubblicare](#publish) le modifiche.

### Riepilogo {#summary}

Dopo aver fornito tutti i dettagli necessari, un riepilogo raccoglie i dettagli sugli artefatti creati o modificati.

* Quando implementi una nuova configurazione, visualizzi un **[!UICONTROL You're almost ready to implement _nome configurazione _per il riepilogo di analisi dei contenuti]**.

* Per le configurazioni implementate esistenti, visualizzi un **[!UICONTROL You have implemented _nome configurazione _per il riepilogo di analisi dei contenuti]**.

![Riepilogo configurazione analisi dei contenuti](../assets/aca-configuration-summary.png)

### Azioni {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Conferma dell’implementazione"
>abstract="Se si seleziona **[!UICONTROL Implement]**, l’analisi dei contenuti verrà configurata in base all’input fornito in questo flusso di lavoro. Per impostazione predefinita, vengono scelte diverse impostazioni in base a ciò che è generalmente utile per Content Analytics, ma (in qualità di titolare del trattamento dei dati) devi rivedere le impostazioni di ciascun artefatto per confermare che le impostazioni siano implementate in conformità all’informativa sulla privacy, ai diritti e agli obblighi contrattuali e ai requisiti di consenso secondo la legge applicabile.<br/><br/>Nessun dato verrà raccolto finché la libreria Tag associata a questa configurazione non verrà pubblicata manualmente.<br/><br/>Per derivare gli attributi di immagini e testo, Adobe recupera gli attributi utilizzando:<ol><li>l’URL della pagina acquisito al momento della visita del sito da parte degli utenti, in base alle impostazioni di raccolta dati configurate, e</li><li>l’URL in cui è ospitata l’immagine.</li></ol>Non devi assegnare tag alle immagini ospitate su siti di terze parti."

<!-- markdownlint-enable MD034 -->

Quando crei o modifichi una configurazione, disponi delle seguenti opzioni:

* **[!UICONTROL Discard]**: tutte le modifiche apportate durante la configurazione vengono eliminate.
* **[!UICONTROL Save for later]**: le modifiche apportate a una configurazione vengono salvate. Puoi rivedere la configurazione in un secondo momento per apportare ulteriori modifiche o implementarla. Per salvare una configurazione è necessario solo un valore per [!UICONTROL Name].
* **[!UICONTROL Implement]**: le impostazioni o le modifiche apportate a una configurazione vengono salvate e implementate. Tutti i campi contrassegnati come ![obbligatori](/help/assets/icons/Required.svg) devono avere valori corretti. L’implementazione consiste in:

   * configurazione di **[!UICONTROL Customer Journey Analytics]**:
      * La visualizzazione dati selezionata viene aggiornata per includere la dimensione e le metriche di Content Analytics.
      * La connessione associata alla visualizzazione dati selezionata viene modificata per includere i set di dati attributi ed eventi di Content Analytics.
      * Un modello di reporting di Content Analytics viene aggiunto a Workspace.


   * configurazione di **[!UICONTROL Adobe Experience Platform]**:
      * La creazione di schemi per modellare eventi di analisi dei contenuti, attributi di risorse e (se configurati) attributi di esperienza.
      * La creazione di set di dati per raccogliere eventi di analisi dei contenuti, attributi delle risorse e (se configurati) attributi di esperienza.
      * La creazione di un flusso di dati che utilizza il servizio di funzionalità per generare e aggiornare gli attributi di contenuto dagli eventi di analisi dei contenuti.


   * Configurazione di **[!UICONTROL Data collection]**:
      * La proprietà dei tag nuova o esistente è configurata per supportare la raccolta dati di Content Analytics. Questa configurazione implica l’inclusione dell’estensione Adobe Content Analytics per i tag.
      * Viene creato uno stream di dati per gli eventi di analisi dei contenuti.
      * L’estensione Adobe Content Analytics è configurata per garantire che gli eventi di analisi dei contenuti vengano inviati allo stream di dati per analisi dei contenuti.
      * Se il Web SDK non è configurato per la proprietà Tag, viene creata una nuova configurazione Web SDK al fine di inviare solo eventi di analisi dei contenuti.
      * Se il Web SDK è configurato per questa proprietà dei tag, non viene apportata alcuna modifica alla configurazione del Web SDK esistente.


* **[!UICONTROL Save]**: le modifiche apportate a una configurazione implementata vengono salvate e l’implementazione viene aggiornata.
* **[!UICONTROL Exit]**. Chiude la configurazione guidata. Tutte le modifiche apportate a una configurazione implementata vengono eliminate.


## Publish {#publish}

Per iniziare a raccogliere i dati per la configurazione di Content Analytics, è necessario pubblicare [manualmente](manual.md) la proprietà dei tag creata dopo aver selezionato **[!UICONTROL Implement]**.


>[!MORELIKETHIS]
>
>[Configurazione manuale](manual.md)
>
