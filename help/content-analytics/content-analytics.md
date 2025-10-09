---
title: Panoramica di Content Analytics
description: Una panoramica di Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: ht
source-wordcount: '835'
ht-degree: 100%

---

# Panoramica di Content Analytics

Content Analytics aiuta i marketer a comprendere in che modo i contenuti influiscono sugli indicatori di prestazioni chiave definiti da un’azienda. Oltre ai dati comportamentali, Content Analytics raccoglie i dati sul modo in cui il contenuto viene utilizzato e su come genera un impatto. Ad esempio, la clientela reagisce meglio a un tono di voce specifico, a una paletta di colori specifica o a temi specifici? Queste informazioni, insieme a flussi di lavoro e modelli di reporting appositamente progettati, possono aiutarti a eseguire analisi ancora migliori e ottenere informazioni più approfondite sui dati del percorso della clientela in Customer Journey Analytics.

Content Analytics utilizza un **servizio di funzionalità** basato sull’IA e sul Machine learning per suddividere il contenuto in componenti e attributi. Creando un profilo di metadati strutturati su tutti i contenuti, puoi analizzare quali contenuti e quali attributi di tali contenuti determinano i risultati aziendali.

Oltre alla creazione di questo profilo di metadati strutturati, Content Analytics fornisce un **servizio Identity** che identifica risorse ed esperienze utilizzando un singolo identificatore. Il servizio Identity è in grado di riconoscere quando esattamente la stessa risorsa viene visualizzata in più posizioni. In questo caso, le due istanze di questa risorsa vengono trattate come se fossero la stessa risorsa, consentendo una visualizzazione più olistica dell’utilizzo e del consumo dei contenuti.

## Valore

Content Analytics fornisce valore a un livello crescente:

1. **Utilizzo** del contenuto: con Content Analytics puoi ottenere informazioni sulle risorse che ricevono impression e sulle aree in cui le risorse ricevono impression. Queste informazioni ti aiutano a capire se le risorse sono sottoutilizzate o sovrautilizzate nelle proprietà web.
1. **Coinvolgimento** del contenuto: Content Analytics può fornire informazioni sul coinvolgimento come il tasso medio di click-through per le risorse con determinati attributi. Queste informazioni ti aiutano a determinare se tipi specifici di esperienze sono ancora efficaci.
1. **Percorsi** del contenuto: inoltre, in combinazione con tutti gli altri dati disponibili in Experience Platform, puoi ottenere ulteriori informazioni sui percorsi nei contenuti. Ad esempio, se un contenuto specifico porta a conversioni, oltre al coinvolgimento. E con questa conoscenza puoi determinare il ROI sui tipi di contenuto.
1. **Personalizzazione** del contenuto: in ultima analisi, Content Analytics ti consente di agire in base alle informazioni e di utilizzarle per determinare come spendere denaro per i contenuti. Ad esempio, devo inviare tipi specifici di contenuto a tipi di pubblico specifici? Quali contenuti mi offrono opportunità di personalizzazione elevate?

## Terminologia

Content Analytics utilizza i seguenti termini chiave:

![Risorse ed esperienze](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Esperienza**: un’esperienza è tutto il testo di una pagina web riproducibile con l’URL utilizzato dall’utente iniziale che visita quella pagina web. A ogni esperienza viene assegnato un identificatore univoco. Le modifiche apportate alla pagina, che comportano modifiche al codice HTML della pagina, generano una nuova esperienza.
* **Risorsa**: una risorsa è un contenuto singolo e univoco, come ad esempio un’immagine. A ogni risorsa viene inoltre assegnato un identificatore univoco e un ID percettivo. Un ID percettivo è un identificatore condiviso con risorse visivamente identiche. Gli ID percettivi aiutano a deduplicare le risorse che possono avere un URL della risorsa diverso e quindi un diverso ID risorsa, ma che sono percettivamente identici.
* **Attributo**: un attributo è un elemento di metadati descrittivo associato a un’esperienza o a una risorsa. Gli esempi di un attributo sono: stile della fotografia, leggibilità, strategia di persuasione, colore dell’oggetto, colore di sfondo.

## Come funziona

Content Analytics utilizza i dati di visualizzazione dell’immagine web nei set di dati evento in Experience Platform per [raccogliere i dati dell’evento contenuto](config/datacollection.md). E combina tale raccolta di dati sui contenuti con l’implementazione della raccolta dati (esistente) dei dati comportamentali.

![Content Analytics: come funziona](assets/aca-overview.gif)

1. Quando un utente visita un sito, [configurato per Content Analytics](config/configuration.md), Experience Platform Web SDK registra le impression e le interazioni con il contenuto.
1. Il servizio di identità e funzionalità elabora queste interazioni. Tale processo consiste in un servizio di recupero che rivede le versioni pubbliche degli URL configurati che definiscono le interazioni. Per tutti questi URL recuperati, il servizio di identità identifica in modo univoco le esperienze e le risorse. Inoltre, il servizio di funzionalità applica i servizi IA/ML per individuare i metadati e gli attributi delle esperienze e delle risorse.
1. I risultati di questi servizi ([componenti, attributi e identità](/help/content-analytics/report/components.md)) vengono utilizzati per aggiornare i set di dati di Content Analytics specifici e pertinenti in Experience Platform.
1. I dati di Content Analytics, insieme ai dati comportamentali e ad altri dati di ricerca, possono essere utilizzati in una configurazione Customer Journey Analytics ([Connessione](/help/connections/overview.md), [Visualizzazione dati](/help/data-views/data-views.md) e [Workspace](/help/analysis-workspace/home.md)). Tale configurazione fornisce le basi per ottenere informazioni uniche a un livello macro sul contenuto. <br/>Puoi avviare i rapporti e l’analisi di Content Analytics utilizzando il [modello Content Analytics](/help/content-analytics/report/report.md#template).


>[!NOTE]
>
>Content Analytics sfrutta i servizi IA/ML che possono produrre risultati imprecisi o fuorvianti. Di conseguenza, utilizza il tuo giudizio per rivedere e convalidare gli output generati da IA/ML.
>
>Puoi utilizzare la scheda **[!UICONTROL Feedback]**, disponibile in ![InfoOutline](/help/assets/icons/InfoOutline.svg) nell’interfaccia principale, per fornire feedback sugli output generati da IA/ML.
>

>[!NOTE]
>
>Se disponi di una licenza per il componente aggiuntivo Privacy and Security Shield, tieni presente che (tutti i dati generati da) esperienze e risorse, soggette a Content Analytics, non sono rientrano nell’etichettatura DULE, né nelle chiavi gestite dal cliente. Inoltre, Content Analytics non è un servizio compatibile con HIPAA.
>


>[!MORELIKETHIS]
>
>[Reporting di Content Analytics](report/report.md)
>>[Configurare Content Analytics](config/configuration.md)
>>[Calcolo dei mancati recapiti e del tasso di mancato recapito in Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446#M454)
>

