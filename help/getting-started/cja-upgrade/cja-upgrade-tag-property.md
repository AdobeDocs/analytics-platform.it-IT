---
title: Creare una proprietà tag e aggiungere l’estensione Web SDK
description: Scopri come creare una proprietà tag e aggiungere l’estensione Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ccc6df56771cd9f83bbd7a8570e32d7ed63a0ced
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 22%

---

# Creare un tag per la proprietà

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), oppure puoi seguire i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

Puoi utilizzare la funzione Tag in Adobe Experience Platform per implementare il codice sul sito per raccogliere i dati. Questa soluzione per la gestione dei tag consente di implementare il codice e altri requisiti di assegnazione dei tag. I tag offrono un’integrazione diretta con Adobe Experience Platform tramite l’estensione dell’SDK per Web di Adobe Experience Platform.

Le informazioni seguenti descrivono come creare un tag per la proprietà. Per ulteriori informazioni, consulta [Configurare l&#39;estensione tag Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) nella documentazione di Experience Platform. L&#39;SDK per Web include [!UICONTROL Adobe Experience Cloud ID Service] in modo nativo, pertanto non è necessario aggiungere l&#39;estensione del servizio ID al tag.

Una proprietà è fondamentalmente un contenitore che riempi con estensioni, regole, elementi dati e librerie durante la distribuzione di tag sul sito. Molte persone creano una proprietà per ogni sito web (o gruppo di siti strettamente correlati) in cui desiderano distribuire lo stesso set di tag. Per ulteriori informazioni sulle proprietà, vedi [Proprietà](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) nell&#39;Experience Platform di documentazione sulla raccolta dati.

Per creare un tag per la proprietà:

1. Accedi a experience.adobe.com utilizzando le credenziali Adobe ID.

1. In Adobe Experience Platform, vai a **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Seleziona **[!UICONTROL New Property]** (Nuova proprietà).

   Assegna un nome al tag, seleziona **[!UICONTROL Web]** e immetti un nome di dominio. Seleziona **[!UICONTROL Save]** (Salva) per continuare.

   ![Creare una proprietà](assets/create-property.png)

1. Continua seguendo i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i [passaggi di aggiornamento generati dinamicamente](https://gigazelle.github.io/cja-ttv/).

