---
title: Creare una proprietà tag e aggiungere l’estensione Web SDK
description: Scopri come creare una proprietà tag e aggiungere l’estensione Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
autotag-review: '2026-05-19T08:18:58.656Z'
TQID: 'https://experienceleague.adobe.com/8Wld534ijt7cmJnlbq4cB7tURTb8hch99Z6FIrhzAcQ'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9efc51843684b8cad96d01f7ada99eafc5950b42
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 69%

---

# Aggiungere l’estensione Web SDK al tag {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="Aggiungere l’estensione Web SDK alla proprietà tag"
>abstract="Aggiungi l’estensione Adobe Experience Platform Web SDK alla tua proprietà tag. L’aggiunta dell’estensione Web SDK alla proprietà tag è semplice e richiede solo pochi minuti per essere completata."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Puoi utilizzare la funzione Tags (Tag) in Adobe Experience Platform per implementare sul tuo sito il codice necessario per raccogliere i dati. Questa soluzione per la gestione dei tag consente di implementare il codice e altri requisiti di assegnazione dei tag. I tag offrono un’integrazione diretta con Adobe Experience Platform tramite l’estensione dell’SDK per Web di Adobe Experience Platform.

Le informazioni seguenti descrivono come aggiungere l’estensione Web SDK al tag. Per ulteriori informazioni, consulta [Configurare l’estensione tag Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) nella documentazione di Experience Platform. Il Web SDK include il servizio Experience Platform Identity, pertanto non è necessario aggiungere l&#39;estensione del servizio [!UICONTROL Experience Cloud ID] al tag.

Dopo aver [creato un tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), è necessario configurarlo con l’estensione Adobe Experience Platform Web SDK. In questo modo potrai inviare dati ad Adobe Experience Platform (tramite lo stream di dati).

Per aggiungere l’estensione Web SDK al tag

1. Accedi a experience.adobe.com utilizzando le credenziali Adobe ID.

1. In Adobe Experience Platform, vai a **[!UICONTROL Raccolta dati]** > **[!UICONTROL Tag]**.

1. Seleziona il tag appena creato dall&#39;elenco di [!UICONTROL Proprietà tag] per aprirlo.

1. Seleziona **[!UICONTROL Estensioni]** nella barra a sinistra.

1. Seleziona **[!UICONTROL Catalogo]** nella barra superiore.

1. Cerca o scorri fino all&#39;estensione **[!UICONTROL Adobe Experience Platform Web SDK]**, quindi seleziona **[!UICONTROL Installa]** per installarla.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Seleziona la sandbox e lo stream di dati creato in precedenza per il tuo [!UICONTROL ambiente di produzione] e (facoltativo) [!UICONTROL ambiente di staging] e [!UICONTROL ambiente di sviluppo].

   ![Configurazione dell’estensione AEP Web SDK](assets/aepwebsk-extension-datastreams.png)

1. Seleziona **[!UICONTROL Salva]**.

{{upgrade-final-step}}
