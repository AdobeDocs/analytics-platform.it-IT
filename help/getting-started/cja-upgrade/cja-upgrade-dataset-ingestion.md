---
title: Monitorare l’acquisizione del set di dati durante l’aggiornamento a Customer Journey Analytics
description: Scopri come monitorare l’acquisizione del set di dati durante l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
autotag-review: '2026-05-19T08:10:42.746Z'
TQID: 'https://experienceleague.adobe.com/tAPQiUUPilyH50PlqwefoZjw14QDN9ER1D6EKsMAR9w'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 224
ht-degree: 72%

---

# Monitorare l’acquisizione del set di dati durante l’aggiornamento a Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Convalidare i dati nel set di dati"
>abstract="Dopo aver configurato l’implementazione, puoi utilizzare Gestione attività del set di dati per visualizzare i batch acquisiti e non riusciti. Se visualizzi principalmente i batch acquisiti, questo passaggio è completo. Se visualizzi principalmente batch non riusciti o nessun batch, controlla l’implementazione per assicurarti che invii correttamente i dati ad Adobe."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Dopo aver configurato l’implementazione di Web SDK o API, è necessario controllare gli stati dei singoli batch per verificare che i dati vengano effettivamente acquisiti nel set di dati.

1. Nell&#39;interfaccia utente di Experience Platform, seleziona **[!UICONTROL Monitoraggio]** nel menu di navigazione a sinistra.

   Viene visualizzata la dashboard Monitoraggio. Questa dashboard consente di visualizzare gli stati dei dati in entrata dall’acquisizione in streaming o in batch.

   <!-- insert screenshot -->

1. Selezionare **[!UICONTROL Batch end-to-end]** per visualizzare un elenco di batch.

   Se non viene visualizzato nessun batch, controlla l’implementazione per assicurarti che invii correttamente i dati ad Adobe.

   <!-- insert screenshot -->

1. Seleziona l&#39;ID batch per un dato set di dati, quindi verifica che **[!UICONTROL Operazione riuscita]** sia visualizzato nel campo **[!UICONTROL Stato]**.

   Se nel campo **[!UICONTROL Stato]** viene visualizzato **[!UICONTROL Non riuscito]**, controlla l&#39;implementazione per assicurarti che invii correttamente i dati ad Adobe.

   Ripeti questo passaggio per verificare lo stato di ciascun batch.

{{upgrade-final-step}}

