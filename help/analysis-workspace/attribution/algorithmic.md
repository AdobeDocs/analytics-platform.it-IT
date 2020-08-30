---
title: Attribuzione algoritmica
description: Dettagli sul modello di attribuzione algoritmica.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 78%

---


# Attribuzione algoritmica

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

>[!NOTE]
>
>**[!UICONTROL Algorithmic attribution]** è attualmente in fase di test limitati. Vedere [Versioni di  delle funzioni Adobe Analytics](https://docs.adobe.com/content/help/it-IT/analytics/landing/an-releases.html) per ulteriori informazioni.

L&#39;algoritmo [modello di attribuzione](models.md) in  Analysis Workspace differisce da altri modelli in quanto utilizza tecniche statistiche per allocare crediti tra le voci di dimensione nel rapporto o nella tabella a forma libera. Come tutti gli altri modelli di attribuzione in Analysis Workspace, può essere utilizzato su qualsiasi dimensione o metrica, supporta segmentazione e raggruppamenti illimitati e distribuisce il 100% delle conversioni alle dimensioni nella tabella (nota anche come attribuzione “frazionaria”).

L’algoritmo utilizzato per l’attribuzione è basato sul dividendo Harsanyi dalla teoria del gioco cooperativo. Il dividendo Harsanyi è una generalizzazione della soluzione del valore di Shapley (che prende il nome da Lloyd Shapley, un economista premio Nobel) per la distribuzione del credito tra i giocatori in un gioco con contributi disuguali al risultato.

Ad un livello elevato, il calcolo dell’attribuzione del credito di conversione per ogni punto di contatto considera ogni punto di contatto di marketing all’interno di un intervallo di lookback come una coalizione di giocatori a cui deve essere equamente distribuito un surplus. La distribuzione dell’eccedenza di ciascuna coalizione è determinata in base all’eccedenza precedentemente creata da ciascuna subcoalizione (o voci di dimensione precedentemente partecipanti) in modo ricorsivo. Per maggiori dettagli, consulta gli articoli originali di John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Il risultato dell’attribuzione algoritmica differisce dagli altri modelli solo quando nell’intervallo di lookback sono presenti più punti di contatto. Le conversioni con un singolo punto di contatto ricevono un credito del 100% indipendentemente dal modello di attribuzione.
