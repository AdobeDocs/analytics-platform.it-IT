---
title: Aggiornamento da una soluzione di analisi di terze parti a Customer Journey Analytics
description: Scopri come effettuare l’aggiornamento da una soluzione di analisi di terze parti al Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 87df2fb92f238ce051ac5f6cc90e218737279471
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 12%

---

# Aggiornamento da una soluzione di analisi di terze parti a Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Prodotto di analisi di terze parti"
>abstract="Implementazione che raccoglie dati per un prodotto di analisi di terze parti, ad esempio Google Analytics. Selezionando questa opzione nel questionario verranno disattivate diverse opzioni che non vengono applicate durante l’aggiornamento a Customer Journey Analytics da un prodotto di analisi di terze parti."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Usa le informazioni in questa pagina per rispondere alle domande nell&#39;elenco di controllo per l&#39;aggiornamento di [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Il processo consigliato di aggiornamento da una soluzione di analisi di terze parti a un Customer Journey Analytics è una nuova implementazione di Experience Platform Web SDK, che è il metodo di raccolta dati preferito per il Customer Journey Analytics. Insieme al Web SDK, Adobe consiglia anche di acquisire in Adobe Experience Platform i dati storici dalla soluzione di analisi di terze parti.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Utilizza la procedura seguente per passare al Customer Journey Analytics da una soluzione di analisi di terze parti, ad esempio Google Analytics:

1. ...


Se hai bisogno di consigli, indicazioni o supporto più specifici, contatta il rappresentante Adobe.

| Soluzione di analisi esistente | Descrizione | Percorsi di aggiornamento disponibili |
|---------|----------|----------|
| AppMeasurement | L’AppMeasurement per JavaScript è sempre stato un metodo comune per implementare Adobe Analytics.<p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics con AppMeasurement per JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Consigliato) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore Source di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrare da Adobe Analytics a Web SDK</li><li>[Connettore Source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Estensione Adobe Analytics (tag) | <p>I tag in Adobe Experience Platform sono una soluzione di gestione dei tag che consente di distribuire il codice Analytics insieme ad altri requisiti di assegnazione tag. Adobe offre integrazioni con altre soluzioni e prodotti e consente di distribuire codice personalizzato. Tutte queste attività possono essere eseguite senza dover ricorrere a team di sviluppo nell’organizzazione per aggiornare il codice sul sito.</p><p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics utilizzando l&#39;estensione Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Consigliato) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore Source di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrare da Adobe Analytics a Web SDK</li><li>[Connettore Source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK è il metodo attualmente consigliato da Adobe per l’implementazione di Adobe Analytics. L’Edge Network di Adobe Experience Platform ti consente di inviare dati destinati a più prodotti a una posizione centralizzata. <p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics con l&#39;Edge Network di Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Consigliato) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore Source di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati a Platform</li></ul> |
| Estensione Experience Platform Web SDK (tag) | L’Experience Platform Web SDK è il metodo attualmente consigliato da Adobe per implementare Adobe Analytics per i dati web. L’Edge Network di Adobe Experience Platform ti consente di inviare dati destinati a più prodotti a una posizione centralizzata. <p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Consigliato) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore Source di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati a Platform</li></ul> |
| Experience Platform Mobile SDK | L’Experience Platform di Mobile SDK è il metodo attualmente consigliato da Adobe per implementare Adobe Analytics per i dati mobili. L’Edge Network di Adobe Experience Platform ti consente di inviare dati destinati a più prodotti a una posizione centralizzata.<p>Adobe Experience Platform Mobile SDK consente di alimentare le soluzioni e i servizi Experience Cloud di Adobe nelle app mobili. </p><p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics utilizzando Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Consigliato) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore Source di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati a Platform</li></ul> |
| API di inserimento dati in blocco | L’API di inserimento dati in blocco (BDIA) è una funzionalità di Adobe Analytics che consente di caricare i dati delle chiamate al server in batch di file invece di utilizzare librerie lato client come AppMeasurement. </p><p>Per ulteriori informazioni su questo tipo di implementazione, vedere [API di inserimento dati in blocco](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Consigliato) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore Source di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[API Adobe Experience Platform Edge Network Server e Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}
