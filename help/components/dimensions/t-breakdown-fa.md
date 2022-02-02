---
description: È possibile suddividere dimensioni ed elementi dimensionali in Analysis Workspace.
keywords: Analysis Workspace
title: Suddividere dimensioni
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
source-git-commit: 4bea8d7997d4084cfb87c1035689c0eea6b1f3b1
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 48%

---

# Analisi di dimensioni in Workspace

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

È possibile suddividere dimensioni ed elementi dimensionali in Analysis Workspace.

Suddividi i tuoi dati in modo illimitato per le tue esigenze specifiche; crea query utilizzando metriche, dimensioni, filtri, linee temporali e altri valori di suddivisione dell’analisi rilevanti.

1. [Crea un progetto](/help/analysis-workspace/home.md) con una tabella di dati.
1. Nella tabella di dati, fai clic con il pulsante destro del mouse su un elemento e seleziona **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Risultato del passaggio](assets/fa_data_table_actions.png)

   Puoi suddividere le metriche per elementi dimensionali o per filtri per pubblico in diversi periodi di tempo selezionati. Puoi anche effettuare analisi molto più dettagliate.

   >[!NOTE]
   >
   >È possibile mostrare nella tabella un massimo di 200 analisi. Questo limite aumenterà per le esportazioni.

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
