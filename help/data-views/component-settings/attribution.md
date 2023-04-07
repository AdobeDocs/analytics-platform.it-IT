---
title: Impostazioni dei componenti di attribuzione
description: Consente di impostare l’attribuzione predefinita per una metrica.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: f49529768d84699b17d2f690daad6dd463166e30
workflow-type: tm+mt
source-wordcount: '1778'
ht-degree: 42%

---

# Impostazioni dei componenti di attribuzione

Attribution ti consente di personalizzare il modo in cui gli elementi dimensionali ottengono credito per gli eventi di successo. Ad esempio:

1. Un visitatore del sito fa clic su un collegamento di ricerca a pagamento a una delle pagine dei tuoi prodotti. Aggiunge il prodotto al carrello, ma non lo acquista.
2. Il giorno successivo, vedrete un post sui social media di uno dei loro amici. Fare clic sul collegamento, quindi completare l’acquisto.

In alcuni rapporti, potresti desiderare che l’ordine sia attribuito a Ricerca a pagamento. In altri rapporti, potresti desiderare che l’ordine sia attribuito a Social. Attribution ti consente di controllare questo aspetto del reporting.

Questa impostazione del componente di visualizzazione dati consente di impostare un modello di attribuzione predefinito per una metrica. Puoi sovrascrivere il modello di attribuzione di una data metrica mentre lavori in Analysis Workspace.

![Attribuzione](../assets/attribution-settings.png)

Se la tua organizzazione richiede che una metrica abbia più impostazioni di attribuzione, puoi effettuare una delle seguenti operazioni:

* Copia la metrica nella visualizzazione dati con ogni impostazione di attribuzione desiderata. È possibile includere la stessa metrica più volte in una visualizzazione dati, assegnando a ciascuna metrica un’impostazione diversa. Assicurati di etichettare correttamente ogni metrica in modo che gli analisti comprendano la differenza tra queste metriche durante la generazione dei rapporti.
* Escludi la metrica in Analysis Workspace. In una metrica [Impostazioni colonna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md), seleziona **[!UICONTROL Use non-default attribution model]** per modificare il modello di attribuzione e l’intervallo di lookback della metrica per quel rapporto specifico.

## Modelli di attribuzione

Un modello di attribuzione determina quali elementi dimensionali ricevono credito per una metrica quando più valori vengono visualizzati all’interno dell’intervallo di lookback di una metrica. I modelli di attribuzione si applicano solo quando sono presenti più elementi dimensionali impostati all’interno dell’intervallo di lookback. Se è impostato un solo elemento dimensione, tale elemento dimensione ottiene il 100% di credito indipendentemente dal modello di attribuzione utilizzato.

| Icona | Modello di attribuzione | Definizione |
| :---: | :--- | --- |
| ![Ultimo contatto](../assets/attribution-models/last_touch1.png) | Ultimo contatto | Attribuisce un credito del 100% al punto di contatto più di recente che si verifica prima della conversione. Questo modello di attribuzione è in genere il valore predefinito per qualsiasi metrica in cui non viene specificato diversamente un modello di attribuzione. Le organizzazioni in genere utilizzano questo modello quando il tempo di conversione è relativamente breve, ad esempio con l’analisi delle parole chiave di ricerca interne. |
| ![Primo contatto](../assets/attribution-models/first_touch.png) | Primo contatto | Attribuisce un credito del 100% al punto di contatto visualizzato per la prima volta nell’intervallo di lookback dell’attribuzione. Le organizzazioni in genere utilizzano questo modello per comprendere la brand awareness o l&#39;acquisizione da parte dei clienti. |
| ![Lineare](../assets/attribution-models/linear.png) | Lineare | Attribuisce lo stesso credito a ogni punto di contatto che porta a una conversione. È utile quando i cicli di conversione sono più lunghi o richiedono un coinvolgimento del cliente più frequente. Le organizzazioni in genere utilizzano questo modello di attribuzione per misurare l’efficacia delle notifiche delle app mobili o con prodotti basati su abbonamento. |
| ![Partecipazione](../assets/attribution-models/participation.png) | Partecipazione | Assegna il 100% di credito a tutti i punti di contatto univoci. Poiché ogni punto di contatto riceve un credito del 100%, i dati delle metriche in genere ammontano a più del 100%. Se un elemento dimensionale appare più volte separatamente prima di una conversione, i valori vengono deduplicati al 100%. Questo modello di attribuzione è ideale nelle situazioni in cui desideri comprendere a quali punti di contatto i clienti sono maggiormente esposti. Generalmente, le organizzazioni di media utilizzano questo modello per calcolare la velocità dei contenuti. Le organizzazioni di vendita al dettaglio utilizzano in genere questo modello per capire quali parti del sito sono fondamentali per la conversione. |
| ![Stesso contatto](../assets/attribution-models/same_touch.png) | Stesso contatto | Attribuisce un credito del 100% allo stesso hit in cui si è verificata la conversione. Se un punto di contatto non si verifica sullo stesso hit di una conversione, viene inserito in “None”. Questo modello di attribuzione a volte è equiparato a non avere alcun modello di attribuzione. È utile in scenari in cui non desideri valori derivanti da altri risultati che influenzano il modo in cui una metrica attribuisce credito agli elementi dimensionali. I team che si occupano di prodotti o design possono utilizzare questo modello per valutare l’efficacia di una pagina in cui si verifica una conversione. |
| ![A forma di U](../assets/attribution-models/u_shaped.png) | A forma di U | Attribuisce il 40% di credito alla prima interazione, il 40% di credito all’ultima interazione e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato un credito del 50% a entrambi. Questo modello di attribuzione viene utilizzato in modo ottimale in scenari in cui valorizzi di più la prima e l’ultima interazione, ma non desideri ignorare completamente le interazioni aggiuntive nel mezzo. |
| ![Curva a J](../assets/attribution-models/j_shaped.png) | Curva a J | Attribuisce il 60% di credito all’ultima interazione, il 20% di credito alla prima interazione e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato il 75% di credito all’ultima interazione e il 25% di credito alla prima. Simile a forma di U, questo modello di attribuzione favorisce le prime e le ultime interazioni, ma favorisce maggiormente l’ultima interazione. |
| ![J inversa](../assets/attribution-models/inverse_j.png) | J inversa | Attribuisce un credito del 60% al primo punto di contatto, un credito del 20% all’ultimo punto di contatto e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato il 75% di credito alla prima interazione e il 25% di credito all’ultima. Simile a forma di J, questo modello di attribuzione favorisce le prime e le ultime interazioni, ma favorisce maggiormente la prima interazione. |
| ![Decadimento nel tempo](../assets/attribution-models/time_decay.png) | Decadimento nel tempo | Segue un decadimento esponenziale con un parametro di mezza durata personalizzato, dove il valore predefinito è 7 giorni. Il valore di ciascun canale dipende dalla quantità di tempo trascorsa tra l’avvio del punto di contatto e l’eventuale conversione. La formula utilizzata per determinare il credito è `2^(-t/halflife)`, dove `t` è il tempo tra un punto di contatto e una conversione. Tutti i punti di contatto vengono quindi normalizzati al 100%. Ideale per scenari in cui desideri misurare l’attribuzione rispetto a un evento specifico e significativo. Più una conversione si verifica dopo questo evento, meno credito viene assegnato. |
| ![Personalizzato](../assets/attribution-models/custom.png) | Personalizzato | Consente di specificare i pesi da assegnare al primo punto di contatto, all’ultimo punto di contatto ed eventuali punti di contatto intermedi. I valori specificati vengono normalizzati al 100% anche se la somma dei numeri personalizzati immessi è inferiore a 100. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le interazioni con due punti di contatto, il parametro intermedio viene ignorato. Il primo e l’ultimo punto di contatto vengono quindi normalizzati al 100% e il credito viene assegnato di conseguenza. Questo modello è ideale per gli analisti che desiderano un controllo completo sul proprio modello di attribuzione e hanno esigenze specifiche che altri modelli di attribuzione non soddisfano. |
| ![Algoritmica](../assets/attribution-models/algorithmic.png) | Algoritmica | Utilizza tecniche statistiche per determinare in modo dinamico l’allocazione ottimale del credito per la metrica selezionata. L’algoritmo utilizzato per l’attribuzione è basato sul dividendo Harsanyi dalla teoria del gioco cooperativo. Il dividendo Harsanyi è una generalizzazione della soluzione del valore di Shapley (che prende il nome da Lloyd Shapley, un economista premio Nobel) per la distribuzione del credito tra i giocatori in un gioco con contributi disuguali al risultato.<br>Ad un livello elevato, l&#39;attribuzione è calcolata come una coalizione di giocatori a cui un surplus deve essere equamente distribuito. La distribuzione del surplus di ogni coalizione è determinata in base al surplus creato in precedenza da ogni subcoalizione (o elementi dimensionali partecipanti in precedenza) in modo ricorsivo. Per maggiori dettagli, vedi gli articoli originali di John Harsanyi e Lloyd Shapley:<br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Intervallo di lookback

Per intervallo di lookback si intende la quantità di tempo che una conversione deve recuperare nel passato per includere i punti di contatto. Se un elemento dimensione è impostato all’esterno dell’intervallo di lookback, il valore non viene incluso in alcun calcolo di attribuzione.

* **14 giorni**: Effettua l’analisi fino a 14 giorni dopo l’avvenuta conversione.
* **30 giorni**: Effettua l’analisi fino a 30 giorni dopo l’avvenuta conversione.
* **60 giorni**: Effettua l’analisi fino a 60 giorni da quando si è verificata la conversione.
* **90 giorni**: Considera fino a 90 giorni da quando si è verificata la conversione.
* **Sessione**: Considera fino all’inizio della sessione in cui si è verificata una conversione. Gli intervalli di lookback delle sessioni rispettano le modifiche apportate [Timeout sessione](../create-dataview.md#session-settings).
* **Persona (finestra di reporting)**: Esamina tutte le visite fino al primo del mese dell’intervallo di date corrente. Ad esempio, se l’intervallo di date del rapporto è dal 15 settembre al 30 settembre, l’intervallo di date del lookback su visitatore considererà il periodo dal 1° al 30 settembre. Se utilizzi questo intervallo di lookback, occasionalmente puoi vedere che gli elementi dimensionali sono attribuiti a date al di fuori dell’intervallo di reporting.
* **Ora personalizzata:** Consente di impostare un intervallo di lookback personalizzato a partire da quando si è verificata una conversione. È possibile specificare il numero di minuti, ore, giorni, settimane, mesi o trimestri. Ad esempio, se il 20 febbraio si è verificata una conversione, un intervallo di lookback di cinque giorni valuterebbe tutti i punti di contatto delle dimensioni dal 15 febbraio al 20 febbraio nel modello di attribuzione.

## Esempio

Prendi in considerazione l’esempio seguente:

1. Il 15 settembre, un visitatore arriva sul tuo sito tramite un annuncio pubblicitario di ricerca a pagamento, poi se ne va.
2. Il 18 settembre, il visitatore ritorna sul tuo sito tramite un collegamento social media ricevuto da un amico. Aggiunge diversi articoli al carrello, ma non acquista nulla.
3. Il 24 settembre, il team marketing gli invia un’e-mail con un coupon da utilizzare su alcuni degli elementi nel carrello. Applica il coupon, ma visita diversi altri siti per vedere se sono disponibili altri coupon. Ne trova un altro tramite un annuncio pubblicitario, quindi completa un acquisto dal valore di 50 $.

A seconda dell’intervallo di lookback e del modello di attribuzione definiti, ai canali saranno assegnati crediti diversi. Di seguito sono riportati alcuni esempi significativi:

* Utilizzo **primo contatto** e **intervallo di lookback su sessione**, l’attribuzione considera solo la terza visita. Tra e-mail e visualizzazione, e-mail è avvenuta prima, quindi e-mail ottiene 100% di credito per l’acquisto di 50 $.
* Utilizzo **primo contatto** e **intervallo di lookback su persona**, l’attribuzione esamina tutte e tre le visite. La ricerca a pagamento è avvenuta prima, quindi ottiene il 100% di credito per l’acquisto di 50 $.
* Utilizzo **lineare** e **intervallo di lookback su sessione**, il credito è suddiviso tra e-mail e visualizzazione. Entrambi questi canali ricevono un credito di 25 $.
* Utilizzo **lineare** e **intervallo di lookback su persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione. Ogni canale ottiene un credito di 12,50 $ per questo acquisto.
* Utilizzo **A forma di J** e **intervallo di lookback su persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione.
   * Il 60% di credito è assegnato alla visualizzazione, per un valore di 30 $.
   * Il 20% di credito è assegnato alla ricerca a pagamento, per un valore di 10 $.
   * Il restante 20% è suddiviso tra social e e-mail, ovvero 5 $ ciascuno.
* Utilizzo **Decadimento nel tempo** e **intervallo di lookback su persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione. Utilizzando la mezza durata predefinita di 7 giorni:
   * Intervallo di zero giorni tra il punto di contatto visualizzazione e la conversione. `2^(-0/7) = 1`
   * Intervallo di zero giorni tra il punto di contatto e-mail e la conversione. `2^(-0/7) = 1`
   * Intervallo di sei giorni tra il punto di contatto social e la conversione. `2^(-6/7) = 0.552`
   * Intervallo di nove giorni tra il punto di contatto ricerca a pagamento e la conversione. `2^(-9/7) = 0.41`
   * La normalizzazione di questi valori determina quanto segue:
      * Visualizzazione: 33,8%, ovvero 16,88 $
      * E-mail: 33,8% ovvero 16,88 $
      * Social: 18,6%, ovvero 9,32 $
      * Ricerca a pagamento: 13,8%, ovvero 6,92 $

Gli eventi di conversione che generalmente hanno numeri interi vengono suddivisi se il credito appartiene a più di un canale. Ad esempio, se due canali contribuiscono a un ordine utilizzando un modello di attribuzione lineare, entrambi i canali ottengono 0,5 di tale ordine. Queste metriche parziali vengono sommate tra tutte le persone e quindi arrotondate al numero intero più vicino per la generazione del rapporto.
