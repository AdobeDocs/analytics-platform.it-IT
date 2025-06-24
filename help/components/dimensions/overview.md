---
title: Panoramica delle dimensioni
description: Scopri cosa sono le dimensioni e come vengono utilizzate in Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 6cabedc5ed58dac450577fc3505be5f95b7a959d
workflow-type: ht
source-wordcount: '235'
ht-degree: 100%

---

# Panoramica delle dimensioni

Le dimensioni sono un tipo di componente in Customer Journey Analytics e vengono utilizzate per analizzare i dati. Ad esempio, puoi utilizzare le dimensioni per creare rapporti in [Analysis Workspace](/help/analysis-workspace/home.md) o in [Report Builder](/help/report-builder/rb-overview.md).

In Customer Journey Analytics le dimensioni sono di tipo illimitato; i valori possono essere numeri, testo, oggetti, elenchi o una combinazioni di tutti questi.

Un rapporto di base in Customer Journey Analytics presenta righe di dimensioni (solitamente valori stringa) rispetto a una colonna di metriche (solitamente valori numerici).

Ad esempio, se si combina la dimensione Pagina con la metrica Persone, si ottiene un rapporto di classificazione che presenta le pagine più visitate per numero di persone:

| Pagina | Persone |
| --- | ---: |
| Pagina Home | 800 |
| Pagina di prodotto | 500 |
| Pagina di acquisto | 100 |

{style="table-layout:fixed"}

Ogni dimensione rappresenta una parte o un facet diversi del sito. Puoi combinare una o più di queste dimensioni con una o più metriche per creare un rapporto desiderato.


## Creare le dimensioni

Gli amministratori di Customer Journey Analytics possono [creare le dimensioni in una visualizzazione dati](/help/data-views/create-dataview.md#components).

## Dimensioni standard

Quando crei una visualizzazione dati, per impostazione predefinita i seguenti componenti vengono aggiunti come dimensioni alla visualizzazione dati:

{{standard-dimensions}}


## Aggiungere descrizioni delle dimensioni

Gli amministratori di Customer Journey Analytics possono aggiungere descrizioni alle dimensioni e ad altri componenti nella visualizzazione dati o direttamente in Analysis Workspace. Per informazioni su come aggiungere descrizioni alle dimensioni, consulta [Aggiungere descrizioni dei componenti](/help/components/add-component-descriptions.md).

>[!MORELIKETHIS]
>
>[Insight più approfonditi sulla clientela con la funzione Profondità evento](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947#M576)
>

