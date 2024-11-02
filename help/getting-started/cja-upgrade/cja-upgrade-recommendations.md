---
title: Percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ea16705e96047cbcf41e428d2018ea7c72b2afac
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 8%

---

# Aggiornamento da Adobe Analytics a Customer Journey Analytics

Prima di iniziare il processo di aggiornamento da Adobe Analytics al Customer Journey Analytics, scopri i passaggi di aggiornamento consigliati.

>[!NOTE]
>
>I passaggi di aggiornamento descritti in questa sezione sono i passaggi di aggiornamento consigliati che qualsiasi organizzazione può utilizzare per eseguire correttamente l’aggiornamento da Adobe Analytics a Customer Journey Analytics.
>
>Tuttavia, a seconda di diversi fattori, come la timeline e i vincoli delle risorse, i passaggi di aggiornamento consigliati potrebbero non essere pratici per la tua organizzazione. In questo caso, utilizza il [questionario di aggiornamento di Adobe Analytics al Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) per generare in modo dinamico passaggi di aggiornamento personalizzati in base alle circostanze specifiche della tua organizzazione.

## Passaggi di aggiornamento consigliati per la maggior parte delle organizzazioni

I passaggi consigliati per l’aggiornamento da Adobe Analytics a Customer Journey Analytics sono rappresentati da una nuova implementazione di Experience Platform Web SDK, il metodo di raccolta dei dati preferito per Customer Journey Analytics. In combinazione con l’SDK per web, Adobe consiglia inoltre di utilizzare il connettore di origine di Analytics per conservare i dati storici di Adobe Analytics e per eseguire confronti di dati affiancati.

Dopo la transizione completa al Customer Journey Analytics, il connettore di origine di Analytics può essere disattivato e l’SDK web di Experience Platform può essere utilizzato esclusivamente.

### Processo di aggiornamento consigliato di alto livello

1. **Implementa Experience Platform Web SDK**

   Una nuova implementazione di Experience Platform Web SDK è il modo migliore per raccogliere dati per il Customer Journey Analytics. Fornisce la base migliore per ottenere il massimo dal Customer Journey Analytics perché è il metodo più performante, semplice e a prova di futuro per l&#39;implementazione del Customer Journey Analytics.

   * Rapporti e disponibilità dei dati ad alte prestazioni perché Adobe Experience Platform è stato progettato per casi d’uso di personalizzazione in tempo reale

   * Consolidare l’implementazione per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)

   * Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)

1. **Configura il connettore di origine di Adobe Analytics**

   Per facilitare la transizione a utilizzando Experience Platform Web SDK con Customer Journey Analytics, Adobe consiglia inoltre di utilizzare il connettore di origine di Adobe Analytics. Questo consente di conservare in Customer Journey Analytics i dati storici e visualizzare i dati dell’implementazione Adobe Analytics esistente, insieme ai dati della nuova implementazione Experience Platform Web SDK.

   Il connettore di origine di Analytics consente di:

   * Trasferisci i dati storici della suite di rapporti di Adobe Analytics in Adobe Experience Platform e Customer Journey Analytics.

     Puoi mantenere in funzione il connettore di origine di Analytics per il tempo necessario a conservare i dati storici di Adobe Analytics.

   * Visualizza i dati raccolti con l’implementazione originale di Adobe Analytics (ad AppMeasurement, l’estensione Analytics o l’estensione Web SDK) all’interno del Customer Journey Analytics. Puoi confrontare questi dati affiancati a quelli della nuova implementazione dell’SDK web.

     Puoi mantenere in funzione il connettore di origine di Analytics fino a quando non avrai familiarità con le differenze. <!--elaborate on what those differences are? -->

   Il connettore di origine di Analytics come implementazione autonoma non è un metodo consigliato a lungo termine per l’utilizzo del Customer Journey Analytics. Ciò è dovuto a latenza elevata, schemi ingombranti e complessi, dipendenza dalla nomenclatura di Adobe Analytics (prop, eVar e così via) e difficoltà nel passare infine dal connettore di origine all’implementazione Web SDK consigliata.

### Passaggi di aggiornamento consigliati dettagliati

I passaggi seguenti mostrano la procedura consigliata per l’aggiornamento da Adobe Analytics a Customer Journey Analytics.

A seconda dell’ambiente e dei requisiti specifici della tua organizzazione, questi passaggi consigliati potrebbero non essere adatti alla tua organizzazione. In questo caso, utilizza il [questionario di aggiornamento di Adobe Analytics al Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) per generare in modo dinamico passaggi di aggiornamento personalizzati in base alle circostanze specifiche della tua organizzazione.

1. [Pianifica l&#39;architettura dello schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Crea lo schema personalizzato desiderato in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. [Crea un set di dati in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. Espandi la sezione che descrive l’implementazione Adobe Analytics corrente, quindi completa i passaggi associati:

   +++Per le implementazioni di Adobe Analytics che utilizzano AppMeasurement

   1. [Crea uno stream di dati in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

   +++Per le implementazioni di Adobe Analytics con estensione Analytics (tag)

   1. [Crea uno stream di dati in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

+++ Per le implementazioni di Adobe Analytics tramite Web SDK

   Non sono necessari passaggi aggiuntivi.

+++

1. [Aggiungi Adobe Experience Platform come servizio al tuo flusso di dati](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. Utilizza la tabella seguente per identificare le funzioni di Adobe Analytics che desideri continuare a utilizzare in Customer Journey Analytics, quindi utilizza le informazioni fornite per scoprire come configurarle come parte dell’aggiornamento a Customer Journey Analytics:

   | Funzione di Adobe Analytics | Requisiti di attuazione per il Customer Journey Analytics | Informazioni aggiuntive |
   |---------|----------|---------|
   | Dati di classificazione | Crea un set di dati di ricerca per ogni dimensione contenente i dati di classificazione. |  |
   | Canali di marketing | Crea un campo derivato dal canale di marketing. |  |
   | Sovrapposizione Activity Map e tracciamento dei collegamenti | N/D | Adobe sta attualmente lavorando sul supporto di sovrapposizione Activity Map per il Customer Journey Analytics. |
   | Feed dati | Nessuna configurazione richiesta durante l’implementazione.<br/>[Scopri le varie opzioni di esportazione nel Customer Journey Analytics](/help/analysis-workspace/export/export-project-overview.md). | Anche se una sostituzione diretta dei feed di dati non è ancora disponibile nel Customer Journey Analytics, puoi esportare i rapporti di Customer Journey Analytics da Analysis Workspace per l’utilizzo in strumenti di terze parti o per combinarli con dati esterni. |
   | Data Warehouse | Nessuna configurazione richiesta durante l’implementazione.<br/>[Informazioni sull&#39;esportazione di tabelle complete nel Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md). | Esportazione tabella completa Customer Journey Analytics è l’evoluzione dei rapporti Data Warehouse in Adobe Analytics, con molte nuove funzioni spesso richieste che oggi non sono disponibili in Data Warehouse. |
   | Dati multimediali in streaming |  |  |

1. (Facoltativo) Acquisisci dati storici da Adobe Analytics utilizzando il connettore di origine di Analytics.

   Per ulteriori informazioni, vedere [Utilizzare un connettore di origine](/help/data-ingestion/sources.md#use-a-source-connector) in [Acquisire e utilizzare dati tramite i connettori di origine](/help/data-ingestion/sources.md).

1. Utilizzare la tabella seguente per identificare le funzionalità di Customer Journey Analytics desiderate, quindi utilizzare le informazioni fornite per scoprire come configurarle come parte dell&#39;aggiornamento al Customer Journey Analytics:

   | Funzioni Customer Journey Analytics desiderate | Requisiti di attuazione per il Customer Journey Analytics | Informazioni aggiuntive |
   |---------|----------|---------|
   | Collegare i dati web con dati provenienti da altri canali, ad esempio i dati del call center | Dopo aver creato una connessione (come descritto in un passaggio successivo), aggiungi ulteriori set di dati alla connessione in Customer Journey Analytics. |  |
   | Integrare con RTCDP | Abilita il profilo nello schema e crea un set di dati di profilo da utilizzare in RTCDP | Questa operazione deve essere eseguita durante la creazione dello schema XDM. |
   | Integrare con Adobe Journey Optimizer | Utilizzare l’oggetto di personalizzazione nell’implementazione per l’utilizzo in Adobe Journey Optimizer |  |

1. Espandi la sezione che descrive l’implementazione del Customer Journey Analytics desiderata, quindi completa i passaggi associati:

   +++Implementazione manuale (file JS)

   1. [Aggiungi alloy.js al tuo sito](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

+++

   +++Tag

   1. [Creare una proprietà tag nella raccolta dati di Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/quick-start#create-a-property).

+++

+++ API

   1. Utilizza l’API Edge Network per inviare dati allo stream di dati desiderato.

+++

1. [Crea una connessione nel Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. [Crea una visualizzazione dati nel Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Convalidare che i dati fluiscano nel Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [Migra progetti e componenti](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

1. Confronta i dati della vecchia implementazione con quelli della nuova implementazione e assicurati di comprendere tutte le differenze e il motivo per cui esistono.

1. Pianifica l’onboarding degli utenti.

   Come in Adobe Analytics, Analysis Workspace è lo strumento principale rivolto all’utente in Customer Journey Analytics. Tuttavia, quando si utilizza Analysis Workspace in Customer Journey Analytics, gli utenti devono essere consapevoli di alcune differenze chiave.

   Dovresti lasciare agli utenti il tempo necessario (3 - 6 mesi) per familiarizzare con le differenze chiave dell’utilizzo di Analysis Workspace in Customer Journey Analytics.

   Per informazioni su alcune delle differenze principali tra Adobe Analytics e Customer Journey Analytics, consulta [Guida per gli utenti di Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

1. Disattiva la raccolta dati di AppMeasurement.

1. Disattiva il connettore di origine di Analytics.

   Con l’implementazione Experience Platform Web SDK, il connettore di origine Analytics è necessario solo per i dati storici di Adobe Analytics e per confrontare i dati dell’implementazione originale con quelli della nuova implementazione.

   Se disponi di un numero sufficiente di dati storici dalla nuova implementazione e hai familiarità con le differenze di reporting nel Customer Journey Analytics, devi disattivare il connettore di origine di Analytics.

## Genera in modo dinamico passaggi di aggiornamento per la tua organizzazione

A seconda di diversi fattori, come la cronologia e i vincoli delle risorse, i passaggi di aggiornamento consigliati descritti in [Comprendere i passaggi di aggiornamento consigliati](#1-understand-the-recommended-upgrade-steps) potrebbero non essere pratici per la tua organizzazione.

Per generare in modo dinamico i passaggi di aggiornamento per le circostanze specifiche dell&#39;organizzazione:

1. Completa il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

   Dopo aver completato il questionario, ti vengono fornite istruzioni dettagliate che descrivono i passaggi di aggiornamento ottimali e specifici per i requisiti aziendali. Questi sono i passaggi di aggiornamento più adatti per allinearsi all’ambiente Adobe Analytics esistente e agli obiettivi di Customer Journey Analytics.

1. Segui le istruzioni dettagliate generate per effettuare l’aggiornamento al Customer Journey Analytics.

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









