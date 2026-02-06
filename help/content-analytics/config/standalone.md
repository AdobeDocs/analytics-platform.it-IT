---
title: Configura Content Analytics (standalone)
description: Illustra i passaggi necessari per configurare Content Analytics (standalone)
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 35d63b7d-f35a-4a88-ae14-96724d32a931
source-git-commit: 20ead546897ad517840f95a5ec4dcd7f830afe8c
workflow-type: tm+mt
source-wordcount: '2517'
ht-degree: 5%

---

# Configurazione autonoma

>[!IMPORTANT]
>
>Questa guida alla configurazione è destinata ai clienti che hanno concesso in licenza il pacchetto Adobe Content Analytics autonomo. La guida presuppone che tu non abbia utilizzato o pianificato di utilizzare Customer Journey Analytics o qualsiasi altra applicazione Experience Platform oltre le funzionalità e le caratteristiche di Content Analytics. Consulta [Configura Content Analytics](configuration.md) se desideri configurare e utilizzare Content Analytics come parte di un&#39;implementazione Customer Journey Analytics esistente.
>

Content Analytics è concesso in licenza come prodotto standalone, ma la configurazione avviene all’interno di Experience Platform e Customer Journey Analytics. Queste piattaforme forniscono l&#39;infrastruttura di raccolta e analisi dei dati richiesta e utilizzata da Content Analytics. Questa guida fornisce tutte le istruzioni specifiche necessarie, anche se non conosci ancora Experience Platform e Customer Journey Analytics.

Prima di iniziare la configurazione di Content Analytics standalone, è necessario:

* Conoscenza di base dei concetti di analisi web, familiarità con i sistemi di gestione dei tag e conoscenze di base di JavaScript.
* Pianificare 4-6 ore per la configurazione iniziale, più tempo aggiuntivo per testare e convalidare la configurazione.

## Terminologia

Questa guida utilizza diversi termini tecnici, da Experience Platform e Customer Journey Analytics, che potresti non conoscere. Di seguito è riportata una spiegazione di questi termini (con collegamenti di riferimento) nel contesto di Content Analytics:

| Termine | Spiegazione |
|---|---|
| **Schema** | Uno [schema](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/schema/composition) è un insieme di regole che rappresentano e convalidano la struttura e il formato dei dati. A un livello avanzato, gli schemi forniscono una definizione astratta di un oggetto reale, ad esempio un evento che si verifica su un sito Web, come un clic. Descrivere i dati da includere in ogni istanza dell&#39;oggetto. |
| **Set di dati** | Un [set di dati](https://experienceleague.adobe.com/it/docs/experience-platform/catalog/datasets/overview) è un costrutto di archiviazione e gestione per una raccolta di dati, in genere una tabella, che contiene uno schema (colonne) e campi (righe). Un set di dati è simile a una tabella di database in cui ogni riga è un evento dal sito Web. |
| **Stream di dati** | Un [datastream](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/overview) rappresenta la configurazione lato server che indirizza i dati dal sito Web al set di dati corretto in Adobe Experience Platform. Un flusso di dati funge da autostrada dei dati che collega il sito allo storage. |
| **Tag** | [I tag](https://experienceleague.adobe.com/it/docs/experience-platform/tags/home) in Experience Platform sono la soluzione Adobe di nuova generazione per la gestione dei tag. I tag offrono ai clienti un modo semplice di implementare e gestire i tag di analisi, marketing e annunci pubblicitari necessari per fornire ai clienti esperienze personalizzate. In Content Analytics, il sistema di gestione dei tag di Adobe consente di distribuire il codice di tracciamento sul sito web senza dover modificare ogni pagina in modo simile. La funzionalità Tag è simile a quella di Google Tag Manager. |
| **Sandbox** | Experience Platform fornisce [sandbox](https://experienceleague.adobe.com/it/docs/experience-platform/sandbox/home) che suddividono una singola istanza Experience Platform in ambienti virtuali separati, utili per le attività di sviluppo e aggiornamento delle applicazioni di esperienza digitale. Content Analytics utilizza in genere la sandbox *Produzione*. |
| **Connessione** | [Le connessioni](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-connections/overview) definiscono quali set di dati di Experience Platform vengono acquisiti. Una connessione definisce il collegamento tra il set di dati (dove i dati vengono memorizzati in AEP) e Customer Journey Analytics (dove vengono analizzati). Una connessione rende i dati raccolti disponibili per il reporting. |
| **Visualizzazione dati** | Una [visualizzazione dati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/data-views) è un contenitore che consente di determinare come interpretare i dati di una connessione. Una visualizzazione dati specifica tutte le dimensioni e le metriche disponibili per il reporting. Una visualizzazione dati è simile a una configurazione che determina le righe e le colonne disponibili per l’analisi. |
| **Analysis Workspace** | [Analysis Workspace](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/home) è un&#39;interfaccia browser con funzionalità di trascinamento della selezione che consente di creare report e analisi di Content Analytics. |
| **Esperienza** | In Content Analytics, un&#39;[esperienza](https://experienceleague.adobe.com/it/docs/analytics-platform/using/content-analytics/content-analytics#terminology) si riferisce a tutto il contenuto di testo in una pagina web che può essere acquisito e analizzato in base all&#39;URL della pagina. |
| **Risorsa** | In Content Analytics, una [risorsa](https://experienceleague.adobe.com/it/docs/analytics-platform/using/content-analytics/content-analytics#terminology) è un contenuto singolo e univoco, come un&#39;immagine. |


## Panoramica sulla configurazione

Questa configurazione ti guida nella configurazione di tutte le applicazioni che richiedono un&#39;implementazione di Content Analytics **autonoma** funzionante. È possibile dividere l&#39;impostazione in tre fasi, in cui ciascuna fase si basa sulla precedente:

**Fase 1** - [Prepara l&#39;ambiente](#prepare-your-environment). In questa fase, puoi impostare le autorizzazioni utente e verificare l’infrastruttura dati. Senza queste autorizzazioni e la struttura dati appropriate, non puoi completare i passaggi rimanenti. Le fasi previste sono le seguenti:

1. **Configura il controllo degli accessi e le autorizzazioni** per supportare la configurazione e l&#39;implementazione di Content Analytics.
1. **Imposta uno schema e un set di dati** per definire il modello (schema) dei dati da cui vuoi raccogliere informazioni di analisi dei contenuti e dove raccogliere tali dati (set di dati).

**Fase 2** - [Configurare la raccolta dati](#configure-data-collection). In questa fase, crei la pipeline che acquisisce i dati del contenuto dal sito web. Quindi, Content Analytics sa quali contenuti i visitatori interagiscono con i tuoi contenuti.

1. **Imposta un flusso di dati** per configurare il modo in cui i dati raccolti vengono instradati al set di dati.
1. **Utilizza i tag del sito Web** per configurare regole ed elementi dati in base ai dati presenti nel livello dati del tuo sito Web e per assicurarti che i dati vengano inviati allo stream di dati configurato.
1. **Distribuisci** in un ambiente di test **e convalida** la raccolta dati prima di pubblicarla in un ambiente di produzione.

**Fase 3** - [Configura reporting](#set-up-reporting). In questa fase, rendi i dati raccolti disponibili per l’analisi nei rapporti. In questo modo è possibile ottenere da Content Analytics le informazioni necessarie sulle prestazioni dei contenuti.

1. **Configura una connessione** al set di dati.
1. **Configura una visualizzazione dati** per definire metriche e dimensioni.
1. **Configurare e implementare Content Analytics**.
1. **Configura un progetto** per creare report e visualizzazioni di Content Analytics.


## Preparare l’ambiente

In questa fase, puoi impostare le autorizzazioni utente e verificare l’infrastruttura dati.

### Configurare il controllo di accesso e le autorizzazioni

In questa sezione vengono documentati gli accessi necessari ai prodotti, ai profili di prodotto e le autorizzazioni necessarie per configurare e configurare Content Analytics standalone. Anche se sei interessato solo alle funzionalità di Content Analytics, affinché tali funzionalità funzionino correttamente devi comunque disporre dell’accesso e delle autorizzazioni per altri prodotti Experience Platform.

#### Controllo degli accessi

Il controllo degli accessi determina se è consentito l’accesso a un prodotto Experience Platform.

Per poter essere aggiunto come amministratore per un prodotto o un profilo di prodotto, devi essere un amministratore di sistema o un amministratore di prodotto. Un amministratore di prodotto può aggiungerti come amministratore solo per il prodotto amministrato (profilo); un amministratore di sistema può aggiungere amministratori di prodotto a qualsiasi prodotto (profilo).

>[!BEGINSHADEBOX]

Vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Gestire gli utenti per un profilo di prodotto](https://video.tv.adobe.com/v/333860/?quality=12&learn=on){target="_blank"} per un video dimostrativo.


>[!ENDSHADEBOX]

Per utilizzare Content Analytics in modo autonomo, è necessario essere amministratore di prodotto per i seguenti prodotti e profili di prodotto:

* Adobe Experience Platform
   * AEP-Default-All-Users (profilo predefinito per l’accesso alla sandbox di produzione)

* Raccolta dati di Adobe Experience Platform
   * Accesso predefinito a tutti i tipi di raccolta dati

* Adobe Experience Platform Privacy Service

* Customer Journey Analytics (personalizzato)
   * Customer Journey Analytics (o qualsiasi altro profilo di prodotto con provisioning predefinito)

Puoi definire l’accesso come amministratore del prodotto tramite Admin Console:

1. Accedi a [Admin Console](https://adminconsole.adobe.com).
1. Seleziona **[!UICONTROL Prodotti]**.
1. Seleziona il prodotto specifico.
1. Selezionare la scheda **[!UICONTROL Amministratori]**.
1. Seleziona **[!UICONTROL Aggiungi amministratore]** per aggiungere un amministratore al prodotto.
1. Immetti uno o più nomi utente o e-mail nella finestra di dialogo **[!UICONTROL Aggiungi amministratori prodotto]**. Seleziona **[!UICONTROL Salva]** per salvare.


Puoi definire l’accesso amministratore del profilo di prodotto tramite Admin Console:

1. Accedi a [Admin Console](https://adminconsole.adobe.com).
1. Seleziona **[!UICONTROL Prodotti]**.
1. Seleziona il prodotto specifico. Assicurati di avere già accesso come amministratore del prodotto.
1. Seleziona **[!UICONTROL Profili di prodotto]**.
1. Seleziona il profilo di prodotto specifico.
1. Selezionare la scheda **[!UICONTROL Amministratori]**.
1. Seleziona **[!UICONTROL Aggiungi amministratore]** per aggiungere un amministratore al profilo di prodotto.
1. Immetti uno o più nomi utente o e-mail nella finestra di dialogo **[!UICONTROL Aggiungi amministratori del profilo di prodotto]**. Seleziona **[!UICONTROL Salva]** per salvare.


#### Autorizzazioni

Le autorizzazioni definiscono cosa puoi fare all’interno di un prodotto una volta che hai accesso al prodotto.

È possibile definire le autorizzazioni per Experience Platform nell&#39;interfaccia [!UICONTROL Autorizzazioni] e utilizzare il controllo degli accessi basato su attributi. Per Customer Journey Analytics, si definiscono le autorizzazioni tramite [!UICONTROL Admin Console].

##### Experience Platform

L&#39;interfaccia [!UICONTROL Autorizzazioni] in Experience Platform si basa sulla definizione di un ruolo. Un ruolo è una raccolta di autorizzazioni basate su risorse. In un nuovo ambiente con provisioning sono disponibili due ruoli predefiniti: **[!UICONTROL Default Production All Access]** e **[!UICONTROL Sandbox Administrators]**.

Con Content Analytics, devi verificare se le seguenti risorse e autorizzazioni associate vengono aggiunte a questi ruoli:

* Ruolo predefinito Tutti gli accessi alla produzione

   * Raccolta dati
      * Visualizzare gli stream di dati
      * Gestire gli stream di dati

   * Gestione dati
      * Visualizzare i set di dati
      * Gestione set di dati

   * Modellazione dati
      * Visualizzare gli schemi
      * Gestire gli schemi
      * Gestire i metadati di identità


* Ruolo Amministratori sandbox

   * Sandbox
      * Prod
      * (qualsiasi altra sandbox che desideri utilizzare per Content Analytics)

   * Amministrazione sandbox
      * Gestisci pacchetti
      * Gestire le sandbox
      * Ripristina sandbox
      * Visualizza Sandbox


Nell’interfaccia Autorizzazioni è possibile verificare sia i ruoli che le autorizzazioni associate. E quali utenti appartengono al ruolo.

1. Accedi ad Experience Platform per la tua organizzazione.
1. Nella schermata iniziale, in **[!UICONTROL Accesso rapido]**, seleziona **[!UICONTROL Visualizza tutto]**.
1. Abilita il pin ![PinOn](/help/assets/icons/PinOn.svg) per **[!UICONTROL Autorizzazioni]**, quindi **[!UICONTROL Autorizzazioni]** diventa disponibile in **[!UICONTROL Accesso rapido]** per utilizzi futuri.
1. Seleziona **[!UICONTROL Autorizzazioni]**.
1. Seleziona ![Utente](/help/assets/icons/User.svg) **[!UICONTROL Ruoli]**.
1. Selezionare il ruolo specifico che si desidera verificare, ad esempio **[!UICONTROL Default Production All Access]**. Seleziona **[!UICONTROL Visualizza tutto]** per visualizzare tutte le autorizzazioni.
1. Nella schermata **[!UICONTROL Dettagli]**:
   1. Verifica le **[!UICONTROL Risorse]** elencate in **[!UICONTROL Autorizzazioni]**.
   1. Verifica i nomi delle sandbox in **[!UICONTROL Sandbox]**.

   Per apportare aggiornamenti, selezionare ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Modifica]**.
   1. Per aggiungere una risorsa mancante, seleziona **[!UICONTROL Nome risorsa]** ![Aggiungi](/help/assets/icons/Add.svg) dalla barra a sinistra **[!UICONTROL Risorse]** > **[!UICONTROL Adobe Experience Platform]**.
   1. Per aggiungere un&#39;autorizzazione mancante, selezionare ![ChevronDown](/help/assets/icons/ChevronDown.svg) all&#39;interno della risorsa per la quale manca l&#39;autorizzazione nel pannello principale, quindi selezionare l&#39;autorizzazione mancante.

      ![Interfaccia autorizzazioni](/help/content-analytics/assets/aep-permissions-ui.png)

   Seleziona **[!UICONTROL Salva]** per salvare eventuali aggiornamenti.

1. Nella schermata Utenti o Gruppi di utenti:
   1. Verifica che singoli utenti o gruppi di utenti giusti facciano parte di questo ruolo.
      1. Seleziona ![UserAdd](/help/assets/icons/UserAdd.svg) Add Users in Users (Aggiungi utenti in Utenti) per aggiungere singoli utenti definiti in Admin Console.
      1. Seleziona ![Aggiungi](/help/assets/icons/Add.svg) Aggiungi gruppi nei gruppi di utenti per aggiungere gruppi di utenti definiti in Admin Console.


##### Customer Journey Analytics

Customer Journey Analytics non supporta il controllo degli accessi basato su attributi. Per specificare le autorizzazioni, utilizza Admin Console.

Con Content Analytics, devi verificare se sono incluse le seguenti autorizzazioni del profilo di prodotto Customer Journey Analytics:

* Visualizzazioni dati
   * Tutte le visualizzazioni dati disponibili.

* Strumenti di reporting
   * Accesso guidato alle analisi?
   * Creazione di metriche calcolate
   * Creazione di segmenti
   * Accesso a Labs?
   * Creazione di annotazioni
   * Creazione di pubblico?
   * Visualizzazione del pubblico?
   * Accesso a registri di audit
   * Condividi i collegamenti al progetto con chiunque
   * Previsioni
   * Assistente IA: conoscenza del prodotto
   * Agente Data Insights
   * Didascalie intelligenti
   * Narrazione dei dati?

* Strumenti di visualizzazione dati
   * Esportazione tabella completa?
   * Estensione CJA BI?

Per verificare e aggiornare queste autorizzazioni per Customer Journey Analytics:

1. Accedi a [Admin Console](https://adminconsole.adobe.com).
1. Seleziona **[!UICONTROL Prodotti]**.
1. Selezionare il prodotto **[!UICONTROL Customer Journey Analytics]**.
1. Seleziona **[!UICONTROL Profili di prodotto]**.
1. Seleziona il profilo di prodotto con provisioning predefinito disponibile per Customer Journey Analytics. Ad esempio: **[!UICONTROL Customer Journey Analytics]**.
1. Nella schermata del profilo di prodotto, seleziona **[!UICONTROL Autorizzazioni]**.
1. Seleziona uno dei pulsanti ![Modifica](/help/assets/icons/Edit.svg) per modificare le autorizzazioni. Nella finestra di dialogo **[!UICONTROL Modifica autorizzazioni per Customer Journey Analytics]**:

   ![Interfaccia utente autorizzazioni CJA](../assets/cja-permissions-ui.png)

   1. Seleziona **[!UICONTROL Visualizzazioni dati]** e abilita **[!UICONTROL Inclusione automatica: il]**. Questa opzione garantisce che tutte le visualizzazioni dati facciano automaticamente parte degli **[!UICONTROL elementi di autorizzazione inclusi]**.
   1. Seleziona **[!UICONTROL Strumenti di reporting]** e assicurati che tutte le autorizzazioni elencate sopra facciano parte degli **[!UICONTROL elementi di autorizzazione inclusi]**.
   1. Seleziona **[!UICONTROL Strumenti visualizzazione dati]** e assicurati che tutte le autorizzazioni elencate in precedenza facciano parte degli **[!UICONTROL elementi di autorizzazione inclusi]**.

   Seleziona **[!UICONTROL Salva]**.


### Configurare schema e set di dati

Per raccogliere i dati dal sito web, in base alle informazioni di Content Analytics, devi innanzitutto definire il tipo di dati da raccogliere. E anche come vengono memorizzati i dati. Entrambi i concetti sono illustrati in [Configurare uno schema e un set di dati](/help/data-ingestion/aepwebsdk.md#set-up-a-schema-and-dataset) nella [Guida rapida all&#39;acquisizione di dati tramite Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


## Configurare la raccolta dati

In questa fase crei la pipeline che acquisisce i dati del contenuto dal sito web.

### Configurare un flusso di dati

Hai definito quali dati raccogliere e come memorizzarli. Il passaggio successivo consiste nel garantire che i dati raccolti dal sito web vengano instradati al set di dati. È necessario impostare e configurare un flusso di dati, come illustrato in [Configurare un flusso di dati](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream) nella [Guida rapida all&#39;acquisizione di dati tramite Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


### Usare i tag

Hai definito quali dati raccogliere (schema), come memorizzarli (set di dati) e come i dati raccolti dal sito web vengono instradati al set di dati (flusso di dati). Come passaggio successivo, devi assegnare un tag al sito web per configurare regole ed elementi dati in base ai dati presenti nel livello dati sul sito web. Assegnare tag al sito web assicura che i dati vengano inviati allo stream di dati configurato. L&#39;assegnazione di tag al sito Web con l&#39;ausilio di Tag è illustrata in [Usa tag](/help/data-ingestion/aepwebsdk.md#use-tags) nella [Guida rapida all&#39;acquisizione di dati tramite Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


### Distribuire e convalidare

Ora puoi distribuire il codice nella versione di sviluppo del tuo sito Web all’interno del tag `<head>`. Una volta implementato, il sito web inizia a raccogliere dati in Adobe Experience Platform. Tali dati sono quindi soggetti a Content Analytics.

Convalidare l’implementazione, correggerla se necessario e, una volta corretta, distribuirla nell’ambiente di staging e produzione utilizzando la funzione del flusso di lavoro di pubblicazione dei tag


## Configurare la generazione di rapporti

In questa fase rendi disponibili i dati raccolti per l’analisi nei rapporti.

### Configurare una connessione al set di dati

Per creare rapporti sui dati raccolti e configurare tali dati per Content Analytics, è necessario impostare una connessione in Customer Journey Analytics. La connessione si connette al set di dati che contiene i dati raccolti. Per informazioni su come impostare una connessione, vedere [Configurare una connessione](../../data-ingestion/aepwebsdk.md#set-up-a-connection) nella [Guida rapida all&#39;acquisizione dei dati tramite Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


### Configurare una visualizzazione dati

L’ultimo passaggio prima di poter configurare Content Analytics è la definizione di una visualizzazione dati. Una visualizzazione dati è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati da una connessione. Una visualizzazione dati consente di definire metriche e dimensioni dai dati di uno o più set di dati a cui è connesso Customer Journey Analytics. Per informazioni su come impostare una visualizzazione dati, vedere [Configurare una visualizzazione dati](/help/data-ingestion/aepwebsdk.md#set-up-a-data-view) nella [Guida rapida all&#39;acquisizione di dati tramite Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


### Configurare Content Analytics

Ora disponi di tutto il necessario per configurare Content Analytics.

#### Configurazione guidata

Utilizza la [configurazione guidata](guided.md) e seleziona la visualizzazione dati creata nell&#39;ambito del passaggio [Imposta una visualizzazione dati](#set-up-a-data-view). Questa selezione garantisce che Content Analytics sia configurato e implementato in aggiunta ai dati raccolti dal sito Web.

Tenere presente che la configurazione guidata configura i seguenti oggetti Content Analytics specifici aggiuntivi:

* **Set di dati**, configurato automaticamente per gli eventi di Content Analytics. Questo set di dati utilizza uno schema Content Analytics specifico già creato e disponibile.
* **Datastream**, configurato automaticamente per inviare in streaming gli eventi Content Analytics nel set di dati Content Analytics.
* **Proprietà Tags**, impostata automaticamente e configurata con l&#39;estensione Content Analytics. Questa proprietà Tags garantisce che il sito web invii dati Content Analytics al flusso di dati Content Analytics e al set di dati Content Analytics.

  >[!IMPORTANT]
  >
  >Accertati di selezionare l&#39;opzione per creare una proprietà Nuovi tag nel passaggio [Raccolta dati](guided.md#new-configuration-1) della procedura guidata.
  >


#### Configurazione manuale

Per implementare Content Analytics per il sito Web, devi pubblicare la proprietà Tag Content Analytics [manualmente](manual.md).


### Configurare un progetto

Configura un progetto in Customer Journey Analytics per creare [report e visualizzazioni di Content Analytics](/help/content-analytics/report/report.md). In alternativa, è possibile utilizzare un [modello Content Analytics](/help/content-analytics/report/report.md#template) per iniziare.
