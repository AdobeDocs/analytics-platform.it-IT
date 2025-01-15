---
description: Visualizzare facilmente i dati di confronto in Analysis Workspace, ad esempio per effettuare confronti con il mese scorso, lo scorso anno e così via.
title: Visualizzazione con grafici combinati
feature: Visualizations
exl-id: 06faa997-3a4e-4c41-b64e-64a15ada6552
role: User
source-git-commit: c7cdeb29729af35d7554b19e395047b364f0b547
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 48%

---

# Combinato {#combo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_combo_button"
>title="Combinato"
>abstract="Crea rapidamente una visualizzazione con grafico combinato senza dover prima creare una tabella a forma libera."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*Questo articolo documenta la visualizzazione combinata in **Customer Journey Analytics**. Vedi [Combo](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts) per la versione **Adobe Analytics**di questo articolo.*

>[!ENDSHADEBOX]


La visualizzazione ![Commento](/help/assets/icons/ComboChart.svg) **[!UICONTROL Combo]** consente di creare rapidamente una visualizzazione di confronto senza dover prima creare una tabella. Puoi visualizzare chiaramente le tendenze nei dati con una combinazione di linee e barre.

Utilizza [!UICONTROL Combo] per:

* Confrontare gli ordini di questa settimana con quelli dello stesso periodo del mese scorso (e dell&#39;anno scorso).
* Analizzare e confrontare rapidamente più metriche (come [!UICONTROL Persons] e [!UICONTROL Revenue]) tra di loro sullo stesso grafico.
* Analizzare una metrica rispetto a una funzione (ad esempio [!UICONTROL Cumulative Average]) su un orizzonte temporale.

Aspetti da considerare:

* Aggiungere più confronti in un singolo [!UICONTROL Combo chart].
* Se aggiungi uno o più confronti, questi devono essere dello stesso tipo, ad esempio [!UICONTROL Time comparison].
* Puoi aggiungere fino a 5 confronti.
* Puoi applicare fino a 3 filtri a una metrica.
* Le metriche calcolate non sono supportate nei grafici combinati.

## Utilizzo

1. Aggiungi una visualizzazione ![Commento](/help/assets/icons/ComboChart.svg) [!UICONTROL Combo]. Vedi [Aggiungere una visualizzazione a un pannello](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)

1. Dall’elenco a discesa, seleziona una dimensione per l’asse X e una metrica per l’asse Y.

1. Selezionare il tipo di [!UICONTROL Line comparison] che si desidera utilizzare.

   | Tipo di confronto a linee | Definizione |
   | --- | --- |
   | **[!UICONTROL Time comparison]** | Il tipo di confronto più comune; ad esempio, è utile per paragonare i dati attuali a qualli di 4 settimane fa. Se hai selezionato [!UICONTROL Time comparison], effettua una selezione secondaria per definire il periodo di tempo che desideri confrontare.<p>![Confronto in linea con il periodo di tempo selezionato e il campo di selezione secondario per il periodo di tempo.](assets/combo-time-period.png) |
   | **[!UICONTROL Function]** | Potresti introdurre nel confronto una funzione come [!UICONTROL Average]. Visualizza l&#39;elenco delle [funzioni supportate](#supported-functions).<p>![Menu a discesa di confronto delle righe che mostra le funzioni selezionate e un elenco delle funzioni supportate disponibili.](assets/combo-functions.png) |
   | **[!UICONTROL Secondary metric]** | Per esempio, puoi confrontare [!UICONTROL Revenue] con un’altra metrica.<p>![Grafico combinato che confronta due metriche.](assets/combo-2metrics-settings.png) |

   {style="table-layout:auto"}

1. Seleziona **[!UICONTROL Build]**.

   L’output è simile al seguente:

   ![Grafico combinato che mostra il periodo corrente in un grafico a barre e il periodo di confronto nel grafico a linee ](assets/combo-output.png)

   Il periodo corrente viene visualizzato nel grafico a barre. Il grafico a linee rappresenta il periodo di confronto. I punti nel grafico a linee sono noti come *bar bells*.

## Funzioni supportate

Se si seleziona **[!UICONTROL Function]** come [!UICONTROL Line comparison type], viene restituita una funzione della metrica scelta.

| Funzione | Definizione |
| --- | --- |
| **[!UICONTROL Column Sum]** | Aggiunge tutti i valori numerici di una metrica all’interno di una colonna (negli elementi di una dimensione) |
| **[!UICONTROL Cumulative Average]** | Restituisce la media delle ultime N righe. |
| **[!UICONTROL Median]** | Restituisce la mediana di una metrica in una colonna. La mediana è il numero al centro di un insieme di numeri. La metà dei numeri ha valori che sono maggiori o uguali alla mediana e la metà dei numeri ha valori che sono minori o uguali alla mediana. |
| **[!UICONTROL Cumulative]** | Somma cumulativa di N righe. |
| **[!UICONTROL Column Maximum]** | Restituisce il valore più grande in un insieme di elementi dimensionali della colonna di una metrica. |
| **[!UICONTROL Mean]** | Restituisce la media aritmetica di una metrica. |
| **[!UICONTROL Column Minimum]** | Restituisce il valore più piccolo in un insieme di elementi dimensionali della colonna di una metrica. |

{style="table-layout:auto"}

Ecco un esempio della media cumulativa della metrica Ricavi:

![Grafico combinato con media cumulativa](assets/combo-cumul-avg.png)

Di seguito è riportato un esempio di grafico combinato con entrambe le funzioni di Media cumulativa e Media:

![Un grafico combinato che mostra le funzioni media cumulativa e media.](assets/combo-three-functions.png)

>[!MORELIKETHIS]
>
>[Aggiungi una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Impostazioni visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu di scelta rapida visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>