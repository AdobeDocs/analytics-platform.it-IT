---
description: Visualizza facilmente i dati di confronto in Analysis Workspace, ad esempio per creare confronti con lo scorso mese, lo scorso anno e così via.
title: Visualizzazione con grafici combinati
feature: Visualizations
exl-id: 06faa997-3a4e-4c41-b64e-64a15ada6552
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 97%

---

# Combinato {#combo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_combo_button"
>title="Combinato"
>abstract="Crea rapidamente una visualizzazione con grafico combinato senza dover prima creare una tabella a forma libera."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo descrive la visualizzazione combinata in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

_Consulta [Combinato](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]


La visualizzazione con ![grafico combinato](/help/assets/icons/ComboChart.svg) **[!UICONTROL Combo]** consente di creare rapidamente una visualizzazione di confronto senza dover prima creare una tabella. Puoi visualizzare chiaramente le tendenze nei dati con una combinazione di linee e barre.

Utilizza una [!UICONTROL Combo] per:

* Confrontare gli ordini di questa settimana con quelli nello stesso periodo dello scorso mese (e dello scorso anno).
* Analizzare e confrontare rapidamente più metriche (come [!UICONTROL Persons] e [!UICONTROL Revenue]) tra di loro sullo stesso grafico.
* Analizzare una metrica rispetto a una funzione (ad esempio [!UICONTROL Cumulative Average]) su un orizzonte temporale.

Tieni presente che:

* Aggiungere più confronti in un singolo [!UICONTROL Combo chart].
* Se aggiungi uno o più confronti, questi devono essere dello stesso tipo, ad esempio [!UICONTROL Time comparison].
* Puoi aggiungere fino a 5 confronti.
* Puoi applicare fino a 3 segmenti a una metrica.
* Le metriche calcolate non sono supportate nei grafici combinati.

## Utilizzo

1. Aggiungi una visualizzazione ![Commento](/help/assets/icons/ComboChart.svg) [!UICONTROL Combo]. Consulta [Aggiungere una visualizzazione a un pannello](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)

1. Dai menu a discesa, seleziona una dimensione per l’asse X e una metrica per l’asse Y.

1. Seleziona il tipo di [!UICONTROL Line comparison] che desideri utilizzare.

   | Tipo di confronto a linee | Definizione |
   | --- | --- |
   | **[!UICONTROL Time comparison]** | Il tipo di confronto più comune; ad esempio, è utile per paragonare i dati attuali a qualli di 4 settimane fa. Se hai selezionato [!UICONTROL Time comparison], effettua una selezione secondaria per definire il periodo di tempo che desideri confrontare.<p>![Confronto a linee con il periodo di tempo selezionato e il campo della selezione secondaria del periodo di tempo.](assets/combo-time-period.png) |
   | **[!UICONTROL Function]** | Potresti introdurre nel confronto una funzione come [!UICONTROL Average]. Consulta l’elenco delle [funzioni supportate](#supported-functions).<p>![Menu a discesa del confronto a linee che mostra le funzioni selezionate e un elenco delle funzioni supportate disponibili.](assets/combo-functions.png) |
   | **[!UICONTROL Secondary metric]** | Per esempio, puoi confrontare [!UICONTROL Revenue] con un’altra metrica.<p>![Un grafico combinato che confronta due metriche.](assets/combo-2metrics-settings.png) |

   {style="table-layout:auto"}

1. Seleziona **[!UICONTROL Build]**.

   L’output è simile a:

   ![Un grafico combinato che mostra il periodo corrente in un grafico a barre e il periodo di confronto nel grafico a linee ](assets/combo-output.png)

   Il periodo corrente viene visualizzato nel grafico a barre. Il grafico a linee rappresenta il periodo di confronto. I punti nel grafico a linee sono noti come *manubri*.

## Funzioni supportate

Se selezioni **[!UICONTROL Function]** come [!UICONTROL Line comparison type], verrà restituita una funzione della metrica scelta.

| Funzione | Definizione |
| --- | --- |
| **[!UICONTROL Column Sum]** | Somma tutti i valori numerici di una metrica all’interno di una colonna (negli elementi di una dimensione). |
| **[!UICONTROL Cumulative Average]** | Restituisce la media delle ultime N righe. |
| **[!UICONTROL Median]** | Restituisce la mediana di una metrica in una colonna. La mediana è il numero al centro di un insieme di numeri. Metà dei numeri è costituita da valori maggiori o uguali alla mediana e l’altra metà da quelli minori o uguali alla mediana. |
| **[!UICONTROL Cumulative]** | Somma cumulativa di N righe. |
| **[!UICONTROL Column Maximum]** | Restituisce il valore più grande in un insieme di elementi dimensionali della colonna di una metrica. |
| **[!UICONTROL Mean]** | Restituisce la media aritmetica di una metrica. |
| **[!UICONTROL Column Minimum]** | Restituisce il valore più piccolo in un insieme di elementi dimensionali della colonna di una metrica. |

{style="table-layout:auto"}

Ecco un esempio della media cumulativa della metrica Ricavi:

![Un grafico combinato che mostra la media cumulativa](assets/combo-cumul-avg.png)

Di seguito è riportato un esempio di grafico combinato con entrambe le funzioni di Media cumulativa e Media:

![Un grafico combinato che mostra le funzioni media cumulativa e media.](assets/combo-three-functions.png)

>[!MORELIKETHIS]
>
>[Aggiungere una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Impostazioni di visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu di scelta rapida della visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
