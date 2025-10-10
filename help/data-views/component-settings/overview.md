---
title: Impostazioni dei componenti
description: Visualizzare le impostazioni di base di un componente vista dati.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: aa635d52007a3032d8c3f90a779d1b70213dee9e
workflow-type: tm+mt
source-wordcount: '3701'
ht-degree: 54%

---

# Impostazioni dei componenti {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="Impostazioni dei componenti"
>abstract="Visualizza e configura nome, descrizione e altre impostazioni relative a un componente. Seleziona questa casella affinché il componente non sia visibile nei rapporti per utenti non amministratori. Gli amministratori possono comunque accedere al componente selezionando **[!UICONTROL Show all components]** in un progetto Workspace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="Etichette di contesto"
>abstract="La rimozione di un’etichetta di contesto può influire su pannelli o rapporti specifici in cui il componente è richiesto."

<!-- markdownlint-enable MD034 -->


Le informazioni seguenti descrivono le impostazioni utilizzate da un componente di visualizzazione dati.

![Impostazioni dei componenti descritte in questa sezione](../assets/component-settings.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Component type] | Obbligatorio. Consente di cambiare un componente da Metrica a Dimension o viceversa. Modificando questa selezione a discesa, il componente viene spostato nella rispettiva area dei componenti inclusi. |
| [!UICONTROL Component name] | Obbligatorio. Consente di specificare il nome descrittivo visualizzato in Analysis Workspace. È possibile rinominare un componente per assegnargli un nome specifico per la vista dati. |
| [!UICONTROL Description] | Facoltativo ma consigliato. Fornisce informazioni sul componente ad altri utenti. |
| [!UICONTROL Tags] | Facoltativo. Consente di assegnare al componente tag personalizzati o predefiniti per facilitarne la ricerca e il filtraggio nell’interfaccia utente di Analysis Workspace. |
| [!UICONTROL Context labels] | Facoltativo. Menu a discesa delle [etichette di contesto](#context-labels) disponibili definite dal sistema che è possibile applicare a un componente. |
| [!UICONTROL Schema field name] | Nome del campo schema. |
| [!UICONTROL Dataset type] | Obbligatorio. Un campo non modificabile che mostra il tipo di set di dati (evento, ricerca o profilo) da cui proviene il componente. |
| [!UICONTROL Dataset] | Un campo non modificabile che mostra da quale set di dati proviene il componente. Questo campo può contenere più set di dati. |
| [!UICONTROL Schema type] | Campo non modificabile che mostra il tipo di dati del componente. Anche se è possibile utilizzare qualsiasi tipo di campo di schema supportato in Platform, non tutti i tipi di campi sono supportati in Customer Journey Analytics. Sono supportati i seguenti tipi di dati: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String`e `Boolean`. Al momento, nei set di dati di ricerca è consentito solo il tipo di dati schema `String`. |
| [!UICONTROL Component ID] | Obbligatorio. L’[API Customer Journey Analytics](https://www.adobe.io/cja-apis/docs) utilizza questo campo per fare riferimento al componente. Ogni componente in una visualizzazione dati deve essere univoco. Adobe genera automaticamente un ID per ogni componente; tuttavia, puoi fare clic sull’icona di modifica e modificare l’ID del componente. La modifica dell’ID del componente interrompe tutti i progetti Workspace esistenti che contengono questo componente. Sebbene ogni componente abbia bisogno di un ID univoco in una singola visualizzazione dati, puoi usare lo stesso ID componente in altre visualizzazioni dati. Se utilizzi lo stesso ID componente in altre visualizzazioni dati, puoi rendere i progetti Workspace compatibili tra le visualizzazioni dati. <br/>Per i componenti basati su profilo e ricerca, l’ID componente ha un prefisso ID basato su quello del set di dati (ad esempio: `642b28fcc1f0ee1c074265a0.person.name.firstName`). Se desideri riutilizzare un profilo o un componente basato sulla ricerca, ad esempio `person.name.firstName` nel progetto Workspace, configurando questo componente in diverse visualizzazioni dati, assicurati di rinominare l’ID componente in modo univoco (ad esempio: `myUniqueID.person.name.firstName`) nelle visualizzazioni dati. |
| [!UICONTROL Path] | Obbligatorio. Un campo non modificabile che mostra il percorso dello schema da cui proviene il componente. |
| [!UICONTROL Data Usage Labels] | Tutte le etichette di utilizzo dei dati assegnate a questo componente in Adobe Experience Platform. [Ulteriori informazioni](/help/data-views/data-governance.md). |
| [!UICONTROL Hide component in reporting] | Consentono di eliminare il componente dalla visualizzazione dati per i non amministratori. Gli amministratori possono comunque accedervi facendo clic su [!UICONTROL Show All Components] in un progetto Analysis Workspace. |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

Per un video demo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Impostazioni del tipo di componente](https://video.tv.adobe.com/v/333112/?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


## Etichette di contesto

Le etichette di contesto sono tag definiti dal sistema applicati ai componenti all’interno di una visualizzazione dati. Quando le etichette di contesto vengono applicate ai componenti (dimensioni o metriche), Customer Journey Analytics è istruito a utilizzare automaticamente questi componenti con etichetta di contesto in determinate visualizzazioni o funzioni.

Le etichette di contesto consentono di fornire contesto semantico a singole parti di dati.  In generale, Customer Journey Analytics non deve necessariamente conoscere il significato semantico di una dimensione o metrica per eseguire l’analisi.  Tuttavia, alcune situazioni (modelli di progetto e alcune visualizzazioni selezionate) richiedono che Customer Journey Analytics comprenda il significato semantico per eseguire un certo tipo di analisi. Le etichette di contesto vengono create per tali situazioni.

Le etichette di contesto funzionano a livello di componente (dimensione o metrica) e offrono al cliente una grande flessibilità all’interno della visualizzazione dati. Ad esempio, puoi assegnare un’etichetta di contesto a una dimensione dopo aver applicato diverse trasformazioni di post-elaborazione a un campo. Oppure a una dimensione basata su un campo derivato.  Le etichette di contesto forniscono un livello di astrazione sopra i componenti e i campi.

Per motivi di praticità, le etichette di contesto predefinite intelligenti vengono applicate automaticamente ai componenti in base ai campi con un percorso XDM specifico. Ad esempio, l&#39;etichetta di contesto **[!UICONTROL Commerce: Product Category]** viene applicata automaticamente a una dimensione **[!UICONTROL Category name]** basata sul percorso dello schema `productListItems.productCategories.categoryName`. Tuttavia, puoi spostare l’etichetta di contesto in un componente diverso senza alcun problema.

Per semplificare i modelli di progetto forniti da Adobe, diverse integrazioni (come Journey Optimizer, Content Analytics e altro) impostano le visualizzazioni dati in cui i componenti predefiniti sono costruiti in un modo specifico. E le etichette di contesto appropriate vengono applicate automaticamente. Di nuovo, puoi semplicemente spostare una qualsiasi di queste etichette di contesto in altri componenti creati nella visualizzazione dati e viene utilizzato il componente personalizzato.

Le etichette di contesto sono importanti anche per la divulgazione dei modelli di progetto. I modelli di progetto realizzano rapidamente le basi per la generazione di rapporti per diversi casi d’uso specifici. Tuttavia, non tutti i modelli hanno senso per ogni visualizzazione dati e non desideri mostrare modelli non applicabili. Le etichette di contesto vengono utilizzate per mostrare i modelli a seconda che le etichette di contesto siano incluse o meno nella visualizzazione dati selezionata.  Puoi semplicemente aggiungere più etichette di contesto alla visualizzazione dati (componenti) e rendere disponibili più modelli. In alternativa, rimuovi le etichette di contesto per nascondere modelli specifici.

>[!NOTE]
>
>È possibile applicare più etichette di contesto a un componente, ma non è possibile applicare un’etichetta di contesto a più componenti all’interno di una visualizzazione dati.
>

I vantaggi delle etichette di contesto sono:

* **Comodità**: non è necessario selezionare nuovamente lo stesso componente in ogni pannello o visualizzazione.
* **Sblocca funzionalità**: alcune visualizzazioni (come [Mappa](/help/analysis-workspace/visualizations/map.md)) richiedono informazioni sul componente latitudine e longitudine. L’assegnazione di etichette di contesto rivela tali informazioni alla visualizzazione.
* **Coerenza**: tutti gli utenti dell&#39;organizzazione che lavorano su uno o più progetti basati su una visualizzazione dati che utilizza le etichette di contesto ottengono lo stesso comportamento.
* **Visibilità delle funzionalità e dei modelli**: alcune visualizzazioni e funzionalità vengono visualizzate solo quando viene assegnata l&#39;etichetta di contesto appropriata. Ad esempio:

   * Una visualizzazione [Mappa](/help/analysis-workspace/visualizations/map.md) viene visualizzata correttamente solo se Customer Journey Analytics conosce i componenti che rappresentano latitudine e longitudine.
   * I [modelli](/help/analysis-workspace/templates/use-templates.md) specifici sono visibili solo quando vengono applicate le etichette di contesto corrette e i componenti associati diventano disponibili.

Le etichette di contesto possono essere necessarie nelle seguenti situazioni:

* Per definire un set di componenti, puoi utilizzare nei rapporti sulla sperimentazione utilizzando il [Pannello Sperimentazione](/help/analysis-workspace/c-panels/experimentation.md) nei progetti Analysis Workspace.

  Per ulteriori informazioni, consulta [Integrare con Journey Optimizer](/help/integrations/ajo.md#data-view) e [Reportistica di destinazione](/help/integrations/at.md).

* Per definire un set di componenti, puoi utilizzare la visualizzazione [Mappa](/help/analysis-workspace/visualizations/map.md) nei progetti Analysis Workspace.

  Per ulteriori informazioni, vedere [Aggiungere etichette di contesto nelle visualizzazioni dati](/help/analysis-workspace/visualizations/map.md#add-context-labels-in-data-views) in [Mappa](/help/analysis-workspace/visualizations/map.md).

  **Nota**: la visualizzazione Mappa si trova nella fase Test limitati del rilascio e potrebbe non essere ancora disponibile nell&#39;ambiente.

* Per visualizzare [modelli forniti da Adobe](/help/analysis-workspace/templates/use-templates.md). Alcuni modelli forniti da Adobe potrebbero non funzionare perché alcuni componenti non sono presenti nella visualizzazione dati.

  Per ogni componente mancante, nella visualizzazione dati è disponibile un’etichetta di contesto corrispondente. È necessario aggiungere l’etichetta di contesto corrispondente a un componente già presente nella visualizzazione dati. In alternativa, è necessario aggiungere un nuovo componente alla visualizzazione dati e aggiungere l’etichetta di contesto al componente (se non è già stata fornita automaticamente).

  Per ulteriori informazioni, consulta [Aggiungere componenti mancanti alla visualizzazione dati per un modello specificato](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) nell’articolo [Creare e gestire modelli](/help/analysis-workspace/templates/create-templates.md).


Sono disponibili i seguenti gruppi di etichette di contesto, ciascuno con un elenco di etichette di contesto specifiche.

+++ Campaign

| Nome | Descrizione |
|------|-------------|
| Codice di tracciamento | Codice di tracciamento. |
| Istanze del codice di tracciamento | Tracciamento delle istanze di codice. |

+++

+++ Commerce

| Nome | Descrizione |
|------|-------------|
| Aggiunte carrello | Aggiunte carrello |
| Aperture carrello | Il carrello si apre. |
| Rimozioni carrello | Rimozioni carrello |
| Visualizzazioni carrello | Visualizzazioni carrello |
| Pagamenti | Pagamenti. |
| Ordini | Ordini. |
| Prodotto | Prodotto. |
| Categoria del prodotto | Categoria di prodotto. |
| Visualizzazioni prodotto | Visualizzazioni di prodotti. |
| Ricavi | Ricavi. |
| Negozio | Archivia. |
| Unità | Unità. |

+++

+++ Sperimentazione

| Nome | Descrizione |
|------|-------------|
| Sperimentazione | Un esperimento è un insieme di varianti di un’esperienza che sono state esposte agli utenti finali per determinare quale è meglio mantenere per sempre. |
| Variante della sperimentazione | Variante è una delle due o più modifiche nell’esperienza di un utente finale che vengono confrontate allo scopo di identificare l’alternativa migliore. |

+++

+++ Media

| Nome | Descrizione |
|------|-------------|
| ID contenuto | ID contenuto. |
| Tempo trascorso dei contenuti | Tempo trascorso dei contenuti. |
| Episodio | Episodio. |
| Tipo evento | Tipo di evento. |
| Tempo trascorso dei contenuti multimediali | Tempo trascorso dei contenuti multimediali. |
| Stagione | Stagione. |
| Secondi trascorsi dall’ultima chiamata | Secondi trascorsi dall&#39;ultima chiamata. |
| Spettacolo | Mostra. |
| Ora di inizio | Ora di inizio. |
| Durata totale buffer | Durata totale buffer. |
| Durata totale pausa | Durata totale pausa. |
| Lunghezza video | Lunghezza video. |
| Nome del video | Nome video. |

+++

+++ Call center

| Nome | Descrizione |
|------|-------------|
| Nome call center | Nome del call center. |
| Costi delle chiamate | Costi di chiamata. |
| Orari di chiamata | Orario di chiamata. |
| Durata della chiamata | Lunghezza della chiamata. |
| Motivo della chiamata | Motivo della chiamata. |
| Punteggio sondaggio sulle chiamate | Punteggio sondaggio chiamata. |
| Chiamate | Chiamate. |

+++

+++ Demografico

| Nome | Descrizione |
|------|-------------|
| Genere | Genere. |

+++

+++ Ambiente

| Nome | Descrizione |
|------|-------------|
| Browser | Browser. |
| Tipo di browser | Tipo di browser. |
| Lingua | Lingua. |
| Sistema operativo | Sistema operativo. |
| Gruppo di sistemi operativi | Gruppo di sistemi operativi. |
| Nome del sistema operativo | Nome del sistema operativo. |

+++

+++ Generale

| Nome | Descrizione |
|------|-------------|
| Nome azione | Nome azione. |
| Azioni | Azioni. |
| Canale di interazione | Canale di interazione. |

+++

+++ Geo

| Nome | Descrizione |
|------|-------------|
| Città per area geografica | Città geografica. |
| Paese per area geografica | Paese geografico. |
| Dma per area geografica | Geo dma. |
| Regione Geo | Area geografica. |
| Latitudine | Latitudine. |
| Longitudine | Longitudine. |
| Punto di interesse | Punto di interesse. |
| Stato | Stato. |

+++

+++ Canale di marketing

| Nome | Descrizione |
|------|-------------|
| Canale di primo contatto | Canale di primo contatto. |
| Dettagli del canale di primo contatto | Dettaglio del canale di primo contatto. |
| Canale di ultimo contatto | Canale di ultimo contatto. |
| Dettaglio del canale di ultimo contatto | Dettaglio canale ultimo contatto. |
| Canale di marketing | Canale di marketing. |

+++

+++ Mobile

| Nome | Descrizione |
|------|-------------|
| ID applicazione | ID applicazione. |
| Operatore telefonia mobile | Operatore mobile. |
| Arresti anomali dei dispositivi mobili | Arresti anomali del dispositivo mobile. |
| Nome dispositivo mobile | Nome del dispositivo mobile. |
| Tipo di dispositivo mobile | Tipo di dispositivo mobile. |
| Nome del messaggio in-app sul dispositivo mobile | Nome del messaggio mobile in-app. |
| Installazioni dei dispositivi mobili | Installazioni per dispositivi mobili. |
| Avvii dai dispositivi mobili | Avvii di dispositivi mobili. |
| Dispositivo mobile - Produttore | Produttore di dispositivi mobili. |
| Annullamento dei messaggi mobili | Il messaggio mobile si annulla. |
| Clic sui messaggi mobili | Clic su messaggio mobile. |
| Impression dei messaggi mobili | Impression dei messaggi mobili. |
| Consenso push dei messaggi mobili | Messaggio push opt-in per dispositivi mobili. |
| Nome del messaggio push del dispositivo mobile | Nome del messaggio push mobile. |
| Aggiornamenti dei dispositivi mobili | Aggiornamenti per dispositivi mobili. |
| Tempo trascorso per azione temporizzata | Tempo trascorso per azione temporizzata. |

+++

+++ Ricerca

| Nome | Descrizione |
|------|-------------|
| Motore di ricerca | Motore di ricerca. |
| Parola chiave del motore di ricerca | Parola chiave del motore di ricerca. |
| Motore di ricerca naturale | Motore di ricerca naturale. |
| Parola chiave naturale del motore di ricerca | Parola chiave naturale del motore di ricerca. |
| Motore di ricerca a pagamento | Motore di ricerca a pagamento. |
| Parola chiave a pagamento del motore di ricerca | Parola chiave a pagamento del motore di ricerca. |

+++

+++ Sondaggio

| Nome | Descrizione |
|------|-------------|
| Sondaggio | Sondaggio. |
| Risposta al sondaggio | Risposta al sondaggio. |
| Completamenti sondaggio | Completamento sondaggio. |
| Domanda del sondaggio | Domanda del sondaggio. |
| Inizio del sondaggio | Inizia il sondaggio. |

+++

+++ Web

| Nome | Descrizione |
|------|-------------|
| Tempo medio di pagina | Tempo medio della pagina. |
| Messaggi non recapitati | Rimbalzi. |
| Pagina di ingresso | Pagina di ingresso. |
| Pagina di uscita | Esci dalla pagina. |
| Pagina | Pagina. |
| Visualizzazioni pagina | Visualizzazioni di pagina. |
| Pagina di provenienza | Referrer. |
| Tipo di destinatario che inoltra | Tipo di referrer. |
| Dominio di riferimento | Dominio di riferimento. |
| Dominio di riferimento originale | Dominio di riferimento originale. |
| Ricariche | Ricarica. |
| Visite a pagina singola | Visite a pagina singola. |
| Sezione sito | Sezioni del sito. |

+++

+++ B2B

| Nome | Descrizione |
|------|-------------|
| Nome account | Nome account. |
| Nome gruppo acquisti | Nome gruppo di acquisto |
| Nome dell’opportunità | Nome opportunità |

+++

+++ Content Analytics

| Nome | Descrizione |
|------|-------------|
| Posizione assoluta sinistra della risorsa | Risorsa Assoluta a sinistra. |
| Posizione assoluta in alto della risorsa | Assoluto risorsa superiore. |
| Attributi delle risorse | Attributi risorsa. |
| Colori di sfondo della risorsa | Colori di sfondo risorsa. |
| Posizioni fotocamera della risorsa | Posizioni delle videocamere degli asset. |
| Prossimità fotocamera della risorsa | Prossimità fotocamera risorsa. |
| Impostazioni della fotocamera della risorsa | Impostazioni fotocamera risorse. |
| Clic su risorsa | Clic su risorsa. |
| Risorsa creata da | Risorsa creata da. |
| Data di creazione della risorsa | Data di creazione risorsa.e |
| Altezza visualizzazione della risorsa | Altezza di visualizzazione risorsa. |
| Larghezza visualizzazione della risorsa | Larghezza visualizzazione risorsa. |
| Colori di primo piano della risorsa | Colori di primo piano risorse. |
| ID risorsa | ID risorsa. |
| Tipi di immagine della risorsa | Tipi di immagini risorse. |
| Ultimo aggiornamento della risorsa di | Ultimo aggiornamento risorsa. |
| Data ultimo aggiornamento della risorsa | Data ultimo aggiornamento risorsa. |
| Condizioni di illuminazione della risorsa | Condizioni di illuminazione delle risorse. |
| URL del collegamento della risorsa | URL collegamento risorsa. |
| Nome della risorsa | Nome risorsa. |
| Categorie di persone della risorsa | Categorie di risorse umane. |
| ID percezione risorsa | Identificatore univoco di risorse che sono percettivamente identiche. |
| Stili fotografici della risorsa | Stili fotografia risorsa. |
| Scene della risorsa | Scene risorse. |
| Origine risorsa | Asset Source. |
| Tag della risorsa | Tag risorsa. |
| Tipo di risorsa | Tipo risorsa. |
| Visualizzazioni risorsa | Visualizzazioni risorse. |
| Distribuzione attenzione visiva della risorsa | Distribuzione dell’attenzione visiva della risorsa. |
| Densità contenuto visivo della risorsa | Densità del contenuto visivo della risorsa. |
| Attributi per esperienze | Attributi esperienza. |
| Canale di esperienza | Canale esperienza. |
| Clic dell’esperienza | Clic sull’esperienza. |
| Conteggio delle emoji dell’esperienza | Conteggio Emoji Esperienza. |
| Conteggio hashtag dell’esperienza | Conteggio degli hashtag esperienza. |
| Profondità orizzontale dell’esperienza in percentuale | Profondità percentuale orizzontale esperienza. |
| Parole chiave dell’esperienza | Parole chiave esperienza. |
| Emozioni marketing dell’esperienzia | Emozioni di Experience Marketing. |
| Narrazioni dell’esperienza | Narrative dell’esperienza. |
| Strategie di persuasione dell’esperienza | Strategie di persuasione dell’esperienza. |
| Conteggio parole per frase leggibilità esperienza | Conteggio delle parole per frase per la leggibilità dell’esperienza. |
| Punteggio di leggibilità dell’esperienza | Punteggio di leggibilità dell’esperienza. |
| Conteggio leggibilità frasi dell’esperienza | Conteggio delle frasi di leggibilità dell’esperienza. |
| Conteggio leggibilità parole vuote dell’esperienza | Conteggio parole non consentite di lettura dell’esperienza. |
| Conteggio virgolette nel testo della leggibilità dell’esperienza | Conteggio delle virgolette di testo di leggibilità dell’esperienza. |
| Conteggio parole di leggibilità dell’esperienza | Conteggio parole leggibilità esperienza. |
| Origine dell’esperienza | Experience Source. |
| Toni dell’esperienza | Toni esperienza. |
| Profondità verticale dell’esperienza in percentuale | Profondità percentuale verticale esperienza. |
| Visualizzazioni dell’esperienza | Visualizzazioni esperienza. |

+++

+++ Journey Optimizer

| Nome | Descrizione |
|------|-------------|
| Errore di azione (AJO) | Numero di errori generati dalle azioni del percorso. |
| Errore di esecuzione azione | Condizione di errore che impediva alla fase di esecuzione del percorso di eseguire l’azione. |
| Etichetta azione (AJO) | Il nome visualizzato generato dal cliente dell’elemento con cui l’utente finale ha interagito. |
| Uscite alternative (AJO) | Numero di uscite che non si sono verificate perché un profilo ha raggiunto un nodo finale o è fallito a causa di un errore. |
| Installazioni app (AJO) | Numero di installazioni dell’app. |
| Avvii app (AJO) | Numero di volte in cui un’app mobile viene avviata. |
| ID batch (AJO) | GUID creato alla chiamata di ogni nuova istanza batch per un Percorso pianificato o un’Azione campagna. Ad esempio: se un Percorso pianificato o un’azione di campagna viene eseguita alle 08:00 e alle 00:00, saranno presenti due batchInstanceID diversi. |
| Marca temporale istanza batch (AJO) | Marca temporale dell’istanza batch. |
| Mancati recapiti per canali in uscita (obsoleti) | Numero totale di messaggi non recapitati tra i canali in uscita. |
| Nome azione campagna (AJO) | Nome dell’azione della campagna. |
| ID campagna (AJO) | ID del set di dati. |
| Nome campagna (AJO) | Nome della campagna. |
| ID versione campagna (AJO) | ID versione della campagna. |
| Canale | Canale a cui devono essere correlati i dati. |
| Clic (AJO) | Numero totale di clic su tutti i canali. |
| Rifiuti del criterio di consenso (AJO) | Numero di azioni di percorso rifiutate a causa di uno o più criteri di consenso. |
| Errore della decisione sul contenuto (AJO) | Messaggi di errore generati dai nodi decisionali sul contenuto del percorso. |
| Errori della decisione sul contenuto (AJO) | Conteggio degli errori generati dai nodi decisionali sul contenuto del percorso. |
| Nome del nodo decisionale sul contenuto (AJO) | Nome del nodo decisionale del contenuto del percorso. |
| ID correlazione | ID correlazione. |
| Numero di offerte (AJO) | Il numero di elementi dell’offerta nella proposta. |
| Chiave di associazione dell’elemento decisionale | Identificatore composito che combina l’ID elemento con l’ID richiesta di Experience Decisioning, consentendo la persistenza dei dati tra le interazioni. |
| Provider di decisioni (AJO) | Provider a cui è stato chiesto di prendere la decisione. Questa dimensione viene utilizzata quando più servizi possono prendere decisioni per lo stesso posizionamento o attività. |
| Provider di decisioni (persistente) (AJO) | Il provider di decisioni con associazione di persistenza abilitata. |
| ID criterio decisione (AJO) | ID del criterio di decisione utilizzato per decidere quali elementi includere nella proposta. |
| Metrica deduplica (AJO) | Metrica di deduplicazione. |
| Consegnato (obsoleto) | Numero totale di messaggi consegnati. |
| Visualizzazioni (AJO) | Il conteggio mostra i messaggi di AJO. Questo conteggio include le aperture e-mail, le visualizzazioni web e le visualizzazioni in app. Le piattaforme mobili non segnalano la visualizzazione di SMS e messaggi push, pertanto non sono conteggiate. |
| Ignorato (AJO) | Conta ogni volta che il messaggio inApp viene chiuso dall’SDK di Adobe, indipendentemente dall’azione scelta dall’utente finale per chiuderlo. |
| ID prova (AJO) | Identificatore univoco per la prova. |
| Aperture e-mail bot (AJO) | Numero totale di aperture di e-mail eseguite dai bot. |
| Aperture e-mail (AJO) | Numero totale di aperture di e-mail. |
| Dominio destinatario e-mail (AJO) | Dominio dell’indirizzo e-mail. |
| Oggetto dell’e-mail | Oggetto e-mail, non personalizzato. |
| ID evento | Identificatore univoco per l’evento di serie temporali. |
| ID criteri di uscita (AJO) | ID dei criteri di uscita utilizzati per determinare se il percorso deve uscire. |
| Nome criteri di uscita (AJO) | Nome dei criteri di uscita. |
| ID esperimento (AJO) | ID della sperimentazione. |
| Nome sperimentazione (AJO) | Nome della sperimentazione. |
| Numero di offerte di fallback (AJO) | Il numero di offerte di fallback. |
| Errore di recupero | Condizione di errore che impediva alla fase di esecuzione del percorso di eseguire il recupero. |
| Clic in entrata (AJO) | Numero totale di clic tra i canali in entrata. |
| Ignorazioni in entrata (AJO) | Numero totale di ignoramenti tra i canali in entrata. |
| Impression in entrata (AJO) | Numero totale di impression tra i canali in entrata. |
| Invii in entrata (AJO) | Numero totale di invii tra canali in entrata. |
| Attivato in entrata (AJO) | La proposta è stata scelta per essere visualizzata dall’SDK di Adobe. Altri fattori possono impedirne l’effettiva visualizzazione. |
| È ottimizzato per l’ora di invio (AJO) | L’esecuzione del messaggio è ottimizzata per il tempo di invio? |
| È un percorso di test | L’evento fa parte di un’esecuzione del percorso di test? |
| È un messaggio di test (AJO) | Il messaggio viene inviato come esecuzione di test? |
| ID elemento (persistente) (AJO) | ID dell’elemento con associazione di persistenza abilitata. |
| ID elemento (AJO) | ID dell’elemento. |
| Nome elemento (AJO) | Nome dell&#39;elemento. |
| Nome elemento (persistente) (AJO) | Nome dell’elemento con associazione di persistenza abilitata. |
| Errore di azione del percorso (AJO) | Messaggi di errore generati dalle azioni del percorso. |
| Nome del nodo azione percorso | Nome del nodo dell&#39;azione di percorso. |
| Ingressi percorso | True se l’evento del passaggio è stato un evento di ingresso percorso per un profilo. |
| Fine percorso (AJO) | Fine del percorso. |
| Nome del nodo evento percorso | Questo valore viene impostato ogni volta che si verifica un segmento o un evento esterno in un percorso. |
| Motivo di esclusione da percorso | Motivo dell’esclusione dell’istanza del percorso. |
| Nome della regola di esclusione del percorso | Nome della regola che ha causato il rifiuto dell’ingresso nel percorso. |
| Esclusioni dal percorso (AJO) | Indicare se l&#39;evento del passaggio corrente ha provocato l&#39;eliminazione di un percorso per un profilo. Ciò si verifica in genere a causa dell’applicazione di regole di limitazione o concorrenza, che impediscono un’ulteriore progressione nel percorso. |
| Tipo di uscita dal percorso (AJO) | Tipo di uscita che si è verificata per l’istanza di percorso. |
| Errori percorso | Fornisce lo stato corrente del passaggio che ha completato l’esecuzione. |
| ID percorso | ID del percorso. |
| Nome del percorso | Nome del percorso. |
| Versione e nome del percorso | Versione e nome del percorso. |
| ID versione del percorso | ID del percorso. |
| JourneyExits | True se il passaggio corrente ha portato alla fine di un’istanza del percorso. Questo è l’ultimo passaggio di un percorso per un determinato profilo eseguito correttamente. |
| Conversioni della pagina di destinazione (AJO) | Numero totale di conversioni nella pagina di destinazione. |
| ID pagina di destinazione (AJO) | Identificatore univoco per pagina di destinazione. |
| Origine pagina di destinazione (AJO) | Origine della pagina di destinazione. |
| Visualizzazioni pagina di destinazione (AJO) | Numero totale di visualizzazioni nella pagina di destinazione. |
| Clic sulla pagina di destinazione (AJO) | Numero totale di clic sulla pagina di destinazione. |
| URL collegamento (AJO) | URL su cui l’utente ha fatto clic. |
| Motivo di mancato recapito messaggio | Motivo del mancato recapito del messaggio. |
| Motivo di errore messaggio (AJO) | Motivo dell’errore messaggio. |
| Motivo di esclusione messaggi (AJO) | Motivo di esclusione. |
| Categoria errore messaggio (AJO) | Categoria errore . |
| Motivo di errore messaggio (AJO) | Motivo dell’errore. |
| Tipo di errore messaggio (AJO) | Tipo di errore. |
| ID messaggio (AJO) | ID messaggio a cui devono essere correlati i dati. |
| Lingua del messaggio (AJO) | Lingua del messaggio. |
| Nome messaggio (AJO) | Nome del messaggio. |
| Nuovo tentativo messaggio (AJO) | Numero di tentativi. |
| Stato del messaggio (AJO) | Stato del messaggio (ad esempio inviato, non recapitato, errore, ecc.) |
| Tipo di messaggio (AJO) | Specifica se il messaggio è di marketing o transazionale. |
| Stato del feedback del messaggio (obsoleto) | Stato del feedback. |
| Ingressi nodo | True se l’evento del passaggio è stato un evento di ingresso al nodo per un profilo. |
| ID nodo | ID nodo del nodo del percorso. |
| Nome del nodo | Nome nodo del nodo del percorso. |
| Tipo di nodo | Tipo di nodo del nodo del percorso. |
| Namespace identità dell’azione campagna orchestrata (AJO) | Spazio dei nomi dell’identità dell’azione della campagna orchestrata. |
| Nome azione campagna orchestrata (AJO) | Nome dell’azione della campagna orchestrata. |
| ID nodo azione campagna orchestrata (AJO) | ID azione della campagna orchestrata. |
| ID campagna orchestrata (AJO) | ID della campagna orchestrata. |
| Nome campagna orchestrata (AJO) | Nome della campagna orchestrata. |
| ID versione campagna orchestrata (AJO) | ID versione della campagna orchestrata. |
| Clic in uscita (AJO) | Numero totale di clic tra i canali in uscita. |
| Errori in uscita (obsoleti) | Numero totale di messaggi con errori tra i canali in uscita. |
| Esclusioni in uscita (obsolete) | Numero totale di eventi di esclusione tra i canali in uscita. |
| Invii in uscita (obsoleti) | Numero totale di messaggi inviati tra i canali in uscita. |
| Punto di interesse | punto di interesse. |
| ID proposta (AJO) | ID della proposta. |
| Azioni personalizzate push (AJO) | Numero totale di azioni personalizzate nell’interazione push. |
| Interazioni push (AJO) | Numero di volte in cui un’app mobile viene avviata a causa di un’interazione di messaggio push diretto. |
| Piattaforma push (AJO) | Servizio provider push, ad esempio APNS o FCM. |
| Titolo push | Titolo push, non personalizzato. |
| ID strategia di classificazione (AJO) | L’ID della strategia di classificazione. |
| Nome del criterio di consenso rifiutato | Nome del criterio di consenso rifiutato corrispondente. |
| Numero di tentativi (AJO) | Quanti tentativi di invio sono stati eseguiti prima che un messaggio risultasse inviato o non riuscito. |
| Nome della regola | Nome della regola che ha causato il rifiuto dell’ingresso nel percorso. |
| Tipo di selezione (AJO) | Questo è il tipo di selezione utilizzato quando un elemento viene derivato come parte di una decisione. |
| Invii (obsoleti) | Numero totale di messaggi inviati su tutti i canali. |
| Messaggi SMS in entrata (AJO) | Risposta SMS in entrata, ad esempio stop, start, subscribe e così via. |
| Messaggi SMS in entrata (AJO) | Risposta SMS in entrata, ad esempio Interrompi, Avvia, Abbonati, ecc. |
| Tipo di messaggio SMS (AJO) | Provider SMS, ad esempio inbound, inboundReply o send. |
| Provider SMS (AJO) | Provider SMS, ad esempio Sinch o Twilio. |
| Segnalazione di spam (AJO) | Numero totale di reclami spam. |
| Nome strategia (AJO) | Nome della strategia. Il nome della strategia da cui è derivato l’elemento. |
| Nome della strategia (persistente) (AJO) | Nome della strategia con associazione di persistenza abilitata. |
| Aggiunte a elenco abbonamenti (AJO) | Numero totale di aggiunte a un elenco di iscrizioni. |
| ID elenco iscrizioni (AJO) | Identificatore univoco per l’elenco iscrizioni. |
| Rimozioni elenco abbonamenti (AJO) | Numero totale di rimozioni da un elenco di iscrizioni. |
| Superficie (AJO) | Superficie di canale su cui è stato visualizzato il messaggio. |
| Mirato (obsoleto) | Questo conteggio del numero di volte in cui una proposta è stata mirata a una persona. Numero di volte in cui una proposta è stata considerata per la visualizzazione a una persona. |
| Nome della regola di targeting (AJO) | Nome della regola di targeting. |
| Evento di test (AJO) | Evento di test. |
| Ora di inizio | Ora di inizio. |
| Durata totale buffer | Durata totale buffer. |
| Durata totale pausa | Durata totale pausa. |
| Tipo di traffico (AJO) | Il tipo di traffico di classificazione. |
| ID trattamento (AJO) | ID del trattamento selezionato per l’esperimento. |
| Nome trattamento (AJO) | Nome del trattamento per l’esperimento. |
| Visitatori univoci nell’esperimento (AJO) | I visitatori univoci nell’esperimento. |
| Abbonamenti annullati (AJO) | Numero totale di annullamenti di abbonamenti. |
| Etichetta URL (AJO) | Etichetta descrittiva dell’URL. |
| ID URL (AJO) | Identificatore univoco dell’URL su cui l’utente ha fatto clic. |

+++
