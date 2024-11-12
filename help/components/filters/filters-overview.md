---
title: Panoramica dei filtri
description: Scopri i filtri utilizzati e come creare un filtro semplice.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 5fbb228fc02304be2246f0b49cb49de7f160b227
workflow-type: tm+mt
source-wordcount: '1421'
ht-degree: 8%

---


# Panoramica sui filtri

Customer Journey Analytics ti consente di generare, gestire e condividere filtri potenti e precisi del pubblico e di applicarli ai rapporti. I filtri ti consentono di identificare sottoinsiemi di persone, sessioni o eventi in base a caratteristiche o interazioni. I filtri sono progettati come approfondimenti codificati del pubblico che puoi generare in base alle tue esigenze specifiche e quindi verificare, modificare e condividere con altri membri del gruppo.

I filtri possono essere basati su:

- attributi (tipo di browser, dispositivo, numero di visite, paese, genere),
- interazioni (campagne, ricerca di parole chiave, motore di ricerca),
- uscite ed entrate (persone provenienti da Facebook, da una pagina di destinazione definita, da un dominio di riferimento, da un evento di recinto geografico),
- variabili personalizzate (campo modulo, categorie definite, ID cliente),
- e altri criteri.

Consulta [Creare filtri](/help/components/filters/create-filters.md) per informazioni sulle varie opzioni disponibili per la creazione di filtri. Generare, modificare e salvare la definizione di un filtro nel [Generatore di filtri](filter-builder.md). In alternativa, è possibile creare filtri rapidi utilizzando il [Generatore di filtri rapidi](quick-filters.md). È inoltre possibile generare filtri dalle visualizzazioni in Workspace, ad esempio utilizzando la visualizzazione [Abbandono](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu).

Per gestire i filtri si utilizza [Gestione filtri](manage-filters.md).

## Pianificare i filtri

In particolare, in qualità di amministratore, la corretta pianificazione dei filtri migliora le possibilità di utilizzo. Quando pianifichi i filtri, tieni presente quanto segue:

- **Pubblico**: chi utilizzerà i filtri? Assicurati di fornire una buona descrizione del filtro affinché il pubblico comprenda:
   - A cosa serve questo filtro?

   - Quando dovrei usare questo filtro?

- **Ambito**: quale [Contenitore filtro](#filter-containers) rappresenta meglio i dati che stai cercando? Utilizza il contenitore più piccolo possibile.

- **Componenti**: decide quali componenti includere nella definizione del filtro e in base a quali valori le condizioni devono essere convalidate.

- **Processo**: considerare un processo di approvazione per il filtro. Non esiste un flusso di lavoro di approvazione nel Customer Journey Analytics, ma è comunque possibile organizzare un processo per determinare se approvare o meno un filtro.

- **Modularità**: definisci i filtri tenendo presente la modularità. Gli utenti dei filtri possono quindi [sovrapporre filtri](filter-builder.md#stack-filters) per creare nuovi potenti filtri.


## Tipi di filtro

Puoi creare tre tipi di filtri:

### Filtri rapidi

I filtri rapidi consentono di esplorare facilmente i dati all&#39;interno di un determinato progetto Workspace, senza dover creare un filtro nel [Generatore di filtri](/help/components/filters/create-filters.md). Puoi definire il filtro direttamente nell’interfaccia di Workspace. Per ulteriori informazioni, vedere [Filtri rapidi](quick-filters.md).

### Filtri regolari

I filtri regolari ti consentono di identificare i dati (persone, sessioni, eventi) in base a una o più condizioni. Se più condizioni, puoi utilizzare operatori logici come And e Or per definire ulteriormente il filtro. Puoi utilizzare i contenitori per raggruppare le condizioni e creare filtri più complessi. Per ulteriori informazioni, vedere [Generatore di filtri](filter-builder.md).

### Filtri sequenziali

>[!IMPORTANT]
>
>Per creare filtri sequenziali cross-channel è necessario disporre del pacchetto **Select**. In caso di dubbi sul pacchetto di Customer Journey Analytics disponibile, contattare l&#39;amministratore.

I filtri sequenziali ti consentono di identificare dati (persone, sessioni, eventi) in base alla navigazione (visualizzazioni di pagina nel sito, interazioni con scene nell’app mobile o utilizzo di un menu su un set-top box). I filtri sequenziali consentono di identificare, ad esempio, cosa piace a una persona e cosa evita. Per definire un filtro sequenziale si utilizza l’operatore logico Then. Per ulteriori informazioni, vedere [Filtri sequenziali](seg-sequential-build.md).


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Contenitori di filtri {#containers}

I filtri si basano su una gerarchia a livello di persona, sessione ed evento che utilizza un modello di contenitore nidificato. I contenitori nidificati ti consentono di definire le condizioni tra e all’interno dei contenitori.


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

Un filtro imposta le condizioni per filtrare persone, sessioni o eventi in base alle condizioni. Ad esempio, condizioni per filtrare le persone in base alle caratteristiche della persona e alle caratteristiche di navigazione. Per suddividere ulteriormente i dati, puoi filtrare in base a sessioni specifiche, eventi di visualizzazione della pagina, tocchi a schermo, scelte di menu su un set-top box e altro ancora. Ma filtra anche gli attributi che hai acquisito da un sistema CRM o fedeltà. Il [Generatore di filtri](/help/components/filters/filter-builder.md) fornisce una semplice interfaccia per generare questi sottoinsiemi e applicare condizioni in contenitori Persona, Sessione o Evento nidificati e gerarchici.

L&#39;architettura del contenitore utilizzata nel generatore di filtri [](/help/components/filters/filter-builder.md) definisce Persona come il contenitore più esterno. Il contenitore contiene dati generali specifici della persona in più sessioni ed eventi come visualizzazioni di pagina, schermate di app mobili o schermate di menu su un set-top box. Un contenitore Sessione nidificato consente di impostare regole per suddividere i dati della persona in base alle sessioni. Un contenitore Evento nidificato consente di suddividere le informazioni sulla persona in base alle singole interazioni. Ogni contenitore consente di generare rapporti sulla cronologia di una persona e sulle sue interazioni suddivise per sessioni o di suddividere singoli eventi.

### Contenitore Persona

Il contenitore Persona include ogni sessione e ogni evento per le persone che si qualificano per la condizione specificata nel contenitore. Quando definisci un filtro con una condizione semplice come `Page Name equals Checkout`, il contenitore Persona viene risolto in:

- Tutte le persone che hanno visitato la pagina con il nome `Checkout`.
- Tutte le sessioni per queste persone.
- Tutti i dati evento per queste persone.

Poiché è il contenitore definito in modo più ampio, i rapporti generati a livello del contenitore Persona restituiscono eventi e sessioni per tutte le persone che si qualificano per il filtro. Il contenitore Persona è quello più suscettibile a modifiche in base a intervalli di date definiti.
I contenitori Persona possono includere valori basati sulla cronologia generale di una persona:

- Giorni precedenti al primo acquisto.
- Pagina iniziale originale o schermata iniziale dell’app mobile.
- Domini di riferimento originali.

### Contenitore Sessione

Il contenitore Sessione consente di identificare le interazioni con pagine o con app mobili, campagne o conversioni per una sessione specifica. Il contenitore Sessione è il contenitore più comunemente utilizzato perché acquisisce i comportamenti per l’intera sessione una volta soddisfatta la regola. Il contenitore Sessione consente inoltre di definire quali sessioni includere o escludere nella creazione e applicazione di un filtro.  Quando definisci un filtro con una condizione semplice come `Page Name equals Checkout`, il contenitore Sessione viene risolto in:

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

Le visualizzazioni dati nel Customer Journey Analytics consentono di determinare la durata di una sessione, ma anche quando crearne una nuova. Ad esempio, puoi definire una nuova sessione di app mobile in base a ogni avvio dell’app mobile da parte di un utente. Per ulteriori informazioni, vedere [Impostazioni sessione](/help/data-views/session-settings.md).

### Contenitore Evento

Il contenitore Evento definisce la pagina, l’app mobile o altri tipi di eventi che desideri includere o escludere da un filtro. È il contenitore più ristretto disponibile per identificare clic specifici, visualizzazioni di pagina e pulsanti su un pulsante in un’app mobile in cui una condizione è vera. Il contenitore Evento consente di visualizzare un singolo codice di tracciamento o di isolare il comportamento all’interno di una particolare area dell’app mobile. Puoi anche individuare un valore specifico quando si verifica un’azione, ad esempio il canale di marketing al momento di un ordine. Quando si definisce un filtro con una condizione semplice come `Page Name equals Checkout`, il contenitore Evento viene risolto in:

- Tutti gli eventi di visualizzazione pagina in cui il nome della pagina è uguale a `Checkout`.

I contenitori Evento includono raggruppamenti di singole pagine basati su valori per:

- Prodotti
- Proprietà elenco
- Dimensioni elenco
- Dimensioni del merchandising (nel contesto degli eventi)


### Contenitore gruppo logico

Gruppo logico consente di raggruppare le condizioni in un singolo punto di controllo del filtro sequenziale. Come parte della sequenza, la logica definita nel contenitore identificato come [!UICONTROL Logic Group] viene valutata dopo qualsiasi punto di controllo sequenziale precedente e prima di qualsiasi punto di controllo sequenziale successivo. Per ulteriori informazioni, vedere [Gruppo logico](seg-sequential-build.md#logic-group).

### Nidificare i contenitori

Quando crei contenitori all’interno di altri contenitori, in realtà stai creando un filtro all’interno di un filtro. Ai contenitori nidificati viene applicata la logica seguente:

1. Determina i dati inclusi utilizzando il contenitore più esterno. Eventuali dati che non corrispondono a questa regola esterna vengono scartati nel rapporto.
2. Applica la definizione del filtro nidificato ai dati rimanenti. La definizione del filtro nidificato NON si applica ai dati scartati dalla prima definizione.
3. Ripeti l’operazione fino al completamento del calcolo di tutte le definizioni dei filtri dei contenitori nidificati. I dati rimanenti vengono quindi inclusi nel risultato e utilizzati per il reporting.

>[!NOTE]
>
>Quando nidifichi un filtro all’interno di un filtro (ad esempio, trascini un filtro dal pannello Componenti alla definizione del filtro), viene creato un contenitore con una copia (non un riferimento) della definizione del filtro trascinato.

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box filter template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Filter Name | Description |
| --- | --- |
| All Data | All Data is a required filter that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[Crea filtri](create-filters.md)
>[Generatore di filtri](filter-builder.md)
>[Filtri rapidi](quick-filters.md)
>[Filtri sequenziali](seg-sequential-build.md)
>[Gestisci filtri](manage-filters.md)
>
