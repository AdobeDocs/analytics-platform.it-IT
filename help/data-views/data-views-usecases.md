---
title: Casi di utilizzo per le visualizzazioni dati in Customer Journey Analytics
description: Casi d’uso multipli che mostrano flessibilità e potenza delle visualizzazioni dati nel Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 1%

---

# Casi d’uso per le visualizzazioni dati

Questi casi d’uso mostrano la flessibilità e la potenza delle visualizzazioni dati in Customer Journey Analytics.

## 1. Creare una metrica da un campo schema stringa

Ad esempio, durante la creazione di una visualizzazione dati, puoi creare una [!UICONTROL Orders] da una metrica [!UICONTROL pageTitle] campo schema che è una stringa. Di seguito sono riportati i passaggi da seguire:

1. Nella scheda Componenti , trascina il pulsante [!UICONTROL pageTitle] nel [!UICONTROL Metrics] sezione [!UICONTROL Included Components].
   ![](assets/use-case1a.png)
1. Ora evidenzia la metrica appena trascinata e rinominala in [!UICONTROL Component Settings] a destra:
   ![](assets/orders.png)
1. Apri [!UICONTROL Include/Exclude Values] a destra e specifica quanto segue:
   ![](assets/orders2.png)

   La frase &quot;di conferma&quot; indica che si tratta di un ordine. Dopo aver esaminato tutti i titoli delle pagine in cui tali criteri sono soddisfatti, viene conteggiato un &quot;1&quot; per ogni istanza. Il risultato è una nuova metrica (non una metrica calcolata). Una metrica con valori inclusi/esclusi può essere utilizzata ovunque sia possibile utilizzare qualsiasi altra metrica. Funziona con Attribution IQ, filtri e ovunque puoi utilizzare metriche standard.
1. Puoi inoltre specificare un modello di attribuzione per questa metrica, ad esempio [!UICONTROL Last Touch], con [!UICONTROL Lookback window] di [!UICONTROL Session].
Puoi anche crearne un altro [!UICONTROL Orders] dallo stesso campo e specifica un modello di attribuzione diverso, ad esempio [!UICONTROL First Touch]e un [!UICONTROL Lookback window], quali [!UICONTROL 30 days].

Un altro esempio potrebbe essere quello di utilizzare l’ID visitatore, una dimensione, come metrica per determinare quanti ID visitatore ha la tua azienda.

## 2. Utilizza i numeri interi come dimensioni

In precedenza, gli interi venivano trattati automaticamente come metriche in CJA. Ora le cifre (compresi gli eventi personalizzati da Adobe Analytics) possono essere trattate come dimensioni. Ecco un esempio:

1. Trascina [!UICONTROL call_length_min] numero intero [!UICONTROL Dimensions] sezione [!UICONTROL Included Components]:

   ![](assets/integers.png)

1. È ora possibile aggiungere [!UICONTROL Value Bucketing] per presentare questa dimensione in modo incassato nel reporting. (Senza bucket, ogni istanza di questa dimensione apparirà come una riga nel reporting di Workspace.)

   ![](assets/bucketing.png)

## 3. Utilizza le dimensioni numeriche come &quot;metriche&quot; nei diagrammi di flusso

Puoi utilizzare una dimensione numerica per ottenere &quot;metriche&quot; nel tuo [!UICONTROL  Flow] visualizzazione.

1. Sulle visualizzazioni dati [Componenti](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-component-settings) trascina [!UICONTROL Marketing Channels] campo schema nel [!UICONTROL Metrics] zona sotto [!UICONTROL Included components].
2. Nel reporting di Workspace, questo flusso viene visualizzato [!UICONTROL Marketing Channels] fluire in [!UICONTROL Orders]:

![](assets/flow.png)

## 4. Eseguire il filtro degli eventi secondari

Questa funzionalità è specifica per i campi basati su array. La funzionalità di inclusione/esclusione consente di filtrare a livello di sottoevento, mentre i filtri (segmenti) generati nel generatore di filtri consentono solo di filtrare a livello di evento. Puoi quindi eseguire il filtraggio degli eventi secondari utilizzando l’inclusione/esclusione nelle visualizzazioni dati, e quindi fare riferimento a tale nuova metrica/dimensione in un filtro a livello di evento.

Ad esempio, utilizza la funzionalità di inclusione/esclusione nelle visualizzazioni dati per concentrarti solo sui prodotti che hanno generato vendite per più di 50 Dollari. Quindi se hai un ordine che include un acquisto di prodotti da 50 Dollari e un acquisto di prodotti da 25 Dollari, rimuoveremo solo l&#39;acquisto di prodotti da 25 Dollari, non l&#39;intero ordine.

1. Sulle visualizzazioni dati [Componenti](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-component-settings) trascina [!UICONTROL Revenue] campo schema nel [!UICONTROL Metrics] zona sotto [!UICONTROL Included components].
1. Seleziona la metrica e configura quanto segue a destra: a) Sotto [!UICONTROL Format], seleziona [!UICONTROL Currency].
b) Sotto [!UICONTROL Currency], seleziona USD.
c. Sotto [!UICONTROL Include/Exclude Values], seleziona la casella di controllo accanto a [!UICONTROL Set include/exclude values].
d. Sotto [!UICONTROL Match], seleziona [!UICONTROL If all criteria are met].
e. Sotto [!UICONTROL Criteria], seleziona [!UICONTROL is greater than or equal].
f. Specifica &quot;50&quot; come valore.

Queste nuove impostazioni ti consentono di visualizzare solo i ricavi di alto valore e di filtrare tutto ciò che è inferiore a $50.

## 5. Utilizzare il [!UICONTROL No Value Options] impostazione

La tua azienda può aver passato del tempo a insegnare agli utenti ad aspettarsi &quot;Non specificato&quot; nei rapporti. Il valore predefinito in Visualizzazioni dati è &quot;No Value&quot;. Ora puoi [rinomina &quot;Nessun valore&quot; in &quot;Non specificato&quot;](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-no-value-options-settings) nell’interfaccia utente Visualizzazioni dati.

Un altro esempio potrebbe essere la dimensione per la registrazione di un programma di iscrizione. In questo caso, è possibile rinominare &quot;Nessun valore&quot; in &quot;Nessuna registrazione al programma di iscrizione&quot;.

## 6. Creazione di più metriche con diversi [!UICONTROL Attribution] impostazioni

Utilizzo della [!UICONTROL Duplicate] in alto a destra, crea un numero di metriche Revenue con diverse impostazioni di attribuzione come [!UICONTROL First Touch], [!UICONTROL Last Touch]e [!UICONTROL Algorithmic].

Non dimenticare di rinominare ogni metrica per riflettere le differenze, ad esempio &quot;Entrate algoritmiche&quot;:

![](assets/algo-revenue.png)

Per ulteriori informazioni sulle altre impostazioni di visualizzazione dati, vedi [Creare visualizzazioni dati](/help/data-views/create-dataview.md).
Per una panoramica concettuale delle visualizzazioni dati, vedi [Panoramica delle visualizzazioni dati](/help/data-views/data-views.md).
