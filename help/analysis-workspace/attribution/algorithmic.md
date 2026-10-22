---
title: Algorithmic Attribution
description: Comprendere i dettagli del modello di attribuzione algoritmica.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
autotag-review: '2026-05-19T07:20:44.651Z'
TQID: 'https://experienceleague.adobe.com/XPFzwdaB2d1PaGEyiYSlzri7Luo4E2uqlMdKClsExdw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: c91f8bd2-df97-4c6a-afcd-f1cde8221302
    internal-label: Attribution
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: c6330935bb6b36fab622b7884e9182ebd4bdc610
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 43%
---
# Attribuzione algoritmica

>[!NOTE]
>
>È necessario disporre del pacchetto Customer Journey Analytics **Ultimate** per utilizzare le funzionalità descritte in questa sezione. In caso di dubbi sul pacchetto di Customer Journey Analytics di cui disponi, contatta l’amministratore.

Il [modello di attribuzione](models.md) algoritmica in Analysis Workspace è diverso da altri modelli in quanto utilizza tecniche statistiche per allocare credito tra gli elementi dimensionali nel rapporto o nella tabella a forma libera. Come tutti gli altri modelli di attribuzione in Analysis Workspace, l’attribuzione algoritmica può essere utilizzata su qualsiasi dimensione o metrica. L’attribuzione algoritmica supporta segmentazione e raggruppamenti illimitati e distribuisce il 100% delle conversioni a una o più dimensioni nella tabella (nota anche come attribuzione &quot;frazionaria&quot;).

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Algorithmic attribution](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

L’algoritmo utilizzato per l’attribuzione è basato sul dividendo Harsanyi dalla teoria del gioco cooperativo. Il dividendo Harsanyi è una generalizzazione della soluzione del valore di Shapley (dal nome di Lloyd Shapley, un economista premio Nobel) per distribuire credito tra i giocatori in un gioco con contributi disuguali al risultato.

Il calcolo dell’attribuzione del credito di conversione per ogni punto di contatto considera ogni punto di contatto di marketing all’interno di un intervallo di lookback come una coalizione di giocatori. A questa coalizione di giocatori, un surplus deve essere equamente distribuito. La distribuzione del surplus di ciascuna coalizione è determinata dal surplus creato in precedenza in modo ricorsivo da ogni subcoalizione.

Per maggiori dettagli, consulta gli articoli originali di John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Il risultato dell’attribuzione algoritmica differisce dagli altri modelli solo quando nell’intervallo di lookback sono presenti più punti di contatto. Le conversioni con un singolo punto di contatto ricevono un credito del 100% indipendentemente dal modello di attribuzione.
