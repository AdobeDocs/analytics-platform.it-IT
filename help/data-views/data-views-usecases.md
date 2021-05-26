---
title: Casi di utilizzo per le visualizzazioni dati in Customer Journey Analytics
description: Casi d’uso multipli che mostrano flessibilità e potenza delle visualizzazioni dati nel Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
source-git-commit: 7386645aa63ddbf1fcc8835037c13382e117ef1e
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# Casi di utilizzo delle visualizzazioni dati

Questi casi d’uso mostrano la flessibilità e la potenza delle visualizzazioni dati in Customer Journey Analytics.

## 1. Crea una metrica Ordini da un campo di schema pageTitle (stringa)

Ad esempio, quando crei una visualizzazione dati, puoi creare una metrica [!UICONTROL Orders] da un campo di schema [!UICONTROL pageTitle] che è una stringa. Di seguito sono riportati i passaggi da seguire:

1. Nella scheda Componenti , trascina [!UICONTROL pageTitle] nella sezione [!UICONTROL Metrics] di [!UICONTROL Included Components].
   ![](assets/use-case1a.png)
1. Ora evidenzia la metrica appena trascinata e rinominala in [!UICONTROL Component Settings] a destra:
   ![](assets/orders.png)
1. Apri la finestra di dialogo [!UICONTROL Include/Exclude Values] a destra e specifica quanto segue:
   ![](assets/orders2.png)

   La frase &quot;di conferma&quot; indica che si tratta di un ordine. Dopo aver esaminato tutti i titoli delle pagine in cui tali criteri sono soddisfatti, viene conteggiato un &quot;1&quot; per ogni istanza. Il risultato è una nuova metrica (non una metrica calcolata). Una metrica con valori inclusi/esclusi può essere utilizzata ovunque sia possibile utilizzare qualsiasi altra metrica. Funziona con Attribution IQ, filtri e ovunque puoi utilizzare metriche standard.
1. Puoi inoltre specificare un modello di attribuzione per questa metrica, ad esempio [!UICONTROL Last Touch], con [!UICONTROL Lookback window] di [!UICONTROL Session].
Puoi anche creare un’altra metrica [!UICONTROL Orders] dallo stesso campo e specificare un modello di attribuzione diverso, ad esempio [!UICONTROL First Touch], e un [!UICONTROL Lookback window] diverso, ad esempio [!UICONTROL 30 days].

## 2. Utilizza i numeri interi come dimensioni

In precedenza, gli interi venivano trattati automaticamente come metriche in CJA. Ora le cifre (compresi gli eventi personalizzati da Adobe Analytics) possono essere trattate come dimensioni. Ecco un esempio:

1. Trascina il numero intero [!UICONTROL call_length_min] nella sezione [!UICONTROL Dimensions] sotto [!UICONTROL Included Components]:

   ![](assets/integers.png)

1. È ora possibile aggiungere [!UICONTROL Value Bucketing] per presentare questa dimensione in modo fisso nel reporting. (Senza bucket, ogni istanza di questa dimensione apparirà come una riga nel reporting di Workspace.)

   ![](assets/bucketing.png)

## 3. Utilizza le dimensioni numeriche come &quot;metriche&quot; nei diagrammi di flusso

Puoi utilizzare una dimensione numerica per ottenere &quot;metriche&quot; nella visualizzazione [!UICONTROL  Flow].

1. Nella scheda Visualizzazioni dati [Componenti](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-component-settings) , trascina il campo schema [!UICONTROL Marketing Channels] nell’area [!UICONTROL Metrics] sotto [!UICONTROL Included components].
2. Nel reporting di Workspace, questo flusso mostra [!UICONTROL Marketing Channels] che scorre in [!UICONTROL Orders]:

![](assets/flow.png)

## 4. Eseguire il filtro degli eventi secondari

È possibile filtrare gli eventi per visualizzare solo ciò che si desidera visualizzare. Ad esempio, utilizza la funzionalità di inclusione/esclusione nelle visualizzazioni dati per concentrarti solo sui prodotti che hanno generato vendite per più di 50 Dollari. Quindi se hai un ordine che include un acquisto di prodotti da 50 Dollari e un acquisto di prodotti da 25 Dollari, rimuoveremo solo l&#39;acquisto di prodotti da 25 Dollari, non l&#39;intero ordine.

1. Nella scheda Visualizzazioni dati [Componenti](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-component-settings) , trascina il campo schema [!UICONTROL Orders] nell’area [!UICONTROL Metrics] sotto [!UICONTROL Included components].
1. Seleziona la metrica e configura quanto segue a destra:
   1. In [!UICONTROL Format], selezionare [!UICONTROL Currency].
   1. Alla voce [!UICONTROL Currency], selezionare USD.
   1. Sotto [!UICONTROL Include/Exclude Values], seleziona la casella di controllo accanto a [!UICONTROL Set include/exclude values].
   1. In [!UICONTROL Match], selezionare [!UICONTROL If all criteria are met].
   1. In [!UICONTROL Criteria], selezionare [!UICONTROL is greater than or equal].
   1. Specifica &quot;50&quot; come valore.

Per ulteriori informazioni sulle altre impostazioni delle visualizzazioni dati, consulta [Creare visualizzazioni dati](/help/data-views/create-dataview.md).
Per una panoramica concettuale delle visualizzazioni dati, consulta [Panoramica delle visualizzazioni dati](/help/data-views/data-views.md).