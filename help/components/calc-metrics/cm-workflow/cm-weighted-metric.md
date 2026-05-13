---
description: Mostra esempi di metriche calcolate.
title: Esempi di metriche calcolate
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
TQID: https://experienceleague.adobe.com/awAk0boIVigYBssgLcSz3t-5eExHhasCVDtwoa3v19k
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 252
ht-degree: 4%

---

# Esempi di metriche calcolate

Questo articolo mostra alcuni esempi su come definire metriche calcolate più avanzate.

## Percentuale mancati recapiti

Desideri calcolare la frequenza di mancato recapito.

+++ Dettagli

La definizione di un mancato recapito è oggetto di un&#39;altra discussione, ma per questo esempio si definisce un segmento di eventi di mancato recapito in cui Inizio sessione è uguale a 1 e Fine sessione è uguale a 1. Questo segmento consente di definire la frequenza delle sessioni non recapitate alle sessioni.


### Segmento

![Eventi di mancato recapito](assets/example-bounce-bouncedevents.png)

### Metrica calcolata

![Percentuale non recapitate](assets/example-bounce-rate.png)


### Campi derivati

In alternativa, è possibile definire un tasso di mancato recapito [ utilizzando campi derivati](/help/data-views/derived-fields/derived-fields.md#bounces).

I campi derivati fanno parte di una visualizzazione dati che presenta il vantaggio che non tutti gli utenti possono ignorare o modificare la definizione di una metrica del tasso di mancato recapito. Anche tale vantaggio ha introdotto una limitazione. Gli utenti che non hanno accesso a una visualizzazione dati non possono utilizzare campi derivati e devono ricorrere a segmenti e metriche calcolate per definire un tasso di mancato recapito.

Per ulteriori informazioni su come calcolare i mancati recapiti e il relativo tasso in Customer Journey Analytics, consulta questo [post di blog](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446).

+++


## Visualizzazioni pagina condizionali

Desideri definire una metrica calcolata che calcoli solo le visualizzazioni di pagina per le pagine visitate in oltre 100 sessioni.

+++ Dettagli 

![Visualizzazioni pagina condizionali](assets/conditional-page-views.png)

+++

## Visualizzazioni di pagina per il 30% delle prime sessioni

Desideri definire una metrica calcolata che calcoli solo le visualizzazioni di pagina per le prime 30% delle sessioni.

+++ Dettagli

![Prime 30% visualizzazioni di pagina](assets/top30-page-views.png)

+++
