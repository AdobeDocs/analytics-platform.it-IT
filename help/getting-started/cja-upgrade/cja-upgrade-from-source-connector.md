---
title: Transizione dal connettore di origine di Analytics all’SDK web per il Customer Journey Analytics
description: Scopri come passare a Web SDK dal connettore di origine di Analytics durante l’aggiornamento al Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 0%

---

# Transizione dal connettore di origine di Analytics all’SDK web per il Customer Journey Analytics

>[!NOTE]
> 
>Usa le informazioni in questa pagina per rispondere alle domande nell&#39;elenco di controllo per l&#39;aggiornamento di [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

L’utilizzo del connettore di origine di Analytics come unica implementazione per il Customer Journey Analytics presenta alcuni svantaggi intrinseci.

Se la tua organizzazione ha già effettuato l’aggiornamento al Customer Journey Analytics utilizzando solo l’implementazione del connettore di origine di Analytics, prendi in considerazione la transizione a un’implementazione che utilizza il connettore di origine di Analytics (per trasferire i dati storici), insieme a una nuova implementazione dell’SDK web (per la raccolta dati in corso).

## Comprendere vantaggi e svantaggi dell’utilizzo esclusivo del connettore di origine di Analytics

Per informazioni sui vantaggi e gli svantaggi dell&#39;utilizzo del connettore di origine Analytics, vedere [Utilizzare il connettore di origine Analytics esclusivamente per l&#39;aggiornamento al Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Transizione dal connettore di origine di Analytics all’SDK per web

Di seguito è riportato il processo di alto livello per la transizione dall’utilizzo esclusivo del connettore di origine di Analytics a un’implementazione composta sia dal connettore di origine di Analytics che da un’implementazione Web SDK:

1. Creare un&#39;implementazione Web SDK, come descritto in [Passaggi dettagliati consigliati per l&#39;aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) nell&#39;articolo [Passaggio da Adobe Analytics al Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Dopo aver configurato l’implementazione dell’SDK web, continua con i passaggi seguenti.

1. [Creare uno schema XDM per il connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Mappa ogni dimensione di Adobe Analytics dal connettore di origine di Analytics alla dimensione nello schema dell’SDK web.

   1. 
      <!-- how do you get here -->

   1. Nella sezione **[!UICONTROL Map standard fields]** selezionare la scheda **[!UICONTROL Custom]**.

   1. Seleziona **[!UICONTROL Add new mapping]**.

      ![mappa campi schema](assets/schema-mapping.png)

   1. In **[!UICONTROL Source field]**, selezionare un campo Adobe Analytics dal gruppo di campi Modello Adobe Analytics ExperienceEvent. Quindi, in **[!UICONTROL Target field]**, seleziona il campo XDM a cui vuoi mappare.

   1. Ripeti questa procedura per ogni campo del gruppo di campi Modello Adobe Analytics ExperienceEvent che utilizzi per raccogliere dati in Adobe Analytics.

1. Aggiungi il set di dati creato automaticamente con il connettore di origine Analytics originale alla connessione di Customer Journey Analytics.

   Per ulteriori informazioni, consulta [Aggiungere il set di dati dal connettore di origine Analytics corrente alla connessione](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Condizionale) Se utilizzi i set di dati di ricerca, devi creare il set di dati di ricerca e aggiungerlo alla connessione. Per ulteriori informazioni, vedere [Creare set di dati di ricerca per classificare i dati nel Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Elimina il connettore di origine originale di Analytics. <!-- need to add steps somewhere about how to do this -->

1. [Crea un nuovo connettore di origine Analytics e mappa i campi](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).