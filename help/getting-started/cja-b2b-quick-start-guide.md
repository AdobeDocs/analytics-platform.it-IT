---
title: Guida introduttiva rapida a Customer Journey Analytics B2B
description: Guida introduttiva rapida a B2B Edition di Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 100%

---


# Guida introduttiva rapida a B2B Edition

Per implementare Customer Journey Analytics B2B Edition, assicurati innanzitutto di comprendere i concetti e le funzionalità specifici di B2B. Inoltre, dovresti avere familiarità con il flusso di lavoro tradizionale di implementazione di Customer Journey Analytics.

Questo documento è incentrato sul flusso di lavoro specifico per l’implementazione di Customer Journey Analytics.

## Prerequisiti

Per implementare Customer Journey Analytics B2B Edition, si applicano i seguenti prerequisiti:

* Disponi dei [controllo degli accessi e autorizzazioni](/help/technotes/access-control.md) necessari per eseguire attività di amministrazione in Customer Journey Analytics.
* Hai acquistato il pacchetto del componente aggiuntivo Customer Journey Analytics B2B Edition.


## Flusso di lavoro

| Attività | Dettagli |
| --- | --- |
| **Passaggio 1: inserire dati B2B in Experience Platform** | Questo passaggio, eseguito in Experience Platform, prevede diversi passaggi secondari:<ul><li>**Passaggio 1a: preparare lo schema dati**. Utilizza [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/home.html?lang=it) per standardizzare i dati B2B e [definire schemi](https://experienceleague.adobe.com/it/docs/experience-platform/rtcdp/schemas/b2b) per la gestione dei dati B2B.</li><li>**Passaggio 1b: creare un set di dati basato sullo schema**: i dati in Platform sono costituiti da set di dati, ad esempio dati dell’account, dati dell’opportunità, dati del gruppo acquisti, dati della campagna, dati dell’elenco di marketing, set di dati e-mail, set di dati CRM, set di dati POS e altro ancora. Ciascun set di dati è costituito da uno schema e da batch di dati. Puoi [creare un set di dati in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=it).</li><li>**Passaggio 1c: inserire dati in Experience Platform**. Sono disponibili [diverse opzioni](https://experienceleague.adobe.com/it/docs/experience-platform/ingestion/home).</li></ul> |
| **Passaggio 2: creare connessioni tra set di dati di Platform e Customer Journey Analytics** | Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per generare rapporti sui set di dati in Experience Platform occorre innanzitutto stabilire una connessione tra set di dati in Experience Platform e Workspace. Quando configuri una connessione con B2B Edition, hai a disposizione opzioni aggiuntive. <br>Consulta [Creare o modificare una connessione](/help/connections/create-connection.md). |
| **Passaggio 3: creare le visualizzazioni dati** | Una visualizzazione dati è una visualizzazione *filtrata* dei dati. Puoi creare diverse visualizzazioni dati per la stessa connessione, con diverse impostazioni per timeout visita, attribuzione e così via. Puoi creare più visualizzazioni dati per un singolo set di dati. Quando configuri una visualizzazione dati con B2B Edition, hai a disposizione opzioni aggiuntive.<br>Consulta [Creare una visualizzazione dati](/help/data-views/create-dataview.md). |
| **Passaggio 4: creare rapporti sui dati multicanale in Workspace** | Dopo aver creato connessioni e visualizzazioni dati, analizza i dati B2B che hai immesso utilizzando la potenza e la flessibilità di Analysis Workspace.<br>Consulta [Eseguire analisi di base](/help/analysis-workspace/perform-basic-analysis.md) ed [Eseguire analisi avanzate](/help/analysis-workspace/perform-adv-analysis.md). |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->