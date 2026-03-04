---
title: Casi di utilizzo dell’analisi del pubblico
description: Scopri i casi d’uso per Audience Analysis.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 974d8a269be15d3ea6fbbcf96f2ab5457d9c9554
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 1%

---

# Casi di utilizzo dell’analisi del pubblico {#analyze-audiences-use-cases}

Audience Analysis consente di generare rapporti sui dati di iscrizione del pubblico di Experience Platform in Customer Journey Analytics. Ciò si ottiene tramite configurazioni gestite tramite la procedura guidata Configurazioni analisi del pubblico, che consente di determinare quale set di dati di profilo stai acquisendo, insieme ad altri parametri e dettagli di configurazione. (Per informazioni di panoramica più dettagliate, vedi [Panoramica di Audience Analysis](/help/connections/audience-analysis/audience-analysis-overview.md). )

Questo documento include esempi di casi d’uso che evidenziano il valore fornito da Audience Analysis. Prima di rivedere i casi di utilizzo, acquisisci familiarità con le considerazioni sulla generazione di rapporti riportate di seguito. È importante tenere presenti queste considerazioni durante l’analisi dei casi d’uso, in quanto potrebbero influire sull’output finale dei rapporti.

## Considerazioni sul reporting

La versione iniziale di Audience Analysis stabilisce le basi essenziali necessarie per l’elaborazione e l’acquisizione dei tipi di pubblico di Experience Platform in Customer Journey Analytics. Durante l’analisi, è importante tenere presenti diversi fattori che possono influenzare i risultati dei progetti Workspace:

* **I dati di iscrizione al pubblico sono accurati solo per il giorno precedente (&quot;ieri&quot;)**: i dati di iscrizione al pubblico conterranno sempre il set di dati più recente dello snapshot del profilo generato da Unified Profile Service. Questo set di dati di profilo è un’istantanea giornaliera ed è accurato solo per il giorno precedente (&quot;ieri&quot;), con la rigenerazione automatica e la rielaborazione ogni notte. Le dimensioni del pubblico sono disponibili per i rapporti e i raggruppamenti, non per la ricostruzione degli stati storici del pubblico.

   * Esempio: Indipendentemente dall’intervallo di tempo di reporting scelto, il pubblico CJA da segnalare rispetterà sempre lo stato di iscrizione al pubblico presente nell’ultima istantanea del profilo acquisita (&quot;ieri&quot;).

      * L’allargamento dell’intervallo di tempo di reporting agli &quot;ultimi 30 giorni&quot;, ad esempio, includerà più eventi e darà l’impressione che la dimensione del pubblico stia cambiando. Tuttavia, la composizione del profilo del pubblico corrisponderà sempre all’istantanea di &quot;ieri&quot; indipendentemente dall’intervallo di tempo scelto.

* **Le dimensioni devono avere un evento corrispondente per essere incluse**: le dimensioni di Audience Analysis possono essere analizzate solo dove esistono eventi corrispondenti in CJA. Se un comportamento, un canale o un momento del ciclo di vita non è rappresentato come evento nella connessione CJA, non può essere analizzato.

   * Esempio: un pubblico utilizzato per il targeting di persone con un annuncio includerebbe molte più persone nel pubblico di RTCDP che in quello di CJA. Questo perché il pubblico di CJA è limitato alle persone che hanno avuto un evento in CJA durante il periodo di reporting.

* **La risoluzione dell&#39;identità si basa esclusivamente su un singolo spazio dei nomi**: la risoluzione dell&#39;identità dipende interamente dallo spazio dei nomi dell&#39;identità selezionato come parte della configurazione di Audience Analysis. L’analisi sarà limitata a tale spazio dei nomi di identità, con gli eventi che non rientrano in esso che non saranno disponibili per i rapporti di analisi del pubblico.

   * Esempio: per un set di dati evento unito che combina CRM ed ECID e la configurazione di Audience Analysis utilizza l’ID del sistema di gestione delle relazioni con i clienti, solo le righe contenenti un ID del sistema di gestione delle relazioni con i clienti verranno riconosciute come parte del pubblico da segnalare in CJA. Pertanto, la dimensione del pubblico risultante potrebbe essere inferiore al previsto.

## Casi d’uso di esempio

### Caso d’uso 1

Scopri il comportamento di un pubblico specifico in un dato canale (ad esempio, web o app), per rispondere a domande come:

* _&quot;Cosa stanno facendo al momento i membri dei potenziali clienti con valori elevati sul sito (pagine, funzionalità, funnel)?&quot;_

* _&quot;Quali campagne e contenuti sono sovraindicizzati per questo pubblico rispetto a tutti gli altri?&quot;_

#### Flusso di configurazione

1. Configurare Audience Analysis in CJA per un singolo spazio dei nomi di identità (ad esempio, ECID o CRM_ID) e una visualizzazione dati incentrata sul web.

   * In questo modo, i dati di iscrizione del pubblico verranno acquisiti automaticamente nella connessione scelta tramite l’esportazione giornaliera delle istantanee del profilo

   * È consigliabile selezionare lo spazio dei nomi delle identità che ritieni abbia la maggiore copertura nel set di dati dell’evento

1. Crea i tuoi progetti Workspace per:

   * Suddividi il Nome del pubblico per pagina, prodotto, campagna, dispositivo, ecc.

   * Confronta pubblico e non pubblico (o con un altro pubblico) su metriche quali sessioni, tasso di conversione, ricavi per persona.

1. Inserisci informazioni sulle strategie di ottimizzazione del canale (ad esempio, regole di targeting, contenuti o ottimizzazione delle offerte).

#### Considerazioni sulla risoluzione delle identità

| Caso d’uso | Domanda aziendale di base | Considerazione sulla risoluzione dell’identità | Organizzazioni con autenticazione elevata/spazio dei nomi singolo (eventi già al di sotto di 1 ID persona, ad esempio login /CRM) | Organizzazioni con più spazi dei nomi e frammenti (eventi in ECID + CRM + altri) |
|---------|----------|---------|---------|---------|
| Approfondimento del comportamento del pubblico nello stato corrente | _&quot;Cosa sta facendo il pubblico X nel canale Y in questo momento?&quot; (pagine, funnel, contenuto, offerte)_ | Per una copertura ottimale, gli eventi e i profili devono condividere uno spazio dei nomi di identità coerente nella connessione CJA e nella configurazione di Audience Analysis. | La maggior parte delle attività è già associata a un ID di accesso/gestione delle relazioni con i clienti, pertanto i tipi di pubblico di AEP si uniscono in modo chiaro ai dati comportamentali in CJA. <p>Ottieni una visione chiara di ciò che ogni pubblico sta facendo in un dato canale con un minimo di gap di reporting previsto.</p> | Anche quando si unisce con un set di dati unito, il reporting sarà ancora vincolato al singolo spazio dei nomi dell’identità scelto nella configurazione. <p>Se alcuni clienti esistono con altri ID, il loro comportamento non verrà incluso e questo può causare una visualizzazione parziale durante la generazione del rapporto.</p> |

### Caso d’uso 2

Aiuta gli addetti al marketing o i designer di percorso a capire quali tipi di pubblico si sovrappongono, in modo da poter deduplicare le esperienze ed evitare conflitti tra le offerte delle diverse campagne:

* _&quot;Quanta sovrapposizione c&#39;è oggi tra membri fedeltà, abbandoni del carrello e alta propensione all&#39;abbandono?&quot;_

* _&quot;Quali tipi di pubblico hanno maggiori probabilità di entrare in conflitto con le offerte promozionali di alto valore questa settimana?&quot;_

#### Flusso di configurazione

1. Configura l’analisi del pubblico in CJA per un singolo spazio dei nomi dell’identità allineato all’attivazione di RTCDP/AJO (ad esempio, CRM_ID se i percorsi sono basati sulle persone).

   * In questo modo, i dati di iscrizione del pubblico verranno acquisiti automaticamente nella connessione scelta tramite l’esportazione giornaliera delle istantanee del profilo.

   * Questa può essere utilizzata per arricchire una visualizzazione dati esistente che potenzia già i rapporti chiave di coinvolgimento e conversione.

1. Utilizza il modello predefinito Panoramica dell’analisi del pubblico e le visualizzazioni di sovrapposizione:

   * Esegui intersezioni di pubblico e visualizzazioni di sovraindicizzazione/sottoindicizzazione (ad esempio, % di abbandoni del carrello che sono anche in Oro fedeltà).

   * Le sezioni si sovrappongono per dimensioni principali (ad esempio tipo di dispositivo, interesse del prodotto) per capire dove contano di più i conflitti.

1. Utilizza le informazioni per mettere a punto aspetti critici, come:

   * Regole di conflitto di offerte o regole di azione di marketing in RTCDP e AJO.

   * Ottimizzazione del pubblico (ad esempio, restringimento delle definizioni dei target in caso di sovrapposizione troppo elevata).

#### Considerazioni sulla risoluzione delle identità

| Caso d’uso | Domanda aziendale di base | Considerazione sulla risoluzione dell’identità | Organizzazioni con autenticazione elevata/spazio dei nomi singolo (eventi già al di sotto di 1 ID persona, ad esempio login /CRM) | Organizzazioni con più spazi dei nomi e frammenti (eventi in ECID + CRM + altri) |
|---------|----------|---------|---------|---------|
| Sovrapposizione del pubblico e rilevamento delle collisioni | _&quot;Quali tipi di pubblico si sovrappongono oggi in modo da evitare conflitti tra offerte?&quot;_ | La sovrapposizione viene calcolata solo per i tipi di pubblico che utilizzano lo stesso ID persona e con l’attività nella connessione CJA. | Poiché la maggior parte delle attività è già associata a un singolo ID di accesso/CRM, questo dovrebbe fornire una mappa di sovrapposizione affidabile tra i tipi di pubblico. <p>I grafici di sovrapposizione forniscono un’immagine affidabile di quali tipi di pubblico si scontrano e dove applicare eliminazioni o regole di priorità.</p> | Se alcune parti del percorso risiedono con altri ID (ad esempio, navigazione anonima solo ECID, ID call center), questi eventi non verranno visualizzati nell’analisi di sovrapposizione. <p>Le persone possono ancora esistere in più spazi dei nomi.</p><p>La sovrapposizione sarà basata sullo spazio dei nomi dell’identità incluso nella configurazione. Se alcuni profili sono ancora suddivisi tra ID, la sovrapposizione potrebbe causare rapporti meno frequenti sulle collisioni vere.</p> |

### Caso d’uso 3

Scopri il comportamento dei clienti che hanno lasciato di recente un pubblico chiave e quello che hanno fatto intorno a tale uscita, per rispondere a domande come:

* _&quot;Chi ha appena lasciato un pubblico chiave e cosa hanno fatto per uscire?&quot;_

* _&quot;Cosa è successo immediatamente prima di uscire? (errori, coinvolgimento ridotto, variazioni di prezzo).&quot;_

#### Flusso di configurazione

1. Configura Audience Analysis in CJA per un singolo spazio dei nomi di identità (ad esempio, CRM_ID o ID di accesso) e per le visualizzazioni dati rilevanti (web, app, CRM, ecc.).

   * In questo modo i dati di iscrizione del pubblico vengono acquisiti automaticamente nella connessione scelta tramite l’esportazione giornaliera delle istantanee dei profili.

   * È consigliabile selezionare lo spazio dei nomi delle identità che ritieni abbia la maggiore copertura nel set di dati dell’evento.

1. Nel modello Audience Analysis / Audience overview (fisso su _ieri_), utilizza:

   * Membri attuali: che è ancora nel pubblico

   * Pubblico in uscita: chi è partito ieri

1. Crea i tuoi progetti Workspace per:

   * Filtra i profili usciti ieri da Audience X e osserva:

      * Il loro comportamento che porta all’uscita (ultime sessioni, errori, esposizione a prezzi/offerte, mix di canali).

      * Il loro comportamento post-uscita (hanno cambiato i prodotti, effettuato il downgrade, sono rimasti inattivi).

   * Suddividi la coorte uscita per area geografica, dispositivo, struttura e livello di valore per trovare tasche ad alto impatto.

1. Utilizza le informazioni approfondite per gli aggiornamenti di percorso e le configurazioni dei tipi di pubblico di recupero in RTCDP o AJO.

#### Considerazioni sulla risoluzione delle identità

| Caso d’uso | Domanda aziendale di base | Considerazione sulla risoluzione dell’identità | Organizzazioni con autenticazione elevata/spazio dei nomi singolo (eventi già al di sotto di 1 ID persona, ad esempio login /CRM) | Organizzazioni con più spazi dei nomi e frammenti (eventi in ECID + CRM + altri) |
|---------|----------|---------|---------|---------|
| Tipi di pubblico in uscita - Analisi dell’abbandono | _&quot;Chi ha appena lasciato un pubblico chiave?&quot;_ <p>_&quot;Cosa hanno fatto all&#39;uscita?&quot;_</p> | L’uscita dal pubblico viene tracciata sullo stesso ID persona utilizzato per la connessione e la configurazione del pubblico. | Le uscite misurate su un ID di accesso/gestione delle relazioni con i clienti stabile tendono a riflettere la vera modifica comportamentale. <p>Quando qualcuno abbandona un pubblico con questo ID, in genere si tratta di una modifica reale (abbandono, downgrade, inattività).</p><p>Puoi analizzarne il comportamento recente per mettere a punto con sicurezza i percorsi e le offerte di recupero.</p> | Le uscite sono visibili solo dove profili ed eventi condividono l’ID configurato e quindi richiedono un’interpretazione attenta.<p>Utilizza le coorti in uscita come segnale o suggerimento forte, ma è consigliabile effettuare un controllo incrociato con altri punti dati prima di prendere decisioni critiche.</p> |

