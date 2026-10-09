---
title: Configurazione automatica Content Analytics Paid Media
description: Scopri la configurazione automatica di set di dati, connessioni, visualizzazioni dati e altro ancora.
solution: Customer Journey Analytics
feature: Content Analytics
hold: true
role: Admin
source-git-commit: 29a21d57b6b50d873a4464d1a705c1b4855dd3ea
workflow-type: tm+mt
source-wordcount: '2502'
ht-degree: 2%
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

![Generazione di set di dati di riepilogo a pagamento](/help/content-analytics/assets/paid-media-generation-of-datasets.png)

La rete di annunci specifica determina quali set di dati di riepilogo vengono creati. Non tutte le reti di annunci, per le quali hai configurato un connettore di origine, generano tutti e sei i possibili set di dati di riepilogo. Consulta la tabella seguente per una panoramica dei set di dati di riepilogo con le seguenti informazioni:

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


* Cosa rappresenta ogni riga in un set di dati di riepilogo.

| Set di dati di riepilogo<br/>Tipo evento<br/>Suffisso componente | Entità<br/>Raggruppamento | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | Ogni riga rappresenta |
|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | Ad<br/>none | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | Prestazioni giornaliere di un annuncio senza raggruppamenti demografici o geografici. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Ad<br/>age, gender | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | Prestazioni giornaliere di un annuncio<br/>suddivise per età e genere. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Ad<br/> paese | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | Prestazioni giornaliere di un annuncio<br/>suddivise per paese e area geografica. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Esperienza<br>piattaforma, posizione | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | Prestazioni giornaliere associate<br/>all&#39;esperienza creativa di un annuncio<br/>suddivise per piattaforma e posizione. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | Risorsa<br/>none | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | | | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | Prestazioni giornaliere a livello di risorsa<br/>nel contesto di annuncio/campagna<br/>senza suddivisione demografica o geografica. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | Età della risorsa <br/>, genere | ![Segno di spunta](/help/assets/icons2/Checkmark.svg) | | | | | Prestazioni giornaliere a livello di risorsa<br/>nel contesto di annunci/campagne<br/>suddivise per età e genere. |

Questa tabella descrive la copertura dei set di dati, non una garanzia che una particolare rete popola ogni campo di metriche o metadati. Controlla i campi necessari per l’analisi. Un campo non disponibile o un raggruppamento non supportato non corrisponde a un valore zero misurato per un campo.

Il raggruppamento dei dati di riepilogo riunisce dimensioni equivalenti; il raggruppamento non totalizza i sei totali della metrica delle prestazioni.

## Set di dati di ricerca

I set di dati di ricerca separati descrivono account, campagna, gruppo di annunci, annuncio, esperienza e risorsa. Forniscono nomi e metadati utilizzando GUID di entità. Non esiste alcuna associazione uno-a-uno tra i set di dati di riepilogo e i sei set di dati di ricerca.

I set di dati di ricerca condividono due blocchi predefiniti comuni:

* **Oggetto ID entità**: memorizza gli oggetti account, annuncio, gruppo di annunci, risorsa, campagna ed esperienza. Ogni oggetto contiene una chiave globale generata da Adobe e un ID nativo della piattaforma.
* **Metadati principali di media a pagamento**: archivia campi descrittivi comuni quali nome, stato, obiettivo, obiettivo di ottimizzazione, strategia di offerta, tipo di budget, valori di budget, valuta, fuso orario, stato del servizio, date, rete di annunci, canale, percorso gerarchico, rete e identificatori di portfolio.

| Set di dati di ricerca | Contenuti chiave |
|---|---|
| Ricerca account | Metadati a livello di account come nome, valuta, fuso orario, stato, limite di spesa e date di creazione |
| Ricerca campagna | Impostazioni della campagna per budget, pianificazione, targeting, tracciamento della conversione, attribuzione, posizionamenti, oggetti promossi, finalità e ID catalogo o store |
| Ricerca gruppo di annunci | Metadati del gruppo di annunci come collegamento della campagna, stato, budget, obiettivi di ottimizzazione e targeting |
| Ricerca annunci | Dettagli della creatività dell’annuncio come risorse, varianti, dimensioni, URL di tracciamento, call to action, corpo del testo, titoli, URL di destinazione, stato di consegna e stato di revisione |
| Ricerca risorse | Proprietà della risorsa come dimensioni, dettagli dei file, proprietà delle immagini, URL dei contenuti multimediali, metadati di utilizzo, metadati video, descrizione, sottotipo, titolo e tipo |
| Ricerca esperienza | Raggruppamenti creativi a livello di esperienza come ID esperienza, risorse, titolo, descrizione e call to action |


## Componenti

Una volta abilitato, il canale Content Analytics Paid media genera anche una serie di componenti di visualizzazione dati. Questi componenti sono forniti con un suffisso per distinguere tra loro componenti denominati simili.

### Metriche

Reti di annunci diverse restituiscono diversi raggruppamenti delle prestazioni. Content Analytics mantiene tali distinzioni invece di trattare ogni versione di una metrica come intercambiabile.

Ad esempio:

| Componente | Significato | Analisi iniziale appropriata |
| --- | --- | --- |
| Clic \| Riepilogo annuncio | Clic segnalati al livello di nessun raggruppamento dell’annuncio | Prestazioni di campagne o annunci |
| Clic \| Riepilogo risorse | Clic segnalati a livello di risorsa | Prestazioni delle risorse Creative |
| Clic \| Ad Geo | Clic dal rapporto dell’area geografica dell’annuncio | Prestazioni per paese |
| Clic \| Posizionamento esperienza | Clic dal rapporto di posizionamento dell’esperienza | Prestazioni Creative per posizionamento |

Ciascun componente della metrica &quot;clic&quot; fornisce un contesto di reporting diverso. Non è possibile calcolare il totale di questi componenti metrici come totale complessivo. La stessa attività pubblicitaria sottostante può essere rappresentata in più set di dati di riepilogo.

### Dimensioni

Ogni set di dati di riepilogo contiene ID e GUID. L&#39;ID è l&#39;identità (per account, campagna, gruppo di annunci, annuncio, esperienza e risorsa) fornita dalla rete di annunci ed è univoco **all&#39;interno** dei dati della rete di annunci. Il GUID è un&#39;identità fornita da Adobe (per account, campagna, gruppo di annunci, annuncio, esperienza e risorsa) ed è univoco **in** reti di annunci. ID e GUID vengono utilizzati per cercare i nomi e i metadati corrispondenti.

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

### Esempi

Di seguito sono riportati alcuni esempi di come creare rapporti e analizzare le prestazioni dei supporti a pagamento e come combinare l’esperienza di Content Analytics e i dati delle risorse con i dati dei supporti a pagamento.

#### Prestazioni della campagna pubblicitaria

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

#### Identificazione degli annunci con prestazioni migliori

Desideri capire quali sono le migliori prestazioni degli annunci Meta?

Per effettuare un’indagine, utilizza ulteriori suddivisioni geografiche e demografiche. Utilizza Nome campagna o Nome annuncio come dimensione e utilizza le metriche come descritto nella tabella seguente. Ogni metrica ha lo stesso suffisso di componente.

| Metriche | Livello di reporting |
| --- | --- |
| Impression | Geo dell’annuncio |
| Clic | Geo dell’annuncio |
| Spesa | Riepilogo annuncio |
| Percentuale di click-through | Geo dell’annuncio |
| Costo per clic | Riepilogo annuncio |


#### Aggiungere dati multimediali a pagamento con i dati dell’evento esperienza

Unisci le prestazioni dei media a pagamento con i dati comportamentali sul sito per comprendere come le campagne e gli annunci sono associati al coinvolgimento, alle conversioni e ai ricavi del sito web. Ad esempio, confronta i clic e le spese della rete pubblicitaria con gli ordini attribuiti alle visite della stessa campagna.

Per configurare questo reporting, includi i set di dati di riepilogo dei file multimediali a pagamento e il set di dati dell’evento nel sito nella stessa connessione Customer Journey Analytics. Acquisisci identificatori stabili di campagne, annunci o risorse supportate dai parametri URL della pagina di destinazione o dai campi evento esistenti. Utilizza i campi derivati necessari per analizzare e mappare tali valori ai corrispondenti identificatori di elementi multimediali a pagamento, mantenendo la rete e il contesto dell’account richiesti. Usa gli identificatori come stringhe. Per associare le dimensioni evento e riepilogo corrispondenti, configura un gruppo di dati di riepilogo nella visualizzazione dati. L’abilitazione del canale Paid Media non configura automaticamente questa mappatura e tracciamento URL specifico per l’implementazione.


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
* Convalida l’origine delle visite con tag della campagna quando i parametri di tracciamento vengono riutilizzati tra i canali.


#### Confronto delle prestazioni delle campagne con gli ordini in loco

Un URL di pagina di destinazione può contenere diversi parametri di tracciamento. In questo esempio, l&#39;ID campagna in `utm_id` viene utilizzato per confrontare la spesa della campagna con gli ordini del sito Web.

https://www.example.com/offer?utm_source=facebook&utm_medium=paid_social&utm_campaign=autumn_offer&utm_id=120218706543980215

Parametro utilizzato per il confronto: `utm_id=120218706543980215`. Gli altri parametri descrivono l’etichetta di origine, il supporto e la campagna, ma non vengono utilizzati come campo corrispondente utilizzato in questo esempio.

Se l’URL viene acquisito nei dati dell’evento del sito web e sia il set di dati dell’evento del sito web che i set di dati a pagamento multimediali fanno parte della stessa connessione Customer Journey Analytics:

1. Identifica la campagna. Utilizza un campo derivato per leggere `utm_id` dall&#39;URL e mapparne il valore all&#39;identificatore della campagna corrispondente nei dati multimediali a pagamento.
1. Raggruppa le dimensioni corrispondenti. Nella visualizzazione dati, aggiungere la dimensione della campagna del sito Web alla dimensione della campagna a pagamento `Summary Data Group`, mantenendo tutti i membri esistenti.
1. Confrontare spese e ordini. In Analysis Workspace, utilizza la dimensione Campagna raggruppata come righe di una tabella a forma libera. Aggiungi `Ad Summary` spesa e sito Web `Orders` come colonne. Imposta il modello di attribuzione e l&#39;intervallo di lookback per `Orders`.


La tabella a forma libera mostra la spesa di rete degli annunci insieme agli ordini dei siti web attribuiti a ciascuna campagna. Due campagne con una spesa pubblicitaria simile hanno un numero diverso di azioni attribuite al sito web a valle. Utilizza questo confronto per identificare campagne ed esperienze di pagine di destinazione per ulteriori indagini o test, anziché valutare le prestazioni solo in base alle metriche pubblicitarie.

L’esempio utilizza un ID campagna, ma lo stesso approccio può utilizzare identificatori di gruppi di annunci, annunci o risorse quando è possibile acquisire valori corrispondenti. Gli attributi di Content Analytics, ad esempio **[!UICONTROL Colori primo piano risorse]**, consentono di confrontare le caratteristiche creative con le prestazioni dei supporti a pagamento. Con il tracciamento specifico delle risorse e le dimensioni degli attributi corrispondenti configurate tra entrambe le origini, puoi estendere il confronto agli ordini attribuiti del sito web e utilizzare i risultati per guidare il test creativo.

#### Combinare le prestazioni delle risorse con i dati web

Se desideri creare rapporti e analizzare le prestazioni delle risorse in relazione agli investimenti in contenuti multimediali a pagamento, puoi aggiungere un parametro UTM specifico per le risorse nella configurazione di contenuti multimediali a pagamento per la rete di annunci. Ad esempio, oltre ai parametri dinamici standard come s`ite_source_name`, `campaign.id`, `adset.id` o `placement`, aggiungi parametri personalizzati statici, come `aca_asset_id=999999`.

Questo parametro personalizzato viene aggiunto all’URL della pagina di destinazione. Ad esempio: https://www.example.com/home.html?utm_content=120241705099850539%2Caca_asset_id%3D9999999%2Caca_placement%3DFacebook_Desktop_Feed&amp;aca_id_2=8888888&amp;utm_medium=paid&amp;utm_source=fb&amp;utm_id=120241705099830539&amp;utm_term=120241705099840539&amp;utm_campaign=120241705099830539

Ora esiste una relazione tra una risorsa su una pagina e i dati multimediali a pagamento. Utilizza questa relazione in Analysis Workspace per vedere in che modo i metadati delle risorse Content Analytics (ad esempio **[!UICONTROL Colori di primo piano risorse]**) contribuiscono al successo della campagna multimediale a pagamento.


<!--

Do we need to include the tables from the Wiki?

## Reference

The following table lists paid media fields, their XDM paths, provisioned components, and reporting visibility.

+++ Paid media fields

| Field name | XDM path | ACA Paid Media component | Provisioning status | Reporting visibility |
| --- | --- | --- | --- | --- |
| Ad Network | `paidMedia.adNetwork` | Ad Network (dimension) | existing | visible through shared grouping: Ad Network |
| Channel | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | existing | visible through shared grouping: Content Channel |
| Account GUID | `paidMedia.accountGUID` | Account GUID (dimension) | existing | visible through shared grouping: Account GUID |
| Campaign GUID | `paidMedia.campaignGUID` | Campaign GUID (dimension) | existing | visible through shared grouping: Campaign GUID |
| Ad Group GUID | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | existing | visible through shared grouping: AdGroup GUID |
| Ad GUID | `paidMedia.adGUID` | Ad GUID (dimension) | existing | visible through shared grouping: Ad GUID |
| Experience GUID | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | existing | visible through shared grouping: Experience Id |
| Asset GUID | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | existing | visible through shared grouping: Asset Id |
| Name | `paidMedia.metadata.name` | Ad Name (derived field)<br/>Ad Name (shared dimension)<br/>AdGroup Name (derived field)<br/>AdGroup Name (shared dimension)<br/>Asset Name (Paid Media) (derived field)<br/>Asset Name (Paid Media) (shared dimension)<br/>Campaign Name (derived field)<br/>Campaign Name (shared dimension)<br/>Experience Name (derived field)<br/>Experience Name (shared dimension) | existing | visible through shared grouping: Ad Name, AdGroup Name, Asset Name (Paid Media), Campaign Name, Experience Name |
| Status | `paidMedia.metadata.status` | Ad Status (derived field)<br/>Ad Status (shared dimension)<br/>Ad Group Status (derived field)<br/>Ad Group Status (shared dimension)<br/>Campaign Status (derived field)<br/>Campaign Status (shared dimension) | curated net-new | visible through shared grouping: Ad Status, Ad Group Status, Campaign Status |
| Serving Status | `paidMedia.metadata.servingStatus` | | excluded | missing provisioned component |
| Updated Time | `paidMedia.metadata.updatedTime` | | excluded | missing provisioned component |
| Account Name | `paidMedia.accountDetails.accountName` | Account Name (derived field)<br/>Account Name (shared dimension) | existing | visible through shared grouping: Account Name |
| Currency | `paidMedia.accountDetails.currency` | Account Currency (derived field)<br/>Account Currency (shared dimension) | curated net-new | visible through shared grouping: Account Currency |
| Timezone | `paidMedia.accountDetails.timezone` | Account Timezone (derived field)<br/>Account Timezone (shared dimension) | curated net-new | visible through shared grouping: Account Timezone |
| Account Type | `paidMedia.accountDetails.accountType` | Account Type (derived field)<br/>Account Type (shared dimension) | curated net-new | visible through shared grouping: Account Type |
| Business Name | `paidMedia.accountDetails.businessName` | Account Business Name (derived field)<br/>Account Business Name (shared dimension) | curated net-new | visible through shared grouping: Account Business Name |
| Campaign Type | `paidMedia.campaignDetails.campaignType` | Campaign Type (derived field)<br/>Campaign Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Type |
| Objective | `paidMedia.campaignDetails.objective` | Campaign Objective (derived field)<br/>Campaign Objective (shared dimension) | curated net-new | visible through shared grouping: Campaign Objective |
| Is Automated Campaign | `paidMedia.campaignDetails.isAutomatedCampaign` | Campaign Is Automated \| Ad Summary (derived field) | curated net-new | hidden |
| Bid Strategy | `paidMedia.campaignDetails.budgetSettings.bidStrategy` | Campaign Bid Strategy (derived field)<br/>Campaign Bid Strategy (shared dimension) | curated net-new | visible through shared grouping: Campaign Bid Strategy |
| Budget Type | `paidMedia.campaignDetails.budgetSettings.budgetType` | Campaign Budget Type (derived field)<br/>Campaign Budget Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Budget Type |
| Daily Budget | `paidMedia.campaignDetails.budgetSettings.dailyBudget` | Campaign Daily Budget (derived field)<br/>Campaign Daily Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Daily Budget |
| Lifetime Budget | `paidMedia.campaignDetails.budgetSettings.lifetimeBudget` | Campaign Lifetime Budget (derived field)<br/>Campaign Lifetime Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Lifetime Budget |
| Campaign Budget Optimization | `paidMedia.campaignDetails.budgetSettings.isCampaignBudgetOptimization` | Campaign Budget Optimization \| Ad Summary (derived field) | curated net-new | hidden |
| Catalog ID | `paidMedia.campaignDetails.catalogId` | Campaign Catalog ID \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.campaignDetails.startTime` | Campaign Start Time (derived field)<br/>Campaign Start Time (shared dimension) | curated net-new | visible through shared grouping: Campaign Start Time |
| End Time | `paidMedia.campaignDetails.endTime` | Campaign End Time (derived field)<br/>Campaign End Time (shared dimension) | curated net-new | visible through shared grouping: Campaign End Time |
| Ad Group Type | `paidMedia.adGroupDetails.adGroupType` | Ad Group Type (derived field)<br/>Ad Group Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Type |
| Bid Strategy Type | `paidMedia.adGroupDetails.budgetSettings.bidStrategyType` | Ad Group Bid Strategy Type (derived field)<br/>Ad Group Bid Strategy Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Bid Strategy Type |
| Optimization Goal | `paidMedia.adGroupDetails.optimizationSettings.optimizationGoal` | Ad Group Optimization Goal (derived field)<br/>Ad Group Optimization Goal (shared dimension) | curated net-new | visible through shared grouping: Ad Group Optimization Goal |
| Delivery Status | `paidMedia.adGroupDetails.deliverySettings.deliveryStatus` | Ad Group Delivery Status \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.adGroupDetails.startTime` | Ad Group Start Time (derived field)<br/>Ad Group Start Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group Start Time |
| End Time | `paidMedia.adGroupDetails.endTime` | Ad Group End Time (derived field)<br/>Ad Group End Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group End Time |
| Ad Type | `paidMedia.adDetails.adType` | Ad Type (derived field)<br/>Ad Type (shared dimension) | curated net-new | visible through shared grouping: Ad Type |
| Delivery Status | `paidMedia.adDetails.deliveryStatus` | Ad Delivery Status (derived field)<br/>Ad Delivery Status (shared dimension) | curated net-new | visible through shared grouping: Ad Delivery Status |
| Review Status | `paidMedia.adDetails.reviewStatus` | Ad Review Status (derived field)<br/>Ad Review Status (shared dimension) | curated net-new | visible through shared grouping: Ad Review Status |
| Creative Type | `paidMedia.adDetails.creative.paidMediaCreative.creativeType` | Ad Creative Type (derived field)<br/>Ad Creative Type (shared dimension) | curated net-new | visible through shared grouping: Ad Creative Type |
| Title | `paidMedia.adDetails.creative.paidMediaCreative.title` | Ad Title (derived field)<br/>Ad Title (shared dimension) | curated net-new | visible through shared grouping: Ad Title |
| Call to Action | `paidMedia.adDetails.creative.paidMediaCreative.callToAction` | Ad Call to Action (derived field)<br/>Ad Call to Action (shared dimension) | curated net-new | visible through shared grouping: Ad Call to Action |
| Destination URL | `paidMedia.adDetails.creative.paidMediaCreative.destinationURL` | Ad Destination URL (derived field)<br/>Ad Destination URL (shared dimension) | curated net-new | visible through shared grouping: Ad Destination URL |
| Display URL | `paidMedia.adDetails.creative.paidMediaCreative.displayURL` | Ad Display URL (derived field)<br/>Ad Display URL (shared dimension) | curated net-new | visible through shared grouping: Ad Display URL |
| Experience Type | `paidMedia.experienceDetails.experienceType` | Experience Type (derived field)<br/>Experience Type (shared dimension) | curated net-new | visible through shared grouping: Experience Type |
| Landing Page URL | `paidMedia.experienceDetails.landingPageURL` | Experience Landing Page URL (derived field)<br/>Experience Landing Page URL (shared dimension) | curated net-new | visible through shared grouping: Experience Landing Page URL |
| Call To Action | `paidMedia.experienceDetails.callToAction` | Experience Call to Action (derived field)<br/>Experience Call to Action (shared dimension) | curated net-new | visible through shared grouping: Experience Call to Action |
| Card Count | `paidMedia.experienceDetails.carouselProperties.cardCount` | Experience Card Count \| Ad Summary (derived field) | curated net-new | hidden |
| Asset Type | `paidMedia.assetDetails.assetType` | Asset Type (derived field)<br/>Asset Type (shared dimension) | curated net-new | visible through shared grouping: Asset Type |
| Permalink URL | `paidMedia.assetDetails.mediaProperties.permalinkURL` | Asset Permalink URL \| Ad Summary (derived field) | curated net-new | hidden |
| Width | `paidMedia.assetDetails.dimensions.width` | Asset Width (derived field)<br/>Asset Width (shared dimension) | curated net-new | visible through shared grouping: Asset Width |
| Height | `paidMedia.assetDetails.dimensions.height` | Asset Height (derived field)<br/>Asset Height (shared dimension) | curated net-new | visible through shared grouping: Asset Height |
| Aspect Ratio | `paidMedia.assetDetails.dimensions.aspectRatio` | Asset Aspect Ratio (derived field)<br/>Asset Aspect Ratio (shared dimension) | curated net-new | visible through shared grouping: Asset Aspect Ratio |
| Orientation | `paidMedia.assetDetails.dimensions.orientation` | Asset Orientation \| Ad Summary (derived field)<br/>Asset Orientation (shared dimension) | curated net-new | visible through shared grouping: Asset Orientation |
| MIME Type | `paidMedia.assetDetails.fileProperties.mimeType` | Asset MIME Type \| Ad Summary (derived field) | curated net-new | hidden |
| Impressions | `paidMedia.metrics.impressions` | Impressions \| Ad Summary (metric) | existing | visible |
| Clicks | `paidMedia.metrics.clicks` | Clicks \| Ad Summary (metric) | existing | visible |
| Spend | `paidMedia.metrics.spend` | Spend \| Ad Summary (metric) | existing | visible |
| Reach | `paidMedia.metrics.reach` | Reach \| Ad Summary (metric) | curated net-new | visible |
| Conversions | `paidMedia.metrics.conversions` | Conversions \| Ad Summary (metric) | curated net-new | visible |
| Conversion Value | `paidMedia.metrics.conversionValue` | Conversion Value \| Ad Summary (metric) | curated net-new | visible |
| Video Views | `paidMedia.metrics.videoViews` | Video Views \| Ad Summary (metric) | curated net-new | visible |
| Engagements | `paidMedia.metrics.engagements` | Engagements \| Ad Summary (metric) | curated net-new | visible |
| Post-Click Conversions | `paidMedia.conversionMetrics.postClickConversions` | Post-Click Conversions \| Ad Summary (metric) | curated net-new | visible |
| Post-View Conversions | `paidMedia.conversionMetrics.postViewConversions` | Post-View Conversions \| Ad Summary (metric) | curated net-new | visible |
| Purchases | `paidMedia.conversionMetrics.conversionsByType.purchases` | Purchases \| Ad Summary (metric) | curated net-new | visible |
| Add to Cart | `paidMedia.conversionMetrics.conversionsByType.addToCart` | Add to Cart \| Ad Summary (metric) | curated net-new | visible |
| Leads | `paidMedia.conversionMetrics.conversionsByType.leads` | Leads \| Ad Summary (metric) | curated net-new | visible |
| Registrations | `paidMedia.conversionMetrics.conversionsByType.registrations` | Registrations \| Ad Summary (metric) | curated net-new | visible |
| Downloads | `paidMedia.conversionMetrics.conversionsByType.downloads` | Downloads \| Ad Summary (metric) | curated net-new | visible |
| Subscriptions | `paidMedia.conversionMetrics.conversionsByType.subscriptions` | Subscriptions \| Ad Summary (metric) | curated net-new | visible |
| Landing Page View | `paidMedia.conversionMetrics.conversionsByType.landingPageView` | Landing Page Views \| Ad Summary (metric) | curated net-new | visible |
| Total Order Value | `paidMedia.conversionMetrics.totalOrderValue` | Total Order Value \| Ad Summary (metric) | curated net-new | visible |
| Video Plays | `paidMedia.videoMetrics.videoPlays` | Video Plays \| Ad Summary (metric) | curated net-new | visible |
| Video Completions | `paidMedia.videoMetrics.videoCompletions` | Video Completions \| Ad Summary (metric) | curated net-new | visible |
| Link Clicks | `paidMedia.extendedMetrics.linkClicks` | Link Clicks \| Ad Summary (metric) | curated net-new | visible |
| Outbound Clicks | `paidMedia.extendedMetrics.outboundClicks` | Outbound Clicks \| Ad Summary (metric) | curated net-new | visible |
| App Installs | `paidMedia.extendedMetrics.appInstalls` | App Installs \| Ad Summary (metric) | curated net-new | visible |
| Lead Submissions | `paidMedia.extendedMetrics.leadSubmissions` | Lead Submissions \| Ad Summary (metric) | curated net-new | visible |
| Device Type | `paidMedia.dimensionalBreakdowns.deviceType` | | excluded | removed in source range |
| Placement | `paidMedia.dimensionalBreakdowns.placement` | Placement (dimension) | curated net-new | visible through shared grouping: Placement |
| Platform | `paidMedia.dimensionalBreakdowns.platform` | Platform (dimension) | curated net-new | visible through shared grouping: Platform |
| Country | `paidMedia.dimensionalBreakdowns.country` | Country (dimension) | curated net-new | visible through shared grouping: Country |
| Region | `paidMedia.dimensionalBreakdowns.region` | Region (dimension) | curated net-new | visible through shared grouping: Region |
| Other connector-populated fields | See field tables | No named component | excluded | not surfaced |

+++

### Identifiers

| Field name | Description | XDM path | ACA Paid Media component | ACA context label | Meta | Google Ads | Pinterest | Snapchat | TikTok |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Record ID | *Unique record URI, inherited from data/record.* | `@id` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (pinterest:&lt;entity&gt;: source-derived composite record ID; GUIDs use pinterest_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (snapchat:&lt;entity&gt;: source-derived composite record ID; GUIDs use snapchat_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (tiktok:&lt;entity&gt;: source-derived composite record ID; GUIDs use tiktok_; summary IDs omit dimension values; writer emits _id.) |
| Entity Type | The type of paid media entity | `entityType` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) |
| Ad Network | The advertising platform/network | `paidMedia.adNetwork` | Ad Network (dimension) | Ad Network | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads`) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Network | Alias of adNetwork for migration from GenStudio templates | `paidMedia.network` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Channel | Content channel indicating the source of the data (e.g., Web, Mobile, PaidMedia). Used as a reporting dimension for cross-channel breakdowns. | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | Content Channel (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) |
| Hierarchy Path | Full hierarchical path showing parent-child relationships (e.g., account_id/campaign_id/adgroup_id/ad_id) | `paidMedia.hierarchyPath` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account ID | Unique identifier for the ad account within the network | `paidMedia.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Unique identifier for the ad account across all networks | `paidMedia.accountGUID` | Account GUID (dimension) | Account Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign ID | Unique identifier for the campaign within the network | `paidMedia.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign GUID | Unique identifier for the campaign across all networks | `paidMedia.campaignGUID` | Campaign GUID (dimension) | Campaign Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group ID | Unique identifier for the ad group/ad set/ad squad within the network | `paidMedia.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group GUID | Unique identifier for the ad group/ad set/ad squad across all networks | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | AdGroup Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad ID | Unique identifier for the individual ad within the network | `paidMedia.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad GUID | Unique identifier for the individual ad across all networks | `paidMedia.adGUID` | Ad GUID (dimension) | Ad Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Experience ID | Unique identifier for creative experience (multi-asset compositions) within the network | `paidMedia.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Ad ID on Experience lookup and summaries; null on Ad lookup; asset reverse join recovers ad ID when metadata matches.) |
| Experience GUID | Unique identifier for creative experience (multi-asset compositions) across all networks | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | Experience Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset ID | Unique identifier for creative assets (images, videos, etc.) within the network | `paidMedia.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset GUID | Unique identifier for creative assets (images, videos, etc.) across all networks | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | Asset Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Account GUID (class entityIDs hierarchy) | `entityIDs.account.accountGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Account ID | Account ID (class entityIDs hierarchy) | `entityIDs.account.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign GUID | Campaign GUID (class entityIDs hierarchy) | `entityIDs.campaign.campaignGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign ID | Campaign ID (class entityIDs hierarchy) | `entityIDs.campaign.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group GUID | Ad Group GUID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group ID | Ad Group ID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad GUID | Ad GUID (class entityIDs hierarchy) | `entityIDs.ad.adGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad ID | Ad ID (class entityIDs hierarchy) | `entityIDs.ad.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience GUID | Experience GUID (class entityIDs hierarchy) | `entityIDs.experience.experienceGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience ID | Experience ID (class entityIDs hierarchy) | `entityIDs.experience.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset GUID | Asset GUID (class entityIDs hierarchy) | `entityIDs.asset.assetGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset ID | Asset ID (class entityIDs hierarchy) | `entityIDs.asset.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group Name | Display name of the ad group/ad set/ad squad. Mirrors metadata.name from the ad group lookup. | `paidMedia.denormalizedNames.adGroupName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad group name"))`) | | |
| Ad Name | Display name of the individual ad. Mirrors metadata.name from the ad lookup. | `paidMedia.denormalizedNames.adName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad name"))`) | | |
| Campaign Name | Display name of the campaign. Mirrors metadata.name from the campaign lookup. | `paidMedia.denormalizedNames.campaignName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Campaign name"))`) | | |

-->
