---
title: Concetti e funzionalità di Customer Journey Analytics B2B edition
description: Concetti e funzionalità per B2B edition di Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: 1a7b877d989764e737d7f35c05f515efe3e7a307
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 2%

---


# Concetti e funzionalità di B2B edition

{{draft-b2b}}

Questo articolo spiega concetti come connessioni, identificatori, contenitori e set di dati, comunemente utilizzati in Customer Journey Analytics. E come Customer Journey Analytics B2B edition aggiunge ulteriori funzioni a questi concetti.


## Connessioni e identificatori

In Customer Journey Analytics, scegli un identificatore comune, noto come ID persona, per collegare i dati dell’evento con altri set di dati come set di dati di profilo e set di dati di ricerca. Questo tipo di connessione è nota come connessione basata su persona, che facilita le attività di reporting e analisi basate su persona.

In Customer Journey Analytics B2B edition è possibile scegliere tra una connessione basata su persona o una connessione basata su account. Una connessione basata su account facilita la creazione di report e l&#39;analisi basati su account.

* Per una connessione basata su persona, selezionare Persona come identificatore principale. Puoi quindi configurare e configurare i progetti di connessione, visualizzazione dati e area di lavoro per il reporting basato su persone.
* Per una connessione basata su account, selezionare Account come identificatore principale. Facoltativamente, puoi aggiungere altri contenitori per Account globale, Gruppo di acquisto e Opportunità. A seconda che si aggiunga o meno un account globale, l&#39;identificatore principale è un identificatore di account o un identificatore di account globale.


## Contenitori

In Customer Journey Analytics i contenitori vengono generati come parte della configurazione di una connessione e di una visualizzazione dati e forniscono struttura e ambito dei dati. I contenitori memorizzano gruppi di identificatori per sequenziare tutte le marche temporali degli eventi per identificatori univoci. Questo tipo di archiviazione consente di eseguire in modo rapido ed efficiente funzionalità quali segmentazione, attribuzione e visualizzazioni.

### Contenitori standard

Customer Journey Analytics si basa sul concetto di tre contenitori: Persona, Sessione ed Evento. Durante una configurazione, questi contenitori vengono generati in modo implicito.

È possibile ridefinire il modo in cui questi contenitori vengono denominati quando si configura una visualizzazione dati, ma la gerarchia e le relazioni tra i contenitori sono predeterminate. Il contenitore Sessione viene generato in base alla modalità di definizione di una sessione nelle [Impostazioni sessione](/help/data-views/session-settings.md) nella visualizzazione dati.

![B2C](assets/b2c-containers.svg){zoomable="yes"}


### contenitori B2B

In Customer Journey Analytics B2B edition, all’elenco dei contenitori generati viene aggiunto un contenitore Account. Inoltre puoi configurare la generazione di contenitori aggiuntivi, come Account globale, Gruppo di acquisto e Opportunità.

La gerarchia e le relazioni tra i contenitori sono predeterminate. Opportunità, Gruppo di acquisto e Persona sono tutti contenitori di pari livello del contenitore Account. In questa gerarchia il contenitore Sessione tra il contenitore Persona e il contenitore Evento viene generato in base alla modalità di definizione di una sessione nelle [Impostazioni sessione](/help/data-views/session-settings.md) nella visualizzazione dati. Contenitori di sessioni aggiuntivi, ad esempio tra il contenitore Account e il contenitore Evento, non sono attualmente generati e supportati. Consulta la tabella seguente per una descrizione e un utilizzo di base dei contenitori B2B.

![B2B](assets/b2b-containers.svg){zoomable="yes"}

| Contenitore B2B | Descrizione<br/>Caso d&#39;uso di base |
|---|---|
| Account | Un&#39;azienda cliente o potenziale cliente della tua attività. La società potrebbe essere una filiale o una divisione di un&#39;organizzazione più grande. Conto rappresenta l&#39;organizzazione per la quale si effettua la vendita e di cui si desidera tenere traccia a livello di organizzazione. |
| Account globale (facoltativo) | Società capogruppo di un gruppo di società collegate. Un conto globale non ha una società madre, ma può avere affiliate o divisioni appartenenti al conto globale. Quando nella connessione è configurato il contenitore Account globale, un account che non ha padre o affiliate deve essere elencato sia nel campo account che nel campo account globale. |
| Opportunità (facoltativo) | Una raccolta di prodotti e servizi venduti insieme. Un&#39;opportunità spesso coinvolgeva varie fasi del ciclo di vendita fino alla chiusura della vendita.<br>I dati verranno utilizzati per misurare la progressione dell&#39;opportunità attraverso il funnel di vendita. Ad esempio, un rapporto che fornisce dettagli sulle principali opportunità che sono state spostate dalla fase 3 alla fase 4. |
| Gruppo di acquisto (facoltativo) | Una raccolta di persone all’interno di un’organizzazione coinvolte nel processo decisionale per l’acquisto di un prodotto o di un servizio. <br/>Puoi utilizzare i dati del gruppo di acquisto per tenere traccia dei gruppi di acquisto tramite la gestione delle campagne. Ad esempio, crea un segmento di pubblico di gruppi di acquisto chiave.<br/> È probabile che si desideri una ricerca dal gruppo di acquisto ai dati del profilo, in modo da poter creare rapporti sulle persone in un gruppo di acquisto. |
| Persona | Un individuo, spesso identificato da un indirizzo e-mail univoco che ha interagito con l&#39;azienda. <br/>Utilizzare i dati del profilo per identificare le persone che lavorano per un account. Ad esempio: esegui il targeting di tutte le persone di un account che si sono iscritte a una conferenza. |

>[!IMPORTANT]
>
>* Se hai **abilitato** il contenitore Account globale in una connessione basata sull&#39;account, ogni record nei set di dati dell&#39;evento deve contenere un ID account e un ID account globale. In caso contrario, il record verrà ignorato.
>* Se **non è abilitato** il contenitore Account globale in una connessione basata sull&#39;account, ogni record nei set di dati evento deve contenere un ID account. In caso contrario, il record verrà ignorato.

Puoi utilizzare i contenitori B2B per specifiche funzionalità B2B in Analysis Workspace:

* **Segmentazione**: [Contenitori di segmenti B2B](/help/components/filters/filters-overview.md#b2b-containers) ti consentono di creare segmenti con un ambito contenitore oltre a persona, sessione o evento. Ad esempio: un segmento Conti con registrazione eventi o un segmento Conti USA con gruppi di acquisto e opportunità di fase 5.

  >[!NOTE]
  >
  >I dati dell’evento B2B in una configurazione basata sull’account in Customer Journey Analytics B2B edition possono contenere righe di dati senza una persona o una sessione. Ad esempio: una riga che descrive la progressione della fase dell’opportunità. Quando valuti il segmento, tieni presente che le persone e le sessioni potrebbero non essere più i criteri giusti.
  >

* **Attribuzione**: è possibile utilizzare i nuovi contenitori B2B in [pannello attribuzione](/help/analysis-workspace/c-panels/attribution.md), in [impostazioni componente attribuzione](/help/data-views/component-settings/attribution.md), in [metriche calcolate](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) o in [colonne in una tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md). I lookback degli account vengono estesi a 13 mesi.

* **Visualizzazioni**: [Abbandono](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), [Flusso](/help/analysis-workspace/visualizations/c-flow/flow.md), [Area di lavoro Percorsi](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) e [La tabella coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) supporta i nuovi contenitori B2B. Ad esempio: puoi utilizzare i nuovi contenitori per comprendere in che modo i gruppi di acquisto consumano i contenuti o come le coorti di opportunità si spostano verso la chiusura di una vendita.
Puoi anche impostare il contenitore predefinito per queste visualizzazioni nelle [preferenze utente](/help/analysis-workspace/user-preferences.md#visualizations-preferences).

Segmenti, attribuzione e visualizzazioni insieme ai contenitori B2B ti supportano nelle analisi e nelle informazioni B2B approfondite.


## Set di dati

Il B2B di Customer Journey Analytics distingue tra i seguenti tipi di dati e set di dati.

| Tipo di dati | Serie temporali | Record contenitore | Record di campo |
|---|---|---|---|
| **Set di dati** | **Set di dati evento**<br/> Ad esempio:<ul><li>Analisi digitale</li><li>Eventi CRM</li><li>Eventi di persona</li><li>Dati del call center</li></ul> | **Set di dati profilo**<br/> Ad esempio:<ul><li>Record CRM</li><li>Record B2B di AJO</li><li>Record CDP</li><ul> | **Classificazioni**<br/> Ad esempio:<ul><li>Record campagna</li><li>Record elenco marketing</li><li>Metadati del contenuto</li><li>Record di prodotto</li></ul> |
| Requisiti | **Timestamp**<br> Per ogni record è necessario:<ul><li>ID account</li><li>ID account globale</li><li>ID persona</li></ul> | **I record ID account**<br> richiedono un ID contenitore, ad esempio:<ul><li>Account</li><li>Persona</li><li>Opportunità</li><li>Gruppo acquisti</li></ul> | **La chiave corrispondente**<br> I record richiedono un ID contenuto in un contenitore o in un set di dati evento, ad esempio:<ul><li>ID campagna</li><li>ID contenuto</li><li>ID prodotto</li></ul> |

{style="table-layout:fixed"}

Esempio di connessione basata su account in Customer Journey Analytics B2B edition:

![Esempio di connessione basata sull&#39;account](assets/b2b-datasets.svg)

Customer Journey Analytics B2B edition offre l&#39;interfaccia [Connection Map](/help/connections/create-connection.md#connection-map) per fornire una panoramica delle relazioni tra i set di dati presenti nella connessione.


Analogamente a Customer Journey Analytics, i dati delle serie temporali basate su eventi sono alla base di Customer Journey Analytics B2B edition. La differenza principale per una connessione basata sull’account è che è necessario un ID account su ogni record nel set di dati dell’evento invece di un ID persona.

Quando configuri [impostazioni set di dati](/help/connections/create-connection.md#dataset-settings) per la connessione basata sull&#39;account in Customer Journey Analytics B2B edition, le opzioni disponibili per alcune impostazioni dipendono dal [tipo di set di dati](/help/connections/create-connection.md#dataset-types). Ad esempio, devi:

* Specifica gli identificatori per ciascuno dei contenitori configurati per i set di dati evento.
* Definisci un campo conto o un campo conto globale per i set di dati profilo.
* Definisci le chiavi e come farle corrispondere (per contenitore di campo) per i set di dati di ricerca.

## Corrispondenza per contenitore o campo

Puoi definire per ogni set di dati di ricerca, sia che tu corrisponda al set di dati per campo o per contenitore.

### Corrispondenza per contenitore

Se un set di dati record utilizza una corrispondenza per contenitore, il set di dati record viene considerato come un tipo di set di dati profilo e come un set di dati profilo nell’interfaccia utente. Utilizza corrispondenza per contenitore nei set di dati che contengono record contenitore e che supportano i contenitori configurati. Ad esempio, un set di dati Gruppo acquisti.

### Corrispondenza per campo

Se un set di dati record utilizza una corrispondenza per campo, nell’interfaccia utente il set di dati record viene considerato come un tipo di set di dati di ricerca e come un set di dati di ricerca. Utilizza corrispondenza per campo nei set di dati che contengono dettagli di classificazione aggiuntivi tramite la ricerca. Ad esempio, un set di dati Membro di elenco di marketing o un set di dati Dettagli prodotto.


## Rapporto sui dati basati su persone e account

Se desideri creare rapporti sui contenitori basati su persone (e sulle identità di persona) e sui contenitori basati su account (e sulle identità di account), imposta due connessioni separate in Customer Journey Analytics. Una connessione in cui si seleziona Persona come ID primario e una connessione in cui si seleziona Account come ID primario. Customer Journey Analytics non supporta la generazione di rapporti basati su persone e account da una singola gerarchia di contenitori.

