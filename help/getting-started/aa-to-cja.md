---
title: Migrazione da Adobe Analytics al Customer Journey Analytics
description: Passaggi per migrare da Adobe Analytics al Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 2f38b38328816a523427d73f812041904e294bc7
workflow-type: tm+mt
source-wordcount: '1222'
ht-degree: 4%

---

# Preparare la migrazione da Adobe Analytics al Customer Journey Analytics

Prima di eseguire la migrazione dei dati da Adobe Analytics al Customer Journey Analytics, esamina queste considerazioni per preparare i dati e prendere coscienza delle differenze critiche tra le due tecnologie.

## Preparare i dati

La preparazione dei dati Adobe Analytics per un passaggio semplice al Customer Journey Analytics è fondamentale per l’integrità dei dati e la coerenza della generazione dei rapporti.

### 1. Raccogliere le identità

Forse la componente più importante per comprendere un percorso di clienti è sapere chi è il cliente in ogni fase. Ad Customer Journey Analytics, l’esistenza di un identificatore su tutti i canali e i dati corrispondenti consente di unire più sorgenti all’interno di CJA.
Esempi di identità possono essere un ID cliente, un ID account o un ID e-mail. Indipendentemente dall&#39;identità (e possono essere presenti più identità), considera quanto segue per ogni ID:

* L’ID esiste o può essere aggiunto a tutte le origini dati che desideri inserire in CJA
* L’ID viene popolato su ogni riga di dati
* L&#39;ID non contiene PII. Applica l’hashing a qualsiasi elemento che potrebbe essere sensibile.
* L&#39;ID utilizza lo stesso formato per tutte le sorgenti (stessa lunghezza, stesso metodo di hashing, ecc.)

Nei set di dati come Adobe Analytics, è possibile che un’identità non esista su ogni riga di dati, ma esiste un’identità secondaria. In questo caso, l’analisi cross-channel (precedentemente nota come &quot;unione basata sui campi&quot;) può essere utilizzata per colmare il gap tra le righe quando un cliente è identificato solo dal proprio ECID e quando viene raccolta un’identità (ad esempio, quando un cliente si autentica). [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=it)

### 2. Allineare le variabili

La migrazione più semplice dei dati di Adobe Analytics al Customer Journey Analytics è quella di acquisire un [suite di rapporti globale](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=en) in Experience Platform utilizzando [Connettore sorgente Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en). Questo connettore mappa le variabili Adobe Analytics direttamente su uno schema e un set di dati XDM in AEP, che a sua volta può essere facilmente connesso a CJA.

Una suite di rapporti globale completa potrebbe non essere sempre possibile per un’implementazione. Se prevedi di mettere in Customer Journey Analytics più suite di rapporti, devi pianificare in anticipo per allineare le variabili in tali suite di rapporti.

Ad esempio, eVar1 nella suite di rapporti 1 può fare riferimento a [!UICONTROL Page]. Nella suite di rapporti 2, eVar1 può indicare [!UICONTROL Internal Campaign]. Una volta introdotte in CJA, queste variabili si combineranno in un’unica dimensione eVar1, generando rapporti potenzialmente confusi e imprecisi.

Se hai evitato di passare a una suite di rapporti globale a causa di problemi con [!UICONTROL Uniques Exceeded] o [!UICONTROL Low Traffic], sapere che CJA non ha [limiti di cardinalità su una dimensione](/help/components/dimensions/high-cardinality.md). Permette di visualizzare e conteggiare qualsiasi valore univoco.

### 3. (Re)Configura i canali di marketing

Le impostazioni tradizionali del canale di marketing Adobe Analytics non funzionano nello stesso modo in CJA. Questo per due motivi:

* Il livello di elaborazione dei dati Adobe Analytics acquisiti in Adobe Experience Platform e

* La natura del Customer Journey Analytics in termini di tempo di relazione

Adobe pubblicato [best practice aggiornate per l’implementazione del canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=en). Questi consigli aggiornati consentono di sfruttare al massimo le funzionalità già presenti in Adobe Analytics con Attribution IQ. Ti configureranno anche per il successo durante la transizione al Customer Journey Analytics.

### 4. Decidi se usare il connettore di origine di Analytics o gli SDK di Experience Platform

Come [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) la raccolta dati si evolve, probabilmente eseguirai la migrazione a [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=en) o [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=en) con Adobe Experience Platform Edge Network. Sebbene un’implementazione tipica degli SDK invii dati ad Adobe Analytics, si presenta una nuova opportunità per l’invio diretto dei dati a Adobe Experience Platform. Può quindi essere acquisito in Customer Journey Analytics, mantenendo al tempo stesso i dati inviati ad Adobe Analytics.

Questo metodo espande notevolmente le possibilità di raccolta dei dati: Non esiste più una limitazione sul numero di campi o sulla necessità di mappare gli elementi dati su proprietà, eVar ed eventi come in Analytics. È possibile utilizzare elementi schema illimitati di tipi diversi e rappresentarli in più modi utilizzando CJA [Visualizzazioni dati](/help/data-views/data-views.md). La velocità di disponibilità dei dati aumenta quando vengono inviati direttamente a Adobe Experience Platform, in quanto viene rimosso il tempo di elaborazione dei dati tramite Adobe Analytics.

**Vantaggi dell&#39;utilizzo degli SDK di Experience Platform**

* Schema flessibile per definire i campi necessari
* Non si basa sulla nomenclatura Adobe Analytics (prop, eVar, event, ecc.)
* Nessun limite di carattere (100 caratteri per proprietà)
* Disponibilità più rapida dei dati in Adobe Experience Platform

**Drawback dell’utilizzo degli SDK di Experience Platform**

Le seguenti funzioni o componenti di Adobe Analytics non sono supportati:

* Canali marketing
* Filtro bot
* Ricerche Geo, Domain, Device
* Analytics for Target (A4T)

## Prepararsi per le differenze critiche

### Acquisisci dimestichezza con l&#39;elaborazione dei tempi di report

Il reporting in Adobe Analytics si basa su una quantità significativa di dati pre-elaborazione per generare risultati come la persistenza visibile in [!UICONTROL eVars]. Al contrario, il Customer Journey Analytics esegue tali calcoli in fase di esecuzione dei rapporti.

[!UICONTROL Report time processing] apre la possibilità di applicare impostazioni retroattive e creare più versioni di persistenza variabile senza dover modificare la modalità di raccolta dei dati sottostanti.

Questo cambiamento comporterà alcune differenze nel modo in cui i dati vengono segnalati, specialmente per tutte le variabili che possono avere una lunga finestra di scadenza. Puoi iniziare valutando in che modo l’elaborazione al momento della generazione del rapporto può influire sui rapporti utilizzando un [suite di rapporti virtuale](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html).

### Identificare i segmenti critici e le metriche calcolate

Segmenti Adobe Analytics (denominati [!UICONTROL filters] in CJA) e le metriche calcolate non sono compatibili con il Customer Journey Analytics. In molti casi, questi componenti possono essere ricostruiti in CJA utilizzando i nuovi schemi e i dati disponibili.

Per rendere la transizione il più semplice possibile per gli utenti quando passano tra i sistemi, pianifica in anticipo

1. Identificazione dei componenti più critici.

1. la documentazione delle loro definizioni e

1. Identificazione dei campi necessari nei dati per replicarli in CJA come [Filtri](/help/components/filters/filters-overview.md) e [Metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md).

Ecco un paio di video per guidarti:

* [Spostare i segmenti Adobe Analytics nel Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=en)

* [Spostare le metriche calcolate da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en)

### Altre considerazioni

* Grazie alla potenza delle visualizzazioni dati CJA, puoi offrire molta più flessibilità nella definizione delle metriche e delle dimensioni all’interno del Customer Journey Analytics. Ad esempio, puoi utilizzare il valore di una dimensione per diventare la definizione di una metrica. [Ulteriori informazioni](/help/data-views/data-views-usecases.md)

* Se hai definito un calendario personalizzato in Adobe Analytics, avrai funzionalità di calendario simili in CJA. È necessario assicurarsi che il calendario sia definito correttamente.

* Al Customer Journey Analytics, puoi definire un timeout personalizzato di visita/sessione e una metrica che avvierà una nuova sessione. Puoi creare visualizzazioni dati con diverse definizioni di sessione per ottenere informazioni oltre a quanto era possibile in Adobe Analytics. Questa funzionalità può risultare particolarmente utile per i set di dati mobili.

## Passaggi successivi

Dopo il passaggio a CJA, se noti eventuali discrepanze di dati, puoi confrontare i dati originali di Adobe Analytics con quelli di Adobe Analytics attualmente in Customer Journey Analytics. [Ulteriori informazioni](/help/troubleshooting/compare.md)