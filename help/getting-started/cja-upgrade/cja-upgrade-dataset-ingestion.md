---
title: Monitorare l’acquisizione del set di dati durante l’aggiornamento a Customer Journey Analytics
description: Scopri come monitorare l’acquisizione del set di dati durante l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 69%

---

# Monitorare l’acquisizione del set di dati durante l’aggiornamento a Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Convalidare i dati nel set di dati"
>abstract="Ora che hai configurato l’implementazione, puoi utilizzare Gestione attività set di dati per visualizzare i batch con errori e non riusciti. Se visualizzi principalmente i batch acquisiti, questo passaggio è completo. Se visualizzi principalmente batch con errori o nessun batch, verifica l’implementazione per assicurarti che stia inviando correttamente i dati ad Adobe."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Dopo aver configurato l’implementazione di Web SDK o API, è necessario controllare gli stati dei singoli batch per verificare che i dati vengano acquisiti nel set di dati.

1. Nell’interfaccia utente di Experience Platform, seleziona **[!UICONTROL Monitoring]** nella barra di navigazione a sinistra.

   Viene visualizzata la dashboard Monitoraggio. Questa dashboard consente di visualizzare gli stati dei dati in entrata dall’acquisizione in batch o in streaming.

   <!-- insert screenshot -->

1. Seleziona **[!UICONTROL Batch end-to-end]** per visualizzare un elenco di batch.

   Se non viene visualizzato alcun batch, controlla l’implementazione per assicurarti che stia inviando correttamente i dati ad Adobe.

   <!-- insert screenshot -->

1. Seleziona l’ID batch per un determinato set di dati, quindi verifica che nel campo **[!UICONTROL Status]** venga visualizzato il valore **[!UICONTROL Success]**.

   Se **[!UICONTROL Failed]** è visualizzato nel campo **[!UICONTROL Status]**, controlla l&#39;implementazione per assicurarti che stia inviando correttamente i dati ad Adobe.

   Ripetere questo passaggio per verificare lo stato di ciascun batch.

{{upgrade-final-step}}

