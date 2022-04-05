---
title: L'evoluzione di Adobe Analytics nel Customer Journey Analytics
description: Passaggi per trasformare i dati di Adobe Analytics in dati di Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 0fe1d1ce880db04f52f9828f97f61925da7b4028
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 81%

---

# L&#39;evoluzione di Adobe Analytics nel Customer Journey Analytics

Man mano che la tua organizzazione si evolve per utilizzare il Customer Journey Analytics, esplora questi passaggi per preparare i tuoi dati e prendere coscienza delle differenze critiche tra le due tecnologie. Questo articolo è destinato a un pubblico amministratore.

## Preparare i dati

Per passare facilmente a Customer Journey Analytics, è fondamentale preparare i dati di Adobe Analytics per garantirne l’integrità e la coerenza nella generazione dei rapporti.

### 1. Raccogliere le identità

Per comprendere un percorso del cliente, l’aspetto forse più importante è sapere chi è il cliente in ogni fase. Per Customer Journey Analytics, l’esistenza di un identificatore su tutti i canali e i dati corrispondenti consente di unire più origini in CJA.
Alcuni esempi di identità sono un ID cliente, un ID account o un ID e-mail. Indipendentemente dall’identità (possono essere presenti anche più identità), considera quanto segue per ogni ID:

* L’ID esiste o può essere aggiunto a tutte le origini dati che desideri inserire in CJA.
* L’ID viene popolato su ogni riga di dati.
* L&#39;ID non contiene dati di identificazione personale. Applica l’hashing a qualsiasi elemento che potrebbe essere sensibile.
* L’ID utilizza lo stesso formato per tutte le origini (stessa lunghezza, stesso metodo di hashing, ecc.)

Nei set di dati come Adobe Analytics, è possibile che un’identità non esista su ogni riga di dati, ma esiste invece un’identità secondaria. In questo caso, è possibile utilizzare l’analisi cross-channel (precedentemente nota come “unione basata sui campi”) per colmare il gap tra le righe quando un cliente è identificato solo dal proprio ECID e quando viene raccolta un’identità (ad esempio, quando un cliente si autentica). [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=it)

### 2. Allineare le variabili

Il metodo più semplice per trasformare i dati di Adobe Analytics in dati di Customer Journey Analytics è quello di acquisire un [suite di rapporti globale](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=it) in Experience Platform utilizzando [Connettore sorgente Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it). Questo connettore mappa le variabili Adobe Analytics direttamente in uno schema e un set di dati XDM in Experience Platform, che a sua volta può essere facilmente collegato al Customer Journey Analytics.

A seconda dell’implementazione, l’utilizzo di una suite di rapporti globale completa potrebbe non essere sempre fattibile. Se intendi portare più suite di rapporti in Customer Journey Analytics, hai 2 opzioni:

* Pianifica in anticipo per allineare le variabili tra le suite di rapporti. Ad esempio, nella suite di rapporti 1 la variable eVar1 può fare riferimento a [!UICONTROL Page]. Nella suite di rapporti 2, la variabile eVar1 potrebbe invece fare riferimento a [!UICONTROL Internal Campaign]. Una volta introdotte in CJA, queste variabili si combineranno in un’unica dimensione eVar1, generando rapporti potenzialmente confusi e imprecisi.

* Utilizza la [Preparazione data](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) per mappare le variabili. Sebbene sia più facile se tutte le suite di rapporti utilizzano la stessa struttura di variabili comune, non è necessario se utilizzi il nuovo Experience Platform [Preparazione dei dati](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#mapping) funzionalità. Ti consente di fare riferimento a una variabile in base al suo valore mappato, che si trova a livello di datastream (o proprietà).

Se hai evitato di passare a una suite di rapporti globale a causa di problemi con [!UICONTROL Uniques Exceeded] o [!UICONTROL Low Traffic], tieni presente che CJA non prevede alcun [limite di cardinalità su una dimensione](/help/components/dimensions/high-cardinality.md). Permette di visualizzare e conteggiare qualsiasi valore univoco.

### 3. (Ri)Configurare i canali di marketing

Le impostazioni tradizionali del canale di marketing Adobe Analytics non funzionano nello stesso modo in CJA. Questo per due motivi:

* Il livello di elaborazione dei dati Adobe Analytics acquisiti in Adobe Experience Platform e

* la natura di Customer Journey Analytics in termini di momento del rapporto

Adobe ha pubblicato [best practice aggiornate per l’implementazione del canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=it). Questi consigli aggiornati consentono di sfruttare al massimo le funzionalità già presenti in Adobe Analytics con Attribution IQ. Inoltre ti saranno utili per prepararti per una transizione di successo a Customer Journey Analytics.

### 4. Decidere se usare il connettore di origine di Analytics o gli SDK di Experience Platform

Mentre la raccolta dati di [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it) si evolve, probabilmente eseguirai la migrazione ad [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=it) o [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=it) con la rete Edge di Adobe Experience Platform. Sebbene un’implementazione tipica degli SDK invii dati ad Adobe Analytics, si presenta una nuova opportunità per l’invio diretto dei dati a Adobe Experience Platform. Possono quindi essere acquisiti in Customer Journey Analytics, mantenendo al tempo stesso i dati inviati ad Adobe Analytics.

Questo metodo estende notevolmente le possibilità di raccolta dei dati: non esiste più un limite al numero di campi né la necessità di mappare gli elementi dati su prop, eVar ed eventi come in Analytics. È possibile utilizzare un numero illimitato di elementi schema di tipi diversi e rappresentarli in più modi utilizzando le [Visualizzazioni dati](/help/data-views/data-views.md) di CJA. Quando i dati vengono inviati direttamente ad Adobe Experience Platform, diventano disponibili più velocemente in quanto viene rimosso il tempo di elaborazione dei dati tramite Adobe Analytics.

**Vantaggi dell’utilizzo degli SDK di Experience Platform:**

* Schema flessibile per definire i campi necessari
* Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)
* Nessun limite di carattere (100 caratteri per prop)
* Disponibilità più rapida dei dati in Adobe Experience Platform

**Limitazioni dell’utilizzo degli SDK di Experience Platform**

Le funzioni o i componenti seguenti di Adobe Analytics non sono supportati:

* Canali marketing
* Filtro bot
* Ricerche per posizione, dominio o dispositivo
* Analytics for Target (A4T)

## Prepararsi per le differenze fondamentali

### Acquisire dimestichezza con l’elaborazione al momento del reporting

Il reporting in Adobe Analytics si basa su una quantità significativa di pre-elaborazione dei dati per generare risultati come la persistenza visibile nelle [!UICONTROL eVars]. Al contrario, Customer Journey Analytics esegue tali calcoli in fase di esecuzione dei rapporti.

[!UICONTROL Report time processing] apre la possibilità di applicare impostazioni retroattive e creare più versioni di persistenza delle variabili senza dover modificare la modalità di raccolta dei dati sottostanti.

Questo cambiamento comporterà alcune differenze nel modo in cui i dati vengono inseriti nei rapporti, specialmente per tutte le variabili che possono avere una lunga finestra di scadenza. Puoi iniziare valutando in che modo l’elaborazione al momento della generazione del rapporto può influire sui rapporti utilizzando una [suite di rapporti virtuale](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=it).

### Identificare i segmenti e le metriche calcolate più importanti

I segmenti (denominati [!UICONTROL filters] in CJA) e le metriche calcolate di Adobe Analytics non sono compatibili con Customer Journey Analytics. In molti casi, questi componenti possono essere ricreati in CJA utilizzando i nuovi schemi e i dati disponibili.

Per rendere la transizione il più semplice possibile per gli utenti che passano da un sistema all’altro, pianifica in anticipo eseguendo le seguenti operazioni:

1. Identifica i componenti più critici.

1. Documenta le loro definizioni.

1. Identifica i campi necessari nei dati per replicarli in CJA come [Filtri](/help/components/filters/filters-overview.md) e [Metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md).

Ecco un paio di video per guidarti:

* [Spostare i segmenti di Adobe Analytics in Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=it)

* [Spostare le metriche calcolate da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=it)

### Altre considerazioni

* Grazie alla potenza delle visualizzazioni dati di CJA, hai a disposizione molta più flessibilità nel definire le metriche e le dimensioni in Customer Journey Analytics. Ad esempio, puoi utilizzare il valore di una dimensione come definizione di una metrica. [Ulteriori informazioni](/help/data-views/data-views-usecases.md)

* Se hai definito un calendario personalizzato in Adobe Analytics, avrai [funzionalità di calendario personalizzate](/help/components/date-ranges/custom-date-ranges.md) nell’ambito di CJA. È necessario assicurarsi che il calendario sia definito correttamente.

* In Customer Journey Analytics, puoi definire un valore di timeout personalizzato per visita o sessione e una metrica che avvierà una nuova sessione. Puoi creare visualizzazioni dati con diverse definizioni di sessione per ottenere più informazioni di quanto non fosse possibile in Adobe Analytics. Questa funzionalità può risultare particolarmente utile per i set di dati mobili.

## Passaggi successivi

Dopo il passaggio a CJA, se noti eventuali discrepanze di dati, puoi confrontare i dati originali di Adobe Analytics con quelli di Adobe Analytics attualmente in Customer Journey Analytics. [Ulteriori informazioni](/help/troubleshooting/compare.md)
