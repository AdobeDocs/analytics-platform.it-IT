---
title: Monitorare l’acquisizione del set di dati durante l’aggiornamento a Customer Journey Analytics
description: Scopri come monitorare l’acquisizione dei set di dati durante l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 41%

---

# Monitorare l’acquisizione del set di dati durante l’aggiornamento a Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Convalidare i dati nel set di dati"
>abstract="Dopo aver configurato l’implementazione di Web SDK, puoi utilizzare Gestione attività set di dati per visualizzare i batch acquisiti e non riusciti. Se visualizzi principalmente i batch acquisiti, questo passaggio è completo. Se visualizzi principalmente batch con errori o nessun batch, controlla l’implementazione di Web SDK per assicurarti che invii correttamente i dati ad Adobe.<br><br>Se tutto è risulta corretto e senza errori, questo passaggio può essere eseguito in meno di un giorno. In caso di più problemi di raccolta dati, risolverli può richiedere molto più tempo."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Dopo aver configurato l’implementazione di Web SDK, è necessario controllare gli stati dei singoli batch per verificare che i dati vengano acquisiti nel set di dati.

1. Nell&#39;interfaccia utente di Experience Platform, seleziona **[!UICONTROL Monitoring]** nel menu di navigazione a sinistra.

   Viene visualizzato il dashboard Monitoraggio. Questa dashboard consente di visualizzare gli stati dei dati in entrata dall’acquisizione in batch o in streaming.

   <!-- insert screenshot -->

1. Selezionare **[!UICONTROL Batch end-to-end]** per visualizzare un elenco di batch.

   Se non viene visualizzato alcun batch, controlla l’implementazione di Web SDK per assicurarti che invii correttamente i dati ad Adobe.

   <!-- insert screenshot -->

1. Selezionare l&#39;ID batch per un determinato set di dati, quindi verificare che **[!UICONTROL Success]** sia visualizzato nel campo **[!UICONTROL Status]**.

   Se **[!UICONTROL Failed]** è visualizzato nel campo **[!UICONTROL Status]**, controlla l&#39;implementazione del Web SDK per assicurarti che invii correttamente i dati ad Adobe.

   Ripetere questo passaggio per verificare lo stato di ciascun batch.

1. Continua seguendo i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i [passaggi di aggiornamento generati dinamicamente](https://gigazelle.github.io/cja-ttv/).

