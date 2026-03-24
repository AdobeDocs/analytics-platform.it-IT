---
title: Mappare le colonne del feed dati di Adobe Analytics su Customer Journey Analytics
description: Determina come utilizzare una determinata colonna di feed dati di Adobe Analytics e determinane l’equivalente approssimativo nell’implementazione di Customer Journey Analytics.
feature: Components
hide: true
hidefromtoc: true
exl-id: 81d6e79e-8324-4726-9a48-10177b0a91b1
source-git-commit: b0be8b726c4fab1bf9bb5f9462be84f39bdf184a
workflow-type: tm+mt
source-wordcount: '3768'
ht-degree: 34%

---

# Mappare le colonne del feed dati di Adobe Analytics su Customer Journey Analytics

Non è possibile eseguire una mappatura true 1:1 tra le colonne dei feed dati di Adobe Analytics e Customer Journey Analytics. I due prodotti sono sostanzialmente diversi e l&#39;implementazione di ogni organizzazione può variare in modo significativo.

Questo riferimento consente ai data engineer di valutare le colonne dei feed dati di Adobe Analytics e identificare gli equivalenti Customer Journey Analytics più simili per i loro flussi di lavoro.

>[!NOTE]
>
>Questo riferimento include solo le colonne considerate correnti da Adobe, in base al [Riferimento colonna feed dati di Analytics](https://experienceleague.adobe.com/it/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference). Se disponi di una colonna di feed dati di Analytics non elencata in questa tabella che utilizzi attivamente, consulta il documento di progettazione della soluzione della tua organizzazione per determinarne l’equivalente migliore in Customer Journey Analytics.

+++**`accept_language`**

Elenca tutte le lingue accettate, come indicato nell’intestazione HTTP Accetta-Lingua in una richiesta di immagine.

+++

+++**`adload`**

Caricamenti di annunci multimediali

{{cja-df-post}}

+++

+++**`aemassetid`**

Variabile multivalore corrispondente agli ID risorsa (GUID) di un set di Adobe Experience Manager Assets. Incrementa gli eventi di impression.

{{cja-df-post}}

+++

+++**`aemassetsource`**

Identifica l’origine dell’evento risorsa. Utilizzato in Adobe Experience Manager.

{{cja-df-post}}
+++

+++**`aemclickedassetid`**

ID risorsa di una risorsa di Adobe Experience Manager. Incrementa gli eventi di clic.

{{cja-df-post}}

+++

+++**`amo_cid`**

La dimensione AMO ID, utilizzata nelle integrazioni Adobe Advertising.

{{cja-df-post}}

+++

+++**`amo_ef_id`**

La dimensione AMO EF ID, utilizzata nelle integrazioni Adobe Advertising.

{{cja-df-post}}

+++

+++**`browser`**

ID numerico che rappresenta il browser.

{{cja-df-lookup}}

+++

+++**`browser_height`**

La dimensione Altezza browser.

{{cja-df-post}}

+++

+++**`browser_width`**

Larghezza browser

{{cja-df-post}}

+++

+++**`campaign`**

La dimensione Codice di tracciamento.

{{cja-df-post}}

+++

+++**`carrier`**

Specifica il gestore di telefonia mobile.

{{cja-df-lookup}}

{{cja-df-ua}}

+++

+++**`channel`**

La dimensione Sezioni del sito.

{{cja-df-post}}

+++

+++**`ch_hdr`**

Hint client raccolti tramite l’intestazione della richiesta HTTP.

In Adobe Analytics, gli hint client venivano inclusi come stringa concatenata in questa colonna. È considerato un approccio più moderno rispetto alla colonna `user_agent`.

{{cja-df-ua}}

+++

+++**`ch_js`**

Hint client raccolti tramite l’API JavaScript per gli hint client dall’agente utente

In Adobe Analytics, gli hint client venivano inclusi come stringa concatenata in questa colonna. È considerato un approccio più moderno rispetto alla colonna `user_agent`.

È possibile raccogliere questi dati utilizzando la stringa di contesto [`highEntropyUserAgentHints`](https://experienceleague.adobe.com/it/docs/experience-platform/collection/js/commands/configure/context) durante la configurazione del Web SDK. Vengono compilati più campi XDM invece di una stringa lunga concatenata:

* **Versione sistema operativo**: `xdm.environment.browserDetails.userAgentClientHints.platformVersion`
* **Architettura**: `xdm.environment.browserDetails.userAgentClientHints.architecture`
* **Modello dispositivo**: `xdm.environment.browserDetails.userAgentClientHints.model`
* **Bitness**: `xdm.environment.browserDetails.userAgentClientHints.bitness`
* **Fornitore browser**: `xdm.environment.browserDetails.userAgentClientHints.vendor`
* **Nome browser**: `xdm.environment.browserDetails.userAgentClientHints.brand`
* **Versione browser**: `xdm.environment.browserDetails.userAgentClientHints.version`

Per ulteriori informazioni, vedere [User agent client hints](https://experienceleague.adobe.com/it/docs/experience-platform/collection/use-cases/client-hints).

{{cja-df-ua}}

+++

+++**`clickmaplink`**

La dimensione Collegamento di Activity Map.

{{cja-df-post}}

{{cja-df-na}}

Questa colonna non è applicabile perché Customer Journey Analytics non supporta ancora Activity Map.

+++

+++**`clickmaplinkbyregion`**

La dimensione Collegamento Activity Map per area geografica.

{{cja-df-post}}

{{cja-df-na}}

Questa colonna non è applicabile perché Customer Journey Analytics non supporta ancora Activity Map.

+++

+++**`clickmappage`**

La dimensione pagina di Activity Map.

{{cja-df-post}}

{{cja-df-na}}

Questa colonna non è applicabile perché Customer Journey Analytics non supporta ancora Activity Map.

+++

+++**`clickmapregion`**

La dimensione dell’area geografica Activity Map.

{{cja-df-post}}

{{cja-df-na}}

Questa colonna non è applicabile perché Customer Journey Analytics non supporta ancora Activity Map.

+++

+++**`code_ver`**

Versione API o SDK client utilizzata per compilare e inviare la richiesta di immagine.

+++

+++**`color`**

ID di profondità colore in base al valore della colonna `c_color`.

{{cja-df-lookup}}

+++

+++**`connection_type`**

ID numerico che rappresenta la dimensione Tipo di connessione.

{{cja-df-lookup}}

+++

+++**`cookies`**

La dimensione Supporto cookie.<br>Y: abilitato<br>N: disabilitato<br>U: sconosciuto

{{cja-df-post}}

+++

+++**`country`**

Un ID numerico che rappresenta il paese del visitatore. Fa riferimento alla tabella di ricerca `country.tsv`.

{{cja-df-lookup}}

+++

+++**`currency`**

Codice valuta utilizzato durante la transazione. Impostato con `currencyCode`.

`xdm.commerce.order.currencyCode`

{{cja-df-post}}

+++

+++**`ct_connect_type`**

Correlato alla colonna `connection_type`. I valori più comuni sono LAN/Wi-Fi, Gestore di telefonia mobile e Modem.

+++

+++**`curr_factor`**

Determina la posizione decimale della valuta. Utilizzato per la conversione di valuta. Ad esempio, USD utilizza due posizioni decimali, quindi il valore di questa colonna sarebbe `2`.

+++

+++**`curr_rate`**

Il tasso di cambio al momento della transazione. Adobe si appoggia a XE per determinare il tasso di cambio del giorno corrente.

+++

+++**`customer_perspective`**

Determina se l’hit è un hit di sfondo per dispositivi mobili.

{{cja-df-post}}

{{cja-df-na}}

Customer Journey Analytics non ha un concetto nativo del tipo di evento in cui include o esclude automaticamente gli hit in base al loro contesto. È possibile utilizzare `xdm.eventType` per determinare quali eventi includere ed escludere nella maggior parte dei rapporti.

+++

+++**`cust_hit_time_gmt`**

Solo suite di rapporti abilitate per la marca temporale. La marca temporale inviata con l’hit, in base al tempo UNIX®.

Customer Journey Analytics non ha un concetto di suite di rapporti con marca temporale o senza marca temporale. Utilizzare `xdm.timestamp` e modificare le impostazioni del componente come desiderato.

{{cja-df-post}}

+++

+++**`cust_visid`**

ID visitatore personalizzato, se impostato con `visitorID`.

Customer Journey Analytics supporta un numero qualsiasi di identità che utilizzano [`identityMap`](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/field-groups/profile/identitymap). Se l’organizzazione utilizza identità personalizzate, è probabile che sia all’interno della mappa delle identità.

{{cja-df-post}}

+++

+++**`c_color`**

Profondità in bit della palette di colori. Utilizzato come parte del calcolo della dimensione Profondità colore. AppMeasurement utilizza la funzione `screen.colorDepth()` di JavaScript.

+++

+++**`daily_visitor`**

Flag che determina se l’hit è un nuovo visitatore giornaliero.

+++

+++**`dataprivacyconsentoptin`**

La dimensione di consenso alla gestione del consenso. È possibile che siano presenti più valori per hit, separati da una barra verticale (`\|`). I valori validi includono `DMP` e `SELL`.

Se la tua organizzazione dispone di una piattaforma di gestione dati, probabilmente popola i campi XDM desiderati per questa dimensione.

+++

+++**`dataprivacyconsentoptout`**

La dimensione di rinuncia alla gestione del consenso. È possibile che siano presenti più valori per hit, separati da una barra verticale (`\|`). I valori validi includono `SSF`, `DMP` e `SELL`.

Se la tua organizzazione dispone di una piattaforma di gestione dati, probabilmente popola i campi XDM desiderati per questa dimensione.

+++

+++**`date_time`**

L’ora dell’hit in formato leggibile, in base al fuso orario della suite di rapporti.

È possibile utilizzare `xdm.timestamp` e applicare l&#39;impostazione del componente **[!UICONTROL Date]** o **[!UICONTROL Date-time]** [Format](/help/data-views/component-settings/format.md).

+++

+++**`domain`**

La dimensione Dominio. In base al punto di accesso a Internet del visitatore.

Abilita **[!UICONTROL Ricerca di rete]** quando [Configurazione di uno stream di dati](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/configure). Il campo XDM è `xdm.environment.domain` se è incluso nello schema.

+++

+++**`duplicated_from`**

Utilizzato solo nelle suite di rapporti contenenti regole VISTA della copia hit. Indica la suite di rapporti da cui è stato copiato l’hit.

{{cja-df-na}}

Questa colonna non è applicabile perché Customer Journey Analytics non ha un concetto di regole VISTA.

+++

+++**`duplicate_events`**

Elenca ogni evento conteggiato come duplicato.

{{cja-df-na}}

Customer Journey Analytics non dispone di un singolo campo che funge da flag di deduplicazione per tutte le metriche. Ogni metrica contiene invece le proprie [impostazioni dei componenti di deduplicazione delle metriche](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication). Di conseguenza, non esiste un campo equivalente in Customer Journey Analytics per questa colonna del feed dati di Adobe Analytics.

+++

+++**`duplicate_purchase`**

Flag che determina se l’evento di acquisto per questo hit viene ignorato perché è un duplicato.

Anche se non esiste una traduzione diretta in questa colonna del feed dati di Analytics, la sua funzionalità di azione per deduplicare gli acquisti esiste ancora. Se utilizzi il gruppo di campi [[!UICONTROL Dettagli Commerce]](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/field-groups/event/commerce-details), puoi impostare [Impostazioni del componente di deduplicazione della metrica](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication) in cui l&#39;**[!UICONTROL ID deduplicazione]** è `xdm.commerce.purchases.id`.

Se è necessaria una traduzione diretta quando si desidera un flag per acquisti duplicati, è possibile utilizzare un [campo derivato](/help/data-views/derived-fields/derived-fields.md) utilizzando la funzione **Deduplica** nel set di regole.

+++

+++**`ef_id`**

L’ID EF, utilizzato nelle integrazioni Adobe Advertising.

{{cja-df-post}}

+++

+++**`evar1 - evar250`**

Variabili personalizzate 1-250. Utilizzato nelle dimensioni di eVar. Ogni organizzazione utilizza le eVar in modo diverso. Il luogo migliore per ulteriori informazioni su come la tua organizzazione compila le rispettive eVar sarebbe un documento di progettazione della soluzione specifico per la tua organizzazione.

{{cja-df-post}}

+++

+++**`event_list`**

Elenco separato da virgole di ID numerici che rappresentano eventi attivati sull’hit. Include eventi di e-commerce ed eventi personalizzati da 1 a 1000. Usa la ricerca `event.tsv`.

Questa colonna è probabilmente associata a decine di metriche separate, a seconda dell’implementazione. Adobe consiglia di eseguire il seguente processo per mappare ciascuna metrica in Customer Journey Analytics al relativo valore numerico rappresentato in questa colonna del feed dati di Analytics:

1. Utilizzare la ricerca `event.tsv` per mappare ogni valore numerico al relativo nome di metrica.
1. Utilizza il documento di progettazione della soluzione per mappare ogni nome evento di Analytics al nome della metrica corrispondente in Customer Journey Analytics.
1. Seleziona il componente mappato nell’interfaccia utente Visualizzazioni dati e annota il relativo ID componente. Se l’ID componente è troppo complesso, puoi popolare il campo ID alias del feed dati e utilizzarlo.
1. Ripeti l’operazione per ogni metrica utilizzata dalla tua organizzazione.

{{cja-df-post}}

Se lo schema utilizza il gruppo di campi [[!UICONTROL Dettagli Commerce]](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/field-groups/event/commerce-details), alcune metriche potrebbero essere mappate direttamente ai seguenti campi XDM:

* **Casse**: `xdm.commerce.checkouts.value`
* **Aggiunte al carrello**: `xdm.commerce.productListAdds.value`
* **Apertura carrello**: `xdm.commerce.productListOpens.value`
* **Rimozioni dal carrello**: `xdm.commerce.productListRemovals.value`
* **Visualizzazioni carrello**: `xdm.commerce.productListViews.value`
* **Visualizzazioni prodotto**: `xdm.commerce.productViews.value`
* **Ordini**: `xdm.commerce.purchases.value`

Alcune metriche possono utilizzare la serializzazione degli eventi, ovvero il modo in cui Adobe Analytics consente il controllo completo sulla deduplicazione. È possibile utilizzare l&#39;impostazione del componente [Deduplicazione metrica](/help/data-views/component-settings/metric-deduplication.md) per ottenere la parità di deduplicazione.

* Se la metrica deduplica per visita in Adobe Analytics, puoi impostare l’ambito di deduplicazione sulla sessione nelle impostazioni dei componenti di quella metrica.
* Se la metrica viene deduplicata per ID evento in Adobe Analytics, è probabile che l’oggetto XDM per tale metrica contenga sia un campo `value` che un campo `id`. Se lo schema utilizza il gruppo di campi [[!UICONTROL Dettagli Commerce]](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/field-groups/event/commerce-details), è probabile che tali metriche risiedano in questi campi XDM, che è possibile impostare il campo **[!UICONTROL ID deduplicazione]** nelle impostazioni del componente della metrica:

   * **Casse**: `xdm.commerce.checkouts.id`
   * **Aggiunte al carrello**: `xdm.commerce.productListAdds.id`
   * **Apertura carrello**: `xdm.commerce.productListOpens.id`
   * **Rimozioni dal carrello**: `xdm.commerce.productListRemovals.id`
   * **Visualizzazioni carrello**: `xdm.commerce.productListViews.id`
   * **Visualizzazioni prodotto**: `xdm.commerce.productViews.id`

Per deduplicare la metrica Ordini, vedere `duplicate_purchase`.

+++

+++**`exclude_hit`**

Flag che determina se l’hit è escluso dal reporting. La colonna `visit_num` non viene incrementata per gli hit esclusi.

Customer Journey Analytics non rispetta gli &quot;hit esclusi&quot; predefiniti. Tuttavia, puoi ricreare questa funzionalità se disponi di un campo XDM che contrassegna alcuni hit da escludere:

1. Assicurati che il campo XDM che contrassegna gli hit esclusi sia incluso come componente (dimensione o metrica, a seconda di come hai impostato questo flag). La selezione di [Nascondi componente nel reporting](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/component-settings/overview) è probabilmente utile per questo campo.
1. In [Impostazioni visualizzazione dati](/help/data-views/session-settings.md), selezionare il menu a discesa **[!UICONTROL Aggiungi segmento]** e selezionare **[!UICONTROL Crea segmento]**.
1. Crea un segmento che escluda tutti gli eventi in cui esiste il componente hit di esclusione o contiene valori che desideri escludere.
1. Seleziona **[!UICONTROL Salva]** sia nel segmento che nella visualizzazione dati.

Gli hit esclusi ora non esistono nei rapporti di Customer Journey Analytics, ma sono ancora disponibili nelle esportazioni di feed di dati.

+++

+++**`first_hit_pagename`**

La dimensione Pagina di ingresso originale. Il nome della pagina di ingresso originale del visitatore.

+++

+++**`first_hit_page_url`**

Il primo URL del visitatore.

+++

+++**`first_hit_referrer`**

Il primo URL di provenienza del visitatore.

+++

+++**`first_hit_ref_domain`**

La dimensione Dominio di riferimento originale. In base a `first_hit_referrer`. Il primo dominio di provenienza del visitatore.

+++

+++**`first_hit_ref_type`**

Un ID numerico che rappresenta il tipo di referrer del primo referrer del visitatore.

{{cja-df-lookup}}

+++

+++**`first_hit_time_gmt`**

Marca temporale del primo hit del visitatore in tempo UNIX®.

+++

+++**`geo_city`**

Il nome della città da cui proviene l’hit, in base all’IP. Utilizzato nella dimensione Città.

+++

+++**`geo_country`**

L’abbreviazione del paese da cui proviene l’hit, basata su IP. Utilizzato nella dimensione Paesi.

+++

+++**`geo_dma`**

ID numerico dell’area demografica di origine dell’hit, basato su IP. Utilizzato nella dimensione DMA USA.

+++

+++**`geo_region`**

Il nome dello stato o dell’area geografica da cui proviene l’hit, in base all’IP. Utilizzato nella dimensione Aree geografiche.

+++

+++**`geo_zip`**

Il codice postale di origine dell’hit, basato su IP. Consente di popolare la dimensione Codice postale. Consulta anche `zip`.

+++

+++**`hitid_high`**

Utilizzato con `hitid_low` per identificare un hit.

+++

+++**`hitid_low`**

Utilizzato con `hitid_high` per identificare un hit.

+++

+++**`hit_source`**

La fonte da cui proviene l’hit. Le origini di hit 1 e 2 sono fatturate. <br>1: richiesta immagine standard senza marca temporale <br>2: richiesta immagine standard con marca temporale <br>3: caricamento origine dati live con marca temporale <br>4: non utilizzato <br>5: caricamento origine dati generica <br>6: non più utilizzato; caricamento origine dati a elaborazione completa <br>7: caricamento origine dati TransactionID <br>8: non più utilizzato; versioni precedenti di origini dati di Adobe Advertising <br>9: non più utilizzato; metriche di riepilogo di Adobe Social <br>10: inoltro lato server di Audience Manager utilizzato

+++

+++**`hit_time_gmt`**

La marca temporale dei server Adobe di raccolta dati degli hit ha ricevuto l’hit, in base all’ora UNIX®.

+++

+++**`hourly_visitor`**

Flag che determina se l’hit è un nuovo visitatore orario.

+++

+++**`ip`**

L’indirizzo IPv4, in base all’intestazione HTTP della richiesta di immagine. Reciprocamente esclusivo per `ipv6`; se questa colonna contiene un indirizzo IP non offuscato, `ipv6` è vuoto.

+++

+++**`ipv6`**

Indirizzo IPv6 compresso, se disponibile. Reciprocamente esclusivo per `ip`; se questa colonna contiene un indirizzo IP non offuscato, `ip` è vuoto.

+++

+++**`javascript`**

ID di ricerca della versione di JavaScript, basato su `j_jscript`.

{{cja-df-lookup}}

+++

+++**`java_enabled`**

La dimensione Java abilitato. <br>Y: abilitato <br>N: disabilitato <br>U: sconosciuto

{{cja-df-post}}

+++

+++**`j_jscript`**

Versione di JavaScript supportata dal browser.

+++

+++**`language`**

Un ID numerico che rappresenta la lingua del visitatore.

{{cja-df-lookup}}

+++

+++**`last_hit_time_gmt`**

Marca temporale (in ora UNIX®) dell’hit precedente. Utilizzato per calcolare la dimensione Giorni dall’ultima visita.

+++

+++**`last_purchase_num`**

La dimensione Fedeltà del cliente. Il numero di acquisti precedenti effettuati dal visitatore. <br>0: nessun acquisto precedente (non è un cliente) <br>1: 1 acquisto precedente (nuovo cliente) <br>2: 2 acquisti precedenti (cliente di ritorno) <br>3: 3 o più acquisti precedenti (cliente abituale)

+++

+++**`last_purchase_time_gmt`**

Utilizzato nella dimensione Giorni dall’ultimo acquisto. Marca temporale (in ora UNIX®) dell’ultimo acquisto effettuato. Per i nuovi acquisti e i visitatori che non hanno effettuato un acquisto in precedenza, questo valore è `0`.

+++

+++**`latlon1`**

Posizione (fino a 10 chilometri)

+++

+++**`latlon23`**

Posizione (fino a 100 m)

+++

+++**`latlon45`**

Posizione (fino a 1 m)

+++

+++**`mcvisid`**

ID visitatore di Experience Cloud. Numero a 128 bit costituito da due numeri concatenati a 64 bit aggiunti a 19 cifre.

+++

+++**`mc_audiences`**

Elenco degli ID del segmento di Audience Manager a cui appartiene il visitatore. Nella colonna `post_mc_audiences` il delimitatore diventa `--**--`.

{{cja-df-post}}

+++

+++**`mobileaction`**

Azione da dispositivo mobile. Raccolta automatica quando `trackAction` viene chiamato nelle implementazioni mobili. Consente il percorso automatico delle azioni nell’app.

{{cja-df-post}}

+++

+++**`mobileappid`**

ID dell’app mobile. Memorizza il nome e la versione dell&#39;applicazione nel seguente formato: `[AppName] [BundleVersion]`

`xdm.application.name` + `xdm.application.version`

{{cja-df-post}}

+++

+++**`mobileappperformanceappid`**

Utilizzato nel connettore dati Apteligent. L’ID app utilizzato in Apteligent.

+++

+++**`mobileappperformancecrashid`**

Utilizzato nel connettore dati Apteligent. ID di arresto anomalo utilizzato in Apteligent.

+++

+++**`mobileappstoreobjectid`**

Utilizzato nel connettore dati [!DNL Appfigures]. ID dell’oggetto nell’app store.

+++

+++**`mobilebeaconmajor`**

Beacon principale di Mobile Services

+++

+++**`mobilebeaconminor`**

Beacon secondario di Mobile Services

+++

+++**`mobilebeaconproximity`**

Prossimità beacon di Mobile Services

+++

+++**`mobilebeaconuuid`**

UUID del beacon di Mobile Services

+++

+++**`mobilecampaigncontent`**

Nome o ID del contenuto che ha visualizzato il collegamento. Viene compilata dalla funzione Acquisizione da app mobile.

{{cja-df-post}}

+++

+++**`mobilecampaignmedium`**

Canale di marketing, ad esempio banner o e-mail. Viene compilata dalla funzione Acquisizione da app mobile.

{{cja-df-post}}

+++

+++**`mobilecampaignname`**

Il nome della campagna, memorizzato anche nella variabile della campagna. Viene compilata dalla funzione Acquisizione da app mobile.

{{cja-df-post}}

+++

+++**`mobilecampaignsource`**

Referente originale, ad esempio newsletter o Social media network. Viene compilata dalla funzione Acquisizione da app mobile.

{{cja-df-post}}

+++

+++**`mobilecampaignterm`**

Parole chiave a pagamento o altri termini di cui tenere traccia con questa acquisizione. Viene compilata dalla funzione Acquisizione da app mobile.

{{cja-df-post}}

+++

+++**`mobiledayofweek`**

Numero del giorno della settimana in cui è stata avviata l’app.

{{cja-df-post}}

+++

+++**`mobiledayssincefirstuse`**

Numero di giorni dalla prima esecuzione dell’app.

{{cja-df-post}}

+++

+++**`mobiledayssincelastuse`**

Numero di giorni dall’ultima esecuzione dell’app.

{{cja-df-post}}

+++

+++**`mobiledeeplinkid`**

Raccolto dalla variabile di dati di contesto `a.deeplink.id`. Utilizzato nei rapporti di acquisizione come identificatore per il collegamento di acquisizione mobile.

+++

+++**`mobiledevice`**

Nome del dispositivo mobile. In iOS, viene memorizzato come stringa di 2 cifre separate da virgola. Il primo numero rappresenta la generazione del dispositivo e il secondo rappresenta la famiglia di dispositivi.

{{cja-df-post}}

+++

+++**`mobilehourofday`**

Definisce l’ora del giorno in cui l’app è stata avviata. Segue il formato numerico di 24 ore.

{{cja-df-post}}

+++

+++**`mobileinstalldate`**

Data di installazione dell’app mobile. Fornisce la data della prima apertura dell’app mobile da parte di un utente.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilelaunchnumber`**

Aumenta di uno ogni volta che l’app mobile viene avviata.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilemessagebuttonname`**

Raccolto dalla variabile di dati di contesto `a.message.button.id`. Utilizzato per la messaggistica in-app per identificare il pulsante che ha chiuso il messaggio.

{{cja-df-post}}

+++

+++**`mobilemessageid`**

ID messaggio in-app

{{cja-df-post}}

+++

+++**`mobilemessageonline`**

Messaggio in-app online

{{cja-df-post}}

+++

+++**`mobilemessagepushoptin`**

Raccolto dalla variabile di dati di contesto `a.push.optin`. Imposta su “true” quando l’utente acconsente ai messaggi push; altrimenti il valore è “false”.

{{cja-df-post}}

+++

+++**`mobilemessagepushpayloadid`**

Raccolto dalla variabile di dati di contesto `a.push.payloadid`. Utilizzato nei messaggi push come identificatore del payload.

{{cja-df-post}}

+++

+++**`mobileosversion`**

Versione del sistema operativo Mobile Services

{{cja-df-post}}

+++

+++**`mobileplaceaccuracy`**

Raccolto dalla variabile di dati di contesto `a.loc.acc`. Indica la precisione del GPS in metri al momento della raccolta.

+++

+++**`mobileplacecategory`**

Raccolto dalla variabile di dati di contesto `a.loc.category`. Descrive la categoria di un luogo specifico.

+++

+++**`mobileplaceid`**

Raccolto dalla variabile di dati di contesto `a.loc.id`. Identificatore per un dato punto di interesse.

+++

+++**`mobilepushoptin`**

Consenso push Mobile Services

{{cja-df-post}}

+++

+++**`mobilepushpayloadid`**

ID payload push Mobile Services

{{cja-df-post}}

+++

+++**`mobilerelaunchcampaigncontent`**

Contenuto del lancio Mobile Services

+++

+++**`mobilerelaunchcampaignmedium`**

Media del lancio Mobile Services

+++

+++**`mobilerelaunchcampaignsource`**

Origine del lancio Mobile Services

+++

+++**`mobilerelaunchcampaignterm`**

Termine del lancio Mobile Services

+++

+++**`mobilerelaunchcampaigntrackingcode`**

Raccolto dalla variabile di dati di contesto `a.launch.campaign.trackingcode`. Utilizzato nell’acquisizione come codice di tracciamento per la campagna di lancio.

+++

+++**`mobileresolution`**

Risoluzione del dispositivo mobile. `[Width] x [Height]` in pixel.

{{cja-df-post}}

+++

+++**`mobile_id`**
Se l’utente utilizza un dispositivo mobile, l’ID numerico del dispositivo.

{{cja-df-lookup}}

+++

+++**`monthly_visitor`**

Flag che determina se il visitatore è univoco per il mese corrente.

+++

+++**`mvvar1`** - **`mvvar3`**

Elenca i valori delle variabili. Contiene un elenco delimitato di valori personalizzati a seconda dell’implementazione. Nelle colonne `post_mvvar1` - `post_mvvar3` il delimitatore originale è sostituito da `--**--`.

{{cja-df-post}}

+++

+++**`mvvar1_instances`** - **`mvvar3_instances`**

I valori delle variabili di elenco impostati sull’hit corrente. Sostituisce il delimitatore originale con `--**--`. Le colonne `post` in genere non contengono dati.

{{cja-df-post}}

+++

+++**`new_visit`**

Flag che determina se l’hit corrente è una nuova visita. Impostato da Adobe dopo 30 minuti di inattività della visita.

+++

+++**`os`**

Un ID numerico che rappresenta il sistema operativo del visitatore. In base alla colonna `user_agent`.

{{cja-df-lookup}}

Durante la [configurazione di uno stream di dati](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/configure), è possibile abilitare **[!UICONTROL Ricerca dispositivo]**. Se attivato, selezionare la casella di controllo **[!UICONTROL Sistema operativo]**. Se hai incluso questi campi nello schema, i seguenti campi XDM vengono compilati automaticamente:

* **Fornitore sistema operativo**: `xdm.environment.operatingSystemVendor`
* **Nome sistema operativo**: `xdm.environment.operatingSystem`
* **Versione sistema operativo**: `xdm.environment.operatingSystemVersion`

{{cja-df-ua}}

+++

+++**`pagename`**

La dimensione Pagina. Se la variabile `pagename` è vuota, Analytics utilizza `page_url`.

{{cja-df-post}}

+++

+++**`pagename_no_url`**

Simile a `pagename`, tranne per il fatto che non torna a `page_url`. Solo la colonna `post` è disponibile.

{{cja-df-post}}

+++

+++**`page_event`**

Tipo di hit inviato nella richiesta di immagine (hit standard, collegamento per il download, collegamento personalizzato, collegamento di uscita).

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`page_event_var1`**

Utilizzato solo nelle richieste di immagine per il tracciamento dei collegamenti. L’URL del collegamento di download, del collegamento di uscita o del collegamento personalizzato in cui è stato fatto clic.

{{cja-df-post}}

+++

+++**`page_event_var2`**

Utilizzato solo nelle richieste di immagine per il tracciamento dei collegamenti. Nome personalizzato (se specificato) del collegamento. Imposta il collegamento personalizzato, il collegamento di download o il collegamento di uscita a seconda del valore in `page_event`.

{{cja-df-post}}

+++

+++**`page_type`**

La dimensione Pagine non trovate, che in genere viene utilizzata per 404 pagine.

{{cja-df-post}}

+++

+++**`page_url`**

**`page_url`**: URL dell&#39;hit. Utilizza un tipo di dati testo.<br>**`post_page_url`**: rimosso per le richieste di immagini di tracciamento dei collegamenti (`tl()`).

{{cja-df-post}}

+++

+++**`paid_search`**

Flag che determina se l’hit corrisponde al rilevamento di ricerche a pagamento.

+++

+++**`persistent_cookie`**

Utilizzato nella dimensione Supporto cookie persistenti. Indica se il visitatore supporta i cookie che non vengono eliminati dopo ogni hit.

{{cja-df-post}}

+++

+++**`pointofinterest`**

Nome del punto di interesse in Mobile Services

{{cja-df-post}}

+++

+++**`pointofinterestdistance`**

Distanza dal centro del punto di interesse in Mobile Services 

{{cja-df-post}}

+++

+++**`product_list`**

La variabile di pagina `products`. Consente di popolare diverse dimensioni e metriche, tra cui Categoria, Prodotto, Unità e Ricavi.

{{cja-df-post}}

+++

+++**`prop1`** - **`prop75`**

Variabili di traffico personalizzate da 1 a 75. Utilizzato nelle dimensioni Prop.

{{cja-df-post}}

+++

+++**`purchaseid`**

Identificatore univoco per un acquisto, impostato mediante la variabile `purchaseID`. Utilizzato dalla colonna `duplicate_purchase`.

`xdm.commerce.order.purchaseID`

{{cja-df-post}}

+++

+++**`quarterly_visitor`**

Flag che determina se l’hit è un nuovo visitatore trimestrale.

+++

+++**`referrer`**

La dimensione Referrer. Tieni presente che `referrer` utilizza un tipo di dati varchar(255), `post_referrer` utilizza un tipo di dati varchar(244).

{{cja-df-post}}

+++

+++**`ref_domain`**

La dimensione Dominio di riferimento. In base alla colonna `referrer`.

+++

+++**`ref_type`**


ID numerico che rappresenta il tipo di riferimento per l’hit. Utilizzato nella dimensione Tipo referrer.<br>1: all&#39;interno del sito<br>2: altri siti Web<br>3: motori di ricerca<br>4: disco rigido<br>5: USENET<br>6: digitato/contrassegnato con segnalibro (nessun referrer)<br>7: e-mail<br>8: nessun JavaScript<br>9: social network<br>10: strumenti di IA per la conversazione

+++

+++**`resolution`**

ID numerico che rappresenta la risoluzione del monitoraggio. Utilizzato nella dimensione Risoluzione monitor.

{{cja-df-lookup}}

+++

+++**`search_engine`**

Un ID numerico che rappresenta il motore di ricerca che ha indirizzato il visitatore al sito. Utilizzato nelle dimensioni del motore di ricerca.

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`search_page_num`**

Utilizzato dalla dimensione Classificazione di tutte le pagine di ricerca. Indica in quale pagina dei risultati di ricerca è stato visualizzato il sito prima che l’utente facesse clic su esso.

+++

+++**`secondary_hit`**

Flag che determina se l’hit è un hit secondario. Questo flag in genere ha origine dall’assegnazione di tag a più suite e dalle regole VISTA che consentono di copiare gli hit.

+++

+++**`sourceid`**

ID sorgente

+++

+++**`stats_server`**

Non è utile. Server interno di Adobe che ha elaborato l’hit.

+++

+++**`s_kwcid`**

ID parola chiave utilizzato nelle integrazioni Adobe Advertising. 

{{cja-df-post}}

+++

+++**`s_resolution`**

Valore di risoluzione dello schermo non elaborato. Raccolto utilizzando la funzione JavaScript `screen.width x screen.height`.

+++

+++**`tnt`**

Utilizzato nelle integrazioni Adobe Target. Rappresenta tutti i test attualmente qualificati per. Il formato è: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`.

{{cja-df-post}}

+++

+++**`tnt_action`**

Utilizzato nelle integrazioni Adobe Target. Rappresenta tutti i test per i quali l’hit è qualificato.

{{cja-df-post}}

+++

+++**`tnt_instances`**

Utilizzato nelle integrazioni Adobe Target. Variabile delle istanze Target.

+++

+++**`transactionid`**

Identificatore univoco in cui è possibile caricare vari punti dati in un secondo momento tramite origini dati. Raccolte utilizzando la variabile `transactionID`.

`xdm.commerce.order.payments[0].transactionID`

{{cja-df-post}}

+++

+++**`truncated_hit`**

Flag che indica che la richiesta di immagine è stata troncata (è stato ricevuto un hit parziale). <br>Y: hit troncato; hit parziale ricevuto <br>N: hit non troncato; hit completo ricevuto

+++

+++**`t_time_info`**

Ora locale del visitatore. Il formato è: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)`

{{cja-df-post}}

+++

+++**`userid`**

Non è utile. ID numerico dell&#39;ID suite di rapporti. Usa `username` invece.

+++

+++**`username`**

ID suite di rapporti per l&#39;hit.

+++

+++**`user_agent`**

Stringa dell’agente utente inviata nell’intestazione HTTP della richiesta di immagine.

+++

+++**`user_hash`**

Non è utile. Hash sull&#39;ID suite di rapporti. Usa `username` invece.

+++

+++**`user_server`**

Utilizzato nella dimensione Server.

{{cja-df-post}}

+++

+++**`va_closer_detail`**

La dimensione Dettaglio ultimo contatto.

+++

+++**`va_closer_id`**

Un ID numerico che identifica la dimensione Canale di ultimo contatto.

{{cja-df-lookup}}

+++

+++**`va_finder_detail`**

La dimensione Dettaglio primo contatto.

+++

+++**`va_finder_id`**

Un ID numerico che identifica la dimensione Canale di primo contatto.

{{cja-df-lookup}}

+++

+++**`va_instance_event`**

Un flag che identifica le istanze del canale di marketing.

+++

+++**`va_new_engagement`**

Un flag che identifica il canale di marketing Nuovi impegni.

+++

+++**`video`**

La dimensione Servizi multimediali di streaming di contenuti.

{{cja-df-post}}

+++

+++**`videoad`**

La dimensione Servizi multimediali di streaming di annunci.

{{cja-df-post}}

+++

+++**`videoadinpod`**

La dimensione Servizi multimediali di streaming di posizione annuncio nel pod.

{{cja-df-post}}

+++

+++**`videoadlength`**

La dimensione Lunghezza annuncio (variabile) dei servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videoadname`**

La dimensione Nome annuncio (variabile) dei servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videoadplayername`**

La dimensione Servizi multimediali in streaming con il nome del lettore di annunci.

{{cja-df-post}}

+++

+++**`videoadpod`**

La dimensione Servizi multimediali di streaming del pod dell’annuncio.

{{cja-df-post}}

+++

+++**`videoadvertiser`**

La dimensione Advertiser (Inserzionista) per i servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videoaudioalbum`**

La dimensione Servizi multimediali di streaming per album.

+++

+++**`videoaudioartist`**

La dimensione Artista servizi multimediali in streaming.

+++

+++**`videoaudioauthor`**

La dimensione Autore servizi multimediali in streaming.

+++

+++**`videoaudiolabel`**

La dimensione Servizi multimediali di streaming di etichette.

+++

+++**`videoaudiopublisher`**

La dimensione Servizi multimediali di streaming di Publisher.

+++

+++**`videoaudiostation`**

La dimensione Servizi multimediali di streaming della stazione.

+++

+++**`videocampaign`**

La dimensione ID campagna: servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videochannel`**

La dimensione Servizi multimediali di streaming per il canale dei contenuti.

{{cja-df-post}}

+++

+++**`videochapter`**

La dimensione Capitolo servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videocontenttype`**

La dimensione Tipo di contenuto servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videodaypart`**

La dimensione Fascia oraria dei servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videoepisode`**

La dimensione Servizi multimediali in streaming dell’episodio.

{{cja-df-post}}

+++

+++**`videofeedtype`**

La dimensione Tipo di feed multimediale servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videogenre`**

La dimensione Servizi multimediali di streaming di genere. Questa dimensione consente di inserire più valori nello stesso hit, delimitati da una virgola.

{{cja-df-post}}

+++

+++**`videolength`**

La dimensione Lunghezza del contenuto (variabile) dei servizi di contenuti multimediali in streaming.

{{cja-df-post}}

+++

+++**`videomvpd`**

La dimensione Servizi multimediali di streaming di MVPD.

{{cja-df-post}}

+++

+++**`videoname`**

La dimensione Nome contenuto (variabile) dei servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videonetwork`**

La dimensione Servizi multimediali di streaming di rete.

{{cja-df-post}}

+++

+++**`videopath`**

La dimensione Percorso multimediale per i servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videoplayername`**

La dimensione Nome del lettore di contenuti servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videoqoebitrateaverageevar`**

La dimensione del bitrate medio dei servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videoqoebitratechangecountevar`**

Il bitrate cambia la dimensione servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videoqoebuffercountevar`**

La dimensione Eventi buffer in streaming per i servizi multimediali.

{{cja-df-post}}

+++

+++**`videoqoebuffertimeevar`**

La dimensione Durata totale del buffer per i servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videoqoedroppedframecountevar`**

La dimensione Servizi multimediali in streaming con fotogrammi rilasciati.

{{cja-df-post}}

+++

+++**`videoqoeerrorcountevar`**

La dimensione Errori dei servizi multimediali in streaming.

+++
{{cja-df-post}}


+++**`videoqoeextneralerrors`**

La dimensione ID errore esterno per Streaming Media Services. Questa dimensione consente più valori nello stesso hit.

+++

+++**`videoqoeplayersdkerrors`**

La dimensione ID errore SDK del lettore relativa ai servizi multimediali in streaming. Questa dimensione consente più valori nello stesso hit.

{{cja-df-post}}

+++

+++**`videoqoetimetostartevar`**

La dimensione Tempo per l’avvio dei servizi di streaming multimediale.

{{cja-df-post}}

+++

+++**`videoseason`**

La dimensione Stagione servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videosegment`**

La dimensione Segmento di contenuto streaming servizi multimediali.

{{cja-df-post}}

+++

+++**`videosessionid`**

La dimensione ID sessione multimediale: servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videoshow`**

La dimensione Mostra servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videoshowtype`**

La dimensione Tipo di spettacolo: servizi multimediali in streaming.

{{cja-df-post}}

+++

+++**`videostreamtype`**

La dimensione Tipo di flusso Servizi multimediali in streaming.

+++

+++**`visid_high`**

Utilizzato con `visid_low` per identificare in modo univoco un visitatore.

{{cja-df-post}}

+++

+++**`visid_low`**

Utilizzato con `visid_high` per identificare in modo univoco un visitatore.

{{cja-df-post}}

+++

+++**`visid_new`**

Flag che determina se l’hit contiene un ID visitatore appena generato.

+++

+++**`visid_timestamp`**

Se un ID visitatore è stato generato di recente, fornisce la marca temporale in UNIX® dell’ora in cui è stato generato l’ID visitatore.

+++

+++**`visid_type`**

Non per uso esterno; utilizzato internamente da Adobe per l’elaborazione delle ottimizzazioni. Un ID numerico che rappresenta il metodo utilizzato per identificare il visitatore.<br>`0`: ID visitatore personalizzato o sconosciuto/non applicabile<br>`1`: fallback dell’IP e dell’agente utente <br>`2`: intestazione dell’abbonato mobile HTTP <br>`3`: valore cookie legacy (`s_vi`) <br>`4` valore cookie di fallback (`s_fid`) <br>`5`: servizio identità

{{cja-df-post}}

+++

+++**`visit_keywords`**

La dimensione Parola chiave di ricerca. Questa colonna utilizza un limite di caratteri non standard di varchar(244) per adattarsi alla logica back-end utilizzata da Adobe. La colonna post-elaborazione è `**post_keywords**`, non `**post_visit_keywords**`.

{{cja-df-post}}

+++

+++**`visit_num`**

La dimensione Numero di visite. Inizia a 1 e viene incrementato ogni volta che inizia una nuova visita per visitatore.

+++

+++**`visit_page_num`**

La dimensione Profondità di hit. Aumenta di 1 per ogni hit generato dal visitatore. Ripristina ogni visita.

+++

+++**`visit_referrer`**

Il primo referrer della visita.

+++

+++**`visit_ref_domain`**

In base alla colonna `visit_referrer`. Il primo dominio di riferimento della visita.

+++

+++**`visit_ref_type`**

Un ID numerico che rappresenta il tipo di referrer del primo referrer della visita.

{{cja-df-lookup}}

+++

+++**`visit_search_engine`**

Un ID numerico che rappresenta il primo motore di ricerca della visita.

{{cja-df-lookup}}

+++

+++**`visit_start_pagename`**

Pagina del primo hit della visita.

+++

+++**`visit_start_page_url`**

URL del primo hit della visita.

+++

+++**`visit_start_time_gmt`**

Marca temporale (in tempo UNIX®) del primo hit della visita.

+++

+++**`weekly_visitor`**

Flag che determina se l’hit è un nuovo visitatore settimanale.

+++

+++**`yearly_visitor`**

Flag che determina se l’hit è un nuovo visitatore annuale.

+++

+++**`zip`**

Consente di popolare la dimensione Codice postale. Consulta anche `geo_zip`.

{{cja-df-post}}

+++
