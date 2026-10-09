---
title: Integrazione Brand Visibility
description: Integrare Brand Visibility con Customer Journey Analytics
feature: Experience Platform Integration
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: fb3ebdba335ce2dde30d37b8aff4e8f201dc5d9f
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%
---

# Integrazione con Adobe Brand Visibility

[Adobe Brand Visibility](https://experienceleague.adobe.com/it/docs/brand-visibility/using/home){target="_blank"} è un&#39;applicazione di intelligenza artificiale generativa per l&#39;ottimizzazione dei motori generativi, progettata per aiutare i brand a migliorare la visibilità, la precisione e l&#39;influenza negli ambienti di ricerca basati sull&#39;intelligenza artificiale. Brand Visibility fornisce informazioni approfondite sulla presenza dei brand nelle risposte generate dall’intelligenza artificiale, offre contenuti consigliati e automatizza le correzioni di ottimizzazione.

L’intelligenza artificiale è diventato un canale di rilevamento primario. Gli agenti LLM (Large Language Model), come ChatGPT, Claude, Copilot e Perplexity, scansionano i contenuti del brand.

>[!NOTE]
>
>È necessario disporre di un’offerta a pagamento Visibilità dei brand predisposta e connessa alla configurazione Experience Platform tramite il connettore gestito.


>[!IMPORTANT]
>
>Come parte di questa integrazione, alcuni trattamenti temporanei dei dati Brand Visibility avvengono negli Stati Uniti. I dati vengono infine memorizzati nell’area geografica designata, come configurato nel contratto Customer Journey Analytics.


## Casi d’uso

L&#39;integrazione tra Customer Journey Analytics e Brand Visibility offre i seguenti vantaggi:

* **Integrazione in entrata**: utilizza i dati Brand Visibility in Customer Journey Analytics per misurare il traffico basato su LLM (crawler bot, richieste RAG, attività agente) insieme a dati Web, mobili e di altro tipo esistenti. Sarà possibile, ad esempio:

  * Misura il traffico guidato da LLM per origine agente insieme ai canali tradizionali.

  * Identifica i contenuti molto utilizzati dai moduli LLM, ma con prestazioni inferiori nella conversione umana.

  * Rilevare dove le richieste dell’agente LLM non vanno a buon fine nei percorsi critici.

  * Confronta la domanda di bot LLM per una pagina con le conversioni e i ricavi di tale pagina nei dati web, confrontati a livello di URL e host.

* **Integrazione in uscita**: invia dati sulle prestazioni di Customer Journey Analytics a Brand Visibility in modo da ottimizzare la visibilità AI per le origini LLM che inviano traffico prezioso, ad esempio ChatGPT o Perplessity. Sarà possibile, ad esempio:

  * Scopri quali fonti LLM inviano visitatori umani che continuano a convertire o generare ricavi. Customer Journey Analytics misura questo dal traffico web di riferimento, non dal set di dati bot.
  * Classifica le origini LLM in base al valore a valle dei visitatori umani inviati, quindi concentra il tuo lavoro di visibilità AI sulle origini che ottengono i migliori risultati.


## Integrazione in entrata

Il traffico LLM raggiunge il sito in due modi. Customer Journey Analytics misura ogni modo da un’origine dati diversa.

Il primo modo è una persona che legge una risposta di IA e poi fa clic sul sito. Tale visita esegue lo stesso JavaScript che raccoglie il resto dei dati web. I dati web Customer Journey Analytics esistenti includono quindi la visita e il dominio di riferimento che ti ha inviato l’utente, ad esempio chatgpt.com. Customer Journey Analytics non etichetta queste visite come traffico AI di per sé. Per identificarli e raggrupparli, crea un campo derivato sulla connessione che corrisponde ai domini di riferimento di IA, quindi genera segmenti e rapporti su tale campo. Vedi [Campi derivati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}. Non è necessario il set di dati Brand Visibility per questo traffico umano.

Il secondo modo è un bot o un agente che richiede direttamente le pagine. Ciò include crawler che generano un indice di intelligenza artificiale e recuperi live che si verificano quando un utente invia una richiesta a un assistente di intelligenza artificiale. Queste richieste non eseguono JavaScript, pertanto i dati web esistenti non li registrano. Il set di dati Brand Visibility acquisisce questo traffico dal livello CDN. Il resto di questa sezione descrive tale set di dati.


### Onboarding del set di dati

Il connettore gestito Brand Visibility fornisce i dati ad Experience Platform come set di dati di riepilogo. Per misurarlo in Customer Journey Analytics, è necessario completare due passaggi di configurazione:

1. Crea una connessione che includa il set di dati Brand Visibility.
2. Crea una visualizzazione dati sulla connessione. La visualizzazione dati rende disponibili in Analysis Workspace le dimensioni e le metriche riportate di seguito.

Il set di dati:

* Utilizza [set di dati di riepilogo](/help/data-views/summary-data.md) basati sulla classe Metriche di riepilogo XDM.
* Dati bucket per URL e host, ora e caratteristiche di richiesta come tipo di bot, provider CDN e stato.

>[!NOTE]
>
>Il set di dati Brand Visibility contiene dati aggregati. Non contiene dati PII come identificatori utente, prompt o risposte.
>

Poiché è un set di dati di riepilogo, puoi utilizzarlo come set di dati di ricerca e unirlo a un set di dati evento su una chiave full URL.

Brand Visibility fornisce questa chiave nella dimensione **URL CDN**. Combina l’host e il percorso richiesto in un unico URL completo normalizzato, in modo simile a come Customer Journey Analytics memorizza i dati web. La riuscita dell’unione dipende dalla tua raccolta di dati. Il set di dati dell’evento richiede un campo URL completo equivalente o un campo che puoi analizzare e normalizzare per corrispondere all’URL fornito da Brand Visibility. Quando entrambi i lati risolvono lo stesso URL completo, il record Visibilità dei brand corrisponde alla pagina corrispondente nei dati web.

Per ulteriori informazioni, consulta:

* [Configurare e configurare l’integrazione in entrata](/help/integrations/bv/configure.md)
* [Riferimento set di dati](/help/integrations/bv/reference.md)

## Integrazione in uscita

Per informazioni sull&#39;integrazione in uscita, fare riferimento a [Integrazione Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/brand-visibility/using/resources/customer-journey-analytics-integration){target="_blank"} nella documentazione di Adobe Brand Visibility.
