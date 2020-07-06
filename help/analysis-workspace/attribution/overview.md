---
title: Panoramica su Attribution
description: Concetto di attribuzione del credito di un evento di successo a più valori di dimensione.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 50%

---


# Panoramica su Attribution

>[!NOTE]
>
>Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Attribuzione consente agli analisti di personalizzare il modo in cui i valori delle dimensioni ottengono credito per gli eventi di successo. Ad esempio:

1. Un visitatore del sito fa clic su un collegamento di ricerca a pagamento per una delle pagine del prodotto. Consente di aggiungere il prodotto al carrello, ma non di acquistarlo.
2. Il giorno successivo, l&#39;utente può consultare un post su social media di uno dei suoi amici, fare clic sul collegamento e completare l&#39;acquisto.

In alcuni rapporti, potreste desiderare l’ordine attribuito alla ricerca a pagamento. In altri rapporti, potreste desiderare l&#39;ordine attribuito a Social. Attribuzione consente di controllare questo aspetto del reporting. È disponibile per tutte le organizzazioni su Adobe  Analytics Ultimate, Prime, Select e Foundation. Se non sei sicuro del tipo di contratto che hai con Adobe, contatta l&#39;Account Manager della tua organizzazione.

## Valore di attribuzione IQ

Un determinato percorso del cliente non è lineare e spesso imprevedibile. Ogni cliente procede secondo il proprio ritmo: spesso si torna indietro, si ferma, inizia di nuovo o si impegna in altri comportamenti non lineari. Queste azioni organiche rendono difficile conoscere l’impatto effettivo delle attività di marketing lungo il percorso del cliente. Inoltre, ostacola gli sforzi volti a collegare più canali di dati tra loro.

![Problema di Attribution IQ](assets/attribution_iq_problem.png)

Adobe Analytics migliora l’attribuzione consentendo di:

* Definire l’attribuzione oltre i mezzi di comunicazione comprati: è possibile applicare ai modelli qualsiasi dimensione, metrica, canale o evento (ad es. ricerca interna), non solo le campagne di marketing.
* Utilizzare il confronto illimitato tra modelli di attribuzione: è possibile confrontare in modo dinamico tanti modelli quanti se ne desiderano.
* Evitare le modifiche di implementazione: con l’elaborazione al momento della generazione del rapporto e le sessioni in base al contesto, è possibile integrare e applicare il contesto del percorso del cliente in fase di esecuzione.
* Costruire la sessione che si adatta al meglio allo scenario di attribuzione.
* Suddividere l’attribuzione in base ai segmenti: è possibile confrontare facilmente le prestazioni dei canali di marketing in qualsiasi segmento importante (ad es. clienti nuovi rispetto a clienti di ritorno, prodotto X rispetto a prodotto Y, livello di fedeltà rispetto a Customer Lifetime Value).
* Ispezionare l’analisi incrociata e a più contatti dei canali: è possibile utilizzare diagrammi di Venn, istogrammi e risultati di attribuzione di tendenze.
* Analizzare visivamente sequenze di marketing principali: è possibile esplorare in modo visivo i percorsi che hanno condotto alla conversione, con visualizzazioni di abbandono e di flusso a più nodi.
* Costruire metriche calcolate: è possibile utilizzare un qualsiasi numero di metodi di allocazione di attribuzione.

## Funzioni

Attribution IQ include le seguenti funzionalità:

* [Pannello](../c-panels/attribution.md)Attribuzione: Prendi qualsiasi dimensione e metrica e confrontala rapidamente con diversi modelli di attribuzione.
* [Applica attribuzione a una metrica](../build-workspace-project/column-row-settings/column-settings.md): Utilizzate un&#39;attribuzione non predefinita su qualsiasi metrica in un progetto.
* [Applica attribuzione a una suddivisione](/help/components/dimensions/t-breakdown-fa.md): Utilizzate un&#39;attribuzione non predefinita per una suddivisione.
* [Confronta modelli](/help/components/apply-create-metrics.md)di attribuzione: Scopri rapidamente i diversi modelli di attribuzione rispetto a qualsiasi metrica.
