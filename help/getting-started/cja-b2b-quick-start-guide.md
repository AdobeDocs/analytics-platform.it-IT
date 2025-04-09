---
title: Guida rapida B2B di Customer Journey Analytics
description: Guida rapida per B2B edition di Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
source-git-commit: 0e4e52cfd42db321c4a7a18a9b1473a67f87e785
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 22%

---

# Guida rapida di B2B edition

{{draft-b2b}}

Per implementare Customer Journey Analytics B2B edition, assicurati innanzitutto di comprendere i concetti e le funzionalità specifici di B2B. Inoltre, dovresti avere familiarità con il flusso di lavoro tradizionale per implementare Customer Journey Analytics.

Questo documento si concentra sul flusso di lavoro specifico per l’implementazione di Customer Journey Analytics.

## Prerequisiti

Per implementare Customer Journey Analytics B2B edition, si applicano i seguenti prerequisiti:

* Non si dispone dei [controlli di accesso e autorizzazioni](/help/technotes/access-control.md) necessari per fornire attività di amministrazione in Customer Journey Analytics.
* Hai acquistato il pacchetto del componente aggiuntivo Customer Journey Analytics B2B edition.


## Flusso di lavoro

| Attività | Dettagli |
| --- | --- |
| **Passaggio 1: inserire dati B2B in Experience Platform** | Questo passaggio, eseguito in Experience Platform, prevede diversi passaggi secondari:<ul><li>**Passaggio 1a: preparare lo schema dati**. Utilizza [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) per standardizzare i dati B2B e [definire schemi](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b) per i dati B2B.</li><li>**Passaggio 1b: creare un set di dati basato sullo schema**: i dati in Platform sono costituiti da set di dati, ad esempio dati dell&#39;account, dati dell&#39;opportunità, dati del gruppo di acquisto, dati della campagna, dati dell&#39;elenco di marketing, set di dati e-mail, set di dati CRM, set di dati POS e altro ancora. Ciascun set di dati è costituito da uno schema e da batch di dati. Puoi [creare un set di dati in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=it).</li><li>**Passaggio 1c: inserire dati in Experience Platform**: sono disponibili [diverse opzioni](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home).</li></ul> |
| **Passaggio 2: creare connessioni tra set di dati di Platform e Customer Journey Analytics** | Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti sui set di dati di Experience Platform devi prima stabilire una connessione tra i set di dati in Experience Platform e Workspace. Sono disponibili opzioni aggiuntive quando si configura una connessione con B2B edition. <br>Consulta [Creare o modificare una connessione](/help/connections/create-connection.md). |
| **Passaggio 3: creare visualizzazioni dati** | Una visualizzazione dati è *filtrata* dei dati. Puoi creare diverse visualizzazioni dati per la stessa connessione, con impostazioni diverse per timeout visita, attribuzione e altro ancora. Puoi creare più viste dati per un singolo set di dati. Quando si configura una visualizzazione dati con B2B edition, sono disponibili opzioni aggiuntive.<br>Consulta [Creare una visualizzazione dati](/help/data-views/create-dataview.md). |
| **Passaggio 4: creare rapporti sui dati multicanale in Workspace** | Dopo aver creato connessioni e visualizzazioni dati, analizza i dati B2B inseriti utilizzando la potenza e la flessibilità di Analysis Workspace.<br>Consulta [Eseguire analisi di base](/help/analysis-workspace/perform-basic-analysis.md) ed [Eseguire analisi avanzate](/help/analysis-workspace/perform-adv-analysis.md). |

## Caso d’uso

Il documento [Caso di utilizzo B2B](../data-ingestion/data-ingestion.md) fornisce un esempio di caso di utilizzo su come implementare Customer Journey Analytics B2B edition.
