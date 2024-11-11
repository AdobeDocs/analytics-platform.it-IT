---
title: Guida di Customer Journey Analytics
description: Pagina di destinazione di Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: ce04e69d2c933f893eeeff04abb0f56fb4000e6f
workflow-type: ht
source-wordcount: '820'
ht-degree: 100%

---

# Guida di Customer Journey Analytics

Questa guida alla documentazione tecnica fornisce supporto autonomo per Customer Journey Analytics. Customer Journey Analytics consente di importare in Adobe Experience Platform i dati del cliente da qualsiasi canale (online e offline). Puoi quindi analizzarli così come faresti con i dati digitali esistenti utilizzando Analysis Workspace.

Con Customer Journey Analytics puoi definire come collegare i dati online e offline in Analysis Workspace su qualsiasi ID cliente comune per poter poi eseguire attività di attribuzione, filtri, flusso, abbandono, e così via, tra i dati cliente.

## Novità

Dai un’occhiata ai miglioramenti più recenti apportati al prodotto e alla documentazione di Customer Journey Analytics. Per un elenco completo delle funzioni, dei miglioramenti e delle correzioni, consulta le [Note sulla versione](../release-notes/latest.md) dettagliate. Visita la [pagina di aggiornamenti della documentazione](../release-notes/doc-changes.md) per conoscere le ultime modifiche.

>[!BEGINTABS]

>[!TAB Assistente IA]

L’Assistente IA è un’esperienza conversazionale che consente ai professionisti di eseguire rapidamente attività, sia che si tratti di comprensione dei concetti, che di risoluzione dei problemi o di effettuare ricerche all’interno delle informazioni. Consente inoltre agli utenti non esperti di svolgere le attività degli esperti e migliora la qualità complessiva del lavoro.

[![immagine](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Analisi guidata]

L’analisi guidata è ora disponibile direttamente da Analysis Workspace, consentendo agli utenti di creare dashboard con informazioni complete provenienti da pannelli, visualizzazioni e analisi guidate.

[![immagine](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)

>[!TAB Avvisi]

Gli avvisi ti consentono di ricevere notifiche in base a percentuali di modifica o a punti dati specifici. Puoi visualizzare in anteprima la frequenza di attivazione di un avviso, inviare avvisi tramite e-mail o SMS, creare avvisi sovrapposti e altro ancora.

[![immagine](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)

>[!TAB Dati di riepilogo]

Consente di inserire dati di serie temporali privi di un ID persona. Questi dati di serie temporali possono essere utilizzati per supportare vari casi d’uso, ad esempio:

- Presentare indicatori di prestazioni di alto livello come parte o insieme ai dati a livello di evento.
- Caricamento di target o obiettivi su base oraria o giornaliera, quindi posizionamento di questi target o obiettivi rispetto alle metriche a livello di evento.

[![immagine](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

>[!TAB Unione basata su grafici*]

Tramite l’unione basata sui grafici, puoi utilizzare il grafico Identità dell&#39;Identity Service per ottenere una visualizzazione migliore del percorso cliente grazie a: <ul><li>L’unione di set di dati con identificatori diversi senza dover estrarre, trasformare e caricare dati aggiuntivi per riflettere un singolo identificatore.</li> <li>Miglioramento della copertura dell’identità preferita o d’oro per un singolo set di dati mediante la condivisione di identità tra set di dati diversi,</li><li>Allineamento dei profili creati in Adobe Real-time CDP e AJO alle persone presenti in Customer Journey Analytics.</li></ul>

[![immagine](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_Per l’unione basata su grafici, è necessario disporre del pacchetto Prime._*

>[!TAB Ricerche B2B]

Come parte della configurazione di una connessione, è possibile trasformare i set di dati per schemi di ricerca B2B specifici, per supportare meglio le ricerche basate su persone sui dati B2B.

[![immagine](assets/learn-more-button.svg)](/help/connections/transform-datasets-b2b-lookups.md)

>[!TAB Campi derivati]

Sono ora disponibili nuove funzioni per i campi derivati (Matematica, Successivo o Precedente, Riepilogo, Deduplica) e per i modelli di funzione aggiuntivi (come Mancati recapiti, Nome descrittivo set di dati, Vacanze, Obiettivi mensili, Rilevamento dei bot semplice e altri).

[![immagine](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB Estensione BI*]

L’estensione BI consente a SQL di accedere alle visualizzazioni dati definite in Customer Journey Analytics. Ora puoi utilizzare il tuo strumento BI preferito per creare rapporti e dashboard basati sulle stesse visualizzazioni dati utilizzate dagli utenti di Customer Journey Analytics con i loro progetti Analysis Workspace.

[![immagine](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

*_Per utilizzare l’estensione BI, devi disporre del pacchetto Select o versione successiva._*


>[!ENDTABS]

## Inizia con le nozioni di base

Inizia consultando il materiale incluso nei collegamenti riportati di seguito per acquisire familiarità con le caratteristiche e le funzionalità di Customer Journey Analytics.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>Oltre i dati online</strong><br/> Scopri il confronto tra Customer Journey Analytics e Adobe Analytics, quali funzioni condividono e come utilizzare i dati di Analytics.</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>Acquisire e utilizzare i dati</strong><br/>Scopri le opzioni disponibili per acquisire i dati in Experience Platform e utilizzarli per l’analisi e il reporting in Customer Journey Analytics.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>Analisi guidata</strong><br/> Scopri come utilizzare i flussi di lavoro per ottenere dati e approfondimenti sull’esperienza cliente con i prodotti. Product Analytics tramite analisi guidata…
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/> Utilizza Analysis Workspace per eseguire analisi di base e avanzate, come diagrammi di attribuzione, di flusso e di fallout e analisi dettagliate delle dimensioni.</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/guided-analysis/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/analysis-workspace/home.md"><img src="./assets/learn-more-button.svg"></a></td>
    </tr>
</table>


## Esplora la documentazione

Confronto tra Customer Journey Analytics e Adobe Analytics. Come inserire i dati nella soluzione e quindi preparare, visualizzare, analizzare e democratizzare tali dati e le analisi e i rapporti risultanti.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>Confronto con Adobe Analytics</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Panoramica</a> - <a href="/help/getting-started/aa-to-cja.md">Evoluzione</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Utilizzo dei dati di Adobe Analytics</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Funzionalità supportate</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminologia</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Elaborazione dati</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>Connessioni</strong><br/><a href="/help/connections/overview.md">Panoramica</a> - <a href="/help/connections/create-connection.md">Crea</a> - <a href="/help/connections/manage-connections.md">Gestisci</a> - <a href="/help/stitching/overview.md">Unisci</a> - <a href="/help/connections/combined-dataset.md">Set di dati evento combinati</a> - <a href="/help/connections/standard-lookups.md">Ricerche standard</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/> <strong>Visualizzazioni dati</strong><br/><a href="/help/data-views/data-views.md">Panoramica</a> - <a href="/help/data-views/create-dataview.md">Crea o modifica</a> - <a href="/help/data-views/session-settings.md">Impostazioni sessione</a> - <a href="/help/data-views/derived-fields/derived-fields.md">Campi derivati</a> - <a href="/help/data-views/summary-data.md">Dati riepilogo</a> - <a href="/help/data-views/component-reference.md">Riferimento componente</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Progetti Workspace</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">Analisi di base </a> e <a href="/help/analysis-workspace/perform-adv-analysis.md">avanzata</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">Progetti</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualizzazioni</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">Pannelli</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>Analisi guidata</strong><br/><a href="/help/guided-analysis/overview.md">Panoramica</a> - <a href="/help/guided-analysis/types/active-growth.md">Crescita utenti</a> - <a href="/help/guided-analysis/types/trends.md">Tendenze</a> - <a href="/help/guided-analysis/types/funnel.md">Funnel</a> - <a href="/help/guided-analysis/types/release-impact.md">Impatto</a> - <a href="/help/guided-analysis/industry-use-cases.md">Casi d’uso del settore</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/> <strong>Condivisione, esportazione, integrazione</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Progetti</a> - <a href="/help/mobile-app/home.md">Dashboard di Analytics</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a> - <a href="/help/components/exports/manage-exports.md">Esportazione cloud</a> - <a href="/help/integrations/overview.md">Integrazioni</a>
    </td>
  </tr>
</table>

## Risorse aggiuntive

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/><a href="https://experienceleague.adobe.com/it/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Tutorial</a> - <a href="https://helpx.adobe.com/it/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Descrizione del prodotto Customer Journey Analytics</a> - <a href="https://helpx.adobe.com/it/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Descrizione del prodotto Adobe Analytics (componente aggiuntivo per Customer Journey Analytics)</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">API di Customer Journey Analytics</a> - <a href="/help/ai-assistant.md">Assistente IA</a>
</td>
<td><strong>Acquisizione dei dati</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Panoramica</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">Batch</a> - <a href="/help/data-ingestion/streaming.md">Streaming</a> - <a href="/help/data-ingestion/sources.md">Origini</a> - <a href="/help/data-ingestion/serverapi.md">API server</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Rimani aggiornato, contribuisci alla community e migliora la tua esperienza di Customer Journey Analytics.</b><br>Visita la community di Adobe Analytics per discutere delle funzionalità con altri professionisti. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">Iscriviti alla community oggi stesso!</a></td></tr></tbody></table>
