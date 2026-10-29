---
title: Unione Di Dati Multimediali A Pagamento Con Dati Web In Customer Journey Analytics
description: Unisciti ai dati di riepilogo dei contenuti multimediali a pagamento con eventi del sito web in Adobe Customer Journey Analytics per confrontare la spesa pubblicitaria, i clic, gli ordini, i ricavi e il ritorno sulla spesa pubblicitaria.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 62a6bb436d59ab7a5a7be515afbe1f5f0f7817ee
workflow-type: tm+mt
source-wordcount: '3912'
ht-degree: 3%
---
# Aggiungere dati multimediali a pagamento con dati web

Questa guida del caso d&#39;uso illustra come unire i dati di riepilogo dei contenuti multimediali a pagamento con i dati dell&#39;evento comportamentale del sito Web in [!DNL Adobe Customer Journey Analytics].


La connessione degli account dell’annuncio (Meta, Google Ads e altri) ad Experience Platform fornisce dati di riepilogo sui contenuti multimediali a pagamento in Customer Journey Analytics: impression giornaliere, clic, spesa e conversioni riportate dalla rete di annunci per account, campagna, gruppo di annunci, annuncio, esperienza e risorsa. Utilizzando Customer Journey Analytics, puoi raccogliere i dati dei tuoi eventi comportamentali nel sito con il SDK web: visualizzazioni di pagina, ordini, ricavi.

Unendo i due tipi di dati in un’unica tabella a forma libera di Workspace, puoi confrontare le prestazioni pubblicitarie con le attività sul tuo sito web. Utilizza gli ID di campagne, gruppi di annunci e annunci condivisi per generare rapporti su impression, clic e spese insieme a sbarchi, ordini e ricavi a pagamento in [!DNL Analysis Workspace].

| Origine dati | Esempio di metriche |
|---|---|
| Dati di riepilogo dei file multimediali a pagamento | Impression, clic, spesa, conversioni e valore di conversione segnalati dalla rete di annunci. |
| Eventi comportamentali del sito web | Pagamento di pagine di destinazione, visualizzazioni di pagina, ordini e ricavi misurati sul sito web |
| Metriche calcolate | Percentuale di pagine di destinazione, tasso di conversione web, ritorno sulla spesa pubblicitaria sul web, costo per ordine web e divario di conversione rete/web |

La combinazione di questi due tipi di dati consente di confrontare i dati pre-clic (dagli annunci) e i dati post-clic (dal sito web).

Questa guida descrive scenari basati su connessioni gestite da [!DNL Adobe Content Analytics] configurazioni e connessioni configurate dall&#39;utente.

## Come funziona

Il diagramma seguente illustra come i dati di riepilogo di elementi multimediali a pagamento e i dati di eventi comportamentali del sito web vengono acquisiti tramite una connessione Customer Journey Analytics.

La visualizzazione dati è responsabile dell’analisi e dell’allineamento dei dati, in modo da poter utilizzare Workspace per generare correttamente rapporti sui dati.

![Partecipazioni a pagamento](./assets/paid-media-web-join.png){zoomable="yes"}

I set di dati di riepilogo dei file multimediali a pagamento contengono metriche giornaliere senza un ID persona. I set di dati dell’evento del sito web contengono eventi comportamentali con marca temporale e un identificatore della persona. Un gruppo di dati di riepilogo associa le dimensioni da questi set di dati in modo che nella stessa riga di reporting vengano visualizzati valori di dimensione uguali.

>[!IMPORTANT]
>
>Questo join allinea i dati di riepilogo aggregati e gli eventi Web per il reporting. Non collega un’impression pubblicitaria o un clic a una singola persona. Le conversioni ad-network mantengono la metodologia di reporting della rete. Gli ordini e i ricavi dei siti web utilizzano le impostazioni di attribuzione configurate in questa guida.

## Comprendere l’unione di reporting

Puoi partecipare solo a livelli i cui ID vengono visualizzati negli URL della pagina di destinazione o nei campi evento esistenti. Ad esempio, l’assegnazione tag solo campagna supporta il reporting delle campagne, ma non quello a livello di annuncio.

>[!NOTE]
>
>I join a livello di esperienza e di risorsa di Content Analytics richiedono parametri URL aggiuntivi e non rientrano nell’ambito di questa guida.


Vedere [Dati di riepilogo](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/summary-data) e [Impostazioni dei componenti del gruppo di dati di riepilogo](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/component-settings/summary-data-group) per riferimento.

### Scegli la chiave di unione

I set di dati multimediali a pagamento forniscono sia ID di rete non elaborati che identificatori univoci globali (GUID) generati da Adobe.

| Identificatore | Esempio | Finalità |
|---|---|---|
| ID rete | ID campagna `123456789` | Abbina un ID acquisito dall’URL di una pagina di destinazione a una dimensione di riepilogo di elementi multimediali a pagamento |
| GUID | `meta_111111111_123456789` | Identificare un’entità a pagamento tramite la gerarchia di rete, account ed entità |

La struttura GUID è `{adNetwork}_{accountID}[_{campaignID}[_{adGroupID}[_{adID}]]]`. I componenti multimediali a pagamento gestiti da [!DNL Adobe Content Analytics] utilizzano questi GUID.

Questa guida utilizza gli ID di rete per i Web join perché le macro di campagne, gruppi di annunci e URL di annunci non forniscono tutte le informazioni necessarie per ricostruire un GUID. Utilizza i seguenti campi di riepilogo:

| Livello di reporting | Campo ID rete | Campo GUID |
|---|---|---|
| Campaign | `paidMedia.campaignID` | `paidMedia.campaignGUID` |
| Gruppo di annunci | `paidMedia.adGroupID` | `paidMedia.adGroupGUID` |
| Annuncio | `paidMedia.adID` | `paidMedia.adGUID` |

Il campo di rete è `paidMedia.adNetwork`. I valori di esempio includono `meta` e `google_ads`. Gli output di campi derivati devono corrispondere esattamente ai valori nei set di dati.

>[!NOTE]
>
>Un gruppo di dati di riepilogo corrisponde ai valori di dimensione, non a una combinazione di tutte le dimensioni nella tabella. Conferma che gli ID scelti identifichino le entità in modo non ambiguo tra gli account e le reti su cui esegui il rapporto. I gruppi basati sul nome possono combinare entità distinte che condividono un nome.

## Prerequisiti

Conferma di disporre di:

* [!DNL Customer Journey Analytics] Seleziona o versione successiva, con accesso alle funzioni di campo derivato utilizzate qui: [URL Parse](/help/data-views/derived-fields/derived-fields.md#url-parse), [Case When](/help/data-views/derived-fields/derived-fields.md#case-when), [Regex Replace](/help/data-views/derived-fields/derived-fields.md#regex-replace) e, per l&#39;arricchimento dei nomi, [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup).
* Autorizzazioni [!DNL Adobe Experience Platform] per gestire schemi, set di dati e flussi di dati nella sandbox di destinazione e accedere ai set di dati e a Query Service per la verifica.
* Autorizzazione [!DNL Customer Journey Analytics] per modificare la connessione di destinazione e la visualizzazione dati.
* Connettori per origini multimediali a pagamento configurati nella stessa sandbox e acquisizione di set di dati di riepilogo e di ricerca. Per un connettore di esempio, vedere [Origine Meta Ads](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/advertising/meta-ads).
* Eventi del sito web che acquisiscono l’URL completo della pagina di destinazione, inclusa la relativa stringa di query, o campi equivalenti contenenti gli ID di rete.


### Assegnazione di tag agli annunci

Identifica i parametri di query che contengono la campagna, il gruppo di annunci e gli ID di annunci. I tag basati su ID esistenti possono essere utilizzati senza apportare modifiche alle piattaforme di annunci.

| Pattern di assegnazione tag | Parametro della campagna | Parametro gruppo di annunci | Parametro annuncio |
|---|---|---|---|
| ID Meta nell’URL del sito web | <code>campaign_id={{campaign.id}}</code> | <code>adset_id={{adset.id}}</code> | <code>ad_id={{ad.id}}</code> |
| ID Meta nei parametri UTM | <code>utm_campaign={{campaign.id}}</code> | <code>utm_term={{adset.id}}</code> | <code>utm_content={{ad.id}}</code> |
| ID di Google Ads nei parametri UTM | <code>utm_campaign={{campaign}}</code> | <code>utm_term={{adgroupid}}</code> | <code>utm_content={{creative}}</code> |

Per i tag UTM di Meta, un valore di origine come `utm_source=fb` può identificare la rete. Per i tag UTM di Google Ads, utilizza un valore di origine come `utm_source=google`.

Alcune integrazioni di [!DNL Adobe Advertising] utilizzano un valore `s_kwcid` con questo layout:

```text
AL!<id>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}!{campaignid}!{adgroupid}
```

Le regole di analisi più avanti in questa guida si applicano solo a questo layout. Controlla gli URL di destinazione effettivi prima di utilizzarli.

Se non hai accesso alle piattaforme di annunci, controlla gli URL di destinazione nel set di dati web. Puoi anche esaminare i seguenti campi di ricerca di contenuti multimediali a pagamento:

* Ricerca account Google Ads: `additionalDetails` voci denominate `google_ads_tracking_url_template` e `google_ads_final_url_suffix`.
* Ricerca annunci Meta: `paidMedia.adDetails.creative.paidMediaCreative.destinationURL`.

Le macro negli URL di destinazione memorizzati possono essere codificate in percentuale. Convalida gli ID espansi negli eventi effettivi del sito web anziché presumere che un URL memorizzato rappresenti l’URL di destinazione finale.

>[!IMPORTANT]
>
>I nomi delle campagne, ad esempio `utm_campaign=fall_sale`, non corrispondono agli ID campagna. Unisciti solo a livelli che contengono ID effettivi. Se gli ID sono assenti, collabora con il team per le operazioni sugli annunci per aggiornare i tag per il traffico futuro; questa configurazione non può ricostruire gli ID mancanti per le visite storiche.

### Punto di partenza

Apri la visualizzazione dati che intendi utilizzare ed esamina i componenti per determinare il punto iniziale.

| | Punto di partenza | Configurazione esistente | Passaggi da seguire |
|---|---|---|---|
| A | Content Analytics con web o mobile e paid media | [Componenti e set di dati multimediali a pagamento](/help/content-analytics/config/paid-media.md), nonché set di dati di ricerca e di eventi di Content Analytics. | Se necessario, aggiungi il set di dati dell’evento del sito web, quindi configura i campi derivati dal web e i gruppi di reporting. |
| B | Content Analytics con solo supporti a pagamento | [Componenti e set di dati multimediali a pagamento](/help/content-analytics/config/paid-media.md); possono essere presenti anche set di dati di ricerca di contenuto condiviso. | Aggiungi il set di dati dell’evento del sito web, quindi configura i campi derivati dal web e i gruppi di reporting. |
| C | Supporti a pagamento senza provisioning Content Analytics | I set di dati di file multimediali a pagamento esistono in Experience Platform, ma la connessione e la visualizzazione dati non contengono la configurazione di file multimediali a pagamento. | Aggiungi il sito web e i set di dati per contenuti multimediali a pagamento, quindi crea i componenti per contenuti multimediali a pagamento e web. |
| D | Content Analytics senza supporti a pagamento | Solo componenti di Content Analytics. | Abilita il canale a pagamento nella configurazione Content Analytics, quindi segui il percorso di configurazione esistente. |

Non rimuovere o modificare i set di dati o i componenti di sola lettura di cui è stato eseguito il provisioning quando si estende una connessione gestita da Content Analytics.

## Raccogli eventi comportamentali del sito web

Ignora la creazione di schemi, set di dati e flussi di dati se il sito web invia già gli eventi richiesti a un set di dati utilizzato in Customer Journey Analytics. Conferma che `web.webPageDetails.URL` include la stringa di query della pagina di destinazione.

### Creare schema e set di dati

1. In Experience Platform, seleziona la sandbox di destinazione.
1. Vai a **[!UICONTROL Gestione dati]** > **[!UICONTROL Schemi]**, quindi seleziona **[!UICONTROL Crea schema]**.
1. Scegliere **[!UICONTROL Manuale]** e la classe `XDM ExperienceEvent`.
1. Denomina lo schema, ad esempio `Web Behavioral Events`.
1. Aggiungi i gruppi di campi necessari per l’implementazione.

   | Gruppo di campi | Dati richiesti |
   |---|---|
   | AEP Web SDK ExperienceEvent | URL della pagina, visualizzazioni di pagina, referrer e altro contesto web. |
   | Dettagli Commerce | Numero di acquisti, valore dell’ordine, valuta, ID acquisto e dettagli del prodotto. |
   | Dettagli di marketing della campagna, facoltativo | I codici di tracciamento se l’implementazione li acquisisce separatamente. |
   | IdentityMap, se non già presente | L’identificatore della persona, ad esempio ECID. |

1. Salva lo schema. Per questo caso d’uso di reporting non è necessaria l’abilitazione del profilo.
1. Vai a **[!UICONTROL Gestione dati]** > **[!UICONTROL Set di dati]** > **[!UICONTROL Crea set di dati]** > **[!UICONTROL Crea set di dati dallo schema]**.
1. Selezionare lo schema e creare un set di dati denominato, ad esempio `Web Behavioral Events`. Lascia **[!UICONTROL Profilo]** disabilitato a meno che non sia richiesto da un altro caso d&#39;uso.

### Configurare lo stream di dati e il Web SDK

1. Vai a **[!UICONTROL Raccolta dati]** > **[!UICONTROL Flussi dati]** > **[!UICONTROL Nuovo flusso dati]**.
1. Denomina lo stream di dati e seleziona lo schema evento come schema di mappatura.
1. Salva, quindi seleziona **[!UICONTROL Aggiungi servizio]** > **[!UICONTROL Adobe Experience Platform]**.
1. Seleziona la sandbox e il set di dati evento, quindi **[!UICONTROL Salva]**.
1. Utilizza l&#39;ID dello stream di dati per configurare [Experience Platform Web SDK](https://experienceleague.adobe.com/it/docs/experience-platform/collection/js/js-overview).

Acquisisci quanto segue:

* Acquisire una visualizzazione di pagina in ogni pagina, con l&#39;URL completo in `web.webPageDetails.URL` e `web.webPageDetails.pageViews.value` impostato su `1`.
* Acquista eventi con `commerce.purchases.value` impostato su `1`, più `commerce.order.priceTotal`, `commerce.order.currencyCode` e `commerce.order.purchaseID`.
* Un identificatore di persona adatto alla tua connessione Customer Journey Analytics.

Non è necessario analizzare i parametri UTM nel codice del sito Web. I campi derivati in questa guida analizzano gli URL al momento del reporting. Se l’implementazione acquisisce già gli ID in campi dedicati, utilizza invece tali campi.

### Verificare l’acquisizione

Controlla l’attività del set di dati per la corretta acquisizione. In Query Service, eseguire la query seguente, sostituendo `web_behavioral_events` con il nome della tabella SQL del set di dati:

```sql
SELECT timestamp, eventType, web.webPageDetails.URL
FROM web_behavioral_events
WHERE web.webPageDetails.URL RLIKE '[?&](campaign_id|utm_campaign|s_kwcid)='
ORDER BY timestamp DESC
LIMIT 20;
```

Verificare che gli URL restituiti contengano ID di rete espansi. Se esiste del traffico a pagamento ma la query non restituisce righe, controlla gli URL di destinazione recenti e adatta il modello del parametro ai tag.

## Configurare la connessione

Per acquisire il set di dati dell’evento web in Customer Journey Analytics, devi aggiungere il set di dati alla connessione pertinente. In questo modo, gli eventi comportamentali web saranno disponibili insieme ai set di dati a pagamento per l’analisi.

### Aggiungi il set di dati dell’evento del sito web

1. In Customer Journey Analytics, vai a **[!UICONTROL Gestione dati]** > **[!UICONTROL Connessioni]**.
1. Modifica la connessione che contiene i set di dati per contenuti multimediali a pagamento.
1. Seleziona **[!UICONTROL Aggiungi set di dati]** e scegli il set di dati dell&#39;evento del sito Web.
1. Configura il set di dati:

   | Impostazione | Valore |
   |---|---|
   | ID persona | `identityMap` con lo spazio dei nomi ECID o con il campo ID persona dell&#39;implementazione. |
   | Marca temporale | `timestamp` |
   | Tipo di origine dati | Dati web |
   | Importa tutti i nuovi dati | Abilitata |
   | Retrocompila tutti i dati esistenti | Abilitato per il periodo storico necessario. |

1. Aggiungi il set di dati e salva la connessione.

### Aggiungi set di dati per file multimediali a pagamento se non sono già configurati

>[!IMPORTANT]
>
>Ignora questa sezione per le connessioni in cui Content Analytics gestisce i set di dati di file multimediali a pagamento.


Aggiungi almeno il riepilogo degli annunci multimediali a pagamento e i set di dati Paid Media Account, Paid Media Campaign, Paid Media AdGroup e Paid Media Ad Lookup.

| Set di dati | Tipo | Configurazione chiave |
|---|---|---|
| Riepilogo annunci multimediali a pagamento | Riepilogo | Utilizza la configurazione della marca temporale giornaliera dello schema; abilita l’importazione di nuovi dati e la retrocompilazione richiesta. |
| Ricerca account di file multimediali a pagamento | Ricerca | Chiave: `paidMedia.accountGUID`; campo corrispondente nel riepilogo annunci: `paidMedia.accountGUID`. |
| Ricerca campagna media a pagamento | Ricerca | Chiave: `paidMedia.campaignGUID`; campo corrispondente nel riepilogo annunci: `paidMedia.campaignGUID`. |
| Ricerca AdGroup di contenuti multimediali a pagamento | Ricerca | Chiave: `paidMedia.adGroupGUID`; campo corrispondente nel riepilogo annunci: `paidMedia.adGroupGUID`. |
| Ricerca annunci multimediali a pagamento | Ricerca | Chiave: `paidMedia.adGUID`; campo corrispondente nel riepilogo annunci: `paidMedia.adGUID`. |

Prima di salvare, verifica che l’editor connessioni esprima i campi corrispondenti previsti. L’arricchimento dei nomi più avanti in questa guida utilizza esplicitamente le regole di ricerca dei campi derivate.

Aggiungi altri set di dati di riepilogo disponibili solo quando ti servono le relative suddivisioni, ad esempio geografia, dati demografici, posizionamento o prestazioni.

## Configurare la visualizzazione dati

Apri **[!UICONTROL Gestione dati]** > **[!UICONTROL Visualizzazioni dati]** e seleziona la tua visualizzazione dati. Se necessario, crea una visualizzazione dati utilizzando la connessione configurata.

Per una nuova visualizzazione dati, utilizza GMT per allineare gli eventi del sito web con i giorni UTC degli elementi multimediali a pagamento e mantenere il timeout di sessione predefinito di 30 minuti, a meno che i requisiti di reporting non siano diversi. La modifica del fuso orario di una visualizzazione dati esistente influisce sugli altri rapporti; valuta tale impatto prima di modificarlo.

### Aggiungi metriche per file multimediali a pagamento se non è già configurato

Ignora questo passaggio se queste metriche o dimensioni esistono già. Aggiungi i seguenti campi da **[!UICONTROL Riepilogo annunci multimediali a pagamento]**:

| Nome componente | Campo schema | Formato |
|---|---|---|
| **Metriche** | | |
| Impression \| Riepilogo annuncio | `paidMedia.metrics.impressions` | Decimale |
| Clic \| Riepilogo annuncio | `paidMedia.metrics.clicks` | Decimale |
| Spesa \| Riepilogo annuncio | `paidMedia.metrics.spend` | Valuta |
| Conversioni \| Riepilogo annuncio | `paidMedia.metrics.conversions` | Decimale |
| Valore di conversione \| Riepilogo annuncio | `paidMedia.metrics.conversionValue` | Valuta |
| **Dimensioni** | | |
| Ad network | `paidMedia.adNetwork` | Stringa |
| GUID account | `paidMedia.accountGUID` | Stringa |
| GUID campagna | `paidMedia.campaignGUID` | Stringa |
| GUID gruppo di annunci | `paidMedia.adGroupGUID` | Stringa |
| GUID annuncio | `paidMedia.adGUID` | Stringa |

La formattazione della valuta non esegue la quadratura di valute di origine diverse. Confermare la base della valuta prima di confrontare spese e ricavi.

Utilizzare i campi derivati per creare nomi descrittivi per la dimensione GUID. Utilizzare una regola [Ricerca](/help/data-views/derived-fields/derived-fields.md#lookup) per applicare un nome descrittivo per la dimensione GUID.  Ad esempio: cerca **[!UICONTROL paidMedia.accountGUID (riepilogo annunci multimediali a pagamento)]** utilizzando il set di dati di ricerca **[!UICONTROL Ricerca account multimediali a pagamento]** con chiave `paidMedia.accountGUID` e valore corrispondenti da restituire: `paidMedia.accountDetails.accountName`.


### Crea il campo derivato dalla rete web

Selezionare **[!UICONTROL Crea campo derivato]** e denominare il campo `PM Network (Web)`. Tutte le [regole di analisi URL](/help/data-views/derived-fields/derived-fields.md#url-parse) seguenti leggono il campo `web.webPageDetails.URL` del set di dati del sito Web, qui denominato URL pagina.

Aggiungi regole in questo ordine:

| Regola | Funzione | Configurazione |
|---|---|---|
| 1 | [Analisi URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | URL della pagina. Ottieni il valore della stringa di query per `utm_source`. |
| 2 | [Analisi URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | URL della pagina. Ottieni il valore della stringa di query per `s_kwcid`. |
| 3 | [Analisi URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | URL della pagina. Ottieni il valore della stringa di query per `gclid`. |
| 4 | [Analisi URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | URL della pagina. Ottieni il valore della stringa di query per `fbclid`. |
| 5 | [Caso In Cui](/help/data-views/derived-fields/derived-fields.md#case-when) | Applica le condizioni seguenti. |

Configura la regola [Case When](/help/data-views/derived-fields/derived-fields.md#case-when) finale:

1. Se è impostata la regola 2 o la regola 3, restituire `google_ads`.
1. In caso contrario, se la regola 4 è impostata o la regola 1 è uguale a `fb`, `facebook`, `ig`, `instagram` o `meta`, restituire `meta`.
1. In caso contrario, se la regola 1 è uguale a `google`, verrà restituito `google_ads`.
1. Aggiungere mappature per altre reti solo dopo aver confermato i relativi valori in `paidMedia.adNetwork`.
1. In caso contrario, non viene restituito alcun valore.

Per immettere un output fisso, aprire il selettore dei valori, selezionare **[!UICONTROL Valore stringa personalizzato]** e immettere la stringa.

Queste regole di classificazione sono basate sui tag, non sulla prova che una visita provenga da un annuncio a pagamento. Ad esempio, un parametro di origine può essere visualizzato anche sui collegamenti non a pagamento. Adatta le condizioni alle convenzioni di assegnazione tag prima di utilizzare il campo come classificatore di traffico a pagamento.

### Creare i campi derivati dell’ID web

Crea un campo derivato per livello di reporting. La seguente struttura gestisce i tre modelli di assegnazione tag descritti in precedenza:

| Regola | Funzione | Configurazione |
|---|---|---|
| 1 | [Analisi URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | Leggi il parametro Meta specifico del livello dall’URL della pagina. |
| 2 | [Analisi URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | Leggi il parametro UTM specifico del livello dall’URL della pagina. |
| 3 | [Analisi URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | Leggi `s_kwcid` dall&#39;URL della pagina. |
| 4 | [Sostituzione Regex](/help/data-views/derived-fields/derived-fields.md#regex-replace) | Applica l&#39;espressione specifica del livello alla regola 3; output `$1`. |
| 5 | [Caso In Cui](/help/data-views/derived-fields/derived-fields.md#case-when) | Se è impostata la regola 3, restituire la regola 4; altrimenti, se è impostata la regola 1, restituire la regola 1; in caso contrario, restituire la regola 2. |

Utilizza i seguenti valori:

| Campo derivato | Parametro Meta | Parametro UTM | Espressione Regex |
|---|---|---|---|
| **ID campagna PM (Web)** | `campaign_id` | `utm_campaign` | `^.*!([^!]*)![^!]*$` |
| **PM ID gruppo annunci (Web)** | `adset_id` | `utm_term` | `^.*!([^!]*)$` |
| **PM ID annuncio (Web)** | `ad_id` | `utm_content` | `^[^!]*![^!]*![^!]*!([^!]*)!.*$` |

Nella regola [Case When](/help/data-views/derived-fields/derived-fields.md#case-when) finale, selezionare gli output della regola precedente dal selettore di valori anziché immetterli come stringhe letterali.

L&#39;espressione della campagna estrae il valore `s_kwcid` dal secondo all&#39;ultimo, l&#39;espressione del gruppo di annunci estrae l&#39;ultimo valore e l&#39;espressione dell&#39;annuncio estrae il quarto valore. Queste posizioni dipendono dal layout esatto mostrato in precedenza.

Utilizza **[!UICONTROL Output finale]** per verificare che i risultati corrispondano agli ID nel riepilogo degli annunci multimediali a pagamento. Non mantenere un ramo di analisi `s_kwcid` se gli URL utilizzano un layout diverso. Se gli URL utilizzano solo parametri UTM, ometti le regole non utilizzate e aggiorna di conseguenza i riferimenti alle regole successivi.

Ogni campo derivato supporta fino a cinque [regole di analisi URL](/help/data-views/derived-fields/derived-fields.md#url-parse) e una [regola Regex Replace](/help/data-views/derived-fields/derived-fields.md#regex-replace). Mantieni un ID per campo derivato.

### Creare la metrica degli sbarchi a pagamento

Creare un campo derivato denominato `Paid Media Landings (Web)` utilizzando `PM Campaign ID (Web)` come input.

Il generatore espande le regole del campo di input nel nuovo campo. Dopo tali regole, aggiungere una regola [Case When](/help/data-views/derived-fields/derived-fields.md#case-when) che restituisce il valore numerico personalizzato `1` quando è impostato l&#39;output dell&#39;ID campagna. In caso contrario, nessun valore. Aggiungi il risultato come metrica.

Questa metrica conta gli eventi con un ID campagna. Questa metrica rappresenta gli atterraggi solo quando l’implementazione invia l’URL recante l’ID sull’evento di destinazione anziché su eventi ripetuti o non correlati.

>[!NOTE]
>
>Le regole dei campi derivati espansi sono copie. Se modifichi un campo ID, controlla e aggiorna anche i campi di destinazione e nome corrispondenti. Se hai omesso le regole di analisi, fai riferimento alla regola dell’ID finale effettivo anziché presumere che si tratti della regola 5.

### Aggiungere campi nome Web facoltativi

Per creare un report per nome, crea i seguenti campi derivati con una [regola di ricerca](/help/data-views/derived-fields/derived-fields.md#lookup) dopo le regole dell&#39;ID Web espanso:

| Campo derivato | Input | Set di dati di ricerca | Campo corrispondente | Campo restituito |
|---|---|---|---|---|
| Nome campagna PM (Web) | Output finale dell&#39;ID campagna PM (Web) | Ricerca campagna media a pagamento | `paidMedia.campaignID` | `paidMedia.metadata.name` |
| Nome gruppo di annunci PM (Web) | Output finale dell&#39;ID gruppo di annunci PM (Web) | Ricerca AdGroup di contenuti multimediali a pagamento | `paidMedia.adGroupID` | `paidMedia.metadata.name` |
| Nome annuncio PM (Web) | Output finale dell&#39;ID annuncio PM (Web) | Ricerca annunci multimediali a pagamento | `paidMedia.adID` | `paidMedia.metadata.name` |

Seleziona la regola ID finale come campo a cui applicare la ricerca. Verifica i nomi nell’anteprima di output finale prima di aggiungere i campi come dimensioni. Se il campo corrispondente richiesto non è disponibile, utilizza la generazione rapporti basati su ID.

I nomi vengono associati come testo. Utilizza le dimensioni ID quando entità diverse condividono un nome.

### Aggiungere componenti web e configurare l’attribuzione

Aggiungi l’ID web e i campi derivati dalla rete come dimensioni. Aggiungi i campi nome facoltativi se li hai creati. Mantieni le impostazioni predefinite dei componenti in modo che corrispondano alle dimensioni di riepilogo aggiunte ai loro gruppi.

Conferma che la visualizzazione dati includa i componenti web necessari:

| Componente | Tipo | Campo schema |
|---|---|---|
| URL della pagina | Dimensione | `web.webPageDetails.URL` |
| Nome pagina | Dimensione | `web.webPageDetails.name` |
| URL referrer | Dimensione | `web.webReferrer.URL` |
| Tipo evento | Dimensione | `eventType` |
| SKU prodotto | Dimensione | `productListItems.SKU` |
| Nome del prodotto | Dimensione | `productListItems.name` |
| Page Views | Metrica | `web.webPageDetails.pageViews.value` |
| Aggiungi ai carrello | Metrica | `commerce.productListAdds.value` |
| Ordini | Metrica | `commerce.purchases.value` |
| Ricavi | Metrica | `commerce.order.priceTotal` |

Aggiungi il campo derivato delle destinazioni a pagamento come metrica, quindi configura metriche separate per ordini e ricavi:

1. Duplica **[!UICONTROL Ordini]** e denomina la copia `Orders (Web)`. Se **[!UICONTROL Ordini]** non esiste, aggiungi direttamente `commerce.purchases.value`.
1. Duplica **[!UICONTROL Ricavo]** e denomina la copia `Revenue (Web)`. Se **[!UICONTROL Revenue]** non esiste, aggiungere direttamente `commerce.order.priceTotal`.
1. Formatta **[!UICONTROL Ordini (Web)]** come decimale con zero cifre decimali e **[!UICONTROL Ricavi (Web)]** come valuta.
1. Per entrambe le metriche, apri **[!UICONTROL Attribuzione]** e abilita **[!UICONTROL Ignora attribuzione predefinita]**.
1. Selezionare il modello **[!UICONTROL Ultimo contatto]** e il contenitore **[!UICONTROL Sessione]**.

Mantieni invariate le metriche **[!UICONTROL Ordini]** e **[!UICONTROL Ricavi]** originali per mantenere i rapporti esistenti. Per questa impostazione è necessario abilitare esplicitamente l&#39;override, anche quando le impostazioni predefinite visualizzate sembrano corrispondere.

Per il credito di conversione tra visite di ritorno, considera invece un contenitore **[!UICONTROL Persona]** e un intervallo di lookback appropriato. Vedi il [caso di utilizzo dei dati di riepilogo](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-usecases/data-views/summary-data).

Utilizza l’attribuzione delle metriche invece di aggiungere persistenza alle dimensioni dell’ID web. Per evitare di gonfiare i conteggi interpretati come atterraggi, non mantenere gli ID per gli eventi successivi, in quanto ciò cambia gli eventi che compaiono nelle righe della campagna.

### Creare dimensioni di join lato riepilogo

Aggiungi dimensioni separate dal Riepilogo annunci a pagamento per i Web join:

| Nome componente | Campo schema |
|---|---|
| Rete di annunci (aggiunta) | `paidMedia.adNetwork` |
| ID campagna (rete) | `paidMedia.campaignID` |
| ID gruppo di annunci (rete) | `paidMedia.adGroupID` |
| ID annuncio (rete) | `paidMedia.adID` |

Non modificare o duplicare componenti multimediali a pagamento gestiti da modelli e di sola lettura. Crea i componenti separati qui sopra dai campi dello schema.

Se hai creato campi facoltativi per il nome Web, crea anche questi campi derivati dalla ricerca lato riepilogo:

| Nome componente | Input da riepilogo annunci | Set di dati di ricerca | Campo corrispondente | Campo restituito |
|---|---|---|---|---|
| Nome campagna (aggiunto) | `paidMedia.campaignGUID` | Ricerca campagna media a pagamento | `paidMedia.campaignGUID` | `paidMedia.metadata.name` |
| Nome gruppo di annunci (aggiunto) | `paidMedia.adGroupGUID` | Ricerca AdGroup di contenuti multimediali a pagamento | `paidMedia.adGroupGUID` | `paidMedia.metadata.name` |
| Nome annuncio (aggiunto) | `paidMedia.adGUID` | Ricerca annunci multimediali a pagamento | `paidMedia.adGUID` | `paidMedia.metadata.name` |

Utilizza un GUID dal set di dati di riepilogo come input di ogni ricerca. Una dimensione presa direttamente da un set di dati di ricerca non soddisfa i requisiti per una dimensione di riepilogo in un gruppo di dati di riepilogo.

### Creare gruppi di dati di riepilogo

Crea ogni gruppo sulla dimensione web che intendi utilizzare nei rapporti. Aggiungi la dimensione di riepilogo corrispondente e nascondi il membro aggiunto nel reporting.

| Dimensione web: crea il gruppo qui | Dimensione di riepilogo: aggiungi come membro nascosto |
|---|---|
| Rete PM (Web) | Rete di annunci (aggiunta) |
| ID campagna PM (Web) | ID campagna (rete) |
| ID gruppo di annunci PM (Web) | ID gruppo di annunci (rete) |
| ID annuncio PM (Web) | ID annuncio (rete) |
| Nome campagna PM (Web), facoltativo | Nome campagna (aggiunto) |
| Nome gruppo di annunci PM (Web), facoltativo | Nome gruppo di annunci (aggiunto) |
| Nome annuncio PM (Web), facoltativo | Nome annuncio (aggiunto) |

Per ogni riga:

1. Seleziona la dimensione web.
1. Apri **[!UICONTROL Summary Data Group]** e abilita **[!UICONTROL Create grouping]**.
1. Aggiungi la dimensione di riepilogo.
1. Abilita **[!UICONTROL Nascondi nel reporting]** per il membro di riepilogo aggiunto. Mantieni visibile la dimensione web.
1. Verificare che le impostazioni del componente, incluse le regole in minuscolo, sottostringa e inclusione/esclusione, corrispondano tra i membri.

Ogni gruppo supporta fino a 10 dimensioni. Per includere le metriche di un altro set di dati di riepilogo, aggiungere la dimensione di riepilogo equivalente del set di dati allo stesso gruppo di un membro nascosto.

>[!IMPORTANT]
>
>Utilizza la dimensione web come dimensione di reporting e crea il gruppo su tale dimensione. La disposizione inversa può mostrare le metriche di riepilogo senza le metriche web corrispondenti.

Salva la visualizzazione dati.

### Creare metriche calcolate

In Workspace, vai a **[!UICONTROL Componenti]** > **[!UICONTROL Metriche calcolate]** e crea le metriche seguenti utilizzando la visualizzazione dati configurata:

| Nome | Definizione | Formato |
|---|---|---|
| Tasso di destinazione | Destinazioni di contenuti multimediali a pagamento (Web) / Clic \| Riepilogo annuncio | Percentuale |
| Tasso di conversione web | Ordini (Web) / Destinazioni di media a pagamento (Web) | Percentuale |
| WEB ROAS | Ricavi (Web) / Spesa \| Riepilogo annuncio | Decimale, due posizioni |
| Costo per ordine Web | Spesa \| Riepilogo annuncio / Ordini (Web) | Valuta |
| Divario tra rete e conversione Web | Conversioni \| Riepilogo annunci - Ordini (Web) | Decimale, zero posizioni |

Rivedi le righe con denominatori zero prima di interpretare le metriche del rapporto. Un gap di conversione tra rete e web non indica di per sé un errore: le due origini possono differire nelle finestre di attribuzione, misurazione e reporting.

## Creare e convalidare il rapporto

1. Crea un progetto Workspace utilizzando la visualizzazione dati configurata.
1. Scegli un intervallo di date con dati provenienti da entrambe le origini. Consenti ritardi di acquisizione di contenuti multimediali a pagamento; i dati di riepilogo possono ritardare gli eventi del sito web di un giorno.
1. Aggiungere una tabella a forma libera con **[!UICONTROL ID campagna PM (Web)]** come dimensione riga oppure **[!UICONTROL Nome campagna PM (Web)]** se sono stati configurati gruppi di nomi.
1. Aggiungi **[!UICONTROL impression | Riepilogo annuncio]**, **[!UICONTROL Clic | Riepilogo annuncio]**, **[!UICONTROL Spesa | Riepilogo annuncio]**, **[!UICONTROL Conversioni | Riepilogo annuncio]**, **[!UICONTROL Destinazioni contenuti multimediali a pagamento | Riepilogo annunci]**, **[!UICONTROL Ordini (Web)]**, **[!UICONTROL Ricavi (Web)]** e le metriche calcolate.
1. Suddividi una riga della campagna in base al gruppo di annunci web e alle dimensioni dell’annuncio. Conferma che le metriche di riepilogo e web vengano compilate a ogni livello configurato.
1. Aggiungere una seconda tabella utilizzando **[!UICONTROL PM Network (Web)]** per esaminare i totali a livello di rete e la riga senza valore.

   ![Progetto area di lavoro dati Web e supporti a pagamento](./assets/paid-media-and-web-data-workspace.png)

   ![Nessun dato per progetto area di lavoro dati Web e supporti a pagamento](./assets/paid-media-and-web-data-workspace-no-value.png)

Prima di condividere il rapporto, verifica quanto segue:

* Gli ID dell’evento di destinazione corrispondono agli ID di riepilogo degli annunci multimediali a pagamento.
* Le metriche dei contenuti multimediali a pagamento e le metriche web si popolano sulle stesse righe.
* Gli ordini e i ricavi ricevono la sessione prevista o l’attribuzione della persona.
* Le righe prive di valore sono comprese. Possono contenere dati di riepilogo senza corrispondenza o attività web senza identificatori di elementi multimediali a pagamento.
* Le differenze tra destinazione e clic sono coerenti con la configurazione della raccolta, la gestione del consenso e le finestre di reporting. Non esiste una percentuale di corrispondenza universale prevista.

### Risolvere i problemi di mancata corrispondenza

| Sintomo | Controllo e azioni correttive |
|---|---|
| Le metriche di riepilogo vengono compilate, ma tutte le metriche web sono pari a zero | Verifica che le righe utilizzino dimensioni web e che siano stati creati dei gruppi su tali dimensioni. Quindi, controlla gli URL di destinazione per individuare gli ID effettivi anziché i nomi. |
| Le metriche web si compilano, ma un livello di riepilogo è vuoto | Verifica che la dimensione di riepilogo del livello sia nel gruppo corrispondente e che esistano dati multimediali a pagamento corrispondenti per le date selezionate. |
| Nomi mancanti nelle righe web | Controlla l’input di ricerca e il campo corrispondente nell’anteprima dell’output finale. Se l’arricchimento dei nomi non è disponibile, utilizza i gruppi ID. |
| Gli ID Web contengono macro letterali o codificate | Chiedi al team delle operazioni sugli annunci di controllare l’URL di destinazione e conferma che la rete espanda le macro prima dell’arrivo. |
| Gli ID di Google Ads non corrispondono | Controllare il layout `s_kwcid` o i parametri UTM effettivi e aggiornare le regole di analisi. |
| I valori di rete sono suddivisi, ad esempio `facebook` e `meta` | Rendere l&#39;output del campo derivato dalla rete uguale esattamente a `paidMedia.adNetwork`. |
| Un ID viene visualizzato in righe separate | Verifica che le impostazioni corrispondano tra dimensioni raggruppate e controlla i valori stringa sottostanti. |
| L’attività del sito web sembra spostata di un giorno | Confronta il fuso orario della visualizzazione dati con i limiti del giorno di riepilogo UTC. |
| Gli ordini o i ricavi sono zero o inaspettatamente bassi nelle campagne | Abilita esplicitamente la sostituzione dell’attribuzione della metrica e ne conferma le impostazioni di modello, contenitore e lookback. |
| Gli sbarchi pagati sono inaspettatamente elevati | Conferma che solo gli eventi di destinazione siano associati al parametro della campagna conteggiato. Anche gli eventi portatori di ID ripetuti contribuiscono a questa metrica. |
| Le campagne distinte condividono una riga del nome | Utilizza i rapporti basati su ID per distinguere le entità che hanno nomi identici. |
