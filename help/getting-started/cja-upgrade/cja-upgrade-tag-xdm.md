---
title: Aggiungere la logica di raccolta dati XDM al tag
description: Scopri come aggiungere la logica di raccolta dati XDM al tag
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc6c7568-8bd2-4ee1-ab1b-9fa1f6138811
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '1463'
ht-degree: 100%

---

# Aggiungere la logica di raccolta dati XDM al tag {#upgrade-tag-xdm}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-xdm"
>title="Aggiungere la logica di raccolta dati XDM al tag"
>abstract="Con il tag di caricamento installato sul sito, puoi aggiungere regole ed elementi di dati per compilare un oggetto XDM da inviare a Adobe. Adobe consiglia di mantenere un documento di progettazione della soluzione per tenere traccia del modo in cui vengono configurati i tag.<br><br>Questo passaggio richiede molto lavoro, in quanto comporta la configurazione di tutta la logica Analytics per la proprietà. Potrebbe essere necessario dedicare oltre un mese per stabilire le corrette regole dei tag, testarle e distribuirle sul sito."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Dopo [aver creato il tag e aggiunto l’estensione Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), devi effettuare la configurazione con elementi dati e regole in base a come desideri tenere traccia del sito e inviare dati ad Adobe Experience Platform. Dopo aver configurato gli elementi dati e le regole per il tag, puoi generarlo e pubblicarlo.

## Configurare gli elementi dati

Gli elementi dati sono i blocchi costitutivi per il dizionario dati (o mappa dati). Utilizza elementi dati per raccogliere, organizzare e distribuire dati in tutta la tecnologia marketing e pubblicitaria. Puoi impostare elementi dati nel tag che leggono dal livello dati e possono essere utilizzati per inviare dati ad Adobe Experience Platform. Per ulteriori informazioni sugli elementi dati, consulta [Elementi dati](https://experienceleague.adobe.com/it/docs/experience-platform/tags/ui/data-elements) nella documentazione dei tag.

Le sezioni seguenti descrivono gli elementi dati consigliati e altri elementi dati comuni che puoi configurare.

Esistono diversi tipi di elementi dati. Due elementi dati comuni che potresti voler configurare sono: uno che acquisisce il nome della pagina che le persone stanno visualizzando sul tuo sito e un altro che acquisisce l’ID Experience Cloud di ogni persona che visita il tuo sito.

Dopo aver configurato questi due elementi dati, puoi configurare elementi dati aggiuntivi per i dati specifici che desideri acquisire.

Infine, dopo aver definito tutti gli elementi dati desiderati, devi assegnare gli elementi dati allo [schema creato](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) in precedenza. A questo scopo, definisci un elemento dati XDM che fornisce una rappresentazione dello schema XDM.

<!-- Assigning data elements to an XDM object. All of the available XDM objects are based on the schema -->

### Creare gli elementi dati suggeriti

Le sezioni seguenti descrivono come creare elementi dati comuni applicabili alla maggior parte delle organizzazioni.

#### Elemento dati Nome pagina

Un elemento dati comune che si applica alla maggior parte delle organizzazioni è un elemento dati che acquisisce il nome della pagina visualizzata dalle persone.

Per creare un elemento dati Nome pagina:

1. Accedi a experience.adobe.com utilizzando le credenziali Adobe ID.

1. In Adobe Experience Platform, passa a **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Nella pagina **[!UICONTROL Tag Properties]**, seleziona il tag appena creato dall’elenco delle proprietà per aprirlo.

1. Seleziona **[!UICONTROL Data Elements]** (Elementi dati) nella barra a sinistra.

1. Seleziona **[!UICONTROL Add Data Element]** (Aggiungi elemento dati).

1. Nella finestra di dialogo **[!UICONTROL Create Data Element]**, fornisci le seguenti informazioni:

   * **[!UICONTROL Name]**: il nome del tuo elemento dati. Ad esempio `Page Name`.

   * **[!UICONTROL Extension]**: seleziona **[!UICONTROL Core]** dall’elenco.

   * **[!UICONTROL Data Element Type]**: seleziona **[!UICONTROL Page Info]** dall’elenco.

   * **[!UICONTROL Attribute]**: seleziona **[!UICONTROL Title]** dall’elenco.

     ![Creare un elemento dati utilizzando le informazioni della pagina](assets/create-dataelement-1.png)

     In alternativa, puoi usare il valore da una variabile del livello dati, ad esempio `pageName` e il tipo di elemento dati [!UICONTROL JavaScript Variable] (Variabile JavaScript) per definire l’elemento dati.

     ![Creare un elemento dati utilizzando una variabile Javascript](assets/create-dataelement-2.png)

1. Seleziona **[!UICONTROL Save]** (Salva).

   Ora immagina di voler impostare un elemento dati che faccia riferimento all’ID Experience Cloud fornito automaticamente dall’SDK per Web Adobe Experience Platform e disponibile tramite l’estensione Experience Cloud ID Service.

1. Continua con [elemento dati ECID](#ecid-data-element).

#### Elemento dati ECID

Un elemento dati comune che si applica alla maggior parte delle organizzazioni è un elemento dati che acquisisce l’Experience Cloud ID di ogni persona che visita il sito.

Per creare un elemento dati ECID:

1. Accedi a experience.adobe.com utilizzando le credenziali Adobe ID.

1. In Adobe Experience Platform, passa a **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Seleziona il tag appena creato dall’elenco [!UICONTROL Tag Properties] (Proprietà tag) per aprirlo.

1. (Condizionale) Installa l’estensione del servizio Experience Cloud ID se non è già installata:

   1. Seleziona **[!UICONTROL Extensions]** (Elementi dati) nella barra a sinistra.

   1. La scheda **[!UICONTROL Installed]** è selezionata per impostazione predefinita. Se il riquadro **[!UICONTROL Experience Cloud ID Service]** è elencato, procedi al passaggio 5.

   1. Se il riquadro **[!UICONTROL Experience Cloud ID Service]** non è elencato, seleziona la scheda **[!UICONTROL Catalog]**.

   1. Nel campo di ricerca, cerca **[!UICONTROL Experience Cloud ID Service]**, quindi seleziona il riquadro visualizzato.

   1. Seleziona **[!UICONTROL Install]** > **[!UICONTROL Save]**.

1. Seleziona **[!UICONTROL Data Elements]** (Elementi dati) nella barra a sinistra.

1. Seleziona **[!UICONTROL Add Data Element]** (Aggiungi elemento dati).

1. Nella finestra di dialogo **[!UICONTROL Create Data Element]**, fornisci le seguenti informazioni:

   * **[!UICONTROL Name]**: il nome del tuo elemento dati. Ad esempio `ECID`.

   * **[!UICONTROL Extension]**: seleziona **[!UICONTROL Experience Cloud ID Service]** dall’elenco.

   * **[!UICONTROL Data Element Type]**: seleziona **[!UICONTROL ECID]** dall’elenco.

     ![Elemento dati ECID](assets/ecid-dataelement.png)

1. Seleziona **[!UICONTROL Save]** (Salva).

1. Continua con [Creare elementi dati aggiuntivi](#create-additional-data-elements).

### Creare elementi dati aggiuntivi

Crea un elemento dati per ogni tipo di dati che desideri raccogliere. Utilizza lo stesso processo descritto in [Elemento dati Nome pagina](#page-name-data-element) e [Elemento dati ECID](#ecid-data-element) per creare ogni elemento dati aggiuntivo.

Per ogni elemento dati creato deve essere presente un campo correlato nello schema.

Gli elementi dati comuni variano a seconda dei requisiti aziendali e di settore. Considera i seguenti elementi dati comuni, organizzati per settore:

**Elementi dati per la vendita al dettaglio**

* Prodotti

* Aggiunte al carrello

* Pagamenti

**Elementi dati finanziari**

* ID transazione

* Data transazione

* Tipo di servizio

**Elementi dati per l’assistenza sanitaria**

* ID provider

* Data della visita

* Tipo di trattamento

Dopo aver creato tutti gli elementi dati necessari per l’implementazione della tua organizzazione, continua con [Elemento dati oggetto XDM](#xdm-object-data-element).

### Elemento dati oggetto XDM

Infine, immagina ora di voler mappare uno degli elementi dati creati allo [schema creato](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) in precedenza. A questo scopo, definisci un elemento dati oggetto XDM che fornisca una rappresentazione dello schema XDM.

Per definire un elemento dati oggetto XDM:

1. Accedi a experience.adobe.com utilizzando le credenziali Adobe ID.

1. In Adobe Experience Platform, passa a **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Seleziona il tag appena creato dall’elenco [!UICONTROL Tag Properties] (Proprietà tag) per aprirlo.

1. Seleziona **[!UICONTROL Data Elements]** (Elementi dati) nella barra a sinistra.

1. Seleziona **[!UICONTROL Add Data Element]** (Aggiungi elemento dati).

1. Nella finestra di dialogo **[!UICONTROL Create Data Element]**, fornisci le seguenti informazioni:

   * **[!UICONTROL Name]**: il nome del tuo elemento dati. Ad esempio `XDM - Page View`.

   * **[!UICONTROL Extension]**: seleziona **[!UICONTROL Adobe Experience Platform Web SDK]** dall’elenco.

   * **[!UICONTROL Data Element Type]**: seleziona **[!UICONTROL XDM Object]** dall’elenco.

   * **[!UICONTROL Sandbox]**: seleziona la sandbox dall’elenco.

   * **[!UICONTROL Schema]**: seleziona lo schema dall’elenco.

1. Mappa l’attributo `identification > core > ecid` all’elemento dati ECID, definito nello schema. Seleziona l’icona del cilindro per scegliere facilmente l’elemento dati ECID dall’elenco degli elementi dati.

   ![Scegli l’elemento dati ECID](assets/pick-ecid-dataelement.png)

   ![Mappa l’elemento dati ECID](assets/map-ecid.png)

1. Mappa l’attributo `web > webPageDetails > name` all’elemento dati Page Name (Nome pagina), definito nello schema.

   ![Mappa l’elementi dati Page Name (Nome pagina)](assets/map-pagename.png)

1. Seleziona **[!UICONTROL Save]** (Salva).

1. Continua con [Configura regole](#configure-rules).

## **Configura regole**

I tag in Adobe Experience Platform seguono un sistema basato su regole. Cercano le interazione degli utenti e i relativi dati. Quando i criteri descritti nelle tue regole vengono soddisfatti, la regola attiva l’estensione, lo script o il codice lato client identificato. Puoi utilizzare le regole per inviare dati (come un oggetto XDM) in Adobe Experience Platform utilizzando l’estensione Adobe Experience Platform Web SDK.

Per definire una regola:

>[!NOTE]
>
>I passaggi seguenti sono un esempio di definizione di una regola che invia dati XDM, contenenti valori da altri elementi di dati, a Adobe Experience Platform.
>
>Puoi utilizzare le regole in vari modi nel tag per manipolare le variabili (utilizzando gli elementi dati).
>
>Per ulteriori informazioni, consulta la sezione [Regole](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=it) per ulteriori informazioni.

1. Accedi a experience.adobe.com utilizzando le credenziali Adobe ID.

1. In Adobe Experience Platform, passa a **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Seleziona il tag appena creato dall’elenco [!UICONTROL Tag Properties] (Proprietà tag) per aprirlo.

1. Seleziona **[!UICONTROL Rules]** (Elementi dati) nella barra a sinistra.

1. Seleziona **[!UICONTROL Add Rule]** (Aggiungi elemento dati).

1. Nella finestra di dialogo **[!UICONTROL Create Rule]**, specifica le seguenti informazioni:

   * **[!UICONTROL Name]**: il nome della regola. Ad esempio `Page View`.

   * **[!UICONTROL Events]**: seleziona **[!UICONTROL + Add]**. Quindi, nella finestra di dialogo **[!UICONTROL Event Configuration]**, specifica le seguenti informazioni. Al termine, seleziona **[!UICONTROL Keep Changes]**.

      * **[!UICONTROL Extension]**: seleziona **[!UICONTROL Core]** dall’elenco.

      * **[!UICONTROL Event Type]**: seleziona **[!UICONTROL Window Loaded]** dall’elenco.

        ![Regola - Configurazione evento](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL Actions]**: seleziona **[!UICONTROL + Add]**. Quindi, nella finestra di dialogo [!UICONTROL Action Configuration], specifica le seguenti informazioni. Al termine, seleziona **[!UICONTROL Keep Changes]**.

      * **[!UICONTROL Extension]**: seleziona **[!UICONTROL Adobe Experience Platform Web SDK]** dall’elenco.

      * **[!UICONTROL Action Type]**: seleziona **[!UICONTROL Send event]** dall’elenco.

      * **[!UICONTROL Type]**: seleziona **[!UICONTROL Web Webpagedetails Page Views]** dall’elenco.

      * **[!UICONTROL XDM data]**: seleziona l’icona cilindro quindi seleziona **[!UICONTROL XDM - Page View]** dall’elenco degli elementi di dati.

        ![Regola - Configurazione azione](assets/action-pageview-xdm.png)

        L’aspetto della regola dovrebbe essere il seguente:

        ![Crea regola](assets/rule-pageview.png)

1. Seleziona **[!UICONTROL Save]** (Salva).

1. Ripeti questo processo per ogni regola da aggiungere al sito.

   Per ulteriori informazioni sulle regole, consulta [Regole](https://experienceleague.adobe.com/it/docs/experience-platform/tags/ui/rules) nella documentazione dei tag.

1. Continua con [Creare e pubblicare il tag](#build-and-publish-your-tag).

## Creare e pubblicare il tag

Dopo aver definito gli elementi dati e le regole, devi creare e pubblicare il tag. Quando crei una build della libreria, devi assegnarla a un ambiente. Le estensioni, le regole e gli elementi dati della build vengono quindi compilati e inseriti nell’ambiente assegnato. Ogni ambiente fornisce un codice da incorporare univoco che consente di integrare la build assegnata nel sito.

I tag Adobe Experience Platform supportano flussi di lavoro di pubblicazione semplici o complessi che devono adattarsi alla distribuzione di Adobe Experience Platform Web SDK. Per ulteriori informazioni, consulta la sezione [Panoramica di pubblicazione](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=it).

Per generare e pubblicare il tag:

1. Accedi a experience.adobe.com utilizzando le credenziali Adobe ID.

1. In Adobe Experience Platform, passa a **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Seleziona il tag appena creato dall’elenco [!UICONTROL Tag Properties] (Proprietà tag) per aprirlo.

1. Seleziona **[!UICONTROL Publishing Flow]** nella barra a sinistra.

1. Seleziona **[!UICONTROL Add Library]**.

1. Nella finestra di dialogo **[!UICONTROL Create Library]**, specifica le seguenti informazioni:

   * **[!UICONTROL Name]**: il nome della libreria.

   * **[!UICONTROL Environment]**: seleziona **[!UICONTROL Development (development)]** dall’elenco.

1. Seleziona **[!UICONTROL + Add All Changed Resources]** (Crea set di dati).

   ![Pubblica - Crea libreria](assets/create-library-aep.png)

1. Seleziona **[!UICONTROL Save & Build to Development]** (Salva e crea per lo sviluppo).

   Il tag viene salvato e quindi creato per il tuo ambiente di sviluppo. Un punto verde indica la corretta compilazione del tag nell’ambiente di sviluppo.

1. È possibile selezionare **[!UICONTROL ...]** per ricreare la libreria o spostarla in un ambiente di gestione temporanea o produzione.

   ![Pubblica - Libreria di compilazione](assets/build-library.png)

{{upgrade-final-step}}

