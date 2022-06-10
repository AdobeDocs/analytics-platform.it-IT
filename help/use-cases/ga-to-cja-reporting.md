---
title: Rapporto sui dati Google Analytics in Customer Journey Analytics
description: Mostra utili rapporti sui dati Google Analytics in Customer Journey Analytics
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: ht
source-wordcount: '807'
ht-degree: 100%

---

# Rapporto sui dati Google Analytics in Customer Journey Analytics

Ora che hai [acquisito i dati Google Analytics in Experience Platform e Customer Journey Analytics (CJA)](/help/use-cases/ga-to-cja.md), ti mostreremo alcuni utili scenari per la generazione di rapporti su tali dati.

## Visualizzare dati da web e app come set di dati combinati

Questo diagramma di Venn mostra la sovrapposizione degli utenti dal sito web (dai dati Google Analytics), dall’app mobile (dai dati Firebase) e dal call center. Evidenzia inoltre i prodotti con prestazioni migliori, non solo sul web, ma anche nell’app mobile. Utilizzando una metrica calcolata, puoi ottenere il totale dei ricavi da entrambi i canali. Osserva come i prodotti migliori raccontano una storia diversa quando si considerano i ricavi combinati. Senza i set di dati combinati, non sarebbe stato possibile comprendere il successo dell’articolo “Twill cap”.

![](assets/combined-datasets.png)

## Identificare i motivi delle chiamate e ridurre il volume di chiamate

Per verificare se si sta ricevendo un numero elevato di chiamate, puoi impostare la durata del call center sugli ultimi 2 mesi. Così facendo è facile osservare la tendenza in crescita. È un aspetto preoccupante, dato che ogni minuto che gli agenti del call center sono impegnati al telefono costa denaro e incide sui risultati complessivi.

Diamo un’occhiata ai principali motivi dell’aumento delle chiamate al call center. Puoi osservare che i motivi principali sono “Carta di credito rifiutata”, “Rimozione carta di credito” e “Prodotto danneggiato”. Questi possono già suggerire come migliorare l’esperienza online. Si può anche osservare la tendenza di tali motivi di chiamata e vedere quali hanno contribuito maggiormente al picco complessivo. È interessante notare che le chiamate per “Prodotto danneggiato” richiedono più di 3 minuti a chiamata.

![](assets/call-volume.png)

Da un’analisi più approfondita, possiamo vedere a quali prodotti è imputabile la maggior parte delle chiamate al call center, e quanti clienti hanno effettuato tali chiamate. Il grafico a bolla indica che hanno chiamato 20.000 persone, per più di 4 ore e 30 minuti, e che sono stati rese 33 unità del prodotto “T-shirt uomo maniche corte”.

Impostando raggruppamenti in base alla dimensione “Motivo chiamata”, possiamo capire perché queste persone hanno restituito il prodotto. La maggior parte delle chiamate è dovuta a “Prodotto danneggiato”. A questo punto non resta che contattare il reparto di controllo qualità e cercare di capire perché i clienti hanno ricevuto T-shirt danneggiate.

![](assets/call-reason.png)

Ora esaminiamo le pagine del sito web che hanno generato chiamate al call center. Questo consente di capire quali aree del sito web offrono esperienze peggiori, affinché i Product Manager possano risolvere tali problemi.

A tale scopo è possibile:

* Utilizzare una metrica calcolata per filtrare i dati in base alle sole sessioni terminate con una chiamata al call center.
* Utilizzare il modello di “partecipazione” in CJA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=it#cja-workspace).

Puoi vedere facilmente le pagine in cui si verifica più spesso una sessione che termina con una chiamata. In questo esempio, si tratta delle pagine “Carrello acquisti” e “Dati di pagamento”. Grazie all’inclusione dei dati Firebase dall’app mobile, puoi anche vedere a quali errori di pagina e arresti dell’app sono imputabili le chiamate. Si tratta di dati molto importanti, che consentono di migliorare l’esperienza offerta tramite web e app mobile.

![](assets/contributing-pages.png)

Infine, utilizzando la tabella coorte in Analysis Workspace, è facile vedere quanto tempo dopo aver visitato il sito web un utente chiama il call center. Qui si può vedere che il tempo medio è tra 3 e 4 settimane.

![](assets/cohort.png)

## Utilizzare l’attribuzione marketing avanzata

CJA consente di utilizzare modelli di attribuzione sofisticati sui dati provenienti da diversi canali. L’esempio seguente propone un confronto tra l’applicazione dell’attribuzione Ultimo contatto, Primo contatto, A forma di U e Algoritmica dei ricavi alla dimensione Raggruppamenti canali di Google Analytics.

![](assets/mktg-attribution.png)

Con una metrica calcolata, puoi applicare tale attribuzione ai ricavi dal web, dall’app mobile e persino rimuovere eventuali resi. Il risultato è un importo realmente netto per ogni canale di marketing.

![](assets/calc-metric.png)

Attribution IQ consente inoltre di filtrare facilmente i dati. Puoi visualizzare l’attribuzione rispetto a solo specifici set di utenti, ad esempio considerando solo chi utilizza più dispositivi.

![](assets/filter.png)

Infine, puoi anche attribuire i ricavi dal sito web e dall’app ai contenuti Google Ad. Puoi osservare come, dagli annunci Google Ads online, hai ottenuto ricavi più elevati dall’app mobile rispetto al sito web. Ordinando gli annunci in base ai ricavi derivanti dal web e dall’app, si ottiene un quadro molto diverso di quali siano gli annunci Google Ads più preformanti.

![](assets/google-ad.png)

Senza CJA, non avresti potuto sapere che gli annunci online avessero un impatto sui prodotti acquistati dall’app mobile. Ora puoi vedere che i ricavi dall’app mobile generati da Google Ads rappresentano un ulteriore $ 14.000 - $ 5.000, rispetto al solo web.

![](assets/google-ad2.png)
