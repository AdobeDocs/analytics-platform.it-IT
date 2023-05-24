---
description: La segmentazione di singole metriche consente di effettuare confronti di metriche all’interno dello stesso rapporto.
title: Metriche segmentate
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 2%

---

# Metriche filtrate

Nel generatore di metriche calcolate, puoi applicare filtri all’interno della definizione della metrica. Questa funzione è utile se desideri derivare nuove metriche da utilizzare nell’analisi. Tieni presente che le definizioni dei filtri possono essere aggiornate tramite il Generatore di filtri. Se vengono apportate modifiche, il filtro verrà aggiornato automaticamente ovunque venga applicato, incluso se fa parte di una definizione di metrica calcolata.

![](assets/german-visitors.png)

## Creare una metrica filtrata {#create}

Supponiamo che tu voglia confrontare diversi aspetti di un filtro &quot;Visitatori tedeschi&quot; con quelli di un filtro &quot;Visitatori internazionali&quot;. Puoi creare metriche che ti forniranno informazioni approfondite, ad esempio:

* Come si confrontano i comportamenti di navigazione del contenuto tra i due gruppi? Un altro esempio potrebbe essere: come si confronta il tasso di conversione tra i due filtri?
* In percentuale del totale delle persone, quante persone tedesche navigano in determinate pagine rispetto a persone internazionali?
* Quali sono le principali differenze in termini di contenuto a cui accedono questi diversi filtri?

1. Se non disponi di un filtro paragonabile, crea un segmento ad hoc nel generatore di metriche calcolate denominato &quot;Visitatori tedeschi&quot;, dove &quot;Paesi&quot; è uguale a &quot;Germania&quot;. Trascina la dimensione Paesi nell’area di lavoro Definizione e seleziona Germania come valore:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Puoi eseguire questa operazione anche nel [Generatore di filtri](/help/components/filters/create-filters.md), ma abbiamo semplificato il flusso di lavoro rendendo le dimensioni disponibili nel Generatore di metriche calcolate. &quot;Adhoc&quot; significa che il segmento non è visibile nel **[!UICONTROL Filters]** nella barra a sinistra. Tuttavia, puoi renderlo pubblico passando il puntatore sull’icona &quot;i&quot; accanto a esso e facendo clic su **[!UICONTROL Make public]**.

1. Se non disponi di un filtro paragonabile, crea un filtro denominato &quot;Visitatori internazionali&quot; in cui &quot;Paesi&quot; non è uguale a &quot;Germania&quot;.
1. Crea e salva una metrica denominata &quot;Visitatori tedeschi&quot; trascinando il filtro Germania nell’area di lavoro Definizione e la metrica Visitatori univoci al suo interno:

   ![](assets/german-visitors.png)

1. Ripeti il passaggio 3 con il segmento Visitatori internazionali e la metrica Visitatori univoci per creare una metrica Visitatori internazionali.
1. In Analysis Workspace, trascina **[!UICONTROL Page]** Dimension in una tabella a forma libera e trascina le due nuove metriche calcolate una accanto all’altra nella parte superiore:

   ![](assets/workspace-pages.png)

Panoramica video:

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

## Percentuale delle metriche totali {#percent-total}

Puoi portare l’esempio precedente più in là confrontando il filtro con una popolazione totale. Per farlo, crea due nuove metriche, &quot;% del totale dei visitatori tedeschi&quot; e &quot;% del totale dei visitatori internazionali&quot;:

1. Rilascia il filtro Visitatori tedeschi (o internazionali) nell’area di lavoro.
1. Rilascia qui sotto un altro filtro Visitatori tedeschi (o internazionali). Tuttavia, questa volta, fai clic sulla relativa icona di configurazione (ingranaggio) per selezionare il tipo di metrica &quot;Totale&quot;. Il formato deve essere &quot;Percentuale&quot;. L’operatore deve essere &quot;diviso per&quot;. Alla fine trovi questa definizione di metrica:

   ![](assets/cm_metric_total.png)

1. Applica questa metrica al progetto:

   ![](assets/cm_percent_total.png)
