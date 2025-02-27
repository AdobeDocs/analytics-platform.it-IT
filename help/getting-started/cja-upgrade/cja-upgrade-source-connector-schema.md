---
title: Creare uno schema XDM personalizzato per il connettore di origine di Analytics
description: Scopri come creare uno schema personalizzato per il connettore di origine di Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 22%

---

# Creare uno schema XDM personalizzato per il connettore di origine di Analytics {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="Creare uno schema XDM per il connettore di origine di Analytics"
>abstract="Questo schema è una combinazione del gruppo di campi ExperienceEvent di Adobe Analytics con tutti i gruppi di campi che compongono lo schema personalizzato della tua organizzazione. Ti consente di mappare i campi utilizzati dal connettore di origine di Analytics sullo schema della tua organizzazione e viene utilizzato solo per i dati storici.<br><br>Poiché di natura tecnica, la creazione di questo schema può essere completata in alcune ore, possibilmente in modo più rapido se conosci esattamente i gruppi di campi che compongono lo schema personalizzato della tua organizzazione."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Comprendere come il connettore di origine di Analytics può inserire dati storici in Customer Journey Analytics

Puoi usare il connettore di origine di Analytics per inserire in Adobe Experience Platform i dati della suite di rapporti di Adobe Analytics. Questi dati possono quindi essere utilizzati come dati storici in Customer Journey Analytics.

Questo processo presuppone che si desideri [creare uno schema personalizzato da utilizzare con l&#39;implementazione di Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), perché si desidera uno schema semplificato personalizzato in base alle esigenze della propria organizzazione e alle applicazioni Platform specifiche utilizzate.

Per utilizzare il connettore di origine di Analytics per inserire dati storici in Customer Journey Analytics, è necessario:

1. Crea uno schema personalizzato per il connettore di origine di Analytics, come descritto di seguito.

1. Se non disponi già di un connettore di origine Analytics, [crea il connettore di origine Analytics e mappa i campi sullo schema personalizzato](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Oppure

   Se disponi già di un connettore di origine Analytics, [mappa i campi dal connettore di origine allo schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Aggiungere il set di dati del connettore di origine di Analytics alla connessione](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Creare uno schema XDM personalizzato per il connettore di origine di Analytics

Dovresti avere già [creato un nuovo schema personalizzato](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) per l&#39;implementazione di Experience Platform Web SDK da utilizzare con Customer Journey Analytics. Questo schema deve contenere qualsiasi gruppo di campi per i campi su cui intendi raccogliere dati.

Ora è necessario utilizzare gli stessi gruppi di campi dallo schema Web SDK e aggiungerli a un nuovo schema che può essere utilizzato con il connettore di origine Analytics.

Questo schema per il connettore di origine di Analytics deve contenere:

* Tutti i gruppi di campi (inclusi i gruppi di campi personalizzati creati dall&#39;utente) inclusi nello schema personalizzato creato per l&#39;implementazione di Web SDK. Eventuali campi personalizzati che non fanno parte di un gruppo di campi predefinito dovrebbero essere stati aggiunti allo schema di Web SDK come parte di un gruppo di campi personalizzato.

* Gruppo di campi Modello Adobe Analytics ExperienceEvent

Per creare lo schema personalizzato da utilizzare con il connettore di origine di Analytics:

1. In Adobe Experience Platform, iniziare a creare un nuovo schema personalizzato come descritto in [Creare uno schema personalizzato da utilizzare con l&#39;implementazione di Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. Aggiungi tutti i gruppi di campi (compresi eventuali gruppi di campi personalizzati) inclusi nello schema creato per l’implementazione di Web SDK.

1. Dopo aver aggiunto questi gruppi di campi, aggiungi il gruppo di campi Adobe Analytics ExperienceEvent:

   Nella sezione **[!UICONTROL Field groups]**, seleziona **[!UICONTROL Add]** per aggiungere un gruppo di campi aggiuntivo.

   ![Aggiungi gruppo di campi allo schema](assets/schema-add-field-group.png)

1. Cercare e selezionare il gruppo di campi **[!UICONTROL Adobe Analytics ExperienceEvent Template]**.

   ![Aggiungi il gruppo di campi Adobe Analytics ExperienceEvent](assets/schema-experienceevent.png)

1. Seleziona **[!UICONTROL Add field groups]**.

1. Seleziona **[!UICONTROL Save]** (Salva) per salvare lo schema.

1. Continua seguendo i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i [passaggi di aggiornamento generati dinamicamente](https://gigazelle.github.io/cja-ttv/).
