---
title: Concetti e funzionalità di Customer Journey Analytics B2B edition
description: Concetti e funzionalità per B2B edition di Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: e16bfa01dd3bedc96a147b2510ba33f4b88b01b9
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

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

In Customer Journey Analytics i contenitori vengono generati come parte della configurazione di una connessione e di una visualizzazione dati. Nei contenitori vengono memorizzati solo gli identificatori per facilitare l’esecuzione rapida ed efficiente di funzionalità quali segmentazione, raggruppamenti e altro ancora.

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

## Set di dati

Quando configuri [impostazioni set di dati](/help/connections/create-connection.md#dataset-settings) per la connessione basata sull&#39;account in Customer Journey Analytics B2B edition, le opzioni disponibili per alcune impostazioni dipendono dal [tipo di set di dati](/help/connections/create-connection.md#dataset-types). Ad esempio, devi:

* Specifica gli identificatori per ciascuno dei contenitori configurati per i set di dati evento.
* Definisci un campo conto o un campo conto globale per i set di dati profilo.
* Definisci le chiavi e come farle corrispondere (per contenitore di campo) per i set di dati di ricerca.

## Corrispondenza per contenitore o campo

Puoi definire per ogni set di dati di ricerca, sia che tu corrisponda al set di dati per campo o per contenitore.

### Corrispondenza per contenitore

Se un set di dati record utilizza una corrispondenza per contenitore, il set di dati record viene considerato come un tipo di set di dati profilo e come un set di dati profilo nell’interfaccia utente. Utilizza corrispondenza per contenitore nei set di dati che supportano i contenitori configurati. Ad esempio, un set di dati Gruppo acquisti.

### Corrispondenza per campo

Se un set di dati record utilizza una corrispondenza per campo, nell’interfaccia utente il set di dati record viene considerato come un tipo di set di dati di ricerca e come un set di dati di ricerca. Utilizza il campo corrispondenza per nei set di dati che supportano ulteriori dettagli tramite la ricerca. Ad esempio, un set di dati Membro di un elenco di marketing o un set di dati Dettagli prodotto.


## Rapporto sui dati basati su persone e account

Se desideri creare rapporti sui contenitori basati su persone (e sulle identità di persona) e sui contenitori basati su account (e sulle identità di account), imposta due connessioni separate in Customer Journey Analytics. Una connessione in cui si seleziona Persona come ID primario e una connessione in cui si seleziona Account come ID primario. Customer Journey Analytics non supporta la generazione di rapporti basati su persone e account da una singola gerarchia di contenitori.

