---
title: Confrontare l’elaborazione dei dati tra le funzioni di reporting di Adobe Analytics e CJA
description: Comprendere le differenze nell’elaborazione dei dati per le varie funzioni di reporting
source-git-commit: bdb2f09c5c0778640c505557adf8ac82037f9b90
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 20%

---


# Confrontare l’elaborazione dei dati tra le funzioni di reporting di Adobe Analytics e CJA

È utile comprendere le differenze nell’elaborazione dei dati per le varie funzioni di reporting per capire quali metriche sono disponibili dove e perché possono differire.

Ad esempio, poiché &quot;visite&quot; come metrica in Adobe Analytics viene definita al momento dell’elaborazione dei dati e &quot;sessioni&quot; come metrica in CJA viene calcolata al momento del rapporto, le due metriche possono differire in base alle regole utilizzate per la definizione della sessione all’interno della visualizzazione dati CJA.

Inoltre, non sono disponibili visite o sessioni come metrica nei set di dati creati dal connettore origine di Analytics e pertanto è necessario definire la sessione nella logica di query per eseguire confronti.

## Terminologia {#terms}

La tabella seguente definisce la terminologia per i diversi tipi di logica di elaborazione applicati ad Adobe Analytics e CJA:

| Termine | Definizione | Note |
| --- | --- | --- |
| Logica del tempo di elaborazione | Logica che viene eseguita quando i dati vengono elaborati, prima di essere memorizzati a scopo di reporting e analisi. | Questa logica viene inserita nei dati storici e generalmente non può essere facilmente modificata. |
| Logica temporale del rapporto | Logica eseguita al momento dell’esecuzione di un rapporto. | Questa logica può essere applicata ai dati futuri e storici in fase di runtime di report in modo non distruttivo. |
| Logica a livello di hit | Logica applicata a livello di riga. | Esempi: Regole di elaborazione, VISTA, determinate regole del canale di marketing. |
| Logica a livello di visita | Logica applicata a livello di visita. | Esempi: Visita e definizione della sessione. |
| Logica a livello di visitatore | Logica applicata a livello di visitatore. | Esempio: Stitching di visitatori tra dispositivi e canali. |
| Logica del segmento (filtro) | Valutazione delle regole del segmento hit/visita/visitatore (evento/sessione/persona) (filtro). | Esempio: Persone che hanno comprato delle scarpe rosse. |
| Metriche calcolate  | Valutazione delle metriche personalizzate create dal cliente che possono essere basate su formule complesse, inclusi segmenti e filtri. | Esempio: Numero di persone che hanno comprato scarpe rosse. |
| Logica di attribuzione | Logica per calcolare l’attribuzione. | Esempio: Persistenza eVar. |

{style=&quot;table-layout:auto&quot;}

Nel tempo, Adobe Analytics e ora il Customer Journey Analytics hanno migliorato la loro flessibilità consentendo l’esecuzione della logica dei dati a livello di visita e visitatore in fase di esecuzione dei rapporti.

## Tipi di trattamento dei dati {#types}

I passaggi di elaborazione dei dati che vengono eseguiti per Adobe Analytics e CJA e la tempistica di tali passaggi variano dalla funzione di Analytics alla funzione di Analytics. La tabella seguente fornisce un riepilogo dei tipi di elaborazione dati per ciascuna funzione di Analytics e quando viene applicata l’elaborazione dati.

| Funzione di Analytics | Applicato al momento dell&#39;elaborazione | Applicato al momento del rapporto | Non disponibile | Note |
| --- | --- | --- | --- | --- |
| [Core AA](https://experienceleague.adobe.com/docs/analytics.html?lang=it) reporting<br/>(escluse le suite di rapporti virtuali o di Attribution IQ con elaborazione al momento del rapporto) | <ul><li>[Regole di elaborazione](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=it)</li><li>[Regole VISTA](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>Livello di hit [regole del canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=it)</li><li>Regole per i canali di marketing a livello di visita (vedi nota)</li><li>Definizione della visita</li><li>Logica di attribuzione</li></ul> | <ul><li>Logica del segmento</li><li>Metriche calcolate </li></ul> | <ul><li>Analisi multidispositivo (vedi nota)</li></ul> | <ul><li>CDA richiede l’utilizzo di suite di rapporti virtuali con elaborazione dei tempi di report.</li><li>Le &quot;regole dei canali di marketing a livello di visita&quot; includono: **È la prima pagina della visita**, **Ignora canale ultimo contatto** e **Scadenza canale di marketing**. (Vedi [documentazione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=it).)</li></ul> |
| Core AA [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=en) | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Regole per i canali di marketing a livello di hit</li><li>Regole per i canali di marketing a livello di visita</li><li>Definizione della visita</li><li>Logica di attribuzione</li></ul> | <ul><li>Logica del segmento</li></ul> | <ul><li>Metriche calcolate </li><li>Analytics tra dispositivi</li></ul> |  |
| Core AA [Feed dati](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Regole per i canali di marketing a livello di hit</li><li>Regole per i canali di marketing a livello di visita</li><li>Definizione della visita (campo visitnum)</li><li>Logica di attribuzione (nelle colonne di post)</li></ul> |  | <ul><li>Logica del segmento</li><li>Metriche calcolate </li><li>Analytics tra dispositivi</li></ul> | <ul><li>Le mappature ID per alcune colonne relative al canale di marketing nei feed di dati non sono incluse nei feed di dati. (Vedi [documentazione sui feed di dati](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=it).)</li></ul> |
| Core AA [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> Regole di elaborazione</li><li>Regole VISTA</li><ul> |  | <ul><li>Regole per i canali di marketing a livello di hit</li><li>Regole per i canali di marketing a livello di visita</li><li>Logica delle visite</li><li>Logica di attribuzione</li><li>Logica del segmento</li><li>Metriche calcolate </li><li>Analytics tra dispositivi</li></ul> |  |
| Core AA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=it) | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Definizione della visita (vedi nota)</li><li>Analisi multidispositivo (vedi nota)</li></ul> | <ul><li>Regole per i canali di marketing a livello di hit (vedi nota)</li><li>Regole per i canali di marketing a livello di visita (consulta nota)Logica di attribuzione</li><li>Logica del segmento</li><li>Metriche calcolate </li></ul> |  | <ul><li>CDA richiede l’utilizzo di suite di rapporti virtuali con elaborazione dei tempi di report.</li><li>Attribution IQ in Core Analytics utilizza canali di marketing derivati completamente al momento della generazione del rapporto (ovvero valori medi derivati).</li><li>Attribution IQ utilizza una definizione di visita in fase di elaborazione, tranne quando utilizzata in una VRS di elaborazione in fase di report.</li></ul> |
| Suite di rapporti virtuali di base AA con [elaborazione dei tempi di report](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) (VRS RTP) | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>[Analytics tra dispositivi](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=it)</li></ul> | <ul><li>Definizione della visita</li><li>Logica di attribuzione</li><li>Logica del segmento</li><li>Metriche calcolate </li><li>Altre impostazioni RTP VRS</li></ul> | <ul><li>Regole per i canali di marketing a livello di hit</li><li>Regole per i canali di marketing a livello di visita</li></ul> | <ul><li>Vedi VRS RTP [documentazione](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en).</li></ul> |
| [Connettore sorgente di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it)dataset basato su AEP data lake | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Regole per i canali di marketing a livello di hit</li><li>Unione basata sui campi (nota)</li></ul> |  | <ul><li>[Regole per i canali di marketing a livello di visita](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>Logica delle visite</li><li>Logica di attribuzione</li><li>Logica del filtro</li></ul> | <ul><li>È necessario applicare la propria logica di filtro e le metriche calcolate</li><li>L’unione basata sui campi crea un set di dati con unione separato, in aggiunta a quello creato dal connettore di origine di Analytics.</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=it) reporting | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Livello di hit [regole del canale di marketing](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>[Connessione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it) impostazioni</li><li>Unione basata sui campi (nota)</li></ul> | <ul><li>Definizione della sessione</li><li>[Impostazioni della visualizzazione dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=it)</li><li>Logica di attribuzione</li><li>Metriche calcolate </li><li>Logica del filtro</li></ul> | <ul><li>Regole per i canali di marketing a livello di visita</li></ul> | <ul><li>Per sfruttare le unione basate sui campi, è necessario utilizzare un set di dati con unione.</li></ul> |

{style=&quot;table-layout:auto&quot;}