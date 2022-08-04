---
title: Panoramica di Customer Journey Analytics
description: Scopri come Customer Journey Analytics consente di utilizzare Analysis Workspace con i dati da Experience Platform.
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: f7b4dcb893586e71302cc6a20ebe931743ea8924
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 100%

---

# Panoramica di Customer Journey Analytics

Customer Journey Analytics rappresenta una funzionalità di Analytics che consente di sfruttare l’efficacia di Analysis Workspace insieme ai dati di Adobe Experience Platform. Tale funzionalità può suddividere, filtrare, eseguire query e visualizzare anni di dati e si abbina alla capacità della Platform di contenere tutti i tipi di schemi e di tipologie di dati. Utilizzando **Experience Data Model (XDM)**, i dati possono essere rappresentati e organizzati in modo uniforme, per poi eseguirne la combinazione e l’esplorazione. **Experience Query Services** consente di utilizzare strumenti e framework compatibili con SQL al fine di eseguire query e manipolazioni di tutti i dati.

L’architettura CJA di alto livello è mostrata qui:

![architettura](assets/cja-architecture.png)

Ecco una panoramica video di Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30090/?quality=12)

## Confronto tra CJA e il tradizionale Adobe Analytics

Customer Journey Analytics estende l’ambito di Adobe Analytics con funzionalità cross-channel facili da usare. Inoltre, rimuove le limitazioni presenti nelle versioni precedenti di Adobe Analytics. Alcuni importanti miglioramenti sono i seguenti:

* **Variabili ed eventi illimitati**: i concetti di eVar, prop ed eventi non esistono più. I dati sono principalmente incentrati su dimensioni e metriche. I set di dati possono disporre di un numero illimitato di dimensioni e metriche univoche.
* **Valori univoci illimitati**: Adobe Experience Platform non è vincolata ad alcun limite univoco.
* **Modifica dei dati storici**: con Adobe Experience Platform è possibile rimuovere o correggere i dati.
* **Dati di più suite di rapporti**: su Platform è possibile combinare le implementazioni esistenti da più set di dati.

La versione iniziale di Customer Journey Analytics include numerose funzioni incluse in Analysis Workspace. Per un elenco completo, consulta il [supporto delle funzioni di Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

## Casi d’uso principali

Customer Journey Analytics ti consente di:

* **Collocare il cliente in un contesto di customer journey**: puoi visualizzare e analizzare i dati in sequenza e su più canali. I dati provenienti dal call center, dai sistemi POS e dalle proprietà online possono essere combinati in un’unica visualizzazione di reporting.
* **Rendere gli insights disponibili a tutti**: semplifica l’accesso ai dati e consenti a più persone di prendere decisioni aziendali sulla base degli insights derivanti dai dati. Qualsiasi membro dell’organizzazione che è in qualche modo responsabile della customer experience può prendere decisioni concrete in tempi rapidi, sulla base di dati più completi.
* **Sfruttare la potenza della data science per i tuoi analisti**: Customer Journey Analytics consente alle persone comuni di avvalersi della data science per acquisire analisi e insights approfonditi.
* **Visualizzare e interagire con i set di dati utilizzando reporting on-demand**: Workspace può sfruttare qualsiasi set di dati di Adobe Experience Platform che risulti conforme ad alcune regole di base.
* **Visualizzare dati non adatti per il web**: Workspace non è più limitato a una definizione rigida di hit o evento. Gli schemi personalizzati consentono il controllo completo dei dati e delle definizioni.
* **Esercitare un controllo maggiore sulla manipolazione dei dati**: modifica i dati caricati, crea set di dati e importali all’interno di Workspace. Tramite Experience Cloud Query Service, Adobe Experience Platform fornisce strumenti di query, estrazione, trasformazione e caricamento.

## Prerequisiti

Prima di iniziare a utilizzare Customer Journey Analytics, è necessario soddisfare i seguenti prerequisiti:

* La tua organizzazione dispone di un contratto attivo con Adobe Analytics per la versione Select, Prime o Ultimate con il componente aggiuntivo Customer Journey Analytics. Se non conosci il tipo di contratto che hai stipulato o se non hai la certezza di possedere il componente aggiuntivo CJA, contatta l’Account Manager della tua organizzazione.
* È stato eseguito il provisioning della tua organizzazione per Adobe Experience Platform.

## Controllo degli accessi

Fai riferimento all’argomento [Controllo degli accessi](/help/getting-started/cja-access-control.md).

## Aggiornamenti terminologici

Rispetto alla soluzione Adobe Analytics tradizionale, diverse funzioni di CJA sono state rinominate, in base agli standard di settore. Alcuni termini aggiornati includono:

* I segmenti sono ora noti come “Filtri”.
* Le suite di rapporti virtuali sono ora denominate “Visualizzazioni dati”.
* Le classificazioni sono ora note come “Set di dati di ricerca”.
* Gli attributi cliente sono ora detti “Dataset di profilo”.
* I contenitori degli hit sono ora noti come contenitori “Evento”.
* I contenitori delle visite sono ora noti come contenitori “Sessione”.
* I contenitori dei visitatori sono ora noti come contenitori “Persona”.

## Altre funzionalità integrate in Adobe Experience Platform

Customer Journey Analytics è una delle funzionalità incentrate su Adobe Experience Platform. Numerose altre funzionalità, basate anch’esse su Experience Platform, ti consentono di sfruttare al massimo i tuoi dati.

Adobe Experience Platform ti permette di centralizzare e standardizzare i dati e i contenuti dei clienti da qualsiasi sistema, oltre che di applicare la data science e l’apprendimento automatico al fine di migliorare la progettazione e l’erogazione di esperienze personalizzate. In Platform i dati del cliente vengono memorizzati come set di dati, costituiti da uno schema e da un batch di dati. Per ulteriori informazioni su Platform, consulta [Panoramica dell’architettura di Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=it).

Dall’inserimento dati all’accesso diretto a SQL, numerosi componenti di Experience Platform sono centrali per Customer Journey Analytics e sono complementari a esso:

* [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=it): sfrutta SQL standard per recuperare i dati da Adobe Experience Platform, ad esempio i dati della soluzione Adobe, i dati 1st-party del cliente o qualsiasi altro dato relativo alla Platform. Si tratta di uno strumento privo di server che consente di unire qualsiasi set di dati e di acquisire i risultati della query sotto forma di nuovo set di dati da utilizzare nel reporting, in Data Science Workspace o da acquisire in Profile Service. È possibile utilizzare Query Service per generare ecosistemi di analisi dei dati, creando un’immagine dei consumatori attraverso i loro molteplici canali di interazione. Tali canali possono includere sistemi POS, web, mobile, sistemi di gestione delle relazioni con i clienti e così via.
* [Profilo del cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it):
* [Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=it):
* [Data Science Workspace](https://experienceleague.adobe.com/docs/experience-platform/data-science-workspace/home.html?lang=it) nell’opzione sviluppatore: puoi usare i modelli di intelligenza artificiale (AI) e apprendimento automatico precompilati in Adobe Experience Platform per influenzare vari punti della customer journey. Sfruttando insights nascosti, puoi effettuare previsioni più affidabili lungo la customer journey, suggerire i migliori passaggi successivi o automatizzare processi complicati.

## Video

* Utilizzo dei dati in Customer Journey Analytics:

   >[!VIDEO](https://video.tv.adobe.com/v/32112/?quality=12)

* Architettura e integrazioni di Customer Journey Analytics:

   >[!VIDEO](https://video.tv.adobe.com/v/32483/?quality=12)

