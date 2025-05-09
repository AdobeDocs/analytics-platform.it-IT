---
title: Panoramica delle dimensioni
description: Scopri che cosa sono le dimensioni e come vengono utilizzate in Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 65b4339b4a1b27c41cfe442482a54661989d704b
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 25%

---

# Panoramica delle dimensioni

Le dimensioni sono un tipo di componente in Customer Journey Analytics utilizzato per analizzare i dati. Ad esempio, puoi utilizzare le dimensioni quando crei rapporti in [Analysis Workspace](/help/analysis-workspace/home.md) o in [Report Builder](/help/report-builder/rb-overview.md).

Le dimensioni di Customer Journey Analytics sono di tipo illimitato; i valori possono essere numerici, testo, oggetti, elenchi o combinazioni di tutti.

Un report di base in Customer Journey Analytics mostra righe di dimensioni (solitamente valori stringa) rispetto a una colonna di metriche (solitamente valori numerici).

Ad esempio, se hai combinato la dimensione Pagina con la metrica Persone, otterrai un rapporto con una classifica che mostra le pagine più visitate dalle persone:

| Pagina | Persone |
| --- | ---: |
| Pagina Home | 800 |
| Pagina prodotto | 500 |
| Pagina di acquisto | 100 |

{style="table-layout:fixed"}

Ogni dimensione rappresenta una parte o un facet diversi del sito. Puoi combinare una o più di queste dimensioni con una o più metriche per creare un rapporto desiderato.


## Creare dimensioni

Gli amministratori di Customer Journey Analytics possono [creare dimensioni in una visualizzazione dati](/help/data-views/create-dataview.md#components).

## Dimensioni standard

Quando crei una visualizzazione dati, i seguenti componenti vengono aggiunti per impostazione predefinita come dimensioni alla visualizzazione dati:

{{standard-dimensions}}


## Aggiungere descrizioni delle dimensioni

Gli amministratori di Customer Journey Analytics possono aggiungere descrizioni per dimensioni e altri componenti sia all’interno della visualizzazione dati che direttamente all’interno di Analysis Workspace. Per informazioni su come aggiungere descrizioni alle dimensioni, consulta [Aggiungere descrizioni dei componenti](/help/components/add-component-descriptions.md).
