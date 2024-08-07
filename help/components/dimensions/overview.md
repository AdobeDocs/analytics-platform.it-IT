---
title: Panoramica delle dimensioni
description: Scopri che cosa sono le dimensioni e come vengono utilizzate nel Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 1564c91616015311393a643fe7fcecd429cf3a36
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 37%

---

# Panoramica delle dimensioni

I Dimension sono un tipo di componente del Customer Journey Analytics utilizzato per analizzare i dati. Ad esempio, puoi utilizzare le dimensioni quando crei rapporti in [Analysis Workspace](/help/analysis-workspace/home.md) o nel [Report Builder](/help/report-builder/report-buider-overview.md).

Le dimensioni Customer Journey Analytics sono illimitate; i valori possono essere numerici, testo, oggetti, elenchi o combinazioni di tutti.

Un report di base in Customer Journey Analytics mostra righe di dimensioni (solitamente valori stringa) rispetto a una colonna di metriche (solitamente valori numerici).

Ad esempio, la combinazione della dimensione ‘Pagina’ con la metrica ‘Visite’, genererà un rapporto con classifica che mostra le pagine più visitate:

| `Page` | `Visits` |
| --- | --- |
| `Home page` | `800` |
| `Product page` | `500` |
| `Purchase page` | `100` |

Ogni dimensione rappresenta una parte o un facet diversi del sito. Puoi combinare una o più di queste dimensioni con una o più metriche per creare un rapporto desiderato.

## Creare dimensioni

Gli amministratori di Customer Journey Analytics possono [creare dimensioni in una visualizzazione dati](/help/data-views/create-dataview.md#components).

## Aggiungere descrizioni delle dimensioni

Gli amministratori di Customer Journey Analytics possono aggiungere descrizioni per dimensioni e altri componenti sia all’interno della visualizzazione dati che direttamente all’interno di Analysis Workspace. Per informazioni su come aggiungere descrizioni alle dimensioni, consulta [Aggiungere descrizioni dei componenti](/help/components/add-component-descriptions.md).
