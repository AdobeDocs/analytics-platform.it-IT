---
description: 'null'
title: Configurare una visualizzazione di flusso
uuid: ff36dc09-6175-43ed-a82a-630d28bca806
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 93%

---


# Configurare una visualizzazione di flusso

>[!NOTE]
>
>Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Un rapporto di flusso consente di tenere traccia di un percorso attraverso le pagine o dimensioni, ad esempio eVar:

* Entrata (solo per dimensioni)
* Dimensioni o elementi
* Uscita (solo per dimensioni)

Ogni categoria è visualizzata come una “zona di rilascio”. Trascina gli elementi dall’elenco alla zona di rilascio desiderata. Le pagine e altri elementi che non sono dimensioni possono essere inseriti solo nella zona di rilascio centrale. Quando rilasci una dimensione nella zona centrale, viene automaticamente eseguito un rapporto in cui sono inseriti i principali elementi per tale dimensione.

Quando rilasci un elemento in una zona di rilascio, viene aperto il diagramma di flusso. Il contenuto del diagramma di flusso dipende dalla zona in cui si rilascia una dimensione o un elemento. Uscita ed Entrata mostrano tutti gli elementi per la dimensione (ad esempio, pagine) rilasciata nella relativa zona. Ad esempio, se rilasci una dimensione nella zona centrale, viene aperto il diagramma di flusso per tale zona.

![](assets/flow.jpg)

Passa il cursore del mouse sul nodo di interesse al centro del diagramma per visualizzare informazioni su tale nodo.

![](assets/flow4.jpg)

Il diagramma di flusso è interattivo. Passa il cursore del mouse sul diagramma per cambiare i dettagli visualizzati.

![](assets/flow2.jpg)

I percorsi nel diagramma sono proporzionali. I percorsi con maggiore attività sono più spessi.

Quando fai clic su un nodo nel diagramma, vengono visualizzati i dettagli per tale nodo. Ad esempio, se fai clic su **[!UICONTROL Search Results]** (Risultati ricerca) in alto a destra nel diagramma superiore illustrato qui sopra, il diagramma si espande per mostrare più dettagli sul nodo dei risultati di ricerca. Fai di nuovo clic sul nodo per chiuderlo.

![](assets/flow3.jpg)

Per impostazione predefinita, il diagramma mostra i primi cinque flussi. Se fai clic sul nodo **[!UICONTROL More]** (Altro) in fondo al diagramma, quest’ultimo si espande verso il basso per visualizzare altri cinque flussi. Continua a fare clic su **[!UICONTROL More]** (Altro) fino a visualizzare tutti i flussi disponibili.

Non vi è alcun limite alla navigazione nel diagramma di flusso.

Puoi anche esportare e analizzare ulteriormente il diagramma di flusso come parte del file .CSV di un progetto, da **[!UICONTROL Project]** (Progetto) > **[!UICONTROL Download CSV]** (Scarica CSV).
