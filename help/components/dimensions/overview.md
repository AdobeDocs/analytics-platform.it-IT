---
title: Panoramica delle dimensioni
description: Scopri che cosa sono le dimensioni e come vengono utilizzate in Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: ed7e9a6c34c5f8ba9ba4f75be05768409cbc158d
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 30%

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

## Dimensioni predefinite

Quando crei una visualizzazione dati, i seguenti componenti basati sul tempo vengono aggiunti per impostazione predefinita come dimensioni alla visualizzazione dati:

- 15 minuti
- 30 minuti
- 5 minuti
- Giorno
- Giorno del mese
- Giorno della settimana
- Giorno dell’anno
- Ora
- Ora del giorno
- Minuto
- Minuto dell’Ora
- Mese
- Mese dell’anno
- Trimestre
- Trimestre dell’anno
- Secondi
- Settimana dell’anno
- Anno

## Aggiungere descrizioni delle dimensioni

Gli amministratori di Customer Journey Analytics possono aggiungere descrizioni per dimensioni e altri componenti sia all’interno della visualizzazione dati che direttamente all’interno di Analysis Workspace. Per informazioni su come aggiungere descrizioni alle dimensioni, consulta [Aggiungere descrizioni dei componenti](/help/components/add-component-descriptions.md).
