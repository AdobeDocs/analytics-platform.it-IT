---
git-repo: https://github.com/AdobeDocs/analytics-platform.it-IT
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Guida di Customer Journey Analytics
user-guide-description: Scopri Customer Journey Analytics (CJA) e come utilizzare Analysis Workspace con i dati di Experience Platform.
breadcrumb-title: Guida di Customer Journey Analytics
source-git-commit: 43c8af6f9010354258a702fb702a330873d9cb8e
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 96%

---


# Guida di Customer Journey Analytics {#using}

+ [Guida di Customer Journey Analytics](../getting-started/cja-landing.md)
+ Note sulla versione {#releases}
   + [Versione più recente](../release-notes/latest.md)
   + [Versioni del 2022](../release-notes/2022.md)
   + [Versioni del 2021](../release-notes/2021.md)
   + [Versioni del 2020](../release-notes/2020.md)
   + [Versioni di CJA](../release-notes/releases.md)
   + [Aggiornamenti della documentazione di CJA](../release-notes/doc-changes.md)
+ Panoramica di Customer Journey Analytics {#cja-overview}
   + [Panoramica di Customer Journey Analytics](../getting-started/cja-overview.md)
   + [Introduzione](../getting-started/cja-getting-started.md)
   + [Coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-Time CDP e CJA](../getting-started/consistency-rcdp-cja.md)
   + [Controllo degli accessi a CJA](../getting-started/cja-access-control.md)
   + [Pagina di destinazione di Customer Journey Analytics](../getting-started/landing.md)
   + [Evoluzione da Adobe Analytics a Customer Journey Analytics](../getting-started/aa-to-cja.md)
   + [Guida per i nuovi utenti di Customer Journey Analytics](../getting-started/aa-to-cja-user.md)
   + [Visualizzare e gestire l’utilizzo di CJA](../getting-started/estimate-usage.md)
   + [Domande frequenti](../getting-started/cja-faq.md)
   + Confrontare Adobe Analytics e Customer Journey Analytics {#compare-aa-cja}
      + [Utilizza i dati di Adobe Analytics nel Customer Journey Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Supporto delle funzioni di Customer Journey Analytics](../getting-started/aa-vs-cja/cja-aa.md)
      + [Confronto della terminologia per i dati di Analytics trasmessi tramite il connettore di origine di Analytics](../getting-started/aa-vs-cja/terminology.md)
      + [Confrontare l’elaborazione dei dati in Adobe Analytics e CJA](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Ambienti di reporting virtuali e ambienti sandbox](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Regole di elaborazione, VISTA e classificazioni rispetto alla preparazione dati](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID, ECID, AACUSTOMID e il connettore di origine di Analytics](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Implicazioni dell’eliminazione](../getting-started/cja-deletion.md)
   + [Glossario di CJA](../getting-started/cja-glossary.md)
+ Acquisizione dei dati {#cja-data-ingestion}
   + [Panoramica sull’acquisizione dei dati](../data-ingestion/data-ingestion.md)
   + Inserire e utilizzare le guide rapide{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + [Adobe Experience Platform Web SDK e Edge Network](../data-ingestion/aepwebsdk.md)
      + [Dati batch](../data-ingestion/batch.md)
      + [Dati in streaming](../data-ingestion/streaming.md)
      + [Connettori sorgente](../data-ingestion/sources.md)
+ Connessioni {#cja-connections}
   + [Panoramica sulle connessioni](../connections/overview.md)
   + [Creare una connessione](../connections/create-connection.md)
   + [Gestire le connessioni](../connections/manage-connections.md)
   + [Set di dati evento combinati](../connections/combined-dataset.md)
   + [Ricerche standard](../connections/standard-lookups.md)
   + [Cross-Channel Analytics](../connections/cca.md)
+ Visualizzazioni dati {#cja-dataviews}
   + [Panoramica delle visualizzazioni dati](../data-views/data-views.md)
   + [Creare o modificare una visualizzazione di dati](../data-views/create-dataview.md)
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
   + [Etichette e criteri](../data-views/data-governance.md)
+ Progetti Workspace {#cja-workspace}
   + [Panoramica di Analysis Workspace](../analysis-workspace/home.md)
   + [Eseguire analisi di base](../analysis-workspace/perform-basic-analysis.md)
   + [Eseguire analisi avanzate](../analysis-workspace/perform-adv-analysis.md)
   + Progetti {#build-workspace-project}
      + [Panoramica dei progetti](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Salvare i progetti](../analysis-workspace/build-workspace-project/save-projects.md)
      + Cartelle in Workspace {#workspace-folders}
         + [Informazioni sulle cartelle in Workspace](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Creare cartelle e sottocartelle](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Elimina cartelle](../analysis-workspace/build-workspace-project/workspace-folders/delete-folders.md)
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
         + [Paginazione, filtri e ordinamento di tabelle](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
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
      + Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) {#media-playback-timespent}
         + [Panoramica](../analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [Impostazioni di ingresso e uscita](../analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [Domande frequenti](../analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + Curare, condividere e pianificare i progetti {#curate-share}
      + [Menu Share](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Curare progetti](../analysis-workspace/curate-share/curate.md)
      + [Condividere progetti](../analysis-workspace/curate-share/share-projects.md)
      + [Creare collegamenti condivisibili](../analysis-workspace/curate-share/shareable-links.md)
      + [Progetti solo visualizzazione](../analysis-workspace/curate-share/view-only-projects.md)
      + [Scaricare file PDF o CSV](../analysis-workspace/curate-share/download-send.md)
      + [Programmare progetti](../analysis-workspace/curate-share/t-schedule-report.md)
   + Attribution IQ {#attribution}
      + [Panoramica di Attribution](../analysis-workspace/attribution/overview.md)
      + [Modelli di attribuzione e intervalli di lookback](../analysis-workspace/attribution/models.md)
      + [Attribuzione algoritmica](../analysis-workspace/attribution/algorithmic.md)
      + [Best practice di attribuzione](../analysis-workspace/attribution/best-practices.md)
      + [Domande frequenti](../analysis-workspace/attribution/faq.md)
   + Virtual Analyst {#virtual-analyst}
      + [Panoramica di Virtual Analyst](../analysis-workspace/virtual-analyst/overview.md)
      + Rilevamento delle anomalie {#anomaly-detection}
         + [Panoramica di Rilevamento delle anomalie](../analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Visualizzare le anomalie in Analysis Workspace](../analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [Tecniche di statistica utilizzate nel rilevamento delle anomalie](../analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [Preferenze utente](../analysis-workspace/user-preferences.md)
   + Domande frequenti su Workspace {#workspace-faq}
      + [Domande frequenti](../analysis-workspace/workspace-faq/faq.md)
      + [Ottimizzare le prestazioni di Analysis Workspace](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Messaggi di errore](../analysis-workspace/workspace-faq/error-messages.md)
      + [Limiti di Analysis Workspace](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Requisiti di amministrazione](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Accessibilità di Analysis Workspace](../analysis-workspace/workspace-faq/aw-accessibility.md)
      + [“Long tail” in Analysis Workspace](../analysis-workspace/workspace-faq/long-tail.md)
+ Componenti {#cja-components}
   + [Panoramica dei componenti](../components/overview.md)
   + Annotazioni {#annotations}
      + [Panoramica sulle annotazioni](../components/annotations/overview.md)
      + [Creare annotazioni](../components/annotations/create-annotations.md)
      + [Gestire le annotazioni](../components/annotations/manage-annotations.md)
      + [Visualizzare le annotazioni](../components/annotations/view-annotations.md)
      + [Annotazioni per dispositivi mobili](../components/annotations/mobile-annotations.md)
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
      + [Creare un filtro](../components/filters/create-filters.md)
      + [Gestire i filtri](../components/filters/manage-filters.md)
      + [Filtri rapidi](../components/filters/quick-filters.md)
      + [Filtri ad hoc](../components/filters/ad-hoc-filters.md)
      + [Operatori](../components/filters/operators.md)
   + Metriche calcolate {#cja-calcmetrics}
      + [Panoramica delle metriche calcolate](../components/calc-metrics/calc-metr-overview.md)
      + Flusso di lavoro per le metriche calcolate {#cm-workflow}
         + [Flusso di lavoro per le metriche calcolate](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Trovare metriche](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Creare metriche](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Tipo di metrica e attribuzione](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Creare una semplice metrica “Visualizzazioni pagina in base alle visite”](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Metriche filtrate](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Sovrapponi e sostituisci segmenti](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Metriche filtrate e ponderate](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Usare le funzioni](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Metrica di partecipazione](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Assegnare tag alle metriche calcolate](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Approvare le metriche calcolate](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Condividere le metriche calcolate](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Gestore metriche calcolate](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [Funzioni di base](../components/calc-metrics/cm-functions.md)
      + [Funzioni avanzate](../components/calc-metrics/cm-adv-functions.md)
   + Intervalli di date {#cja-date-ranges}
      + [Panoramica degli intervalli di date](../components/date-ranges/overview.md)
      + [Creare un intervallo di date](../components/date-ranges/create.md)
      + [Gestire gli intervalli di date](../components/date-ranges/manage.md)
      + [Panoramica del calendario](../components/date-ranges/calendar.md)
      + [Creare intervalli di date personalizzati](../components/date-ranges/custom-date-ranges.md)
      + [Confronto delle date](../components/date-ranges/time-comparison.md)
+ Dashboard di Analytics {#cja-dashboards}
   + [Panoramica dei dashboard di Analytics](../mobile-app/home.md)
   + [Attività del curatore](../mobile-app/curator.md)
   + [Creare una scorecard per dispositivi mobili](../mobile-app/create-scorecard.md)
   + [Preparare gli utenti manageriali a utilizzare le scorecard](../mobile-app/set-up-execs.md)
   + [Guida introduttiva per utenti direzionali](../mobile-app/executive.md)
+ Report Builder {#cja-reportbuilder}
   + [Panoramica del Report Builder](../report-builder/report-buider-overview.md)
   + [Configurazione Report Builder](../report-builder/report-builder-setup.md)
   + [Creare un blocco di dati](../report-builder/create-a-data-block.md)
   + [Hub Report Builder](../report-builder/report-builder-hub.md)
   + [Selezionare un intervallo di date](../report-builder/select-date-range.md)
   + [Utilizzare i filtri](../report-builder/work-with-filters.md)
   + [Dimensioni filtro](../report-builder/filter-dimensions.md)
   + [Gestire i blocchi di dati](../report-builder/manage-reportbuilder.md)
   + [Pianificare cartelle di lavoro](../report-builder/schedule-reportbuilder.md)
   + [Etichette per limitazioni](../report-builder/restricted-labels.md)
   + [Impostazioni Report Builder](../report-builder/report-builder-settings.md)
+ Cross-Channel Analytics {#cca}
   + [Panoramica di Cross-Channel Analytics](../cca/overview.md)
   + [Funzionamento delle riproduzioni](../cca/replay.md)
   + [Domande frequenti su Cross-Channel Analytics](../cca/faq.md)
+ Integrazioni Adobe {#integrations}
   + [Panoramica sull’integrazione delle soluzioni Adobe con CJA](/help/integrations/overview.md)
   + [Integrare Adobe Analytics con Customer Journey Analytics](/help/integrations/aa.md)
   + [Integrare i dati Journey Optimizer con CJA](/help/integrations/ajo.md)
   + [Integrare la funzione IA per l’analisi dei clienti con CJA](/help/integrations/customer-ai.md)
+ Governance dei dati {#cja-privacy}
   + [Governance dei dati](../privacy/privacy-overview.md)
   + [Registro di controllo](../privacy/audit-log.md)
   + [Chiavi gestite dal cliente](../privacy/cmk.md)
+ Casi d’uso {#cja-usecases}
   + [Casi d’uso di Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Dati di Google Analytics {#ga}
      + [Panoramica sulla migrazione dei dati da Google Analytics a CJA](../use-cases/ga/overview.md)
      + [Acquisire dati storici Google Analytics in Platform](../use-cases/ga/backfill.md)
      + [Configurare i dati streaming di Google Analytics in Platform](../use-cases/ga/streaming.md)
      + [Generare rapporti sui dati Google Analytics in CJA](../use-cases/ga/report.md)
   + Acquisizione dei dati {#data-ingestion}
      + [Acquisire i dati Marketo Engage in AEP e generare rapporti in CJA](../use-cases/data-ingestion/marketo.md)
      + [Acquisire i tipi di pubblico di AEP in CJA](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Visualizzazioni dati {#data-views}
      + [Casi d’uso per le visualizzazioni dati](../use-cases/data-views/data-views-usecases.md)
      + [Utilizzare dimensioni e metriche di binding](../use-cases/data-views/binding-dimensions-metrics.md)
   + B2B {#b2b}
   + [Aggiungere dati a livello di account come set di dati di ricerca](../use-cases/b2b/b2b.md)
   + Dati cross-channel {#cross-channel}
      + [Analizzare i dati tra canali diversi](../use-cases/cross-channel/cross-channel.md)
      + [Importare dati web e call center](../use-cases/cross-channel/call-center.md)
   + Dati Adobe Analytics {#aa-data}
      + [Utilizzare le dimensioni del canale di marketing](../use-cases/aa-data/marketing-channels.md)
      + [Combinare suite di rapporti con schemi diversi](../use-cases/aa-data/combine-report-suites.md)
   + [Utilizzare gli array di oggetti](../use-cases/object-arrays.md)
+ Labs {#labs}
   + [Guida utente di Labs](../labs/labs.md)
+ Risoluzione dei problemi {#troubleshooting}
   + [Confrontare i dati di Adobe Analytics con i dati CJA](../troubleshooting/compare.md)
+ [API di CJA](https://developer.adobe.com/cja-apis/docs/)
