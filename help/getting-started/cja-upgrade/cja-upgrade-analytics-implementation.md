---
title: Comprendere l’implementazione di Adobe Analytics e come influisce sull’aggiornamento al Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: aedf7a2ad41b09521938b789dbaf1c193cdb661f
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 9%

---

# Comprendere l’implementazione di Adobe Analytics e come influisce sull’aggiornamento al Customer Journey Analytics

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), oppure puoi seguire i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

Esistono diversi modi per effettuare l’aggiornamento al Customer Journey Analytics, ma non tutti i percorsi di aggiornamento sono disponibili per ciascun tipo di implementazione di Adobe Analytics. Tuttavia, il percorso di aggiornamento consigliato è disponibile indipendentemente da come Adobe Analytics viene implementato nella tua organizzazione.

Utilizza le informazioni riportate di seguito per comprendere l’implementazione corrente di Adobe Analytics e quali percorsi di aggiornamento sono disponibili per la tua organizzazione.

Se hai bisogno di consigli, indicazioni o supporto più specifici, contatta il rappresentante Adobe.

| Implementazione esistente di Adobe Analytics | Descrizione | Percorsi di aggiornamento disponibili |
|---------|----------|----------|
| AppMeasurement | L’AppMeasurement per JavaScript è sempre stato un metodo comune per implementare Adobe Analytics.<p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics con AppMeasurement per JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>(Consigliata) Nuova implementazione di Experience Platform Web SDK con il connettore Source di Analytics</li><li>Nuova implementazione di Experience Platform Web SDK</li><li>Migrare da Adobe Analytics a Web SDK</li><li>Connettore di origine di Analytics</li></ul> |
| Estensione Adobe Analytics (tag) | <p>I tag in Adobe Experience Platform sono una soluzione di gestione dei tag che consente di distribuire il codice Analytics insieme ad altri requisiti di assegnazione tag. Adobe offre integrazioni con altre soluzioni e prodotti e consente di distribuire codice personalizzato. Tutte queste attività possono essere eseguite senza dover ricorrere a team di sviluppo nell’organizzazione per aggiornare il codice sul sito.</p><p>Per ulteriori informazioni su questo tipo di implementazione, vedi [Implementare Adobe Analytics utilizzando l&#39;estensione Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>(Consigliata) Nuova implementazione di Experience Platform Web SDK con il connettore Source di Analytics</li><li>Nuova implementazione di Experience Platform Web SDK</li><li>Migrare da Adobe Analytics a Web SDK</li><li>Connettore di origine di Analytics</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK è il metodo attualmente consigliato da Adobe per l’implementazione di Adobe Analytics. L’Edge Network di Adobe Experience Platform ti consente di inviare dati destinati a più prodotti a una posizione centralizzata. <p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics con l&#39;Edge Network di Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Consigliata) Nuova implementazione di Experience Platform Web SDK con il connettore Source di Analytics</li><li>Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati a Platform</li></ul> |
| Estensione Experience Platform Web SDK (tag) | Experience Platform Web SDK è il metodo attualmente consigliato da Adobe per l’implementazione di Adobe Analytics per i dati web. L’Edge Network di Adobe Experience Platform ti consente di inviare dati destinati a più prodotti a una posizione centralizzata. <p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>(Consigliata) Nuova implementazione di Experience Platform Web SDK con il connettore Source di Analytics</li><li>Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati a Platform</li></ul> |
| Experience Platform Mobile SDK | L’SDK di Mobile di Experience Platform è il metodo attualmente consigliato da Adobe per implementare Adobe Analytics per i dati mobili. L’Edge Network di Adobe Experience Platform ti consente di inviare dati destinati a più prodotti a una posizione centralizzata.<p>L’SDK di Adobe Experience Platform Mobile aiuta ad alimentare le soluzioni e i servizi di Experience Cloud di Adobe nelle app mobili. </p><p>Per ulteriori informazioni su questo tipo di implementazione, vedi [Implementare Adobe Analytics utilizzando l&#39;SDK di Adobe Experience Platform Mobile](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>(Consigliata) Nuova implementazione di Experience Platform Web SDK con il connettore Source di Analytics</li><li>Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati a Platform</li></ul> |

{style="table-layout:auto"}
