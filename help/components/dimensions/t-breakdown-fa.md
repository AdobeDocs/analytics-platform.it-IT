---
description: È possibile suddividere dimensioni ed elementi dimensionali in Analysis Workspace.
keywords: Analysis Workspace
title: Suddividere dimensioni
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 42%

---

# Analisi di dimensioni in Workspace

È possibile suddividere dimensioni ed elementi dimensionali in Analysis Workspace.

Suddividi i tuoi dati in modo illimitato per le tue esigenze specifiche; crea query utilizzando metriche, dimensioni, filtri, linee temporali e altri valori di suddivisione dell’analisi rilevanti.

1. [Crea un progetto](/help/analysis-workspace/home.md) con una tabella di dati.
1. Nella tabella di dati, fai clic con il pulsante destro del mouse su un elemento e seleziona **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Risultato del passaggio](assets/fa_data_table_actions.png)

   Puoi suddividere le metriche per elementi dimensionali o per filtri per pubblico in diversi periodi di tempo selezionati. Puoi anche effettuare analisi molto più dettagliate.

   >[!NOTE]
   >
   >È possibile mostrare nella tabella un massimo di 200 analisi. Questo limite aumenta per le esportazioni.

**Video: Dimension in Analysis Workspace**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**Video: Analisi approfondita dei Dimension**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## Applicare modelli di attribuzione ai raggruppamenti

A qualsiasi raggruppamento all’interno di una tabella può essere applicato anche qualsiasi modello di attribuzione. Tale modello di attribuzione può essere lo stesso o diverso dalla colonna principale. Ad esempio, puoi analizzare gli ordini lineari sulla dimensione canali di marketing, ma applicare ordini a forma di U agli specifici codici di tracciamento all’interno di un canale. Per modificare il modello di attribuzione applicato a un raggruppamento, passa il cursore sul modello di raggruppamento e fai clic su **[!UICONTROL Edit]**:

![Impostazioni di raggruppamento](assets/breakdown_settings.png)

Questo è il comportamento previsto quando si applicano o si modificano modelli di attribuzione alle suddivisioni:

* Se applichi un’attribuzione quando non esistono altre attribuzioni, l’attribuzione si applica all’intero albero delle colonne.

* Se aggiungi un raggruppamento dopo aver applicato un’attribuzione, utilizza l’impostazione predefinita per il raggruppamento specificato aggiunto (se tale dimensione ha un valore predefinito). In caso contrario, utilizzerà la suddivisione dalla colonna padre. Alcune dimensioni hanno un&#39;allocazione predefinita. Ad esempio, le dimensioni Tempo e il referente utilizzano lo stesso contatto. La dimensione Prodotto utilizza Ultimo contatto. Altre dimensioni non hanno un valore predefinito e utilizzeranno l’allocazione della colonna padre.

* Se l’albero delle colonne contiene già delle attribuzioni, la modifica dell’attribuzione ha effetto solo su quella che si sta modificando.

## Video

Aggiunta di dimensioni e metriche al progetto in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/30606)

Utilizzo delle dimensioni nelle tabelle a forma libera:

>[!VIDEO](https://video.tv.adobe.com/v/40179)

Suddivisioni di Dimension per posizione:

>[!VIDEO](https://video.tv.adobe.com/v/24033)
