---
title: Segmentazione nei feed dati di Customer Journey Analytics
description: Scopri come applicare segmenti ai feed di dati di Customer Journey Analytics e come i segmenti di intervallo di date interagiscono con la finestra di reporting del feed.
keywords: clickstream;feed dati;feed dati;segmentazione;segmenti;intervallo date
feature: Components
hide: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: f36723dab5500f728dd9ec267d97305aff604149
workflow-type: tm+mt
source-wordcount: 659
ht-degree: 2%

---


# Segmentazione nei feed dati

{{release-limited-testing}}

I feed di dati in Customer Journey Analytics supportano la segmentazione, consentendo di filtrare quali righe sono incluse in ogni consegna di feed. Puoi applicare segmenti a livello di visualizzazione dati, di feed o di entrambi.

## Dove vengono applicati i segmenti

Puoi applicare segmenti a un feed di dati in due posizioni:

- **Visualizzazione dati**: segmento configurato nella visualizzazione dati che si applica a tutti i feed che utilizzano tale visualizzazione dati.
- **Feed dati**: segmento applicato direttamente a un singolo feed, oltre a qualsiasi segmento di visualizzazione dati.

Quando entrambi sono configurati, Customer Journey Analytics li combina; nell’output del feed vengono incluse solo le righe che soddisfano entrambi i segmenti.

## Segmenti di intervallo di date

I segmenti che fanno riferimento a intervalli di date sono supportati nei feed di dati. Tuttavia, il comportamento è diverso da Analysis Workspace in modo importante: **le condizioni dell&#39;intervallo di date in un segmento non sovrascrivono l&#39;intervallo di date del reporting del feed.**

In Analysis Workspace, l’applicazione di un segmento di intervallo di date modifica la finestra di reporting attiva in modo che corrisponda all’intervallo di date del segmento. Nei feed di dati, l’intervallo di reporting è sempre definito dalla consegna pianificata del feed (su base oraria o giornaliera). Un segmento con una condizione di intervallo di date filtra le righe all’interno di tale finestra, senza spostare o espandere la finestra stessa.

Questo progetto è intenzionale. Consentendo ai segmenti di intervallo di date di ignorare l’intervallo di reporting, un feed orario potrebbe fornire una finestra di dati molto più ampia del previsto, con conseguente duplicazione dei dati o volume di output eccessivo.

### Esempi

**Esempio 1: segmento che include eventi da una data specifica**

Supponiamo di applicare un segmento che restituisce solo gli eventi dal 1° luglio ed eseguire il feed per il 22 luglio:

- La finestra di consegna dei feed rimane il 22 luglio.
- Il segmento filtra tutte le righe, perché nessun evento nella finestra del 22 luglio corrisponde ai criteri del 1 luglio. Il feed viene eseguito ma non fornisce righe.
- Se esegui una retrocompilazione per il 1° luglio, il segmento si comporta come previsto; vengono inclusi solo gli eventi che corrispondono ai criteri del 1° luglio.

**Esempio 2: segmento che esclude gli eventi da una data specifica**

Supponiamo di applicare un segmento che esclude tutti gli eventi con un ordine il 1° luglio ed eseguire il feed per il 22 luglio:

- Il segmento si applica ai dati del 22 luglio. Poiché nella finestra del 22 luglio non sono presenti eventi del 1° luglio, non viene escluso nulla e vengono consegnate tutte le righe.
- Se esegui una retrocompilazione per il 1° luglio, il segmento esclude le righe rilevanti come previsto.

## Segmenti con più condizioni

Per i segmenti che combinano le condizioni dell’intervallo di date con altri criteri, Customer Journey Analytics valuta la parte dell’intervallo di date solo come filtro di riga, non come sostituzione della finestra di reporting. Tutte le condizioni nel segmento vengono rispettate all’interno della finestra di consegna del feed.

## Qualificazione del segmento e intervallo di date di lookback

Per i segmenti che utilizzano un contenitore Persona o Sessione, la qualifica è determinata dall&#39;impostazione **Intervallo di date di lookback**, non solo dall&#39;intervallo di consegna. Se una persona è idonea all’interno dell’intervallo di date di lookback, vengono inclusi tutti gli eventi di tale persona nell’intervallo di consegna. L’impostazione del contenitore determina l’ambito:

- **Contenitore eventi**: sono inclusi solo gli eventi che corrispondono ai criteri del segmento all&#39;interno della finestra di consegna.
- **Contenitore sessione**: sono inclusi tutti gli eventi nelle sessioni qualificate all&#39;interno dell&#39;intervallo di consegna, in cui la qualifica della sessione viene valutata nell&#39;intervallo di date del lookback.
- **Contenitore persona**: tutti gli eventi all&#39;interno dell&#39;intervallo di consegna sono inclusi per qualsiasi persona qualificata durante l&#39;intervallo di date di lookback.

Per ulteriori informazioni sull&#39;intervallo di date del lookback e su come questo influisce sulla qualificazione dei segmenti, vedi [Creare un feed di dati](/help/components/exports/cja-data-feeds/create-feed.md).

## Confronto con Analysis Workspace

| Comportamento | Analysis Workspace | Feed di dati |
|---|---|---|
| Il segmento dell’intervallo di date sostituisce l’intervallo di reporting | Sì | No |
| Filtra i segmenti e le righe all’interno dell’intervallo di reporting | Sì | Sì |
| Si applica il segmento della visualizzazione dati | Sì | Sì |
| Segmento aggiuntivo applicato direttamente alla consegna | No | Sì |

{style="table-layout:auto"}
