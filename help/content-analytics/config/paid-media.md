---
title: Configurazione automatica Content Analytics Paid Media
description: Scopri la configurazione automatica di set di dati, connessioni, visualizzazioni dati e altro ancora.
solution: Customer Journey Analytics
feature: Content Analytics
hold: true
role: Admin
source-git-commit: 684fef6a5e007d6dabe6518d7c7ec93a41dc6cdd
workflow-type: tm+mt
source-wordcount: '2179'
ht-degree: 3%
---
# Configurazione automatica supporti a pagamento

Quando abiliti il canale dei file multimediali a pagamento in Content Analytics e salvi la configurazione, Adobe aggiorna la connessione e le visualizzazioni dati selezionate con la configurazione di reporting per i set di dati dei file multimediali a pagamento. Non è necessario ricreare personalmente le dimensioni, le metriche, la logica di ricerca o i gruppi di dati di riepilogo predefiniti.

Vengono creati tre livelli di oggetti:

| Oggetti | Contiene | Finalità |
| --- | --- | --- |
| Set di dati di riepilogo | Dati sulle prestazioni della rete Advertising a livello di annuncio, posizionamento dell’esperienza o risorsa, con raggruppamenti demografici/geografici separati, se supportati. | Consente di misurare la consegna, i clic, la spesa e i risultati riportati dalla rete pubblicitaria |
| Set di dati di ricerca di metadati e attributi | Dettagli di account, campagna, gruppo di annunci, annunci, esperienza e risorse; attributi creativi di Content Analytics. | Consente di creare rapporti utilizzando nomi riconoscibili, dettagli creativi, miniature e attributi di contenuto anziché identificatori. |
| Componenti e configurazione della visualizzazione dati | Dimensioni, metriche, metriche calcolate, campi derivati e gruppi di dati di riepilogo. | Consente di creare analisi di Workspace senza ricreare manualmente le relazioni tra questi set di dati. |

L’abilitazione dei supporti a pagamento non collega automaticamente i dati dei supporti a pagamento agli ordini, alle prenotazioni o ai ricavi del sito. La correlazione tra i dati dell’evento esperienza e i dati multimediali a pagamento richiede la mappatura dei tasti di tracciamento e la configurazione di reporting specifiche per il cliente.

## Set di dati di riepilogo

L’illustrazione seguente mostra come vengono generati i set di dati di riepilogo quando abiliti il canale dei file multimediali a pagamento in Content Analytics per una o più reti di annunci. Le API pertinenti delle reti di annunci disponibili vengono utilizzate per scaricare e trasformare esperienze, risorse e dati pubblicitari in potenzialmente sei set di dati di riepilogo.

![Generazione di set di dati di riepilogo a pagamento](/help/content-analytics/assets/paid-media-generation-of-datasets.svg)

I set di dati di riepilogo creati sono determinati dalla rete di annunci specifica. Non tutte le reti di annunci, per le quali hai configurato un connettore di origine, generano tutti e sei i possibili set di dati di riepilogo. Consulta la tabella seguente per una panoramica dei set di dati di riepilogo con le seguenti informazioni:

* Nome set di dati di riepilogo, tipo di evento e suffisso componente
* Entità
* Raggruppamenti
* Quali set di dati sono compilati ![Segno di spunta](/help/assets/icons2/Checkmark.svg) per le reti seguenti:
  * ![MetaSolid](/help/assets/icons2/MetaSolid.svg) Meta
  * ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) Google
  * ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) Pinterest
  * ![Snapchat](/help/assets/icons2/Snapchat.svg) Snapchat
  * ![TikTok](/help/assets/icons2/TikTok.svg) TikTok

    >[!AVAILABILITY]
    >
    >Pinterest, Snapchat e TikTok sono in fase di test limitato del rilascio e potrebbero non essere ancora disponibili nel tuo ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sulla procedura di rilascio di Customer Journey Analytics, vedere [Versioni delle funzionalità di Customer Journey Analytics](/help/release-notes/releases.md)
    >


* che cosa rappresenta ogni riga in un set di dati di riepilogo.

| Set di dati di riepilogo<br/>Tipo evento<br/>Suffisso componente | Entità | Raggruppamento | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | Ogni riga rappresenta |
|---|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | Annuncio | Nessuno | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | Prestazioni giornaliere di un annuncio senza raggruppamenti demografici o geografici. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Annuncio | età, sesso | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | Performance giornaliere di un annuncio suddivise per età e sesso. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Annuncio | paese, regione | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | Le prestazioni giornaliere di un annuncio suddivise per paese e area geografica. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Esperienza | piattaforma, posizione | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | Prestazioni giornaliere associate all’esperienza creativa di un annuncio, suddivise per piattaforma e posizione. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | Risorsa | Nessuno | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | | | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | Prestazioni giornaliere a livello di risorsa nel contesto di annunci/campagne, senza suddivisioni demografiche o geografiche. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | Risorsa | età, sesso | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | | | | | Prestazioni giornaliere a livello di risorsa nel contesto di annunci/campagne, suddivise per età e genere. |


Questa tabella descrive la copertura dei set di dati, non garantisce che ogni metrica o campo di metadati sia compilato da una particolare rete. Controlla i campi necessari per l’analisi. Un campo non disponibile o un raggruppamento non supportato non corrisponde a un valore zero misurato per un campo.

I set di dati di ricerca separati descrivono account, campagna, gruppo di annunci, annuncio, esperienza e risorsa. Forniscono nomi e metadati utilizzando GUID di entità. Non esiste alcuna associazione uno-a-uno tra i set di dati di riepilogo e i sei set di dati di ricerca.

Il raggruppamento dei dati di riepilogo riunisce dimensioni equivalenti; il raggruppamento non totalizza i sei totali della metrica delle prestazioni.

## Componenti

Una volta abilitato, il canale Content Analytics Paid media genera anche una serie di componenti di visualizzazione dati. Questi componenti sono forniti con un suffisso componente per distinguere tra loro componenti denominati simili.

### Metriche

Reti di annunci diverse restituiscono diversi raggruppamenti delle prestazioni. Content Analytics mantiene tali distinzioni invece di trattare ogni versione di una metrica come intercambiabile.

Ad esempio:

| Componente | Significato | Analisi iniziale appropriata |
| --- | --- | --- |
| Clic \| Riepilogo annuncio | Clic segnalati al livello di nessun raggruppamento dell’annuncio | Prestazioni di campagne o annunci |
| Clic \| Riepilogo risorse | Clic segnalati a livello di risorsa | Prestazioni delle risorse Creative |
| Clic \| Ad Geo | Clic dal rapporto dell’area geografica dell’annuncio | Prestazioni per paese |
| Clic \| Posizionamento esperienza | Clic dal rapporto di posizionamento dell’esperienza | Prestazioni Creative per posizionamento |

Ciascun componente della metrica &quot;clic&quot; fornisce un contesto di reporting diverso. Non puoi semplicemente sommare questi componenti metrici in un totale complessivo. La stessa attività pubblicitaria sottostante può essere rappresentata in più set di dati di riepilogo.

### Dimensioni

Ogni set di dati di riepilogo contiene ID e GUID. L&#39;ID è l&#39;identità (per account, campagna, gruppo di annunci, annuncio, esperienza e risorsa) fornita dalla rete di annunci ed è univoco **all&#39;interno** dei dati della rete di annunci. Il GUID è un&#39;identità fornita da Adobe (per account, campagna, gruppo di annunci, annuncio, esperienza e risorsa) ed è univoco **in tutte** le reti di annunci. ID e GUID vengono utilizzati per cercare i nomi e i metadati corrispondenti.

### Campi derivati

I campi derivati fanno parte della configurazione del reporting automatico. I campi derivati traducono gli identificatori in nomi e metadati, espongono gli attributi creativi e supportano le dimensioni equivalenti utilizzate nelle origini di reporting. Non creano attività pubblicitarie aggiuntive né attribuiscono automaticamente una conversione a un sito web.

Utilizza la stessa suddivisione per le metriche all’interno di un’analisi e per le dimensioni supportate da tale suddivisione. Tieni presente che i totali demografici e geografici non equivalgono necessariamente ai totali senza raggruppamenti per una rete di annunci e non implicano un errore di acquisizione.

## Reporting e analisi

Dopo aver completato la configurazione e l’acquisizione di Content Analytics Paid Media, puoi iniziare con le attività di reporting e analisi. Per alcuni esempi, consulta la tabella seguente. Utilizza le dimensioni canoniche raggruppate, se disponibili, e scegli le metriche dal livello di reporting corrispondente.

| Domanda aziendale | Livello iniziale | Righe e raggruppamenti | Metriche iniziali | Limite importante |
| --- | --- | --- | --- | --- |
| Come vanno le campagne e gli annunci? | Riepilogo annuncio | Nome della campagna, Nome del gruppo di annunci, Nome dell’annuncio; facoltativamente Nome della rete di annunci e dell’account | Impression \| Riepilogo annuncio, Clic \| Riepilogo annuncio, Spesa \| Riepilogo annuncio, CTR e CPC corrispondenti | Utilizza un livello per i totali di consegna/spesa; convalida la valuta prima di combinare i conti |
| Quali risorse creative ottengono la risposta più efficace? | Riepilogo risorse | Nome risorsa (file multimediali a pagamento), identità risorsa; facoltativamente Ad Network | Impression \| Riepilogo risorse, Clic \| Riepilogo risorse, Tasso di click-through \| Riepilogo risorse | Si tratta delle prestazioni delle risorse segnalate dalla rete, non della prova di una successiva conversione in loco |
| Quali caratteristiche dell&#39;immagine sono associate alle prestazioni? | Riepilogo risorse | Tag risorsa, oggetti risorsa, categorie di persone risorsa, scene risorsa o altri attributi risorsa disponibili | Impression di riepilogo delle risorse, clic e CTR | L’estrazione degli attributi deve essere disponibile; le categorie di attributi multivalore possono sovrapporsi |
| Quali caratteristiche di messaggistica sono associate alle prestazioni a pagamento? | Posizionamento esperienza | Parole chiave dell’esperienza, toni dell’esperienza, strategie di persuasione dell’esperienza o altri attributi di esperienza disponibili; opzionalmente Piattaforma e posizionamento | Impression \| Posizionamento esperienza, Clic \| Posizionamento esperienza, CTR corrispondente | Richiede attributi di esperienza compilati; i risultati sono specifici per il posizionamento e descrivono l’associazione, non l’impatto causale |
| Quali posizionamenti hanno prestazioni migliori? | Posizionamento esperienza | Nome esperienza, Piattaforma, Posizionamento | Impression \| Posizionamento esperienza, Clic \| Posizionamento esperienza, CTR corrispondente | Le definizioni di posizionamento e i valori disponibili variano a seconda della rete pubblicitaria |
| Come si confrontano annunci, risorse ed esperienze di Meta e Google? | Riepilogo annuncio, Riepilogo risorse o Posizionamento esperienza, scelti per la domanda | Aggiungi una rete con la dimensione appropriata per campagne, risorse o esperienze | Definizione dello stesso livello e metrica per entrambe le reti | Confronta solo i campi popolati da entrambe le reti; Google non popola i tre riepiloghi demografici/geografici in questo modello |

Questi rapporti possono rivelare associazioni tra attributi creativi e prestazioni, non dimostrare che un attributo ha causato un risultato.

Evitare combinazioni incompatibili: il nome della risorsa (elemento multimediale a pagamento) con le metriche Riepilogo annunci non sostituisce un rapporto sulle risorse. Utilizza le metriche Riepilogo risorse per l’analisi delle risorse e le metriche Ad Geography per l’analisi regionale. Le celle vuote o zero da un accoppiamento non compatibile non devono essere interpretate come prova di assenza di attività.

### Esempio di prestazioni della campagna pubblicitaria

Desideri creare rapporti sulle prestazioni della campagna a livello di annuncio. In Analysis Workspace, utilizza Nome campagna come dimensione (righe) e utilizza le metriche come descritto nella tabella seguente. Ogni metrica ha lo stesso suffisso di componente.

| Metriche | Livello di reporting |
| --- | --- |
| Impression | Riepilogo annuncio |
| Clic | Riepilogo annuncio |
| Spesa | Riepilogo annuncio |
| Percentuale di click-through | Riepilogo annuncio |
| Costo per clic | Riepilogo annuncio |

Facoltativamente, suddividi il Nome campagna per Nome annuncio ma mantieni tutte e cinque le colonne a livello di Riepilogo annuncio.

Per esaminare le singole risorse, utilizza una tabella separata con le colonne Nome risorsa (Elementi multimediali a pagamento) e Riepilogo risorse corrispondenti. Non aggiungere i totali delle due tabelle insieme.

### Esempio di annunci con prestazioni migliori per la rete

Desideri capire quali sono le migliori prestazioni degli annunci Meta?

Per effettuare un’indagine, utilizza ulteriori suddivisioni geografiche e demografiche. Utilizza Nome campagna o Nome annuncio come dimensione e utilizza le metriche come descritto nella tabella seguente. Ogni metrica ha lo stesso suffisso di componente.

| Metriche | Livello di reporting |
| --- | --- |
| Impression | Geo dell’annuncio |
| Clic | Geo dell’annuncio |
| Spesa | Riepilogo annuncio |
| Percentuale di click-through | Geo dell’annuncio |
| Costo per clic | Riepilogo annuncio |


### Correlazione dei dati multimediali a pagamento con le date dell’evento esperienza

Combina le prestazioni dei media a pagamento con i dati comportamentali sul sito per comprendere come le campagne e gli annunci sono associati al coinvolgimento, alle conversioni e ai ricavi del sito web. Ad esempio, confronta i clic e le spese della rete pubblicitaria con gli ordini attribuiti alle visite della stessa campagna.

Per configurare questo reporting, includi i set di dati di riepilogo dei file multimediali a pagamento e il set di dati dell’evento nel sito nella stessa connessione Customer Journey Analytics. Acquisisci identificatori stabili di campagne, annunci o risorse supportate dai parametri URL della pagina di destinazione o dai campi evento esistenti. Utilizza i campi derivati necessari per analizzare e mappare tali valori ai corrispondenti identificatori di elementi multimediali a pagamento, mantenendo la rete e il contesto dell’account richiesti. Usa gli identificatori come stringhe. Configura un gruppo di dati di riepilogo nella visualizzazione dati per associare l&#39;evento corrispondente e le dimensioni di riepilogo. L’abilitazione del canale Paid Media non configura automaticamente questa mappatura e tracciamento URL specifico per l’implementazione.


| Opzione di tracciamento | Considerazioni |
|---|---|
| Meta Ads | Configurare i parametri dell&#39;URL di destinazione utilizzando identificatori dinamici come `campaign.id`, `adset.id` e `ad.id`, se supportati. Acquisisci i valori risolti sul tuo sito web. L’abilitazione del connettore non aggiunge automaticamente questi parametri agli URL dell’annuncio. |
| Google Ads | |
| Singole risorse | La segnalazione a livello di risorsa dei risultati a valle richiede un identificatore acquisito mappato alla risorsa specifica associata al clic. Un parametro URL personalizzato può supportare questa funzione se il formato dell’annuncio consente il tracciamento specifico delle risorse. Un identificatore di annuncio da solo non è in grado di distinguere più risorse all’interno di un annuncio e un parametro di risorsa statico applicato a un intero annuncio con più risorse non identifica quale risorsa è stata associata al clic. |

In Analysis Workspace, utilizza le metriche **[!UICONTROL Riepilogo annuncio]** per i confronti tra campagne o annunci e le metriche **[!UICONTROL Riepilogo risorse]** per i confronti tra risorse supportati. Applica un modello di attribuzione e un intervallo di lookback alle metriche di conversione nel sito che riflettono la domanda di reporting.

Tieni presente quanto segue:

* I dati multimediali a pagamento sono dati di riepilogo aggregati senza un ID persona. Il comportamento nel sito è dato da un evento.
* Il raggruppamento delle dimensioni corrispondenti supporta il reporting tra queste origini, ma non corrisponde alle conversioni di singoli annunci e di rete in conversioni di siti web o esegue unioni a livello di persona.
* Il confronto mostra un&#39;associazione, non un incremento causale.
* I risultati possono variare a causa delle definizioni di conversione, delle finestre di attribuzione, delle conversioni view-through o modellate, del consenso e delle date di reporting o dei fusi orari.
* Convalida l’origine delle visite con tag della campagna, in particolare quando i parametri di tracciamento vengono riutilizzati tra i canali.


### Esempio di confronto delle prestazioni della campagna con gli ordini in loco

Un URL di pagina di destinazione può contenere diversi parametri di tracciamento. In questo esempio viene utilizzato l&#39;ID campagna in `utm_id` per confrontare la spesa della campagna con gli ordini del sito Web.

https://www.example.com/offer?utm_source=facebook&utm_medium=paid_social&utm_campaign=autumn_offer&utm_id=120218706543980215

Parametro utilizzato per il confronto: `utm_id=120218706543980215`. Gli altri parametri descrivono l’etichetta di origine, il supporto e la campagna, ma non vengono utilizzati come campo corrispondente utilizzato in questo esempio.

Se l’URL viene acquisito nei dati dell’evento del sito web e sia il set di dati dell’evento del sito web che i set di dati a pagamento multimediali fanno parte della stessa connessione Customer Journey Analytics:

1. Identifica la campagna. Utilizza un campo derivato per leggere `utm_id` dall&#39;URL e mapparne il valore all&#39;identificatore della campagna corrispondente nei dati multimediali a pagamento.
1. Raggruppa le dimensioni corrispondenti. Nella visualizzazione dati, aggiungere la dimensione della campagna del sito Web alla dimensione della campagna a pagamento `Summary Data Group`, mantenendo tutti i membri esistenti.
1. Confrontare spese e ordini. In Analysis Workspace, utilizza la dimensione Campagna raggruppata come righe di una tabella a forma libera. Aggiungi `Ad Summary` spesa e sito Web `Orders` come colonne. Imposta il modello di attribuzione e l&#39;intervallo di lookback per `Orders`.


La tabella mostra le spese di rete degli annunci e gli ordini dei siti web attribuiti a ciascuna campagna. Due campagne con una spesa pubblicitaria simile potrebbero avere un numero diverso di azioni attribuite al sito web a valle. Utilizza questo confronto per identificare campagne ed esperienze di pagine di destinazione per ulteriori indagini o test, anziché valutare le prestazioni solo in base alle metriche pubblicitarie.

L’esempio utilizza un ID campagna, ma lo stesso approccio può utilizzare identificatori di gruppi di annunci, annunci o risorse quando è possibile acquisire valori corrispondenti. Gli attributi di Content Analytics, ad esempio **[!UICONTROL Colori primo piano risorse]**, consentono di confrontare le caratteristiche creative con le prestazioni dei supporti a pagamento. Con il tracciamento specifico delle risorse e le dimensioni degli attributi corrispondenti configurate tra entrambe le origini, puoi estendere il confronto agli ordini attribuiti del sito web e utilizzare i risultati per guidare il test creativo.
