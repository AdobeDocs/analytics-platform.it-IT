---
title: Rapporto sui dati Google Analytics in Customer Journey Analytics
description: Mostra utili rapporti sui dati Google Analytics in Customer Journey Analytics
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 35%

---

# Rapporto sui dati Google Analytics in Customer Journey Analytics

Una volta che i dati sono disponibili in Customer Journey Analytics, gli esempi seguenti forniscono scenari utili per la generazione di rapporti su tali dati.

## Visualizzare dati da web e app come set di dati combinati

Questo diagramma di Venn mostra la sovrapposizione degli utenti dal sito web (dai dati Google Analytics), dall’app mobile (dai dati Firebase) e dal call center. Evidenzia inoltre i prodotti con prestazioni migliori, non solo sul web, ma anche nell’app mobile. Puoi anche ottenere i ricavi totali da entrambi utilizzando una metrica calcolata. Osserva come i prodotti migliori raccontano una storia diversa quando si considerano i ricavi combinati. Senza i set di dati combinati, non sarebbe stato possibile comprendere il successo dell’articolo “Twill cap”.

![Dataset combinati](../assets/combined-datasets.png)

## Identificare i motivi delle chiamate e ridurre il volume di chiamate

Puoi impostare la tendenza del tempo impiegato dal call center negli ultimi due mesi per determinare il volume delle chiamate. L’esempio seguente mostra la tendenza di questi dati negli ultimi due mesi. L’esempio seguente mostra una tendenza crescente che può influire sui costi organizzativi.

![Volume di chiamata](../assets/call-volume.png)

L’utilizzo della dimensione &quot;Motivo della chiamata&quot; può suggerire modi per migliorare l’esperienza web, impedendo ai visitatori di invocare in primo luogo. L&#39;esempio precedente mostra che il &quot;prodotto danneggiamento&quot; ha un tempo medio di chiamata di circa 3 minuti per chiamata, dando alla tua organizzazione un modo preciso per migliorare l&#39;esperienza del cliente e ridurre i costi del call center.

Puoi visualizzare quali prodotti causano la maggior parte delle chiamate al call center e quanti clienti hanno effettuato tali chiamate. Il grafico a bolle mostra che 20.000 persone hanno chiamato, hanno trascorso più di 4 ore e 30 minuti e hanno restituito 33 unità del prodotto &quot;Men&#39;s short Sleeve Tee&quot;.

![Motivo della chiamata](../assets/call-reason.png)

Applicando un raggruppamento delle dimensioni di &quot;Motivo chiamata&quot;, l’esempio mostra un elemento dimensione &quot;Prodotto danneggiato&quot;. A questo punto non resta che contattare il reparto di controllo qualità e cercare di capire perché i clienti hanno ricevuto T-shirt danneggiate.

Puoi vedere quali pagine web hanno portato le chiamate al call center. Questo rapporto ti consente di sapere dove si trovano le esperienze meno ottimali sul sito web e di aiutare i responsabili dei prodotti a risolvere tali problemi. Nell&#39;esempio seguente viene utilizzata una metrica calcolata per filtrare i dati in base alle sole sessioni terminate con una chiamata al call center. Utilizza anche il modello di &quot;partecipazione&quot; nel modello di CJA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=it#cja-workspace).

L’esempio seguente mostra che le pagine &quot;Carrello acquisti&quot; e &quot;Informazioni di pagamento&quot; generano la maggior parte delle chiamate.

![Pagine contributi](../assets/contributing-pages.png)

La tabella coorte consente di vedere quanto tempo normalmente gli utenti devono chiamare il call center dopo aver visitato il sito web. L’esempio seguente indica che il tempo medio per questo set di dati di esempio è tra tre e quattro settimane.

Coorte ![](../assets/cohort.png)

## Utilizzare l’attribuzione marketing avanzata

CJA consente di utilizzare modelli di attribuzione sofisticati sui dati multicanale. L’esempio seguente propone un confronto tra l’applicazione dell’attribuzione Ultimo contatto, Primo contatto, A forma di U e Algoritmica dei ricavi alla dimensione Raggruppamenti canali di Google Analytics.

![Attribuzione di marketing](../assets/mktg-attribution.png)

Con una metrica calcolata, puoi applicare tale attribuzione ai ricavi dal web, dall’app mobile e persino rimuovere eventuali resi. Il risultato è un importo realmente netto per ogni canale di marketing.

![Metrica calcolata](../assets/calc-metric.png)

Attribution IQ consente inoltre di filtrare i dati. Puoi visualizzare l’attribuzione rispetto a solo specifici set di utenti, ad esempio considerando solo chi utilizza più dispositivi.

![Filtro](../assets/filter.png)

Puoi anche attribuire i ricavi per web e app al contenuto dell&#39;annuncio Google. L&#39;esempio di questo set di dati ha guadagnato più entrate dall&#39;app mobile guidata da Google Ads online che dal web. Ordinando gli annunci in base ai ricavi da web e app, ottieni un&#39;immagine diversa di quali erano i tuoi annunci Google più performanti.

![annuncio Google](../assets/google-ad.png)

La combinazione di set di dati in CJA consente di vedere in questo esempio che gli annunci online hanno avuto un impatto sui prodotti acquistati nella tua app mobile. La visualizzazione seguente mostra che i ricavi delle app mobili da Google Ads rappresentano un ulteriore da $ 14 k - $ 15 k, rispetto al solo web.

![Google ad 2](../assets/google-ad2.png)
