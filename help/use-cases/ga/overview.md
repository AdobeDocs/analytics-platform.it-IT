---
title: Migrazione di dati da Google Analytics al Customer Journey Analytics
description: Scopri il flusso di lavoro complessivo su come spostare i dati da Google Analytics a Adobe Experience Platform e come visualizzare i rapporti in Customer Journey Analytics.
source-git-commit: 7c195453490499cc42e7d5b2f2d111e2654f918c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Migrazione di dati da Google Analytics al Customer Journey Analytics

Se hai poca esperienza con il Customer Journey Analytics, è possibile che la tua organizzazione disponga di dati esistenti su un&#39;altra piattaforma Analytics, ad esempio Google Analytics. Puoi seguire questi passaggi generali per spostare tali dati in Adobe Experience Platform, consentendoti di visualizzare i rapporti in Customer Journey Analytics.

I flussi di lavoro vengono forniti sia per i dati storici che per la raccolta dati corrente. Puoi seguire uno o entrambi questi flussi di lavoro, a seconda delle esigenze di dati della tua organizzazione.

## Inserire dati storici da Google Analytics in Adobe Experience Platform

L’acquisizione di dati storici (backfill) comporta l’esportazione di dati da Google e l’importazione di tali dati in Adobe Experience Platform. Vedi [Inserire dati Google Analytics in Adobe Experience Platform](backfill.md).

Una volta inseriti correttamente i dati storici in Platform, puoi [Configura lo streaming dei dati correnti](streaming.md), oppure inizia immediatamente a generare rapporti sui dati precompilati in CJA da [Creazione di una connessione](/help/connections/create-connection.md).

## Configurare un&#39;implementazione Google Analytics esistente per Adobe Experience Platform {#configure}

L’inserimento dei dati correnti (in streaming) comporta l’invio di dati ad Adobe Experience Edge, che quindi li inoltra a Adobe Experience Platform. Vedi [Configurazione dei dati delle Google Analytics in streaming in Adobe Experience Platform](streaming.md).

## Configurare una connessione e una visualizzazione dati in CJA

Dopo aver acquisito correttamente i dati storici e/o configurato la raccolta dati in Adobe Experience Platform, puoi [Creare una connessione](/help/connections/create-connection.md) per consentire al Customer Journey Analytics di fare riferimento a tali dati.

Utilizzare la connessione per creare uno o più [Visualizzazioni dati](/help/data-views/create-dataview.md) da utilizzare in Analysis Workspace.

## Creare rapporti

Dopo aver configurato dimensioni e metriche all’interno di una visualizzazione dati, puoi iniziare a utilizzare Analysis Workspace per generare i rapporti desiderati. Vedi [Rapporto sui dati Google Analytics nel Customer Journey Analytics](report.md).
