---
title: Confrontare l’elaborazione dei dati nelle funzioni di reporting di Adobe Analytics e Customer Journey Analytics
description: Comprendere le differenze nell’elaborazione dei dati delle varie funzioni di reporting
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: Basics
role: User
source-git-commit: 0e9dc47b80db142801a94dcbf31470d99a610949
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 64%

---

# Confrontare l’elaborazione dei dati tra Adobe Analytics e Customer Journey Analytics

Spesso è necessario poter elaborare i dati prima che siano utili per il reporting. Puoi elaborarli in diverse fasi del percorso, dalla raccolta dei dati alla generazione del report o della visualizzazione.

In Adobe Analytics la maggior parte dell’elaborazione dei dati avviene immediatamente dopo la raccolta dei dati. Per supportare questa **elaborazione al momento della raccolta** sono disponibili funzionalità come regole VISTA, regole di elaborazione, regole di elaborazione dei canali di marketing.
I dati vengono quindi memorizzati e al momento del rapporto puoi applicare un’elaborazione aggiuntiva. Ad esempio, suddividi le dimensioni, applica la segmentazione o seleziona un modello di attribuzione diverso. Questa **elaborazione al momento del rapporto** avviene istantaneamente.

In Adobe Analytics, l’elaborazione al momento del rapporto rappresenta in genere una quantità di elaborazione inferiore rispetto a quella che avviene al momento della raccolta.

![Elaborazione al momento della raccolta di Adobe Analytics](../assets/aa-processing.png)

Al contrario, Customer Journey Analytics è progettato per richiedere un’elaborazione iniziale minima del tempo di raccolta prima che i dati vengano organizzati e memorizzati. L’architettura di base di Customer Journey Analytics è progettata per funzionare con i dati memorizzati al momento del reporting. Customer Journey Analytics offre la sua potente funzionalità di elaborazione al momento del reporting non solo in Analysis Workspace. Ulteriori funzionalità di elaborazione al momento del reporting sono disponibili tramite la definizione di [componenti](/help/data-views/component-settings/overview.md) e [campi derivati](/help/data-views/derived-fields/derived-fields.md) nelle visualizzazioni dati.

![Elaborazione al momento dell’elaborazione del rapporto di Customer Journey Analytics](../assets/cja-processing.png)

Comprendere le differenze nell’elaborazione dei dati delle varie funzioni di reporting è utile per capire quali metriche sono disponibili e dove e perché possono differire.

Ad esempio, *visite* è definito come una metrica in Adobe Analytics al momento dell&#39;elaborazione dei dati. E *sessioni* è calcolato come una metrica in Customer Journey Analytics al momento del reporting. Di conseguenza, le due metriche possono differire in base alle regole per la definizione della sessione in una visualizzazione dati di Customer Journey Analytics.

Inoltre, visite e sessioni come metrica non sono disponibili nei set di dati creati dal connettore di origine di Analytics. E quindi ti richiederebbe di definire la sessione nella logica di query per eseguire confronti.

## Terminologia {#terms}

La tabella seguente definisce la terminologia dei diversi tipi di logica di elaborazione applicati ad Adobe Analytics e Customer Journey Analytics:

| Termine | Definizione | Note |
| --- | --- | --- |
| Elaborazione al momento della raccolta | Logica che viene eseguita quando i dati vengono elaborati, prima di essere memorizzati a scopo di reporting e analisi. | Questa logica viene incorporata nei dati storici e in genere non può essere modificata facilmente. |
| Elaborazione al momento dell’elaborazione del rapporto | Logica eseguita al momento dell’esecuzione di un rapporto. | Questa logica può essere applicata ai dati futuri e storici in fase di esecuzione del report in modo non distruttivo. |
| Logica a livello di hit | Logica applicata a livello di riga per riga. | Esempi: regole di elaborazione, VISTA, determinate regole dei canali di marketing. |
| Logica a livello di visita | Logica applicata a livello di visita. | Esempi: definizione di visita e sessione. |
| Logica a livello di visitatore | Logica applicata a livello di persona. | Esempio: unione di persone su dispositivi e canali diversi. |
| Logica di segmento | Valutazione delle regole del segmento evento/visita/persona (evento/sessione/persona). | Esempio: persone che hanno acquistato delle scarpe rosse. |
| Metriche calcolate | Valutazione delle metriche personalizzate create dal cliente. Le metriche calcolate possono essere basate su formule complesse, inclusi i segmenti. | Ad esempio, il numero di persone che hanno acquistato delle scarpe rosse. |
| Logica di attribuzione | Logica per il calcolo dell’attribuzione. | Esempio: persistenza eVar. |
| Impostazioni del componente | Applicazione di personalizzazioni a metriche o dimensioni quali attribuzione, comportamento, formato e altri | Esempio: creazione di bucket di valori per combinare valori numerici basati su un intervallo |
| Campi derivati | Logica applicata ai campi dello schema o standard come parte della definizione dei componenti in una visualizzazione dati. | Esempio: creazione di una nuova dimensione del canale di marketing |

{style="table-layout:auto"}

Nel tempo, Adobe Analytics e ora Customer Journey Analytics hanno migliorato la flessibilità consentendo l’esecuzione della logica dei dati a livello di visita e di persona in fase di esecuzione dei rapporti.

## Tipi di elaborazione dei dati {#types}

I passaggi di elaborazione dei dati eseguiti da Adobe Analytics e Customer Journey Analytics e la tempistica di tali passaggi varia da funzione a funzione. La tabella seguente fornisce un riepilogo dei tipi di elaborazione dei dati per ogni funzione e indica quando viene applicata l’elaborazione dei dati.

| Funzione | Applicata al momento dell’elaborazione | Applicata al momento del reporting | Non disponibile | Note |
| --- | --- | --- | --- | --- |
| [Rapporti di Adobe Analytics](https://experienceleague.adobe.com/it/docs/analytics)<br/>(escluse le funzionalità di attribuzione avanzate o le suite di rapporti virtuali con elaborazione al momento del reporting) | <ul><li>[Regole di elaborazione](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/c-processing-rules/processing-rules)</li><li>[Regole VISTA](https://experienceleague.adobe.com/en/docs/analytics/technotes/terms)</li><li>[Regole dei canali di marketing](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules) a livello di hit</li><li>Regole dei canali di marketing a livello di visita (vedi nota)</li><li>Definizione di visita</li><li>Logica di attribuzione</li></ul> | <ul><li>Logica di segmento</li><li>Metriche calcolate</li></ul> | <ul><li>Analytics tra dispositivi (vedi nota)</li></ul> | <ul><li>Analytics tra dispositivi richiede l’utilizzo di suite di rapporti virtuali con elaborazione al momento del reporting.</li><li>Le “regole dei canali di marketing a livello di visita” includono: **Is First Page of Visit** (È la prima pagina della visita), **Override Last-Touch Channel** (Sovrascrivi canale di ultimo contatto) e **Marketing Channel Expiration** (Scadenza canale di marketing). Consulta la [documentazione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels).</li></ul> |
| [Data Warehouse](https://experienceleague.adobe.com/it/docs/analytics/export/data-warehouse/data-warehouse) di Adobe Analytics | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Regole dei canali di marketing a livello di hit</li><li>Regole dei canali di marketing a livello di visita</li><li>Definizione di visita</li><li>Logica di attribuzione</li></ul> | <ul><li>Logica di segmento</li></ul> | <ul><li>Metriche calcolate</li><li>Cross-Device Analytics</li></ul> |     |
| [Feed di dati](https://experienceleague.adobe.com/it/docs/analytics/export/analytics-data-feed/data-feed-overview) di Adobe Analytics | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Regole dei canali di marketing a livello di hit</li><li>Regole dei canali di marketing a livello di visita</li><li>Definizione di visita (campo visitnum)</li><li>Logica di attribuzione (nelle colonne successive)</li></ul> |   | <ul><li>Logica di segmento</li><li>Metriche calcolate</li><li>Cross-Device Analytics</li></ul> | <ul><li>Le mappature ID di alcune colonne relative ai canali di marketing nei feed dati non sono incluse nei feed dati. Consulta la [documentazione sui feed dati](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference).</li></ul> |
| [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) di Adobe Analytics | <ul><li> Regole di elaborazione</li><li>Regole VISTA</li><ul> |   | <ul><li>Regole dei canali di marketing a livello di hit</li><li>Regole dei canali di marketing a livello di visita</li><li>Logica di visita</li><li>Logica di attribuzione</li><li>Logica di segmento</li><li>Metriche calcolate</li><li>Cross-Device Analytics</li></ul> |  |
| Adobe Analytics [Funzioni di attribuzione avanzate](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview) | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Definizione di visita (vedi nota)</li><li>Analytics tra dispositivi (vedi nota)</li></ul> | <ul><li>Regole dei canali di marketing a livello di hit (vedi nota)</li><li>Regole dei canali di marketing a livello di visita (vedi nota) Logica di attribuzione</li><li>Logica di segmento</li><li>Metriche calcolate</li></ul> |  | <ul><li>Analytics tra dispositivi richiede l’utilizzo di suite di rapporti virtuali con elaborazione al momento del reporting.</li><li>Le funzioni di attribuzione avanzate di Analytics core utilizzano canali di marketing derivati completamente al momento del reporting (ovvero valori medi derivati).</li><li>Le funzioni di attribuzione avanzate utilizzano una definizione di visita al momento dell’elaborazione, tranne quando utilizzate in una suite di rapporti virtuali per l’elaborazione al momento del reporting.</li></ul> |
| Suite di rapporti virtuali di Adobe Analytics con [elaborazione al momento del rapporto](https://experienceleague.adobe.com/it/docs/analytics/components/virtual-report-suites/vrs-report-time-processing) | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>[Analytics tra dispositivi](https://experienceleague.adobe.com/en/docs/analytics/components/cda/overview)</li></ul> | <ul><li>Definizione di visita</li><li>Logica di attribuzione</li><li>Logica di segmento</li><li>Metriche calcolate</li><li>Altre impostazioni di elaborazione al momento del rapporto delle suite di rapporti virtuali</li></ul> | <ul><li>Regole dei canali di marketing a livello di hit</li><li>Regole dei canali di marketing a livello di visita</li></ul> | <ul><li>Consulta la [documentazione](https://experienceleague.adobe.com/it/docs/analytics/components/virtual-report-suites/vrs-report-time-processing) sull’elaborazione al momento del rapporto della suite di rapporti virtuali.</li></ul> |
| Set di dati basato sul [connettore di origine di Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/analytics) nel data lake di Adobe Experience Platform | <ul><li>Regole di elaborazione</li><li>Regole VISTA</li><li>Regole dei canali di marketing a livello di hit</li><li>Unione basata sui campi (vedi nota)</li></ul> |   | <ul><li>[Regole dei canali di marketing a livello di visita](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels)</li><li>Logica di visita</li><li>Logica di attribuzione</li><li>Logica di segmento</li></ul> | <ul><li>Applicare la propria logica dei segmenti e le metriche calcolate</li><li>L’unione basata sui campi crea un set di dati unito e separato, in aggiunta a quello creato dal connettore di origine di Analytics.</li></ul> |
| Reporting di [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-landing) | <ul><li>Implementato come parte della raccolta dati di Adobe Experience Platform</li></ul> | <ul><li>Definizione di sessione</li><li>Impostazioni della [visualizzazione dati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-dataviews/data-views)<li>Logica di attribuzione</li><li>Metriche calcolate</li><li>Logica di segmento</li></ul> | <ul><li>Regole dei canali di marketing a livello di visita</li></ul> | <ul><li>Utilizza i set di dati uniti per sfruttare i vantaggi dell’analisi cross-channel.</li></ul> |

{style="table-layout:auto"}
