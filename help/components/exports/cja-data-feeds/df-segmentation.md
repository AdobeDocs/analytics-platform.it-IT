---
title: Segmentazione nei feed dati
description: Scopri come applicare segmenti ai feed di dati di Customer Journey Analytics e come i segmenti di intervallo di date interagiscono con la finestra di reporting del feed.
keywords: clickstream;feed dati;feed dati;segmentazione;segmenti;intervallo date
feature: Components
hide: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: c7fc5df2a0fd7393b48bfe6bdfa7dccdfffde46c
workflow-type: tm+mt
source-wordcount: 357
ht-degree: 0%

---


# Segmentazione nei feed dati

{{release-limited-testing}}

I feed di dati in Customer Journey Analytics supportano la segmentazione, consentendo di filtrare quali righe sono incluse in ogni consegna di feed. Puoi applicare segmenti a livello di visualizzazione dati, di feed o di entrambi.

## Dove vengono applicati i segmenti

Puoi applicare segmenti a un feed di dati in due posizioni:

- **Visualizzazione dati**: segmento configurato nella visualizzazione dati che si applica a tutti i feed che utilizzano tale visualizzazione dati.
- **Feed dati**: segmento applicato direttamente a un singolo feed, oltre a qualsiasi segmento di visualizzazione dati.

Quando entrambi sono configurati, Customer Journey Analytics li combina; nell’output del feed vengono incluse solo le righe che soddisfano entrambi i segmenti.

## Segmenti che includono un intervallo di date

Puoi utilizzare segmenti che includono intervalli di date all’interno di un feed di dati. Tuttavia, l’intervallo di reporting è sempre definito dalla consegna pianificata del feed (oraria o giornaliera). Se un segmento contiene un intervallo di date, filtra le righe all’interno della finestra del feed dati senza spostare o espandere la finestra stessa.

Questo è diverso da Analysis Workspace, dove l’applicazione di un segmento che include un intervallo di date modifica la finestra di reporting attiva in modo che corrisponda all’intervallo di date del segmento.

## Qualificazione del segmento e intervallo di date di lookback

Per i segmenti che utilizzano un contenitore Persona o Sessione, la qualifica è determinata dall&#39;impostazione **Intervallo di date di lookback**, non solo dall&#39;intervallo di consegna. Se una persona è idonea all’interno dell’intervallo di date di lookback, vengono inclusi tutti gli eventi di tale persona nell’intervallo di consegna. L’impostazione del contenitore determina l’ambito:

- **Contenitore eventi**: sono inclusi solo gli eventi che corrispondono ai criteri del segmento all&#39;interno della finestra di consegna.
- **Contenitore sessione**: sono inclusi tutti gli eventi nelle sessioni qualificate all&#39;interno dell&#39;intervallo di consegna, in cui la qualifica della sessione viene valutata nell&#39;intervallo di date del lookback.
- **Contenitore persona**: tutti gli eventi all&#39;interno dell&#39;intervallo di consegna sono inclusi per qualsiasi persona qualificata durante l&#39;intervallo di date di lookback.

Per ulteriori informazioni sull&#39;intervallo di date del lookback e su come questo influisce sulla qualificazione dei segmenti, vedi [Creare un feed di dati](/help/components/exports/cja-data-feeds/create-feed.md).

