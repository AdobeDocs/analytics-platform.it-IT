---
title: Confrontare l’elaborazione dei dati nelle funzioni di reporting di Adobe Analytics e Customer Journey Analytics
description: Comprendere le differenze nell’elaborazione dei dati delle varie funzioni di reporting
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: Basics
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 100%

---

# Confrontare l’elaborazione dei dati tra Adobe Analytics e Customer Journey Analytics

Spesso è necessario poter elaborare i dati prima che siano utili per il reporting. Puoi elaborarli in diverse fasi del percorso, dalla raccolta dei dati alla generazione del report o della visualizzazione.

In Adobe Analytics la maggior parte dell’elaborazione dei dati avviene immediatamente dopo la raccolta dei dati. Per supportare questa **elaborazione al momento della raccolta** sono disponibili funzionalità come regole VISTA, regole di elaborazione, regole di elaborazione dei canali di marketing.
I dati vengono quindi memorizzati e al momento del rapporto puoi applicare un’elaborazione aggiuntiva. Ad esempio, suddividi le dimensioni, applica la segmentazione o seleziona un modello di attribuzione diverso. Questa **elaborazione al momento del rapporto** avviene istantaneamente.

In Adobe Analytics, l’elaborazione al momento del rapporto rappresenta in genere una quantità di elaborazione inferiore rispetto a quella che avviene al momento della raccolta.

![Elaborazione al momento della raccolta di Adobe Analytics](../assets/aa-processing.png)

Al contrario, Customer Journey Analytics è progettato per richiedere un’elaborazione iniziale minima al momento della raccolta prima che i dati vengano organizzati e memorizzati. L’architettura di base di Customer Journey Analytics è progettata per utilizzare i dati memorizzati al momento dell’elaborazione del rapporto e offre la sua potente funzionalità, non solo in Workspace ma anche, cosa ancora più importante, tramite la definizione di [componenti](/help/data-views/component-settings/overview.md) e [campi derivati](/help/data-views/derived-fields/derived-fields.md) nelle visualizzazioni dati.

![Elaborazione al momento dell’elaborazione del rapporto di Customer Journey Analytics](../assets/cja-processing.png)

Comprendere le differenze nell’elaborazione dei dati delle varie funzioni di reporting è utile per capire quali metriche sono disponibili e dove e perché possono differire.

Ad esempio, poiché “visite” come metrica in Adobe Analytics viene definita al momento dell’elaborazione dei dati e “sessioni” come metrica in Customer Journey Analytics viene calcolata al momento dell’elaborazione del rapporto, le due metriche possono differire in base alle regole utilizzate per la definizione della sessione all’interno della visualizzazione dati di Customer Journey Analytics.

Inoltre, né visite né sessioni sono disponibili come metriche nei set di dati creati dal connettore di origine di Analytics e pertanto è necessario definire la sessione nella logica di query per poter eseguire dei confronti.

## Terminologia {#terms}

La tabella seguente definisce la terminologia dei diversi tipi di logica di elaborazione applicati ad Adobe Analytics e Customer Journey Analytics:

| Termine | Definizione | Note |
| --- | --- | --- |
| Elaborazione al momento della raccolta | Logica che viene eseguita quando i dati vengono elaborati, prima di essere memorizzati a scopo di reporting e analisi. | Questa logica viene incorporata nei dati storici e in genere non può essere modificata facilmente. |
| Elaborazione al momento dell’elaborazione del rapporto | Logica eseguita al momento dell’esecuzione di un rapporto. | Questa logica può essere applicata ai dati futuri e storici in fase di esecuzione del report in modo non distruttivo. |
| Logica a livello di hit | Logica applicata a livello di riga per riga. | Esempi: regole di elaborazione, VISTA, determinate regole dei canali di marketing. |
| Logica a livello di visita | Logica applicata a livello di visita. | Esempi: definizione di visita e sessione. |
| Logica a livello di visitatore | Logica applicata a livello di persona. | Esempio: unione di persone su dispositivi e canali diversi. |
| Logica di segmento (filtro) | Valutazione delle regole del segmento (filtro) evento/visita/persona (evento/sessione/persona). | Esempio: persone che hanno acquistato delle scarpe rosse. |
| Metriche calcolate | Valutazione delle metriche personalizzate create dai clienti che possono essere basate su formule complesse, inclusi segmenti e filtri. | Esempio: numero di persone che hanno acquistato delle scarpe rosse. |
| Logica di attribuzione | Logica per il calcolo dell’attribuzione. | Esempio: persistenza eVar. |
| Impostazioni del componente | Applicazione di personalizzazioni alle metriche o alle dimensioni quali attribuzione, comportamento, formato e altri | Esempio: creazione di bucket di valori per combinare valori numerici basati su un intervallo |
| Campi derivati | La logica si applica ai campi dello schema o a campi standard come parte della definizione dei componenti in una visualizzazione dati. | Esempio: creazione di una nuova dimensione del canale di marketing |

{style="table-layout:auto"}

Nel tempo, Adobe Analytics e ora Customer Journey Analytics hanno migliorato la flessibilità consentendo l’esecuzione della logica dei dati a livello di visita e di persona in fase di esecuzione dei rapporti.

## Tipi di elaborazione dei dati {#types}

I passaggi di elaborazione dei dati eseguiti per Adobe Analytics e Customer Journey Analytics e le loro tempistiche variano in base alla funzione di Analytics. La tabella seguente fornisce un riepilogo dei tipi di elaborazione dei dati di ciascuna funzione di Analytics e indica quando viene applicata l’elaborazione dei dati.

| Funzione | Applicata al momento dell’elaborazione | Applicata al momento del reporting | Non disponibile | Note |
| --- | --- | --- | --- | --- |
| Reporting di [Adobe Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=it) <br/>(escluse le le suite di rapporti virtuali o Attribution IQ con elaborazione al momento del rapporto) | <ul><li>[Regole di elaborazione](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=it)</li><li>[Regole VISTA](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=it)</li><li>[Regole dei canali di marketing](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=it) a livello di hit</li><li>Regole dei canali di marketing a livello di visita (vedi nota)</li><li>Definizione di visita</li><li>Logica di attribuzione</li></ul> | <ul><li>Logica di segmento</li><li>Metriche calcolate</li></ul> | <ul><li>Analytics tra dispositivi (vedi nota)</li></ul> | <ul><li>CDA richiede l’utilizzo di suite di rapporti virtuali con elaborazione al momento del reporting.</li><li>Le “regole dei canali di marketing a livello di visita” includono: **Is First Page of Visit** (È la prima pagina della visita), **Override Last-Touch Channel** (Sovrascrivi canale di ultimo contatto) e **Marketing Channel Expiration** (Scadenza canale di marketing). Consulta la [documentazione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=it).</li></ul> |
| [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=it) di Adobe Analytics | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Regole dei canali di marketing a livello di hit</li><li>Regole dei canali di marketing a livello di visita</li><li>Definizione di visita</li><li>Logica di attribuzione</li></ul> | <ul><li>Logica di segmento</li></ul> | <ul><li>Metriche calcolate</li><li>Cross-Device Analytics</li></ul> |     |
| [Feed di dati](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=it) di Adobe Analytics | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Regole dei canali di marketing a livello di hit</li><li>Regole dei canali di marketing a livello di visita</li><li>Definizione di visita (campo visitnum)</li><li>Logica di attribuzione (nelle colonne successive)</li></ul> |   | <ul><li>Logica di segmento</li><li>Metriche calcolate</li><li>Cross-Device Analytics</li></ul> | <ul><li>Le mappature ID di alcune colonne relative ai canali di marketing nei feed dati non sono incluse nei feed dati. Consulta la [documentazione sui feed dati](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=it).</li></ul> |
| [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) di Adobe Analytics | <ul><li> Regole di elaborazione</li><li>Regole VISTA</li><ul> |   | <ul><li>Regole dei canali di marketing a livello di hit</li><li>Regole dei canali di marketing a livello di visita</li><li>Logica di visita</li><li>Logica di attribuzione</li><li>Logica di segmento</li><li>Metriche calcolate</li><li>Cross-Device Analytics</li></ul> |  |
| [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=it) di Adobe Analytics | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Definizione di visita (vedi nota)</li><li>Analytics tra dispositivi (vedi nota)</li></ul> | <ul><li>Regole dei canali di marketing a livello di hit (vedi nota)</li><li>Regole dei canali di marketing a livello di visita (vedi nota) Logica di attribuzione</li><li>Logica di segmento</li><li>Metriche calcolate</li></ul> |  | <ul><li>CDA richiede l’utilizzo di suite di rapporti virtuali con elaborazione al momento del reporting.</li><li>Attribution IQ in Analytics core utilizza canali di marketing derivati completamente al momento del reporting (ovvero valori medi derivati).</li><li>Attribution IQ utilizza una definizione di visita al momento dell’elaborazione, tranne quando è utilizzato in una suite di rapporti virtuali con elaborazione al momento dell’elaborazione del rapporto.</li></ul> |
| Suite di rapporti virtuali di Adobe Analytics con [elaborazione al momento del rapporto](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=it) | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>[Analytics tra dispositivi](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=it)</li></ul> | <ul><li>Definizione di visita</li><li>Logica di attribuzione</li><li>Logica di segmento</li><li>Metriche calcolate</li><li>Altre impostazioni di elaborazione al momento del rapporto delle suite di rapporti virtuali</li></ul> | <ul><li>Regole dei canali di marketing a livello di hit</li><li>Regole dei canali di marketing a livello di visita</li></ul> | <ul><li>Consulta la [documentazione](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=it) sull’elaborazione al momento del rapporto della suite di rapporti virtuali.</li></ul> |
| Set di dati basato sul [connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it) nel data lake di Adobe Experience Platform | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Regole dei canali di marketing a livello di hit</li><li>Unione basata sui campi (vedi nota)</li></ul> |   | <ul><li>[Regole dei canali di marketing a livello di visita](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=it)</li><li>Logica di visita</li><li>Logica di attribuzione</li><li>Logica di filtro</li></ul> | <ul><li>È necessario applicare la propria logica di filtro e le metriche calcolate</li><li>L’unione basata sui campi crea un set di dati unito e separato, in aggiunta a quello creato dal connettore di origine di Analytics.</li></ul> |
| Reporting di [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=it) | <ul><li>Implementato come parte della raccolta dati di Adobe Experience Platform</li></ul> | <ul><li>Definizione di sessione</li><li>Impostazioni della [visualizzazione dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=it)<li>Logica di attribuzione</li><li>Metriche calcolate</li><li>Logica di filtro</li></ul> | <ul><li>Regole dei canali di marketing a livello di visita</li></ul> | <ul><li>Per sfruttare le analisi cross-channel, è necessario utilizzare set di dati uniti.</li></ul> |

{style="table-layout:auto"}
