---
title: Attribuzione algoritmica
description: Dettagli sul modello di attribuzione algoritmica.
feature: Attribution
exl-id: ce174253-4864-4fb0-8a96-a134a9fc9fba
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '298'
ht-degree: 100%

---

# Attribuzione algoritmica

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Ecco una panoramica video di Algorithmic Attribution:

>[!VIDEO](https://video.tv.adobe.com/v/36205/?quality=12)

Il [modello di attribuzione](models.md) algoritmica in Analysis Workspace è diverso da altri modelli in quanto utilizza tecniche statistiche per allocare credito tra gli elementi dimensionali nel rapporto o nella tabella a forma libera. Come tutti gli altri modelli di attribuzione in Analysis Workspace, può essere utilizzato su qualsiasi dimensione o metrica, supporta filtri e raggruppamenti illimitati e distribuisce il 100% delle conversioni alle dimensioni nella tabella (nota anche come attribuzione “frazionaria”).

L’algoritmo utilizzato per l’attribuzione è basato sul dividendo Harsanyi dalla teoria del gioco cooperativo. Il dividendo Harsanyi è una generalizzazione della soluzione del valore di Shapley (che prende il nome da Lloyd Shapley, un economista premio Nobel) per la distribuzione del credito tra i giocatori in un gioco con contributi disuguali al risultato.

Ad un livello elevato, il calcolo dell’attribuzione del credito di conversione per ogni punto di contatto considera ogni punto di contatto di marketing all’interno di un intervallo di lookback come una coalizione di giocatori a cui deve essere equamente distribuito un surplus. La distribuzione del surplus di ciascuna coalizione è determinata in base al surplus creato in precedenza da ogni subcoalizione (o dagli elementi dimensionali partecipanti in precedenza) in modo ricorsivo. Per maggiori dettagli, consulta gli articoli originali di John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!IMPORTANT]
>
>Il risultato dell’attribuzione algoritmica differisce dagli altri modelli solo quando nell’intervallo di lookback sono presenti più punti di contatto. Le conversioni con un singolo punto di contatto ricevono un credito del 100% indipendentemente dal modello di attribuzione.
