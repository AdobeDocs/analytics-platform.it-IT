---
title: Creazione di uno schema per il Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 28%

---

# Creare un set di dati da utilizzare con il Customer Journey Analytics

>[!NOTE]
>
>Utilizzare questa documentazione dopo aver completato il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi precedenti generati in modo dinamico per la tua organizzazione.
>
>Dopo aver completato i passaggi in questa pagina, continua seguendo i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione dal [questionario Adobe Analytics all&#39;aggiornamento di Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Dopo aver creato uno schema XDM, ora è necessario definire il costrutto per memorizzare e gestire tali dati, che viene eseguito in Adobe Experience Platform tramite un set di dati.

Per creare un set di dati:

1. In Adobe Experience Platform, nella barra a sinistra, seleziona **[!UICONTROL Datasets]** entro [!UICONTROL DATA MANAGEMENT].

1. Seleziona **[!UICONTROL Create dataset]** (Crea set di dati).

   ![Creare un set di dati](assets/create-dataset.png)

1. Seleziona **[!UICONTROL Create dataset from schema]** (Crea set di dati da schema).

   ![Creare un set di dati da uno schema](assets/create-dataset-from-schema.png)

1. Seleziona lo schema creato in precedenza e seleziona **[!UICONTROL Next]** (Avanti).

1. Assegna un nome al set di dati e (facoltativamente) fornisci una descrizione.

   ![Assegnare un nome al set di dati](assets/name-your-datatest.png)

1. Seleziona **[!UICONTROL Finish]** (Fine).

1. Seleziona il pulsante **[!UICONTROL Profile]** (Profilo).

   Viene richiesto di abilitare il set di dati per il profilo. Una volta attivato, il set di dati arricchisce i profili dei clienti in tempo reale con i relativi dati inseriti.

   >[!IMPORTANT]
   >
   >    Puoi abilitare un set di dati per il profilo solo quando lo schema a cui aderisce il set di dati è abilitato anche per il profilo.

   ![Abilitare lo schema per il profilo](assets/aepwebsdk-dataset-profile.png)

   Per ulteriori informazioni su come visualizzare, visualizzare in anteprima, creare ed eliminare un set di dati, consulta la [guida dell&#39;interfaccia utente per i set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it). Scopri anche come abilitare un set di dati per Real-Time Customer Profile.

1. Continua seguendo i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione dal [questionario di aggiornamento di Adobe Analytics al Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

