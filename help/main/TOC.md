---
git-repo: https://github.com/AdobeDocs/analytics-platform.it-IT
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Guida di Customer Journey Analytics
user-guide-description: Scopri Adobe Customer Journey Analytics e come utilizzare Analysis Workspace con i dati di Experience Platform.
breadcrumb-title: Guida di Customer Journey Analytics
source-git-commit: 663c7442bce8222f5163b0c8e38afb087b268ad9
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 98%

---

# Guida di Adobe Customer Journey Analytics {#using}

+ [Guida di Adobe Customer Journey Analytics](../getting-started/cja-landing.md)

+ Note sulla versione {#releases}
   + [Versione più recente](../release-notes/latest.md)
   + [Note pre-release](../release-notes/pre-release-notes.md)
   + [Versioni del 2025](../release-notes/2025.md)
   + [Versioni del 2024](../release-notes/2024.md)
   + [Versioni del 2023](../release-notes/2023.md)
   + [Versioni del 2022](../release-notes/2022.md)
   + [Versioni del 2021](../release-notes/2021.md)
   + [Versioni del 2020](../release-notes/2020.md)
   + [Strategia di rilascio delle funzioni](../release-notes/releases.md)
   + [Aggiornamenti alla documentazione](../release-notes/doc-changes.md)

+ Introduzione {#cja-overview}
   + Customer Journey Analytics {#cja-b2c-overview}
      + [Panoramica](../getting-started/cja-overview.md)
      + [Guida rapida](../getting-started/cja-getting-started.md)
      + [Pagina di destinazione](../getting-started/landing.md)
      + [Domande frequenti](../getting-started/cja-faq.md)
      + [Confronto con soluzioni BI](../getting-started/cja-vs-bi.md)
      + [Assistente IA](../ai-assistant.md)
      + [Agente Data Insights](../data-analysis-ai.md)
   + Customer Journey Analytics B2B Edition {#cja-b2b}
      + [Panoramica](/help/getting-started/cja-b2b-edition.md)
      + [Concetti e funzioni B2B](/help/getting-started/cja-b2b-concepts-features.md)
      + [Guida rapida](/help/getting-started/cja-b2b-quick-start-guide.md)
      + [Guida alla transizione](/help/getting-started/cja-b2b-transition.md)

+ Aggiornamento e confronto {#compare-aa-cja}
   + Aggiornamento a Customer Journey Analytics {#upgrade-to-cja}
      + [Introduzione](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [Scegliere il percorso di aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Inviare i dati a Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [Conservare i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
      + [Processo di aggiornamento consigliato](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)
      + Architettura e creazione di uno schema {#schema}
         + [Progettare lo schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)
         + [Creare lo schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)
         + [Utilizzare lo schema esistente](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)
      + Creare uno stream di dati {#create-datastream}
         + [Creare uno stream di dati](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)
         + [Aggiungere Platform come servizio](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)
      + Creare set di dati {#create-datasets}
         + [Creare un set di dati](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)
         + [Creare set di dati di ricerca per le classificazioni](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)
         + [Monitorare l’acquisizione del set di dati](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)
      + Implementare Web SDK con i tag {#create-tags}
         + [Creare un tag per la proprietà](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)
         + [Aggiungere l’estensione Web SDK al tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)
         + [Implementare il tag loader per l’estensione Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)
         + [Aggiungere la logica di raccolta dati XDM al tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)
      + [Implementare Web SDK manualmente](/help/getting-started/cja-upgrade/cja-upgrade-manual.md)
      + [Implementare Web SDK con l’API](/help/getting-started/cja-upgrade/cja-upgrade-api.md)
      + [Creare una connessione](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)
      + [Creare una visualizzazione dati](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)
      + [Creare un campo derivato da un canale di marketing](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)
      + [Convalidare il flusso di dati](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)
      + [Impostare Streaming Media Collection](/help/getting-started/cja-upgrade/cja-upgrade-streaming-media.md)
      + Conservare i dati storici con il connettore di origine di Analytics {#historical-data-source-connector}
         + [Creare uno schema XDM per il connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)
         + [Creare il connettore di origine di Analytics e mappare i campi](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)
         + [Aggiungere il set di dati del connettore di origine di Analytics alla connessione](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)
      + [Valutare quando disabilitare Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)
      + [Disabilitare Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)
      + Metodi di aggiornamento alternativi {#alternative-upgrade-methods}
         + [Utilizzare la raccolta dati di AppMeasurement](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)
         + [Inviare il livello dati](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)
         + [Connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)
      + Altri scenari di aggiornamento {#other-upgrade-scenarios}
         + [Passare dal connettore di origine di Analytics a Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)
         + [Aggiornamento da una soluzione diversa da Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-third-party-solution.md)
      + Informazioni aggiuntive {#additional-information}
         + [Informazioni sull’implementazione di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md)
         + [Supporto delle funzioni di Adobe Analytics durante l’aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)
         + [Funzioni di Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md)
         + [Opzioni di implementazione di Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md)
         + [Configurazione di Adobe Analytics Web SDK per Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)
         + [Utilizzare la personalizzazione con Adobe Journey Optimizer](/help/getting-started/cja-upgrade/cja-upgrade-personalization-journeyoptimizer.md)
   + Confronto con Adobe Analytics {#cja-aa-comparison}
      + [Panoramica](../getting-started/aa-vs-cja/overview.md)
      + [Utilizzare i dati di Adobe Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Funzionalità supportate](../getting-started/aa-vs-cja/cja-aa.md)
      + [Confronto della terminologia](../getting-started/aa-vs-cja/terminology.md)
      + [Confronto dell’elaborazione dati](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Ambienti](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Elaborazione di Analytics rispetto alla preparazione dei dati](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [Identità di Analytics](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Evoluzione da Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Guida per utenti di Adobe Analytics](../getting-started/aa-to-cja-user.md)

+ Acquisizione di dati {#cja-data-ingestion}
   + [Panoramica](../data-ingestion/data-ingestion.md)
   + Guide rapide per l’acquisizione e l’utilizzo{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Experience Platform Edge Network {#edge-network}
         + [Web SDK](../data-ingestion/aepwebsdk.md)
         + [Mobile SDK](../data-ingestion/aepmobilesdk.md)
         + [API server](../data-ingestion/serverapi.md)
      + [Dati batch](../data-ingestion/batch.md)
      + [Dati in streaming](../data-ingestion/streaming.md)
      + [Connettori di origine](../data-ingestion/sources.md)
      + [Dati ad hoc](/help/data-ingestion/adhoc.md)

+ Mirroring dati {#cja-data-mirror}
   + [Panoramica](/help/data-mirror/data-mirror.md)
   + Configurare {#configure}
      + [Soluzioni native per data warehouse](/help/data-mirror/datawarehouse.md)
      + [Experience Platform](/help/data-mirror/aep.md)
      + [Customer Journey Analytics](/help/data-mirror/cja.md)
   + [Guida rapida di Data Mirror](/help/data-mirror/model-based.md)

+ Connessioni {#cja-connections}
   + [Panoramica sulle connessioni](../connections/overview.md)
   + [Creare o modificare una connessione](../connections/create-connection.md)
   + [Gestire le connessioni](../connections/manage-connections.md)
   + [Set di dati evento combinati](../connections/combined-dataset.md)
   + [Ricerche standard](../connections/standard-lookups.md)
   + [Ricerche B2B](../connections/transform-datasets-b2b-lookups.md)

+ Visualizzazioni dati {#cja-dataviews}
   + [Panoramica delle visualizzazioni dati](../data-views/data-views.md)
   + [Creare o modificare una visualizzazione di dati](../data-views/create-dataview.md)
   + [Impostazioni di sessione](../data-views/session-settings.md)
   + Impostazioni dei componenti {#component-settings}
      + [Panoramica delle impostazioni dei componenti](../data-views/component-settings/overview.md)
      + [Attribuzione](../data-views/component-settings/attribution.md)
      + [Comportamento](../data-views/component-settings/behavior.md)
      + [Formato](../data-views/component-settings/format.md)
      + [Includere valori di esclusione](../data-views/component-settings/include-exclude-values.md)
      + [Deduplica delle metriche](../data-views/component-settings/metric-deduplication.md)
      + [Opzioni per “Nessun valore”](../data-views/component-settings/no-value-options.md)
      + [Persistenza](../data-views/component-settings/persistence.md)
      + [Sottostringa](../data-views/component-settings/substring.md)
      + [Gruppo di dati di riepilogo](../data-views/component-settings/summary-data-group.md)
      + [Bucket dei valori](../data-views/component-settings/value-bucketing.md)
   + [Documentazione dei componenti standard](../data-views/component-reference.md)
   + [Estensione BI](../data-views/bi-extension.md)
   + [Campi derivati](../data-views/derived-fields/derived-fields.md)
   + [Dati di riepilogo](../data-views/summary-data.md)
   + [Etichette e criteri](../data-views/data-governance.md)
   + Metriche e dimensioni condivise{#shared-metrics-dimensions}
      + [Panoramica](/help/data-views/shared-metrics-dimensions/smd-overview.md)
      + [Editor](/help/data-views/shared-metrics-dimensions/shared-component-editor.md)

+ Strumenti {#tools}
   + Trasferimento risorse {#asset-transfer}
      + [Trasferire le risorse](../tools/asset-transfer/transfer-assets.md)
   + Utilizzo del prodotto {#product-usage}
      + [Panoramica](../tools/product-usage/usage-overview.md)
      + [Impostazioni dei dati](../tools/product-usage/data-settings.md)
      + [Impostazioni di rinuncia](../tools/product-usage/opt-out-settings.md)

+ Progetti Workspace {#cja-workspace}
   + [Panoramica di Analysis Workspace](../analysis-workspace/home.md)
   + [Eseguire analisi di base](../analysis-workspace/perform-basic-analysis.md)
   + [Eseguire analisi avanzate](../analysis-workspace/perform-adv-analysis.md)
   + Progetti {#build-workspace-project}
      + [Panoramica](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Avviare rapidamente i progetti](/help/analysis-workspace/build-workspace-project/starter-projects.md)
      + [Creare progetti](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Aprire i progetti](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [Aggiungere commenti nei progetti](/help/analysis-workspace/build-workspace-project/comment-projects.md)
      + [Salvare i progetti](../analysis-workspace/build-workspace-project/save-projects.md)
      + [Sommario](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
      + Cartelle in Workspace {#workspace-folders}
         + [Panoramica](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Creare le cartelle](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Gestire le cartelle](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [Aggiungere o spostare i progetti](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [Tasti di scelta rapida](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Palette di colori](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Densità di visualizzazione](../analysis-workspace/build-workspace-project/view-density.md)
      + [Debugger](../analysis-workspace/build-workspace-project/debugger.md)
   + Modelli {#templates}
      + [Utilizzare i modelli](../analysis-workspace/templates/use-templates.md)
      + [Creare e gestire i modelli](../analysis-workspace/templates/create-templates.md)
   + Visualizzazioni {#visualizations}
      + [Panoramica](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Gestione delle origini dati](../analysis-workspace/visualizations/t-sync-visualization.md)
      + [Didascalie intelligenti](../analysis-workspace/visualizations/intelligent-captions.md)
      + Tabella a forma libera {#freeform-table}
         + [Panoramica](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + [Creare collegamenti ipertestuali](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
         + Impostazioni colonna e riga {#column-row-settings}
            + [Impostazioni colonna](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Impostazioni riga](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Elementi statici e dinamici](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtrare e ordinare](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Totali](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Tabella coorte {#cohort-table}
         + [Panoramica](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configurare](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Casi d’uso](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Fallout {#fallout}
         + [Panoramica](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configurare](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Abbandono interdimensionale](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Applicare i segmenti](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flusso {#flow}
         + [Panoramica](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Configurare](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Flussi interdimensionali](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + Area di lavoro del percorso {#journey-canvas}
         + [Panoramica](../analysis-workspace/visualizations/journey-canvas/journey-canvas.md)
         + [Configurare](../analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)
         + [Risoluzione dei problemi](../analysis-workspace/visualizations/journey-canvas/journey-canvas-troubleshooting.md)
      + [Superfici (sovrapposte)](../analysis-workspace/visualizations/area.md)
      + [Barre (sovrapposte)](../analysis-workspace/visualizations/bar.md)
      + [Bullet](../analysis-workspace/visualizations/bullet-graph.md)
      + [Combinato](../analysis-workspace/visualizations/combo-charts.md)
      + [Ad anello](../analysis-workspace/visualizations/donut.md)
      + [Istogramma](../analysis-workspace/visualizations/histogram.md)
      + [Barre orizzontali (sovrapposte)](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Riepilogo delle metriche chiave](../analysis-workspace/visualizations/key-metric.md)
      + [A linee](../analysis-workspace/visualizations/line.md)
      + [Mappa](/help/analysis-workspace/visualizations/map.md)
      + [A dispersione](../analysis-workspace/visualizations/scatterplot.md)
      + [Intestazione di sezione](/help/analysis-workspace/visualizations/section-header.md)
      + [Numero e variazione di riepilogo](../analysis-workspace/visualizations/summary-number-change.md)
      + [Testo](../analysis-workspace/visualizations/text.md)
      + [Mappa ad albero](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Pannelli {#panels}
      + [Panoramica](../analysis-workspace/c-panels/panels.md)
      + [Pannello vuoto](../analysis-workspace/c-panels/blank-panel.md)
      + [Attribuzione](../analysis-workspace/c-panels/attribution.md)
      + [Sperimentazione](../analysis-workspace/c-panels/experimentation.md)
      + [A forma libera](../analysis-workspace/c-panels/freeform-panel.md)
      + [Pubblico medio per minuto del file multimediale](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [Visualizzatori simultanei di file multimediali](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Tempo trascorso su contenuti multimediali](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [Elemento successivo o precedente](../analysis-workspace/c-panels/next-previous.md)
      + [Quick Insights](../analysis-workspace/c-panels/quickinsight.md)
   + Curare e condividere {#curate-share}
      + [Panoramica](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Curare progetti](../analysis-workspace/curate-share/curate.md)
      + [Condividere progetti](../analysis-workspace/curate-share/share-projects.md)
      + [Creare collegamenti condivisibili](../analysis-workspace/curate-share/shareable-links.md)
      + [Progetti di sola lettura](../analysis-workspace/curate-share/view-only-projects.md)
      + [Genera presentazioni](/help/analysis-workspace/curate-share/generate-presentations.md)
   + Esportare {#export}
      + [Panoramica](../analysis-workspace/export/export-project-overview.md)
      + [Scaricare](../analysis-workspace/export/download-send.md)
      + [Invio e pianificazione](../analysis-workspace/export/t-schedule-report.md)
      + [Esportare nel cloud](../analysis-workspace/export/export-cloud.md)
   + Attribution {#attribution}
      + [Panoramica su Attribution](../analysis-workspace/attribution/overview.md)
      + [Modello, contenitore e intervallo di lookback](../analysis-workspace/attribution/models.md)
      + [Attribuzione algoritmica](../analysis-workspace/attribution/algorithmic.md)
      + [Best practice](../analysis-workspace/attribution/best-practices.md)
      + [Domande frequenti](../analysis-workspace/attribution/faq.md)
   + Rilevamento delle anomalie {#anomaly-detection}
      + [Panoramica](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Visualizzare le anomalie](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [Tecniche statistiche](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + Previsioni {#forecasting}
      + [Panoramica](../analysis-workspace/c-forecast/forecasting.md)
      + [Visualizzare le previsioni](../analysis-workspace/c-forecast/view-forecasts.md)
      + [Tecniche statistiche](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [Preferenze utente](../analysis-workspace/user-preferences.md)
   + Domande frequenti su Workspace e altro {#workspace-faq}
      + [Domande frequenti](../analysis-workspace/workspace-faq/faq.md)
      + [Ottimizzare le prestazioni](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Errori e risoluzione dei problemi](../analysis-workspace/workspace-faq/error-messages.md)
      + [Limitazioni](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Requisiti](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Accessibilità](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Content Analytics {#content-analytics}
   + [Panoramica](/help/content-analytics/content-analytics.md)
   + Rapporto {#report}
      + [Panoramica](/help/content-analytics/report/report.md)
      + [Componenti](/help/content-analytics/report/components.md)
   + Configurazione {#configuration}
      + [Panoramica](/help/content-analytics/config/configuration.md)
      + [Configurazione guidata](/help/content-analytics/config/guided.md)
      + [Configurazione manuale](/help/content-analytics/config/manual.md)
      + [Raccolta dati](/help/content-analytics/config/datacollection.md)

+ Dashboard di Analytics {#cja-dashboards}
   + [Panoramica](../mobile-app/home.md)
   + [Attività del curatore](../mobile-app/curator.md)
   + [Creare scorecard per dispositivi mobili](../mobile-app/create-scorecard.md)
   + [Gestire le scorecard per dispositivi mobili](../mobile-app/manage-scorecard.md)
   + [Preparare il management a utilizzare le dashboard](../mobile-app/set-up-execs.md)
   + [Guida introduttiva per utenti direzionali](../mobile-app/executive.md)

+ Analisi guidata {#guided-analysis}
   + [Panoramica](../guided-analysis/overview.md)
   + [Crescita attiva](../guided-analysis/types/active-growth.md)
   + [Tendenze di conversione](../guided-analysis/types/conversion-trends.md)
   + [Coinvolgimento](../guided-analysis/types/engagement.md)
   + [Impatto sul primo utilizzo](../guided-analysis/types/first-use-impact.md)
   + [Frequenza](../guided-analysis/types/frequency.md)
   + [Funnel](../guided-analysis/types/funnel.md)
   + [Crescita netta](../guided-analysis/types/net-growth.md)
   + [Impatto della versione](../guided-analysis/types/release-impact.md)
   + [Conservazione](../guided-analysis/types/retention.md)
   + [Timeline](../guided-analysis/types/timeline.md)
   + [Tendenze](../guided-analysis/types/trends.md)
   + [Casi d’uso di settore](../guided-analysis/industry-use-cases.md)
   + [Domande frequenti](../guided-analysis/faq.md)

+ Componenti {#cja-components}
   + [Panoramica](../components/overview.md)
   + [Utilizzare i componenti](../components/use-components-in-workspace.md)
   + [Aggiungere descrizioni dei componenti](../components/add-component-descriptions.md)
   + Annotazioni {#annotations}
      + [Panoramica](../components/annotations/overview.md)
      + [Creare annotazioni](../components/annotations/create-annotations.md)
      + [Gestire le annotazioni](../components/annotations/manage-annotations.md)
      + [Visualizzare le annotazioni](../components/annotations/view-annotations.md)
      + [Annotazioni delle scorecard per dispositivi mobili](../components/annotations/mobile-annotations.md)
   + Tipi di pubblico {#audiences}
      + [Panoramica dei tipi di pubblico](../components/audiences/audiences-overview.md)
      + [Creare e pubblicare tipi di pubblico](../components/audiences/publish.md)
      + [Gestire i tipi di pubblico](../components/audiences/manage.md)
   + Dimensioni {#dimensions}
      + [Panoramica](../components/dimensions/overview.md)
      + [Anteprima dimensioni](../components/dimensions/view-dimensions.md)
      + [Suddividere dimensioni](../components/dimensions/t-breakdown-fa.md)
      + [Suddividere le dimensioni in base al tempo](../components/dimensions/time-parting-dimensions.md)
      + [Dimensioni a cardinalità elevata](../components/dimensions/high-cardinality.md)
   + [Metriche](../components/apply-create-metrics.md)
   + Segmenti {#segments}
      + [Panoramica](/help/components/segments/seg-overview.md)
      + [Creare i segmenti](/help/components/segments/seg-create.md)
      + [Generare i segmenti](/help/components/segments/seg-builder.md)
      + [Segmenti rapidi](/help/components/segments/seg-quick.md)
      + [Segmenti sequenziali](/help/components/segments/seg-sequential-build.md)
      + [Condividere i segmenti](/help/components/segments/seg-share.md)
      + [Assegnare tag ai segmenti](/help/components/segments/seg-tag.md)
      + [Filtrare l’elenco dei segmenti](/help/components/segments/seg-filter.md)
      + [Contrassegnare i segmenti come preferiti](/help/components/segments/seg-favorite.md)
      + [Approvare i segmenti](/help/components/segments/seg-approve.md)
      + [Copiare segmenti](/help/components/segments/seg-copy.md)
      + [Gestire i segmenti](/help/components/segments/seg-manage.md)
      + [Operatori](/help/components/segments/seg-operators.md)
      + [Utilizzare i segmenti](/help/components/segments/seg-use.md)
   + Metriche calcolate {#cja-calcmetrics}
      + [Panoramica](../components/calc-metrics/calc-metr-overview.md)
      + Flusso di lavoro {#cm-workflow}
         + [Creare metriche calcolate](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Trovare metriche](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Generare metriche calcolate](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Un esempio semplice](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Un esempio più complesso](../components/calc-metrics/cm-workflow/cm-orders-participation.md)
         + [Tipo di metrica e attribuzione](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Metriche di partecipazione.](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Metriche segmentate](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Sovrapponi e sostituisci segmenti](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Filtrare le metriche calcolate](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Contrassegnare le metriche calcolate come preferite](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [Copiare le metriche calcolate](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [Usare le funzioni](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Assegnare tag alle metriche calcolate](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Approvare le metriche calcolate](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Condividere le metriche calcolate](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Gestire le metriche calcolate](../components/calc-metrics/cm-workflow/cm-manager.md)
         + [Esempi](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
      + [Modelli di metriche calcolate](../components/calc-metrics/default-calcmetrics.md)
      + [Funzioni di base](../components/calc-metrics/cm-functions.md)
      + [Funzioni avanzate](../components/calc-metrics/cm-adv-functions.md)
   + Intervalli di date {#cja-date-ranges}
      + [Panoramica](../components/date-ranges/overview.md)
      + [Creare intervalli di date](../components/date-ranges/create.md)
      + [Gestire gli intervalli di date](../components/date-ranges/manage.md)
      + [Confronto delle date](../components/date-ranges/time-comparison.md)
      + [Esempi](../components/date-ranges/custom-date-ranges.md)
   + Avvisi {#alerts}
      + [Panoramica](/help/components/c-intelligent-alerts/intelligent-alerts.md)
      + [Creare avvisi](/help/components/c-intelligent-alerts/alert-builder.md)
      + [Gestire gli avvisi](/help/components/c-intelligent-alerts/alert-manager.md)
      + [Confronto delle funzioni](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)
      + [Casi d’uso](/help/components/c-intelligent-alerts/alerts-use-cases.md)
   + Esportazioni {#exports}
      + [Configurare account di esportazione cloud](/help/components/exports/cloud-export-accounts.md)
      + [Configurare le posizioni di esportazione cloud](/help/components/exports/cloud-export-locations.md)
      + [Gestire le posizioni di esportazione cloud](/help/components/exports/manage-export-locations.md)
      + [Gestire le esportazioni](/help/components/exports/manage-exports.md)
      + [Gestire i registri di esportazione](/help/components/exports/manage-export-logs.md)
      + [Risolvere i problemi relativi alle esportazioni](/help/components/exports/troubleshoot-exports.md)
   + Dizionario dati {#data-dictionary}
      + [Panoramica](../components/data-dictionary/data-dictionary-overview.md)
      + [Visualizzare le informazioni sui componenti nel dizionario dati](../components/data-dictionary/view-data-dictionary.md)
      + [Modificare le voci dei componenti nel dizionario dati](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Monitorare l’integrità del dizionario dati](../components/data-dictionary/monitor-data-dictionary-health.md)
   + Reporting in tempo reale {#real-time-reporting}
      + [Panoramica](/help/components/real-time/real-time.md)
      + [Utilizzare il reporting in tempo reale](/help/components/real-time/use-real-time.md)
   + [Progetti pianificati](../components/scheduled-projects-manager.md)
+ Report Builder {#cja-reportbuilder}
   + [Panoramica](../report-builder/rb-overview.md)
   + [Configurazione di Report Builder](../report-builder/report-builder-setup.md)
   + [Creare un blocco di dati](../report-builder/create-a-data-block.md)
   + [Hub Report Builder](../report-builder/report-builder-hub.md)
   + [Selezionare una visualizzazione dati](../report-builder/select-data-view.md)
   + [Selezionare un intervallo di date](../report-builder/select-date-range.md)
   + [Utilizzare i segmenti](../report-builder/work-with-filters.md)
   + [Filtrare le dimensioni](../report-builder/filter-dimensions.md)
   + [Gestire i blocchi di dati](../report-builder/manage-reportbuilder.md)
   + [Pianificare le cartelle di lavoro per l’e-mail](../report-builder/schedule-reportbuilder.md)
   + [Pianificare le cartelle di lavoro per le esportazioni cloud](../report-builder/report-builder-export.md)
   + [Gestire le pianificazioni delle cartelle di lavoro](/help/report-builder/manage-schedules-reportbuilder.md)
   + [Etichette limitate](../report-builder/restricted-labels.md)
   + [Impostazioni di Report Builder](../report-builder/report-builder-settings.md)


+ Reporting Activity Manager {#reporting-activity-manager}
   + [Panoramica](../reporting-activity-manager/reporting-activity-overview.md)
   + [Visualizzare l’attività di reporting](../reporting-activity-manager/reporting-activity.md)
   + [Annullare le richieste di reporting](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Unione {#stitching}
   + [Panoramica](/help/stitching/overview.md)
   + [Unione basata su campi](/help/stitching/fbs.md)
   + [Unione basata su grafico](/help/stitching/gbs.md)
   + [Utilizzare l’unione](/help/stitching/use-stitching.md)
   + [Utilizzare l’unione](/help/stitching/use-stitching-ui.md)
   + [Creare e gestire i set di dati con unione delle identità](/help/stitching/stitching-ui.md)
   + [Convalidare l’unione delle identità](/help/stitching/validate.md)
   + [Domande frequenti](/help/stitching/faq.md)

+ Integrazioni Adobe {#integrations}
   + [Panoramica](/help/integrations/overview.md)
   + [Integrare Adobe Analytics](/help/integrations/aa.md)
   + [Integrare Target](/help/integrations/at.md)
   + [Integrare i dati di Journey Optimizer](/help/integrations/ajo.md)
   + [Integrare i dati di gestione delle decisioni](/help/integrations/ajo-od.md)
   + [Configurare IA per l’analisi dei clienti](/help/integrations/customer-ai.md)
   + [Integrare Adobe Advertising](/help/integrations/advertising.md)

+ Governance dei dati {#cja-privacy}
   + [Governance dei dati](../privacy/privacy-overview.md)
   + [Registro di controllo](../privacy/audit-log.md)
   + [Chiavi gestite dal cliente](../privacy/cmk.md)

+ Casi d’uso {#cja-usecases}
   + [Casi d’uso di Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Dati Adobe Analytics {#aa-data}
      + [Utilizzare le dimensioni del canale di marketing](../use-cases/aa-data/marketing-channels.md)
      + [Combinare suite di rapporti con schemi diversi](../use-cases/aa-data/combine-report-suites.md)
   + B2B {#b2b}
      + [Un esempio di progetto B2B basato su persona](../use-cases/b2b/example.md)
      + B2B Edition {#b2b-edition}
         + [Panoramica dei casi d’uso](/help/use-cases/b2b/b2b-edition/use-cases-overview.md)
         + [Configurazione](/help/use-cases/b2b/b2b-edition/setup.md)
         + [Ottimizzare il marketing per account](/help/use-cases/b2b/b2b-edition/optimize-account-marketing.md)
         + [Far crescere gli account chiave](/help/use-cases/b2b/b2b-edition/grow-key-accounts.md)
         + [Creare valore di prodotto](/help/use-cases/b2b/b2b-edition/build-product-value.md)
   + Dati complessi {#complex-data}
      + [Utilizzare gli array di oggetti](../use-cases/object-arrays.md)
   + Dati cross-channel {#cross-channel}
      + [Analizzare i dati tra canali diversi](../use-cases/cross-channel/cross-channel.md)
      + [Importare dati Web e call center](../use-cases/cross-channel/call-center.md)
   + Esportazione dei dati {#data-export}
      + [Panoramica](../use-cases/data-export/overview.md)
      + [Estensione BI](../use-cases/data-export/bi-extension.md)
      + [Esportare i set di dati](../use-cases/data-export/export-datasets.md)
      + [Esportare tabelle complete](../use-cases/data-export/export-full-table.md)
      + [Query Service ed esportazione di set di dati](../use-cases/data-export/queryservice-export-datasets.md)
   + Acquisizione di dati {#data-ingestion}
      + [Acquisire e utilizzare i dati di Marketo Engage](../use-cases/data-ingestion/marketo.md)
      + [Acquisire e utilizzare i tipi di pubblico di Experience Platform](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Visualizzazioni dati {#data-views}
      + [Casi d’uso per le visualizzazioni dati](/help/use-cases/data-views/data-views-usecases.md)
      + [Utilizzare dimensioni e metriche di binding](/help/use-cases/data-views/binding-dimensions-metrics.md)
      + [Utilizzare i dati di riepilogo](/help/use-cases/data-views/summary-data.md)
      + [Casi d’uso dell’estensione BI](/help/use-cases/data-views/bi-extension-usecases.md)
   + Campi derivati {#derived-fields}
      + [Rapporto sugli obiettivi](../use-cases/goals-using-derived-fields.md)
   + Analisi del prodotto {#product-analysis}
      + [Analisi del prodotto](/help/use-cases/product-analysis.md)
   + Unione {#stitching}
      + [Dispositivi condivisi](/help/use-cases/stitching/shared-devices.md)
   + Dati di terze parti {#third-party}
      + [Panoramica](/help/use-cases/third-party/overview.md)
      + Google Analytics {#ga}
         + [Migrare i dati da Google Analytics](/help/use-cases/third-party/ga/overview.md)
         + [Acquisire dati storici di Google Analytics](/help/use-cases/third-party/ga/backfill.md)
         + [Configurare i dati in streaming di Google Analytics](/help/use-cases/third-party/ga/streaming.md)
         + [Rapporti sui dati di Google Analytics](/help/use-cases/third-party/ga/report.md)
      + Quantum Metric {#qm}
         + [Panoramica](/help/use-cases/third-party/quantum-metric/qm-overview.md)
         + [Collegare le ripetizioni di sessioni](/help/use-cases/third-party/quantum-metric/tie-session-replays.md)
         + [Utilizzare le mappe di calore](/help/use-cases/third-party/quantum-metric/heatmap.md)
         + [Aggiungere eventi di attrito](/help/use-cases/third-party/quantum-metric/friction-events.md)
         + [Connettore di origine](/help/use-cases/third-party/quantum-metric/source-connector.md)

+ Labs {#labs}
   + [Guida utente di Labs](../labs/labs.md)

+ Risoluzione dei problemi {#troubleshooting}
   + [Confrontare dati](../troubleshooting/compare.md)
   + [Coerenza di metriche e tipi di pubblico](../troubleshooting/consistency-rcdp-cja.md)
   + [Mancanza di autorizzazioni](../troubleshooting/lack-of-permissions.md)

+ Note tecniche {#technotes}
   + [Controllo degli accessi](../technotes/access-control.md)
   + [Data center](../technotes/data-centers.md)
   + [Implicazioni dell’eliminazione](../technotes/deletion.md)
   + [Domini](../technotes/domains.md)
   + [Glossario](../technotes/glossary.md)
   + [Guardrail](../technotes/guardrails.md)
   + [Indirizzi IP](../technotes/ip-addresses.md)
   + [Ottimizzare le prestazioni](../technotes/optimizing-performance.md)
   + [Gestire l’utilizzo](../technotes/estimate-usage.md)

+ [API di Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/)
