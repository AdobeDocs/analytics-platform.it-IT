---
title: Algorithmic Attribution
description: Comprendere i dettagli del modello di attribuzione algoritmica.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
TQID: https://experienceleague.adobe.com/t9MaGZioEVgtaMgoTpemXlvulgaDFo-XBtM6-G8562Q
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 42%

---

# Attribuzione algoritmica

Il [modello di attribuzione](models.md) algoritmica in Analysis Workspace è diverso da altri modelli in quanto utilizza tecniche statistiche per allocare credito tra gli elementi dimensionali nel rapporto o nella tabella a forma libera. Come tutti gli altri modelli di attribuzione in Analysis Workspace, l’attribuzione algoritmica può essere utilizzata su qualsiasi dimensione o metrica. L’attribuzione algoritmica supporta segmentazione e raggruppamenti illimitati e distribuisce il 100% delle conversioni a una o più dimensioni nella tabella (nota anche come attribuzione &quot;frazionaria&quot;).

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Algorithmic attribution](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

L’algoritmo utilizzato per l’attribuzione è basato sul dividendo Harsanyi dalla teoria del gioco cooperativo. Il dividendo Harsanyi è una generalizzazione della soluzione del valore di Shapley (dal nome di Lloyd Shapley, un economista premio Nobel) per distribuire credito tra i giocatori in un gioco con contributi disuguali al risultato.

Ad alto livello, il calcolo dell’attribuzione del credito di conversione per ogni punto di contatto considera ogni punto di contatto di marketing all’interno di un intervallo di lookback come una coalizione di giocatori. A questa coalizione di giocatori, un surplus deve essere equamente distribuito. La distribuzione del surplus di ogni coalizione è determinata dal surplus creato in precedenza ricorsivamente da ogni subcoalizione.

Per maggiori dettagli, consulta gli articoli originali di John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Il risultato dell’attribuzione algoritmica differisce dagli altri modelli solo quando nell’intervallo di lookback sono presenti più punti di contatto. Le conversioni con un singolo punto di contatto ricevono un credito del 100% indipendentemente dal modello di attribuzione.
