---
title: Panoramica di Content Analytics
description: Panoramica di Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
hidefromtoc: true
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 501a9fbd7c8abd8a63348c2c8d11b88b31a0f6df
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 0%

---

# Panoramica di Content Analytics

<!-- 
This is a placeholder article for upcoming Content Analytics documentation. Currently used to set up contextual help entries for developer working on onboarding UI and workspace UI 
-->

>[!WARNING]
>
>Questo articolo è una bozza preliminare non ufficiale di una versione finale di prossima pubblicazione e fa parte della documentazione di Content Analytics. Tutti i contenuti sono soggetti a modifiche e nessun obbligo legale può essere derivato dalla versione corrente di questo articolo.
>

{#release-limited-testing}

L’analisi dei contenuti aiuta gli addetti al marketing a comprendere in che modo i contenuti influiscono sugli indicatori prestazioni chiave definiti da un’azienda. Oltre alle tradizionali funzionalità basate su microlivello per testare parti di contenuto (ad esempio, test A/B), Content Analytics fornisce approfondimenti sul modo in cui il contenuto sta determinando l’impatto a livello macro. Ad esempio, i clienti rispondono meglio a un tono di voce specifico, a una paletta di colori specifica o a temi specifici?

L&#39;analisi dei contenuti utilizza un servizio di funzionalità **basato su AI e apprendimento automatico** per suddividere il contenuto in componenti e attributi. Creando un profilo di metadati strutturato su tutti i contenuti, puoi analizzare quali contenuti e quali attributi di tali contenuti determinano i risultati aziendali.

Oltre alla creazione di questo profilo di metadati strutturato, Content Analytics fornisce un **servizio Identity** che identifica risorse ed esperienze utilizzando un singolo identificatore. Il servizio Identity controlla se una risorsa, ad esempio, è stata ridimensionata, ritagliata o salvata in un formato di file diverso. Il servizio assegna tutte le varianti di quella risorsa allo stesso identificatore singolo. Di conseguenza, il servizio Identity ti consente di aggregare le prestazioni di una risorsa in base ai suoi vari moduli e posizionamenti.

## Valore

L’analisi dei contenuti fornisce valore a un livello crescente:

1. Contenuto **utilizzo**: con Content Analytics puoi ottenere informazioni sulle risorse che ricevono impression e sulle aree in cui le risorse ricevono impression. Queste informazioni consentono di verificare se le risorse sono sottoutilizzate o sovrautilizzate nelle proprietà web.
1. Contenuto **accordi**: l&#39;analisi del contenuto può fornire informazioni sul coinvolgimento come il tasso medio di click-through per le risorse con determinati attributi. Queste informazioni consentono di determinare se tipi specifici di esperienze sono ancora efficaci.
1. Contenuto **percorsi**: inoltre, se combinato con tutti gli altri dati disponibili in Experience Platform, puoi ottenere ulteriori informazioni sui percorsi di contenuti. Ad esempio, se un contenuto specifico porta a conversioni, oltre al coinvolgimento. E con questa conoscenza è possibile determinare il ROI sui tipi di contenuto.
1. Contenuto **personalizzazione**: in ultima analisi, Content Analytics ti consente di agire in base alle tue informazioni e di utilizzarle per determinare come spendere denaro per i contenuti. Ad esempio, devo inviare tipi specifici di contenuto a tipi di pubblico specifici? Quali contenuti mi offrono opportunità di personalizzazione elevate?

## Terminologia

L’analisi dei contenuti utilizza i seguenti termini chiave:

![Assets ed esperienze](/help/content-analytics/assets//content-analytics-experience-asset.png)

* **Esperienza**: per esperienza si intende tutto il testo di una pagina Web riproducibile tramite l&#39;URL utilizzato dall&#39;utente iniziale che visita la pagina Web. A ogni esperienza viene assegnato un identificatore univoco.
* **Risorsa**: una risorsa è un contenuto singolo e univoco, come un&#39;immagine. A ogni risorsa viene inoltre assegnato un identificatore univoco.
* **Attributo**: un attributo è un elemento di metadati descrittivo associato a un&#39;esperienza o a una risorsa. Esempi di un attributo sono: stile della fotografia, leggibilità, strategia di persuasione, colore dell&#39;oggetto, colore di sfondo.

## Come funziona

Nell’Experience Platform di Content Analytics vengono utilizzati i dati di visualizzazione delle immagini web raccolti nei set di dati evento. Questi dati possono essere raccolti tramite i vari metodi disponibili: Experience Platform Edge Network (Web SDK, Server API) o il connettore di origine Analytics.

![Analisi dei contenuti - Come funziona](assets/how-it-works.png)


1. La parte di rilevamento del servizio di funzionalità viene attivata su qualsiasi nuova istantanea di dati in arrivo a un set di dati evento abilitato di Content Analytics.
1. Il servizio di rilevamento delle funzioni determina i dati di tale istantanea rilevanti per l’analisi dei contenuti e rivede l’esperienza e le risorse di queste visualizzazioni di immagini web.
1. Al momento della nuova visita, i dati di analisi dei contenuti specifici vengono raccolti tramite una configurazione appropriata dell’Edge Network Experience Platform Web SDK e dell’Experience Platform. I dati vengono quindi inviati a un set di dati di analisi dei contenuti dedicato e a set di dati di ricerca rilevanti.
1. Il servizio assemblatore di funzioni e il servizio Identity elaborano i dati rivisti.
1. I risultati di questi servizi (componenti, attributi e identità) vengono utilizzati per aggiornare i set di dati di analisi del contenuto pertinenti specifici in Experience Platform.
1. I dati di analisi dei contenuti, insieme ai dati comportamentali e ad altri set di dati di ricerca, possono quindi essere utilizzati in una configurazione di Customer Journey Analytics (Connessione, Visualizzazione dati e Workspace). Tale configurazione fornisce le basi per ottenere informazioni esclusive a livello di macro sul contenuto.

>[!MORELIKETHIS]
>
>[Generazione rapporti di Content Analytics](#report/report.md)
>[Configura analisi contenuto](config/configuration.md)
