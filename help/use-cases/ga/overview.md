---
title: Migrazione dei dati da Google Analytics a Customer Journey Analytics
description: Scopri il flusso di lavoro generale per spostare i dati da Google Analytics a Adobe Experience Platform e visualizzare i rapporti in Customer Journey Analytics.
source-git-commit: 7c195453490499cc42e7d5b2f2d111e2654f918c
workflow-type: ht
source-wordcount: '304'
ht-degree: 100%

---

# Migrazione dei dati da Google Analytics a Customer Journey Analytics

Se hai poca esperienza con Customer Journey Analytics, è possibile che la tua organizzazione disponga di dati esistenti su un&#39;altra piattaforma Analytics, ad esempio Google Analytics. Puoi seguire questi passaggi generali per spostare tali dati in Adobe Experience Platform, consentendoti di visualizzare i rapporti su Customer Journey Analytics.

I flussi di lavoro vengono forniti sia per i dati storici che per la raccolta dati corrente. Puoi seguire uno o entrambi questi flussi di lavoro, a seconda delle esigenze di dati della tua organizzazione.

## Spostamento di dati storici da Google Analytics ad Adobe Experience Platform

L’acquisizione di dati storici (di recupero) comporta l’esportazione di dati da Google e l’importazione di tali dati su Adobe Experience Platform. Consulta [Inserire dati Google Analytics su Adobe Experience Platform](backfill.md).

Una volta inseriti correttamente i dati storici su Platform, puoi [configurare lo streaming dei dati correnti](streaming.md) o iniziare immediatamente a generare rapporti sui dati precompilati in CJA [creando una connessione](/help/connections/create-connection.md).

## Configurare un&#39;implementazione Google Analytics esistente per Adobe Experience Platform {#configure}

L&#39;acquisizione dei dati correnti (in streaming) comporta l’invio di dati ad Adobe Experience Edge, che in seguito li inoltra a Adobe Experience Platform. Consulta [Configurazione dei dati Google Analytics in streaming su Adobe Experience Platform](streaming.md).

## Configurare una connessione e una visualizzazione dati in CJA

Dopo aver acquisito correttamente i dati storici e/o configurato la raccolta dati su Adobe Experience Platform, puoi [Creare una connessione](/help/connections/create-connection.md) per consentire a Customer Journey Analytics di fare riferimento a tali dati.

Utilizza la connessione per creare una o più [Visualizzazioni dati](/help/data-views/create-dataview.md) da utilizzare su Analysis Workspace.

## Creare rapporti

Dopo aver configurato le dimensioni e le metriche all’interno di una visualizzazione dati, puoi iniziare a utilizzare Analysis Workspace per generare i rapporti desiderati. Consulta [Rapporto sui dati Google Analytics in Customer Journey Analytics](report.md).
