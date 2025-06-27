---
description: Utilizza la visualizzazione delle linee per rappresentare set di dati con tendenze (basati sul tempo).
title: Linee
feature: Visualizations
exl-id: b68aa8dc-2c96-4c49-8d3c-d94804aab479
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 98%

---

# Linee {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_line_button"
>title="Linee"
>abstract="Crea una visualizzazione a linee che mostra come cambiano i valori in un periodo di tempo. Una visualizzazione a linee può essere utilizzata solo quando si usa la dimensione tempo."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo descrive la visualizzazione Linee in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Consulta [Linee](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/visualizations/line) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]


La visualizzazione ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Line]** rappresenta le metriche con linee che mostrano come cambiano i valori nel tempo. Una visualizzazione a linee può essere utilizzata solo quando è utilizzata la dimensione temporale.

![Visualizzazione a linee](assets/line-viz.png)


## Impostazioni

Come parte delle [impostazioni di visualizzazione](freeform-analysis-visualizations.md#settings), sono disponibili impostazioni specifiche di visualizzazione a linee.

| Impostazione | Descrizione |
|---|---|
| **[!UICONTROL Granularity]** | Seleziona dall’elenco a discesa la granularità per cambiare una visualizzazione con tendenza da giornaliera a settimanale, mensile e così via. La granularità viene aggiornata anche nella tabella dell’origine dati. |
| **[!UICONTROL Show min]** <br/>**[!UICONTROL Show max]** | Puoi sovrapporre un’etichetta di valore minimo e massimo per evidenziare i valori minimo e massimo in una metrica. I valori minimo/massimo sono derivati dai punti di dati visibili nella visualizzazione e non dall’intero insieme di valori all’interno di una dimensione.<br/>![Sovrapposizione con l&#39;etichetta di valore minimo e massimo.](assets/min-max-labels.png) |
| **[!UICONTROL Show trendline]** | Puoi scegliere di aggiungere alla serie di linee una linea di tendenza di regressione o di media mobile. Le linee di tendenza consentono di rappresentare un pattern più chiaro nei dati. Quando è selezionata, seleziona un modello dall’elenco. Consulta [Modelli](#models) per una panoramica e una descrizione dei modelli disponibili.<br/>![Linea di tendenza lineare](assets/show-linear-trendline.png). |

>[!TIP]
>
>È consigliato applicare le linee di tendenza ai dati che non includono la data odierna (dati parziali) o date future. Le date odierne o future alterano la linea di tendenza. Tuttavia, se devi includere date future, rimuovi gli zeri dai dati per evitare distorsioni per quei giorni. Passa alla tabella dell’origine dati della visualizzazione, scegli la colonna della metrica, quindi abilita **[!UICONTROL Column Settings]** > **[!UICONTROL Interpret zero as no value]**.



### Modelli

Tutte le linee di tendenza del modello di regressione sono adattabili utilizzando i minimi quadrati ordinari:

| Modello | Descrizione |
| --- | --- |
| **[!UICONTROL Linear]** | Crea una linea retta di adattamento ottimale per set di dati lineari semplici, utile quando i dati aumentano o diminuiscono a un tasso costante. Equazione: `y = a + b * x` |
| **[!UICONTROL Logarithmic]** | Crea una linea curva di adattamento ottimale, utile quando il tasso di variazione nei dati aumenta o diminuisce rapidamente e poi si stabilizza. Una linea di tendenza logaritmica può utilizzare valori negativi e positivi. Equazione: `y = a + b * log(x)` |
| **[!UICONTROL Exponential]** | Crea una linea curva, utile quando i dati aumentano o diminuiscono a tassi costantemente crescenti. Questa opzione non deve essere utilizzata se i dati contengono valori zero o negativi. Equazione: `y = a + e^(b * x)` |
| **[!UICONTROL Power]** | Crea una linea curva, utile per i set di dati che confrontano misurazioni che aumentano a un tasso specifico. Questa opzione non deve essere utilizzata se i dati contengono valori zero o negativi. Equazione: `y = a * x^b` |
| **[!UICONTROL Quadratic]** | Trova l’adattamento ottimale per un set di dati a forma di parabola (concava verso l’alto o verso il basso). Equazione: `y = a + b * x + c * x^2` |
| **[!UICONTROL Moving average]** | Crea una linea di tendenza uniforme basata su un insieme di medie. Anche nota come media continua, la media mobile utilizza un numero specifico di punti di dati (determinati da una selezione di [!UICONTROL Granularity]), ne calcola la media e utilizza tale media come punto sulla linea. Alcuni esempi includono una media mobile di 7 giorni o di 4 settimane. |

>[!MORELIKETHIS]
>
>[Aggiungere una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Impostazioni di visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Menu di scelta rapida della visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

