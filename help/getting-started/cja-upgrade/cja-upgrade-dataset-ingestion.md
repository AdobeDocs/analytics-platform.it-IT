---
title: Monitorare l’acquisizione del set di dati durante l’aggiornamento al Customer Journey Analytics
description: Scopri come monitorare l’acquisizione dei set di dati durante l’aggiornamento al Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a5425eccff643cd45fd630172b0113e646b2a9cc
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---

# Monitorare l’acquisizione del set di dati durante l’aggiornamento al Customer Journey Analytics

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), oppure puoi seguire i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Dopo aver configurato l’implementazione dell’SDK web, devi controllare gli stati dei singoli batch per verificare che i dati vengano acquisiti nel set di dati.

1. Nell&#39;interfaccia utente di Experience Platform, selezionare **[!UICONTROL Monitoring]** nel menu di navigazione a sinistra.

   Viene visualizzato il dashboard Monitoraggio. Questa dashboard consente di visualizzare gli stati dei dati in entrata dall’acquisizione in batch o in streaming.

   <!-- insert screenshot -->

1. Selezionare **[!UICONTROL Batch end-to-end]** per visualizzare un elenco di batch.

   Se non viene visualizzato alcun batch, controlla l’implementazione dell’SDK web per assicurarti che invii correttamente i dati ad Adobe.

   <!-- insert screenshot -->

1. Selezionare l&#39;ID batch per un determinato set di dati, quindi verificare che **[!UICONTROL Success]** sia visualizzato nel campo **[!UICONTROL Status]**.

   Se **[!UICONTROL Failed]** è visualizzato nel campo **[!UICONTROL Status]**, controlla l&#39;implementazione dell&#39;SDK Web per assicurarti che invii correttamente i dati ad Adobe.

   Ripetere questo passaggio per verificare lo stato di ciascun batch.




