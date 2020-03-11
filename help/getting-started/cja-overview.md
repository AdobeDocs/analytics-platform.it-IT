---
title: Panoramica sull'analisi del percorso del cliente
description: Introduzione all'analisi del percorso del cliente
translation-type: tm+mt
source-git-commit: 336adb3762258cc657ffa5c74a50d28e6f63c7db

---


# Panoramica sull&#39;analisi del percorso del cliente

Analisi del percorso del cliente è una funzionalità di Analytics che consente di utilizzare l&#39;efficacia di Analysis Workspace con i dati di Adobe Experience Platform. Può suddividere, filtrare, query e visualizzare il valore di dati degli anni ed è combinato con la capacità della Piattaforma di contenere tutti i tipi di schemi e tipi di dati. Utilizzando il modello dati **esperienza (XDM)**, i dati possono essere rappresentati e organizzati in modo uniforme, pronti per essere combinati e esplorati. **Experience Query Services** consente di utilizzare strumenti e framework compatibili con SQL per eseguire query e manipolare tutti i dati.

## Confronto tra CJA e Adobe Analytics tradizionale

Analisi del percorso del cliente amplia l&#39;ambito di Analytics offrendo funzionalità multicanale facili da usare e rimuovendo le limitazioni nelle versioni precedenti di Adobe Analytics. Alcuni miglioramenti importanti sono:

* **Variabili ed eventi** illimitati: I concetti di eVar, prop ed eventi non esistono più. I dati sono principalmente incentrati su dimensioni e metriche. I set di dati possono avere una quantità illimitata di dimensioni e metriche univoche.
* **Valori** univoci illimitati: Adobe Experience Platform non è limitato ad alcun limite univoco, come i valori univoci da 500 k nelle suite di rapporti tradizionali.
* **Modifica dei dati** storici: Con Adobe Experience Platform è possibile rimuovere o correggere i dati.
* **Dati** suite per report: Le implementazioni esistenti da più set di dati possono essere combinate in Piattaforma.

La versione iniziale di Analisi del percorso del cliente include molte delle funzioni incluse in Analysis Workspace. Per un elenco completo, consulta Supporto [delle funzioni Analisi percorso](cja-aa.md)clienti.

## Confronto tra CJA e analisi multi-dispositivo

[Analytics](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-home.html) cross-device si integra con Adobe Experience Platform Identity Service, utilizzando Co-op Graph o Private Graph, per identificare la mappatura dei dispositivi digitali alle persone. È disponibile per i clienti di Adobe Analytics Ultimate.

CJA si integra con i set di dati della piattaforma Adobe Experience e consente l&#39;analisi tra canali in Analysis Workspace. Anche se la CJA non si integra ancora con i grafici di identità Co-op o Privati, puoi &quot;unire il tuo ID&quot; per unire i set di dati, e questi set di dati possono andare oltre i dati digitali per includere sia punti di contatto online che offline. I prerequisiti per la CJA sono descritti più dettagliatamente di seguito.

## Casi di utilizzo chiave

Analisi del percorso del cliente consente di:

* **Scopri il cliente in un contesto** di viaggio: È possibile visualizzare e analizzare i dati in sequenza su più canali. I dati provenienti dai call center, dai sistemi POS e dalle proprietà online possono essere combinati in un&#39;unica visualizzazione di reporting.
* **Rendi le informazioni disponibili a tutti**: Democratizzare l&#39;accesso ai dati e consentire a più persone di prendere decisioni aziendali con informazioni derivate dai dati. Chiunque all&#39;interno dell&#39;organizzazione sia responsabile di qualsiasi aspetto dell&#39;esperienza cliente può prendere decisioni concrete più rapidamente, sulla base di dati più completi.
* **Sfruttate la potenza della scienza dei dati per i vostri analisti**: Analisi del percorso dei clienti consente agli esseri umani normali di utilizzare la scienza dei dati per acquisire informazioni approfondite e analizzarle.
* **Visualizzare e interagire con i set di dati utilizzando i rapporti** ad hoc: Workspace può utilizzare qualsiasi set di dati di Adobe Experience Platform conforme ad alcune regole di base.
* **Visualizzare dati** non Web: Workspace non è più limitato a una definizione rigida di &quot;hit&quot; o &quot;event&quot;. Gli schemi personalizzati consentono il controllo completo dei dati e delle definizioni.
* **Controllo maggiore sulla manipolazione** dei dati: Modificare i dati caricati, creare nuovi set di dati e importarli in Workspace. Adobe Experience Platform fornisce strumenti di query, estrazione, trasformazione e caricamento tramite Experience Cloud Query Service.

## Prerequisiti

Prima di iniziare a utilizzare Analisi percorso cliente, è necessario soddisfare i seguenti prerequisiti:

* La tua organizzazione ha un contratto attivo con Adobe Analytics per Select, Prime o Ultimate con il componente aggiuntivo Analisi del percorso cliente. Se non sei sicuro di quale tipo di contratto hai o se non sei sicuro di avere il componente aggiuntivo CJA, contatta l&#39;Account Manager della tua organizzazione.
* È stato eseguito il provisioning della tua organizzazione per Adobe Experience Platform.

## Autorizzazioni di accesso utente

Per creare connessioni, aggiungere set di dati, ecc., è necessario disporre delle seguenti autorizzazioni in [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Per gestire i set di dati in Experience Platform, devi far parte di un profilo di prodotto della piattaforma che ti dà l&#39;autorizzazione &quot;Gestisci set di dati&quot;. Per ulteriori informazioni, consulta Controllo [degli accessi in Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Per creare una connessione a un set di dati della piattaforma, dovete far parte di un profilo di prodotto della piattaforma che vi dia le seguenti autorizzazioni:
   * Visualizza schemi
   * Visualizza set di dati
   * Gestisci spazi dei nomi identità
   * Visualizza sandbox
* Per accedere ad Analisi percorso cliente o per stabilire una connessione, dovrai anche essere aggiunto a un profilo di prodotto Analisi percorso cliente in [Admin Console](https://adminconsole.adobe.com/enterprise/).

### Aggiornamenti terminologici

Diverse funzioni della CJA sono state rinominate per allinearsi con gli standard di settore. Alcuni nomi aggiornati includono:

* I segmenti sono ora noti come &#39;Filtri&#39;.
* Le suite di rapporti virtuali sono ora denominate &quot;visualizzazioni&quot;.
* Le classificazioni sono ora note come &quot;dataset di ricerca&quot;.
* Gli attributi del cliente sono ora noti come &quot;dataset di profilo&quot;.
* I contenitori degli hit sono ora noti come contenitori &#39;Event&#39;.
* I contenitori delle visite sono ora noti come contenitori &#39;Session&#39;.
* I contenitori dei visitatori sono ora noti come contenitori &quot;Persona&quot;.

## Altre funzionalità integrate in Adobe Experience Platform

Analisi del percorso del cliente è una delle funzionalità che si basa su Adobe Experience Platform. Diverse altre funzionalità, basate anche su Piattaforma, vi consentono di sfruttare al massimo i vostri dati.

Adobe Experience Platform consente di centralizzare e standardizzare i dati e i contenuti dei clienti da qualsiasi sistema e di applicare la scienza dei dati e l&#39;apprendimento automatico per migliorare la progettazione e la distribuzione di esperienze personalizzate. I dati del cliente nella piattaforma vengono memorizzati come insiemi di dati, che consistono in uno schema e in batch di dati. Per ulteriori informazioni sulla piattaforma, consulta Panoramica [di](https://www.adobe.io/apis/experienceplatform/home/overview.html)Adobe Experience Platform Architecture.

Dall&#39;inserimento dei dati all&#39;accesso diretto a SQL, diversi componenti della piattaforma Experience sono centrali per l&#39;analisi del percorso dei clienti e agiscono in combinazione con esso:

* [Servizio](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html)query: Utilizzate SQL standard per recuperare dati da Adobe Experience Platform, come dati della soluzione Adobe, dati di prime parti cliente o qualsiasi altro dato della piattaforma. Si tratta di uno strumento senza server che consente di unire qualsiasi set di dati e acquisire i risultati della query come nuovo set di dati da utilizzare nei report, in Data Science Workspace o per l&#39;inserimento in Profile Service. È possibile utilizzare Query Service per creare ecosistemi di analisi dei dati, creando un&#39;immagine dei consumatori attraverso i loro canali di interazione. Questi canali possono includere sistemi Point-of-Sale, Web, dispositivi mobili, sistemi CRM, ecc.
* [Profilo](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)cliente in tempo reale:
* [Servizio identità](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Area di lavoro](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) di scienza dei dati nell&#39;opzione &quot;sviluppatore&quot;: puoi usare i modelli di intelligenza artificiale (AI) e apprendimento automatico pregenerati in Adobe Experience Platform per influenzare vari punti del percorso del cliente. Sfruttando informazioni nascoste, puoi fare previsioni migliori durante il percorso del cliente, suggerire i passaggi successivi consigliati o automatizzare processi ingombranti.
