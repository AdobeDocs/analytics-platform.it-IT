---
description: Un flusso interdimensionale consente di esaminare i percorsi seguiti dai clienti attraverso varie dimensioni.
title: Flussi interdimensionali
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 80522177d5258e4b5046b3872483ce2b482ae77d
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 8%

---

# Flussi interdimensionali

Un flusso interdimensionale ti consente di esaminare i percorsi seguiti dai clienti attraverso varie dimensioni. Questo articolo mostra come utilizzare questo flusso per due casi d’uso: interazioni ed eventi delle app mobili e come le campagne guidano le visite web

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## Interazioni ed eventi delle app mobili

La dimensione [!UICONTROL Screen Name] viene utilizzata in questo flusso di esempio per vedere come gli utenti utilizzano le varie schermate (scene) nell&#39;app. La schermata superiore restituita è **[!UICONTROL luma: content: ios: en: home]**, che è la home page dell&#39;app:

![Un flusso che mostra l&#39;elemento aggiunto.](assets/flowapp.png)

Per esplorare l&#39;interazione tra schermate e tipi di evento (come aggiungi al carrello, acquisti e altri) in questa app, trascina e rilascia la dimensione **[!UICONTROL Event Types]**:

* Per sostituire la dimensione, esegui le operazioni riportate di seguito.

  ![Flusso che mostra la dimensione Pagina trascinata in più aree.](assets/flowapp-replace.png)

* Al di fuori della visualizzazione del flusso corrente, per aggiungere la dimensione:

  ![Flusso che mostra la dimensione Pagina trascinata nello spazio vuoto alla fine.](assets/flowapp-add.png)

La visualizzazione di flusso seguente mostra il risultato dell&#39;aggiunta della dimensione **[!UICONTROL  Event Types]**. La visualizzazione fornisce informazioni su come gli utenti dell’app mobile si spostano attraverso le varie schermate dell’app prima di aggiungere prodotti al carrello, chiudere l’applicazione, visualizzare un’offerta e altro ancora.

![Un fLow che mostra i risultati della dimensione Pagina nella parte superiore dell&#39;elenco.](assets/flowapp-result.png)

## Come le campagne guidano le visite web

Desideri analizzare quali campagne sono all’origine delle visite al sito web. Si crea una visualizzazione di flusso con **[!UICONTROL Campaign Name]** come dimensione

![Dimensione nome campagna Web flusso](assets/flowweb.png)

L&#39;ultima dimensione **[!UICONTROL Campaign Name]** viene sostituita con la dimensione **[!UICONTROL Formatted Page Name]** e viene aggiunta un&#39;altra dimensione **[!UICONTROL Formatted Page Name]** alla fine della visualizzazione del flusso.

![Nome campagna Web di flusso e dimensione pagina Web](assets/flowweb-replace.png)

Puoi passare il cursore del mouse su uno dei flussi per visualizzare ulteriori dettagli. Ad esempio, quali campagne hanno generato un’estrazione dal carrello.

![Passaggio del mouse sul nome della campagna Web e sulla dimensione della pagina Web](assets/flowweb-hover.png)
