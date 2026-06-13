---
title: Migrare i dati da Google Analytics
description: Scopri il flusso di lavoro generale per spostare i dati da Google Analytics a Adobe Experience Platform e visualizzare i rapporti in Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
TQID: https://experienceleague.adobe.com/C9rt1pyuM6ykLUlXCHc0ITwGeGcuLw6qisXnJxwX4uU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 70%

---

# Migrare i dati da Google Analytics

>[!BEGINSHADEBOX]

Questa guida descrive la migrazione dei dati per gli amministratori. Se sei un analista che cerca di trovare i tuoi report GA4 in Customer Journey Analytics, consulta [Passaggio da Google Analytics 4 a Customer Journey Analytics](/help/getting-started/ga-to-cja/home.md) e [report GA4 in Customer Journey Analytics](/help/getting-started/ga-to-cja/reports.md).

>[!ENDSHADEBOX]

Se hai poca esperienza con Customer Journey Analytics, è possibile che la tua organizzazione disponga di dati esistenti su un&#39;altra piattaforma Analytics, ad esempio Google Analytics. Puoi seguire questi passaggi generali per spostare tali dati in Adobe Experience Platform, consentendoti di visualizzare i rapporti su Customer Journey Analytics.

I flussi di lavoro vengono forniti sia per i dati storici che per la raccolta dati corrente. Puoi seguire uno o entrambi questi flussi di lavoro, a seconda delle esigenze di dati della tua organizzazione.

## Spostamento di dati storici da Google Analytics ad Adobe Experience Platform

L’acquisizione di dati storici (di recupero) comporta l’esportazione di dati da Google e l’importazione di tali dati su Adobe Experience Platform. Consulta [Inserire dati Google Analytics su Adobe Experience Platform](backfill.md).

Una volta inseriti correttamente i dati storici in Platform, puoi [configurare i dati correnti in streaming](streaming.md) oppure iniziare immediatamente a generare rapporti sui dati precompilati in Customer Journey Analytics [creando una connessione](/help/connections/create-connection.md).

## Configurare un&#39;implementazione Google Analytics esistente per Adobe Experience Platform {#configure}

L’acquisizione dei dati correnti (in streaming) comporta l’invio di dati a Adobe Experience Platform Edge Network, che a sua volta li inoltra a Adobe Experience Platform. Consulta [Configurazione dei dati Google Analytics in streaming su Adobe Experience Platform](streaming.md).

## Configurare una connessione e una visualizzazione dati in Customer Journey Analytics

Dopo aver acquisito correttamente i dati storici e/o configurato la raccolta dati su Adobe Experience Platform, puoi [Creare una connessione](/help/connections/create-connection.md) per consentire a Customer Journey Analytics di fare riferimento a tali dati.

Utilizza la connessione per creare una o più [Visualizzazioni dati](/help/data-views/create-dataview.md) da utilizzare su Analysis Workspace.

## Creare rapporti

Dopo aver configurato le dimensioni e le metriche all’interno di una visualizzazione dati, puoi iniziare a utilizzare Analysis Workspace per generare i rapporti desiderati. Consulta [Rapporto sui dati Google Analytics in Customer Journey Analytics](report.md).
