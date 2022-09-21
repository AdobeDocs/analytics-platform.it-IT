---
title: Rapporto sui dati Google Analytics in Customer Journey Analytics
description: Mostra utili rapporti sui dati Google Analytics in Customer Journey Analytics
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: ht
source-wordcount: '694'
ht-degree: 100%

---

# Rapporto sui dati Google Analytics in Customer Journey Analytics

Quando i dati sono disponibili in Customer Journey Analytics, gli esempi seguenti forniscono scenari utili per la generazione di rapporti su tali dati.

## Visualizzare dati da web e app come set di dati combinati

Questo diagramma di Venn mostra la sovrapposizione degli utenti dal sito web (dai dati Google Analytics), dall’app mobile (dai dati Firebase) e dal call center. Evidenzia inoltre i prodotti con prestazioni migliori, non solo sul web, ma anche nell’app mobile. Utilizzando una metrica calcolata, puoi anche ottenere il totale dei ricavi da entrambi i canali. Osserva come i prodotti migliori raccontano una storia diversa quando si considerano i ricavi combinati. Senza i set di dati combinati, non sarebbe stato possibile comprendere il successo dell’articolo “Twill cap”.

![Dataset combinati](../assets/combined-datasets.png)

## Identificare i motivi delle chiamate e ridurre il volume di chiamate

Puoi impostare la tendenza del tempo impiegato dal call center negli ultimi due mesi per determinare il volume delle chiamate. L’esempio seguente mostra la tendenza di questi dati negli ultimi due mesi. L’esempio seguente mostra una tendenza crescente che può influire sui costi organizzativi.

![Volume di chiamata](../assets/call-volume.png)

L’utilizzo della dimensione “Motivo della chiamata” può suggerire modi per migliorare l’esperienza web, evitando in primo luogo che i visitatori debbano chiamare. L’esempio precedente mostra che “Prodotto danneggiato” ha un tempo medio di circa 3 minuti per chiamata, dando alla tua organizzazione un modo preciso per migliorare l’esperienza del cliente e ridurre i costi del call center.

Puoi visualizzare quali prodotti causano la maggior parte delle chiamate al call center e quanti clienti hanno effettuato tali chiamate. Il grafico a bolla indica che hanno chiamato 20.000 persone, per più di 4 ore e 30 minuti, e che sono stati rese 33 unità del prodotto “T-shirt uomo maniche corte”.

![Motivo della chiamata](../assets/call-reason.png)

Nell’esempio, l’applicazione di un breakdown per la dimensione “Motivo chiamata” mostra un elemento dimensione “Prodotto danneggiato”. A questo punto non resta che contattare il reparto di controllo qualità e cercare di capire perché i clienti hanno ricevuto T-shirt danneggiate.

Puoi vedere quali pagine web hanno portato le chiamate al call center. Questo rapporto consente di capire quali aree del sito web offrono esperienze non ottimali, affinché i Product Manager possano occuparsi di migliorarle. L’esempio seguente utilizza una metrica calcolata per filtrare i dati in base alle sole sessioni terminate con una chiamata al call center. Utilizza anche il modello di “partecipazione” nel modello [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=it#cja-workspace) di CJA.

L’esempio seguente mostra che le pagine “Carrello acquisti” e “Informazioni di pagamento” generano la maggior parte delle chiamate.

![Pagine che contribuiscono](../assets/contributing-pages.png)

La tabella coorte consente di vedere dopo quanto tempo normalmente gli utenti chiamano il call center dopo aver visitato il sito web. L’esempio seguente indica che il tempo medio per questo set di dati di esempio è tra tre e quattro settimane.

![Coorte](../assets/cohort.png)

## Utilizzare l’attribuzione marketing avanzata

CJA consente di utilizzare modelli di attribuzione sofisticati sui dati provenienti da diversi canali. L’esempio seguente propone un confronto tra l’applicazione dell’attribuzione Ultimo contatto, Primo contatto, A forma di U e Algoritmica dei ricavi alla dimensione Raggruppamenti canali di Google Analytics.

![Attribuzione di marketing](../assets/mktg-attribution.png)

Con una metrica calcolata, puoi applicare tale attribuzione ai ricavi dal web, dall’app mobile e persino rimuovere eventuali resi. Il risultato è un importo realmente netto per ogni canale di marketing.

![Metrica calcolata](../assets/calc-metric.png)

Attribution IQ consente inoltre di filtrare i dati. Puoi visualizzare l’attribuzione rispetto a solo specifici set di utenti, ad esempio considerando solo chi utilizza più dispositivi.

![Filtro](../assets/filter.png)

Puoi anche attribuire i ricavi dal sito web e dall’app ai contenuti Google Ad. L’esempio di questo set di dati ha portato maggiori ricavi dall’app mobile guidata da Google Ads online che dal web. Ordinando gli annunci in base ai ricavi derivanti dal web e dall’app, ottieni un quadro diverso di quali siano gli annunci Google Ads più preformanti.

![Google Ad](../assets/google-ad.png)

La combinazione di set di dati in CJA consente di vedere in questo esempio che gli annunci online hanno avuto un impatto sui prodotti acquistati nella tua app mobile. La visualizzazione seguente mostra che i ricavi dall’app mobile generati da Google Ads rappresentano un ulteriore $ 14.000 - $ 15.000, rispetto al solo web.

![Google Ad 2](../assets/google-ad2.png)
