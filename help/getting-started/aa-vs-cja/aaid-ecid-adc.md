---
source-git-commit: f97439676c61acf1b6ba8818ef1d06542402e675
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 9%

---
# AAID, ECID, AACUSTOMID e il connettore di origine di Analytics

I dati di Adobe Analytics contengono più campi di identità. Tre importanti campi d&#39;identità sono trattati in modo particolare da [Connettore sorgente di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it):

* **AAID** è l’identificatore del dispositivo principale in Adobe Analytics ed è garantito che esista su ogni evento trasmesso tramite il connettore di origine di Analytics. AAID viene talvolta indicato come &quot;ID Analytics legacy&quot; o &quot;id cookie s\_vi&quot;, anche se viene creato un AAID anche se il cookie s\_vi non è presente. AAID è rappresentato dal **_post\_visid\_high/post\_visid\_low_** colonne in [Feed dati di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=it#columns%2C-descriptions%2C-and-data-types). Nel connettore di origine di Analytics, AAID viene trasformato in **HEX(post_visid_high) + &quot;-&quot; + HEX(host_visid_low)**. Il campo AAID su un dato evento contiene una singola identità che può essere uno dei diversi tipi descritti in [Ordine delle operazioni per gli ID di Analytics](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). All’interno di un’intera suite di rapporti, AAID può contenere diversi tipi di eventi. Il tipo di ogni hit è indicato nella variabile **_[post\_]visid\_type_** nei feed di dati di Analytics). Vedi anche: [Riferimento colonna dati](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=it).
* **ECID** (ID Experience Cloud), talvolta indicato anche come MCID (ID Marketing Cloud), è un campo di identificazione dispositivo separato che viene popolato in Adobe Analytics quando Adobe Analytics viene implementato utilizzando il [Servizio Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=it). ECID è rappresentato dal **_mcvisid_** nei feed di dati di Adobe Analytics. Se un ECID esiste su un evento, AAID può essere basato su ECID a seconda che Analytics [periodo di tolleranza](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=it) è configurato. Vedi anche: [Richieste Analytics ed Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).
* **AACUSTOMID** è un campo di identificazione separato che viene popolato in Adobe Analytics in base all&#39;utilizzo della variabile s.VisitorID nell&#39;implementazione di Analytics. AACUSTOMID è rappresentato dal **_cust_visid_** nei feed di dati di Adobe Analytics. Se AACUSTOMID è presente, AAID sarà basato su AACUSTOMID. (AACUSTOMID trumpa tutti gli altri identificatori come definiti dall&#39;ordine delle operazioni di cui sopra.)

Il connettore di origine di Analytics passa attraverso queste identità ad AEP in formato XDM come:

* endUserIDs.\_experience.aaid.id
* endUserIDs.\_experience.mcid.id
* endUserIDs.\_experience.aacustomid.id

Questi campi non sono contrassegnati come identità. Le stesse identità vengono invece copiate in XDM **_identityMap_** come coppie di valori chiave come segue:

* { &quot;key&quot;: &quot;AAID&quot;, &quot;value&quot;: [ { &quot;id&quot;: &quot;**_\&lt;identity>_**&quot;, &quot;primario&quot;: **_\&lt;true or=&quot;&quot; false=&quot;&quot;>_**} ] }
* { &quot;key&quot;: &quot;ECID&quot;, &quot;value&quot;: [ { &quot;id&quot;: &quot;**_\&lt;identity>_**&quot;, &quot;primario&quot;: **_\&lt;true or=&quot;&quot; false=&quot;&quot;>_** } ] }
* { &quot;key&quot;: &quot;AACUSTOMID&quot;, &quot;value&quot;: [ { &quot;id&quot;: &quot;**_\&lt;identity>_**&quot;, &quot;primario&quot;: **false** } ] }

In identityMap:

* Se ECID è presente, viene contrassegnato come identità principale per l’evento. In questo caso AAID può essere basato su ECID per la discussione precedente.
In caso contrario, AAID è contrassegnato come identità principale per l’evento.
* AACUSTOMID non viene mai contrassegnato come ID principale dell’evento. Tuttavia, se AACUSTOMID è presente, AAID si basa su AACUSTOMID come indicato nella discussione precedente.

Per quanto riguarda CJA, la definizione dell’ID principale è importante solo se l’utente finale decide di utilizzare l’ID principale come ID persona. Ciò non è tuttavia obbligatorio. L’utente può scegliere un’altra colonna di identità come ID persona.

