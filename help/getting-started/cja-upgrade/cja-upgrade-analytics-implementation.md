---
title: Comprendere l’implementazione di Adobe Analytics e il modo in cui influisce sull’aggiornamento a Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 21%

---

# Comprendere l’implementazione di Adobe Analytics e il modo in cui influisce sull’aggiornamento a Customer Journey Analytics {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement (file JS manuale)"
>abstract="Implementazione di JavaScript che carica AppMeasurement.js su una pagina e invia i dati ad Adobe utilizzando l’oggetto s (ad esempio, s.eVar1)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Estensione di Adobe Analytics (tag)"
>abstract="Implementazione di tag che carica la raccolta dati di Adobe Experience Platform (precedentemente nota come Launch). Nel tag è installata l’estensione di Adobe Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="Web SDK (alloy.js)"
>abstract="Implementazione di JavaScript che carica la libreria Web SDK (alloy.js) su una pagina e invia i dati ad Adobe utilizzando un payload JSON."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Estensione Web SDK (tag)"
>abstract="Implementazione di tag che carica la raccolta dati di Adobe Experience Platform (precedentemente nota come Launch). Nel tag è installata l’estensione Web SDK."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="API di inserimento dati"
>abstract="Implementazione che utilizza l’API di inserimento dati o l’API di inserimento dati in blocco."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="Mobile SDK"
>abstract="Implementazione che utilizza Adobe Experience Platform Mobile SDK."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-third-party"
>title="AppMeasurement utilizzando uno strumento di gestione dei tag di terze parti"
>abstract="Implementazione che utilizza uno strumento di gestione tag di terze parti."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="Implementazione sconosciuta"
>abstract="Se non sei la persona che gestisce l’implementazione, puoi selezionare temporaneamente questa opzione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-determine-implementation"
>title="Determinare il tipo di implementazione esistente"
>abstract="Lavora internamente nella tua organizzazione per determinare quale tipo di implementazione utilizzi attualmente per inviare dati ad Adobe Analytics. Quando effettui l’aggiornamento a Customer Journey Analytics, collabora con l’utente o il team che conosce queste informazioni.<br><br>Dopo aver determinato il tipo di implementazione utilizzato dalla propria organizzazione, modificare la risposta nella Guida all&#39;aggiornamento di Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Esistono diversi modi per implementare Adobe Analytics. Durante l’aggiornamento a Customer Journey Analytics, non tutti i percorsi di aggiornamento sono disponibili per tutte le implementazioni di Adobe Analytics. Tuttavia, il percorso di aggiornamento consigliato è disponibile indipendentemente da come Adobe Analytics viene implementato nella tua organizzazione.

Utilizza le informazioni seguenti per scoprire l’implementazione corrente di Adobe Analytics e quali percorsi di aggiornamento sono disponibili per la tua organizzazione.

Se hai bisogno di consigli, indicazioni o supporto più specifici, contatta il rappresentante Adobe.

| Implementazione esistente di Adobe Analytics | Descrizione | Percorsi di aggiornamento disponibili |
|---------|----------|----------|
| AppMeasurement | AppMeasurement per JavaScript è sempre stato un metodo comune per implementare Adobe Analytics.<p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics con AppMeasurement per JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Consigliata) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore di origine di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrazione di Adobe Analytics al Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Estensione Adobe Analytics (tag) | <p>I tag in Adobe Experience Platform sono una soluzione di gestione dei tag che consente di distribuire il codice Analytics insieme ad altri requisiti di assegnazione tag. Adobe offre integrazioni con altre soluzioni e prodotti e consente di distribuire codice personalizzato. Tutte queste attività possono essere eseguite senza dover ricorrere a team di sviluppo nell’organizzazione per aggiornare il codice sul sito.</p><p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics utilizzando l&#39;estensione Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Consigliata) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore di origine di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrazione di Adobe Analytics al Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK è il metodo attualmente consigliato da Adobe per l’implementazione di Adobe Analytics. Adobe Experience Platform Edge Network consente di inviare dati destinati a più prodotti a una posizione centralizzata. <p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics con Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Consigliata) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore di origine di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Configura l&#39;implementazione di Adobe Analytics Web SDK per inviare dati a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Estensione Experience Platform Web SDK (tag) | Experience Platform Web SDK è il metodo attualmente consigliato da Adobe per l’implementazione di Adobe Analytics per i dati web. Adobe Experience Platform Edge Network consente di inviare dati destinati a più prodotti a una posizione centralizzata. <p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Consigliata) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore di origine di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[Configura l&#39;implementazione di Adobe Analytics Web SDK per inviare dati a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK è il metodo attualmente consigliato da Adobe per l’implementazione di Adobe Analytics per i dati mobili. Adobe Experience Platform Edge Network consente di inviare dati destinati a più prodotti a una posizione centralizzata.<p>Adobe Experience Platform Mobile SDK consente di alimentare le soluzioni e i servizi Experience Cloud di Adobe nelle app mobili. </p><p>Per ulteriori informazioni su questo tipo di implementazione, vedere [Implementare Adobe Analytics utilizzando Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Consigliata) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore di origine di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Configura l&#39;implementazione di Adobe Analytics Web SDK per inviare dati a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| API di inserimento dati in blocco | L’API di inserimento dati in blocco (BDIA) è una funzionalità di Adobe Analytics che consente di caricare i dati delle chiamate al server in batch di file invece di utilizzare librerie lato client come AppMeasurement. </p><p>Per ulteriori informazioni su questo tipo di implementazione, vedere [API di inserimento dati in blocco](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Consigliata) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore di origine di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[API server Adobe Experience Platform Edge Network e Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}


