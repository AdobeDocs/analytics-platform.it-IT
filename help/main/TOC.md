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
source-git-commit: 04a95b6e502a8a1c1e686738d490d2a40936e738
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 91%

---


# Guida di Adobe Customer Journey Analytics {#using}

+ [Guida di Adobe Customer Journey Analytics](../getting-started/cja-landing.md)
+ [Assistente IA per Adobe Customer Journey Analytics](../ai-assistant.md)
+ Note sulla versione {#releases}
   + [Versione più recente](../release-notes/latest.md)
   + [Versioni del 2024](../release-notes/2024.md)
   + [Versioni del 2023](../release-notes/2023.md)
   + [Versioni del 2022](../release-notes/2022.md)
   + [Versioni del 2021](../release-notes/2021.md)
   + [Versioni del 2020](../release-notes/2020.md)
   + [Strategia di rilascio delle funzioni](../release-notes/releases.md)
   + [Aggiornamenti alla documentazione](../release-notes/doc-changes.md)

+ Introduzione {#cja-overview}
   + [Panoramica di Customer Journey Analytics](../getting-started/cja-overview.md)
   + [Guida rapida](../getting-started/cja-getting-started.md)
   + [Pagina di destinazione](../getting-started/landing.md)
   + [Pagina di destinazione (precedente)](../getting-started/cja-landing-old.md)
   + [Domande frequenti](../getting-started/cja-faq.md)
   + [Confronto tra Customer Journey Analytics e soluzioni BI](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics e Adobe Analytics {#compare-aa-cja}
   + Aggiornamento a Customer Journey Analytics {#upgrade-to-cja}
      + [Introduzione](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [Scegliere il percorso di aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Inviare i dati a Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [Conservare i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
   + Confronto con Adobe Analytics {#cja-aa-comparison}
      + [Panoramica](../getting-started/aa-vs-cja/overview.md)
      + [Utilizzare i dati di Adobe Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Funzionalità supportate](../getting-started/aa-vs-cja/cja-aa.md)
      + [Confrontare la terminologia](../getting-started/aa-vs-cja/terminology.md)
      + [Confrontare l’elaborazione dati](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Ambienti](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Elaborazione di Analytics e preparazione dati](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [Identità di Analytics](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Evoluzione da Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Guida per utenti di Adobe Analytics](../getting-started/aa-to-cja-user.md)

+ Acquisizione dei dati {#cja-data-ingestion}
   + [Panoramica sull’acquisizione di dati](../data-ingestion/data-ingestion.md)
   + Inserire e utilizzare le guide introduttive{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Rete Edge di Adobe Experience Platform {#edge-network}
         + [Web SDK](../data-ingestion/aepwebsdk.md)
         + [Mobile SDK](../data-ingestion/aepmobilesdk.md)
         + [API server](../data-ingestion/serverapi.md)
      + [Dati batch](../data-ingestion/batch.md)
      + [Dati in streaming](../data-ingestion/streaming.md)
      + [Connettori di origine](../data-ingestion/sources.md)

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
      + [Attribution](../data-views/component-settings/attribution.md)
      + [Comportamento](../data-views/component-settings/behavior.md)
      + [Formato](../data-views/component-settings/format.md)
      + [Includere valori di esclusione](../data-views/component-settings/include-exclude-values.md)
      + [Deduplicazione delle metriche](../data-views/component-settings/metric-deduplication.md)
      + [Opzioni per “Nessun valore”](../data-views/component-settings/no-value-options.md)
      + [Persistenza](../data-views/component-settings/persistence.md)
      + [Sottostringa](../data-views/component-settings/substring.md)
      + [Gruppo di dati di riepilogo](../data-views/component-settings/summary-data-group.md)
      + [Bucketing dei valori](../data-views/component-settings/value-bucketing.md)
   + [Documentazione dei componenti standard](../data-views/component-reference.md)
   + [Estensione BI](../data-views/bi-extension.md)
   + [Campi derivati](../data-views/derived-fields/derived-fields.md)
   + [Dati di riepilogo](../data-views/summary-data.md)
   + [Etichette e criteri](../data-views/data-governance.md)

+ Strumenti {#tools}
   + Utilizzo prodotto {#product-usage}
      + [Panoramica](../tools/product-usage/usage-overview.md)
      + [Impostazioni dati](../tools/product-usage/data-settings.md)
      + [Impostazioni di rinuncia](../tools/product-usage/opt-out-settings.md)

+ Progetti Workspace {#cja-workspace}
   + [Panoramica di Analysis Workspace](../analysis-workspace/home.md)
   + [Eseguire analisi di base](../analysis-workspace/perform-basic-analysis.md)
   + [Eseguire analisi avanzate](../analysis-workspace/perform-adv-analysis.md)
   + Progetti {#build-workspace-project}
      + [Panoramica dei progetti](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Creare progetti](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Progetti aperti](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [Salvare progetti](../analysis-workspace/build-workspace-project/save-projects.md)
      + Cartelle in Workspace {#workspace-folders}
         + [Informazioni sulle cartelle in Workspace](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Creare cartelle e sottocartelle](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Gestione cartelle](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [Aggiungere o spostare progetti nelle cartelle](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [Tasti di scelta rapida](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Tavolozze dei colori](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Densità di visualizzazione](../analysis-workspace/build-workspace-project/view-density.md)
   + Visualizzazioni {#visualizations}
      + [Panoramica delle visualizzazioni](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Gestione delle origini dati](../analysis-workspace/visualizations/t-sync-visualization.md)
      + [Didascalie intelligenti](../analysis-workspace/visualizations/intelligent-captions.md)
      + Tabella a forma libera {#freeform-table}
         + [Panoramica](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + [Creare collegamenti ipertestuali](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
         + Impostazioni colonna e riga {#column-row-settings}
            + [Impostazioni colonna](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Impostazioni riga](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Elementi dinamici e statici](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtrare e ordinare tabelle](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Totali in Workspace](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Tabella coorte {#cohort-table}
         + [Panoramica](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configurare](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Casi d’uso](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Abbandono {#fallout}
         + [Panoramica](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configurare](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Abbandono interdimensionale](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Applicazione di filtri](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flusso {#flow}
         + [Panoramica](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Configurare](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Flussi interdimensionali](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + Area di lavoro percorso {#journey-canvas}
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
      + [A dispersione](../analysis-workspace/visualizations/scatterplot.md)
      + [Numero riepilogo e modifica](../analysis-workspace/visualizations/summary-number-change.md)
      + [Intestazione sezione](/help/analysis-workspace/visualizations/section-header.md)
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
      + [Visualizzatori simultanei di contenuti multimediali ](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Tempo di riproduzione dei contenuti multimediali trascorso](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [Elemento successivo o precedente](../analysis-workspace/c-panels/next-previous.md)
      + [Informazioni rapide](../analysis-workspace/c-panels/quickinsight.md)
   + Curare, condividere e pianificare i progetti {#curate-share}
      + [Menu Share](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Curare progetti](../analysis-workspace/curate-share/curate.md)
      + [Condividere progetti](../analysis-workspace/curate-share/share-projects.md)
      + [Creare collegamenti condivisibili](../analysis-workspace/curate-share/shareable-links.md)
      + [Progetti solo visualizzazione](../analysis-workspace/curate-share/view-only-projects.md)
   + Esportazione {#export}
      + [Panoramica](../analysis-workspace/export/export-project-overview.md)
      + [Scaricare](../analysis-workspace/export/download-send.md)
      + [Inviare ad altri](../analysis-workspace/export/t-schedule-report.md)
      + [Esportare nel cloud](../analysis-workspace/export/export-cloud.md)
   + Rilevamento delle anomalie {#anomaly-detection}
      + [Panoramica](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Visualizzare le anomalie in Analysis Workspace](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [Tecniche di statistica utilizzate nel rilevamento delle anomalie](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + Previsione {#forecasting}
      + [Panoramica](../analysis-workspace/c-forecast/forecasting.md)
      + [Visualizzare previsioni in Analysis Workspace](../analysis-workspace/c-forecast/view-forecasts.md)
      + [Tecniche di statistica utilizzate nel servizio di previsione](../analysis-workspace/c-forecast/statistics-forecasting.md)
      + [Sommario ](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
   + [Preferenze utente](../analysis-workspace/user-preferences.md)
   + Domande frequenti su Workspace {#workspace-faq}
      + [Domande frequenti](../analysis-workspace/workspace-faq/faq.md)
      + [Messaggi di errore](../analysis-workspace/workspace-faq/error-messages.md)
      + [Limiti di Analysis Workspace](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Requisiti di amministrazione](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Accessibilità di Analysis Workspace](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Dashboard di Analytics {#cja-dashboards}
   + [Panoramica dei dashboard di Analytics](../mobile-app/home.md)
   + [Attività del curatore](../mobile-app/curator.md)
   + [Creare una scorecard per dispositivi mobili](../mobile-app/create-scorecard.md)
   + [Gestire le scorecard per dispositivi mobili](../mobile-app/manage-scorecard.md)
   + [Preparare gli utenti direzionali a utilizzare le scorecard](../mobile-app/set-up-execs.md)
   + [Guida introduttiva per utenti direzionali](../mobile-app/executive.md)

+ Analisi guidata {#guided-analysis}
   + [Panoramica](../guided-analysis/overview.md)
   + Matrice di funzioni {#feature-matrix}
      + [Coinvolgimento](../guided-analysis/types/engagement.md)
   + Funnel {#funnel}
      + [Visualizzazione attrito](../guided-analysis/types/friction.md)
      + [Visualizzazione delle tendenze di conversione](../guided-analysis/types/conversion-trends.md)
   + Impatto {#impact}
      + [Visualizzazione versione](../guided-analysis/types/release.md)
      + [Visualizzazione primo utilizzo](../guided-analysis/types/first-use.md)
   + Conservazione {#retention}
      + [Tassi di conservazione](../guided-analysis/types/retention-rates.md)
   + Tendenze {#trends}
      + [Visualizzazione utilizzo](../guided-analysis/types/usage.md)
      + [Visualizzazione frequenza](../guided-analysis/types/frequency.md)
   + Crescita degli utenti {#user-growth}
      + [Visualizzazione attiva](../guided-analysis/types/active.md)
      + [Visualizzazione della crescita netta](../guided-analysis/types/net-growth.md)
   + Flusso dell’utente {#streams}
      + [Linea temporale](../guided-analysis/types/timeline.md)
   + [Casi d’uso di settore](../guided-analysis/industry-use-cases.md)
   + [Domande frequenti](../guided-analysis/faq.md)

+ Componenti {#cja-components}
   + [Panoramica dei componenti](../components/overview.md)
   + [Utilizzare i componenti in Analysis Workspace](../components/use-components-in-workspace.md)
   + [Aggiungere descrizioni dei componenti](../components/add-component-descriptions.md)
   + Annotazioni {#annotations}
      + [Panoramica sulle annotazioni](../components/annotations/overview.md)
      + [Creare annotazioni](../components/annotations/create-annotations.md)
      + [Gestire le annotazioni](../components/annotations/manage-annotations.md)
      + [Visualizzare le annotazioni](../components/annotations/view-annotations.md)
      + [Annotazioni per dispositivi mobili](../components/annotations/mobile-annotations.md)
   + [Progetti programmati](../components/scheduled-projects-manager.md)
   + Tipi di pubblico {#audiences}
      + [Panoramica dei tipi di pubblico](../components/audiences/audiences-overview.md)
      + [Creare e pubblicare tipi di pubblico](../components/audiences/publish.md)
      + [Gestire i tipi di pubblico](../components/audiences/manage.md)
   + Dimensioni {#dimensions}
      + [Panoramica delle dimensioni](../components/dimensions/overview.md)
      + [Anteprima dimensioni](../components/dimensions/view-dimensions.md)
      + [Suddividere dimensioni](../components/dimensions/t-breakdown-fa.md)
      + [Suddividere le dimensioni in base al tempo](../components/dimensions/time-parting-dimensions.md)
      + [Dimensioni ad alta cardinalità](../components/dimensions/high-cardinality.md)
   + [Metriche](../components/apply-create-metrics.md)
   + Filtri {#cja-filters}
      + [Panoramica dei filtri](../components/filters/filters-overview.md)
      + [Creare filtri](../components/filters/create-filters.md)
      + [Creare filtri](../components/filters/filter-builder.md)
      + [Filtri rapidi](../components/filters/quick-filters.md)
      + [Filtri sequenziali](../components/filters/seg-sequential-build.md)
      + [Condividere i filtri](../components/filters/filters-share.md)
      + [Assegnare tag ai filtri](../components/filters/filters-tag.md)
      + [Filtrare l’elenco dei filtri](../components/filters/filters-filter.md)
      + [Contrassegnare i filtri come preferiti](../components/filters/filters-favorite.md)
      + [Approvare i filtri](../components/filters/filters-approve.md)
      + [Copiare filtri](../components/filters/filters-copy.md)
      + [Gestire i filtri](../components/filters/manage-filters.md)
      + [Operatori](../components/filters/operators.md)
   + Metriche calcolate {#cja-calcmetrics}
      + [Panoramica delle metriche calcolate](../components/calc-metrics/calc-metr-overview.md)
      + Flusso di lavoro per le metriche calcolate {#cm-workflow}
         + [Creare metriche calcolate](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Creare metriche calcolate](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Trovare metriche](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Tipo di metrica e attribuzione](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Creare una metrica di partecipazione](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Metriche filtrate](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Sovrapporre e sostituire filtri](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Filtrare le metriche calcolate](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Contrassegnare le metriche calcolate come preferite](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [Copiare le metriche calcolate](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [Usare le funzioni](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Assegnare tag alle metriche calcolate](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Approvare le metriche calcolate](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Condividere le metriche calcolate](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Gestire le metriche calcolate](../components/calc-metrics/cm-workflow/cm-manager.md)
         + [Esempi](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
      + [Metriche calcolate predefinite](../components/calc-metrics/default-calcmetrics.md)
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
      + [Panoramica del dizionario dati](../components/data-dictionary/data-dictionary-overview.md)
      + [Visualizzare le informazioni sui componenti nel dizionario dati](../components/data-dictionary/view-data-dictionary.md)
      + [Modificare le voci dei componenti nel dizionario dati](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Monitorare l’integrità del dizionario dati](../components/data-dictionary/monitor-data-dictionary-health.md)

+ Report Builder {#cja-reportbuilder}
   + [Panoramica del Report Builder](../report-builder/report-buider-overview.md)
   + [Configurazione Report Builder](../report-builder/report-builder-setup.md)
   + [Creare un blocco di dati](../report-builder/create-a-data-block.md)
   + [Hub Report Builder](../report-builder/report-builder-hub.md)
   + [Seleziona una visualizzazione dati](../report-builder/select-data-view.md)
   + [Selezionare un intervallo di date](../report-builder/select-date-range.md)
   + [Utilizzare i filtri](../report-builder/work-with-filters.md)
   + [Dimensioni filtro](../report-builder/filter-dimensions.md)
   + [Gestire i blocchi di dati](../report-builder/manage-reportbuilder.md)
   + [Pianificare le cartelle di lavoro](../report-builder/schedule-reportbuilder.md)
   + [Etichette per limitazioni](../report-builder/restricted-labels.md)
   + [Impostazioni Report Builder](../report-builder/report-builder-settings.md)

+ Reporting Activity Manager {#reporting-activity-manager}
   + [Panoramica](../reporting-activity-manager/reporting-activity-overview.md)
   + [Visualizzare l’attività di reporting](../reporting-activity-manager/reporting-activity.md)
   + [Annullare le richieste di reporting](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Unione {#stitching}
   + [Panoramica](../stitching/overview.md)
   + [Creare e gestire i set di dati uniti](../stitching/stitching-ui.md)
   + [Domande frequenti](../stitching/faq.md)

+ Integrazioni Adobe {#integrations}
   + [Panoramica](/help/integrations/overview.md)
   + [Integrare Adobe Analytics](/help/integrations/aa.md)
   + [Integrare Target](/help/integrations/at.md)
   + [Integrare i dati di Journey Optimizer](/help/integrations/ajo.md)
   + [Integrare i dati di gestione delle decisioni](/help/integrations/ajo-od.md)
   + [Configurare IA per l’analisi dei clienti](/help/integrations/customer-ai.md)

+ Governance dei dati {#cja-privacy}
   + [Governance dei dati](../privacy/privacy-overview.md)
   + [Registro di controllo](../privacy/audit-log.md)
   + [Chiavi gestite dal cliente](../privacy/cmk.md)

+ Casi d’uso {#cja-usecases}
   + [Casi d’uso di Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Dati di Google Analytics {#ga}
      + [Migrazione dei dati da Google Analytics alla panoramica di Customer Journey Analytics](../use-cases/ga/overview.md)
      + [Acquisire dati storici Google Analytics in Platform](../use-cases/ga/backfill.md)
      + [Configurare i dati streaming di Google Analytics in Platform](../use-cases/ga/streaming.md)
      + [Rapporto sui dati Google Analytics in Customer Journey Analytics](../use-cases/ga/report.md)
   + Acquisizione dei dati {#data-ingestion}
      + [Acquisire e utilizzare i dati di Marketo Engage](../use-cases/data-ingestion/marketo.md)
      + [Acquisire e utilizzare i tipi di pubblico di Experience Platform](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Visualizzazioni dati {#data-views}
      + [Casi d’uso per le visualizzazioni dati](../use-cases/data-views/data-views-usecases.md)
      + [Utilizzare dimensioni e metriche di binding](../use-cases/data-views/binding-dimensions-metrics.md)
      + [Utilizzare i dati di riepilogo](../use-cases/data-views/summary-data.md)
   + Esportazione dei dati {#data-export}
      + [Panoramica](../use-cases/data-export/overview.md)
      + [Estensione BI](../use-cases/data-export/bi-extension.md)
      + [Esportare i set di dati](../use-cases/data-export/export-datasets.md)
      + [Esportare tabelle complete](../use-cases/data-export/export-full-table.md)
      + [Query Service ed esportazione di set di dati](../use-cases/data-export/queryservice-export-datasets.md)
   + B2B {#b2b}
      + [Un esempio di progetto B2B](../use-cases/b2b/example.md)
   + Dati cross-channel {#cross-channel}
      + [Analizzare i dati tra canali diversi](../use-cases/cross-channel/cross-channel.md)
      + [Importare dati Web e call center](../use-cases/cross-channel/call-center.md)
   + Dati Adobe Analytics {#aa-data}
      + [Utilizzare le dimensioni del canale di marketing](../use-cases/aa-data/marketing-channels.md)
      + [Combinare suite di rapporti con schemi diversi](../use-cases/aa-data/combine-report-suites.md)
   + Dati complessi {#complex-data}
      + [Utilizzare gli array di oggetti](../use-cases/object-arrays.md)
   + Unione {#stitching}
      + [Dispositivi condivisi](/help/use-cases/stitching/shared-devices.md)
   + Campi derivati {#derived-fields}
      + [Utilizzare i campi derivati per creare report sugli obiettivi](../use-cases/goals-using-derived-fields.md)

+ Labs {#labs}
   + [Guida utente di Labs](../labs/labs.md)

+ Risoluzione dei problemi {#troubleshooting}
   + [Confrontare i dati di Adobe Analytics con quelli di Customer Journey Analytics](../troubleshooting/compare.md)
   + [Coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-Time CDP e Customer Journey Analytics](../troubleshooting/consistency-rcdp-cja.md)
   + [Mancanza di autorizzazioni](../troubleshooting/lack-of-permissions.md)

+ Note tecniche {#technotes}
   + [Controllo degli accessi](../technotes/access-control.md)
   + [Data center](../technotes/data-centers.md)
   + [Implicazioni dell’eliminazione](../technotes/deletion.md)
   + [Domini](../technotes/domains.md)
   + [Glossario](../technotes/glossary.md)
   + [Guardrail](../technotes/guardrails.md)
   + [Indirizzi IP](../technotes/ip-addresses.md)
   + [Ottimizzare le prestazioni di Customer Journey Analytics](../technotes/optimizing-performance.md)
   + [Visualizzare e gestire l’utilizzo](../technotes/estimate-usage.md)

+ [API di Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/)
