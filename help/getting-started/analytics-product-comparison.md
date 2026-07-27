---
title: Confronto tra i prodotti Customer Journey Analytics
description: Confronta gli attributi del cliente degli strumenti di reporting ed esportazione di Percorsi Analytics, come Analysis Workspace, Report Builder, Esportazione di tabelle complete, feed di dati, API e MCP.
keywords: clickstream;feed dati;feed dati;confronto prodotti;Analysis Workspace;Report Builder;Esportazione tabella completa
feature: Components
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: d5ecbbc28bc3892a2114de2c73df3287f22cf1a0
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 58%

---


# Confronto tra i prodotti Analytics

Utilizza questa pagina per confrontare gli strumenti di reporting ed esportazione di Customer Journey Analytics sugli attributi chiave, per aiutarti a scegliere lo strumento giusto per le tue esigenze di analisi o esportazione dei dati.

| Nome del prodotto e collegamento all’Aiuto | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [Esportazione tabella completa](/help/analysis-workspace/export/export-cloud.md) | [Feed dati](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [API](https://developer.adobe.com/cja-apis/docs/) | MCP |
|---|---|---|---|---|---|---|
| **Metodo di accesso** | Browser | Microsoft Excel | Browser | Configurazione tramite browser | Strumenti API RESTful | Strumenti compatibili con MCP |
| **Granularità dei dati** | Aggregata | Aggregata | Aggregata | Evento | Aggregata | Aggregata |
| **Experience Cloud ID (ECID) disponibile** | No | No | Sì | Sì | No | No |
| **Timestamp disponibile** | No | No | No | Sì | No | No |
| **Livello di elaborazione** | Elaborazione completa | Elaborazione completa | Elaborazione completa | Elaborazione completa | Elaborazione completa | Elaborazione completa |
| **Dati filtro bot inclusi** | No | No | No | No | No | No |
| **Visualizzazione traffico ridotto (valori univoci eccessivi)** <br> [Ulteriori informazioni](/help/components/dimensions/high-cardinality.md) | Sì | Sì | No | No | Sì | Sì |
| **Limite righe visibili (prima dell’impaginazione)** | 400 | 50,000 | Senza limiti | Senza limiti | 50,000 | 50,000 |
| **Visualizzazioni dati multiple** | Sì | Sì | No | No | Sì | Sì |
| **Numero di raggruppamenti** | Senza limiti | Fino a 2 | Senza limiti | Senza limiti | Senza limiti, eseguito su più query | Senza limiti |
| **Segmentazione** <br> [Ulteriori informazioni](/help/components/segments/seg-overview.md) | Sì | Sì | Sì | Sì, con [limitazioni](/help/components/exports/cja-data-feeds/df-segmentation.md) | Sì | Sì |
| **Metriche calcolate** <br> [Ulteriori informazioni](/help/components/calc-metrics/calc-metr-overview.md) | Sì, con [Attribution](/help/analysis-workspace/attribution/overview.md) | Sì, con attribuzione | No | No | Sì, con attribuzione | Sì, con attribuzione |
| **Campi derivati** <br> [Ulteriori informazioni](/help/data-views/derived-fields/derived-fields.md) | Sì | Sì | Sì | Sì | Sì | Sì |
| **Analisi per coorte** | [Sì](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | No | No | No | No | No |
| **Attribuzione** <br> [Ulteriori informazioni](/help/analysis-workspace/attribution/overview.md) | Sì | Limitato | No | No | Sì | Sì |
| **Cura** <br> [Ulteriori informazioni](/help/analysis-workspace/curate-share/curate.md) | Sì, con nei progetti e nelle visualizzazioni dati | No | No | Sì, all’interno della visualizzazione dati | Sì, all’interno della visualizzazione dati | Sì, all’interno della visualizzazione dati |
| **Condivisione dei progetti** <br> [Ulteriori informazioni](/help/analysis-workspace/curate-share/share-projects.md) | Sì, con ruoli di progetto | No | No | No | No | No |
| **Consegna pianificata** | Sì | Sì | Sì | Sì | No | No |
| **Destinazioni di consegna** | E-mail | E-mail | Amazon S3, Azure RBAC, Azure SAS, GCP | Amazon S3, Azure RBAC, Azure SAS, GCP | — | — |
| **Elaborazione al momento del reporting della visualizzazione dati** <br> [Ulteriori informazioni](/help/data-views/data-views.md) | Sì | Sì | No | No | Sì | Sì |

{style="table-layout:auto"}
