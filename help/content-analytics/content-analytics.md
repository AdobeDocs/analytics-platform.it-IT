---
title: Panoramica di Content Analytics
description: Panoramica di Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
hidefromtoc: true
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 62491fcbf37961d33be92d209e5710bf9696c223
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 0%

---

# Panoramica di Content Analytics

>[!WARNING]
>
>Questo articolo è una bozza preliminare non ufficiale di una versione finale di prossima pubblicazione e fa parte della documentazione di Content Analytics. Tutti i contenuti sono soggetti a modifiche e nessun obbligo legale può essere derivato dalla versione corrente di questo articolo.
>

{{release-limited-testing}}

L’analisi dei contenuti aiuta gli addetti al marketing a comprendere in che modo i contenuti influiscono sugli indicatori prestazioni chiave definiti da un’azienda. Oltre ai dati comportamentali, Content Analytics raccoglie dati sul modo in cui i contenuti vengono utilizzati e sul loro impatto sulle varie unità. Ad esempio, i clienti rispondono meglio a un tono di voce specifico, a una paletta di colori specifica o a temi specifici? Queste informazioni, insieme a flussi di lavoro e modelli di reporting appositamente progettati, possono aiutarti a eseguire analisi ancora migliori e ottenere informazioni più approfondite sui dati del percorso dei clienti in Customer Journey Analytics.

L&#39;analisi dei contenuti utilizza un servizio di funzionalità **basato su AI e apprendimento automatico** per suddividere il contenuto in componenti e attributi. Creando un profilo di metadati strutturato su tutti i contenuti, puoi analizzare quali contenuti e quali attributi di tali contenuti determinano i risultati aziendali.

Oltre alla creazione di questo profilo di metadati strutturato, Content Analytics fornisce un **servizio Identity** che identifica le risorse e le esperienze utilizzando un singolo identificatore. Il servizio Identity è in grado di riconoscere quando la stessa risorsa viene visualizzata in più posizioni. In questo caso, le due istanze di risorse vengono trattate come se fossero le stesse, consentendo una visualizzazione più olistica dell’utilizzo e del consumo dei contenuti.

## Valore

L’analisi dei contenuti fornisce valore a un livello crescente:

1. Contenuto **utilizzo**: con Content Analytics puoi ottenere informazioni sulle risorse che ricevono impression e sulle aree in cui le risorse ricevono impression. Queste informazioni consentono di verificare se le risorse sono sottoutilizzate o sovrautilizzate nelle proprietà web.
1. Contenuto **accordi**: l&#39;analisi del contenuto può fornire informazioni sul coinvolgimento come il tasso medio di click-through per le risorse con determinati attributi. Queste informazioni consentono di determinare se tipi specifici di esperienze sono ancora efficaci.
1. Contenuto **percorsi**: in combinazione con tutti gli altri dati disponibili in Experience Platform, puoi ottenere ulteriori informazioni sui percorsi di contenuti. Ad esempio, se un contenuto specifico porta a conversioni, oltre al coinvolgimento. E con questa conoscenza è possibile determinare il ROI sui tipi di contenuto.
1. Contenuto **personalizzazione**: in ultima analisi, Content Analytics ti consente di agire in base alle tue informazioni e di utilizzarle per determinare come spendere denaro per i contenuti. Ad esempio, devo inviare tipi specifici di contenuto a tipi di pubblico specifici? Quali contenuti mi offrono opportunità di personalizzazione elevate?

## Terminologia

Content Analytics utilizza i seguenti termini chiave:

![Assets ed esperienze](/help/content-analytics/assets//content-analytics-experience-asset.png)

* **Esperienza**: per esperienza si intende tutto il testo di una pagina Web riproducibile tramite l&#39;URL utilizzato dall&#39;utente iniziale che visita la pagina Web. A ogni esperienza viene assegnato un identificatore univoco.
* **Risorsa**: una risorsa è un contenuto singolo e univoco, come un&#39;immagine. A ogni risorsa viene inoltre assegnato un identificatore univoco.
* **Attributo**: un attributo è un elemento di metadati descrittivo associato a un&#39;esperienza o a una risorsa. Esempi di un attributo sono: stile della fotografia, leggibilità, strategia di persuasione, colore dell&#39;oggetto, colore di sfondo.

## Come funziona

Content Analytics utilizza i dati di visualizzazione delle immagini web raccolti nei set di dati evento in Experience Platform. Questi dati possono essere raccolti tramite i vari metodi disponibili: Experience Platform Edge Network (Web SDK, Server API) o il connettore di origine Analytics.

![Analisi dei contenuti - Come funziona](assets/aca-overview.gif)


1. Quando un utente visita un sito configurato per Content Analytics, Experience Platform Web SDK registra le interazioni con il contenuto.
1. Il servizio assemblatore di funzioni e il servizio Identity elaborano i dati rivisti. Tale processo consiste in un crawler che rivede le versioni pubbliche degli URL configurati e applica i servizi AI/ML.
1. I risultati di questi servizi (componenti, attributi e identità) vengono utilizzati per aggiornare i set di dati di analisi del contenuto pertinenti in Experience Platform.
1. I dati di analisi dei contenuti, insieme ai dati comportamentali e ad altri set di dati di ricerca, vengono utilizzati nella configurazione di Customer Journey Analytics (combinazione di Connessione, Visualizzazione dati e Workspace). Tale configurazione fornisce le basi per ottenere informazioni esclusive a livello di macro sul contenuto.

>[!NOTE]
>
>Content Analytics sfrutta i servizi AI/ML che possono produrre risultati imprecisi o fuorvianti. Di conseguenza, utilizza il tuo giudizio per rivedere e convalidare gli output generati da IA/ML.
>
>Puoi utilizzare la scheda **[!UICONTROL Feedback]**, disponibile in ![InfoOutline](/help/assets/icons/InfoOutline.svg) nell&#39;interfaccia principale, per fornire feedback sugli output generati da IA/ML.
>

>[!NOTE]
>
>Se hai concesso la licenza per il componente aggiuntivo Privacy and Security Shield, tieni presente che (tutti i dati generati da) esperienze e risorse, soggette a Content Analytics, non sono coperti dall’etichettatura DULE o dalle chiavi gestite dal cliente.
>


>[!MORELIKETHIS]
>
>[Generazione rapporti di Content Analytics](report/report.md)
>[Configura analisi contenuto](config/configuration.md)
>