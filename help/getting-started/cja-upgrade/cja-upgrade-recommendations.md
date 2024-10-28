---
title: Percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 4%

---

# Aggiornamento da Adobe Analytics a Customer Journey Analytics

Prima di iniziare il processo di aggiornamento da Adobe Analytics al Customer Journey Analytics, scopri i passaggi di aggiornamento consigliati.

A seconda di diversi fattori, come la timeline e i vincoli delle risorse, i passaggi di aggiornamento consigliati potrebbero non essere pratici per la tua organizzazione. Dopo aver compreso i passaggi di aggiornamento consigliati, completa il questionario per generare in modo dinamico passaggi di aggiornamento personalizzati per le circostanze specifiche della tua organizzazione.

## 1. Comprendere i passaggi di aggiornamento consigliati

>[!NOTE]
>
>I passaggi di aggiornamento descritti in questa sezione sono i passaggi di aggiornamento consigliati che qualsiasi organizzazione può utilizzare per eseguire correttamente l’aggiornamento da Adobe Analytics a Customer Journey Analytics.
>
>Tuttavia, a seconda di diversi fattori, come la timeline e i vincoli delle risorse, i passaggi di aggiornamento consigliati potrebbero non essere pratici per la tua organizzazione. Dopo aver compreso i passaggi di aggiornamento consigliati, completa il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) per generare in modo dinamico passaggi di aggiornamento personalizzati per le circostanze specifiche della tua organizzazione.

I passaggi consigliati per l’aggiornamento da Adobe Analytics a Customer Journey Analytics sono rappresentati da una nuova implementazione di Experience Platform Web SDK, il metodo di raccolta dei dati preferito per Customer Journey Analytics. In combinazione con l’SDK per web, Adobe consiglia inoltre di utilizzare il connettore di origine di Analytics per conservare i dati storici di Adobe Analytics e per eseguire confronti di dati affiancati.

Dopo la transizione completa al Customer Journey Analytics, il connettore di origine di Analytics può essere disattivato e l’SDK web di Experience Platform può essere utilizzato esclusivamente.

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

## 2. Genera in modo dinamico passaggi di aggiornamento per l’organizzazione

A seconda di diversi fattori, come la cronologia e i vincoli delle risorse, i passaggi di aggiornamento consigliati descritti in [Comprendere i passaggi di aggiornamento consigliati](#1-understand-the-recommended-upgrade-steps) potrebbero non essere pratici per la tua organizzazione.

Per visualizzare i passaggi di aggiornamento generati in modo dinamico per le circostanze specifiche dell&#39;organizzazione:

1. Completa il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

   Dopo aver completato il questionario, ti vengono fornite istruzioni dettagliate che descrivono i passaggi di aggiornamento ottimali e specifici per la tua organizzazione. Questi sono i passaggi di aggiornamento più adatti per allinearsi all’ambiente Adobe Analytics esistente e agli obiettivi di Customer Journey Analytics.

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









