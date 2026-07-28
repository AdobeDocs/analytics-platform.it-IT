---
title: Confronto tra i prodotti Customer Journey Analytics
description: Confronta gli attributi del cliente degli strumenti di reporting ed esportazione di Percorsi Analytics, come Analysis Workspace, Report Builder, Esportazione di tabelle complete, feed di dati, API e MCP.
keywords: clickstream;feed dati;feed dati;confronto prodotti;Analysis Workspace;Report Builder;Esportazione tabella completa
feature: Components
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: e686fca2c77a8f9739298ece01ccf0fa2fe87b3b
workflow-type: tm+mt
source-wordcount: 464
ht-degree: 43%

---


# Confronto tra i prodotti Analytics

Utilizza questa pagina per confrontare gli strumenti di reporting ed esportazione di Customer Journey Analytics sugli attributi chiave, per aiutarti a scegliere lo strumento giusto per le tue esigenze di analisi o esportazione dei dati.

| Nome del prodotto e collegamento all’Aiuto | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [Esportazione tabella completa](/help/analysis-workspace/export/export-cloud.md) | [Feed dati](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [API](https://developer.adobe.com/cja-apis/docs/) | MCP | Estensione BI | Collaboratore |
|---|---|---|---|---|---|---|---|---|
| **Metodo di accesso** | Browser | Microsoft Excel | Browser | Configurazione tramite browser | Strumenti API RESTful | Strumenti compatibili con MCP | Strumenti BI | Strumenti compatibili con MCP |
| **Granularità dei dati** | Aggregata | Aggregata | Aggregata | Evento | Aggregata | Aggregata | Aggregata | Aggregata |
| **Experience Cloud ID (ECID) disponibile** | No | No | No | Sì | No | No | No | No |
| **Timestamp disponibile** | No | No | No | Sì | No | No | No | No |
| **Livello di elaborazione** | Elaborazione completa | Elaborazione completa, con rapporto in tempo reale separato | Elaborazione completa | Elaborazione completa | Elaborazione completa | Elaborazione completa | Elaborazione completa | Elaborazione completa |
| **Dove viene applicato il filtro bot** | All&#39;interno di [Datastream](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/bot-detection) e/o entro [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | All&#39;interno di [Datastream](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/bot-detection) e/o entro [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | All&#39;interno di [Datastream](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/bot-detection) e/o entro [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | All&#39;interno di [Datastream](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/bot-detection) e/o entro [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) |  |  | All&#39;interno di [Datastream](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/bot-detection) e/o entro [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | |
| **Limite righe visibili (prima dell’impaginazione)** | 400 | 50,000 | Limite di 3 milioni, 30 milioni, 150 milioni o 300 milioni, a seconda del livello | Dipende dal livello | 50,000 | 50,000 | 50,000 | 50,000 |
| **Visualizzazioni dati multiple** | Sì, un progetto può contenere dati provenienti da più visualizzazioni dati | Sì, un progetto può contenere dati provenienti da più visualizzazioni dati | No, un’esportazione può contenere dati provenienti da una sola visualizzazione dati | No, un’esportazione può contenere dati provenienti da una sola visualizzazione dati | No, ogni query può fare riferimento a una sola visualizzazione dati | No, ogni query può fare riferimento a una sola visualizzazione dati | No, ogni query può fare riferimento a una sola visualizzazione dati | Sì, se richiesto dall&#39;utente |
| **Numero di colonne della dimensione** | Fino a 5 | ? | Fino a 10 | Senza limiti | Fino a 5 | ? | ? | ? |
| **Numero di colonne di metrica** | ? | ? | Fino a 10 | Senza limiti | ? | ? | ? | ? |
| **Segmentazione** <br> [Ulteriori informazioni](/help/components/segments/seg-overview.md) | Sì | Sì | Sì | Sì, con [limitazioni](/help/components/exports/cja-data-feeds/df-segmentation.md) | Sì | Sì | Sì | Sì |
| **Metriche calcolate** <br> [Ulteriori informazioni](/help/components/calc-metrics/calc-metr-overview.md) | Sì | Sì | Sì, con [limitazioni](/help/analysis-workspace/export/export-cloud.md#calculated-metric-functions-support) | No | Sì | Sì | Sì | Sì |
| **Campi derivati** <br> [Ulteriori informazioni](/help/data-views/derived-fields/derived-fields.md) | Sì | Sì | Sì | Sì | Sì | Sì | Sì | Sì |
| **Attribuzione** <br> [Ulteriori informazioni](/help/analysis-workspace/attribution/overview.md) | Sì | Limitato | Sì, con [limitazioni](/help/analysis-workspace/export/export-cloud.md#attribution-behavior) | No | Sì | Sì | Sì | Sì |
| **Consegna pianificata** | Sì | Sì | Sì | Sì | — | — | — | — |
| **Destinazioni di consegna** | E-mail | E-mail | Amazon S3, Azure RBAC, Azure SAS, GCP | Amazon S3, Azure RBAC, Azure SAS, GCP | — | — | — | — |

{style="table-layout:auto"}
