---
description: Un flusso interdimensionale consente di esaminare i percorsi seguiti dai clienti attraverso varie dimensioni.
title: Flussi interdimensionali
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 73%

---

# Flussi interdimensionali

Un flusso interdimensionale consente di esaminare i percorsi seguiti dai clienti attraverso varie dimensioni.

Un’etichetta di dimensione all’inizio di ogni colonna Flusso facilita l’utilizzo di più dimensioni in una visualizzazione di flusso.

![Flusso interdimensionale che evidenzia più dimensioni, tra cui prodotto, pagina, versione del sistema operativo e tempo trascorso.](assets/flow.png)

Verranno esaminati due casi di utilizzo: per un’app e per un sito Web.

## Caso di utilizzo 1: app

La dimensione [!UICONTROL Action Name] (Nome azione) è stata aggiunta al flusso, e il primo elemento restituito è [!UICONTROL ItemAdded]:

![Un flusso che mostra l&#39;elemento aggiunto.](assets/multi-dimensional-flow.png)

Per scoprire l’interazione tra le schermate o pagine e le azioni dell’app, puoi trascinare la Dimensione pagina in più luoghi, a seconda di cosa ti interessa:

* Trascinala a una delle estremità della zona di rilascio (all’interno del rettangolo con bordo nero che viene visualizzato) per **sostituire** i primi risultati di tale estremità:

  ![Flusso che mostra la dimensione Pagina trascinata in più aree.](assets/multi-dimensional-flow2.png) ![Diagramma di flusso che mostra gli elementi trascinati.](assets/multi-dimensional-flow3.png)

* Trascinala nello spazio bianco alla fine (osserva la parentesi quadra nera) per **aggiungere** altri dati alla visualizzazione:

  ![Flusso che mostra la dimensione Pagina trascinata nello spazio vuoto alla fine.](assets/multi-dimensional-flow4.png)

Quando si sostituisce l’elemento ItemScaled nella colonna a destra con la Dimensione pagina, si ottiene questo risultato. Il primo risultato ora diventa il primo risultato per la Dimensione pagina:

![Un fLow che mostra i risultati della dimensione Pagina nella parte superiore dell&#39;elenco.](assets/multi-dimensional-flow5.png)

Ora puoi vedere quanti clienti si stanno spostando tra le varie azioni e pagine. Per esplorare ulteriormente il flusso, fai clic sui vari nodi:

![Un flusso che mostra gli elementi aggiunti, gli elementi trascinati e la visualizzazione principale.](assets/multi-dimensional-flow6.png)

Quando si aggiunge un’altra dimensione Nome azione alla fine della visualizzazione, si ottiene questo risultato:

![Flusso che mostra il nome dell&#39;azione aggiunto.](assets/multi-dimensional-flow7.png)

Questo ti permette di ottenere informazioni approfondite e di apportare eventuali modifiche all’app che stai analizzando.

## Caso di utilizzo 2: web

Questo caso di utilizzo mostra come individuare le campagne che generano il maggior numero di accessi al sito Web.

Trascina la dimensione Nome campagna in un nuovo flusso:

![Un flusso che mostra la dimensione Nome campagna trascinata in un nuovo flusso.](assets/multi-dimensional-flow8.png)

Per vedere le pagine per le quali queste campagne generano traffico, trascina la dimensione Pagina a destra dei risultati del flusso per aggiungere altri dati alla visualizzazione:

![Flusso che mostra la dimensione Pagina trascinata a destra dei risultati del flusso.](assets/multi-dimensional-flow9.png)
