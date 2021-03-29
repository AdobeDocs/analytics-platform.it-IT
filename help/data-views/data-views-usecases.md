---
title: Casi di utilizzo per le visualizzazioni dati in Customer Journey Analytics
description: Casi d’uso multipli che mostrano flessibilità e potenza delle visualizzazioni dati nel Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 7db2474bf3cd16863c597295399a262c328172dc
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---


# Casi di utilizzo delle visualizzazioni dati

Le possibilità di

## Creare una metrica Ordini da un campo di schema pageTitle (stringa)

Ad esempio, quando crei una visualizzazione dati, puoi creare una metrica [!UICONTROL Orders] da un campo di schema [!UICONTROL pageTitle] che è una stringa. Di seguito sono riportati i passaggi da seguire:

1. Nella scheda Componenti , trascina [!UICONTROL pageTitle] nella sezione [!UICONTROL Metrics] di [!UICONTROL Included Components].
   ![](assets/use-case1a.png)
1. Ora evidenzia la metrica appena trascinata e rinominala in [!UICONTROL Component Settings] a destra:
   ![](assets/orders.png)
1. Apri la finestra di dialogo [!UICONTROL Include/Exclude Values] a destra e specifica quanto segue:
   ![](assets/orders2.png)

   La frase &quot;di conferma&quot; indica che si tratta di un ordine. Dopo aver esaminato tutti i titoli delle pagine in cui tali criteri sono soddisfatti, viene conteggiato un &quot;1&quot; per ogni istanza. Il risultato è una nuova metrica (non una metrica calcolata). Funziona con Attribution IQ, filtri e ovunque puoi utilizzare metriche standard.
1. Puoi inoltre specificare un modello di attribuzione per questa metrica, ad esempio [!UICONTROL Last Touch], con [!UICONTROL Lookback window] di [!UICONTROL Session].
Puoi anche creare un’altra metrica [!UICONTROL Orders] dallo stesso campo e specificare un modello di attribuzione diverso, ad esempio [!UICONTROL First Touch], e un [!UICONTROL Lookback window] diverso, ad esempio [!UICONTROL 30 days].

## Creazione di più dimensioni da un campo schema

## Utilizzare i numeri interi come dimensioni

34:00

Incluso il bucket