---
title: Raccolta dati di Content Analytics
description: Panoramica della raccolta dei dati in Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: 89f7d8b388ab8c742712d748813520a51c736003
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 0%

---

# Raccolta dati di Content Analytics

{{release-limited-testing}}

Questo articolo spiega in dettaglio come Content Analytics raccoglie i dati


## Definizioni

Nel contesto del presente articolo si utilizzano le seguenti definizioni:

* **Esperienza**: per esperienza si intende il contenuto di testo di un&#39;intera pagina Web. Per la raccolta dati, Content Analytics registra l’Experience ID basato sull’URL della pagina. Successivamente, il testo sulla pagina viene acquisito tramite il servizio di recupero.
* **Experience ID**: combinazione univoca di URL rilevanti (URL di base più eventuali parametri che determinano il contenuto della pagina) e [experience version](manual.md#versioning).
   * Specifica, come parte della [configurazione](configuration.md), quali parametri sono rilevanti per ogni URL completo specificato.
   * È possibile definire l&#39;[identificatore di versione](manual.md#versioning) utilizzato.
* **Risorsa**: immagine. Content Analytics registra l’URL della risorsa.
* **ID risorsa**: URL della risorsa.
* **URL rilevante**: l&#39;URL di base più eventuali parametri che determinano il contenuto della pagina.


## Funzionalità

La libreria Content Analytics raccoglie dati quando:

* Content Analytics è incluso nella libreria Tag caricata sulla pagina.
* L&#39;URL della pagina è configurato nell&#39;estensione [Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, parte della libreria Tag inclusa.


## Evento Content Analytics

Un evento Content Analytics è costituito da:

* Campi standard
   * Marca temporale
   * Identità
* Visualizzazioni esperienza (se presenti e se configurate)
* Clic sull’esperienza (se presenti e se configurati)
* Visualizzazioni risorse (se presenti e se configurate)
* Clic su risorsa (se presenti e se configurati)


Gli eventi Content Analytics vengono raccolti come sequenza di:

1. [Visualizzazione registrata o clic](#recorded-view-or-click).
1. [Un evento regolare o specifico (comportamentale)](#regular-or-specific-behaviorial-event).

Content Analytics raccoglie i dati in questo modo per riflettere tale sequenza, invece di raccogliere una visualizzazione o fare clic separatamente dalla raccolta dell’evento immediatamente successivo alla visualizzazione o fare clic su. Questo modo di raccogliere i dati di analisi dei contenuti riduce anche la quantità di dati raccolti. raccolta di dati.

### Visualizzazione registrata o clic su

Viene registrata una visualizzazione delle risorse quando:

* La risorsa non è stata esclusa in base alla configurazione dell&#39;estensione Content Analytics.
* La risorsa è visualizzata al 75%.
* La risorsa non è già stata registrata per questa pagina.

Un clic su risorsa viene registrato quando:

* La risorsa è stata visualizzata.
* La risorsa non è stata esclusa in base alla configurazione dell&#39;estensione ACA.
* Un clic direttamente sulla risorsa, che è un collegamento, porta a un’altra pagina.

Viene registrata una visualizzazione dell’esperienza quando:

* Le esperienze sono abilitate nella configurazione Content Analytics.

Un clic sull&#39;esperienza viene registrato quando:

* Qualsiasi clic si verifica su un collegamento nella pagina per il quale sono abilitate le esperienze.


### Evento regolare o specifico (comportamentale)

Gli attivatori per attivare un evento regolare o specifico (comportamentale) nel contesto di Content Analytics sono:

* Web SDK o AppMeasurement invia un evento.
* La visibilità diventa nascosta, ad esempio:
   * Download delle pagine
   * Cambia scheda
   * Riduci a icona browser
   * Chiudi browser
   * Schermata di blocco
* L’URL viene modificato e diventa un URL rilevante modificato.
* Le visualizzazioni di una risorsa superano il limite batch di 32.


## Schemi

I dati di Content Analytics vengono raccolti in set di dati in Experience Platform, in base a schemi Content Analytics specifici. Gli schemi di riferimento sono disponibili al pubblico:

* [Schema risorse digitali](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Schema esperienza digitale](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Schema contenuto evento esperienza](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
