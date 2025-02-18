---
title: Creare una proprietà tag e aggiungere l’estensione Web SDK
description: Scopri come creare una proprietà tag e aggiungere l’estensione Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 32%

---

# Aggiungere l’estensione Web SDK al tag {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="Aggiungere l’estensione Web SDK alla proprietà tag"
>abstract="Aggiungi l’estensione Adobe Experience Platform Web SDK alla tua proprietà tag. L’aggiunta dell’estensione Web SDK alla proprietà tag è semplice e richiede solo pochi minuti per essere completata."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oppure i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

Puoi utilizzare la funzione Tag in Adobe Experience Platform per implementare il codice sul sito per raccogliere i dati. Questa soluzione per la gestione dei tag consente di implementare il codice e altri requisiti di assegnazione dei tag. I tag offrono un’integrazione diretta con Adobe Experience Platform tramite l’estensione dell’SDK per Web di Adobe Experience Platform.

Le informazioni seguenti descrivono come aggiungere l’estensione Web SDK al tag. Per ulteriori informazioni, consulta [Configurare l&#39;estensione tag Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) nella documentazione di Experience Platform. Il Web SDK include [!UICONTROL Adobe Experience Cloud ID Service] in modo nativo, pertanto non è necessario aggiungere l&#39;estensione del servizio ID al tag.

Dopo aver [creato un tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), è necessario configurarlo con l&#39;estensione Adobe Experience Platform Web SDK. In questo modo puoi inviare dati a Adobe Experience Platform (tramite lo stream di dati).

Per aggiungere l’estensione Web SDK al tag:

1. Accedi a experience.adobe.com utilizzando le credenziali Adobe ID.

1. In Adobe Experience Platform, vai a **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Seleziona il tag appena creato dall’elenco [!UICONTROL Tag Properties] (Proprietà tag) per aprirlo.

1. Seleziona **[!UICONTROL Extensions]** (Estensioni) nella barra a sinistra.

1. Seleziona **[!UICONTROL Catalog]** (Catalogo) nella barra superiore.

1. Cerca o scorri fino a **[!UICONTROL Adobe Experience Platform Web SDK extension]**, quindi seleziona **[!UICONTROL Install]** per installarlo.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Seleziona la sandbox e il flusso di dati creato in precedenza per il tuo [!UICONTROL Production Environment] (Ambiente di produzione) e (facoltativamente) [!UICONTROL Staging Environment] (Ambiente di gestione temporanea) e [!UICONTROL Development Environment] (Ambiente di sviluppo).

   ![Configurazione dell’estensione AEP Web SDK](assets/aepwebsk-extension-datastreams.png)

1. Seleziona **[!UICONTROL Save]** (Salva).

1. Continua seguendo i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i [passaggi di aggiornamento generati dinamicamente](https://gigazelle.github.io/cja-ttv/).
