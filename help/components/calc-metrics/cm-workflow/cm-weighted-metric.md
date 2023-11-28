---
description: Mostra esempi di metriche filtrate e ponderate.
title: Metriche filtrate e ponderate
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 4%

---

# Metriche filtrate e ponderate

Mostra esempi di metriche filtrate e ponderate.

## Percentuale non recapitate filtrate {#section_D42F2452E4464948934063EB6F2DAAB4}

Questa semplice metrica filtrata mostra il tasso di mancato recapito solo per le pagine con più di 100 visite:

![Finestra di riepilogo che mostra le metriche applicate alle colonne 1 (Visite) e 2 (100) insieme alla Percentuale non recapitate. ](assets/cm_fbr.png)

Tieni presente che questa formula dipende da un intervallo di tempo coerente. Se esegui un rapporto per un singolo giorno, vale la pena esaminare qualsiasi pagina con più di 20 visite. Se lo esegui per un mese, potrebbe essere utile che il filtro includa più visite.

## Percentile percentuale di mancato recapito filtrata {#section_4F3E6D33A1FD438A932FA662B3510552}

Questo filtro mostra la Percentuale non recapitate per il primo 30% delle pagine, quando ordinato per visite.

![Se e poi filtrano mostrando la Percentuale non recapitate per il 30% delle pagine principali ordinate per visite.](assets/cm_wbr_2.png)

## Metrica ponderata {#section_F2D16B14569948289CF1310F9E6E3FC2}

Supponiamo di voler ordinare in generale per frequenza di rimbalzo, ma le pagine con visite più alte dovrebbero essere più in alto nell’elenco. Puoi creare una percentuale di mancato recapito ponderata simile alla seguente:

![Riepilogo con definizione per frequenza di rimbalzo per visite.](assets/cm_wbr.png)
