---
title: Percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: 967d8a957e722a080cd712ea7cf77f26660289da
workflow-type: tm+mt
source-wordcount: '1584'
ht-degree: 10%

---

# Aggiornamento da Adobe Analytics a Customer Journey Analytics

Durante l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics, puoi seguire i [passaggi di aggiornamento consigliati](#recommended-upgrade-steps-for-most-organizations). Oppure puoi [generare dinamicamente i passaggi di aggiornamento](#dynamically-generate-upgrade-steps-for-your-organization) per le circostanze univoche della tua organizzazione.

## Passaggi di aggiornamento consigliati per la maggior parte delle organizzazioni {#upgrade-process}

Il processo consigliato di aggiornamento da Adobe Analytics a Customer Journey Analytics è una nuova implementazione di Experience Platform Web SDK, che è il metodo di raccolta dati preferito per Customer Journey Analytics. Insieme al SDK web, Adobe consiglia anche di utilizzare il connettore di origine di Analytics per facilitare la transizione a Customer Journey Analytics. Utilizza il connettore di origine di Analytics per conservare i dati storici di Adobe Analytics ed eseguire confronti di dati affiancati.

Una volta che si dispone di un numero sufficiente di dati storici utilizzando Experience Platform Web SDK e si è effettuata la transizione completa a Customer Journey Analytics, il connettore di origine di Analytics può essere disattivato e il Web SDK può essere utilizzato esclusivamente.

>[!NOTE]
>
>Se i passaggi di aggiornamento descritti in questa sezione non sono pratici per la tua organizzazione, utilizza il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) per generare in modo dinamico passaggi di aggiornamento personalizzati per le circostanze specifiche della tua organizzazione.

### Processo di aggiornamento consigliato di alto livello {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Dati storici da Adobe Analytics"
>abstract="Importa i dati storici della suite di rapporti di Adobe Analytics in Adobe Experience Platform e Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

1. **Implementare Experience Platform Web SDK (per la raccolta dati in corso)**

   Una nuova implementazione di Experience Platform Web SDK è il modo migliore per raccogliere dati per Customer Journey Analytics. Fornisce le basi migliori per ottenere il massimo da Customer Journey Analytics perché è il metodo più performante, semplice e a prova di futuro per implementare Customer Journey Analytics.

   * Rapporti e disponibilità dei dati ad alte prestazioni perché Adobe Experience Platform è stato progettato per casi d’uso di personalizzazione in tempo reale

   * Consolidare l’implementazione per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)

   * Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)

1. **Configura il connettore di origine di Adobe Analytics (per il recupero dei dati storici)**

   Per facilitare la transizione all’utilizzo di Experience Platform Web SDK con Customer Journey Analytics, Adobe consiglia inoltre di utilizzare il connettore di origine di Adobe Analytics. Questo consente di conservare i dati storici e visualizzare i dati dell’implementazione Adobe Analytics esistente in Customer Journey Analytics, insieme ai dati della nuova implementazione Experience Platform Web SDK.

   Il connettore di origine di Analytics consente di:

   * Importa i dati storici della suite di rapporti di Adobe Analytics in Adobe Experience Platform e Customer Journey Analytics.

     Puoi mantenere in funzione il connettore di origine di Analytics per il tempo necessario a conservare i dati storici di Adobe Analytics.

   * Visualizza i dati raccolti con l’implementazione originale di Adobe Analytics (AppMeasurement, Analytics Extension o Web SDK Extension) in Customer Journey Analytics. Puoi confrontare questi dati affiancati a quelli della nuova implementazione di Web SDK.

     Puoi mantenere in funzione il connettore di origine di Analytics fino a quando non avrai familiarità con le differenze. <!--elaborate on what those differences are? -->

   Il connettore di origine di Analytics come implementazione autonoma non è un metodo consigliato a lungo termine per l’utilizzo di Customer Journey Analytics. Ciò è dovuto a latenza elevata, schemi ingombranti e complessi, dipendenza dalla nomenclatura di Adobe Analytics (prop, eVar e così via) e difficoltà nel passare infine dal connettore di origine di Analytics all’implementazione consigliata di Web SDK.

### Passaggi di aggiornamento consigliati dettagliati

I passaggi seguenti descrivono il processo consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics.

Ogni passaggio fornisce una spiegazione di alto livello di un processo più dettagliato. Seguire il collegamento di ogni passaggio e completare le attività associate, quindi tornare a questa pagina e continuare con il passaggio successivo del processo.

1. [Pianifica l&#39;architettura dello schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Crea lo schema personalizzato desiderato in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Quando crei lo schema, considera le seguenti opzioni:

   * Per integrare Customer Journey Analytics con RTCDP, devi abilitare l&#39;opzione **[!UICONTROL Profile]** nello schema, come descritto in [Creare uno schema XDM da utilizzare con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md). Con questa opzione abilitata, quando i dati vengono acquisiti in set di dati basati su questo schema, questi vengono uniti al Profilo cliente in tempo reale.

   * Se desideri includere dati multimediali in streaming, devi [configurare lo schema per acquisire e utilizzare dati in streaming](/help/data-ingestion/streaming.md).

1. [Crea un set di dati in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Facoltativo) Se utilizzi i dati di classificazione in Adobe Analytics, puoi aggiungere i dati di classificazione al set di dati in Customer Journey Analytics.

   A questo scopo, [crea un set di dati di ricerca per ogni dimensione contenente i dati di classificazione](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Per le implementazioni Adobe Analytics che utilizzano AppMeasurement o l&#39;estensione Analytics (tag), [crea uno stream di dati in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Per le implementazioni Adobe Analytics che utilizzano il Web SDK, esiste già uno stream di dati. Per ulteriori informazioni, consulta [Configurare l&#39;implementazione di Adobe Analytics Web SDK esistente per inviare dati a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md).

1. [Aggiungi Adobe Experience Platform come servizio al tuo flusso di dati](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Facoltativo) Se desideri integrare Customer Journey Analytics con Adobe Journey Optimizer, utilizza l’oggetto di personalizzazione nella tua implementazione per l’utilizzo in Adobe Journey Optimizer.

1. Espandi la sezione che descrive come implementare Experience Platform Web SDK per l’implementazione di Customer Journey Analytics, quindi completa i passaggi associati:

   +++Implementazione manuale (file JS)

   1. [Aggiungi alloy.js al tuo sito](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Popola un oggetto XDM e invialo allo stream di dati.

+++

   +++Tag

   1. [Creare una proprietà tag e aggiungere l&#39;estensione Adobe Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Aggiungere l’estensione Adobe Experience Platform Web SDK alla proprietà tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [Implementa il tag loader sul tuo sito](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Aggiungi la logica di raccolta dati XDM al tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Utilizza l’API di Edge Network per inviare dati allo stream di dati desiderato.

+++

1. [Verifica che l&#39;implementazione di Web SDK stia inviando dati a un set di dati](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Crea una connessione in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Facoltativo) Collega i dati web con dati provenienti da altri canali, ad esempio i dati del call center.

   A tale scopo, aggiungi set di dati aggiuntivi alla tua connessione Customer Journey Analytics, come descritto in [Importare dati web e call center](/help/use-cases/cross-channel/call-center.md).

1. [Creare una visualizzazione dati in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Verificare che i dati vengano inseriti nella visualizzazione dati in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [Migra progetti e componenti](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Facoltativo) Se utilizzi i canali di marketing in Adobe Analytics, puoi [creare un campo derivato dal canale di marketing in Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   I campi derivati sono un aspetto importante del reporting in tempo reale in Customer Journey Analytics. Un campo derivato consente di definire al volo manipolazioni di dati (spesso complesse) tramite un generatore di regole personalizzabile.

   Un utilizzo per i campi derivati consiste nel definire un campo Canale di marketing derivato che determina il canale di marketing appropriato in base a una o più condizioni (ad esempio, parametro URL, URL pagina o nome pagina).

   Utilizza [il modello di funzione canali di marketing](/help/data-views/derived-fields/derived-fields.md#marketing-channels) nei campi derivati per creare rapidamente un campo derivato per i canali di marketing.

1. Confronta i dati in Adobe Analytics dalla vecchia implementazione con i dati in Customer Journey Analytics dalla nuova implementazione e assicurati di comprendere eventuali differenze e perché esistono. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Acquisisci dati storici da Adobe Analytics utilizzando il connettore di origine di Analytics:

   >[!NOTE]
   >
   >Se non hai creato in precedenza un connettore di origine Analytics, procedi come segue.
   >
   >Se utilizzi già il connettore di origine Analytics con Customer Journey Analytics, segui i passaggi descritti in [Passaggio dal connettore di origine Analytics al Web SDK per Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Creare uno schema XDM per il connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. Se non disponi già di un connettore di origine Analytics, [crea il connettore di origine Analytics e mappa i campi sullo schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      Oppure

      Se disponi già di un connettore di origine Analytics, [mappa i campi dal connettore di origine allo schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Aggiungere il set di dati del connettore di origine di Analytics alla connessione](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. Pianifica l’onboarding degli utenti.

   Come in Adobe Analytics, Analysis Workspace è lo strumento principale rivolto all’utente in Customer Journey Analytics. Tuttavia, quando si utilizza Analysis Workspace in Customer Journey Analytics, gli utenti devono essere consapevoli di alcune differenze chiave.

   Dovresti lasciare agli utenti il tempo necessario (3 - 6 mesi) per familiarizzare con le differenze chiave dell’utilizzo di Analysis Workspace in Customer Journey Analytics.

   Per informazioni su alcune delle differenze principali tra Adobe Analytics e Customer Journey Analytics, consulta [Guida per gli utenti di Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

1. Informazioni sul supporto delle funzionalità [ in Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). La maggior parte delle funzioni di Adobe Analytics sono supportate in Customer Journey Analytics e molte altre sono disponibili in Customer Journey Analytics.

1. Disattiva Adobe Analytics quando l’implementazione di Customer Journey Analytics Web SDK è completa e hai familiarità con i dati che stai raccogliendo.

   Adobe consiglia di mantenere l’ambiente Adobe Analytics in esecuzione per un periodo di tempo dopo l’implementazione di Customer Journey Analytics.

   Per ulteriori informazioni sugli usi di Adobe Analytics durante e dopo un aggiornamento, nonché sulla tempistica consigliata per la disattivazione di Adobe Analytics, vedi [Valutare per quanto tempo è necessario Adobe Analytics dopo l&#39;aggiornamento a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

## Genera in modo dinamico passaggi di aggiornamento per la tua organizzazione

A seconda di diversi fattori, come la cronologia e i vincoli delle risorse, i passaggi di aggiornamento consigliati descritti in [Comprendere i passaggi di aggiornamento consigliati](#1-understand-the-recommended-upgrade-steps) potrebbero non essere pratici per la tua organizzazione.

Per generare in modo dinamico i passaggi di aggiornamento per le circostanze specifiche dell&#39;organizzazione:

1. Completa il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

   Dopo aver completato il questionario, ti vengono fornite istruzioni dettagliate che descrivono i passaggi di aggiornamento ottimali e specifici per i requisiti aziendali. Questi sono i passaggi di aggiornamento più adatti per l’ambiente Adobe Analytics esistente e gli obiettivi per Customer Journey Analytics.

1. Segui le istruzioni dettagliate generate per effettuare l’aggiornamento a Customer Journey Analytics.

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->
