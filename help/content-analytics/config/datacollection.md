---
title: Raccolta dati di Content Analytics
description: Panoramica su come vengono raccolti i dati in Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: a593221a9eb81d747777aedb323fd44a32c470be
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 47%

---

# Raccolta dati di Content Analytics

Questo articolo spiega nei dettagli come Content Analytics raccoglie i dati

## Definizioni

Nel contesto del presente articolo sono utilizzate le definizioni seguenti:

* **Esperienza**:
   * Per il canale **web**, per esperienza si intende il contenuto di testo di un&#39;intera pagina Web. Per la raccolta dati, Content Analytics registra l’Experience ID che si basa sull’URL della pagina. Successivamente, il testo sulla pagina viene acquisito tramite il servizio di recupero.
   * Per il canale **mobile**, viene definita e tracciata un&#39;esperienza nell&#39;app mobile tramite l&#39;estensione Content Analytics per Adobe Experience Platform Mobile SDK.
* **ID esperienza**:
   * Per il canale web, l&#39;ID esperienza è una combinazione univoca di URL rilevanti (URL di base più eventuali parametri che determinano il contenuto della pagina) e [versione esperienza](manual.md#versioning).
      * Specifica, come parte della [configurazione](configuration.md), quali parametri sono rilevanti per ogni URL completo specificato.
      * Puoi definire un [identificatore di versione](manual.md#versioning) da utilizzare, in modo da raccogliere correttamente le modifiche apportate alle esperienze.
   * Per il canale **mobile**, l&#39;ID esperienza è il valore restituito dall&#39;utilizzo della chiamata API `registerExperience`.
* **Risorsa**: un’immagine. Content Analytics registra l’URL della risorsa.
* **ID risorsa**: l’URL della risorsa.
* **URL pertinente**: l’URL di base più eventuali parametri che determinano il contenuto della pagina.


## Funzionalità

Content Analytics richiede Experience Platform Edge Network Web SDK (per il canale web) e Experience Platform Edge Network Mobile SDK (per il canale mobile) per raccogliere i dati dell’evento contenuto. Questi dati evento vengono combinati con i dati comportamentali esistenti utilizzando Experience Platform Edge Network (Web SDK, Mobile SDK o Server API) o un connettore di origine Analytics, come Adobe AppMeasurement.

La libreria Content Analytics raccoglie dati quando:

* Content Analytics è incluso nella libreria Tag caricata nella pagina o utilizzata all’interno dell’app mobile.
* L&#39;URL della pagina e l&#39;URL della risorsa sono configurati nell&#39;[estensione Web Content Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, parte della libreria Tag inclusa.
* L&#39;URL della risorsa, il percorso della risorsa o il percorso dell&#39;esperienza non sono esclusi nell&#39;estensione [Content Analytics mobile](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/).


## Evento di Content Analytics

Questa sezione descrive le specifiche per gli eventi Web Content Analytics. Consulta [Tracciamento dell&#39;esperienza](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/experience-tracking/) per informazioni dettagliate sugli eventi di Mobile Content Analytics.
Un evento di Content Analytics è costituito da:

* Campi standard
   * Marca temporale
   * Identità
* Visualizzazioni esperienza (se presenti e se configurate)
* Clic sull’esperienza (se presenti e se configurati)
* Visualizzazioni risorse (se presenti e se configurate)
* Clic sulla risorsa (se presenti e se configurati)

Gli eventi di Content Analytics vengono raccolti come sequenza di:

1. [visualizzazione registrata o clic](#recorded-view-or-click).
1. Un [trigger per inviare un evento Content Analytics](#trigger-to-send-a-content-analytics-event).

Content Analytics raccoglie i dati in questo modo per riflettere tale sequenza, invece di raccogliere visualizzazioni o clic separatamente rispetto alla raccolta dell’evento immediatamente successivo alla visualizzazione o clic. Questo modo di raccogliere i dati di Content Analytics riduce anche la quantità di dati raccolti.

### Visualizzazione o clic registrato

Una visualizzazione della risorsa viene registrata quando:

* La risorsa non è stata esclusa in base alla configurazione dell’estensione Content Analytics.
* La risorsa è visualizzata al 75%.
* La risorsa non è già stata registrata per questa pagina.

Un clic sulla risorsa viene registrato quando:

* La risorsa è stata visualizzata.
* La risorsa non è stata esclusa in base alla configurazione dell’estensione Content Analytics.
* Un clic diretto sulla risorsa, che è un collegamento, porta a un’altra pagina.

Una visualizzazione dell’esperienza viene visualizzata quando:

* Le esperienze sono abilitate nella configurazione di Content Analytics.

Un clic sull’esperienza viene registrato quando:

* Qualsiasi clic su un collegamento abilitato attiva un’esperienza.


### Trigger per inviare un evento Content Analytics

Per ridurre il numero di richieste di rete inviate dalla pagina, Content Analytics raccoglie le informazioni ma non le invia immediatamente. Le informazioni relative all’interazione con i contenuti vengono raccolte e un evento contenente tali informazioni viene inviato solo quando si verifica uno dei seguenti trigger:

* Web SDK o Adobe AppMeasurement inviano un evento.
* La visibilità viene cambiata in nascosta, ad esempio:
   * Scaricamenti della pagina
   * Passaggio a un’altra scheda
   * Riduzione a icona del browser
   * Chiusura del browser
   * Blocco dello schermo
* Cambio dell’URL che determina la modifica dell’URL pertinente.
* Le visualizzazioni delle risorse registrate e pronte per l’invio superano 32.

>[!NOTE]
>
>Gli eventi aggiuntivi di Content Analytics probabilmente influiscono su qualsiasi definizione di tasso di mancato recapito basata sul numero di eventi in una sessione o in una pagina.
>

## Identità

Questa sezione spiega come Content Analytics gestisce le identità.

### Web

Content Analytics gestisce le identità per il canale web nel modo seguente:

* ECID viene popolato automaticamente nella porzione `identityMap` dello schema Content Analytics.
* Se sono necessari altri valori di identità in `identityMap`, è necessario impostare questi valori nel callback `onBeforeEventSend` all’interno dell’estensione Web SDK.
* L’unione identità basata sui campi non è supportata perché lo schema è di proprietà del sistema. Pertanto, non è possibile aggiungere un altro campo allo schema per supportare l’unione identità basata sui campi


Per garantire che i dati di identità di Content Analytics e i dati di identità di SDK Web siano uniti correttamente a livello di campo, modificare il callback [su Web SDK prima dell&#39;invio dell&#39;evento](https://experienceleague.adobe.com/it/docs/experience-platform/collection/js/commands/configure/onbeforeeventsend){target="_blank"}.

1. Passa alla proprietà **[!UICONTROL Tags]** contenente l&#39;estensione Adobe Experience Platform Web SDK e l&#39;estensione Adobe Content Analytics.
1. Seleziona ![Plug](/help/assets/icons/Plug.svg) **[!UICONTROL Estensioni]**.
1. Selezionare l&#39;estensione **[!UICONTROL Adobe Experience Platform Web SDK]**.
1. Seleziona **[!UICONTROL Configura]**.
1. Nella sezione **[!UICONTROL Istanze di SDK]**, scorri verso il basso fino a **[!UICONTROL Raccolta dati]** - **[!UICONTROL Attiva prima del callback di invio dell&#39;evento]**.

   ![Callback prima dell’invio dell’evento](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Selezionare **[!UICONTROL &lt;/> Fornisci il prima del codice callback di invio evento]**.
1. Aggiungi il seguente codice:

   ```JavaScript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![Callback prima dell’invio dell’evento](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Seleziona **[!UICONTROL Salva]** per salvare il codice.
1. Seleziona **[!UICONTROL Salva]** per salvare l&#39;estensione.
1. [Pubblica](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview) gli aggiornamenti per la proprietà Tag.


### Mobile

Per ulteriori informazioni su come utilizzare le identità nell&#39;app mobile, consulta l&#39;estensione [Identità per il servizio Experience Cloud ID](https://developer.adobe.com/client-sdks/home/base/mobile-core/identity/) e l&#39;estensione [Identità per Edge Network mobile](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/).

Non appena l&#39;identità cambia nell&#39;app mobile, il [batch](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/#batching-settings) corrente dei dati di Content Analytics viene reimpostato per avviare una nuova raccolta di dati di Content Analytics per la nuova identità.

## Schemi

Experience Platform raccoglie i dati di Content Analytics in set di dati basati su schemi Content Analytics specifici. Gli schemi di riferimento sono disponibili pubblicamente:

* [Schema risorsa digitale](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Schema esperienza digitale](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Schema contenuto evento esperienza](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
