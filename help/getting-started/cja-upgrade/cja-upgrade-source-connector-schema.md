---
title: Creare uno schema XDM per il connettore di origine di Analytics
description: Scopri come creare uno schema XDM per il connettore di origine di Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 8%

---

# Creare uno schema XDM per il connettore di origine di Analytics

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), oppure puoi seguire i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

## Comprendere come il connettore di origine di Analytics può inserire dati storici nel Customer Journey Analytics

Puoi usare il connettore di origine di Analytics per inserire in Adobe Experience Platform i dati della suite di rapporti di Adobe Analytics. Questi dati possono quindi essere utilizzati come dati storici nel Customer Journey Analytics.

Si presuppone che si desideri [creare uno schema XDM durante l&#39;aggiornamento al Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), perché si desidera uno schema semplificato personalizzato in base alle esigenze della propria organizzazione e alle specifiche applicazioni Platform utilizzate.

Per utilizzare il connettore di origine di Analytics per inserire nel Customer Journey Analytics i dati storici, è necessario:

1. Crea uno schema XDM per il connettore di origine di Analytics, come descritto di seguito.

1. Se non disponi già di un connettore di origine Analytics, [crea il connettore di origine Analytics e mappa i campi sullo schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Oppure

   Se disponi già di un connettore di origine Analytics, [mappa i campi dal connettore di origine allo schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Aggiungere il set di dati del connettore di origine di Analytics alla connessione](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Creare uno schema XDM per il connettore di origine di Analytics

Dovresti avere già [creato un nuovo schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) per l&#39;implementazione Experience Platform Web SDK da utilizzare con il Customer Journey Analytics. Questo schema deve contenere qualsiasi gruppo di campi per i campi su cui intendi raccogliere dati.

Ora è necessario utilizzare gli stessi gruppi di campi dallo schema SDK per web e aggiungerli a un nuovo schema che può essere utilizzato con il connettore di origine di Analytics.

Questo schema per il connettore di origine di Analytics deve contenere:

* Tutti i gruppi di campi (inclusi i gruppi di campi personalizzati creati dall&#39;utente) inclusi nello schema personalizzato creato per l&#39;implementazione dell&#39;SDK Web. Eventuali campi personalizzati che non fanno parte di un gruppo di campi predefinito avrebbero dovuto essere aggiunti allo schema SDK Web come parte di un gruppo di campi personalizzato.

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
