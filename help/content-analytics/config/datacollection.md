---
title: Raccolta dati di Content Analytics
description: Panoramica su come vengono raccolti i dati in Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: ht
source-wordcount: '622'
ht-degree: 100%

---

# Raccolta dati di Content Analytics

Questo articolo spiega nei dettagli come Content Analytics raccoglie i dati

## Definizioni

Nel contesto del presente articolo sono utilizzate le definizioni seguenti:

* **Esperienza**: per esperienza si intende il contenuto di testo su un’intera pagina web. Per la raccolta dati, Content Analytics registra l’ID esperienza basato sull’URL della pagina. Successivamente, il testo sulla pagina viene acquisito tramite il servizio di recupero.
* **ID esperienza**: una combinazione univoca dell’URL pertinente (URL di base più eventuali parametri che determinano il contenuto della pagina) e la [versione dell’esperienza](manual.md#versioning).
   * Specifica, come parte della [configurazione](configuration.md), quali parametri sono rilevanti per ogni URL completo specificato.
   * Puoi definire un [identificatore di versione](manual.md#versioning) da utilizzare, in modo da raccogliere correttamente le modifiche apportate alle esperienze.
* **Risorsa**: un’immagine. Content Analytics registra l’URL della risorsa.
* **ID risorsa**: l’URL della risorsa.
* **URL pertinente**: l’URL di base più eventuali parametri che determinano il contenuto della pagina.


## Funzionalità

Content Analytics richiede la rete Edge Web SDK di Experience Platform per raccogliere i dati evento relativi ai contenuti. Tale raccolta di dati evento è combinata con la raccolta di dati evento comportamentali (esistenti) tramite meccanismi come la rete Edge di Experience Platform (Web SDK, server API) o il connettore di origine di Analytics (ad esempio, utilizzando AppMeasurement).

La libreria Content Analytics raccoglie dati quando:

* Content Analytics è incluso nella libreria Tag caricata sulla pagina.
* L’URL della pagina è configurato nell’[estensione Content Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, che fa parte della libreria Tag inclusa.


## Evento di Content Analytics

Un evento di Content Analytics è costituito da:

* Campi standard
   * Marca temporale
   * Identità
* Visualizzazioni esperienza (se presenti e se configurate)
* Clic sull’esperienza (se presenti e se configurati)
* Visualizzazioni risorse (se presenti e se configurate)
* Clic sulla risorsa (se presenti e se configurati)

Gli eventi di Content Analytics vengono raccolti come sequenza di:

1. [Una visualizzazione o un clic registrato](#recorded-view-or-click).
1. [Un trigger per inviare un evento di Content Analytics](#trigger-to-send-a-content-analytics-event).

Content Analytics raccoglie i dati in questo modo per riflettere tale sequenza, invece di raccogliere visualizzazioni o clic separatamente rispetto alla raccolta dell’evento immediatamente successivo alla visualizzazione o clic. Questo modo di raccogliere i dati di Content Analytics riduce anche la quantità di dati raccolti.

### Visualizzazione o clic registrato

Una visualizzazione della risorsa viene registrata quando:

* La risorsa non è stata esclusa in base alla configurazione dell’estensione Content Analytics.
* La risorsa è visualizzata al 75%.
* La risorsa non è già stata registrata per questa pagina.

Un clic sulla risorsa viene registrato quando:

* La risorsa è stata visualizzata.
* La risorsa non è stata esclusa in base alla configurazione dell’estensione Content Analytics.
* Viene fatto clic direttamente sulla risorsa, che è un collegamento che porta a un’altra pagina.

Una visualizzazione dell’esperienza viene visualizzata quando:

* Le esperienze sono abilitate nella configurazione di Content Analytics.

Un clic sull’esperienza viene registrato quando:

* Qualsiasi clic si verifica su un collegamento nella pagina per il quale sono abilitate le esperienze.


### Trigger per inviare un evento Content Analytics

Per ridurre il numero di chiamate che lasciano la pagina, Content Analytics raccoglie le informazioni ma non le invia immediatamente. Le informazioni relative all’interazione con i contenuti vengono raccolte e un evento contenente tali informazioni viene inviato solo quando si verifica uno dei seguenti trigger:

* Web SDK o AppMeasurement invia un evento.
* La visibilità viene cambiata in nascosta, ad esempio:
   * Scaricamenti della pagina
   * Passaggio a un’altra scheda
   * Riduzione a icona del browser
   * Chiusura del browser
   * Blocco dello schermo
* Cambio dell’URL che determina la modifica dell’URL pertinente.
* Le visualizzazioni delle risorse registrate e pronte per l’invio sono superiori al numero di 32.

>[!NOTE]
>
>Gli eventi aggiuntivi di Content Analytics probabilmente influiscono su qualsiasi definizione di tasso di mancato recapito basata sul numero di eventi in una sessione o in una pagina.
>


## Schemi

I dati di Content Analytics vengono raccolti in set di dati in Experience Platform, in base a schemi specifici di Content Analytics. Gli schemi di riferimento sono disponibili pubblicamente:

* [Schema risorsa digitale](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Schema esperienza digitale](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Schema contenuto dell’evento esperienza](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
