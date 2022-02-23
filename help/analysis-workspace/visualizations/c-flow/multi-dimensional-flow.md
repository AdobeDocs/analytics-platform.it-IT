---
description: Un flusso interdimensionale consente di esaminare i percorsi seguiti dai clienti attraverso varie dimensioni.
title: Flussi interdimensionali
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '335'
ht-degree: 100%

---

# Flussi interdimensionali

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Un flusso interdimensionale consente di esaminare i percorsi seguiti dai clienti attraverso varie dimensioni.

Un’etichetta di dimensione all’inizio di ogni colonna Flusso facilita l’utilizzo di più dimensioni in una visualizzazione di flusso.

![](assets/flow.png)

Verranno esaminati due casi di utilizzo: per un’app e per un sito Web.

## Caso di utilizzo 1: app

La dimensione [!UICONTROL Action Name] (Nome azione) è stata aggiunta al flusso, e il primo elemento restituito è [!UICONTROL ItemAdded]:

![](assets/multi-dimensional-flow.png)

Per scoprire l’interazione tra le schermate o pagine e le azioni dell’app, puoi trascinare la Dimensione pagina in più luoghi, a seconda di cosa ti interessa:

* Trascinala a una delle estremità della zona di rilascio (all’interno del rettangolo con bordo nero che viene visualizzato) per **sostituire** i primi risultati di tale estremità:

   ![](assets/multi-dimensional-flow2.png) ![](assets/multi-dimensional-flow3.png)

* Trascinala nello spazio bianco alla fine (osserva la parentesi quadra nera) per **aggiungere** altri dati alla visualizzazione:

   ![](assets/multi-dimensional-flow4.png)

Quando si sostituisce l’elemento ItemScaled nella colonna a destra con la Dimensione pagina, si ottiene questo risultato. Il primo risultato ora diventa il primo risultato per la Dimensione pagina:

![](assets/multi-dimensional-flow5.png)

Ora puoi vedere quanti clienti si stanno spostando tra le varie azioni e pagine. Per esplorare ulteriormente il flusso, fai clic sui vari nodi:

![](assets/multi-dimensional-flow6.png)

Quando si aggiunge un’altra dimensione Nome azione alla fine della visualizzazione, si ottiene questo risultato:

![](assets/multi-dimensional-flow7.png)

Questo ti permette di ottenere informazioni approfondite e di apportare eventuali modifiche all’app che stai analizzando.

## Caso di utilizzo 2: web

Questo caso di utilizzo mostra come individuare le campagne che generano il maggior numero di accessi al sito Web.

Trascina la dimensione Nome campagna in un nuovo flusso:

![](assets/multi-dimensional-flow8.png)

Per vedere le pagine per le quali queste campagne generano traffico, trascina la dimensione Pagina a destra dei risultati del flusso per aggiungere altri dati alla visualizzazione:

![](assets/multi-dimensional-flow9.png)
