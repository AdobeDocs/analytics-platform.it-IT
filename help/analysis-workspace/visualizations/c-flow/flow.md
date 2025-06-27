---
description: Scopri come utilizzare la visualizzazione Flusso in un Analysis Workspace.
title: Panoramica del flusso
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 95%

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

_Questo articolo descrive la visualizzazione del Flusso in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Consulta [Flusso](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]


La visualizzazione **[!UICONTROL Flow]** ![GraphPathing](/help/assets/icons/GraphPathing.svg) mostra i percorsi del cliente nei siti web e nelle app.

Con la visualizzazione puoi:

* Visualizzare il percorso del cliente nel sito web o nell’applicazione.
* Analizzare dove vanno i clienti prima e dopo specifici punti di controllo, ad esempio entrata, una specifica dimensione oppure uscita.
* Creare segmenti designando un punto specifico nel percorso scelto.


>[!BEGINSHADEBOX]

Per un video demo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Creare una visualizzazione del flusso](https://video.tv.adobe.com/v/346063/?quality=12&learn=on){target="_blank"}.

{{videoaa}}

>[!ENDSHADEBOX]


## Flussi interdimensionali

Ora puoi visualizzare il [flusso tra dimensioni](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md). Ad esempio, puoi combinare pagine e reparti in un unico diagramma. In questo caso, il flusso potrebbe andare dalla home page alla pagina Uomo e quindi al reparto Scarpe.

Ogni colonna può mostrare una diversa dimensione. Per aggiungere una dimensione al diagramma, trascinala fino ad una zona di rilascio.

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
