---
description: Un flusso interdimensionale consente di esaminare i percorsi seguiti dai clienti attraverso varie dimensioni.
title: Flussi interdimensionali
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
source-git-commit: ab30cd4e884dbf92d4148e8f81a638a8ea0b63f3
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 73%

---

# Flussi interdimensionali

Un flusso interdimensionale consente di esaminare i percorsi seguiti dai clienti attraverso varie dimensioni.

Un’etichetta di dimensione all’inizio di ogni colonna Flusso facilita l’utilizzo di più dimensioni in una visualizzazione di flusso.

![Un flusso interdimensionale che evidenzia più dimensioni tra cui Prodotto, Pagina, Versione del sistema operativo e Tempo trascorso.](assets/flow.png)

Verranno esaminati due casi di utilizzo: per un’app e per un sito Web.

## Caso di utilizzo 1: app

La dimensione [!UICONTROL Action Name] (Nome azione) è stata aggiunta al flusso, e il primo elemento restituito è [!UICONTROL ItemAdded]:

![Un flusso che mostra l’elemento aggiunto.](assets/multi-dimensional-flow.png)

Per scoprire l’interazione tra le schermate o pagine e le azioni dell’app, puoi trascinare la Dimensione pagina in più luoghi, a seconda di cosa ti interessa:

* Trascinala a una delle estremità della zona di rilascio (all’interno del rettangolo con bordo nero che viene visualizzato) per **sostituire** i primi risultati di tale estremità:

  ![Un flusso che mostra la dimensione Pagina trascinata nelle aree multiple.](assets/multi-dimensional-flow2.png) ![Diagramma di flusso che mostra gli elementi trascinati.](assets/multi-dimensional-flow3.png)

* Trascinala nello spazio bianco alla fine (osserva la parentesi quadra nera) per **aggiungere** altri dati alla visualizzazione:

  ![Flusso che mostra la dimensione Pagina trascinata nello spazio vuoto alla fine.](assets/multi-dimensional-flow4.png)

Quando si sostituisce l’elemento ItemScaled nella colonna a destra con la Dimensione pagina, si ottiene questo risultato. Il primo risultato ora diventa il primo risultato per la Dimensione pagina:

![Un valore fLow che mostra i risultati della dimensione Pagina nella parte superiore dell’elenco.](assets/multi-dimensional-flow5.png)

Ora puoi vedere quanti clienti si stanno spostando tra le varie azioni e pagine. Per esplorare ulteriormente il flusso, fai clic sui vari nodi:

![Flusso che mostra gli elementi aggiunti, gli elementi trascinati e la vista principale.](assets/multi-dimensional-flow6.png)

Quando si aggiunge un’altra dimensione Nome azione alla fine della visualizzazione, si ottiene questo risultato:

![Un flusso che mostra il Nome azione aggiunto.](assets/multi-dimensional-flow7.png)

Questo ti permette di ottenere informazioni approfondite e di apportare eventuali modifiche all’app che stai analizzando.

## Caso di utilizzo 2: web

Questo caso di utilizzo mostra come individuare le campagne che generano il maggior numero di accessi al sito Web.

Trascina la dimensione Nome campagna in un nuovo flusso:

![Un flusso che mostra la dimensione Nome campagna trascinata in un nuovo flusso.](assets/multi-dimensional-flow8.png)

Per vedere le pagine per le quali queste campagne generano traffico, trascina la dimensione Pagina a destra dei risultati del flusso per aggiungere altri dati alla visualizzazione:

![Un flusso che mostra la dimensione Pagina trascinata a destra dei risultati del flusso.](assets/multi-dimensional-flow9.png)
