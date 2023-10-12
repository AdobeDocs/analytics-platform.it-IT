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
source-git-commit: 82e0fbb714852750963e08597b6b1606127e0ac6
workflow-type: tm+mt
source-wordcount: '1024'
ht-degree: 77%

---


# Guida di Adobe Customer Journey Analytics {#using}

+ [Guida di Adobe Customer Journey Analytics](../getting-started/cja-landing.md)

+ Note sulla versione {#releases}
   + [Versione più recente](../release-notes/latest.md)
   + [Versioni del 2023](../release-notes/2023.md)
   + [Versioni del 2022](../release-notes/2022.md)
   + [Versioni del 2021](../release-notes/2021.md)
   + [Versioni del 2020](../release-notes/2020.md)
   + [Versioni Customer Journey Analytics](../release-notes/releases.md)
   + [Aggiornamenti della documentazione di Customer Journey Analytics](../release-notes/doc-changes.md)

+ Introduzione {#cja-overview}
   + [Panoramica di Customer Journey Analytics](../getting-started/cja-overview.md)
   + [Guida rapida](../getting-started/cja-getting-started.md)
   + [Pagina di destinazione](../getting-started/landing.md)
   + [Domande frequenti](../getting-started/cja-faq.md)
   + [Confronto tra Customer Journey Analytics e soluzioni BI](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics e Adobe Analytics {#compare-aa-cja}
   + [Evoluzione da Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Guida per utenti di Adobe Analytics](../getting-started/aa-to-cja-user.md)
   + Confronto con Adobe Analytics {#cja-aa-comparison}
      + [Panoramica](../getting-started/aa-vs-cja/overview.md)
      + [Utilizza i dati di Adobe Analytics nel Customer Journey Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Supporto delle funzioni di Customer Journey Analytics](../getting-started/aa-vs-cja/cja-aa.md)
      + [Confrontare la terminologia per i dati di Analytics trasmessi tramite il connettore di origine di Analytics](../getting-started/aa-vs-cja/terminology.md)
      + [Confrontare l’elaborazione dei dati in Adobe Analytics e Customer Journey Analytics](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Ambienti di reporting virtuali e ambienti sandbox](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Regole di elaborazione, VISTA e classificazioni rispetto alla preparazione dati](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID, ECID, AACUSTOMID e il connettore di origine di Analytics](../getting-started/aa-vs-cja/aaid-ecid-adc.md)

+ Inserimento dei dati {#cja-data-ingestion}
   + [Panoramica sull’inserimento di dati](../data-ingestion/data-ingestion.md)
   + Inserire e utilizzare le guide introduttive{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Adobe Experience Platform Edge Network {#edge-network}
         + [Web SDK](../data-ingestion/aepwebsdk.md)
         + [Mobile SDK](../data-ingestion/aepmobilesdk.md)
         + [API server](../data-ingestion/serverapi.md)
      + [Dati batch](../data-ingestion/batch.md)
      + [Dati in streaming](../data-ingestion/streaming.md)
      + [Connettori di origine](../data-ingestion/sources.md)

+ Connessioni {#cja-connections}
   + [Panoramica sulle connessioni](../connections/overview.md)
   + [Creare una connessione](../connections/create-connection.md)
   + [Gestire le connessioni](../connections/manage-connections.md)
   + [Set di dati evento combinati](../connections/combined-dataset.md)
   + [Ricerche standard](../connections/standard-lookups.md)
   + [Analisi cross-channel](../connections/cca.md)

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
      + [Bucketing dei valori](../data-views/component-settings/value-bucketing.md)
   + [Documentazione dei componenti standard](../data-views/component-reference.md)
   + [Connettore SQL](../data-views/sql-connector.md)
   + [Campi derivati](../data-views/derived-fields/derived-fields.md)
   + [Etichette e criteri](../data-views/data-governance.md)

+ Progetti Workspace {#cja-workspace}
   + [Panoramica di Analysis Workspace](../analysis-workspace/home.md)
   + [Eseguire analisi di base](../analysis-workspace/perform-basic-analysis.md)
   + [Eseguire analisi avanzate](../analysis-workspace/perform-adv-analysis.md)
   + Progetti {#build-workspace-project}
      + [Panoramica dei progetti](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Creare progetti](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Salvare progetti](../analysis-workspace/build-workspace-project/save-projects.md)
      + Cartelle in Workspace {#workspace-folders}
         + [Informazioni sulle cartelle in Workspace](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Creare cartelle e sottocartelle](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Eliminare le cartelle](../analysis-workspace/build-workspace-project/workspace-folders/delete-folders.md)
         + [Aggiungere progetti](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
         + [Rimuovere un progetto](../analysis-workspace/build-workspace-project/workspace-folders/remove-projects.md)
         + [Salvare un nuovo progetto](../analysis-workspace/build-workspace-project/workspace-folders/save-new-project-folder.md)
      + [Tasti di scelta rapida](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Palette di colori](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Densità di visualizzazione](../analysis-workspace/build-workspace-project/view-density.md)
   + Visualizzazioni {#visualizations}
      + [Panoramica delle visualizzazioni](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Gestione delle origini dati](../analysis-workspace/visualizations/t-sync-visualization.md)
      + Tabella a forma libera {#freeform-table}
         + [Tabella a forma libera](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + Impostazioni colonna e riga {#column-row-settings}
            + [Impostazioni colonna](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Impostazioni riga](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Elementi dinamici e statici](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtrare e ordinare tabelle](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Totali in Workspace](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Tabella coorte {#cohort-table}
         + [Cos’è un’analisi per coorte?](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configurare un rapporto di analisi per coorte](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Casi di utilizzo dell’analisi per coorte](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Abbandono {#fallout}
         + [Panoramica dell’abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configurare una visualizzazione dell’abbandono](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Abbandono interdimensionale](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Applicare i filtri nell’analisi dell’abbandono](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flusso {#flow}
         + [Panoramica del flusso](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Configurare una visualizzazione di flusso](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Flussi interdimensionali](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [Superfici e superfici sovrapposte](../analysis-workspace/visualizations/area.md)
      + [Barre e barre sovrapposte](../analysis-workspace/visualizations/bar.md)
      + [Grafico bullet](../analysis-workspace/visualizations/bullet-graph.md)
      + [Grafico combinato](../analysis-workspace/visualizations/combo-charts.md)
      + [Ad anello](../analysis-workspace/visualizations/donut.md)
      + [Istogramma](../analysis-workspace/visualizations/histogram.md)
      + [Barre orizzontali e Barre orizzontali sovrapposte](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Didascalie intelligenti](../analysis-workspace/visualizations/intelligent-captions.md)
      + [Riepilogo delle metriche chiave](../analysis-workspace/visualizations/key-metric.md)
      + [A linee](../analysis-workspace/visualizations/line.md)
      + [Grafico a dispersione](../analysis-workspace/visualizations/scatterplot.md)
      + [Numero di riepilogo e Variazione di riepilogo](../analysis-workspace/visualizations/summary-number-change.md)
      + [Testo](../analysis-workspace/visualizations/text.md)
      + [Mappa ad albero](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Pannelli {#panels}
      + [Panoramica dei pannelli](../analysis-workspace/c-panels/panels.md)
      + [Pannello Attribution](../analysis-workspace/c-panels/attribution.md)
      + [Pannello vuoto](../analysis-workspace/c-panels/blank-panel.md)
      + [Pannello Sperimentazione](../analysis-workspace/c-panels/experimentation.md)
      + [Pannello a forma libera](../analysis-workspace/c-panels/freeform-panel.md)
      + [Pannello Quick Insights](../analysis-workspace/c-panels/quickinsight.md)
      + [Pannello Visualizzatori simultanei di contenuti multimediali](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Pannello Tempo trascorso su contenuti multimediali](../analysis-workspace/c-panels/media-playback-time-spent.md)
   + Curare, condividere e pianificare i progetti {#curate-share}
      + [Menu Share](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Curare progetti](../analysis-workspace/curate-share/curate.md)
      + [Condividere progetti](../analysis-workspace/curate-share/share-projects.md)
      + [Creare collegamenti condivisibili](../analysis-workspace/curate-share/shareable-links.md)
      + [Progetti solo visualizzazione](../analysis-workspace/curate-share/view-only-projects.md)
   + Esportazione {#export}
      + [Panoramica sull’esportazione](../analysis-workspace/export/export-project-overview.md)
      + [Scarica](../analysis-workspace/export/download-send.md)
      + [Invia ad altri](../analysis-workspace/export/t-schedule-report.md)
      + [Esporta nel cloud](../analysis-workspace/export/export-cloud.md)
   + Virtual Analyst {#virtual-analyst}
      + [Panoramica di Virtual Analyst](../analysis-workspace/virtual-analyst/overview.md)
      + Rilevamento delle anomalie {#anomaly-detection}
         + [Panoramica di Rilevamento delle anomalie](../analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Visualizzare le anomalie in Analysis Workspace](../analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [Tecniche di statistica utilizzate nel rilevamento delle anomalie](../analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
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
   + [Preparare gli utenti manageriali a utilizzare le scorecard](../mobile-app/set-up-execs.md)
   + [Guida introduttiva per utenti direzionali](../mobile-app/executive.md)

+ Analisi guidata {#guided-analysis}
   + [Panoramica](../guided-analysis/overview.md)
   + Impatto {#impact}
      + [Vista versione](../guided-analysis/types/release.md)
      + [Vista primo utilizzo](../guided-analysis/types/first-use.md)
   + Funnel {#funnel}
      + [Vista frizione](../guided-analysis/types/friction.md)
      + [Visualizzazione tendenze di conversione](../guided-analysis/types/conversion-trends.md)
   + Crescita degli utenti {#user-growth}
      + [Visualizzazione attiva](../guided-analysis/types/active.md)
      + [Visualizzazione della crescita netta](../guided-analysis/types/net-growth.md)
   + Tendenze {#trends}
      + [Visualizzazione utilizzo](../guided-analysis/types/usage.md)
      + [Visualizzazione frequenza](../guided-analysis/types/frequency.md)
   + [Casi di utilizzo del settore](../guided-analysis/industry-use-cases.md)
   + [Domande frequenti](../guided-analysis/faq.md)

+ Componenti {#cja-components}
   + [Panoramica dei componenti](../components/overview.md)
   + [Aggiungere descrizioni dei componenti](../components/add-component-descriptions.md)
   + Annotazioni {#annotations}
      + [Panoramica sulle annotazioni](../components/annotations/overview.md)
      + [Creare annotazioni](../components/annotations/create-annotations.md)
      + [Gestire le annotazioni](../components/annotations/manage-annotations.md)
      + [Visualizzare le annotazioni](../components/annotations/view-annotations.md)
      + [Annotazioni per dispositivi mobili](../components/annotations/mobile-annotations.md)
   + [Progetto pianificato](../components/scheduled-projects-manager.md)
   + Tipi di pubblico {#audiences}
      + [Panoramica dei tipi di pubblico](../components/audiences/audiences-overview.md)
      + [Creare e pubblicare tipi di pubblico](../components/audiences/publish.md)
      + [Gestire i tipi di pubblico](../components/audiences/manage.md)
   + Dimensioni {#dimensions}
      + [Anteprima dimensioni](../components/dimensions/view-dimensions.md)
      + [Suddividere dimensioni](../components/dimensions/t-breakdown-fa.md)
      + [Suddividere le dimensioni in base al tempo](../components/dimensions/time-parting-dimensions.md)
      + [Dimensioni con cardinalità molto elevata](../components/dimensions/high-cardinality.md)
   + [Metriche](../components/apply-create-metrics.md)
   + Filtri {#cja-filters}
      + [Panoramica dei filtri](../components/filters/filters-overview.md)
      + [Creare filtri](../components/filters/create-filters.md)
      + [Condividere i filtri](../components/filters/filters-share.md)
      + [Assegnare tag ai filtri](../components/filters/filters-tag.md)
      + [Filtrare l’elenco dei filtri](../components/filters/filters-filter.md)
      + [Contrassegnare i filtri come preferiti](../components/filters/filters-favorite.md)
      + [Approvare i filtri](../components/filters/filters-approve.md)
      + [Copia filtri](../components/filters/filters-copy.md)
      + [Filtri rapidi](../components/filters/quick-filters.md)
      + [Generatore di filtri](../components/filters/filter-builder.md)
      + [Gestire i filtri](../components/filters/manage-filters.md)
      + [Operatori](../components/filters/operators.md)
   + Metriche calcolate {#cja-calcmetrics}
      + [Panoramica delle metriche calcolate](../components/calc-metrics/calc-metr-overview.md)
      + Flusso di lavoro per le metriche calcolate {#cm-workflow}
         + [Flusso di lavoro per le metriche calcolate](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Trovare metriche](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Creare metriche](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Tipo di metrica e attribuzione](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Creare una metrica “Partecipazione”](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Metriche filtrate](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Sovrapporre e sostituire filtri](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Metriche filtrate e ponderate](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Filtrare le metriche calcolate](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Contrassegnare le metriche calcolate come preferite](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [Copiare le metriche calcolate](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [Usare le funzioni](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Assegnare tag alle metriche calcolate](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Approvare le metriche calcolate](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Condividere le metriche calcolate](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Gestore metriche calcolate](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [Metriche calcolate predefinite](../components/calc-metrics/default-calcmetrics.md)
      + [Funzioni di base](../components/calc-metrics/cm-functions.md)
      + [Funzioni avanzate](../components/calc-metrics/cm-adv-functions.md)
   + Calendario e intervalli di date {#cja-date-ranges}
      + [Panoramica del calendario e degli intervalli di date](../components/date-ranges/calendar.md)
      + [Creare un intervallo di date](../components/date-ranges/create.md)
      + [Gestire gli intervalli di date](../components/date-ranges/manage.md)
      + [Creare intervalli di date personalizzati](../components/date-ranges/custom-date-ranges.md)
      + [Confronto delle date](../components/date-ranges/time-comparison.md)
   + Esportazioni {#exports}
      + [Configurare account di esportazione cloud](/help/components/exports/cloud-export-accounts.md)
      + [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md)
      + [Gestire i percorsi di esportazione cloud](/help/components/exports/manage-export-locations.md)
      + [Gestione esportazioni](/help/components/exports/manage-exports.md)
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

+ Stitching {#stitching}
   + [Panoramica](../stitching/overview.md)
   + [Come funziona l’unione](../stitching/explained.md)
   + [Creare e gestire set di dati uniti](../stitching/stitching-ui.md)
   + [Domande frequenti](../stitching/faq.md)

+ Analisi cross-channel {#cca}
   + [Panoramica dell’Analisi cross-channel](../cca/overview.md)
   + [Funzionamento delle riproduzioni](../cca/replay.md)
   + [Domande frequenti sull’Analisi cross-channel](../cca/faq.md)

+ Integrazioni Adobe {#integrations}
   + [Panoramica sull’integrazione delle soluzioni Adobe con il Customer Journey Analytics](/help/integrations/overview.md)
   + [Integrare Adobe Analytics con Customer Journey Analytics](/help/integrations/aa.md)
   + [Integrare i dati Journey Optimizer con Customer Journey Analytics](/help/integrations/ajo.md)
   + [Integrare i dati di Gestione delle decisioni con il Customer Journey Analytics](/help/integrations/ajo-od.md)
   + [Integrare IA per l’analisi dei clienti con Customer Journey Analytics](/help/integrations/customer-ai.md)

+ Governance dei dati {#cja-privacy}
   + [Governance dei dati](../privacy/privacy-overview.md)
   + [Registro di controllo](../privacy/audit-log.md)
   + [Chiavi gestite dal cliente](../privacy/cmk.md)

+ Casi d’uso {#cja-usecases}
   + [Casi d’uso di Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Dati di Google Analytics {#ga}
      + [Panoramica sulla migrazione dei dati da Google Analytics a Customer Journey Analytics](../use-cases/ga/overview.md)
      + [Acquisire dati storici Google Analytics in Platform](../use-cases/ga/backfill.md)
      + [Configurare i dati streaming di Google Analytics in Platform](../use-cases/ga/streaming.md)
      + [Rapporto sui dati Google Analytics in Customer Journey Analytics](../use-cases/ga/report.md)
   + Acquisizione dei dati {#data-ingestion}
      + [Acquisire dati di Marketo Engage in Adobe Experience Platform e generare report nel Customer Journey Analytics](../use-cases/data-ingestion/marketo.md)
      + [Inserire il pubblico Adobe Experience Platform nel Customer Journey Analytics](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Visualizzazioni dati {#data-views}
      + [Casi d’uso per le visualizzazioni dati](../use-cases/data-views/data-views-usecases.md)
      + [Utilizzare dimensioni e metriche di binding](../use-cases/data-views/binding-dimensions-metrics.md)
   + B2B {#b2b}
      + [Aggiungere dati a livello di account come set di dati di ricerca](../use-cases/b2b/b2b.md)
   + Dati cross-channel {#cross-channel}
      + [Analizzare i dati tra canali diversi](../use-cases/cross-channel/cross-channel.md)
      + [Importare dati Web e call center](../use-cases/cross-channel/call-center.md)
   + Dati Adobe Analytics {#aa-data}
      + [Utilizzare le dimensioni del canale di marketing](../use-cases/aa-data/marketing-channels.md)
      + [Combinare suite di rapporti con schemi diversi](../use-cases/aa-data/combine-report-suites.md)
   + Dati complessi {#complex-data}
      + [Utilizzare gli array di oggetti](../use-cases/object-arrays.md)

+ Amministrazione {#cja-admin}
   + [Controllo degli accessi](../admin/cja-access-control.md)
   + [Visualizzare e gestire l’utilizzo](../admin/estimate-usage.md)
   + [Implicazioni dell’eliminazione](../admin/cja-deletion.md)
   + [Ottimizzare le prestazioni del Customer Journey Analytics](../admin/optimizing-performance.md)
   + [Indirizzi IP](../admin/ip-addresses.md)

+ Labs {#labs}
   + [Guida utente di Labs](../labs/labs.md)

+ Risoluzione dei problemi {#troubleshooting}
   + [Confrontare i dati di Adobe Analytics con i dati del Customer Journey Analytics](../troubleshooting/compare.md)
   + [Coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-time CDP e Customer Journey Analytics](../troubleshooting/consistency-rcdp-cja.md)
   + [Mancanza di autorizzazioni](../troubleshooting/lack-of-permissions.md)

+ [Glossario di Customer Journey Analytics](../getting-started/cja-glossary.md)

+ [API CUSTOMER JOURNEY ANALYTICS](https://developer.adobe.com/cja-apis/docs/)
