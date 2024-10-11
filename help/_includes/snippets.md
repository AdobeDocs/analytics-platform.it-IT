---
source-git-commit: 609aac6e0a2231b15296945dbf9dd4f917fb9a19
workflow-type: tm+mt
source-wordcount: '3955'
ht-degree: 32%

---
# Snippet

## Fase di test del rilascio {#release-limited-testing}

>[!AVAILABILITY]
>
>La funzionalità descritta in questo articolo si trova nella fase di test del rilascio e potrebbe non essere ancora disponibile nell‘ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sulla procedura di rilascio del Customer Journey Analytics, vedere [Rilasci di funzionalità del Customer Journey Analytics](/help/release-notes/releases.md).

## Sezione della fase di test del rilascio {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funzionalità descritta in questa sezione si trova nella fase di test del rilascio e potrebbe non essere ancora disponibile nell‘ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sulla procedura di rilascio del Customer Journey Analytics, vedere [Rilasci di funzionalità del Customer Journey Analytics](/help/release-notes/releases.md).

## Seleziona pacchetto {#select-package}

>[!NOTE]
>
>Per utilizzare le funzionalità descritte in questa sezione è necessario disporre del pacchetto **Select** o versione successiva. In caso di dubbi sul pacchetto di Customer Journey Analytics di cui disponi, contatta l’amministratore.

## Pacchetto Prime {#prime-package}

>[!NOTE]
>
>Per utilizzare le funzionalità descritte in questa sezione è necessario disporre del pacchetto **Prime** o versione successiva. In caso di dubbi sul pacchetto di Customer Journey Analytics di cui disponi, contatta l’amministratore.

## Pacchetto Ultimate {#ultimate-package}

>[!NOTE]
>
>Per utilizzare le funzionalità descritte in questa sezione è necessario disporre del pacchetto **Ultimate**. In caso di dubbi sul pacchetto di Customer Journey Analytics di cui disponi, contatta l’amministratore.


## Criteri del filtro del dizionario dati {#dd-filter-criteria}

1. (Facoltativo) Seleziona l’icona **Filtro** ![icona Filtro dizionario dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) e quindi una delle seguenti opzioni per filtrare l’elenco dei componenti:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Approvato**] | Mostra solo i componenti contrassegnati come approvati da un amministratore. |
   | [!UICONTROL **Preferiti**] | Mostra solo i componenti inclusi nell’elenco dei Preferiti. Per informazioni sull’aggiunta di componenti all’elenco dei preferiti, consulta [Panoramica dei componenti](/help/components/overview.md). |
   | [!UICONTROL **Dimensioni**] | Mostra solo i componenti che sono Dimensioni. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
   | [!UICONTROL **Metriche**] | Mostra solo i componenti che sono Metriche. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
   | [!UICONTROL **Filtri**] | Mostra solo i componenti che sono filtri. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Intervalli di date**] | Mostra solo i componenti che sono Intervalli di date. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
   | [!UICONTROL **Mostra tutti**] | Mostra tutti i componenti. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Non approvato**] | Mostra solo i componenti non ancora contrassegnati come approvati da un amministratore. In qualità di amministratore, questo è utile per identificare i componenti che richiedono la revisione e l’approvazione. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Descrizione mancante**] | Mostra solo i componenti che non dispongono ancora di una descrizione nel campo apposito. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Mostra duplicati**] | Mostra solo i componenti con lo stesso nome o la stessa descrizione di un altro componente nella visualizzazione dati selezionata. Sono inclusi i componenti creati e quelli forniti da Adobe. I nomi o le descrizioni devono avere corrispondenze esatte per poter essere visualizzati come duplicati. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Nessun dato recente**] | Mostra solo i componenti che non hanno raccolto dati negli ultimi 90 giorni. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Creato da Adobe**] <!-- I don't see this option--> | Mostra solo i componenti creati da Adobe. I componenti creati da un amministratore o da un altro utente dell’organizzazione non vengono visualizzati. |

   {style="table-layout:auto"}

## Informazioni sui componenti del dizionario dati {#dd-component-information}

| Opzione | Funzione |
|---------|----------|
| [!UICONTROL **Approvato**] | <p>Indica che il componente è stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano un&#39;opzione per [!UICONTROL **annullare l&#39;approvazione**]. Selezionando questa opzione, il componente viene contrassegnato come &quot;Non approvato&quot; per gli utenti.</p> |
| [!UICONTROL **Non approvato**] | <p>Indica che il componente non è ancora stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano l’opzione [!UICONTROL **Approva**]. Selezionando questa opzione, il componente viene visualizzato dagli utenti come “Approvato”.</p> |
| [!UICONTROL **Descrizione**] | Descrive la funzione prevista del componente. (Queste informazioni vengono aggiunte dall’amministratore di Analytics, come descritto in [Aggiungi descrizioni dei componenti](/help/components/add-component-descriptions.md).) |
| [!UICONTROL **Utilizzato di frequente con**] | <p>Mostra i componenti più comunemente utilizzati insieme a quello che stai visualizzando.</p><p>Vengono visualizzati fino a 5 componenti nei 5 tipi di componenti principali: Metrica, Metrica calcolata, Dimension, Filtro e Intervallo date.</p><p>Questo elenco è basato sui dati degli ultimi 90 giorni. Vengono mostrati solo i componenti a cui hai accesso alla visualizzazione.</p><p>Gli amministratori possono curare i componenti che gli utenti possono visualizzare in questa sezione, selezionandoli nei campi a discesa [!UICONTROL **Includi sempre**] e [!UICONTROL **Escludi sempre**]. Prima di curare i componenti visualizzati dagli utenti, applicare il filtro **Mostra tutti** per assicurarsi di visualizzare i componenti non condivisi con l&#39;utente che potrebbero essere stati aggiunti da un altro amministratore.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Simile a**] | <p>Mostra i componenti con nomi simili al componente che stai visualizzando.</p><p>Vengono visualizzati fino a 5 componenti nei 5 tipi di componenti principali: Metrica, Metrica calcolata, Dimension, Filtro e Intervallo date.</p><p>Vengono mostrati solo i componenti a cui hai accesso alla visualizzazione.</p><p>Tutti i componenti duplicati nella visualizzazione dati verranno visualizzati qui. Gli amministratori di Analytics devono identificare e rimuovere tutti i componenti duplicati, come descritto in [Monitorare l’integrità del dizionario dati](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Gli amministratori possono curare i componenti che gli utenti possono visualizzare in questa sezione, selezionandoli nei campi a discesa [!UICONTROL **Includi sempre**] ed [!UICONTROL **Escludi sempre**]. Prima di curare i componenti visualizzati dagli utenti, applicare il filtro **Mostra tutti** per assicurarsi di visualizzare i componenti non condivisi con l&#39;utente che potrebbero essere stati aggiunti da un altro amministratore.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**NOTA:** attualmente, la sezione **Simile a** include solo i componenti che hai creato e non quelli forniti da Adobe. I componenti forniti da Adobe verranno aggiunti in una versione futura.</p> |
| [!UICONTROL **Compatibilità del prodotto**] | Indica dove nel Customer Journey Analytics può essere utilizzata questa metrica calcolata. <p>I valori possibili sono:</p><ul><li>[!UICONTROL **Ovunque nel Customer Journey Analytics**]: la metrica calcolata può essere utilizzata in tutto il Customer Journey Analytics, inclusi Analysis Workspace, Report Builder e così via.</li><li>[!UICONTROL **Ovunque nel Customer Journey Analytics (esclusa la sperimentazione)**]: la metrica calcolata può essere utilizzata in tutto il Customer Journey Analytics, eccetto nel pannello Sperimentazione.</li> <p>Per informazioni sui criteri che determinano se una metrica calcolata può essere utilizzata con la sperimentazione, vedere [Utilizzare le metriche calcolate nel pannello Sperimentazione](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) in [Pannello Sperimentazione](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
| [!UICONTROL **Tag**] | Mostra tutti i tag applicati al componente. Gli utenti con accesso amministratore possono aggiungere tag durante la modifica del componente. |
| [!UICONTROL **Tipo di componente**] | Elenca il tipo di componente, sia esso un Dimension, una metrica, un filtro o un intervallo di date. |
| [!UICONTROL **Creato da**] | Mostra il nome dell’utente che ha creato il componente. |
| [!UICONTROL **Anteprima**] | Mostra un’anteprima dell’aspetto del componente in Analysis Workspace. |
| [!UICONTROL **Data ultima modifica**] | Mostra il giorno dell’ultima modifica apportata al componente. Questa sezione viene visualizzata quando si visualizzano Filtri, Metriche, Metriche calcolate e Intervalli di date. |

{style="table-layout:auto"}

## Opzioni di ordinamento dei componenti {#components-sort-options}

| Opzione | Funzione |
|---------|----------|
| **[!UICONTROL Recommended]** | Ordina i componenti per ciascun tipo (dimensione, metrica, filtro e intervallo di date) in base ai consigli. I componenti utilizzati più di frequente e più di recente da te o da altri nella tua organizzazione vengono visualizzati più in alto in ciascun elenco. |
| **[!UICONTROL Last modified]** | Ordina i componenti per ciascun tipo (dimensione, metrica, filtro e intervallo di date) in base alla data dell’ultima modifica. I componenti modificati più di recente vengono visualizzati più in alto in ciascun elenco. |
| **[!UICONTROL Alphabetical]** | Ordina i componenti per ciascun tipo (dimensione, metrica, filtro e intervallo di date) in ordine alfabetico crescente. |
| **[!UICONTROL Categorical]** | Ordina i componenti per ciascun tipo (dimensione, metrica, filtro e intervallo di date) in base alla loro categoria. Ad esempio, componenti di visualizzazione dati curati e non curati. |

{style="table-layout:auto"}

## Confronto temporale {#apply-time-comparison}

È possibile confrontare il periodo di tempo corrente con un periodo precedente. Se selezionate un&#39;opzione in questo menu, ogni punto dati riceve una controparte con linee punteggiate di colore simile. Questa controparte rappresenta la stessa metrica nell’intervallo di date precedente selezionato. Impostando questa opzione si raddoppia il numero di elementi nel grafico e di righe nella tabella.

Le opzioni di confronto del tempo disponibili includono il periodo precedente, 13 settimane prima, 52 settimane prima e un intervallo di date personalizzato. Se selezioni Intervallo date personalizzato, vengono visualizzate opzioni aggiuntive per consentirti di selezionare il numero e la granularità. Se selezioni Nessuno, il confronto tra date viene rimosso.


## Dimostrazione video Adobe Analytics {#videoaa}

Questo video illustra le funzionalità di con Adobe Analytics. Tuttavia, la funzionalità è disponibile anche in Customer Journey Analytics. Tieni presente le seguenti differenze terminologiche.

| Adobe Analytics | Customer Journey Analytics |
|:---:|:---:|
| Segmenti | Filtri |
| Visitatore | Persona |
| Visita | Sessione |
| Hit | Evento |


## Pannello Filtri {#filterspanel}

1. Seleziona ![Filtro](/help/assets/icons/Filter.svg) per aprire il pannello Filtri. Se hai bisogno di più spazio per l&#39;elenco Filtri, puoi selezionare ancora ![Filtro](/help/assets/icons/Filter.svg) per chiudere il pannello.
1. Seleziona i filtri da una qualsiasi delle sezioni disponibili.


## Sezione filtro tag {#tagfiltersection}

| Tag | Descrizione |
|---|---|
| ![Tag](/help/assets/filter-tag.png){width="300"} | La sezione **[!UICONTROL Tags]** consente di filtrare i tag. <ul><li>Puoi ![cercare](/help/assets/icons/Search.svg) *Cerca tag* per cercare i tag che puoi utilizzare per filtrare.</li><li>È possibile selezionare più tag. I tag disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**(1)**: numero di tag selezionati (se sono selezionati uno o più tag).</li><li>**2︎⃣**: numero di tag disponibili per gli elementi risultanti dal filtro corrente.</li><li>7︎⃣: numero di elementi associati al tag specifico.</li></ul></li></ul> |


## Sezione filtro visualizzazione dati {#dataviewfiltersection}

| Visualizzazione dati | Descrizione |
|---|---|
| ![Visualizzazioni dati](/help/assets/filter-dataview.png){width="300"} | La sezione **[!UICONTROL Data view]** consente di filtrare le visualizzazioni dati. <ul><li>Puoi ![Cercare](/help/assets/icons/Search.svg) *Cercare le visualizzazioni dati* per cercare le visualizzazioni dati da utilizzare per filtrare.</li><li>Puoi selezionare più di una visualizzazione dati. Le visualizzazioni dati disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**(2)**: numero di visualizzazioni dati selezionate (se sono selezionate una o più visualizzazioni dati).</li><li>**3︎⃣**: numero di visualizzazioni dati disponibili per gli elementi risultanti dal filtro corrente.</li><li>4︎⃣: numero di elementi associati alla visualizzazione dati specifica.</li></ul></li></ul> |

## Sezione filtro di stato abilitato {#enabledstatusfiltersection}

| Stato abilitato | Descrizione |
|---|---|
| ![Stato abilitato](/help/assets/filter-enabledstatus.png){width="300"} | La sezione **[!UICONTROL Enabled status]** consente di filtrare in base allo stato abilitato. <ul><li>È possibile selezionare più stati.</li><li>I numeri indicano:<ul><li>**(2)**: numero di stati selezionati (se sono selezionati uno o più stati).</li><li>**2︎⃣**: numero di stati disponibili per gli elementi risultanti dal filtro corrente.</li><li>1︎⃣: numero di elementi associati allo stato specifico.</li></ul></li></ul> |

## Digita la sezione del filtro {#typefiltersection}

| Tipo | Descrizione |
|---|---|
| ![Tipo](/help/assets/filter-type.png){width="300"} | La sezione **[!UICONTROL Type]** consente di filtrare in base al tipo. <ul><li>È possibile selezionare più tipi.</li><li>I numeri indicano:<ul><li>**(2)**: numero di tipi selezionati (se sono selezionati uno o più tipi).</li><li>**1︎⃣**: il numero di tipi disponibili per gli elementi risultanti dal filtro corrente.</li><li>3︎⃣: numero di elementi associati al tipo specifico.</li></ul></li></ul> |

## Sezione filtro proprietario {#ownerfiltersection}

| Proprietario | Descrizione |
|---|---|
| ![Proprietari](/help/assets/filter-owners.png){width="300"} | La sezione **[!UICONTROL Owner]** consente di filtrare in base ai proprietari. <ul><li>Puoi ![cercare](/help/assets/icons/Search.svg) *Cerca proprietari* per cercare i proprietari che puoi utilizzare per filtrare.</li><li>È possibile selezionare più di un proprietario. I proprietari disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**(2)**: numero di proprietari selezionati (se sono selezionati uno o più proprietari).</li><li>**3︎⃣**: numero di proprietari disponibili per gli elementi risultanti dal filtro corrente.</li><li>4︎⃣: numero di elementi associati al proprietario specifico.</li></ul></li></ul> |

## Sezione filtro Altri filtri {#otherfiltersfiltersection}

| Altri filtri | Descrizione |
|---|---|
| ![Altri filtri](/help/assets/filter-other.png){width="300"} | La sezione **[!UICONTROL Other filters]** consente di filtrare in base ad un altro filtro predefinito.<ul><li>Puoi selezionare una o più delle seguenti opzioni:<ul><li> **[!UICONTROL Show all]**</li><li>**[!UICONTROL Shared with me]**</li><li>**[!UICONTROL Mine]**</li><li>**[!UICONTROL Approved]**</li><li>**[!UICONTROL Favorites]**</li></ul> Ciò che puoi selezionare dipende dal tuo ruolo e dalle autorizzazioni.</li><li>Puoi selezionare più di un altro filtro. Gli altri filtri disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**(1)**: numero di altri filtri selezionati (se sono selezionati uno o più altri filtri).</li><li>**5︎⃣**: numero di altri filtri disponibili per gli elementi risultanti dal filtro corrente.</li><li>4︎⃣: numero di elementi associati all’altro filtro specifico.</li></ul></li></ul> |

## Sezione filtro intervallo di date  {#daterangefiltersection}

| Intervallo date applicato | Descrizione |
|---|---|
| ![Intervallo date](/help/assets/filter-daterange.png){width="300"} | La sezione Intervallo date applicato consente di filtrare in base a un intervallo di date applicabile agli elementi.<ol><li>Seleziona un intervallo di date.</li><li>Nel popup del calendario definisci un intervallo di date o seleziona uno dei predefiniti disponibili.<br>In alternativa, è possibile specificare un intervallo di date direttamente nella sezione Intervallo date del pannello Filtro.</li></ol><ul><li>I numeri indicano:<ul><li>**(1)**: numero di intervalli di date modificati dai predefiniti predefiniti.</li><li>**5︎⃣**: numero di intervalli di date disponibili per gli elementi risultanti dal filtro corrente.</li></ul> |


## Modelli di attribuzione {#attribution-models-details}

Un modello di attribuzione determina quali elementi dimensionali ricevono credito per una metrica quando vengono visualizzati più valori nell’intervallo di lookback di una metrica. I modelli di attribuzione si applicano solo quando nell’intervallo di lookback sono impostati più elementi dimensionali. Se è impostato un solo elemento dimensionale, a tale elemento viene assegnato un credito del 100% indipendentemente dal modello di attribuzione utilizzato.

| Icona | Modello di attribuzione | Definizione |
| :---: | :--- | --- |
| ![Ultimo contatto](/help/assets/icons/AttributeLastTouch.svg) | Ultimo contatto | Attribuisce un credito del 100% al punto di contatto che si verifica più di recente prima della conversione. Questo modello di attribuzione è in genere il valore predefinito per qualsiasi metrica in cui un modello di attribuzione non è specificato altrimenti. In genere, le organizzazioni utilizzano questo modello quando il tempo di conversione è relativamente breve, ad esempio con l’analisi delle parole chiave di ricerca interne. |
| ![Primo contatto](/help/assets/icons/AttributeFirstTouch.svg) | Primo contatto | Attribuisce un credito del 100% al punto di contatto visualizzato per la prima volta nell’intervallo di lookback dell’attribuzione. In genere, le organizzazioni utilizzano questo modello per comprendere la consapevolezza del brand o l’acquisizione dei clienti. |
| ![Lineare](/help/assets/icons/AttributeLinear.svg) | Lineare | Attribuisce lo stesso credito a ogni punto di contatto che porta a una conversione. È utile quando i cicli di conversione sono più lunghi o richiedono un coinvolgimento più frequente dei clienti. In genere le organizzazioni utilizzano questo modello di attribuzione per misurare l’efficacia delle notifiche delle app mobili o con prodotti basati su abbonamento. |
| ![Partecipazione](/help/assets/icons/AttributeParticipation.svg) | Partecipazione | Assegna il 100% di credito a tutti i punti di contatto univoci. Poiché ogni punto di contatto riceve un credito del 100%, i dati delle metriche in genere superano il 100%. Se un elemento dimensionale appare più volte separatamente, portando a una conversione, i valori vengono deduplicati al 100%. Questo modello di attribuzione è ideale nelle situazioni in cui desideri comprendere a quali punti di contatto i clienti sono più esposti. Le organizzazioni di media in genere utilizzano questo modello per calcolare la velocità dei contenuti. Le organizzazioni di vendita al dettaglio in genere utilizzano questo modello per comprendere quali parti del sito sono fondamentali per la conversione. |
| ![Stesso contatto](/help/assets/icons/AttributeSameTouch.svg) | Stesso contatto | Attribuisce un credito del 100% allo stesso evento in cui si è verificata la conversione. Se un punto di contatto non si verifica nello stesso evento di una conversione, viene inserito in &quot;None&quot;. A volte questo modello di attribuzione viene equiparato all’assenza totale di un modello di attribuzione. È utile negli scenari in cui non desideri valori da altri eventi che influiscono sul modo in cui una metrica attribuisce credito agli elementi dimensionali. I team di prodotto o di progettazione possono utilizzare questo modello per valutare l’efficacia di una pagina in cui si verifica una conversione. |
| ![U a forma di](/help/assets/icons/AttributeUShaped.svg) | A forma di U | Attribuisce il 40% di credito alla prima interazione, il 40% di credito all’ultima interazione e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato un credito del 50% a entrambi. Questo modello di attribuzione è meglio utilizzato in scenari in cui si attribuisce il maggior valore alla prima e all’ultima interazione, ma non si desidera escludere completamente ulteriori interazioni intermedie. |
| ![J Curva](/help/assets/icons/AttributeJCurve.svg) | Curva J | Attribuisce il 60% di credito all’ultima interazione, il 20% di credito alla prima interazione e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato il 75% di credito all’ultima interazione e il 25% di credito alla prima. Simile al modello a forma di U, questo modello di attribuzione favorisce la prima e l’ultima interazione, ma favorisce in modo più significativo l’ultima interazione. |
| ![J inversa](/help/assets/icons/AttributeInverseJ.svg) | J inversa | Attribuisce un credito del 60% al primo punto di contatto, un credito del 20% all’ultimo punto di contatto e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato il 75% di credito alla prima interazione e il 25% di credito all’ultima. Simile al modello a forma di J, questo modello di attribuzione favorisce la prima e l’ultima interazione, ma favorisce in modo più significativo la prima interazione. |
| ![Decadimento nel tempo](/help/assets/icons/AttributeTimeDecay.svg) | Decadimento nel tempo | Segue un decadimento esponenziale con un parametro di mezza durata personalizzato, dove il valore predefinito è 7 giorni. Il valore di ciascun canale dipende dalla quantità di tempo trascorsa tra l’avvio del punto di contatto e l’eventuale conversione. La formula utilizzata per determinare il credito è `2^(-t/halflife)`, dove `t` è il tempo tra un punto di contatto e una conversione. Tutti i punti di contatto vengono quindi normalizzati al 100%. Ideale per scenari in cui desideri misurare l’attribuzione rispetto a un evento specifico e significativo. Più si verifica una conversione dopo questo evento, meno credito viene assegnato. |
| ![Personalizzato](/help/assets/icons/AttributeCustom.svg) | Personalizzato | Consente di specificare i valori da assegnare al primo punto di contatto, all&#39;ultimo punto di contatto e a eventuali punti di contatto intermedi. I valori specificati vengono normalizzati al 100% anche se la somma dei numeri personalizzati immessi è inferiore a 100. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le interazioni con due punti di contatto, il parametro intermedio viene ignorato. Il primo e l’ultimo punto di contatto vengono quindi normalizzati al 100% e il credito viene assegnato di conseguenza. Questo modello è ideale per gli analisti che desiderano un controllo completo sul proprio modello di attribuzione e hanno esigenze specifiche che altri modelli di attribuzione non soddisfano. |
| ![Algoritmica](/help/assets/icons/AttributeAlgorithmic.svg) | Algoritmico | Utilizza tecniche statistiche per determinare in modo dinamico l’allocazione ottimale del credito per la metrica selezionata. L’algoritmo utilizzato per l’attribuzione è basato sul dividendo Harsanyi dalla teoria del gioco cooperativo. Il dividendo Harsanyi è una generalizzazione della soluzione del valore di Shapley (che prende il nome da Lloyd Shapley, un economista premio Nobel) per la distribuzione del credito tra i giocatori in un gioco con contributi disuguali al risultato.<br>Ad alto livello, l&#39;attribuzione viene calcolata come una coalizione di giocatori a cui deve essere equamente distribuito un surplus. La distribuzione del surplus di ciascuna coalizione è determinata in base al surplus creato in precedenza da ogni subcoalizione (o dagli elementi dimensionali partecipanti in precedenza) in modo ricorsivo. Per maggiori dettagli, vedi gli articoli originali di John Harsanyi e Lloyd Shapley:<br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Intervallo di lookback dell’attribuzione {#attribution-lookback-window}

Per intervallo di lookback si intende la quantità di tempo che una conversione deve recuperare nel passato per includere i punti di contatto. Se un elemento dimensione è impostato all’esterno dell’intervallo di lookback, il valore non viene incluso in alcun calcolo di attribuzione.

* **14 giorni**: cerca fino a 14 giorni dal momento in cui si è verificata la conversione.
* **30 giorni**: cerca fino a 30 giorni da quando si è verificata la conversione.
* **60 giorni**: cerca fino a 60 giorni da quando si è verificata la conversione.
* **90 giorni**: cerca fino a 90 giorni dal momento in cui si è verificata la conversione.
* **Sessione**: considera fino l&#39;inizio della sessione in cui si è verificata una conversione. Gli intervalli di lookback della sessione rispettano il [Timeout sessione](/help/data-views/create-dataview.md#session-settings) modificato in una visualizzazione dati.
* **Persona (intervallo di reporting)**: esamina tutte le visite fino al primo del mese dell&#39;intervallo date corrente. Ad esempio, se l’intervallo di date del rapporto è dal 15 settembre al 30 settembre, l’intervallo di date del lookback a persona sarà dal 1° al 30 settembre. Se utilizzi questo intervallo di lookback, puoi notare occasionalmente che gli elementi dimensionali sono attribuiti a date al di fuori dell’intervallo di reporting.
* **Ora personalizzata:** consente di impostare un intervallo di lookback personalizzato da quando si è verificata una conversione. È possibile specificare il numero di minuti, ore, giorni, settimane, mesi o trimestri. Ad esempio, se si verificasse una conversione il 20 febbraio, un intervallo di lookback di cinque giorni valuterebbe tutti i punti di contatto delle dimensioni dal 15 febbraio al 20 febbraio nel modello di attribuzione.

## Esempio di attribuzione {#attribution-example}

Prendi in considerazione l’esempio seguente:

1. Il 15 settembre, una persona arriva sul tuo sito tramite un annuncio pubblicitario di ricerca a pagamento, poi se ne va.
1. Il 18 settembre, la persona ritorna sul tuo sito tramite un collegamento social media ricevuto da un amico. Aggiunge diversi articoli al carrello, ma non acquista nulla.
1. Il 24 settembre, il team marketing gli invia un’e-mail con un coupon da utilizzare su alcuni degli elementi nel carrello. Applica il coupon, ma visita diversi altri siti per vedere se sono disponibili altri coupon. Ne trova un altro tramite un annuncio pubblicitario, quindi completa un acquisto dal valore di 50 $.

A seconda dell’intervallo di lookback e del modello di attribuzione definiti, ai canali saranno assegnati crediti diversi. Di seguito sono riportati alcuni esempi:

* Utilizzando **il primo contatto** e un intervallo di lookback di **sessione**, l&#39;attribuzione considera solo la terza visita. Tra e-mail e visualizzazione, e-mail è avvenuta prima, quindi e-mail ottiene 100% di credito per l’acquisto di 50 $.

* Utilizzando **il primo contatto** e un intervallo di lookback di **persona**, l&#39;attribuzione esamina tutte e tre le visite. La ricerca a pagamento è avvenuta prima, quindi ottiene il 100% di credito per l’acquisto di 50 $.

* Utilizzando **linear** e un intervallo di lookback di **sessione**, il credito è suddiviso tra e-mail e visualizzazione. Entrambi questi canali ricevono un credito di 25 $.
Utilizzando **linear** e un intervallo di lookback di **persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione. Ogni canale ottiene un credito di 12,50 $ per questo acquisto.

* Utilizzando **a forma di J** e un intervallo di lookback di **persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione.

   * Il 60% di credito è assegnato alla visualizzazione, per un valore di 30 $.
   * Il 20% di credito è assegnato alla ricerca a pagamento, per un valore di 10 $.
   * Il restante 20% è suddiviso tra social e e-mail, ovvero 5 $ ciascuno.

* Utilizzando **Decadimento nel tempo** e un intervallo di lookback di **persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione. Utilizzando la mezza durata predefinita di 7 giorni:

   * Intervallo di zero giorni tra il punto di contatto visualizzazione e la conversione. `2^(-0/7) = 1`
   * Intervallo di zero giorni tra il punto di contatto e-mail e la conversione. `2^(-0/7) = 1`
   * Intervallo di sei giorni tra il punto di contatto social e la conversione. `2^(-6/7) = 0.552`
   * Intervallo di nove giorni tra il punto di contatto ricerca a pagamento e la conversione. `2^(-9/7) = 0.41`
   * La normalizzazione di questi valori determina quanto segue:

      * Visualizzazione: 33,8%, ovvero 16,88 $
      * E-mail: 33,8% ovvero 16,88 $
      * Social: 18,6%, ovvero 9,32 $
      * Ricerca a pagamento: 13,8%, ovvero 6,92 $

Gli eventi di conversione che in genere hanno numeri interi vengono suddivisi se il credito appartiene a più di un canale. Ad esempio, se due canali contribuiscono a un ordine utilizzando un modello di attribuzione lineare, entrambi i canali ottengono 0,5 di tale ordine. Queste metriche parziali vengono sommate tra tutte le persone e quindi arrotondate al numero intero più vicino per il reporting.

## Confronti nella visualizzazione percorso {#journey-visualization-comparisons}

Varie visualizzazioni nell’analisi del Percorso di clienti sono progettate per analizzare i percorsi forniti ai clienti.

Utilizza le seguenti informazioni per scegliere la visualizzazione che meglio soddisfa le tue esigenze.

| Funzione | Area di lavoro percorso | Fallout (abbandono) | Flusso |
|---------|----------|---------|---------|
| **Sequenza di pagine predefinita** | Sì</br>Combina analisi predefinite ed esplorative. Il percorso finale viene utilizzato quando si utilizzano nodi predefiniti sul percorso (i visitatori vengono conteggiati purché passino infine da un nodo predefinito all’altro). È inoltre possibile visualizzare i nodi successivi immediati (non finali). | Sì</br>Il percorso può essere un percorso finale o essere vincolato al punto di contatto successivo | No |
| **Sequenza esplorativa di pagine (analisi ad hoc)** | Sì</br>Combina analisi predefinite ed esplorative. Il percorso finale viene utilizzato quando si utilizzano nodi predefiniti sul percorso (i visitatori vengono conteggiati purché passino infine da un nodo predefinito all’altro). È inoltre possibile visualizzare i nodi successivi immediati (non finali). | Limitato</br>Consente di fare clic con il pulsante destro del mouse e visualizzare l&#39;abbandono immediato in una tabella a forma libera. | Sì</br>Solo analisi esplorativa. Ogni nodo mostra il punto di contatto successivo immediato (non finale) lungo il percorso. |
| **Mostra dove le persone hanno lasciato (abbandonato) e continuato (proseguito)** | Sì</br>Mostra per percorsi predefiniti ed esplorativi | Sì</br>Mostra percorsi predefiniti | Sì</br>Mostra per percorsi esplorativi |
| **percorsi lineari** | Sì | Sì | No |
| **percorsi non lineari con più punti di ingresso e percorsi** | Sì | No | Sì |
| **Metrica primaria** | Qualsiasi metrica, comprese quelle calcolate | Solo sessione o persona | Solo occorrenze |
| **Metrica secondaria** | Sì<p>Qualsiasi metrica, comprese quelle calcolate</p> | No | No |
| **Supporto dei componenti nei nodi o nei punti di contatto** | Qualsiasi componente per tutti i nodi, compresi metriche, metriche calcolate, dimensioni, elementi dimensionali, filtri e intervalli di date. | Qualsiasi componente per tutti i nodi, compresi metriche, metriche calcolate, dimensioni, elementi dimensionali, filtri e intervalli di date. | Solo elementi dimensionali (ad eccezione del punto di contatto iniziale e finale) |
| **Confronta filtri** | No | Sì<p>Eseguire confronti affiancati di due diversi filtri nello stesso rapporto</p> | No |
| **percorsi Adobe Journey Optimizer** | Sì</br>Apri percorsi da Journey Optimizer per analisi più approfondite e personalizzazione | No | No |

{style="table-layout:auto"}
