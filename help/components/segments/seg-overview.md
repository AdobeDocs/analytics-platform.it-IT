---
title: Panoramica sulla segmentazione
description: Informazioni sui segmenti che vengono utilizzati e su come creare un segmento semplice.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1472'
ht-degree: 99%

---


# Panoramica sulla segmentazione

Customer Journey Analytics consente di generare, gestire, condividere e applicare ai rapporti segmenti di pubblico potenti e specifici. I segmenti consentono di identificare sottoinsiemi di persone, sessioni o eventi in base a caratteristiche o interazioni. I segmenti sono progettati come insight sul pubblico codificati che puoi generare in base alle tue esigenze specifiche e quindi verificare, modificare e condividere con altri membri del gruppo.

I segmenti possono essere basati su:

- attributi (tipo di browser, dispositivo, numero di visite, paese, genere);
- interazioni (campagne, ricerca di parole chiave, motore di ricerca);
- uscite ed entrate (persone da Facebook, una pagina di destinazione definita, un dominio di riferimento, un evento di geofence);
- variabili personalizzate (campo modulo, categorie definite, ID cliente);
- e altri criteri.

Per le varie opzioni disponibili per la creazione di annotazioni, consulta [Creare i segmenti](/help/components/segments/seg-create.md). Quindi, crea, modifica e salva la definizione di un segmento nel [Generatore di segmenti](seg-builder.md). In alternativa, puoi creare segmenti rapidi utilizzando il [Generatore di segmenti rapidi](seg-quick.md). È possibile inoltre generare segmenti dalle visualizzazioni in Workspace, ad esempio utilizzando la visualizzazione [Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu) (Abbandono).

Per gestire i segmenti, utilizza la funzione [Gestione segmenti](seg-manage.md).

## Pianificare i segmenti

In qualità di amministratore, la corretta pianificazione di segmenti è particolarmente importante per migliorare le possibilità di utilizzo degli stessi. Quando pianifichi dei segmenti rapidi, considera quanto segue:

- **Pubblico**: chi utilizzerà i tuoi segmenti? Assicurati di fornire una buona descrizione dei segmenti in modo che il tuo pubblico possa comprenderli:
   - A cosa serve questo segmento?

   - Quando dovrei usare questo segmento?

- **Ambito**: quale [Contenitore di segmenti](#segment-containers) rappresenta meglio i dati che ti interessano? Utilizza il contenitore più piccolo possibile.

- **Componenti**: decidi quali componenti includere nella definizione del segmento e in base a quali valori le condizioni devono essere convalidate.

- **Processo**: considera un processo di approvazione per i segmenti. In Customer Journey Analytics non è presente alcun flusso di lavoro di approvazione, ma è comunque possibile organizzare un processo per determinare se approvare o meno un segmento.

- **Modularità**: definisci i segmenti in modo che possano offrire modularità. Chi userà i segmenti dovrà essere in grado di [sovrapporre segmenti](seg-builder.md#stack-filters) con facilità per creare nuovi segmenti efficaci.


## Tipi di segmenti

Puoi creare tre tipi di segmenti:

### Segmenti rapidi

I segmenti rapidi consentono di esplorare facilmente i dati all’interno di un determinato progetto in Workspace senza la necessità di creare un segmento nel [Generatore di segmenti](/help/components/segments/seg-create.md). Il segmento viene definito direttamente nell’interfaccia di Workspace. Per ulteriori informazioni, consulta [Segmenti rapidi](seg-quick.md).

### Segmenti regolari

I segmenti regolari consentono di identificare i dati (persone, sessioni, eventi) in base a una o più condizioni. Se disponi di più condizioni, utilizza operatori logici come E e Oppure per definire ulteriormente il segmento. Puoi utilizzare i contenitori per raggruppare le condizioni e generare segmenti più complessi. Per ulteriori informazioni, consulta [Generatore di segmenti](seg-builder.md).

### Segmenti sequenziali

>[!IMPORTANT]
>
>Per creare segmenti sequenziali cross-channel devi disporre del pacchetto **Select**. In caso di dubbi sul pacchetto di Customer Journey Analytics di cui disponi, contatta l’amministratore.

I segmenti sequenziali consentono di identificare dati (persone, sessioni, eventi) in base alla navigazione (visualizzazioni di pagine nel sito, interazioni con scene nell’app mobile o utilizzo di un menu su un set top box). I segmenti sequenziali consentono di identificare, ad esempio, le preferenze di una persona e i contenuti che invece evita. Per definire un segmento sequenziale, utilizza l’operatore logico Allora. Per ulteriori informazioni, consulta [Segmenti sequenziali](seg-sequential-build.md).


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Contenitori di segmenti {#containers}

I segmenti si basano su una gerarchia a livello di Persona, Sessione ed Evento che utilizza un modello di contenitori nidificati. I contenitori nidificati consentono di definire le condizioni tra e all’interno dei contenitori.


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
> - Il contenitore **Persona** è noto in Adobe Analytics come il contenitore **Visitatore**.
> - Il contenitore **Sessione** è noto in Adobe Analytics come contenitore **Visita**.
> - Il contenitore **Evento** è noto in Adobe Analytics come contenitore **Hit**.
>

Un segmento imposta le condizioni in base alle quali segmentare persone, sessioni o eventi. Ad esempio, le condizioni per segmentare le persone si basano sulle caratteristiche della persona e della navigazione. Per suddividere ulteriormente i dati, puoi segmentare in base a particolari sessioni, eventi di visualizzazione di pagina, tocchi a schermo, scelte di menu su un set top box e altro ancora. Puoi anche segmentare in base agli attributi acquisiti da un sistema fedeltà o CRM. Il [Generatore di segmenti](/help/components/segments/seg-builder.md) fornisce un’interfaccia semplice per generare questi sottoinsiemi e applicare le condizioni in contenitori Persona, Sessione o Evento nidificati e gerarchici.

Nell’architettura dei contenitori utilizzata nel [generatore di segmenti](/help/components/segments/seg-builder.md), il contenitore Persona è quello più esterno. Questo contenitore contiene dati specifici della persona da più sessioni ed eventi come visualizzazioni di pagina, schermate di app mobili o schermate di menu su un set top box. Un contenitore Sessione nidificato consente di impostare le regole secondo cui suddividere i dati della persona in base alle sessioni. Un contenitore Evento nidificato consente di suddividere le informazioni sulla persona in base alle singole interazioni. Ogni contenitore consente di generare rapporti sulla cronologia di una persona, sulle sue interazioni suddivise per sessioni o di suddividere singoli eventi.

### Contenitore Persona

Il contenitore Persona include ogni sessione e ogni evento per le persone idonee per la condizione specificata nel contenitore. Quando definisci un segmento con una condizione semplice come `Page Name equals Checkout`, il contenitore Persona viene risolto in:

- Tutte le persone che hanno visitato la pagina con il nome `Checkout`.
- Tutte le sessioni per queste persone.
- Tutti i dati evento per queste persone.

Poiché è il contenitore dalla definizione più ampia, i rapporti generati a livello del contenitore Persona restituiscono eventi e sessioni per tutte le persone idonee per il segmento. Il contenitore Persona è il più suscettibile a modifiche in base a intervalli di date definiti.
I contenitori Persona possono includere valori basati sulla cronologia generale di una persona:

- Giorni precedenti al primo acquisto.
- Pagina o schermata Home dell’app mobile in cui si è verificato l’ingresso originale.
- Domini di riferimento originali.

### Contenitore Sessione

Il contenitore Sessione consente di identificare le interazioni nelle pagine o nell’app mobile, le campagne o le conversioni per una sessione specifica. Il contenitore Sessione è il più comunemente utilizzato perché acquisisce i comportamenti per l’intera sessione una volta soddisfatta la regola. Il contenitore Sessione consente anche di definire quali sessioni includere o escludere nella creazione e nell’applicazione di un segmento.  Quando definisci un segmento con una condizione semplice come `Page Name equals Checkout`, il contenitore Sessione viene risolto in:

- Tutte le sessioni in cui viene visitata una pagina denominata `Checkout`.
- Tutti i dati evento per quelle sessioni.

Il contenitore sessione può essere utile per rispondere alle seguenti domande:

- Quante sessioni hanno interessato origini dati sia web che call center?
- Quali pagine hanno contribuito alla conversione in una vendita?

I contenitori Sessione includono valori basati su eventi per sessione:

- Tipo di sessione.
- Pagina di ingresso.
- Frequenza di ritorno.
- Metriche di partecipazione.
- Metriche allocate linearmente.

Le visualizzazioni dati in Customer Journey Analytics consentono di determinare la durata di una sessione e quando crearne una nuova. Ad esempio, puoi definire che si verifica una nuova sessione di app mobile ogni volta che l’utente avvia l’app mobile. Per ulteriori informazioni, consulta la sezione sulle [Impostazioni delle sessioni](/help/data-views/session-settings.md).

### Contenitore Evento

Il contenitore Evento definisce quale pagina, app mobile o altro tipo di eventi desideri includere o escludere da un segmento. È il contenitore dall’ambito più limitato. Consente di identificare particolari clic, visualizzazioni di pagina e tocchi sul pulsante in un’app mobile in cui si verifica una condizione. Il contenitore Evento consente di visualizzare un singolo codice di tracciamento o di isolare il comportamento all’interno di una particolare area dell’app mobile. Puoi inoltre identificare un valore specifico quando si verifica un’azione, ad esempio il canale di marketing al momento di un ordine. Quando definisci un segmento con una condizione semplice come `Page Name equals Checkout`, il contenitore Evento viene risolto in:

- Tutti gli eventi di visualizzazione pagina in cui il nome della pagina è uguale a `Checkout`.

I contenitori di eventi includono raggruppamenti di singole pagine basati su valori per:

- Prodotti
- Proprietà elenco
- Dimensioni elenco
- Dimensioni del merchandising (nel contesto degli eventi)



### Contenitori B2B

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

Se hai accesso a [Customer Journey Analytics B2B Edition](/help/getting-started/cja-b2b-edition.md), sono disponibili altri contenitori da utilizzare nei segmenti. Ulteriori dettagli sull’utilizzo di questi contenitori aggiuntivi sono disponibili in [Concetti e funzioni B2B](/help/getting-started/cja-b2b-concepts-features.md).


### Contenitore Gruppo logico

Il Gruppo logico consente di raggruppare le condizioni in un singolo punto di controllo del segmento sequenziale. Come parte della sequenza, la logica definita nel contenitore identificato come [!UICONTROL Logic Group] viene valutata dopo qualsiasi punto di controllo sequenziale precedente e prima di qualsiasi punto di controllo sequenziale successivo. Per ulteriori informazioni, consulta [Gruppo logico](seg-sequential-build.md#logic-group).

### Nidificare i contenitori

Quando crei dei contenitori all’interno di altri contenitori, crei in sostanza un segmento all’interno di un segmento. I contenitori nidificati utilizzano la logica seguente:

1. Determina i dati inclusi utilizzando il contenitore più esterno. Eventuali dati che non corrispondono a questa regola esterna vengono eliminati dal rapporto.
2. Applica la definizione del segmento nidificato ai dati rimanenti. La definizione del segmento nidificato NON si applica ai dati eliminati dalla prima definizione.
3. Ripeti l’operazione fino al completamento del calcolo di tutte le definizioni dei segmenti con contenitori nidificati. I dati rimanenti vengono quindi inclusi nel risultato e utilizzati per la generazione di rapporti.

>[!NOTE]
>
>Quando nidifichi un segmento all’interno di un segmento (ad esempio, trascini un segmento dal pannello Componenti alla definizione del segmento), viene creato un contenitore con una copia (non un riferimento) della definizione del segmento trascinato.

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
>[Creare i segmenti](seg-create.md)
>&#x200B;>[Generatore di segmenti](seg-builder.md)
>&#x200B;>[Segmenti rapidi](seg-quick.md)
>&#x200B;>[Segmenti sequenziali](seg-sequential-build.md)
>&#x200B;>[Gestire i segmenti](seg-manage.md)
