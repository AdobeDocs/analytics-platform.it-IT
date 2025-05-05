---
title: Panoramica sulla segmentazione
description: Scopri i segmenti utilizzati e come creare un segmento semplice.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: 85a22d1e57925f0512ce0cc658cfba1008339d91
workflow-type: tm+mt
source-wordcount: '1472'
ht-degree: 5%

---


# Panoramica sulla segmentazione

Customer Journey Analytics ti consente di creare, gestire, condividere e applicare segmenti di pubblico potenti e mirati ai tuoi rapporti. I segmenti ti consentono di identificare sottoinsiemi di persone, sessioni o eventi in base a caratteristiche o interazioni. I segmenti sono progettati come informazioni codificate sul pubblico che puoi creare in base alle tue esigenze specifiche e che puoi verificare, modificare e condividere con altri membri del gruppo.

I segmenti possono essere basati su:

- attributi (tipo di browser, dispositivo, numero di visite, paese, genere),
- interazioni (campagne, ricerca di parole chiave, motore di ricerca),
- uscite e entrate (persone da Facebook, una pagina di destinazione definita, dominio di riferimento, evento recinto geografico),
- variabili personalizzate (campo modulo, categorie definite, ID cliente),
- e altri criteri.

Consulta [Creare segmenti](/help/components/filters/create-filters.md) per le varie opzioni disponibili per la creazione dei segmenti. Generare, modificare e salvare la definizione di un segmento nel [Generatore di segmenti](filter-builder.md). In alternativa, puoi creare segmenti rapidi utilizzando [Generatore di segmenti rapidi](quick-filters.md). È inoltre possibile generare segmenti dalle visualizzazioni in Workspace, ad esempio utilizzando la visualizzazione [Abbandono](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu).

Utilizza il [Gestore segmenti](manage-filters.md) per gestire i segmenti.

## Pianificare segmenti

In particolare, in qualità di amministratore, la corretta pianificazione dei segmenti migliora le possibilità di utilizzo dei segmenti. Quando pianifichi i segmenti, tieni presente quanto segue:

- **Pubblico**: chi utilizzerà i tuoi segmenti? Assicurati di fornire una buona descrizione del segmento in modo che il pubblico comprenda:
   - A cosa serve questo segmento?

   - Quando dovrei usare questo segmento?

- **Ambito**: quale [Contenitore di segmenti](#filter-containers) rappresenta meglio i dati che stai cercando? Utilizza il contenitore più piccolo possibile.

- **Componenti**: decide quali componenti includere nella definizione del segmento e in base a quali valori le condizioni devono essere convalidate.

- **Processo**: è consigliabile un processo di approvazione per i segmenti. In Customer Journey Analytics non è presente alcun flusso di lavoro di approvazione, ma è comunque possibile organizzare un processo per determinare se approvare o meno un segmento.

- **Modularità**: definisci i segmenti pensando alla modularità. Gli utenti dei segmenti dovrebbero essere in grado di [sovrapporre segmenti](filter-builder.md#stack-filters) in modo semplice per creare nuovi segmenti efficaci.


## Tipi di segmenti

Puoi creare tre tipi di segmenti:

### Segmenti rapidi

I segmenti rapidi consentono di esplorare facilmente i dati all&#39;interno di un determinato progetto Workspace, senza la necessità di creare un segmento nel [Generatore di segmenti](/help/components/filters/create-filters.md). Puoi definire il segmento direttamente nell’interfaccia di Workspace. Per ulteriori informazioni, consulta [Segmenti rapidi](quick-filters.md).

### Segmenti regolari

I segmenti regolari ti consentono di identificare i dati (persone, sessioni, eventi) in base a una o più condizioni. Se disponi di più di una condizione, puoi utilizzare operatori logici come And e Or per definire ulteriormente il segmento. Puoi utilizzare i contenitori per raggruppare le condizioni e creare segmenti più complessi. Per ulteriori informazioni, consulta [Generatore di segmenti](filter-builder.md).

### Segmenti sequenziali

>[!IMPORTANT]
>
>Per creare segmenti sequenziali cross-channel è necessario disporre del pacchetto **Select**. In caso di dubbi sul pacchetto di Customer Journey Analytics di cui disponi, contatta l’amministratore.

I segmenti sequenziali ti consentono di identificare dati (persone, sessioni, eventi) in base alla navigazione (visualizzazioni di pagina nel sito, interazioni con scene nell’app mobile o utilizzo di un menu su un set-top box). I segmenti sequenziali ti consentono di identificare, ad esempio, cosa piace a una persona e cosa evita. Per definire un segmento sequenziale si utilizza l’operatore logico Then. Per ulteriori informazioni, consulta [Segmenti sequenziali](seg-sequential-build.md).


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Contenitori di segmenti {#containers}

I segmenti si basano su una gerarchia a livello di persona, sessione ed evento che utilizza un modello di contenitore nidificato. I contenitori nidificati ti consentono di definire le condizioni tra e all’interno dei contenitori.


<table style="table-layout: fixed; border: none;" width="100%">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Persona</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Sessione</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Evento</td>
</tr>
</table>

>[!NOTE]
>
>Per gli utenti di Adobe Analytics:
> 
> - Il contenitore **Persona** è noto in Adobe Analytics come contenitore **Visitatore**.
> - Il contenitore **Session** è noto in Adobe Analytics come contenitore **Visit**.
> - Il contenitore **Event** è noto in Adobe Analytics come contenitore **Hit**.
>

Un segmento imposta le condizioni per segmentare persone, sessioni o eventi in base alle condizioni. Ad esempio, le condizioni per segmentare le persone si basano sulle caratteristiche delle persone e sulle caratteristiche di navigazione. Per suddividere ulteriormente i dati, puoi segmentare su sessioni specifiche, eventi di visualizzazione della pagina, tocchi a schermo, scelte di menu su un set-top box e altro ancora. Puoi anche segmentare gli attributi che hai acquisito da un sistema CRM o fedeltà. [Generatore di segmenti](/help/components/filters/filter-builder.md) fornisce una semplice interfaccia per generare questi sottoinsiemi e applicare condizioni in contenitori Persona, Sessione o Evento nidificati e gerarchici.

L&#39;architettura del contenitore utilizzata nel generatore di segmenti [&#128279;](/help/components/filters/filter-builder.md) definisce Persona come il contenitore più esterno. Questo contenitore contiene dati generali specifici della persona in più sessioni ed eventi come visualizzazioni di pagina, schermate di app mobili o schermate di menu su un set-top box. Un contenitore Sessione nidificato consente di impostare regole per suddividere i dati della persona in base alle sessioni. Un contenitore Evento nidificato consente di suddividere le informazioni sulla persona in base alle singole interazioni. Ogni contenitore consente di generare rapporti sulla cronologia di una persona e sulle sue interazioni suddivise per sessioni o di suddividere singoli eventi.

### Contenitore Persona

Il contenitore Persona include ogni sessione e ogni evento per le persone che si qualificano per la condizione specificata nel contenitore. Quando definisci un segmento con una condizione semplice come `Page Name equals Checkout`, il contenitore Persona viene risolto in:

- Tutte le persone che hanno visitato la pagina con il nome `Checkout`.
- Tutte le sessioni per queste persone.
- Tutti i dati evento per queste persone.

Poiché è il contenitore definito in modo più ampio, i rapporti generati a livello del contenitore Persona restituiscono eventi e sessioni per tutte le persone idonee per il segmento. Il contenitore Persona è quello più suscettibile a modifiche in base a intervalli di date definiti.
I contenitori Persona possono includere valori basati sulla cronologia generale di una persona:

- Giorni precedenti al primo acquisto.
- Pagina iniziale originale o schermata iniziale dell’app mobile.
- Domini di riferimento originali.

### Contenitore Sessione

Il contenitore Sessione consente di identificare le interazioni con pagine o con app mobili, campagne o conversioni per una sessione specifica. Il contenitore Sessione è il contenitore più comunemente utilizzato perché acquisisce i comportamenti per l’intera sessione una volta soddisfatta la regola. Il contenitore Sessione consente inoltre di definire quali sessioni includere o escludere nella creazione e applicazione di un segmento.  Quando definisci un segmento con una condizione semplice come `Page Name equals Checkout`, il contenitore Sessione viene risolto in:

- Tutte le sessioni in cui viene visitata una pagina denominata `Checkout`.
- Tutti i dati evento per tali sessioni.

Il contenitore di sessione può essere utile per rispondere alle seguenti domande:

- Quante sessioni hanno coinvolto sia origini dati del web che del call center?
- Quali pagine hanno contribuito alla conversione in una vendita?

I contenitori Sessione includono valori basati su eventi per sessione:

- Tipo di sessione.
- Pagina di ingresso.
- Frequenza di ritorno.
- Metriche di partecipazione.
- Metriche allocate linearmente.

Le visualizzazioni dati in Customer Journey Analytics consentono di determinare la durata di una sessione e quando crearne una nuova. Ad esempio, puoi definire una nuova sessione di app mobile in base a ogni avvio dell’app mobile da parte di un utente. Per ulteriori informazioni, vedere [Impostazioni sessione](/help/data-views/session-settings.md).

### Contenitore Evento

Il contenitore Evento definisce la pagina, l’app mobile o altri tipi di eventi che desideri includere o escludere da un segmento. È il contenitore più stretto disponibile. Ti consente di identificare clic specifici, visualizzazione pagina e pulsanti su pulsante in un’app mobile in cui una condizione è vera. Il contenitore Evento consente di visualizzare un singolo codice di tracciamento o di isolare il comportamento all’interno di una particolare area dell’app mobile. Puoi anche individuare un valore specifico quando si verifica un’azione, ad esempio il canale di marketing al momento di un ordine. Quando definisci un segmento con una condizione semplice come `Page Name equals Checkout`, il contenitore Evento viene risolto in:

- Tutti gli eventi di visualizzazione pagina in cui il nome della pagina è uguale a `Checkout`.

I contenitori Evento includono raggruppamenti di singole pagine basati su valori per:

- Prodotti
- Proprietà elenco
- Dimensioni elenco
- Dimensioni del merchandising (nel contesto degli eventi)



### contenitori B2B

[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}

Se hai accesso a [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md), sono disponibili altri contenitori da utilizzare nei segmenti. Ulteriori dettagli sull&#39;utilizzo di questi contenitori aggiuntivi sono disponibili in [Concetti e funzionalità B2B](/help/getting-started/cja-b2b-concepts-features.md).


### Contenitore gruppo logico

Gruppo logico consente di raggruppare le condizioni in un singolo punto di controllo del segmento sequenziale. Come parte della sequenza, la logica definita nel contenitore identificato come [!UICONTROL Logic Group] viene valutata dopo qualsiasi punto di controllo sequenziale precedente e prima di qualsiasi punto di controllo sequenziale successivo. Per ulteriori informazioni, vedere [Gruppo logico](seg-sequential-build.md#logic-group).

### Nidificare i contenitori

Quando crei contenitori all’interno di altri contenitori, in realtà stai creando un segmento all’interno di un segmento. Ai contenitori nidificati viene applicata la logica seguente:

1. Determina i dati inclusi utilizzando il contenitore più esterno. Eventuali dati che non corrispondono a questa regola esterna vengono scartati nel rapporto.
2. Applica la definizione del segmento nidificato ai dati rimanenti. La definizione del segmento nidificato NON si applica ai dati eliminati dalla prima definizione.
3. Ripeti l’operazione fino al completamento del calcolo di tutte le definizioni dei segmenti dei contenitori nidificati. I dati rimanenti vengono quindi inclusi nel risultato e utilizzati per il reporting.

>[!NOTE]
>
>Quando nidificate un segmento all’interno di un segmento (ad esempio, trascinate un segmento dal pannello Componenti nella definizione del segmento), viene creato un contenitore con una copia (non un riferimento) della definizione del segmento trascinato.

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box segment template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Segment Name | Description |
| --- | --- |
| All Data | All Data is a required segment that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[Creare un segmento](create-filters.md)
>[Generatore di segmenti](filter-builder.md)
>[Segmenti rapidi](quick-filters.md)
>[Segmenti sequenziali](seg-sequential-build.md)
>[Gestisci segmenti](manage-filters.md)
>
