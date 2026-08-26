---
title: Reporting popolazione totale
description: Utilizza il reporting sulla popolazione totale in Customer Journey Analytics per analizzare profili e account nei set di dati, indipendentemente dall’attività dell’evento o dagli intervalli di date del pannello.
solution: Customer Journey Analytics
feature: Connections
role: Admin
hide: true
source-git-commit: 1ce48a6e077ee1069c55f3ef8969ed2eced4742e
workflow-type: tm+mt
source-wordcount: '1388'
ht-degree: 4%

---

# Segnalazione popolazione totale

Il reporting sulla popolazione totale introduce la possibilità di analizzare e creare rapporti sulle entità definite nei set di dati di profilo e di ricerca esistenti in una connessione Customer Journey Analytics. Tale analisi e reporting vanno oltre la serie temporale di eventi dai set di dati evento. Questa funzionalità consente di abilitare nuove classi di query, metriche e definizioni di pubblico che riflettono l’intero ambito della base clienti di un’azienda.

Customer Journey Analytics è basato sugli eventi. Ogni metrica, visualizzazione, pannello, rapporto è ancorato a un intervallo di date e agli eventi che si verificano durante tale intervallo. Fai domande sulle soluzioni come:

| Domanda | Evento | Intervallo data/ora |
|---|---|---|
| Quante persone hanno effettuato un acquisto la scorsa settimana? | acquisto | ultima settimana |
| Quanti account hanno visitato la pagina dei prezzi nel primo trimestre? | visita | Q1 |

L’intervallo di date e ora del pannello Workspace filtra i dati e le dimensioni e metriche descrivono cosa è successo durante tale intervallo.

Ma non tutte le domande a cui la tua azienda deve rispondere riguardano qualcosa che è successo. A volte è necessario conoscere la propria popolazione.

| Domanda | Evento | Intervallo data/ora |
|---|---|---|
| Quanti clienti attivi abbiamo al momento? | N/D | N/D |
| Quanti account ci sono nel nostro database? | N/D | N/D |
| Quanti dei nostri membri non hanno effettuato un acquisto negli ultimi 30 giorni? | N/D | ultimi 30 giorni |

Queste domande non riguardano eventi, ma persone e account che esistono, indipendentemente dal fatto che queste persone o questi account abbiano fatto qualcosa di recente.

Il reporting sulla popolazione totale introduce una nuova classe di metriche che generano rapporti sui dati di profilo. I dati del profilo, che possono contenere persone e account, nei set di dati del profilo sono indipendenti dall’intervallo di date di un pannello. Con il reporting sulla popolazione totale, puoi combinare metriche basate sulla popolazione e metriche basate su eventi nella stessa analisi, fornendo un quadro più completo sia di chi sono i clienti sia di cosa sono stati fatti.

Il reporting sulla popolazione totale consente a Customer Journey Analytics di generare rapporti su tutte le entità definite nei set di dati di profilo e di ricerca, indipendentemente dall’attività dell’evento. Questo reporting include:

* **Query basate su profili**: analizza gli attributi (indipendentemente dagli eventi) dei profili (tutte le persone, gli account, le opportunità e i gruppi di acquisto).
* **Profilo meno query evento**: identifica i profili (tutte le persone, gli account, le opportunità e i gruppi di acquisto) che non hanno eseguito un&#39;azione o un&#39;esperienza specifica durante l&#39;intervallo di reporting.
* **Ricerche condivise**: supporta il riutilizzo dei set di dati di ricerca tra più entità per ridurre i costi di acquisizione e migliorare le prestazioni.

<!--
* **Classification-based queries**: (future enhancement) Analyze lookup datasets such as product catalogs, including items not tied to events.
-->



## Metriche di reporting popolazione totale

Le metriche di reporting relative alla popolazione totale si comportano in modo diverso rispetto alle metriche tipicamente utilizzate in Customer Journey Analytics:

* Le metriche di reporting sulla popolazione totale non sono associate all’intervallo di date del pannello. Una metrica di reporting popolazione totale come **[!UICONTROL Persone totali (profilo)]** restituisce la popolazione corrente dal set di dati del profilo, indipendentemente dall&#39;intervallo di date applicato al pannello. I filtri delle date e i confronti tra intervalli di date non influiscono sulle metriche di reporting della popolazione totale, né sul modo in cui tali filtri e confronti influiscono sulle metriche degli eventi.
* Il reporting sulla popolazione totale richiede un set di dati di profilo sulla connessione. Le metriche di reporting sulla popolazione totale vengono visualizzate solo quando la connessione include almeno un set di dati di profilo insieme ad almeno un set di dati di evento. Le connessioni con solo i set di dati evento continuano a funzionare esattamente come prima e non mostrano le metriche di reporting della popolazione totale.

In Workspace, le metriche di popolazione totale sono contrassegnate da un’icona distinta (TBD) che consente di identificare rapidamente quali metriche rispettano l’intervallo di date del pannello e quali no. Nella maggior parte dei casi, le metriche di popolazione totale possono essere utilizzate insieme alle metriche degli eventi, ma non sono supportati i tipi di visualizzazione che dipendono dalle sequenze di eventi (come Abbandono e Flusso).

### Metriche standard di segnalazione della popolazione totale

Per impostazione predefinita, il sistema include tre metriche standard per la generazione di rapporti sulla popolazione totale, disponibili in qualsiasi visualizzazione dati la cui connessione include un set di dati di profilo:

* **Persone totali (profilo)**: il numero totale di persone nel set di dati del profilo.
* **Account totali (profilo)**: il conteggio totale degli account nel set di dati del profilo. [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}
* **Persone totali (profilo + evento)**: un conteggio di unione che combina persone con ambito profilo con persone con ambito evento.

Puoi anche creare metriche personalizzate con uno qualsiasi dei tre ambiti, utilizzando i campi dei set di dati del profilo.

## Requisiti, prerequisiti e considerazioni

Affinché la segnalazione della popolazione totale funzioni correttamente, è necessario tenere in considerazione prerequisiti, requisiti e considerazioni.

### Requisiti di connessione

Per una connessione per supportare la generazione di rapporti sulla popolazione totale:

* È necessario almeno un set di dati evento per la connessione. Le connessioni di solo profilo non sono supportate.
* È necessario aggiungere alla connessione almeno un set di dati di profilo. Le metriche di reporting relative alla popolazione totale non vengono visualizzate nelle visualizzazioni dati create su connessioni che contengono solo dati evento.
* Le ricerche condivise devono essere configurate per ogni set di dati di profilo. Le ricerche condivise definiscono il modo in cui ogni set di dati di profilo viene unito agli eventi nella connessione specificando la chiave corrispondente, lo spazio dei nomi (per i campi della mappa di identità) e il percorso di unione.

#### Configurazione del set di dati profilo

Quando un set di dati di profilo viene aggiunto a una connessione, Customer Journey Analytics popola una configurazione di ricerca condivisa predefinita basata sul tipo di set di dati:

* Per i set di dati del profilo persona: l&#39;impostazione predefinita è corrispondenza per contenitore impostata su [!UICONTROL Persona], con la mappa identità come campo chiave. È possibile modificare questa impostazione predefinita. Ad esempio, per scegliere uno spazio dei nomi specifico dalla mappa delle identità anziché dalla chiave primaria. Oppure per specificare uno spazio dei nomi secondario nei casi in cui il primo spazio dei nomi non viene popolato (comune con i set di dati uniti).
* Per i set di dati del profilo account [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: il valore predefinito è match-by-container impostato su [!UICONTROL Account] (o [!UICONTROL Account globale], se gli account globali sono abilitati nella connessione). Il campo account può essere un singolo identificatore o una mappa di identità. Quando il campo account è una mappa di identità, seleziona lo spazio dei nomi da utilizzare.

Puoi configurare più ricerche condivise in un singolo set di dati profilo per supportare più percorsi di unione agli eventi. Quando si utilizza come campo chiave la stessa mappa di identità in più ricerche condivise, le selezioni dello spazio dei nomi devono essere coerenti.

### Requisiti della visualizzazione dati

Per il corretto funzionamento delle metriche di reporting sulla popolazione totale in una visualizzazione dati:

* La connessione deve includere un set di dati del profilo (vedi [Requisiti di connessione](#connection-requirements)). Se rimuovi l’ultimo set di dati di profilo rimanente da una connessione, le metriche di reporting sulla popolazione totale non sono disponibili nelle visualizzazioni dati create da tale connessione.
* [I segmenti a livello di visualizzazione dati](/help/data-views/create-dataview.md#settings-segments) non devono essere espliciti da eventi. Se un segmento applicato direttamente alla visualizzazione dati è definito interamente in termini di condizioni con ambito evento (ad esempio, `hit where page = X`), la segnalazione della popolazione totale non è possibile in tale visualizzazione dati. Prima di affidarti alle metriche di reporting sulla popolazione totale, verifica che tutti i segmenti a livello di visualizzazione dati siano compatibili con il reporting con ambito di profilo.
* L’ambito della metrica deve essere impostato correttamente. Quando crei un componente metrico personalizzato nel data view builder, seleziona l’ambito appropriato (evento, profilo o profilo + evento) in base al set di dati del campo e al comportamento che desideri che si comporti con la metrica. L’ambito non può essere modificato dopo che la metrica viene utilizzata in tipi di pubblico o in rapporti ricorrenti senza interrompere tali dipendenze.

### Compatibilità con Workspace

Le metriche totali di reporting sulla popolazione possono essere utilizzate insieme alle metriche basate su eventi nella maggior parte dei contesti di Workspace: [tabelle a forma libera](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), [riga](/help/analysis-workspace/visualizations/line.md), [barra](/help/analysis-workspace/visualizations/bar.md) e [visualizzazioni a barre orizzontali](/help/analysis-workspace/visualizations/horizontal-bar.md), [tabelle coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) se configurate in modo appropriato e così via. Alcuni tipi di visualizzazione non sono supportati perché dipendono intrinsecamente dalle sequenze di eventi:

* [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)
* [Flusso](/help/analysis-workspace/visualizations/c-flow/flow.md)
* ulteriori tipi di visualizzazione non supportati da confermare prima della pubblicazione.

Quando aggiungi una metrica di reporting sulla popolazione totale a una visualizzazione non supportata, Workspace indica che la metrica non può essere utilizzata in tale contesto.

### Considerazioni sul pubblico

I tipi di pubblico generati dalle metriche di reporting per popolazione totale dipendono dalle metriche che rimangono presenti nella visualizzazione dati:

* Un pubblico ricorrente che utilizza una metrica di segnalazione della popolazione totale ha esito negativo e passa a uno stato di ERRORE se la metrica di segnalazione della popolazione totale viene rimossa dalla visualizzazione dati.
* L’interfaccia di Customer Journey Analytics impedisce la rimozione di una metrica, mentre qualsiasi pubblico ricorrente attivo dipende dalla metrica, e prima di confermare la rimozione espone indicazioni sulla dipendenza.

### Autorizzazioni

Da confermare: eventuali requisiti di accesso a ruoli o funzionalità sull’organizzazione IMS o sul profilo di prodotto del cliente prima che siano visibili le metriche di reporting sulla popolazione totale. Vale la pena segnalare a PM prima della pubblicazione.
