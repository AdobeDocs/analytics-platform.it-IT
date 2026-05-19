---
title: Informazioni sull’implementazione di Adobe Analytics e sul modo in cui influisce sull’aggiornamento a Customer Journey Analytics
description: Scopri il percorso consigliato durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
autotag-review: '2026-05-19T08:10:04.372Z'
TQID: 'https://experienceleague.adobe.com/DYm1jOVvaGGgUpz51TEXYPNyqvJdMMY-clhvSEiEEyw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5eid: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 994
ht-degree: 98%

---

# Informazioni sull’implementazione di Adobe Analytics e sul modo in cui influisce sull’aggiornamento a Customer Journey Analytics {#implementation-affects-upgrade}

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
>title="AppMeasurement con uno strumento di gestione dei tag di terze parti"
>abstract="Implementazione che utilizza uno strumento di gestione dei tag di terze parti."

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
>abstract="Lavora internamente nella tua organizzazione per determinare il tipo di implementazione attualmente utilizzato per inviare dati ad Adobe Analytics. Quando effettui l’aggiornamento a Customer Journey Analytics, collabora con l’utente o il team che conosce queste informazioni.<br><br>Dopo aver determinato il tipo di implementazione utilizzato dalla tua organizzazione, modifica la risposta nella guida per l’aggiornamento di Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Esistono diversi modi per poter implementare Adobe Analytics. Durante l’aggiornamento a Customer Journey Analytics, non tutti i percorsi di aggiornamento sono disponibili per tutte le implementazioni di Adobe Analytics. Tuttavia, il percorso di aggiornamento consigliato è disponibile indipendentemente da come Adobe Analytics viene implementato nella tua organizzazione.

Utilizza le informazioni seguenti per scoprire l’implementazione corrente di Adobe Analytics e quali percorsi di aggiornamento sono disponibili per la tua organizzazione.

Se hai bisogno di consigli, indicazioni o supporto più specifici, contatta il tuo rappresentante Adobe.

| Implementazione esistente di Adobe Analytics | Descrizione | Percorsi di aggiornamento disponibili |
|---------|----------|----------|
| AppMeasurement | AppMeasurement per JavaScript è sempre stato un metodo comune per implementare Adobe Analytics.<p>Per ulteriori informazioni su questo tipo di implementazione, consulta [Implementare Adobe Analytics con AppMeasurement per JavaScript](https://experienceleague.adobe.com/it/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Consigliato) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore di origine di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrare da Adobe Analytics a Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Estensione di Adobe Analytics (tag) | <p>Tag in Adobe Experience Platform è una soluzione di gestione dei tag che consente di distribuire il codice Analytics insieme ad altri requisiti di assegnazione tag. Adobe offre integrazioni con altre soluzioni e prodotti e consente di implementare codice personalizzato. Tutte queste attività possono essere eseguite senza dover ricorrere a un team di sviluppatori nell’organizzazione per aggiornare il codice sul sito.</p><p>Per ulteriori informazioni su questo tipo di implementazione, consulta [Implementare Adobe Analytics utilizzando l’estensione Analytics](https://experienceleague.adobe.com/it/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Consigliato) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore di origine di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrare da Adobe Analytics a Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK è il metodo attualmente consigliato da Adobe per l’implementazione di Adobe Analytics. Adobe Experience Platform Edge Network ti consente di inviare dati destinati a più prodotti in una posizione centralizzata. <p>Per ulteriori informazioni su questo tipo di implementazione, consulta [Implementare Adobe Analytics con Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Consigliato) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore di origine di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Estensione di Adobe Experience Platform Web SDK (tag) | Experience Platform Web SDK è il metodo attualmente consigliato da Adobe per l’implementazione di Adobe Analytics per i dati web. Adobe Experience Platform Edge Network ti consente di inviare dati destinati a più prodotti in una posizione centralizzata. <p>Per ulteriori informazioni su questo tipo di implementazione, consulta [Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Consigliato) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore di origine di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK è il metodo attualmente consigliato da Adobe per l’implementazione di Adobe Analytics per i dati mobile. Adobe Experience Platform Edge Network ti consente di inviare dati destinati a più prodotti in una posizione centralizzata.<p>Adobe Experience Platform Mobile SDK consente di potenziare le soluzioni e i servizi Adobe CX Enterprise nelle app mobili. </p><p>Per ulteriori informazioni su questo tipo di implementazione, consulta [Implementare Adobe Analytics utilizzando Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Consigliato) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore di origine di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| API di inserimento dati in blocco | API di inserimento dati in blocco (BDIA) è una soluzione Adobe Analytics che consente di caricare i dati delle chiamate al server in batch di file invece di utilizzare librerie lato client come AppMeasurement. </p><p>Per ulteriori informazioni su questo tipo di implementazione, consulta [API di inserimento dati in blocco](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Consigliato) Nuova implementazione di Experience Platform Web SDK per la raccolta dati continua; connettore di origine di Analytics per i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nuova implementazione di Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[API server di Adobe Experience Platform Edge Network ed Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}


