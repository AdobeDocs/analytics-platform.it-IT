---
title: Creare uno schema XDM per il connettore di origine di Analytics
description: Scopri come creare uno schema XDM per il connettore di origine di Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8e51e97b0616a5406c5c3a29431fde87a551ab9f
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 1%

---

# Creare uno schema XDM per il connettore di origine di Analytics

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), oppure puoi seguire i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

Dovresti avere già [creato un nuovo schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) per l&#39;implementazione Experience Platform Web SDK da utilizzare con il Customer Journey Analytics. Questo schema deve contenere qualsiasi gruppo di campi per i campi su cui intendi raccogliere dati.

Oltre allo schema XDM già creato per l’implementazione dell’SDK per web, ora è necessario creare un secondo schema XDM da utilizzare con il connettore di origine di Analytics per inserire i dati storici nel Customer Journey Analytics.

Questo secondo schema deve contenere:

* Tutti i gruppi di campi (inclusi i gruppi di campi personalizzati) inclusi nello schema creato per l’implementazione dell’SDK per web. Eventuali campi personalizzati che non fanno parte di un gruppo di campi predefinito avrebbero dovuto essere aggiunti allo schema SDK Web come parte di un gruppo di campi personalizzato.

* Gruppo di campi Modello Adobe Analytics ExperienceEvent

Per creare lo schema XDM da utilizzare con il connettore di origine di Analytics:

1. In Adobe Experience Platform, iniziare a creare un nuovo schema XDM come descritto in [Creare uno schema XDM da utilizzare con il Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. Aggiungi tutti i gruppi di campi (compresi eventuali gruppi di campi personalizzati) inclusi nello schema creato per l’implementazione dell’SDK per web.

1. Dopo aver aggiunto questi gruppi di campi, aggiungi il gruppo di campi Adobe Analytics ExperienceEvent:

   Nella sezione **[!UICONTROL Field groups]**, seleziona **[!UICONTROL Add]** per aggiungere un gruppo di campi aggiuntivo.

   ![Aggiungi gruppo di campi allo schema](assets/schema-add-field-group.png)

1. Cercare e selezionare il gruppo di campi **[!UICONTROL Adobe Analytics ExperienceEvent Template]**.

   ![Aggiungi il gruppo di campi Adobe Analytics ExperienceEvent](assets/schema-experienceevent.png)

1. Seleziona **[!UICONTROL Add field groups]**.

1. Seleziona **[!UICONTROL Save]** (Salva) per salvare lo schema.

1. Continua seguendo i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i [passaggi di aggiornamento generati dinamicamente](https://gigazelle.github.io/cja-ttv/).

