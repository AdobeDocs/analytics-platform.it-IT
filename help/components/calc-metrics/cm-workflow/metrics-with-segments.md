---
description: Il filtro per singole metriche consente di effettuare confronti di metriche all’interno dello stesso rapporto.
title: Metriche filtrate
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 1%

---

# Metriche filtrate

Nel generatore di metriche calcolate, puoi applicare filtri all’interno della definizione della metrica. Questa funzione è utile se desideri derivare nuove metriche da utilizzare nell’analisi. Tieni presente che le definizioni dei filtri possono essere aggiornate tramite il Generatore di filtri. Se vengono apportate modifiche, il filtro verrà aggiornato automaticamente ovunque venga applicato, incluso se fa parte di una definizione di metrica calcolata.

![Riepilogo e definizione dei filtri per Paesi = Germania e Visitatori univoci](assets/german-visitors.png)

## Creare una metrica filtrata {#create}

Supponiamo che tu voglia confrontare diversi aspetti di un filtro &quot;Visitatori tedeschi&quot; con quelli di un filtro &quot;Visitatori internazionali&quot;. Puoi creare metriche che ti forniranno informazioni approfondite, ad esempio:

* Come si confrontano i comportamenti di navigazione del contenuto tra i due gruppi? Un altro esempio potrebbe essere: come si confronta il tasso di conversione tra i due filtri?
* In percentuale del totale delle persone, quante persone tedesche navigano in determinate pagine rispetto a persone internazionali?
* Quali sono le principali differenze in termini di contenuto a cui accedono questi diversi filtri?

Crea e salva una metrica denominata &quot;Visitatori tedeschi&quot; e una metrica denominata &quot;Visitatori internazionali&quot;:

1. Crea un filtro ad hoc nel generatore di metriche calcolate denominato &quot;Visitatori tedeschi&quot;, dove &quot;Paesi&quot; è uguale a &quot;Germania&quot;. Trascina la dimensione Paesi nell&#39;area di lavoro Definizione e seleziona [!UICONTROL **Germania**] come valore:

   ![Il filtro ad hoc che mostra Paesi è uguale a Germania](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Puoi eseguire questa operazione anche nel [Generatore di filtri](/help/components/filters/create-filters.md), ma il flusso di lavoro è stato semplificato rendendo disponibili le dimensioni nel generatore di metriche calcolate. &quot;Adhoc&quot; significa che il filtro non è visibile nell&#39;elenco **[!UICONTROL Filters]** nella barra a sinistra. È tuttavia possibile renderlo pubblico passando il puntatore sull&#39;icona &quot;i&quot; accanto a esso e facendo clic su **[!UICONTROL Make public]**.

1. Trascina il filtro Germania nell’area di lavoro Definizione e al suo interno trascina la metrica Visitatori univoci:

   ![Riepilogo e definizione dei paesi uguali a Germania e Visitatori univoci](assets/german-visitors.png)

1. Seleziona [!UICONTROL **Salva**] per salvare la metrica calcolata.

1. Crea un filtro ad hoc nel generatore di metriche calcolate denominato &quot;visitatori internazionali&quot;, dove &quot;Paesi&quot; non è uguale a &quot;Germania&quot;.

   Trascina la dimensione Paesi nell&#39;area di lavoro Definizione, seleziona [!UICONTROL **Germania**] come valore, quindi seleziona [!UICONTROL **è diverso**] come operatore.

1. Trascina la metrica Visitatori univoci al suo interno.

1. Seleziona [!UICONTROL **Salva**] per salvare la metrica calcolata.

1. In Analysis Workspace, trascina il Dimension **[!UICONTROL Page]** in una tabella a forma libera e trascina le due nuove metriche calcolate una accanto all&#39;altra nella parte superiore:

   ![Tabella a forma libera che mostra la dimensione Pagina per i visitatori tedeschi e internazionali](assets/workspace-pages.png)

Panoramica video:

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

## Percentuale delle metriche totali {#percent-total}

Puoi portare l’esempio precedente più in là confrontando il filtro con una popolazione totale. Per farlo, crea due nuove metriche, &quot;% del totale dei visitatori tedeschi&quot; e &quot;% del totale dei visitatori internazionali&quot;:

1. Rilascia il filtro Visitatori tedeschi (o internazionali) nell’area di lavoro.
1. Rilascia qui sotto un altro filtro Visitatori tedeschi (o internazionali). Tuttavia, questa volta, fai clic sulla relativa icona di configurazione (ingranaggio) per selezionare il tipo di metrica &quot;Totale&quot;. Il formato deve essere &quot;Percentuale&quot;. L’operatore deve essere &quot;diviso per&quot;. Alla fine trovi questa definizione di metrica:

   ![Paesi è uguale a Germania e Totale visitatori univoci](assets/cm_metric_total.png)

1. Applica questa metrica al progetto:

   ![Tabella a forma libera con pagina e % di visitatori tedeschi totali](assets/cm_percent_total.png)
