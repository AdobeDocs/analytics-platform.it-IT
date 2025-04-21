---
title: Panoramica di Content Analytics
description: Una panoramica di Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: feb253b20820112d5aa4b4eee31cff74d99fa186
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 44%

---

# Panoramica di Content Analytics

{{release-limited-testing}}

Content Analytics aiuta i marketer a comprendere in che modo i contenuti influiscono sugli indicatori di prestazioni chiave definiti da un’azienda. Oltre ai dati comportamentali, Content Analytics raccoglie dati sul modo in cui i contenuti vengono utilizzati e sul loro impatto sulle varie unità. Ad esempio, i clienti rispondono meglio a un tono di voce specifico, a una palette di colori specifica o a temi specifici? Queste informazioni, insieme a flussi di lavoro e modelli di reporting appositamente progettati, possono aiutarti a eseguire analisi ancora migliori e ottenere informazioni più approfondite sui dati del percorso della clientela in Customer Journey Analytics.

Content Analytics utilizza un **servizio di funzionalità** basato sull’IA e sul Machine learning per suddividere il contenuto in componenti e attributi. Creando un profilo di metadati strutturati su tutti i contenuti, puoi analizzare quali contenuti e quali attributi di tali contenuti determinano i risultati aziendali.

Oltre alla creazione di questo profilo di metadati strutturati, Content Analytics fornisce un **servizio Identity** che identifica risorse ed esperienze utilizzando un singolo identificatore. Il servizio Identity è in grado di riconoscere quando esattamente la stessa risorsa viene visualizzata in più posizioni. In questo caso, le istanze di questa risorsa vengono trattate come la stessa risorsa, consentendo una visualizzazione più olistica dell’utilizzo e del consumo dei contenuti.

## Valore

Content Analytics fornisce valore a un livello crescente:

1. **Utilizzo** del contenuto: con Content Analytics puoi ottenere informazioni sulle risorse che ricevono impression e sulle aree in cui le risorse ricevono impression. Queste informazioni ti aiutano a capire se le risorse sono sottoutilizzate o sovrautilizzate nelle proprietà web.
1. **Coinvolgimento** del contenuto: Content Analytics può fornire informazioni sul coinvolgimento come il tasso medio di click-through per le risorse con determinati attributi. Queste informazioni ti aiutano a determinare se tipi specifici di esperienze sono ancora efficaci.
1. **Percorsi** del contenuto: inoltre, in combinazione con tutti gli altri dati disponibili in Experience Platform, puoi ottenere ulteriori informazioni sui percorsi nei contenuti. Ad esempio, se un contenuto specifico porta a conversioni, oltre al coinvolgimento. E con questa conoscenza puoi determinare il ROI sui tipi di contenuto.
1. **Personalizzazione** del contenuto: in ultima analisi, Content Analytics ti consente di agire in base alle informazioni e di utilizzarle per determinare come spendere denaro per i contenuti. Ad esempio, devo inviare tipi specifici di contenuto a tipi di pubblico specifici? Quali contenuti mi offrono opportunità di personalizzazione elevate?

## Terminologia

Content Analytics utilizza i seguenti termini chiave:

![Risorse ed esperienze](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Esperienza**: un&#39;esperienza è tutto il testo in una pagina Web riproducibile utilizzando l&#39;URL utilizzato dall&#39;utente iniziale che ha visitato la pagina Web. A ogni esperienza viene assegnato un identificatore univoco. Le modifiche apportate alla pagina, che comportano modifiche al HTML della pagina, generano una nuova esperienza.
* **Risorsa**: una risorsa è un contenuto singolo e univoco, come un’immagine. A ogni risorsa viene inoltre assegnato un identificatore univoco e un ID percettivo. Un ID percettivo è un identificatore condiviso con risorse visivamente identiche. Gli ID percettivi aiutano a deduplicare le risorse che possono avere un URL risorsa diverso e quindi un ID risorsa diverso, ma che sono percepitamente identici.
* **Attributo**: un attributo è un elemento di metadati descrittivo associato a un’esperienza o a una risorsa. Gli esempi di un attributo sono: stile della fotografia, leggibilità, strategia di persuasione, colore dell’oggetto, colore di sfondo.

## Come funziona

Content Analytics utilizza i dati di visualizzazione dell&#39;immagine Web nei set di dati evento in Experience Platform per [raccogliere i dati dell&#39;evento contenuto](config/datacollection.md). E combina tale raccolta di dati sui contenuti con l’implementazione di raccolta dati (esistente) dei dati comportamentali.

![Content Analytics: come funziona](assets/aca-overview.gif)

1. Quando un utente visita un sito, [configurato per Content Analytics](config/configuration.md), Experience Platform Web SDK registra le impression e le interazioni con il contenuto.
1. Il servizio Identity e Feature elabora queste interazioni. Tale processo consiste in un servizio di recupero che rivede le versioni pubbliche degli URL configurati che definiscono le interazioni. Per tutti questi URL recuperati, il servizio Identity identifica in modo univoco le esperienze e le risorse. Inoltre, il servizio di funzionalità applica i servizi AI/ML per individuare esperienze, risorse, metadati e attributi.
1. I risultati di questi servizi ([componenti, attributi e identità](/help/content-analytics/report/components.md)) vengono utilizzati per aggiornare i set di dati di analisi del contenuto pertinenti in Experience Platform.
1. I dati di analisi dei contenuti, insieme ai dati comportamentali e ad altri dati di ricerca, possono essere utilizzati in una configurazione di Customer Journey Analytics ([Connessione](/help/connections/overview.md), [Visualizzazione dati](/help/data-views/data-views.md) e [Workspace](/help/analysis-workspace/home.md)). Tale configurazione fornisce le basi per ottenere informazioni esclusive a livello di macro sul contenuto. <br/>Puoi avviare i tuoi report e l&#39;analisi di Content Analytics utilizzando [il modello Content Analytics](/help/content-analytics/report/report.md#template).


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

>[!NOTE]
>
>Content Analytics [invia eventi aggiuntivi](config/datacollection.md#content-analytics-event) che probabilmente influiscono su qualsiasi definizione di percentuale di mancato recapito basata sul numero di eventi in una sessione o in una pagina.
>

>[!MORELIKETHIS]
>
>[Reporting di Content Analytics](report/report.md)
>[Configurare Content Analytics](config/configuration.md)
>[Calcolo dei mancati recapiti e della frequenza di rimbalzo in Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446#M454)
>

