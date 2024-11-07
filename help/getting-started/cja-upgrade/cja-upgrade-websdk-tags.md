---
title: Utilizzare i tag per implementare Web SDK per Customer Journey Analytics
description: Scopri come utilizzare i tag per implementare Web SDK per Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 73%

---

# Utilizzare i tag per implementare Web SDK per Customer Journey Analytics

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), oppure puoi seguire i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

Puoi utilizzare la funzione Tag in Adobe Experience Platform per implementare il codice sul sito per raccogliere i dati. Questa soluzione per la gestione dei tag consente di implementare il codice e altri requisiti di assegnazione dei tag. I tag offrono un’integrazione diretta con Adobe Experience Platform tramite l’estensione dell’SDK per Web di Adobe Experience Platform.

## Creare il tag

1. Nell’interfaccia utente di Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Tags]** (Tag) all’interno di [!UICONTROL DATA COLLECTION] (GESTIONE DATI).

2. Seleziona **[!UICONTROL New Property]** (Nuova proprietà).

   Assegna un nome al tag, seleziona **[!UICONTROL Web]** e immetti un nome di dominio. Seleziona **[!UICONTROL Save]** (Salva) per continuare.

   ![Creare una proprietà](assets/create-property.png)

## Configurare il tag

Dopo aver creato il tag, devi configurarlo con le estensioni corrette e configurare elementi dati e regole in base a come desideri tenere traccia del sito e inviare dati a Adobe Experience Platform.

Seleziona il tag appena creato dall’elenco [!UICONTROL Tag Properties] (Proprietà tag) per aprirlo.


### **Estensioni**

Per garantire che tu possa inviare dati a Adobe Experience Platform (tramite lo stream di dati), aggiungi l’estensione Adobe Platform Web SDK al tag.

Per creare e configurare l’estensione Adobe Experience Platform Web SDK:

1. Seleziona **[!UICONTROL Extensions]** (Estensioni) nella barra a sinistra.

1. Seleziona **[!UICONTROL Catalog]** (Catalogo) nella barra superiore.

1. Cerca o scorri fino all’estensione Adobe Experience Platform Web SDK e seleziona **[!UICONTROL Install]** (Installa) per installarlo.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Seleziona la sandbox e il flusso di dati creato in precedenza per il tuo [!UICONTROL Production Environment] (Ambiente di produzione) e (facoltativamente) [!UICONTROL Staging Environment] (Ambiente di gestione temporanea) e [!UICONTROL Development Environment] (Ambiente di sviluppo).

   ![Configurazione dell’estensione AEP Web SDK](assets/aepwebsk-extension-datastreams.png)

   Seleziona **[!UICONTROL Save]** (Salva).

Per ulteriori informazioni, consulta la sezione [Configurare l’estensione Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html).

L&#39;SDK per Web include [!UICONTROL Adobe Experience Cloud ID Service] in modo nativo, pertanto non è necessario aggiungere l&#39;estensione del servizio ID al tag.

### **Elementi dati**

Gli elementi dati sono i blocchi costitutivi per il dizionario dati (o mappa dati). Utilizza elementi dati per raccogliere, organizzare e distribuire dati in tutta la tecnologia marketing e pubblicitaria. Puoi impostare elementi dati nel tag che leggono dal livello dati e possono essere utilizzati per inviare dati ad Adobe Experience Platform.

Esistono diversi tipi di elementi dati. Devi innanzitutto impostare un elemento dati per acquisire il nome della pagina che le persone visualizzano sul tuo sito.

Per definire un elemento dati nome pagina:

1. Seleziona **[!UICONTROL Data Elements]** (Elementi dati) nella barra a sinistra.

2. Seleziona **[!UICONTROL Add Data Element]** (Aggiungi elemento dati).

3. Nella finestra di dialogo [!UICONTROL Create Data Element] (Crea elemento dati):

   - Assegna un nome all’elemento dati, ad esempio `Page Name` (Nome pagina).

   - Seleziona **[!UICONTROL Core]** dall’elenco [!UICONTROL Extension] (Estensioni).

   - Seleziona **[!UICONTROL Page Info]** (Info pagina) dall’elenco [!UICONTROL Data Element Type] (Tipo di elemento dati).

   - Seleziona **[!UICONTROL Title]** (Titolo) dall’elenco [!UICONTROL Attribute] (Attributo).

     ![Creare un elemento dati utilizzando le informazioni della pagina](assets/create-dataelement-1.png)

     In alternativa, puoi usare il valore da una variabile del livello dati, ad esempio `pageName` e il tipo di elemento dati [!UICONTROL JavaScript Variable] (Variabile JavaScript) per definire l’elemento dati.

     ![Creare un elemento dati utilizzando una variabile Javascript](assets/create-dataelement-2.png)

   - Seleziona **[!UICONTROL Save]** (Salva).

Ora immagina di voler impostare un elemento dati che faccia riferimento all’ID Experience Cloud fornito automaticamente dall’SDK per Web Adobe Experience Platform e disponibile tramite l’estensione Experience Cloud ID Service.

Per definire un elemento dati ECID:

1. Seleziona **[!UICONTROL Data Elements]** (Elementi dati) nella barra a sinistra.

2. Seleziona **[!UICONTROL Add Data Element]** (Aggiungi elemento dati).

3. Nella finestra di dialogo [!UICONTROL Create Data Element] (Crea elemento dati):

   - Assegna un nome all’elemento dati, ad esempio `ECID` (Nome pagina).

   - Seleziona **[!UICONTROL Experience Cloud ID Service]** dall’elenco [!UICONTROL Extension] (Estensioni).

   - Seleziona **[!UICONTROL ECID]** dall’elenco [!UICONTROL Data Element Type] (Tipo di elemento dati).

     ![Elemento dati ECID](assets/ecid-dataelement.png)

   - Seleziona **[!UICONTROL Save]** (Salva).

Infine, ora immagina di voler mappare uno qualsiasi degli elementi dati specifici allo schema definito in precedenza. Puoi definire un altro elemento dati che fornisce una rappresentazione dello schema XDM.

Per definire un elemento dati oggetto XDM:

1. Seleziona **[!UICONTROL Data Elements]** (Elementi dati) nella barra a sinistra.

2. Seleziona **[!UICONTROL Add Data Element]** (Aggiungi elemento dati).

3. Nella finestra di dialogo [!UICONTROL Create Data Element] (Crea elemento dati):

   - Assegna un nome all’elemento dati, ad esempio `XDM - Page View` (Nome pagina).

   - Seleziona **[!UICONTROL Adobe Experience Platform Web SDK]** dall’elenco [!UICONTROL Extension] (Estensioni).

   - Seleziona **[!UICONTROL XDM Object]** (Oggetto XDM) dall’elenco [!UICONTROL Data Element Type] (Tipo di elemento dati).

   - Seleziona la sandbox dall’elenco [!UICONTROL Sandbox].

   - Seleziona lo schema dall’elenco [!UICONTROL Schema].

   - Mappa l’attributo `identification > core > ecid` all’elemento dati ECID, definito nello schema. Seleziona l’icona del cilindro per scegliere facilmente l’elemento dati ECID dall’elenco degli elementi dati.

     ![Scegli l’elemento dati ECID](assets/pick-ecid-dataelement.png)

     ![Mappa l’elemento dati ECID](assets/map-ecid.png)


   - Mappa l’attributo `web > webPageDetails > name` all’elemento dati Page Name (Nome pagina), definito nello schema.

     ![Mappa l’elementi dati Page Name (Nome pagina)](assets/map-pagename.png)

   - Seleziona **[!UICONTROL Save]** (Salva).


### **Regole**

I tag in Adobe Experience Platform seguono un sistema basato su regole. Cercano le interazione degli utenti e i relativi dati. Quando i criteri descritti nelle tue regole vengono soddisfatti, la regola attiva l’estensione, lo script o il codice lato client identificato. Puoi utilizzare le regole per inviare dati (come un oggetto XDM) in Adobe Experience Platform utilizzando l’estensione Adobe Experience Platform Web SDK.

Per definire una regola:

1. Seleziona **[!UICONTROL Rules]** (Regole) nella barra a sinistra.

1. Seleziona **[!UICONTROL Create New Rule]** (Aggiungi elemento dati).

1. Nella finestra di dialogo [!UICONTROL Create Rule] (Crea regola):

   - Assegna un nome alla regola, ad esempio `Page View`.

   - Seleziona **[!UICONTROL + Add]** (Aggiungi) sotto [!UICONTROL Events] (Eventi).

   - Nella finestra di dialogo [!UICONTROL Event Configuration] (Configurazione evento):

      - Seleziona **[!UICONTROL Core]** dall’elenco [!UICONTROL Extension] (Estensioni)

      - Seleziona **[!UICONTROL Window Loaded]** (Finestra caricata) dall’elenco [!UICONTROL Event Type] (Estensioni)

        ![Regola - Configurazione evento](assets/event-windowloaded-pageview.png)

      - Seleziona **[!UICONTROL Keep Changes]** (Mantieni modifiche).



   - Seleziona **[!UICONTROL + Add]** (Aggiungi) sotto [!UICONTROL Actions] (Azioni).

   - Nella finestra di dialogo [!UICONTROL Action Configuration] (Configurazione evento):

      - Seleziona **[!UICONTROL Adobe Experience Platform Web SDK]** dall’elenco [!UICONTROL Extension] (Estensioni)

      - Seleziona **[!UICONTROL Send Event]** (Info pagina) dall’elenco [!UICONTROL Action Type] (Tipo di elemento dati).

      - Seleziona **[!UICONTROL web.webpagedetails.pageViews]** dall’elenco [!UICONTROL Type] (Tipo)

      - Seleziona l’icona del cilindro accanto a [!UICONTROL XDM data] (Dati XDM) e seleziona **[!UICONTROL XDM - Page View]** (XDM - Vista pagina) dall’elenco degli elementi dati.

     ![Regola - Configurazione azione](assets/action-pageview-xdm.png)

      - Seleziona **[!UICONTROL Keep Changes]** (Mantieni modifiche).

   - L’aspetto della regola dovrebbe essere il seguente:

     ![Crea regola](assets/rule-pageview.png)

1. Seleziona **[!UICONTROL Save]** (Salva).

Quanto sopra è solo un esempio di definizione di una regola che invia a Adobe Experience Platform dati XDM, contenenti valori da altri elementi di dati.

Puoi utilizzare le regole in vari modi nel tag per manipolare le variabili (utilizzando gli elementi dati).

Per ulteriori informazioni, consulta la sezione [Regole](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=it) per ulteriori informazioni.

## Creare e pubblicare il tag

Dopo aver definito elementi dati e regole, devi generare e pubblicare il tag. Quando crei una build della libreria, devi assegnarla a un ambiente. Le estensioni, le regole e gli elementi dati della build vengono quindi compilati e inseriti nell’ambiente assegnato. Ogni ambiente fornisce un codice di incorporamento univoco che consente di integrare la build assegnata nel sito.

Per generare e pubblicare il tag:

1. Seleziona **[!UICONTROL Publishing Flow]** (Flusso di pubblicazione) nella barra a sinistra.

2. Seleziona **[!UICONTROL Select a working library]** (Seleziona una libreria di lavoro) e poi **[!UICONTROL Add Library…]** (Aggiungi libreria...).

3. Nella finestra di dialogo [!UICONTROL Create Library] (Crea libreria):

   - Assegna un nome alla libreria.

   - Seleziona **[!UICONTROL Development (development)]** dall’elenco.[!UICONTROL Environment]

   - Seleziona **[!UICONTROL + Add All Changed Resources]** (Crea set di dati).

     ![Pubblica - Crea libreria](assets/create-library-aep.png)

   - Seleziona **[!UICONTROL Save & Build to Development]** (Salva e crea per lo sviluppo).

   Il tag viene salvato e generato per l’ambiente di sviluppo. Un punto verde indica la corretta compilazione del tag nell’ambiente di sviluppo.

4. È possibile selezionare **[!UICONTROL ...]** per ricreare la libreria o spostarla in un ambiente di gestione temporanea o produzione.

   ![Pubblica - Libreria di compilazione](assets/build-library.png)

I tag Adobe Experience Platform supportano flussi di lavoro di pubblicazione semplici o complessi che devono adattarsi alla distribuzione dell’SDK Web di Adobe Experience Platform.

Per ulteriori informazioni, consulta la sezione [Panoramica di pubblicazione](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=it).


## Recuperare il codice del tag

Infine, devi installare il tag sul sito web di cui desideri tenere traccia, il che implica il posizionamento di codice nel tag di intestazione del modello del sito web.

Per ottenere il codice che fa riferimento al tag:

1. Seleziona **[!UICONTROL Environments]** (Ambienti) nella barra a sinistra.

1. Dall’elenco degli ambienti, seleziona il pulsante di installazione (casella) corretto.

   Nella finestra di dialogo [!UICONTROL Web Install Instructions] (Istruzioni per l’installazione Web) seleziona il pulsante di copia accanto al codice script che dovrebbe essere simile al seguente:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Ambiente](assets/environment.png)

1. Seleziona **[!UICONTROL Close]** (Chiudi).

   Invece del codice per l’ambiente di sviluppo, potresti aver selezionato un altro ambiente (gestione temporanea, produzione) in base al punto in cui stai distribuendo l’SDK Web di Adobe Experience Platform.

   Per ulteriori informazioni, consulta la sezione [Ambienti](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=it).

1. Continua seguendo i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i [passaggi di aggiornamento generati dinamicamente](https://gigazelle.github.io/cja-ttv/).
