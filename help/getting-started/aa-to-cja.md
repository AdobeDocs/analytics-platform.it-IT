---
title: Evoluzione da Adobe Analytics
description: Passaggi per trasformare i dati di Adobe Analytics in dati di Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: a67c12a7b5244b7802eba2cbcbfdb320802d088b
workflow-type: tm+mt
source-wordcount: '1476'
ht-degree: 73%

---

# Evoluzione da Adobe Analytics

Man mano che la tua organizzazione inizia a utilizzare Customer Journey Analytics, segui questi passaggi per preparare i dati esistenti e capire le differenze principali tra queste due tecnologie. Questo articolo è destinato agli amministratori.

## Preparare i dati

Per passare facilmente a Customer Journey Analytics, è fondamentale preparare i dati di Adobe Analytics per garantirne l’integrità e la coerenza nella generazione dei rapporti.

### 1. Raccogliere le identità {#identities}

Per comprendere un percorso del cliente, l’aspetto forse più importante è sapere chi è il cliente in ogni fase. Ad Customer Journey Analytics, l’esistenza di un identificatore su tutti i canali e i dati corrispondenti consente di unire più origini all’interno del Customer Journey Analytics.
Alcuni esempi di identità sono un ID cliente, un ID account o un ID e-mail. Indipendentemente dall’identità (possono essere presenti anche più identità), considera quanto segue per ogni ID:

* L’ID esiste o può essere aggiunto a tutte le origini dati che desideri inserire nel Customer Journey Analytics
* L’ID viene popolato su ogni riga di dati.
* L’ID non contiene dati di identificazione personale. Applica l’hashing a qualsiasi elemento che potrebbe essere sensibile.
* L’ID utilizza lo stesso formato per tutte le origini (stessa lunghezza, stesso metodo di hashing, ecc.).

Nei set di dati come Adobe Analytics, è possibile che un’identità non esista su ogni riga di dati, ma esiste invece un’identità secondaria. In questo caso, è possibile utilizzare Analisi cross-channel (precedentemente nota come “unione basata sui campi”) per colmare il gap tra le righe quando un cliente è identificato solo dal proprio ECID e quando viene raccolta un’identità (ad esempio, quando un cliente si autentica). [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=it)

### 2. Allineare le variabili {#variables}

Il metodo più semplice per trasformare i dati di Adobe Analytics in dati di Customer Journey Analytics è quello di acquisire un [suite di rapporti globale](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=it) in Experienci Platform utilizzando [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it). Questo connettore mappa le variabili di Adobe Analytics direttamente su un set di dati e uno schema XDM in Experience Platform, che a sua volta può essere facilmente connesso a Customer Journey Analytics.

A seconda dell’implementazione, l’utilizzo di una suite di rapporti globale completa potrebbe non essere sempre fattibile. Se intendi portare in Customer Journey Analytics più suite di rapporti, puoi scegliere tra 2 approcci:

* Pensa per tempo ad allineare le variabili tra le diverse suite di rapporti. Ad esempio, nella suite di rapporti 1 la variabile eVar1 può fare riferimento a [!UICONTROL Page]. Nella suite di rapporti 2, la variabile eVar1 potrebbe invece fare riferimento a [!UICONTROL Internal Campaign]. Una volta introdotte nel Customer Journey Analytics, queste variabili si combineranno in un’unica dimensione eVar1, generando rapporti potenzialmente confusi e imprecisi.

* Utilizza la funzione [Preparazione dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) per mappare le variabili. Sebbene sia più facile se tutte le suite di rapporti utilizzano la stessa struttura di variabili, questo non sarà necessario se utilizzi la nuova funzione [Preparazione dati](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it#mapping) di Experience Platform. Consente infatti di fare riferimento a una variabile in base al suo valore mappato, a livello di flusso dei dati (o proprietà).

Se hai evitato di passare a una suite di rapporti globale a causa di problemi con [!UICONTROL Uniques Exceeded] o [!UICONTROL Low Traffic], sappiate che il Customer Journey Analytics non ha [limiti di cardinalità su una dimensione](/help/components/dimensions/high-cardinality.md). Permette di visualizzare e conteggiare qualsiasi valore univoco.

Qui puoi trovare un caso di utilizzo sulla [combinazione di suite di rapporti con schemi diversi](/help/use-cases/aa-data/combine-report-suites.md).

### 3. (Ri)Configurare i canali di marketing {#marketing-channels}

Le impostazioni tradizionali del canale di marketing di Adobe Analytics non funzionano allo stesso modo nel Customer Journey Analytics. Questo per due motivi:

* Il livello di elaborazione dei dati Adobe Analytics acquisiti in Adobe Experience Platform e

* la natura di Customer Journey Analytics in termini di momento del rapporto

Adobe ha pubblicato [best practice aggiornate per l’implementazione del canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=it). Questi consigli aggiornati consentono di sfruttare al massimo le funzionalità già presenti in Adobe Analytics con Attribution IQ. Inoltre ti saranno utili per prepararti per una transizione di successo a Customer Journey Analytics.

Con l&#39;introduzione di [Campi derivati](../data-views/derived-fields/derived-fields.md) come parte delle visualizzazioni dati di Customer Journey Analytics, i canali di marketing sono supportati anche in modo non distruttivo e retroattivo utilizzando [Modello di funzione Canale di marketing](../data-views/derived-fields/derived-fields.md#function-templates).

### 4. Decidere se utilizzare il connettore di origine di Analytics o gli SDK Experienci Platform {#connector-vs-sdk}

I clienti di Adobe Analytics possono facilmente sfruttare le loro suite di rapporti in Adobe Experience Platform e nel Customer Journey Analytics utilizzando il connettore di origine di Analytics. Per informazioni sull’utilizzo del connettore di origine di Analytics, consulta la guida rapida su come [acquisire dati da Adobe Analytics e utilizzarli in Customer Journey Analytics](../data-ingestion/analytics.md). Per ulteriori informazioni, vedi anche [Creare una connessione origine Adobe Analytics nell’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it).

Mentre la raccolta dati di [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it) si evolve, probabilmente eseguirai la migrazione ad [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=it) o [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=it) con la rete Edge di Adobe Experience Platform. Sebbene un’implementazione tipica degli SDK invii dati ad Adobe Analytics, si presenta una nuova opportunità per l’invio diretto dei dati a Adobe Experience Platform. Possono quindi essere acquisiti in Customer Journey Analytics, mantenendo al tempo stesso i dati inviati ad Adobe Analytics.

Questo metodo estende notevolmente le possibilità di raccolta dei dati: non esiste più un limite al numero di campi né la necessità di mappare gli elementi dati su prop, eVar ed eventi come in Analytics. Puoi utilizzare un numero illimitato di elementi schema di tipi diversi e rappresentarli in più modi utilizzando Customer Journey Analytics [Visualizzazioni dati](/help/data-views/data-views.md). Quando i dati vengono inviati direttamente ad Adobe Experience Platform, diventano disponibili più velocemente in quanto viene rimosso il tempo di elaborazione dei dati tramite Adobe Analytics.

**Vantaggi dell’utilizzo degli SDK di Experience Platform:**

* Schema flessibile per definire i campi necessari
* Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)
* Nessun limite di carattere (100 caratteri per prop)
* Disponibilità più rapida dei dati in Adobe Experience Platform per [casi d’uso di personalizzazione in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=it)
* [ID dispositivo di prime parti](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=it) per una maggiore precisione nell’identificazione dei visitatori

**Limitazioni dell’utilizzo degli SDK di Experience Platform**

Le funzioni o i componenti seguenti di Adobe Analytics non sono supportati:

* Filtro bot
* Misurazione di file multimediali in streaming
* Livestream o trigger di Livestream

## Prepararsi per le differenze fondamentali

### Acquisire dimestichezza con l’elaborazione al momento del reporting {#report-time}

Il reporting in Adobe Analytics si basa su una quantità significativa di pre-elaborazione dei dati per generare risultati come la persistenza visibile nelle [!UICONTROL eVars]. Al contrario, Customer Journey Analytics esegue tali calcoli in fase di esecuzione dei rapporti.

[!UICONTROL Report time processing] apre la possibilità di applicare impostazioni retroattive e creare più versioni di persistenza delle variabili senza dover modificare la modalità di raccolta dei dati sottostanti.

Questo cambiamento comporterà alcune differenze nel modo in cui i dati vengono inseriti nei rapporti, specialmente per tutte le variabili che possono avere una lunga finestra di scadenza. Puoi iniziare valutando in che modo l’elaborazione al momento della generazione del rapporto può influire sui rapporti utilizzando una [suite di rapporti virtuale](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=it).

### Identificare i segmenti e le metriche calcolate più importanti {#segments-calcmetrics}

Segmenti Adobe Analytics (denominati [!UICONTROL filters] in Customer Journey Analytics) e le metriche calcolate non sono compatibili con Customer Journey Analytics. In molti casi, questi componenti possono essere ricreati in Customer Journey Analytics utilizzando i nuovi schemi e i dati disponibili.

Per rendere la transizione il più semplice possibile per gli utenti che passano da un sistema all’altro, pianifica in anticipo eseguendo le seguenti operazioni:

1. Identifica i componenti più critici.

2. Documenta le loro definizioni.

3. Identificazione dei campi necessari nei dati per replicarli nel Customer Journey Analytics come [Filtri](/help/components/filters/filters-overview.md) e [Metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md).

Ecco un paio di video per guidarti:

* [Spostare i segmenti di Adobe Analytics in Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=it)

* [Spostare le metriche calcolate da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=it)

### Altre considerazioni

* Grazie alla potenza delle visualizzazioni dati del Customer Journey Analytics, hai a disposizione molta più flessibilità nella definizione di metriche e dimensioni all’interno del Customer Journey Analytics. Ad esempio, puoi utilizzare il valore di una dimensione come definizione di una metrica. [Ulteriori informazioni](/help/use-cases/data-views/data-views-usecases.md)

* Se hai definito un calendario personalizzato in Adobe Analytics, avrai un calendario [funzionalità di calendario personalizzato](/help/components/date-ranges/custom-date-ranges.md) entro il Customer Journey Analytics. È necessario assicurarsi che il calendario sia definito correttamente.

* In Customer Journey Analytics, puoi definire un valore di timeout personalizzato per visita o sessione e una metrica che avvierà una nuova sessione. Puoi creare visualizzazioni dati con diverse definizioni di sessione per ottenere più informazioni di quanto non fosse possibile in Adobe Analytics. Questa funzionalità può risultare particolarmente utile per i set di dati mobili.

* Considera la possibilità di fornire ai tuoi utenti un dizionario di dati, oppure includi nel documento SDR (Solution Design Reference, riferimento per la progettazione della soluzione) il nome dei campi di Experience Platform per gli elementi dello schema.

## Passaggi successivi

Dopo il passaggio al Customer Journey Analytics, se noti eventuali discrepanze di dati, puoi confrontare i dati Adobe Analytics originali con quelli di Adobe Analytics attualmente in Customer Journey Analytics. [Ulteriori informazioni](/help/troubleshooting/compare.md)
