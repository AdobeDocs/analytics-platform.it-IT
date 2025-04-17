---
title: Supporto delle funzioni di Adobe Analytics durante l’aggiornamento a Customer Journey Analytics
description: Scopri il supporto delle funzioni di Adobe Analytics durante l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 88%

---

# Supporto delle funzioni di Adobe Analytics durante l’aggiornamento a Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="Componenti e progetti"
>abstract="I componenti di Adobe Analytics includono: progetti (con le relative tabelle a forma libera e visualizzazioni associate), segmenti e metriche calcolate."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Sovrapposizione Activity Map e tracciamento dei collegamenti"
>abstract="Estensione del browser che consente di visualizzare i dati di tracciamento dei collegamenti come sovrapposizione sul sito."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map-support"
>title="Supporto per la sovrapposizione Activity Map non ancora disponibile"
>abstract="Il supporto per la sovrapposizione Activity Map non è ancora disponibile in Customer Journey Analytics. Sarà disponibile in futuro."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="Dati di classificazione"
>abstract="Raggruppa o categorizza i dati come dimensioni separate."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="Canali di marketing"
>abstract="Crea regole che categorizzano il modo in cui la clientela arriva sul sito."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="Feed dati"
>abstract="Esporta dati non elaborati da Adobe Analytics per l’utilizzo in strumenti e processi esterni."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="Esporta dati elaborati da Adobe Analytics in formato foglio di calcolo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="Dati di file multimediali in streaming"
>abstract="Componente aggiuntivo per Adobe Analytics e Customer Journey Analytics, specializzato nella raccolta dati di file multimediali, come audio, video o contenuti in streaming."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="Migrazione di progetti e componenti"
>abstract="Porta in Customer Journey Analytics i progetti Adobe Analytics e i relativi componenti."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

L’elenco seguente mostra solo le funzioni di Adobe Analytics che richiedono una valutazione durante il processo di aggiornamento a Customer Journey Analytics. Per un elenco completo delle funzionalità di Adobe Analytics completamente supportate, parzialmente supportate o non supportate in Customer Journey Analytics, consulta [Supporto delle funzionalità di Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Valuta quali delle seguenti funzioni di Adobe Analytics desideri continuare a utilizzare quando effettui l’aggiornamento a Customer Journey Analytics:

| Funzionalità di Adobe Analytics | Funzionalità corrispondente in Customer Journey Analytics |
|---------|----------|
| [Componenti e progetti da Adobe Analytics](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [Eseguire la migrazione dei progetti e dei relativi componenti in Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). |
| [Sovrapposizione Activity Map e tracciamento dei collegamenti](https://experienceleague.adobe.com/it/docs/analytics/analyze/activity-map/overview) | Non ancora disponibile |
| [Dati di classificazione](https://experienceleague.adobe.com/it/docs/analytics/components/classifications/c-classifications) | I set di dati di ricerca sono il metodo per classificare i dati in Customer Journey Analytics.<p>[Creare un set di dati di ricerca per ogni dimensione contenente dati di classificazione](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [Canali di marketing](https://experienceleague.adobe.com/it/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | I campi derivati vengono creati all’interno di una visualizzazione dati. <p>[Creare un campo derivato da un canale di marketing.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [Feed dati](https://experienceleague.adobe.com/it/docs/analytics/export/analytics-data-feed/data-feed-overview) | Experience Platform e Customer Journey Analytics forniscono una serie di funzionalità che, in modo indipendente o combinato, possono risolvere i vari requisiti di esportazione. Queste funzionalità includono [API di accesso ai dati di Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=it), [Destinazioni Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=it), [Esportazione tabella completa Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) e [Integrazione strumento BI](/help/data-views/bi-extension.md).<p>Per ulteriori informazioni sulle opzioni di esportazione, vedere [Casi di utilizzo per l&#39;esportazione dei dati](/help/use-cases/data-export/overview.md).</p> |
| [Data Warehouse](https://experienceleague.adobe.com/it/docs/analytics/export/data-warehouse/data-warehouse) | L’[Esportazione tabella completa di Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) è l’evoluzione dei rapporti Data Warehouse in Adobe Analytics, con molte nuove funzioni, spesso richieste, che oggi non sono disponibili in Data Warehouse. |
| [Dati di file multimediali in streaming](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-overview) | I dati multimediali in streaming sono disponibili tramite il connettore di origine di Analytics come parte del pannello Visualizzatori simultanei di contenuti multimediali e del pannello Tempo di riproduzione multimediale utilizzato in Workspace. |
