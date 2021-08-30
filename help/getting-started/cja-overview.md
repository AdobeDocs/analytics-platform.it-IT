---
title: Panoramica su Customer Journey Analytics
description: Scopri come Customer Journey Analytics consente di utilizzare Analysis Workspace con i dati da Experience Platform.
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
source-git-commit: fa0033202650f17acd275f1050565285c1464f53
workflow-type: tm+mt
source-wordcount: '1255'
ht-degree: 91%

---

# Panoramica su Customer Journey Analytics

Customer Journey Analytics rappresenta una funzionalità di Analytics che consente di sfruttare l’efficacia di Analysis Workspace insieme ai dati di Adobe Experience Platform. Tale funzionalità può suddividere, filtrare, eseguire query e visualizzare anni di dati e si abbina alla capacità della Platform di contenere tutti i tipi di schemi e di tipologie di dati. Utilizzando **Experience Data Model (XDM)**, i dati possono essere rappresentati e organizzati in modo uniforme, per poi eseguirne la combinazione e l’esplorazione. **Experience Query Services** consente di utilizzare strumenti e framework compatibili con SQL al fine di eseguire query e manipolazioni di tutti i dati.

## Confronto tra CJA e il tradizionale Adobe Analytics

Customer Journey Analytics estende l’ambito di Analytics attraverso l’offerta di funzionalità tra canali facili da usare, rimuovendo inoltre le limitazioni presenti nelle versioni precedenti di Adobe Analytics. Alcuni importanti miglioramenti sono i seguenti:

* **Variabili ed eventi illimitati**: i concetti di eVar, prop ed eventi non esistono più. I dati sono principalmente incentrati su dimensioni e metriche. I set di dati possono disporre di una quantità illimitata di dimensioni e metriche univoche.
* **Valori** univoci illimitati: Adobe Experience Platform non è vincolata ad alcun limite univoco.
* **Modifica dei dati storici**: con Adobe Experience Platform è possibile rimuovere o correggere i dati.
* **Dati di più suite di rapporti**: su Platform è possibile combinare le implementazioni esistenti da più set di dati.

La versione iniziale di Customer Journey Analytics include numerose funzioni incluse in Analysis Workspace. Per un elenco completo, consulta il [supporto delle funzioni di Customer Journey Analytics](cja-aa.md).

## Confronto tra CJA e Analisi multidispositivo

[Analisi multidispositivo](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html) si integra con Adobe Experience Platform Identity Service tramite Co-op Graph (Grafico co-op) o Private Graph (Grafico privato), per identificare in che modo i dispositivi digitali si associano alle persone. È disponibile per i clienti di Adobe Analytics Ultimate.

Customer Journey Analytics (CJA), invece, si integra con i set di dati di Adobe Experience Platform e consente di effettuare l’analisi cross-channel in Analysis Workspace. Anche se CJA non si integra ancora con i grafici co-op o di identità privata, puoi inserire il tuo ID per unire i set di dati, i quali possono andare ben oltre i semplici dati digitali, includendo sia punti di contatto online che offline. I prerequisiti per CJA sono descritti di seguito in modo più dettagliato.

## Casi d’uso principali

Customer Journey Analytics ti consente di:

* **Collocare il cliente in un contesto di customer journey**: puoi visualizzare e analizzare i dati in sequenza e su più canali. I dati provenienti dal call center, dai sistemi POS e dalle proprietà online possono essere combinati in un’unica visualizzazione di reporting.
* **Rendere gli insights disponibili a tutti**: semplifica l’accesso ai dati e consenti a più persone di prendere decisioni aziendali sulla base degli insights derivanti dai dati. Qualsiasi membro dell’organizzazione che è in qualche modo responsabile della customer experience può prendere decisioni concrete in tempi rapidi, sulla base di dati più completi.
* **Sfruttare la potenza della data science per i tuoi analisti**: Customer Journey Analytics consente alle persone comuni di avvalersi della data science per acquisire analisi e insights approfonditi.
* **Visualizzare e interagire con i set di dati utilizzando reporting ad hoc**: Workspace può sfruttare qualsiasi set di dati di Adobe Experience Platform che risulti conforme ad alcune regole di base.
* **Visualizzare dati non adatti per il web**: Workspace non è più limitato a una definizione rigida di hit o evento. Gli schemi personalizzati consentono il controllo completo dei dati e delle definizioni.
* **Esercitare un controllo maggiore sulla manipolazione dei dati**: modifica i dati caricati, crea nuovi set di dati e importali all’interno di Workspace. Tramite Experience Cloud Query Service, Adobe Experience Platform fornisce strumenti di query, estrazione, trasformazione e caricamento.

## Prerequisiti

Prima di iniziare a utilizzare Customer Journey Analytics, è necessario soddisfare i seguenti prerequisiti:

* La tua organizzazione dispone di un contratto attivo con Adobe Analytics per la versione Select, Prime o Ultimate con il componente aggiuntivo Customer Journey Analytics. Se non conosci il tipo di contratto che hai stipulato o se non hai la certezza di possedere il componente aggiuntivo CJA, contatta l’Account Manager della tua organizzazione.
* È stato eseguito il provisioning della tua organizzazione per Adobe Experience Platform.

## Autorizzazioni di accesso per gli amministratori

Per creare connessioni, aggiungere set di dati e così via è necessario disporre delle seguenti autorizzazioni in [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Per accedere al Customer Journey Analytics o effettuare una connessione, devi essere aggiunto come Amministratore al **Customer Journey Analytics prodotto** nell&#39; [Admin Console](https://adminconsole.adobe.com/enterprise/). Gli amministratori di prodotto dispongono delle seguenti autorizzazioni:
   * Creare/aggiornare/eliminare connessioni o visualizzazioni dati
   * Aggiornare/eliminare progetti, filtri, metriche calcolate o filtri creati da altri utenti
   * Condividere un progetto Workspace con tutti gli utenti
* Per poter creare, aggiornare o eliminare una connessione, non è sufficiente diventare amministratore di prodotto in Customer Journey Analytics. Per creare una connessione a un set di dati di Experience Platform, è necessario disporre anche di autorizzazioni Experience Platform. In particolare, devi far parte di un **profilo di prodotto Experience Platform** che ti fornisca le seguenti autorizzazioni:
   * Visualizzare gli schemi
   * Gestire gli schemi
   * Visualizzare gli spazi dei nomi delle identità
   * Visualizzare i set di dati

Per ulteriori informazioni sulle autorizzazioni di Experience Platform, consulta [Controllo degli accessi in Adobe Experience Platform](https://docs.adobe.com/content/help/it-IT/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).

>[!NOTE]
>
>Non puoi autorizzare singole metriche o dimensioni nel Customer Journey Analytics, come puoi fare nella tradizionale Adobe Analytics. Le metriche e le dimensioni possono essere modificate nelle visualizzazioni dati e sono quindi soggette a modifiche in CJA, che cambia anche la generazione di rapporti retroattivamente.

### Accesso utente

Gli utenti di Customer Journey Analytics che non sono amministratori di prodotto non possono visualizzare le visualizzazioni di dati o le connessioni, ma possono creare filtri, progetti e metriche calcolate.

## Aggiornamenti terminologici

Rispetto alla soluzione Adobe Analytics tradizionale, diverse funzioni di CJA sono state rinominate, in base agli standard di settore. Alcuni termini aggiornati includono:

* I segmenti sono ora noti come “Filtri”.
* Le suite di rapporti virtuali sono ora note come &quot;visualizzazioni dati&quot;.
* Le classificazioni sono ora note come “Set di dati di ricerca”.
* Gli attributi cliente sono ora detti “Dataset di profilo”.
* I contenitori degli hit sono ora noti come contenitori “Evento”.
* I contenitori delle visite sono ora noti come contenitori “Sessione”.
* I contenitori dei visitatori sono ora noti come contenitori “Persona”.

## Altre funzionalità integrate in Adobe Experience Platform

Customer Journey Analytics è una delle funzionalità incentrate su Adobe Experience Platform. Numerose altre funzionalità, basate anch’esse su Experience Platform, ti consentono di sfruttare al massimo i tuoi dati.

Adobe Experience Platform ti permette di centralizzare e standardizzare i dati e i contenuti dei clienti da qualsiasi sistema, oltre che di applicare la data science e l’apprendimento automatico al fine di migliorare la progettazione e l’erogazione di esperienze personalizzate. In Platform i dati del cliente vengono memorizzati come set di dati, costituiti da uno schema e da un batch di dati. Per ulteriori informazioni su Platform, consulta [Panoramica dell’architettura di Adobe Experience Platform](https://docs.adobe.com/content/help/it-IT/experience-platform/landing/home.translate.html).

Dall’inserimento dati all’accesso diretto a SQL, numerosi componenti di Experience Platform sono centrali per Customer Journey Analytics e agiscono sinergicamente:

* [Query Service](https://docs.adobe.com/content/help/it-IT/experience-platform/query/home.translate.html): sfrutta SQL standard per recuperare i dati da Adobe Experience Platform, ad esempio i dati della soluzione Adobe, i dati 1st-party del cliente o qualsiasi altro dato relativo alla Platform. Si tratta di uno strumento serverless che consente di unire qualsiasi set di dati e di acquisire i risultati della query sotto forma di nuovo set di dati da utilizzare nel reporting, in Data Science Workspace o per l’inserimento in Profile Service. È possibile utilizzare Query Service per generare ecosistemi di analisi dei dati, creando un’immagine dei consumatori attraverso i loro molteplici canali di interazione. Tali canali possono includere sistemi POS, web, mobile, sistemi di gestione delle relazioni con i clienti e così via.
* [Profilo del cliente in tempo reale](https://docs.adobe.com/content/help/it-IT/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [Servizio identità](https://docs.adobe.com/content/help/it-IT/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://docs.adobe.com/content/help/it-IT/experience-platform/data-science-workspace/home.translate.html) nell’opzione sviluppatore: puoi usare i modelli di intelligenza artificiale (AI) e apprendimento automatico precompilati in Adobe Experience Platform per influenzare vari punti della customer journey. Sfruttando insights nascosti, puoi effettuare previsioni più affidabili lungo la customer journey, suggerire i migliori passaggi successivi o automatizzare processi complicati.
