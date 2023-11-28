---
description: Un istogramma è simile a un grafico a barre, ma con i numeri raggruppati in intervalli.
title: Istogramma
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 79%

---

# Istogramma

Un istogramma è simile a un grafico a barre, ma con i numeri raggruppati in intervalli. Analytics automatizza la creazione di intervalli di numeri, ma puoi comunque cambiare le impostazioni in [Impostazioni avanzate](#section_09D774C584864D4CA6B5672DC2927477).

## Creare un istogramma {#section_74647707CC984A1CB6D3097F43A30B45}

Per creare un istogramma:

1. Fai clic su **[!UICONTROL Visualizations]** nella barra a sinistra.
1. Trascina **[!UICONTROL Histogram]** nel pannello.
1. Scegli una metrica da trascinare sulla visualizzazione Istogramma e fai clic su **[!UICONTROL Build]**.

![Pannello istogramma vuoto che mostra il campo Rilascia una metrica sotto.](assets/histogram.png)

>[!NOTE]
>
>Gli istogrammi supportano solo metriche standard; le metriche calcolate non sono supportate.

In questo esempio abbiamo usato la metrica Visualizzazioni di pagina per Visitatori uninovi. Il primo bucket (a sinistra) corrisponde a 1 visualizzazione di pagina per persona univoca, il secondo a due visualizzazioni di pagina, ecc.

![](assets/histogram2.png)

## Impostazioni avanzate {#section_09D774C584864D4CA6B5672DC2927477}

Per regolare le impostazioni dell’istogramma, fai clic sull’icona Impostazioni (a forma di ingranaggi) in alto a destra. Puoi modificare le seguenti impostazioni:

| Impostazioni istogramma | Funzione |
|---|---|
| Intervallo iniziale | Determina con quale intervallo inizia l’istogramma. L’impostazione predefinita è 1. Puoi impostare il numero iniziale da 0 all’infinito (non sono consentiti numeri negativi). |
| Intervalli di metrica | Puoi aumentare o ridurre il numero di intervalli di dati. Il numero massimo consentito è 50. |
| Dimensione intervalli di metrica | Puoi impostare la dimensione di ogni intervallo. Ad esempio, puoi cambiare la dimensione dell’intervallo da 1 a 2 visualizzazioni di pagina. |
| Metodo di conteggio | Consente di scegliere tra [Visitatore](https://experienceleague.adobe.com/docs/analytics/components/metrics/unique-visitors.html?lang=it), [Visita](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=it) o Tipo di hit. Ad esempio, visualizzazioni di pagina per visita, per persona o per evento. Per Hit, “Occorrenze” viene usato come metrica dell’asse y in una tabella a forma libera. |

<!--Russ or Meike - Check Hit Type link above. -->

**Esempi**:

* Con Intervallo iniziale: 1; Intervalli di metrica: 5; Dimensione intervalli di metrica: 2 viene generato l’istogramma: 1-2, 3-4, 5-6, 7-8, 9-10.
* Con Intervallo iniziale: 0; Intervalli di metrica: 3; Dimensione intervalli di metrica: 5 viene generato l’istogramma: 0-4, 5-9, 10-14.

## Visualizzare e modificare i dati dell’istogramma {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

Per visualizzare o modificare l’origine dei dati dell’istogramma, fai clic sul punto accanto all’intestazione Istogramma per passare a **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![Opzioni delle impostazioni dell’origine dati con l’opzione Mostra origine dati e blocca selezione selezionata.](assets/manage-data-source.png)

I filtri pregenerati che compaiono nella tabella sono filtri interni e non saranno visualizzati nel selettore dei filtri. Fai clic sul pulsante “i” accanto al nome del filtro, quindi fai clic su **[!UICONTROL Make public]** per rendere il filtro pubblico.

![Segmenti che mostrano la finestra di modifica e il collegamento Rendi pubblico.](assets/prebuilt_segments.png)

Per scoprire altri modi di gestire le tabelle di dati a forma libera e altre visualizzazioni, ad esempio per raggruppare i dati, visita [questa pagina](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=it).

## Post di blog

Consulta questo post di blog per informazioni su [utilizzo di istogrammi per identificare valori di dati imprevisti](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168).
