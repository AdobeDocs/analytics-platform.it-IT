---
title: Creazione di uno schema per il Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 27%

---

# Aggiungere Platform as a service allo stream di dati

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), oppure puoi seguire i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Prima di completare i passaggi descritti in questa sezione, deve esistere già un flusso di dati. La data e la modalità di creazione dello stream di dati dipendono dall’implementazione di Adobe Analytics, come segue:

* Se la tua implementazione di Adobe Analytics utilizza l’SDK per web o l’estensione SDK per web, lo stream di dati era disponibile per il tuo ambiente Adobe Analytics prima del processo di aggiornamento.

* Per altre implementazioni di Adobe Analytics, la creazione di un datastream fa parte del processo di aggiornamento, come descritto in [Creare un datastream da utilizzare con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

Con lo stream di dati disponibile, devi aggiungere Platform as a service:

1. Nell’interfaccia utente di Adobe Experience Platform, seleziona **[!UICONTROL Datastreams]** (Flussi di dati) da [!UICONTROL DATA COLLECTION] (RACCOLTE DATI) nella barra a sinistra.

1. Seleziona lo stream di dati configurato in precedenza. <!--true?-->

1. Seleziona **[!UICONTROL Add Service]** (Aggiungi servizio).

1. Nella schermata [!UICONTROL Add Service screen] (Aggiungi servizio):

   1. Seleziona **[!UICONTROL Adobe Experience Platform]** dall’elenco [!UICONTROL Service] (Servizio).

   1. Assicurati di aver selezionato **[!UICONTROL Enabled]** (Abilitato).

   1. Seleziona il set di dati dall’elenco [!UICONTROL Event Dataset] (Set di dati evento).

      ![Servizio AEP del flusso di dati](./assets/datastream-aep-service.png)

   1. Abbandona le altre impostazioni e seleziona **[!UICONTROL Save]** per salvare il flusso di dati.

   Il flusso di dati è ora configurato per inoltrare i dati raccolti dal sito Web al set di dati in Adobe Experience Platform.

   Per ulteriori informazioni su come configurare un flusso di dati e come gestire i dati sensibili consulta la sezione [Panoramica dei flussi di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html).

1. Continua seguendo i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i [passaggi di aggiornamento generati dinamicamente](https://gigazelle.github.io/cja-ttv/).
