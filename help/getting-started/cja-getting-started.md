---
title: Guida introduttiva all'analisi del percorso del cliente
description: Guida Introduttiva All'Analisi Del Percorso Del Cliente.
translation-type: tm+mt
source-git-commit: 1aebe79040b6c8b9eb8a336e158f5ce6d2ea16a4

---


# Guida introduttiva all&#39;analisi del percorso del cliente

Per implementare Analisi percorso cliente, devi seguire questo flusso di lavoro. Alcune attività iniziali vengono eseguite in Adobe Experience Platform, altre in Customer Journey Analytics.

## Prerequisiti

Analisi del percorso del cliente è disponibile per i clienti che

* Sono clienti Adobe Analytics [Select, Prime o Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) ?
* Sono predisposti per [Adobe Experience Platform](https://www.adobe.com/experience-platform.html)
* Hai acquistato lo SKU di analisi del percorso del cliente

## Flusso di lavoro

| Attività | Dove eseguito | Dettagli |
|---|---|---|
| **Passaggio 1: Preparare lo schema dati** | Adobe Experience Platform | Utilizzate [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) per standardizzare i dati sull&#39;esperienza cliente e definire schemi per la gestione dell&#39;esperienza cliente. |
| **Passaggio 2: Creare un dataset basato sullo schema** | Adobe Experience Platform | I dati in Piattaforma sono costituiti da set di dati, ad esempio set di dati e-mail, set di dati CRM, set di dati POS, set di dati Adobe Analytics, ecc. Ciascun set di dati è costituito da uno schema e da batch di dati. Puoi creare un set di dati [in Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).<br>Anche se lo schema per i set di dati che è possibile importare in Customer Journey Analytics è flessibile, deve essere conforme ad alcune regole di base. È consigliabile assicurarsi che i dati soddisfino questi requisiti prima di caricarli in Piattaforma. (Lo schema include metriche e dimensioni.)<br>Esistono tre tipi di dati compatibili con l&#39;analisi del percorso cliente:<ul><li>**Dati** evento: Dati che rappresentano eventi nel tempo (ad esempio visite Web, interazioni, transazioni, dati POS, dati sondaggio, dati ad impression, ecc.). Si tratta di dati tipici del clickstream, con un ID cliente o un ID cookie e una marca temporale. Con i dati dell’evento, vi consentiamo di utilizzare l’ID desiderato.</li><li>**Dati** di ricerca: Questi dati vengono utilizzati per cercare i valori o le chiavi presenti nei dati dell&#39;evento o del profilo. Ad esempio, potete caricare dati di ricerca che mappano ID numerici nei dati dell&#39;evento ai nomi di prodotto.</li><li>**Dati** profilo: Dati applicati ai visitatori, utenti o clienti nei dati dell’evento. Ad esempio, consente di caricare dati CRM sui clienti.</li></ul> |
| **Passaggio 3:creare connessioni tra set di dati della piattaforma e analisi del percorso cliente** | Customer Journey Analytics | Consultate [Creare una connessione](/help/connections/create-connection.md). |
| **Passaggio 4: Creazione di viste dati** | Customer Journey Analytics | Consultate [Creare una visualizzazione](/help/data-views/create-dataview.md)dati. |
| **Passaggio 5: Report sui dati multicanale in Workspace** | Customer Journey Analytics | Consultate [Eseguire analisi](/help/projects/perform-basic-analysis.md) di base ed [Eseguire analisi](/help/projects/perform-adv-analysis.md)avanzate. |

## Preparare lo schema dati

[Creazione di uno schema con l&#39;Editor di schema](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)


