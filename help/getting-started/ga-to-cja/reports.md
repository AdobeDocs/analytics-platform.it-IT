---
title: Rapporti GA4 in Customer Journey Analytics
description: Trova l’equivalente Customer Journey Analytics per ogni sezione di rapporto GA4.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: c2d8f4a1-7b3e-4c9f-a5d2-8e1b6c3f9072
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 3202
ht-degree: 0%

---


# Rapporti GA4 in Customer Journey Analytics

Utilizza questa pagina come riferimento di ricerca quando sai quale rapporto GA4 stai esaminando e vuoi ricrearne l’equivalente approssimativo in Analysis Workspace. I rapporti sono organizzati in base alle sezioni di navigazione di GA4. Per scenari di reporting avanzati cross-channel che diventano disponibili dopo la migrazione dei dati GA a Customer Journey Analytics, consulta [Rapporto sui dati Google Analytics](/help/use-cases/third-party/ga/report.md).

## In tempo reale

+++In tempo reale

Il rapporto in tempo reale di GA4 mostra l’attività degli ultimi 30 minuti: gli utenti attivi, gli eventi che si attivano, dove si trovano gli utenti, cosa guida il traffico e su quali pagine si trovano.

Customer Journey Analytics non dispone di un’area separata per i rapporti in tempo reale. Genera invece un pannello in Analysis Workspace e abilita l&#39;interruttore **[!UICONTROL Aggiornamento in tempo reale]** (parte del pacchetto **Ultimate**) in modo che le visualizzazioni vengano aggiornate ogni minuto:

1. Crea un pannello [a forma libera](/help/analysis-workspace/c-panels/freeform-panel.md) (l&#39;interruttore funziona anche sui pannelli [Vuoto](/help/analysis-workspace/c-panels/blank-panel.md), [Attribuzione](/help/analysis-workspace/c-panels/attribution.md) e [Elemento successivo o precedente](/help/analysis-workspace/c-panels/next-previous.md)) con le dimensioni e le metriche che desideri monitorare. Per eseguire il mirroring delle schede in tempo reale di GA4, utilizza **[!UICONTROL Pagina]**, **[!UICONTROL Tipo evento]**, **[!UICONTROL Dominio di riferimento]** o **[!UICONTROL Paesi]** come dimensione, con **[!UICONTROL Sessioni]** come metrica.
2. Attiva l&#39;opzione **[!UICONTROL Aggiornamento in tempo reale]** e scegli un periodo compreso tra **[!UICONTROL Ultimi 15 minuti]** e **[!UICONTROL Ultime 24 ore]**. I dati sono limitati a una finestra continua di 24 ore e il pannello viene aggiornato ogni minuto per un massimo di 30 minuti.

Il reporting in tempo reale favorisce i dati a livello di evento e di sessione e non può utilizzare l&#39;unione, pertanto preferisci **[!UICONTROL Sessioni]** rispetto a **[!UICONTROL Persone]**. Consulta [Utilizzare il reporting in tempo reale](/help/components/real-time/use-real-time.md) per la procedura completa e [Panoramica sul reporting in tempo reale](/help/components/real-time/real-time.md) per i dettagli su adesione e latenza.

+++

## Acquisizione

+++Acquisizione utente (primo contatto)

Il rapporto di acquisizione utente di GA4 attribuisce ogni utente al canale, all’origine e al mezzo che lo ha portato al sito per la prima volta, utilizzando l’attribuzione di primo contatto.

In Analysis Workspace, applica un modello di attribuzione **[!UICONTROL Primo contatto]** alla dimensione **[!UICONTROL Canale di marketing]**. I canali di marketing devono essere configurati prima dell’uso. Vedi [Creare un campo derivato da un canale di marketing](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md).

1. Trascina la dimensione **[!UICONTROL Canale di marketing]** in una [[!UICONTROL tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Fare clic con il pulsante destro del mouse sull&#39;intestazione di una colonna di metriche e selezionare **[!UICONTROL Usa modello di attribuzione non predefinito]**.
3. Seleziona **[!UICONTROL Primo contatto]** con un intervallo di lookback appropriato per l&#39;analisi.

In alternativa, utilizza il pannello [[!UICONTROL Attribuzione]](/help/analysis-workspace/c-panels/attribution.md) per un confronto affiancato delle prestazioni del canale di primo e ultimo contatto.

+++

+++Acquisizione del traffico (basata su sessione)

Il rapporto di acquisizione del traffico di GA4 attribuisce ogni sessione al canale, all’origine e al supporto che l’ha avviata, utilizzando l’attribuzione basata sulla sessione. Puoi suddividerlo per gruppo di canali, origine/supporto, referrer o campagna predefiniti.

In Analysis Workspace, la dimensione **[!UICONTROL Canale di marketing]** con il modello di attribuzione **[!UICONTROL Ultimo contatto]** predefinito fornisce rapporti sui canali basati su sessione:

1. Trascina la dimensione **[!UICONTROL Canale di marketing]** in una [[!UICONTROL tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Trascina le metriche desiderate accanto alla metrica predefinita **[!UICONTROL Eventi]**.

I raggruppamenti di GA4 corrispondono alle seguenti dimensioni di Customer Journey Analytics:

* **Canale**: **[!UICONTROL Canale Di Marketing]**. Customer Journey Analytics non dispone di raggruppamenti di canali incorporati. Definirli come [campo derivato](/help/data-views/derived-fields/derived-fields.md) utilizzando il modello di funzione **[!UICONTROL Canali di marketing]** o trasferire regole da Adobe Analytics quando si utilizza il connettore di origine di Analytics (vedere [Utilizzare dimensioni del canale di marketing](/help/use-cases/aa-data/marketing-channels.md)).
* **Source / medium e referral**: **[!UICONTROL Dominio di riferimento]** e **[!UICONTROL Tipo referrer]**.
* **Campagna**: i parametri `utm_*` di GA4 non vengono raccolti automaticamente. Durante l&#39;implementazione è necessario mappare ogni parametro a un campo XDM prima che venga visualizzato come dimensione. Se i valori della campagna arrivano come codice di tracciamento, utilizza la dimensione **[!UICONTROL Codice di tracciamento]**.

+++

+++Percorsi di attribuzione e conversione

I rapporti di attribuzione di GA4 (in Advertising) mostrano come diversi canali contribuiscono alle conversioni e consentono il confronto dei modelli e l’analisi dei percorsi di conversione.

In Analysis Workspace, utilizza il pannello [[!UICONTROL Attribuzione]](/help/analysis-workspace/c-panels/attribution.md):

1. Seleziona l&#39;icona Pannelli e trascina un pannello **[!UICONTROL Attribuzione]** nell&#39;area di lavoro.
2. Trascina la dimensione **[!UICONTROL Canale di marketing]** nella casella **[!UICONTROL Aggiungi Dimension]**.
3. Trascina la metrica di conversione (ad esempio, un evento di acquisto) nella casella **[!UICONTROL Aggiungi metrica]**.
4. Seleziona **[!UICONTROL Genera]**.

Il [!UICONTROL pannello Attribuzione] genera una tabella di confronto dei modelli e una visualizzazione [!UICONTROL Flusso di canale] che mostra i percorsi principali seguiti dai visitatori prima della conversione. Seleziona **[!UICONTROL Aggiungi modello]** per confrontare più modelli di attribuzione contemporaneamente.

+++

## Coinvolgimento

+++Pagine e schermate

Il rapporto Pagine e schermate di GA4 mostra le metriche delle prestazioni per singole pagine e schermate dell’app.

In Analysis Workspace, trascina la dimensione **[!UICONTROL Pagina]** in una [[!UICONTROL tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) e aggiungi le metriche desiderate. Le metriche comuni includono **[!UICONTROL Sessioni]**, **[!UICONTROL Persone]**, **[!UICONTROL Percentuale non recapitate]** e **[!UICONTROL Tempo trascorso per sessione]**.

Per raggruppare le pagine in base alla struttura del percorso URL (ad esempio, `/blog/` o `/products/`), utilizzare la dimensione **[!UICONTROL Sezione sito]** se definita dall&#39;implementazione oppure creare un [campo derivato](/help/data-views/derived-fields/derived-fields.md) che analizza l&#39;URL della pagina con la funzione **[!UICONTROL Analisi URL]**. Se si mantiene un mapping pagina-sezione esplicito, un [set di dati di ricerca](/help/connections/standard-lookups.md) può fornire il raggruppamento.

+++

+++Pagine di destinazione

Il rapporto sulla pagina di destinazione di GA4 mostra su quali pagine gli utenti arrivano quando iniziano una sessione.

In Analysis Workspace, trascina la dimensione **[!UICONTROL Pagina di ingresso]** in una [[!UICONTROL tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). **[!UICONTROL Sessioni]** è la metrica più rilevante per questa dimensione.

+++

+++Eventi

Il rapporto Eventi di GA4 mostra quante volte ogni evento è stato attivato, con metriche a livello di evento.

In GA4, gli eventi hanno un nome e parametri facoltativi (ad esempio, evento `video_play` con parametro `video_title`). In Customer Journey Analytics, la dimensione standard per il nome dell&#39;evento è **[!UICONTROL Tipo evento]** (originato da `xdm.eventType`). I parametri evento sono mappati su altri campi XDM, i cui nomi dipendono dall’implementazione.

Trascina la dimensione **[!UICONTROL Tipo evento]** in una [[!UICONTROL Tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) per elencare tutti i tipi di evento, insieme alla metrica **[!UICONTROL Eventi]**.

+++

+++Eventi chiave (conversioni)

Il rapporto Eventi chiave di GA4 (precedentemente Conversioni) elenca ogni evento chiave per nome con il relativo conteggio, ovvero gli eventi contrassegnati come business-critical nella configurazione della proprietà GA4.

Customer Journey Analytics non ha un flag di &quot;evento chiave&quot;; ogni interazione è un evento, quindi non esiste un elenco predefinito di conversioni da aprire.

Per ricreare l&#39;elenco di conversioni di GA4 per nome, utilizzare **segmenti come righe**. Una [[!UICONTROL tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) non può posizionare una metrica nella posizione della riga, ma può posizionare un segmento in tale posizione:

1. Per ogni conversione, crea un segmento che isola i relativi eventi, ad esempio un segmento con ambito evento in cui `xdm.eventType` è uguale a `commerce.purchases`. Assegna un nome a ciascun segmento dopo la conversione che rappresenta (ad esempio, **Acquisti**).
2. Trascina ogni segmento di conversione nell&#39;area riga di una [!UICONTROL tabella a forma libera], una per riga.
3. Aggiungi la metrica **[!UICONTROL Eventi]** come colonna. Ogni riga mostra il conteggio della conversione, rispecchiando l’elenco di eventi chiave di GA4. Utilizza **[!UICONTROL Persone]** invece di contare i convertitori univoci.

Per aggiungere un tasso di conversione, crea una metrica calcolata (seleziona l&#39;icona **+** accanto all&#39;elenco delle metriche) definita come una metrica di conversione divisa per **[!UICONTROL Sessioni]** o **[!UICONTROL Persone]**.

Ogni conversione isolata qui può essere definita anche come metrica riutilizzabile nella visualizzazione dati. Per informazioni su come configurare questa impostazione, consulta la voce **Eventi chiave → Metriche evento personalizzate** in [Metriche comuni](#common-metrics).

+++

## Monetizzazione

+++Acquisti e-commerce

Il rapporto sugli acquisti e-commerce di GA4 mostra i dati di acquisto a livello di prodotto, inclusi gli articoli, i ricavi e la quantità.

In Customer Journey Analytics, il reporting di e-commerce utilizza la dimensione **[!UICONTROL Prodotto]** insieme alle metriche di acquisto. Questo report richiede che la tua implementazione invii dati di e-commerce XDM (come `xdm.commerce.purchases`, `xdm.commerce.order` e `xdm.productListItems`).

1. Trascina la dimensione **[!UICONTROL Product]** in una [[!UICONTROL tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Trascina le metriche di e-commerce come **[!UICONTROL Ordini]**, **[!UICONTROL Ricavi]** e **[!UICONTROL Unità]** insieme alla metrica predefinita **[!UICONTROL Eventi]**.

+++

+++Percorso di acquisto (funnel)

Il rapporto percorso acquisti di GA4 mostra come gli utenti passano attraverso il funnel dell’acquisto, ad esempio dall’aggiunta al carrello per iniziare il pagamento all’acquisto, e dove abbandonano.

In Analysis Workspace, utilizza la visualizzazione [**[!UICONTROL Abbandono]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md):

1. Seleziona l&#39;icona Visualizzazioni e trascina una visualizzazione **[!UICONTROL Abbandono]** nell&#39;area di lavoro.
2. Individua la dimensione **[!UICONTROL Pagina]** ed espandila per visualizzare i singoli valori di pagina.
3. Trascina il primo passaggio di funnel (ad esempio, una pagina di prodotto) nel primo slot **[!UICONTROL Aggiungi punto di contatto]**.
4. Continua ad aggiungere punti di contatto per ogni passaggio.

La visualizzazione Abbandono accetta qualsiasi dimensione, metrica o segmento come punto di contatto, non solo le pagine, quindi corrisponde ai funnel basati sugli eventi di GA4 ed si estende alle sequenze che combinano eventi, pagine e segmenti.

+++

+++Promozioni

Il rapporto Promozioni di GA4 mostra come le promozioni interne (banner, posizionamenti in primo piano) guidano le interazioni dei prodotti.

In Customer Journey Analytics, i dati di promozione richiedono l’acquisizione di impression di promozione e clic nei campi dello schema XDM. Una volta raccolta, crea una [[!UICONTROL tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) che includa la dimensione del nome della promozione con metriche impression e clic. Rivolgiti al tuo amministratore Customer Journey Analytics per verificare quali dati di promozione sono disponibili nella visualizzazione dati.

+++

+++Annunci di Publisher

Il rapporto Annunci publisher di GA4 mostra i ricavi degli annunci da Google Ad Manager o AdMob per le proprietà monetizzate dall&#39;editore.

In Customer Journey Analytics non è disponibile alcuna integrazione nativa di ad-revenue per l’editore. Per generare rapporti su questi dati, acquisisci le cifre dei ricavi dalla piattaforma di monetizzazione degli annunci (ad esempio Google Ad Manager o AdMob) in Adobe Experience Platform come set di dati, utilizzando un connettore di origine o l’acquisizione diretta dei dati. Una volta acquisiti, i dati sono disponibili per il reporting in Customer Journey Analytics.

+++

## Conservazione

+++Panoramica sulla conservazione

Il rapporto Panoramica sul mantenimento di GA4 combina diverse visualizzazioni di conservazione, ovvero utenti nuovi rispetto a utenti di ritorno, e un grafico a coorte che mostra quanti utenti ritornano nel tempo.

**Utenti nuovi rispetto a utenti di ritorno**: utilizza i segmenti **[!UICONTROL Prima sessione]** e **[!UICONTROL Sessioni di ritorno]** come righe in una [[!UICONTROL tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md):

1. Trascina il segmento **[!UICONTROL Prima sessione]** dal pannello Componenti nell&#39;area delle righe della tabella, quindi trascina il segmento **[!UICONTROL Sessioni di ritorno]** sotto di esso.
2. Aggiungi le metriche desiderate insieme alla metrica predefinita **[!UICONTROL Eventi]**.
3. Per cambiare tendenza nel tempo, trascina una visualizzazione [**[!UICONTROL Riga]**](/help/analysis-workspace/visualizations/line.md) sopra la tabella, quindi fai clic su ciascuna riga tenendo premuto il tasto Ctrl (Windows) o Comando (Mac) per evidenziare entrambi i segmenti.

**Mantenimento nel tempo**: utilizza la visualizzazione [**[!UICONTROL Tabella coorte]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md):

1. Seleziona l&#39;icona Visualizzazioni e trascina una **[!UICONTROL Tabella coorte]** nell&#39;area di lavoro.
2. Trascina la metrica **[!UICONTROL Persone]** nei campi Criteri di inclusione e Criteri di ritorno, quindi seleziona **[!UICONTROL Genera]**.

La [!UICONTROL Tabella coorte] raggruppa le persone in base al periodo iniziale e tiene traccia del comportamento di ritorno nei periodi successivi. I criteri di inclusione, ritorno e granularità sono tutti configurabili.

+++

## Utente

+++Dettagli demografici

Il rapporto Dettagli demografici di GA4 tratta le caratteristiche degli utenti (età, genere e interessi), insieme a posizione (paese, regione, città) e lingua.

**Posizione** è mappato direttamente alle dimensioni di Customer Journey Analytics: utilizza **[!UICONTROL Paesi]**, **[!UICONTROL Aree]** o **[!UICONTROL Città]** in una [[!UICONTROL Tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) oppure la visualizzazione [[!UICONTROL Mappa]](/help/analysis-workspace/visualizations/map.md) per una panoramica geografica (trascina la metrica **[!UICONTROL Persone]** nello slot **[!UICONTROL Aggiungi metrica]** e seleziona **[!UICONTROL Build]**).

**Età, genere e interessi** richiedono dati di prime parti. Se la tua organizzazione raccoglie dati demografici tramite CRM, moduli di registrazione o sondaggi basati sul consenso, acquisiscili come [set di dati profilo](/help/connections/create-connection.md#profile-dataset) e uniscili ai dati evento. Questo approccio produce dati più affidabili rispetto al modello di segnali Google dedotto di GA4 perché utilizza attributi di prime parti consentiti.

+++

+++Dettagli tecnici

Il rapporto tecnico di GA4 mostra browser, sistema operativo, risoluzione dello schermo e categoria di dispositivi.

In Analysis Workspace, le seguenti dimensioni corrispondono alle dimensioni Tech di GA4, ciascuna originata da un campo XDM standard:

| Dimensione tecnica GA4 | Dimensione Analysis Workspace | Campo XDM |
|---|---|---|
| Browser | **[!UICONTROL Browser]** | `xdm.environment.browserDetails.name` |
| Sistema operativo | **[!UICONTROL Sistema operativo]** | `xdm.environment.operatingSystem` |
| Risoluzione dello schermo | **[!UICONTROL Risoluzione monitor]** | `xdm.device.screenWidth`, `xdm.device.screenHeight` |
| Categoria dispositivo (mobile, desktop, tablet) | **[!UICONTROL Tipo di dispositivo mobile]** | `xdm.device.type` |
| Modello dispositivo | **[!UICONTROL Dispositivo mobile]** | `xdm.device.model` |

Trascina una di queste dimensioni dal pannello Componenti in una [[!UICONTROL tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).

>[!NOTE]
>
>Poiché i browser moderni hanno ridotto i dettagli nella stringa dell&#39;agente utente, i valori completi e precisi dipendono dalla raccolta di [User-Agent Client Hints](https://experienceleague.adobe.com/en/docs/experience-platform/collection/use-cases/client-hints) nella configurazione del Web SDK.

+++

## Esplora

+++Esplorazione in formato libero

L’esplorazione in formato libero di GA4 è una tabella vuota con righe, colonne e sovrapposizioni di grafici configurabili.

La [**[!UICONTROL tabella a forma libera]**](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) di Analysis Workspace è l&#39;equivalente diretto e la base della maggior parte dei progetti Workspace. Trascina una dimensione nelle righe, una metrica nelle colonne e un segmento nella zona di rilascio del segmento sopra la tabella.

Consulta [Guida introduttiva ad Analysis Workspace](home.md#getting-started-in-analysis-workspace) per la mappatura terminologica tra GA4 Explore e Workspace.

+++

+++Esplorazione di funnel

L’esplorazione Funnel di GA4 definisce una sequenza di passaggi e misura il completamento e il abbandono in ogni passaggio.

In Analysis Workspace, utilizza la visualizzazione [**[!UICONTROL Abbandono]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md):

1. Seleziona l&#39;icona Visualizzazioni e trascina una visualizzazione **[!UICONTROL Abbandono]** nell&#39;area di lavoro.
2. Trascina la dimensione, la metrica o il segmento che rappresenta il primo passaggio nel primo slot **[!UICONTROL Aggiungi punto di contatto]**.
3. Continua ad aggiungere un punto di contatto per ogni passaggio successivo della sequenza.

Poiché qualsiasi dimensione, metrica o segmento può fungere da punto di contatto, [!UICONTROL Fallout] corrisponde ai funnel basati su eventi di GA4 e si estende alle sequenze cross-channel che combinano eventi, pagine e segmenti.

+++

+++Esplorazione del percorso

L’esplorazione del percorso di GA4 (Universal Analytics denominato Flusso utenti) visualizza le sequenze di pagine o eventi attraversati dagli utenti.

In Analysis Workspace, utilizza la visualizzazione [**[!UICONTROL Flusso]**](/help/analysis-workspace/visualizations/c-flow/flow.md):

1. Seleziona l&#39;icona Visualizzazioni e trascina una visualizzazione **[!UICONTROL Flusso]** nell&#39;area di lavoro.
2. Trascina un valore dalla dimensione su cui desideri tracciare il percorso (ad esempio, un valore di **[!UICONTROL Pagina]** o **[!UICONTROL Tipo evento]**) al centro del flusso.
3. La visualizzazione mostra cosa hanno fatto gli utenti prima e dopo quel punto.

La visualizzazione [!UICONTROL Flusso] è interattiva: seleziona un nodo per espandere ulteriormente i percorsi in entrambe le direzioni. È possibile utilizzare qualsiasi dimensione, in modo da poter tracciare pagine, eventi, canali di marketing o collegamenti personalizzati.

+++

+++Sovrapposizione segmento

L’esplorazione della sovrapposizione dei segmenti di GA4 mostra come si intersecano più segmenti di utenti, visualizzati come diagramma di Venn.

In Analysis Workspace, utilizza la visualizzazione [**[!UICONTROL Venn]**](/help/analysis-workspace/visualizations/venn.md):

1. Seleziona l&#39;icona Visualizzazioni e trascina una visualizzazione **[!UICONTROL Venn]** nell&#39;area di lavoro.
2. Trascina fino a tre segmenti dal pannello Componenti nella visualizzazione.

Il diagramma di Venn mostra le dimensioni delle intersezioni e la [[!UICONTROL tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) sottostante mostra i dati sottostanti.

+++

+++Esplorazione per coorte

La funzione di esplorazione coorte di GA4 raggruppa gli utenti in base a una caratteristica condivisa (in genere la data di acquisizione) e ne tiene traccia nel tempo.

In Analysis Workspace, utilizza la visualizzazione [**[!UICONTROL Tabella coorte]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md):

1. Seleziona l&#39;icona Visualizzazioni e trascina una **[!UICONTROL Tabella coorte]** nell&#39;area di lavoro.
2. Trascina la metrica **[!UICONTROL Persone]** nei campi Inclusion (Criteri di inclusione) e Return Criteria (Criteri di ritorno).
3. Seleziona **[!UICONTROL Genera]**.

La [!UICONTROL tabella coorte] raggruppa le persone in base al loro periodo iniziale e tiene traccia del comportamento di ritorno nei periodi successivi. Per impostazione predefinita, coorte alla data di acquisizione, ma i criteri di inclusione, ritorno e granularità sono tutti configurabili.

+++

+++Esplora utenti

Esplora utenti di GA4 mostra i singoli utenti, la cronologia delle sessioni e una cronologia degli eventi.

Customer Journey Analytics supporta l’analisi a livello di persona in due modi:

* **Con unione abilitata**: crea un ambito di segmento per un valore ID persona specifico e applicalo a qualsiasi progetto Workspace. Il contenitore **[!UICONTROL Persona]** isola l&#39;attività di tale individuo unita tra sessioni e canali.
* **Dati evento non elaborati**: utilizza **anteprime di set di dati** nell&#39;interfaccia utente di Adobe Experience Platform per esaminare i record evento XDM non elaborati. Questa visualizzazione è utile per la convalida dell’implementazione e il debug di singoli eventi.

+++

+++Durata utente

L’esplorazione della durata di vita degli utenti di GA4 misura il valore e il coinvolgimento accumulati da ciascun utente nell’intera relazione con la tua azienda, anziché all’interno di un intervallo di date fisso. Combina le metriche storiche del ciclo di vita con le previsioni di apprendimento automatico di Google per la probabilità di acquisto, la probabilità di abbandono e i ricavi previsti.

Questi elementi sono associati a Customer Journey Analytics in due parti:

**Il valore della durata cronologica** è raggiungibile in modo nativo. Poiché Customer Journey Analytics genera rapporti in un intervallo di conservazione dei dati completo, puoi impostare un intervallo di date lungo e aggregare i ricavi e il coinvolgimento accumulati di ogni persona in tale lookback. Con l&#39;unione o un ID persona persistente, il contenitore **[!UICONTROL Persona]** collega l&#39;attività a un singolo utente e le metriche calcolate esprimono il valore per persona. Il risultato non è una durata illimitata, ma un lookback lungo e configurabile che ne approssima una.

**Il valore della durata predittiva** non è incorporato. Customer Journey Analytics non dispone di un modello di acquisto, probabilità di abbandono o ricavo previsto all’interno del prodotto. Per utilizzare i punteggi predittivi, calcolali esternamente (ad esempio, in un flusso di lavoro di gestione delle relazioni con i clienti o di scienza dei dati), inseriscili in Customer Journey Analytics come set di dati di profilo e infine visualizzali come dimensioni o metriche. Adobe consiglia di collaborare con un consulente per l’implementazione per progettare questo approccio.

+++

## Metriche comuni

+++Utenti attivi → Persone

**Utenti attivi** di GA4 conta gli utenti che hanno avuto almeno una sessione attiva nell&#39;intervallo di date.

In Customer Journey Analytics, l&#39;equivalente più vicino è **[!UICONTROL Persone]**, un conteggio di ID persona univoci nell&#39;intervallo di date. [!UICONTROL Persone] include tutte le persone identificate indipendentemente dal livello di coinvolgimento, quindi in genere è superiore a Utenti attivi di GA4 per i siti con traffico passivo significativo.

Per un confronto comportamentale più stretto, applica un segmento [sessioni impegnate](compare-data.md#engaged-sessions) per definire l&#39;ambito della metrica [!UICONTROL Persone] agli utenti che soddisfano i criteri di coinvolgimento.

+++

+++Sessioni coinvolte → metrica calcolata

Le **sessioni impegnate** di GA4 contano sessioni della durata di 10 o più secondi, con 2 o più visualizzazioni di pagina o almeno un evento chiave.

Customer Journey Analytics non dispone di una metrica integrata per le sessioni attive: la definisci come un segmento che acquisisce i criteri di coinvolgimento, quindi la utilizzi insieme alla metrica **[!UICONTROL Sessioni]**. Per l&#39;approccio consigliato e come derivarne un tasso di coinvolgimento, consulta [Sessioni impegnate](compare-data.md#engaged-sessions).

+++

+++Tasso di coinvolgimento → metrica calcolata

Il **tasso di coinvolgimento** di GA4 è la percentuale di sessioni impegnate: sessioni impegnate divise per il totale delle sessioni.

In Customer Journey Analytics, generalo come metrica calcolata dalla definizione delle sessioni impegnate. Per istruzioni dettagliate, consulta [Sessioni coinvolte](compare-data.md#engagement-rate).

+++

+++Tempo medio di coinvolgimento → tempo trascorso per sessione

Il **tempo medio di coinvolgimento** di GA4 misura il tempo medio in cui il browser o l&#39;app sono stati in primo piano durante le sessioni impegnate.

In Customer Journey Analytics, utilizza **[!UICONTROL Durata sessione (secondi)]**, che misura il tempo trascorso dal primo evento all&#39;ultimo evento di una sessione. Questo componente include periodi in cui l’utente potrebbe non essere stato attivamente coinvolto, quindi i valori possono differire dalla misurazione di GA4. È l&#39;equivalente incorporato più vicino.

+++

+++Conteggio eventi → eventi

Il **conteggio eventi** di GA4 indica il numero totale di volte in cui è stato registrato un evento.

In Customer Journey Analytics, la metrica equivalente è **[!UICONTROL Eventi]**, ovvero il numero totale di record evento nel set di dati per l&#39;intervallo di date selezionato e i segmenti applicati.

+++

+++Sessioni → sessioni

Le **sessioni** di GA4 e le **[!UICONTROL sessioni]** di Customer Journey Analytics misurano entrambe il numero di sessioni in un intervallo di date. I conteggi possono variare a causa di diverse regole di definizione della sessione. Per ulteriori informazioni, vedere [Perché i dati di GA4 e Customer Journey Analytics differiscono](compare-data.md#sessions).

+++

+++Nuovi utenti → segmento Prima sessione applicato agli utenti

**Nuovi utenti** di GA4 conta gli utenti che hanno avuto la loro prima sessione in assoluto nell&#39;intervallo di date selezionato.

In Analysis Workspace:

1. Individua il segmento **[!UICONTROL Prima sessione]** nel pannello Componenti.
2. Trascinalo nella zona di rilascio segmenti sopra la [[!UICONTROL tabella a forma libera]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
3. Utilizza la metrica **[!UICONTROL Persone]** per contare le nuove persone univoche.

+++

+++Frequenza di mancato recapito → Frequenza di mancato recapito (con avvertenze)

**Percentuale di mancato recapito** di GA4 indica la percentuale di sessioni non utilizzate (meno di 10 secondi, nessun evento chiave, meno di 2 visualizzazioni di pagina). È l&#39;inverso di Livello di Coinvolgimento.

Per impostazione predefinita, la metrica **[!UICONTROL Percentuale non recapitate]** di Customer Journey Analytics utilizza una definizione diversa ed è configurabile in base alla visualizzazione dati. Queste differenze producono numeri materialmente diversi che misurano comportamenti diversi.

Per approssimare il tasso di mancato recapito di GA4 in Customer Journey Analytics, generare una metrica di tasso di coinvolgimento e invertirla con una seconda metrica calcolata definita come `1 - Engagement Rate`. Consulta [Sessioni impegnate](compare-data.md#engagement-rate) per la compilazione dettagliata.

Per una spiegazione dettagliata della differenza nelle definizioni, vedere [Perché i dati di GA4 e Customer Journey Analytics differiscono](compare-data.md#bounce-rate).

+++

+++Eventi chiave → metriche evento personalizzate

I **eventi chiave** di GA4 (precedentemente denominati Conversioni) sono eventi designati come risultati aziendali importanti nella configurazione della proprietà GA4.

In Customer Journey Analytics, una conversione è una metrica evento personalizzata configurata nella visualizzazione dati. Qualsiasi evento XDM può essere esposto come metrica e una metrica può essere impostata per l&#39;incremento condizionale su un valore di campo XDM, ad esempio una metrica **[!UICONTROL Purchases]** che aumenta quando `xdm.eventType` è uguale a `commerce.purchases`. Individua la metrica pertinente dalla relativa etichetta nel pannello Componenti di Analysis Workspace; il nome riflette il modo in cui l’amministratore l’ha configurata.

Per riprodurre gli eventi chiave di GA4 *report* (un elenco di ogni conversione con il relativo conteggio), vedere la voce **Eventi chiave (conversioni)** in [Coinvolgimento](#engagement) in questa pagina.

+++

>[!MORELIKETHIS]
>
>* [Rapporto sui dati di Google Analytics](/help/use-cases/third-party/ga/report.md)
