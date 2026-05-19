---
description: Scopri in che modo un flusso interdimensionale consente di esaminare i percorsi seguiti dagli utenti attraverso varie dimensioni.
title: Flussi interdimensionali
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
autotag-review: '2026-05-19T08:41:06.716Z'
TQID: 'https://experienceleague.adobe.com/1er03t5uOypgXP6sjFW3z7vbN8IucVak2OiDeUG-OaU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 5%

---

# Flussi interdimensionali

Un flusso interdimensionale ti consente di esaminare i percorsi seguiti dai clienti attraverso varie dimensioni. Questo articolo mostra come utilizzare questo flusso per due casi d’uso: interazioni ed eventi delle app mobili e come le campagne guidano le visite web

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## Interazioni ed eventi delle app mobili

La dimensione [!UICONTROL Nome schermo] viene utilizzata in questo flusso di esempio per vedere come gli utenti utilizzano le varie schermate (scene) nell&#39;app. La schermata superiore restituita è **[!UICONTROL luma: content: ios: en: home]**, che è la home page dell&#39;app:

![Un flusso che mostra l&#39;elemento aggiunto.](assets/flowapp.png)

Per esplorare l&#39;interazione tra schermate e tipi di evento (come aggiungi al carrello, acquisti e altri) in questa app, trascina e rilascia la dimensione **[!UICONTROL Tipi di evento]**:

* Per sostituire la dimensione, esegui le operazioni riportate di seguito.

  ![Flusso che mostra la dimensione Pagina trascinata in più aree.](assets/flowapp-replace.png)

* Al di fuori della visualizzazione del flusso corrente, per aggiungere la dimensione:

  ![Flusso che mostra la dimensione Pagina trascinata nello spazio vuoto alla fine.](assets/flowapp-add.png)

La visualizzazione di flusso seguente mostra il risultato dell&#39;aggiunta della dimensione **[!UICONTROL Tipi di evento]**. La visualizzazione fornisce informazioni su come gli utenti dell’app mobile si spostano attraverso le varie schermate dell’app prima di aggiungere prodotti al carrello, chiudere l’applicazione, visualizzare un’offerta e altro ancora.

![Un fLow che mostra i risultati della dimensione Pagina nella parte superiore dell&#39;elenco.](assets/flowapp-result.png)

## Come le campagne guidano le visite web

Desideri analizzare quali campagne sono all’origine delle visite al sito web. Crea una visualizzazione di flusso con **[!UICONTROL Nome campagna]** come dimensione

![Dimensione nome campagna Web flusso](assets/flowweb.png)

Sostituisci l&#39;ultima dimensione **[!UICONTROL Nome campagna]** con la dimensione **[!UICONTROL Nome pagina formattato]** e aggiungi un&#39;altra dimensione **[!UICONTROL Nome pagina formattato]** alla fine della visualizzazione del flusso.

![Nome campagna Web di flusso e dimensione pagina Web](assets/flowweb-replace.png)

Puoi passare il cursore del mouse su uno dei flussi per visualizzare ulteriori dettagli. Ad esempio, quali campagne hanno generato un’estrazione dal carrello.

![Passaggio del mouse sul nome della campagna Web e sulla dimensione della pagina Web](assets/flowweb-hover.png)
