---
title: Configurazione guidata di Content Analytics
description: Come configurare Content Analytics utilizzando una configurazione guidata dell’onboarding
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 61b27e14386aaba1612844f3e00692edd38cba17
workflow-type: tm+mt
source-wordcount: '3192'
ht-degree: 12%

---

# Configurazione guidata di Content Analytics

>[!WARNING]
>
>Questo articolo è una bozza preliminare non ufficiale di una versione finale di prossima pubblicazione e fa parte della documentazione di Content Analytics. Tutti i contenuti sono soggetti a modifiche e nessun obbligo legale può essere derivato dalla versione corrente di questo articolo.
>

{{release-limited-testing}}

La configurazione guidata consente di configurare l’analisi dei contenuti in modo rapido e semplice. La configurazione guidata utilizza una procedura guidata per impostare i requisiti necessari per configurare automaticamente Content Analytics per la tua organizzazione. Nella schermata **[!UICONTROL Configuration]** è possibile creare una nuova configurazione o modificare una configurazione esistente.

>[!IMPORTANT]
>
>Nella tua organizzazione puoi avere una sola configurazione di Analytics contenuto per sandbox.


Per accedere alla configurazione di Content Analytics

* Selezionare **[!UICONTROL Data Management]** > **[!UICONTROL Content Analytics]** dal menu principale in Customer Journey Analytics.

Nella schermata Configurazione analisi contenuto viene visualizzata una tabella delle configurazioni di analisi contenuto esistenti.

![Configurazioni analisi contenuto](../assets/aca-configuration-table.png)
Per ogni configurazione, sono disponibili i seguenti dettagli:

| Colonna | Descrizione |
|---|---|
| **[!UICONTROL Name]** | Nome della configurazione. |
| **[!UICONTROL Created by]** | Account tecnico che ha creato la configurazione. |
| **[!UICONTROL Created on]** | La marca temporale in cui è stata creata la configurazione. |
| **[!UICONTROL Modified on]** | Il timestamp dell’ultima modifica apportata alla configurazione. |
| **[!UICONTROL Sandbox]** | La sandbox all’interno dell’organizzazione in cui è (pianificato per essere) configurato e implementato Content Analytics. |
| **[!UICONTROL Status]** | Stato della configurazione. Lo stato può essere:<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Draft]**: la configurazione viene salvata per un momento successivo e non distribuita.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Failed]**: configurazione non riuscita. È necessario modificare la configurazione e apportare le modifiche necessarie.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**: configurazione completata e implementata correttamente. |

È possibile utilizzare ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per personalizzare la tabella. Selezionare le colonne da visualizzare nella finestra di dialogo **[!UICONTROL Customize table]** e selezionare **[!UICONTROL Apply]** per applicare le modifiche.

Dalla schermata Content Analytics **[!UICONTROL Configuration]** è possibile creare una nuova configurazione o modificare una configurazione esistente.

Per creare una nuova configurazione:

* Seleziona **[!UICONTROL Create configuration]**. Questa azione apre la procedura guidata di configurazione.

Per modificare una configurazione esistente:

* Seleziona ![Altro](/help/assets/icons/More.svg) e quindi ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** per una configurazione di Content Analytics esistente. Questa azione apre la procedura guidata di configurazione.

## Configurazione guidata guidata

La procedura guidata di configurazione è costituita da quattro sezioni ([Dettagli](#details), [Visualizzazione dati](#data-view), [Acquisizione e definizione esperienza](#experience-capture-and-definition) e [Raccolta dati](#data-collection)), ognuna delle quali richiede i dettagli necessari per configurare e configurare Content Analytics. Completa ogni sezione prima di passare a quella successiva, in quanto alcune impostazioni in una sezione potrebbero dipendere dai valori di configurazione delle sezioni precedenti.

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

![Dettagli configurazione analisi contenuto](../assets/aca-configuration-details.png)


### Visualizzazione dati {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Visualizzazione dati"
>abstract="Per la configurazione di Content Analytics è necessario selezionare una visualizzazione dati esistente. In questo modo, puoi unire i dati di analisi dei contenuti con altri dati."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Visualizzazione dati"
>abstract="Seleziona una visualizzazione dati esistente di Customer Journey Analytics con cui desideri unire i dati di analisi dei contenuti."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Visualizzazione dati"
>abstract="Seleziona una visualizzazione dati esistente di Customer Journey Analytics con cui desideri unire i dati di analisi dei contenuti.<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="Nuova visualizzazione dati"
>abstract="La selezione di una nuova visualizzazione dati comporta un aggiornamento a tale visualizzazione dati per includere le metriche e le dimensioni di Content Analytics. Se necessario, anche la connessione associata viene aggiornata per includere i set di dati di analisi dei contenuti. La connessione e la visualizzazione dati attualmente configurate per l’analisi dei contenuti non vengono modificate."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="Pulisci visualizzazione dati selezionata"
>abstract="Hai selezionato una visualizzazione dati per la quale è già stato eseguito il provisioning per Content Analytics. La configurazione di Content Analytics esistente viene rimossa e la visualizzazione dati viene fornita con la nuova configurazione."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Pulizia visualizzazione dati precedente"
>abstract="È stata selezionata una nuova visualizzazione dati. La configurazione Content Analytics per la visualizzazione dati selezionata in precedenza è stata rimossa."

<!-- markdownlint-enable MD034 -->

La configurazione richiede la selezione di una [Visualizzazione dati](/help/data-views/data-views.md).

1. Seleziona una visualizzazione dati

   * Per selezionare una nuova visualizzazione dati per una configurazione, utilizzare ![Dati](/help/assets/icons/Data.svg) **[!UICONTROL Select Data view]**.

     ![Configurazione di Content Analytics di una visualizzazione dati](../assets/aca-configuration-dataview.png)

   * Per modificare una visualizzazione dati per una configurazione, selezionare ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**.

     ![Configurazione di Content Analytics di una visualizzazione dati](../assets/aca-configuration-dataview-edit.png)


   In entrambi gli scenari viene visualizzata una finestra di dialogo **[!UICONTROL Data view]** in cui è possibile selezionare una visualizzazione dati per la configurazione.

   ![Configurazione Content Analytics di una visualizzazione dati - Tabella visualizzazioni dati](../assets/aca-configuration-dataview-dialog.png)

   Per una nuova configurazione, l’elenco mostra solo le visualizzazioni dati associate a sandbox che non hanno una configurazione attiva.

   Se modifichi una configurazione esistente, l’elenco mostra solo le visualizzazioni dati disponibili nella sandbox già associate alla configurazione esistente.

   * Per cercare una visualizzazione dati specifica, utilizzare il campo ![Cerca](/help/assets/icons/Search.svg).
   * Per filtrare l&#39;elenco delle visualizzazioni dati disponibili, selezionare ![Mostra filtri](/help/assets/icons/Filter.svg). Puoi filtrare l’elenco per Connessione, Proprietario e Sandbox.<br/>Utilizzare ![Nascondi](/help/assets/icons/Filter.svg) **[!UICONTROL Hide filters]** per nascondere il riquadro del filtro.
   * Per definire le colonne da visualizzare nella tabella, selezionare ![Impostazioni colonna](/help/assets/icons/ColumnSetting.svg). Selezionare le colonne da visualizzare nella finestra di dialogo **[!UICONTROL Customize table]** e selezionare **[!UICONTROL Apply]** per applicare le modifiche.

1. Selezionare **[!UICONTROL Save]** per confermare la visualizzazione dati selezionata. Selezionare **[!UICONTROL Cancel]** per annullare.


Una visualizzazione dati è associata a una [connessione](/help/connections/overview.md) Customer Journey Analytics. Una connessione si basa su una sandbox all’interno della tua organizzazione. Dopo aver salvato la configurazione, **[!UICONTROL Sandbox]** viene automaticamente compilato con il nome corretto della sandbox, in base alla visualizzazione dati selezionata.


### Acquisizione e definizione dell’esperienza {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Acquisizione e definizione dell’esperienza"
>abstract="Puoi scegliere di includere le esperienze nei dati raccolti con Content Analytics. Quando questa opzione è selezionata, devi definire una o più combinazioni di un regex e parametri di query per definire gli URL per i quali desideri includere le esperienze."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Acquisizione e definizione dell’esperienza"
>abstract="Raccogliere esperienze in Content Analytics"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="Acquisizione e definizione dell’esperienza"
>abstract="Specifica i parametri che determinano il rendering del contenuto sul sito web."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Acquisizione e definizione dell’esperienza"
>abstract="Puoi modificare le impostazioni nell’estensione Adobe Content Analytics nella proprietà Tags associata alla configurazione corrente."

<!-- markdownlint-enable MD034 -->

In questa sezione, puoi scegliere di includere le esperienze nei dati raccolti con Content Analytics.  Un’esperienza è tutto il testo su una pagina web riproducibile utilizzando l’URL utilizzato dall’utente che visita inizialmente quella pagina web.

Per impostazione predefinita, **[!UICONTROL Include experiences]** è disattivato. Quando viene selezionata, è necessario definire gli URL per i quali includere le esperienze.

Considera l’inclusione delle esperienze solo quando è applicabile quanto segue:

* Puoi accedere al contenuto del sito solo utilizzando URL rivolti al pubblico. L’accesso al sito non richiede token personalizzati, cookie o altri meccanismi non disponibili tramite l’URL.
* Le pagine del sito devono essere riproducibili utilizzando l’URL della pagina.

Per includere le esperienze in una configurazione nuova o non implementata:

![Configurazione di Content Analytics Acquisizione e definizione dell&#39;esperienza](../assets/aca-configuration-experience.png)

1. Abilita **[!UICONTROL Include experiences]**.
1. Facoltativamente. specifica la modalità di rendering del contenuto sul sito web. I parametri sono zero o più combinazioni di **[!UICONTROL Domain regular expression]** e **[!UICONTROL Query parameters]**.
   1. Immettere un **[!UICONTROL Domain regular expression]**, ad esempio `/^(?!.*\b(store|help|admin)\b)/`. Assicurarsi di eseguire l&#39;escape delle espressioni regolari, utilizzando `/`.
   1. Specificare un elenco separato da virgole di **[!UICONTROL Query parameters,]**, ad esempio `outdoors, patio, kitchen`.
1. Selezionare **[!UICONTROL Remove]** se si desidera rimuovere una combinazione di espressioni regolari di dominio e parametri di query.
1. Selezionare **[!UICONTROL Add Regex]** se si desidera aggiungere un&#39;altra combinazione di un&#39;espressione regolare e parametri di query.

Per modificare esperienze esistenti o includerne di nuove in una configurazione implementata:

![Configurazione di Content Analytics Acquisizione e definizione dell&#39;esperienza](../assets/aca-configuration-experience-edit.png)

* Seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** per modificare la configurazione di raccolta esperienze in Content Analytics. Sei stato reindirizzato all&#39;estensione [Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) nella proprietà Tags associata alla configurazione corrente.




### Raccolta dati {#onboarding-data-collection}

In questa sezione configuri come raccogliere i dati di analisi dei contenuti.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Raccolta dati"
>abstract="Definisci la proprietà Tag da utilizzare o creane una nuova. Definisci inoltre le pagine e le risorse da includere o escludere utilizzando espressioni regolari."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Raccolta dati"
>abstract="**Fornisci una proprietà tag**"

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
>abstract="Puoi modificare le impostazioni per le pagine dell’estensione Adobe Content Analytics nella proprietà Tags associata alla configurazione corrente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Raccolta dati"
>abstract="Puoi modificare le impostazioni per le risorse nell’estensione Adobe Content Analytics nella proprietà Tags associata alla configurazione corrente."

<!-- markdownlint-enable MD034 -->

#### Nuova configurazione {#new-configuration}

In una nuova configurazione, devi definire se desideri utilizzare una proprietà Tags esistente o crearne una nuova. Inoltre, devi definire le pagine e le risorse da includere o escludere utilizzando espressioni regolari.

* Per utilizzare una proprietà Tags esistente:

  ![Tag esistente raccolta dati di Content Analytics](../assets/aca-configuration-datacollection-existingtag.png)

   1. Seleziona **[!UICONTROL Existing]**.
   2. Selezionare una proprietà esistente dal menu a discesa **[!UICONTROL Tags property]**. Puoi iniziare a digitare per cercare e limitare le opzioni disponibili.

* Per creare una nuova proprietà Tags:

  ![Nuovo tag per la raccolta dati di Content Analytics](../assets/aca-configuration-datacollection-newtag.png)

   1. Seleziona **[!UICONTROL Create new]**.
   2. Specificare **[!UICONTROL Tags name]**, ad esempio `ACA Test`.
   3. Specificare **[!UICONTROL Domains]**, ad esempio `example.com`.

* Se hai selezionato di includere le esperienze, indica quali pagine includere o escludere durante la raccolta di dati per Content Analytics.

   * Specificare un&#39;espressione regolare per **[!UICONTROL Experience]**. Ad esempio: `/^(?!.*documentation).*/` per escludere tutte le pagine della documentazione da Content Analytics. Assicurarsi di eseguire l&#39;escape delle espressioni regolari, utilizzando `/`.

* Indica quali risorse includere o escludere durante la raccolta di dati per Content Analytics.

   * Specificare un&#39;espressione regolare per **[!UICONTROL Asset]**. Ad esempio: `/^(?!.*(logo\.jpg|\.svg)).*$/` per escludere tutte le immagini JPEG e SVG del logo da Content Analytics. Assicurarsi di eseguire l&#39;escape delle espressioni regolari, utilizzando `/`.


#### Configurazione esistente {#existing-configuration}

Per una configurazione esistente, non è possibile modificare la proprietà Tags. Tuttavia, puoi modificare le pagine e le risorse da includere o escludere.

* Per modificare le pagine da includere o escludere durante la raccolta dei dati per Content Analytics, selezionare ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** sotto **[!UICONTROL Experience]**. Sei stato reindirizzato all&#39;[estensione Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) associata alla proprietà Tags per la configurazione di Content Analytics corrente. Puoi modificare l’espressione regolare per includere o escludere pagine. Assicurati di [pubblicare](manual.md#publish) le modifiche.

* Per modificare le risorse da includere o escludere durante la raccolta dei dati per Content Analytics, seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** sotto **[!UICONTROL Asset]**. Sei stato reindirizzato all&#39;[estensione Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) associata alla proprietà Tags per la configurazione di Content Analytics corrente. Puoi modificare l’espressione regolare per includere o escludere le risorse. Assicurati di [pubblicare](manual.md#publish) le modifiche.

### Riepilogo {#summary}

Dopo aver fornito tutti i dettagli necessari, un riepilogo fornisce dettagli sugli artefatti creati o modificati.

* Quando si implementa una nuova configurazione, viene visualizzato un **[!UICONTROL You're almost ready to implement _nome configurazione _per il riepilogo di Content Analytics]**.

* Per le configurazioni implementate esistenti, viene visualizzato un **[!UICONTROL You have implemented _nome configurazione _per il riepilogo di Content Analytics]**.

![Riepilogo configurazione analisi contenuto](../assets/aca-configuration-summary.png)

### Azioni {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Conferma dell’implementazione"
>abstract="Se si seleziona **[!UICONTROL Implement]**, l&#39;analisi dei contenuti verrà configurata in base all&#39;input fornito in questo flusso di lavoro. Per impostazione predefinita, vengono scelte diverse impostazioni in base a ciò che è generalmente utile per Content Analytics, ma l’utente (in qualità di titolare del trattamento dei dati) deve esaminare le impostazioni di ciascun artefatto per verificare che le impostazioni siano implementate in conformità all’informativa sulla privacy, ai diritti e agli obblighi contrattuali e ai requisiti di consenso secondo la legge applicabile.<br/><br/>Nessun dato verrà raccolto finché la libreria Tag associata a questa configurazione non verrà pubblicata manualmente.<br/><br/>Per derivare gli attributi di immagini e testo, Adobe recupera gli attributi utilizzando:<ol><li>L’URL, acquisito al momento della visita del sito dell’utente, in base alle impostazioni di raccolta dati configurate e</li><li>l’URL in cui è ospitata l’immagine.</li></ol>Non devi assegnare tag alle immagini ospitate su siti di terze parti."

<!-- markdownlint-enable MD034 -->

Dopo aver creato o modificato una configurazione, sono disponibili le azioni riportate di seguito.

* **[!UICONTROL Discard]**: tutte le modifiche apportate durante la creazione di una nuova configurazione o la modifica di una configurazione esistente vengono ignorate.
* **[!UICONTROL Save for later]**: le modifiche apportate a una nuova configurazione o a una configurazione esistente non ancora implementata vengono salvate. Puoi rivedere la configurazione in un secondo momento per apportare ulteriori modifiche o implementarla.
* **[!UICONTROL Implement]**: le impostazioni o le modifiche apportate a una nuova configurazione o a una configurazione esistente non ancora implementata vengono salvate e implementate. L&#39;attuazione consiste in:
   * Configurazione di **[!UICONTROL Adobe Experience Platform]**:
      * La creazione di schemi per modellare eventi di Content Analytics, attributi di risorse e (se configurati) attributi di esperienza.
      * La creazione di set di dati per raccogliere eventi di analisi dei contenuti, attributi delle risorse e (se configurati) attributi di esperienza.
      * La creazione di un flusso di dati che utilizza il servizio di funzionalità per generare e aggiornare gli attributi di contenuto dagli eventi di Content Analytics.
   * Configurazione di **[!UICONTROL Data collection]**:
      * La proprietà Tags nuova o esistente è configurata per supportare la raccolta dati di Content Analytics. Questa configurazione implica l’inclusione dell’estensione Adobe Content Analytics per i tag.
      * Viene creato uno stream di dati per gli eventi di Analisi del contenuto.
      * L’estensione Adobe Content Analytics è configurata per garantire che gli eventi di Content Analytics vengano inviati allo stream di dati per Content Analytics.
      * Se il Web SDK non è configurato per la proprietà Tags, viene creata una nuova configurazione Web SDK per inviare solo eventi di Content Analytics.
      * Se il Web SDK è configurato per questa proprietà Tags, non viene apportata alcuna modifica alla configurazione esistente del Web SDK.
   * Configurazione di **[!UICONTROL Customer Journey Analytics]**:
      * La visualizzazione dati selezionata viene aggiornata per includere la dimensione e le metriche di Content Analytics.
      * La connessione associata alla visualizzazione dati selezionata viene modificata per includere eventi Content Analytics e set di dati di attributi.
      * A Workspace viene aggiunto un modello di reporting di Content Analytics.
* **[!UICONTROL Save]**: le modifiche apportate a una configurazione implementata vengono salvate e l&#39;implementazione viene aggiornata.
* **[!UICONTROL Exit]**. Chiude la configurazione guidata. Tutte le modifiche apportate a una configurazione implementata vengono ignorate.


## Pubblica {#publish}

Per attivare la configurazione di Content Analytics, devi pubblicare la proprietà Tags creata dopo aver selezionato **[!UICONTROL Implement]** [manualmente](manual.md).


## Impostazioni e configurazioni di onboarding

Le sezioni seguenti descrivono le impostazioni e le configurazioni applicate a [Customer Journey Analytics](#customer-journey-analytics-cja), [Experience Platform](#experience-platform-aep) e [Data Collection](#data-collection-dc) nell&#39;ambito dell&#39;implementazione di una configurazione Content Analytics.

Vengono forniti dettagli per i seguenti scenari:

* La proprietà **Tags** esiste **✓** o non esiste **✕**.
* L&#39;estensione **Web SDK** per la proprietà Tags esiste **✓** o non esiste **✕**.
* L&#39;estensione Adobe **Content Analytics** per la proprietà Tag esiste **✓** o non esiste **✕**.

### Customer Journey Analytics {#cja}

<table style="table-layout:fixed">
  <tr>
    <th></th>
    <th colspan="4">Scenari</th>
  </tr>
  <tr>
    <th>
      <strong>Impostazione</strong>
    </th>
    <th>
      <strong>✓ Tag<br>✓ Web SDK<br/>✓ Content Analytics</strong>
    </th>
    <th>
      <strong>✓ Tag<br>✓ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✓Tag<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✕ Tag<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
  </tr>
  <tbody>
    <tr>
      <td>Modello di rapporto</td>
      <td colspan="4">È disponibile un modello di report</td>
    </tr>
    <tr>
      <td>Visualizzazione dati</td>
      <td colspan="4">Modificato/creato per avere dimensioni e metriche di ACA</td>
    </tr>
    <tr>
      <td>Connessione</td>
      <td colspan="4">Modificato per includere i set di dati di ACA (eventi di ACA, attributi della risorsa, attributo dell’esperienza)</td>
    </tr>
  </tbody>
</table>

### Experience Platform {#aep}

<table style="table-layout:fixed">
  <tr>
    <th></th>
    <th colspan="4">Scenari</th>
  </tr>
  <tr>
    <th>
      <strong>Impostazione</strong>
    </th>
    <th>
      <strong>✓ Tag<br>✓ Web SDK<br/>✓ Content Analytics</strong>
    </th>
    <th>
      <strong>✓ Tag<br>✓ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✓Tag<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✕ Tag<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
  </tr>
  <tbody>
    <tr>
      <td colspan="5"><strong><br/>Schema eventi di Content Analytics</strong></td>
    </tr>
    <tr>
      <td style="margin-left: 160.0px;">Nome</td>
      <td>Eventi Content Analytics</td>
      <td>Eventi Content Analytics</td>
      <td>Eventi Content Analytics</td>
      <td>Eventi Content Analytics</td>
    </tr>
    <tr>
      <td>Descrizione</td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
    </tr>
    <tr>
      <td>Profilo abilitato</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Set di dati di eventi Content Analytics</strong></td>
    </tr>
    <tr>
      <td>Nome</td>
      <td>Eventi Content Analytics</td>
      <td>Eventi Content Analytics</td>
      <td>Eventi Content Analytics</td>
      <td>Eventi Content Analytics</td>
    </tr>
    <tr>
      <td>Schema</td>
      <td>Evento Content Analytics</td>
      <td>Evento Content Analytics</td>
      <td>Evento Content Analytics</td>
      <td>Evento Content Analytics</td>
    </tr>
    <tr>
      <td>Descrizione</td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
    </tr>
    <tr>
      <td>Tag</td>
      <td><i>vuoto?</i></td>
      <td><i>vuoto?</i></td>
      <td><i>vuoto?</i></td>
      <td><i>vuoto?</i></td>
    </tr>
    <tr>
      <td>Set di dati di sistema</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td>Profilo abilitato</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Governance dei dati (etichette DULE)</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Schema degli attributi della risorsa Content Analytics</strong></td>
    </tr>
    <tr>
      <td>Nome</td>
      <td>Attributi risorse Content Analytics</td>
      <td>Attributi risorse Content Analytics</td>
      <td>Attributi risorse Content Analytics</td>
      <td>Attributi risorse Content Analytics</td>
    </tr>
    <tr>
      <td>Descrizione</td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
    </tr>
    <tr>
      <td>Profilo abilitato</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Set di dati Attributi di Content Analytics Assets</strong></td>
    </tr>
    <tr>
      <td>Nome</td>
      <td>Attributi risorse Content Analytics</td>
      <td>Attributi risorse Content Analytics</td>
      <td>Attributi risorse Content Analytics</td>
      <td>Attributi risorse Content Analytics</td>
    </tr>
    <tr>
      <td>Schema</td>
      <td>Attributi risorse Content Analytics</td>
      <td>Attributi risorse Content Analytics</td>
      <td>Attributi risorse Content Analytics</td>
      <td>Attributi risorse Content Analytics</td>
    </tr>
    <tr>
      <td>Descrizione</td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
    </tr>
    <tr>
      <td>Tag</td>
      <td><i>vuoto?</i></td>
      <td><i>vuoto?</i></td>
      <td><i>vuoto?</i></td>
      <td><i>vuoto?</i></td>
    </tr>
    <tr>
      <td>Set di dati di sistema</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td>Profilo abilitato</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Governance dei dati (etichette DULE)</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Schema degli attributi di esperienza Content Analytics</strong></td>
    </tr>
    <tr>
      <td>Nome</td>
      <td>Attributi esperienza Content Analytics</td>
      <td>Attributi esperienza Content Analytics</td>
      <td>Attributi esperienza Content Analytics</td>
      <td>Attributi esperienza Content Analytics</td>
    </tr>
    <tr>
      <td>Descrizione</td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
    </tr>
    <tr>
      <td>Profilo abilitato</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Set di dati Attributi esperienza Content Analytics</strong></td>
    </tr>
    <tr>
      <td>Nome</td>
      <td>Attributi esperienza Content Analytics</td>
      <td>Attributi esperienza Content Analytics</td>
      <td>Attributi esperienza Content Analytics</td>
      <td>Attributi esperienza Content Analytics</td>
    </tr>
    <tr>
      <td>Schema</td>
      <td>Attributi esperienza Content Analytics</td>
      <td>Attributi esperienza Content Analytics</td>
      <td>Attributi esperienza Content Analytics</td>
      <td>Attributi esperienza Content Analytics</td>
    </tr>
    <tr>
      <td>Descrizione</td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
      <td><i>tbd predeterminato</i></td>
    </tr>
    <tr>
      <td>Tag</td>
      <td><i>vuoto?</i></td>
      <td><i>vuoto?</i></td>
      <td><i>vuoto?</i></td>
      <td><i>vuoto?</i></td>
    </tr>
    <tr>
      <td>Set di dati di sistema</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td>Profilo abilitato</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Governance dei dati (etichette DULE)</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
  </tbody>
</table>


### Raccolta dati {#dc}

<table style="table-layout:fixed">
  <tr>
    <th></th>
    <th colspan="4">Scenari</th>
  </tr>
  <tr>
    <th>
      <strong>Impostazione</strong>
    </th>
    <th>
      <strong>✓ Tag<br>✓ Web SDK<br/>✓ Content Analytics</strong>
    </th>
    <th>
      <strong>✓ Tag<br>✓ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✓Tag<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✕ Tag<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
  </tr>
  <tbody>
    <tr>
      <td colspan="5"><strong><br/>Datastream</strong></td>
    </tr>
    <tr>
      <td>Nome</td>
      <td><i>valore esistente</i></td>
      <td>Analisi dei contenuti</td>
      <td>Analisi dei contenuti</td>
      <td>Analisi dei contenuti</td>
    </tr>
    <tr>
      <td>Descrizione</td>
      <td><i>valore esistente</i></td>
      <td><i>predeterminato</i></td>
      <td><i>predeterminato</i></td>
      <td><i>predeterminato</i></td>
    </tr>
    <tr>
      <td>Schema di mappatura</td>
      <td><i>valore esistente</i></td>
      <td><i>predeterminato</i></td>
      <td><i>predeterminato</i></td>
      <td><i>predeterminato</i></td>
    </tr>
    <tr>
      <td>Geolocalizzazione e ricerca di rete</td>
      <td><i>valori esistenti</i></td>
      <td>Tutte le opzioni disattivate</td>
      <td>Tutte le opzioni disattivate</td>
      <td>Tutte le opzioni disattivate</td>
    </tr>
    <tr>
      <td>Ricerca dispositivo</td>
      <td><i>valore esistente</i></td>
      <td>Non raccogliere informazioni sul dispositivo</td>
      <td>Non raccogliere informazioni sul dispositivo</td>
      <td>Non raccogliere informazioni sul dispositivo</td>
    </tr>
    <tr>
      <td>Offuscamento IP</td>
      <td><i>valore esistente</i></td>
      <td>Nessuno</td>
      <td>Nessuno</td>
      <td>Nessuno</td>
    </tr>
    <tr>
      <td>Cookie ID di prima parte</td>
      <td><i>valore esistente</i></td>
      <td>Off</td>
      <td>Off</td>
      <td>Off</td>
    </tr>
    <tr>
      <td>Sincronizzazione ID di terze parti</td>
      <td><i>valore esistente</i></td>
      <td>Off</td>
      <td>Off</td>
      <td>Off</td>
    </tr>
    <tr>
      <td>Tipo di accesso</td>
      <td><i>valore esistente</i></td>
      <td>Autenticazione mista</td>
      <td>Autenticazione mista</td>
      <td>Autenticazione mista</td>
    </tr>
    <tr>
      <td>Media Analytics</td>
      <td><i>valore esistente</i></td>
      <td>Off</td>
      <td>Off</td>
      <td>Off</td>
    </tr>
        <tr>
      <td>Rilevamento bot</td>
      <td><i>valore esistente</i></td>
      <td>Off</td>
      <td>Off</td>
      <td>Off</td>
    </tr>
    <tr>
      <td>Mappatura</td>
      <td><i>valore esistente</i></td>
      <td><i>utente fornito</i></td>
      <td><i>utente fornito</i></td>
      <td><i>utente fornito</i></td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Proprietà Tags</strong><br/>Proprietà esistente o nuova. Il nome e il dominio sono forniti dall’utente.</td>
    </tr>
    <tr>
      <td>Nome</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td><i>utente fornito</i> (predefinito "Content Analytics")</td>
    </tr>
    <tr>
      <td>Dominio</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td ><i>predeterminato</i></td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Libreria tag</strong></td>
    </tr>
    <tr>
      <td>Nome</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>
        <br/>
      </td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Estensione Web SDK</strong></td>
    </tr>
    <tr>
      <td>Nome</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Content Analytics - Web SDK</td>
      <td>Content Analytics - Web SDK</td>
    </tr>
    <tr>
      <td>Organizzazione IMS</td>
      <td><i>popolato automaticamente</i></td>
      <td><i>popolato automaticamente</i></td>
      <td><i>popolato automaticamente</i></td>
      <td><i>popolato automaticamente</i></td>
    </tr>
    <tr>
      <td>Dominio Edge</td>
      <td><i>valore esistente<br/>Potrebbe essere necessario un aggiornamento per corrispondere all'implementazione di AppMeasurement</i></td>
      <td><i>valore esistente<br/>Potrebbe essere necessario un aggiornamento per corrispondere all'implementazione di AppMeasurement</i></td>
      <td>
        <a href="http://edge.adobedc.net">edge.adobedc.net</a>
      </td>
      <td>
        <a href="http://edge.adobedc.net">edge.adobedc.net</a>
      </td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Stream di dati</strong></td>
    </tr>
    <tr>
      <td>Produzione</td>
      <td><i>valore esistente<br/>Override dello stream di dati utilizzato per inviare a uno stream di dati diverso</i></td>
      <td><i>valore esistente<br/>Override dello stream di dati utilizzato per inviare a uno stream di dati diverso</i></td>
      <td><i>utente fornito</i>?</td>
      <td><i>utente fornito</i>?</td>
    </tr>
    <tr>
      <td>Staging</td>
      <td><i>valore esistente<br/>Override dello stream di dati utilizzato per inviare a uno stream di dati diverso</i></td>
      <td><i>valore esistente<br/>Override dello stream di dati utilizzato per inviare a uno stream di dati diverso</i></td>
      <td><i>utente fornito</i>?</td>
      <td><i>utente fornito</i>?</td>
    </tr>
    <tr>
      <td>Sviluppo</td>
      <td><i>valore esistente<br/>Override dello stream di dati utilizzato per inviare a uno stream di dati diverso</i></td>
      <td><i>valore esistente<br/>Override dello stream di dati utilizzato per inviare a uno stream di dati diverso</i></td>
      <td><i>utente fornito</i>?</td>
      <td><i>utente fornito</i>?</td>
    </tr>
    <tr>
      <td>Privacy</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Dentro?</td>
      <td>Dentro?</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Identità</strong></td>
    </tr>
    <tr>
      <td>Migrazione ECID</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Selezionato</td>
      <td>Selezionato</td>
    </tr>
    <tr>
      <td>Utilizzare i cookie di terze parti</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Selezionato</td>
      <td>Selezionato</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Personalizzazione</strong></td>
    </tr>
    <tr>
      <td>Migrare Target da at.js a Web SDK</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Deselezionato</td>
      <td>Deselezionato</td>
    </tr>
    <tr>
      <td>Abilita archiviazione personalizzazione</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Deselezionato</td>
      <td>Deselezionato</td>
    </tr>
    <tr>
      <td>Raccolta con clic automatico per Adobe Journey Optimizer</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Sempre</td>
      <td>Sempre</td>
    </tr>
    <tr>
      <td>Raccolta con clic automatico per Adobe Target</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Mai</td>
      <td>Mai</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Raccolta dati</strong></td>
    </tr>
    <tr>
      <td>Raccogliere clic sui collegamenti interni</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Deselezionato</td>
      <td>Deselezionato</td>
    </tr>
    <tr>
      <td>Raccogli clic sui collegamenti esterni</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Deselezionato</td>
      <td>Deselezionato</td>
    </tr>
    <tr>
      <td>Raccogliere i clic sui collegamenti di download</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Deselezionato</td>
      <td>Deselezionato</td>
    </tr>
    <tr>
      <td>Quando si inviano dati evento, includi automaticamente</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Tutte le informazioni di contesto predefinite</td>
      <td>Tutte le informazioni di contesto predefinite</td>
    </tr>
    <tr>
      <td>Contenuti multimediali in streaming</td>
      <td><i>valori esistenti</i></td>
      <td><i>valori esistenti</i></td>
      <td>Valori vuoti</td>
      <td>Valori vuoti</td>
    </tr>
    <tr>
      <td>Override della configurazione dello stream di dati</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>Corrispondenza configurazione dello stream di dati</td>
      <td>Corrispondenza configurazione dello stream di dati</td>
    </tr>
    <tr>
      <td>Impostazioni avanzate - Percorso base Edge</td>
      <td><i>valore esistente</i></td>
      <td><i>valore esistente</i></td>
      <td>vedi</td>
      <td>vedi</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Estensione Content Analytics</strong></td>
    </tr>
    <tr>
      <td>Stream di dati</td>
      <td><i>valore esistente</i></td>
      <td><i>predeterminato</i></td>
      <td><i>predeterminato</i></td>
      <td><i>predeterminato</i></td>
    </tr>
    <tr>
      <td>Acquisizione esperienza e definizione</td>
      <td><i>valore esistente</i></td>
      <td><i>utente fornito</i></td>
      <td><i>utente fornito</i></td>
      <td><i>utente fornito</i></td>
    </tr>
    <tr>
      <td>Filtro eventi</td>
      <td><i>valore esistente</i></td>
      <td><i>utente fornito</i></td>
      <td><i>utente fornito</i></td>
      <td><i>utente fornito</i></td>
    </tr>
  </tbody>
</table>

>[!MORELIKETHIS]
>
>[Configurazione manuale](manual.md)
>
