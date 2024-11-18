---
title: Passare dal connettore di origine di Analytics all’SDK per web per il Customer Journey Analytics
description: Scopri come passare a Web SDK dal connettore di origine di Analytics durante l’aggiornamento al Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Passare dal connettore di origine di Analytics all’SDK per web per il Customer Journey Analytics

>[!NOTE]
> 
>Usa le informazioni in questa pagina per rispondere alle domande nell&#39;elenco di controllo per l&#39;aggiornamento di [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

L’utilizzo del connettore di origine di Analytics come unica implementazione per il Customer Journey Analytics presenta alcuni svantaggi intrinseci. Se la tua organizzazione ha già effettuato l’aggiornamento al Customer Journey Analytics utilizzando solo l’implementazione del connettore di origine di Analytics, dovresti considerare il passaggio a un’implementazione Web SDK.

Adobe consiglia di utilizzare il connettore di origine di Analytics (per il trasferimento dei dati storici), in combinazione con una nuova implementazione dell’SDK web (per la raccolta dati continua).

## Comprendere vantaggi e svantaggi dell’utilizzo esclusivo del connettore di origine di Analytics

Per informazioni sui vantaggi e gli svantaggi dell&#39;utilizzo del connettore di origine Analytics, vedere [Utilizzare il connettore di origine Analytics esclusivamente per l&#39;aggiornamento al Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Spostarsi dal connettore di origine di Analytics all’SDK per web

Di seguito è riportato il processo di alto livello per passare dal connettore di origine di Analytics a un’implementazione composta sia dal connettore di origine di Analytics che da un’implementazione Web SDK:

1. Creare un&#39;implementazione Web SDK, come descritto in [Passaggi dettagliati consigliati per l&#39;aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) nell&#39;articolo [Passaggio da Adobe Analytics al Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Dopo aver configurato l’implementazione dell’SDK web, continua con il passaggio seguente.

1. Decidi se utilizzare lo schema Adobe Analytics o uno schema XDM nell’implementazione dell’SDK web.

   Per ulteriori informazioni, vedere [Scegliere lo schema per il Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

1. (Condizionale) Se prevedi di utilizzare lo schema Adobe Analytics, aggiungi alla connessione di Customer Journey Analytics il set di dati creato automaticamente dal connettore di origine Analytics.

   Per ulteriori informazioni, vedere [Aggiungere il set di dati del connettore di origine di Analytics alla connessione](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Condizionale) Se prevedi di creare uno schema XDM:

   1. [Creare uno schema XDM per il connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

   1. Aggiungi il set di dati creato automaticamente con il connettore di origine Analytics originale alla connessione di Customer Journey Analytics.

      Per ulteriori informazioni, consulta [Aggiungere il set di dati dal connettore di origine Analytics corrente alla connessione](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

   1. Elimina il connettore di origine originale di Analytics. <!-- need to add steps somewhere about how to do this -->

   1. [Crea un nuovo connettore di origine Analytics e mappa i campi](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).








