---
title: Panoramica sui filtri
description: Scopri i filtri utilizzati e come creare un filtro semplice.
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Panoramica sui filtri

Analisi del percorso del cliente consente di creare, gestire, condividere e applicare potenti filtri per l&#39;audience ai rapporti. I filtri consentono di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni con siti Web. I filtri sono progettati come approfondimenti codificati dell&#39;audience che puoi creare in base alle tue esigenze specifiche, e quindi verificare, modificare e condividere con altri membri del team.

I filtri possono essere basati su attributi (tipo di browser, dispositivo, numero di visite, paese, genere), interazioni (campagne, ricerca di parole chiave, motore di ricerca), uscite e voci (visitatori da Facebook, una pagina di destinazione definita, dominio di provenienza), variabili personalizzate (campo modulo, categorie definite, ID cliente) e altri criteri.

Potete creare e salvare i filtri nel generatore di filtri oppure generare filtri da una visualizzazione Abbandono (in Workspace). Inoltre, i filtri possono essere utilizzati insieme come filtri sovrapposti.

>[!IMPORTANT]
I filtri sono noti come &quot;segmenti&quot; in Adobe Analytics. Abbiamo rinominato i segmenti in filtri perché Adobe Experience Platform ha una definizione diversa di &quot;segmento&quot;. Un segmento in AEP si riferisce a...

Il filtro include [Filter Builder](/help/components/filters/create-filters.md) per creare filtri ed eseguire un test preliminare, e [Filter Manager](/help/components/filters/manage-filters.md) per raccogliere, assegnare tag, approvare, impostare la protezione e condividere i filtri all&#39;interno dell&#39;organizzazione.

## Filtri sequenziali

I filtri sequenziali consentono di identificare i visitatori in base alla navigazione e alla visualizzazione della pagina nel sito, fornendo un filtro di azioni e interazioni definite. I segmenti sequenziali consentono di identificare cosa piace a un visitatore e cosa evita. Quando si creano filtri sequenziali, l&#39;operatore THEN viene utilizzato per definire e ordinare la navigazione dei visitatori.

Ecco un esempio:

![](assets/sequential_fil.png)

| Visita uno | Visita due | Visita tre |
|---|---|---|
| Il visitatore è andato alla pagina di destinazione principale (A), ha escluso la pagina della campagna (B), quindi ha visualizzato la pagina Prodotto (C). | Il visitatore è nuovamente passato alla pagina di destinazione principale (A), ha escluso la pagina della campagna (B), è tornato nuovamente alla pagina Prodotto (C) e quindi a una nuova pagina (D). | Il visitatore è entrato e ha seguito lo stesso percorso della prima e della seconda visita, quindi esclusa la pagina F per passare direttamente a una pagina di prodotto di destinazione (G). |

## Filtra contenitori

I filtri si basano su una gerarchia a livello di Persona, Sessione ed Evento che utilizza un modello contenitore nidificato. I contenitori nidificati consentono di definire gli attributi e le azioni delle persone in base alle regole tra e all&#39;interno dei contenitori.

>[!NOTE]
>Il contenitore Persona era precedentemente noto come Contenitore visitatori. Il contenitore Sessione era denominato Contenitore Visita e il contenitore Evento era il contenitore Hit.

Un filtro imposta le condizioni per filtrare un visitatore in base agli attributi o alle interazioni con il sito. Per impostare le condizioni in un filtro, impostate le regole per filtrare i visitatori in base alle caratteristiche e/o alle caratteristiche di navigazione del visitatore. Per suddividere ulteriormente i dati dei visitatori, puoi filtrare in base a visite e/o hit di visualizzazione della pagina specifici per ciascun visitatore. Il Generatore di filtri fornisce un&#39;architettura semplice per creare questi sottoinsiemi e applicare le regole come contenitori nidificati, gerarchici Persona, Sessione o Evento.

L’architettura del contenitore utilizzata nel Generatore filtri definisce la Persona come contenitore più esterno, contenente i dati generali specifici per il visitatore per visite e visualizzazioni di pagina. Un contenitore di sessione nidificato consente di impostare regole per suddividere i dati del visitatore in base alle sessioni, mentre un contenitore di eventi nidificato consente di suddividere le informazioni del visitatore in base alle singole viste di pagina. Ogni contenitore consente di eseguire rapporti nella cronologia di un visitatore, interazioni suddivise per sessioni, o di suddividere singoli eventi.

### Contenitore persona

Il contenitore Persona include ogni visita e visualizzazione di pagina per i visitatori entro un intervallo di tempo specificato. Un filtro a livello di Persona restituisce la pagina che soddisfa la condizione più tutte le altre pagine visualizzate dal visitatore (e che è vincolata solo da intervalli di date definiti). Come contenitore più ampio, i report generati a livello di contenitore Persona restituiranno le visualizzazioni di pagina per tutte le visite e consentono di generare un&#39;analisi per più visite. Di conseguenza, il contenitore Persona è il contenitore più suscettibile a modifiche in base a intervalli di date definiti.
I contenitori delle persone possono includere valori basati sulla cronologia generale di un visitatore:

* Giorni precedenti al primo acquisto

* Pagina di entrata originale

* Domini di riferimento originali

### Contenitore sessione

Il contenitore Sessione consente di identificare le interazioni di pagina, le campagne o le conversioni per una sessione specifica. Il contenitore Sessione è il contenitore più comunemente utilizzato perché acquisisce i comportamenti per l&#39;intera sessione di visita una volta soddisfatta la regola e consente di definire quali sessioni includere o escludere nella creazione e nell&#39;applicazione di un segmento. Può essere utile per rispondere a queste domande:

* Quanti visitatori hanno visualizzato la sezione news e sport nella stessa sessione?

* Quali pagine hanno contribuito alla conversione di una vendita?

I contenitori di sessione includono valori basati sull&#39;occorrenza per sessione:

* Numero sessione

* Pagina di entrata

* Restituisci frequenza

* Metriche di partecipazione

* Metriche allocate lineari

### Contenitore evento

Il contenitore Evento definisce gli eventi di pagina da includere o escludere da un filtro. Si tratta dei contenitori più stretti disponibili per identificare clic specifici e visualizzare la pagina dove una condizione è vera, consentendo di visualizzare un singolo codice di tracciamento o di isolare il comportamento all’interno di una particolare sezione del sito. È inoltre possibile identificare un valore specifico quando si verifica un&#39;azione, ad esempio il canale di marketing al momento dell&#39;ordine.

I contenitori degli eventi includono valori basati su singole analisi di pagina:

* Prodotti

* Proprietà elenco

* Elenca le dimensioni

* Dimensioni del merchandising (nel contesto degli eventi)