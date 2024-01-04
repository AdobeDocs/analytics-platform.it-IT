---
description: È possibile suddividere dimensioni ed elementi dimensionali in Analysis Workspace.
keywords: Analysis Workspace
title: Suddividere dimensioni
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 92%

---

# Suddividere dimensioni in Workspace

È possibile suddividere dimensioni ed elementi dimensionali in Analysis Workspace.

Raggruppa i dati in tantissimi modi per ogni necessità; realizza query con metriche, dimensioni, filtri, linee temporali e altri valori rilevanti.

1. [Crea un progetto](/help/analysis-workspace/home.md) con una tabella di dati.
1. Nella tabella di dati, fai clic con il pulsante destro del mouse su un elemento e seleziona **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Risultato passaggio che mostra l’avviso di creazione dalla selezione selezionata.](assets/fa_data_table_actions.png)

   Puoi analizzare metriche per elementi dimensionali o filtri di pubblico in diversi periodi di tempo selezionati. Puoi anche effettuare analisi molto più dettagliate.

   >[!NOTE]
   >
   >È possibile mostrare nella tabella un massimo di 200 raggruppamenti. Questo limite aumenta per l’esportazione di raggruppamenti.

**Video: dimensioni in Analysis Workspace**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**Video: raggruppamenti delle dimensioni**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## Applicare modelli di attribuzione ai raggruppamenti

A qualsiasi raggruppamento all’interno di una tabella può essere applicato anche qualsiasi modello di attribuzione. Tale modello di attribuzione può essere lo stesso o diverso dalla colonna principale. Ad esempio, puoi analizzare gli ordini lineari sulla dimensione canali di marketing, ma applicare ordini a forma di U agli specifici codici di tracciamento all’interno di un canale. Per modificare il modello di attribuzione applicato a un raggruppamento, passa il cursore sul modello di raggruppamento e fai clic su **[!UICONTROL Edit]**:

![Confronto attribuzione ordine con le impostazioni del raggruppamento](assets/breakdown_settings.png)

Questo è il comportamento previsto quando si applicano modelli di attribuzione ai raggruppamenti o quando questi vengono modificati:

* Se applichi un’attribuzione quando non esistono altre attribuzioni, questa si applica all’intera struttura ad albero della colonna.

* Se aggiungi un raggruppamento dopo aver applicato un’attribuzione, utilizzerà l’impostazione predefinita per il raggruppamento specificato che è stato aggiunto (se tale dimensione ha un valore predefinito). In caso contrario, utilizzerà il raggruppamento dalla colonna padre. Alcune dimensioni hanno un’allocazione predefinita. Ad esempio, le dimensioni di Tempo e Referrer utilizzano Same Touch (Stesso contatto). La dimensione Prodotto utilizza Last Touch (Ultimo contatto). Altre dimensioni non hanno un valore predefinito e utilizzeranno l’allocazione della colonna padre.

* Se la struttura ad albero della colonna contiene già delle attribuzioni, la modifica dell’attribuzione ha effetto solo su quella che si sta modificando.

## Video

Aggiungere dimensioni e metriche al progetto in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/30606)

Utilizzo delle dimensioni nelle tabelle a forma libera:

>[!VIDEO](https://video.tv.adobe.com/v/40179)

Raggruppamenti delle dimensioni per posizione:

>[!VIDEO](https://video.tv.adobe.com/v/24033)
