---
description: Scopri come visualizzare i dati di confronto in Analysis Workspace, ad esempio come creare confronti con il mese scorso, l’anno scorso e così via.
title: Combinato
feature: Visualizations
exl-id: 06faa997-3a4e-4c41-b64e-64a15ada6552
role: User
TQID: https://experienceleague.adobe.com/ZJeq9DcK3JpxCTuzLec1pahJSTUES3rhEC-5avBmqpE
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 617
ht-degree: 65%

---

# Combinato {#combo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_combo_button"
>title="Combinato"
>abstract="Crea rapidamente una visualizzazione con grafico combinato senza dover prima creare una tabella a forma libera."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo descrive la visualizzazione combinata in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._

_Consulta [Combinato](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]


La visualizzazione ![Grafico combinato](/help/assets/icons/ComboChart.svg) **[!UICONTROL Combo]** consente di creare rapidamente una visualizzazione di confronto senza dover prima creare una tabella. Puoi visualizzare chiaramente le tendenze nei dati con una combinazione di linee e barre.

Utilizza un [!UICONTROL Combo] per:

* Confrontare gli ordini di questa settimana con quelli nello stesso periodo dello scorso mese (e dello scorso anno).
* Analizza e confronta rapidamente più metriche (come [!UICONTROL Persone] e [!UICONTROL Ricavi]) tra di loro sullo stesso grafico.
* Analizzare una metrica rispetto a una funzione (ad esempio [!UICONTROL Media cumulativa]) su un orizzonte temporale.

Tieni presente che:

* È possibile aggiungere più confronti in un singolo [!UICONTROL grafico combinato].
* Se aggiungi uno o più confronti, questi devono essere dello stesso tipo, ad esempio [!UICONTROL Confronto temporale].
* Puoi aggiungere fino a 5 confronti.
* Puoi applicare fino a 3 segmenti a una metrica.
* Le metriche calcolate non sono supportate nei grafici combinati.

## Utilizzo

1. Aggiungi una visualizzazione ![Commento](/help/assets/icons/ComboChart.svg) [!UICONTROL Combo]. Consulta [Aggiungere una visualizzazione a un pannello](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)

1. Dai menu a discesa, seleziona una dimensione per l’asse X e una metrica per l’asse Y.

1. Selezionare il tipo di [!UICONTROL Confronto righe] che si desidera utilizzare.

   | Tipo di confronto a linee | Definizione |
   | --- | --- |
   | **[!UICONTROL Confronto delle ore]** | Il tipo di confronto più comune; ad esempio, è utile per paragonare i dati attuali a qualli di 4 settimane fa. Se hai selezionato [!UICONTROL Confronto ore], effettua una selezione secondaria per definire il periodo di tempo che desideri confrontare.<p>![Confronto a linee con il periodo di tempo selezionato e il campo della selezione secondaria del periodo di tempo.](assets/combo-time-period.png) |
   | **[!UICONTROL Funzione]** | È possibile introdurre nel confronto una funzione come [!UICONTROL Media]. Consulta l’elenco delle [funzioni supportate](#supported-functions).<p>![Menu a discesa del confronto a linee che mostra le funzioni selezionate e un elenco delle funzioni supportate disponibili.](assets/combo-functions.png) |
   | **[!UICONTROL Metrica secondaria]** | Ad esempio, puoi confrontare [!UICONTROL Ricavi] con un&#39;altra metrica.<p>![Un grafico combinato che confronta due metriche.](assets/combo-2metrics-settings.png) |

   {style="table-layout:auto"}

1. Seleziona **[!UICONTROL Genera]**.

   L’output è simile a:

   ![Un grafico combinato che mostra il periodo corrente in un grafico a barre e il periodo di confronto nel grafico a linee &#x200B;](assets/combo-output.png)

   Il periodo corrente viene visualizzato nel grafico a barre. Il grafico a linee rappresenta il periodo di confronto. I punti nel grafico a linee sono noti come *manubri*.

## Funzioni supportate

Se si seleziona **[!UICONTROL Funzione]** come tipo di confronto [!UICONTROL Linee], verrà restituita una funzione della metrica scelta.

| Funzione | Definizione |
| --- | --- |
| **[!UICONTROL Somma colonna]** | Somma tutti i valori numerici di una metrica all’interno di una colonna (negli elementi di una dimensione). |
| **[!UICONTROL Media cumulativa]** | Restituisce la media delle ultime N righe. |
| **[!UICONTROL Median (Mediano)]** | Restituisce la mediana di una metrica in una colonna. La mediana è il numero al centro di un insieme di numeri. Metà dei numeri è costituita da valori maggiori o uguali alla mediana e l’altra metà da quelli minori o uguali alla mediana. |
| **[!UICONTROL Cumulativo]** | Somma cumulativa di N righe. |
| **[!UICONTROL Massimo Colonna]** | Restituisce il valore più grande in un insieme di elementi dimensionali della colonna di una metrica. |
| **[!UICONTROL Mean (Media)]** | Restituisce la media aritmetica di una metrica. |
| **[!UICONTROL Minimo colonna]** | Restituisce il valore più piccolo in un insieme di elementi dimensionali della colonna di una metrica. |

{style="table-layout:auto"}

Ecco un esempio della media cumulativa della metrica Ricavi:

![Un grafico combinato che mostra la media cumulativa](assets/combo-cumul-avg.png)

Di seguito è riportato un esempio di grafico combinato con entrambe le funzioni di Media cumulativa e Media:

![Un grafico combinato che mostra le funzioni media cumulativa e media.](assets/combo-three-functions.png)

>[!MORELIKETHIS]
>
>[Aggiungi una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Impostazioni di visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu di scelta rapida della visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
