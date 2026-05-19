---
description: Scopri come utilizzare la visualizzazione Flusso in Analysis Workspace.
title: Panoramica del flusso
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
autotag-review: '2026-05-19T08:39:33.544Z'
TQID: 'https://experienceleague.adobe.com/X0VLZhluDR9Q-ax7TcTOHEcn4r0V5yu64spZlfc4fwU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 349
ht-degree: 70%

---

# Panoramica del flusso {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="Flusso"
>abstract="Crea una visualizzazione per visualizzare il flusso di persone da un punto di controllo a quello successivo."

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="Flusso"
>abstract="Analizza il flusso di visite o visitatori da un punto di contatto a quello successivo. Specifica un componente (metrica, dimensione o elemento) per iniziare e terminare. Facoltativamente, puoi definire impostazioni avanzate per configurare ulteriormente la visualizzazione."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo documenta la visualizzazione Flusso in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Consulta [Flusso](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]


La visualizzazione ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flusso]** mostra i percorsi seguiti dai clienti nei tuoi siti Web e nelle tue app.

Con la visualizzazione puoi:

* Visualizzare il percorso del cliente nel sito web o nell’applicazione.
* Analizzare dove vanno i clienti prima e dopo specifici punti di controllo, ad esempio entrata, una specifica dimensione oppure uscita.
* Creare segmenti designando un punto specifico nel percorso scelto.


>[!BEGINSHADEBOX]

Per un video demo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Creare una visualizzazione del flusso](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization){target="_blank"}.

{{videoaa}}

>[!ENDSHADEBOX]


## Flussi interdimensionali

Ora puoi visualizzare il [flusso tra dimensioni](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md). Ad esempio, puoi combinare pagine e reparti in un unico diagramma. In questo caso, il flusso potrebbe passare dalla home page alla pagina Uomini e quindi al reparto Scarpe.

Ogni colonna può mostrare una dimensione diversa. Trascina una dimensione e rilascia una zona di rilascio per aggiungerla al diagramma.

>[!MORELIKETHIS]
>
>[Configurare una visualizzazione del flusso](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
>

## Scegliere tra le visualizzazioni Flusso, Abbandono o Area di lavoro del percorso

La visualizzazione Flusso ha analogie con la [visualizzazione Abbandono](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) e la [visualizzazione Area di lavoro del percorso](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md), ma con differenze importanti.

### Comprendere le differenze

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Quando utilizzare Flusso

Le visualizzazioni Flusso sono più adatte per:

* Analisi esplorativa ad hoc per il punto di contatto immediatamente successivo sul percorso. Utilizza Area di lavoro del percorso per i percorsi con una sequenza di pagine predefinita o per quelli che utilizzano un percorso finale.

* Percorsi non lineari con più punti di ingresso e percorsi. Utilizza Area di lavoro del percorso per percorsi con una sequenza di pagine predefinita.

Utilizza [la tabella precedente](#understand-the-differences) per le informazioni sulle differenze tra Flusso, Abbandono e Area di lavoro del percorso.
