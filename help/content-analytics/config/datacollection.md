---
title: Raccolta dati di Content Analytics
description: Panoramica della raccolta dei dati in Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
hide: true
hidefromtoc: true
role: Admin
source-git-commit: d835411beba3d40f67d2f93ee76aa5eda6f45041
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 1%

---


# Raccolta dati di Content Analytics

Questo articolo spiega in dettaglio come Content Analytics raccoglie i dati


## Definizioni

Nel contesto del presente articolo si utilizzano le seguenti definizioni:

* **Esperienza**: per esperienza si intende il contenuto di testo di un&#39;intera pagina Web. Per la raccolta dati, Content Analytics registra l’Experience ID. Content Analytics non registra il testo sulla pagina.
* **Risorsa**: immagine. Content Analytics registra l’URL della risorsa.
* **URL rilevante**: l&#39;URL di base più eventuali parametri che determinano il contenuto della pagina.
* **Experience ID**: combinazione univoca di URL rilevanti e versione esperienza.
   * Specifica, come parte della [configurazione](configuration.md), quali parametri sono rilevanti per ogni URL completo specificato.
   * È possibile definire l&#39;[identificatore di versione](manual.md#versioning) utilizzato. Per la raccolta dati, la versione non viene considerata. Viene raccolto solo l’URL rilevante.

## Funzionalità

La libreria Content Analytics raccoglie dati quando:

* Content Analytics è incluso nella libreria Tag caricata sulla pagina.
* L&#39;URL della pagina è configurato nell&#39;estensione [Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, parte della libreria Tag inclusa.


### Evento Content Analytics

Un evento Content Analytics è costituito da:

* Campi standard
   * Marca temporale
   * Identità
* Visualizzazioni esperienza (se presenti e se configurate)
* Clic sull’esperienza (se presenti e se configurati)
* Visualizzazioni risorse (se presenti e se configurate)
* Clic su risorsa (se presenti e se configurati)

#### Visualizzazioni o clic registrati

Viene registrata una visualizzazione delle risorse quando:

* La risorsa non è stata esclusa in base alla configurazione dell&#39;estensione ACA.
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


#### Eventi inviati

Gli eventi Content Analytics vengono inviati quando si verificano le due condizioni seguenti:

* Il contenuto viene inviato quando:

   * Viene registrata una visualizzazione o un clic su una risorsa.
   * Viene registrata una visualizzazione esperienza o un clic su.

* Viene attivato un trigger per l’invio di un evento, che si verifica quando:

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

I dati di Content Analytics vengono raccolti in set di dati in Experience Platform, in base a schemi Content Analytics specifici. Gli schemi di riferimento sono disponibili al pubblico e vengono utilizzati in un’implementazione predefinita di Content Analytics.

* [Schema risorse digitali](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Schema esperienza digitale](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Schema contenuto evento esperienza](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
