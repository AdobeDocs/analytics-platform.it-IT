---
title: Informazioni sul supporto delle funzioni di Adobe Analytics durante l’aggiornamento al Customer Journey Analytics
description: Scopri il supporto delle funzioni di Adobe Analytics durante l’aggiornamento al Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1460cbd05cce793b25d026c413744508ab951147
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 29%

---

# Informazioni sul supporto delle funzioni di Adobe Analytics durante l’aggiornamento al Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="Componenti e progetti"
>abstract="I componenti di Adobe Analytics includono: Progetti (con le relative tabelle a forma libera e visualizzazioni associate), segmenti e metriche calcolate."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Sovrapposizione Activity Map e tracciamento dei collegamenti"
>abstract="Estensione del browser che consente di visualizzare i dati di tracciamento dei collegamenti come sovrapposizione sul sito."

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
>abstract="Crea regole che categorizzano il modo in cui i clienti arrivano sul tuo sito."

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
>title="Dati multimediali in streaming"
>abstract="Componente aggiuntivo per Adobe Analytics, specializzato nella raccolta di dati di contenuti multimediali, come audio, video o contenuti in streaming."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Usa le informazioni in questa pagina per rispondere alle domande nell&#39;elenco di controllo per l&#39;aggiornamento di [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Nell&#39;elenco seguente vengono visualizzate solo le funzionalità incluse nell&#39;elenco di controllo per l&#39;aggiornamento di [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/). Per un elenco completo delle funzionalità di Adobe Analytics supportate, parzialmente supportate o non supportate nel Customer Journey Analytics, vedere [Supporto delle funzionalità di Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Considera quali delle seguenti funzioni di Adobe Analytics desideri continuare a utilizzare quando effettui l’aggiornamento al Customer Journey Analytics:

| Funzione di Adobe Analytics | Caratteristica corrispondente nel Customer Journey Analytics |
|---------|----------|
| [Componenti e progetti da Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [Migra i progetti e i relativi componenti al Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). |
| [Sovrapposizione Activity Map e tracciamento dei collegamenti](https://experienceleague.adobe.com/en/docs/analytics/analyze/activity-map/overview) | Non ancora disponibile |
| [Dati di classificazione](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/c-classifications) | I set di dati di ricerca sono il metodo per classificare i dati in Customer Journey Analytics.<p>[Crea un set di dati di ricerca per ogni dimensione contenente i dati di classificazione.](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [Canali di marketing](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | I campi derivati vengono creati all’interno di una visualizzazione dati. <p>[Crea un campo derivato da canale di marketing.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [Feed dati](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | L’esportazione dei set di dati di prima generazione è disponibile tramite l’[API di accesso ai dati di Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=it) e attraverso le [destinazioni di Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=it). Queste opzioni forniscono l’esportazione a livello di evento/riga di tutti i dati raccolti o acquisiti nel data lake di Experience Platform. Le colonne dei dati di post-elaborazione non sono disponibili perché le colonne post vengono calcolate in fase di query. L’esportazione delle colonne post è disponibile tramite il reporting. |
| [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | L’[Esportazione tabella completa di Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) è l’evoluzione dei rapporti Data Warehouse in Adobe Analytics, con molte nuove funzioni, spesso richieste, che oggi non sono disponibili in Data Warehouse. |
| [Dati multimediali in streaming](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-overview) | I dati multimediali in streaming sono disponibili tramite il connettore di origine di Analytics come parte del pannello Visualizzatori simultanei di contenuti multimediali e del pannello Tempo di riproduzione multimediale utilizzato in Workspace. |

