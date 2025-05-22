---
title: Creare una proprietà tag e aggiungere l’estensione Web SDK
description: Scopri come creare una proprietà tag e aggiungere l’estensione Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '276'
ht-degree: 100%

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

Le informazioni seguenti descrivono come aggiungere l’estensione Web SDK al tag. Per ulteriori informazioni, consulta [Configurare l’estensione per tag Web SDK](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) nella documentazione di Experience Platform. Web SDK include [!UICONTROL Adobe Experience Cloud ID Service] in modo nativo e, pertanto, non è necessario aggiungere al tag l’estensione del servizio ID.

Dopo aver [creato un tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), è necessario configurarlo con l’estensione Adobe Experience Platform Web SDK. In questo modo potrai inviare dati ad Adobe Experience Platform (tramite lo stream di dati).

Per aggiungere l’estensione Web SDK al tag

1. Accedi a experience.adobe.com utilizzando le credenziali Adobe ID.

1. In Adobe Experience Platform, passa a **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Seleziona il tag appena creato dall’elenco [!UICONTROL Tag Properties] (Proprietà tag) per aprirlo.

1. Seleziona **[!UICONTROL Extensions]** (Estensioni) nella barra a sinistra.

1. Seleziona **[!UICONTROL Catalog]** (Catalogo) nella barra superiore.

1. Cerca o scorri fino a **[!UICONTROL Adobe Experience Platform Web SDK extension]**, quindi seleziona **[!UICONTROL Install]** per installarlo.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Seleziona la sandbox e il flusso di dati creato in precedenza per il tuo [!UICONTROL Production Environment] (Ambiente di produzione) e (facoltativamente) [!UICONTROL Staging Environment] (Ambiente di gestione temporanea) e [!UICONTROL Development Environment] (Ambiente di sviluppo).

   ![Configurazione dell’estensione AEP Web SDK](assets/aepwebsk-extension-datastreams.png)

1. Seleziona **[!UICONTROL Save]** (Salva).

{{upgrade-final-step}}
