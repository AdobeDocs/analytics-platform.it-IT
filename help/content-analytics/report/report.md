---
title: Generazione rapporti Content Analytics
description: Scopri come creare rapporti su Content Analytics utilizzando visualizzazioni come tabelle a forma libera, barre e a dispersione.
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: 93ef16462842a819c3b980d557abaaf0cd547b6c
workflow-type: tm+mt
source-wordcount: '1473'
ht-degree: 56%

---

# Panoramica del reporting di Content Analytics

Puoi creare rapporti, eseguire analisi e ottenere informazioni approfondite su [!DNL Content Analytics] in [Analysis Workspace](/help/analysis-workspace/home.md). È disponibile un [modello](#template) Workspace specifico, che consente di accedere subito a un progetto Workspace precompilato con insight rilevanti sul contenuto.

Per creare un rapporto Content Analytics personalizzato da zero, effettua le seguenti operazioni:

1. [Crea un nuovo progetto](/help/analysis-workspace/build-workspace-project/create-projects.md) o [apri un progetto esistente](/help/analysis-workspace/build-workspace-project/open-projects.md) in Workspace.
1. Assicurati di [selezionare una visualizzazione dati](/help/analysis-workspace/c-panels/panels.md#data-view) per la generazione di rapporti con Content Analytics. La funzione di reporting di Content Analytics è disponibile solo per le visualizzazioni dati [configurate](/help/content-analytics/config/configuration.md) per Content Analytics.
1. Trascina una visualizzazione ![Tabella](/help/assets/icons/Table.svg) [Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) nell’area di lavoro.
1. Utilizza [componenti specifici di Content Analytics](components.md) e altri [componenti](/help/components/overview.md) generici (come segmenti, intervalli di date, annotazioni) per generare insight da Content Analytics.
1. Usa altre [visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) per migliorare il progetto.


## Miniature

In base alle dimensioni specifiche di Content Analytics utilizzate nel progetto, le miniature vengono visualizzate nelle seguenti visualizzazioni:

### Tabella a forma libera

![Miniature di Content Analytics](../assets/aca-thumbnails.png)

Per impostazione predefinita, le miniature sono visualizzate in una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). Per configurare la visualizzazione delle miniature per una dimensione Content Analytics:

* Passa il puntatore su una riga di intestazione per una dimensione Content Analytics. Ad esempio, **[!UICONTROL ID risorsa]** o **[!UICONTROL ID esperienza]**.
* Seleziona ![Impostazione](/help/assets/icons/Setting.svg).
* Nella finestra a comparsa **[!UICONTROL Impostazione riga]**, sotto **[!UICONTROL Impostazioni]**, selezionare o deselezionare **[!UICONTROL Mostra miniature]**.


### Barre (sovrapposte) e Barre orizzontali (sovrapposte)

{{release-limited-testing-section}}

![Miniature Content Analytics per grafico a barre](/help/content-analytics/assets/aca-bar-thumbnail.png)


Le miniature vengono visualizzate come parte della legenda sull&#39;asse verticale o orizzontale. Le miniature vengono visualizzate anche quando passi il cursore su una barra in una [barra (sovrapposta)](/help/analysis-workspace/visualizations/bar.md) e una [barra orizzontale (sovrapposta)](/help/analysis-workspace/visualizations/horizontal-bar.md).


### A dispersione

{{release-limited-testing-section}}

![Miniature Content Analytics per dispersione](/help/content-analytics/assets/aca-scatter-thumbnail.png)

Le miniature vengono visualizzate quando passi il cursore su un punto dati in una [dispersione](/help/analysis-workspace/visualizations/scatterplot.md).

## Anteprime

>[!AVAILABILITY]
>
>La funzionalità per le visualizzazioni a barre e a dispersione descritta in questa sezione si trova nella fase di test limitato del rilascio e potrebbe non essere ancora disponibile nell’ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Customer Journey Analytics, consulta [Rilascio delle funzioni di Customer Journey Analytics](/help/release-notes/releases.md).
>

È possibile aprire una finestra a comparsa di anteprima. A tale scopo, effettua le seguenti operazioni:

* Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) in una [tabella a forma libera](#freeform-table).
* Seleziona una barra specifica in una visualizzazione [barra](#bar-and-horizontal-bar) o [barra orizzontale](#bar-and-horizontal-bar) o un punto dati in una visualizzazione [dispersione](#scatter).


Vengono visualizzati i dettagli seguenti.

| Anteprima esperienza | Anteprima risorsa |
|---|---|
| ![Anteprima esperienza di Content Analytics](../assets/aca-experience-preview.png) | ![Anteprima risorsa di Content Analytics](../assets/aca-asset-preview.png) |
| Nome della dimensione (ad esempio, **[!UICONTROL ID esperienza])** | Nome della dimensione della risorsa (ad esempio, **[!UICONTROL ID risorsa])** |
| **[!UICONTROL Impression (in qualsiasi momento)]**: numero di impression per l&#39;esperienza. | **[!UICONTROL Impression (tutte le volte)]**: numero di impression per la risorsa. |
| **[!UICONTROL Assets]**: numero di risorse contenute in questa esperienza. <br/>Seleziona ![Raggruppamento](/help/assets/icons/Breakdown.svg) **[!UICONTROL Raggruppamento]** per esaminare le risorse. | **[!UICONTROL Esperienze]**: numero di esperienze in cui questa risorsa viene visualizzata. <br/>Seleziona ![Raggruppamento](/help/assets/icons/Breakdown.svg) **[!UICONTROL Raggruppamento]** per esaminare le risorse. |
| **[!UICONTROL Prima impressione]**: data della prima impressione dell&#39;esperienza. | **[!UICONTROL Prima impression]**: data della prima impression della risorsa. |
| **[!UICONTROL Impression più recente]**: data dell&#39;impression più recente dell&#39;esperienza. | **[!UICONTROL Impression più recente]**: data dell&#39;impression più recente della risorsa. |
| **[!UICONTROL Attributi esperienza]**: gli [attributi](/help/content-analytics/report/components.md#experience-attributes) dell&#39;esperienza. | **[!UICONTROL Attributi risorsa]**: gli [attributi](/help/content-analytics/report/components.md#asset-attributes) della risorsa. |


## Modello

È disponibile un [modello](/help/analysis-workspace/templates/use-templates.md) di Content Analytics per aiutarti a capire quali sono i contenuti e gli attributi di contenuto con prestazioni migliori. Il modello fa parte del [caso d’uso Canale web e coinvolgimento](/help/analysis-workspace/templates/use-templates.md#web-engagement) e descrive le prestazioni dei contenuti a livello granulare. Puoi esaminare le prestazioni di singole risorse o attributi specifici.

In base ai risultati, potresti fare diverse cose. Ad esempio, promuovere le risorse ad alte prestazioni nella pagina Home; personalizzare i contenuti per segmenti specifici in modo da includere attributi ad alte prestazioni; o sostituire i contenuti che iniziano a perdere la loro attrattiva.

Per utilizzare il modello:

1. Selezionare **[!UICONTROL Workspace]** dal menu principale.
1. Assicurati di selezionare una visualizzazione dati configurata per Content Analytics.
1. Cerca o utilizza segmenti (**[!UICONTROL Web]** per **[!UICONTROL Canale]** e **[!UICONTROL Coinvolgimento]** per **[!UICONTROL Caso d&#39;uso]**s) per trovare e selezionare il modello **[!UICONTROL Content Analytics]**.
1. Seleziona **[!UICONTROL Usa modello]**.
1. Nella finestra di dialogo **[!UICONTROL Configura il modello]**, seleziona una metrica dalla finestra di dialogo **[!UICONTROL Seleziona una metrica di conversione]**. Ad esempio, **[!UICONTROL CTR risorsa]**.
1. Seleziona **[!UICONTROL Continua]**.

Un progetto **[!UICONTROL Panoramica di Content Analytics]** viene aperto in [Analysis Workspace](/help/analysis-workspace/home.md). Il progetto è costituito da quattro [pannelli](/help/analysis-workspace/c-panels/panels.md) e ogni pannello fornisce [tabelle a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) e [visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) per rispondere a una domanda specifica:

* **Quale contenuto offre le prestazioni migliori?**
Questo pannello ti aiuta a capire quali esperienze e relative risorse contribuiscono al coinvolgimento e alla conversione. Le esperienze sono pagine web complete, acquisite in un momento specifico. Un’esperienza può contenere sia testo che più singole risorse di immagini. Una risorsa è una singola immagine.

  Il pannello è costituito dalle visualizzazioni seguenti:

   * **Esperienze**.

     >[!NOTE]
     >
     >Queste visualizzazioni vengono visualizzate nel modello solo se hai configurato per [includere esperienze](/help/content-analytics/config/guided.md#experience-capture-and-definition) nella configurazione di Content Analytics.
     > 

      * **Experience CTR**: una visualizzazione [summary change](/help/analysis-workspace/visualizations/summary-number-change.md) che mostra Experience CTR.
      * **Esperienze con più conversioni**: una visualizzazione a [barre orizzontali](/help/analysis-workspace/visualizations/horizontal-bar.md) che mostra le esperienze con il maggior numero di conversioni in base alla metrica di conversione selezionata.
      * **Esperienze dalle prestazioni migliori**: una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (incluse [miniature](#thumbnails) e [anteprime](#previews)) per le esperienze dalle prestazioni migliori.

   * **Risorse**

      * **CTR risorsa**
Una visualizzazione [Variazione di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md) che mostra il CTR della risorsa.
      * **Risorse con più conversione**
Una visualizzazione a [barre orizzontali](/help/analysis-workspace/visualizations/horizontal-bar.md) che mostra le risorse con più conversioni in base alla metrica selezionata.
      * **Risorse con prestazioni migliori**
Una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (incluse [miniature](#thumbnails) e [anteprime](#previews)) per le risorse dalle prestazioni migliori.
      * **Risorse: visualizzazioni e conversione.**
Un [grafico a dispersione](/help/analysis-workspace/visualizations/scatterplot.md) che mostra il numero di visualizzazioni delle risorse rispetto al numero di conversioni delle stesse.

* **Quali attributi delle risorse contribuiscono alle conversioni?**
Content Analytics utilizza AI e GenAI per assegnare automaticamente ogni risorsa [metadati](/help/content-analytics/report/components.md#asset-metadata) e [attributi](/help/content-analytics/report/components.md#asset-attributes), come soggetti, scene, colori di primo piano e altro ancora. Un attributo è un tag di metadati assegnato dall’IA che descrive il contenuto di una risorsa o di un’esperienza. Ad esempio: <code>colore di primo piano: rosso</code> è un attributo assegnato automaticamente. Le visualizzazioni consentono di identificare gli attributi delle risorse che contribuiscono maggiormente alla conversione.

  Il pannello è costituito dalle visualizzazioni seguenti:

   * **Attributi di risorsa con più conversioni**
Un grafico a [barre orizzontali](/help/analysis-workspace/visualizations/horizontal-bar.md) che mostra gli attributi di risorsa con il maggior numero di conversioni in base alla metrica selezionata.
   * **Attributi di risorsa con più conversioni rispetto ai 30 giorni precedenti**
Visualizzazione a [barre orizzontali](/help/analysis-workspace/visualizations/horizontal-bar.md) che mostra gli attributi di risorsa con più conversioni rispetto ai 30 giorni precedenti, in base alla metrica di conversione selezionata.
   * **Dati degli attributi di risorsa con più conversione**
Una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) che mostra gli attributi con più conversioni in base alla metrica di conversione selezionata. Seleziona una riga nella tabella per aggiornare la visualizzazione della tendenza degli attributi.
   * **Tendenza attributo**
Una visualizzazione a [linee](/help/analysis-workspace/visualizations/line.md) che mostra la tendenza per gli attributi selezionati per le risorse con più conversioni.
   * **Colore di primo piano risorsa**
Esempio di [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) che confronta le prestazioni degli elementi di una singola categoria di attributi di risorsa: Colori di primo piano. Puoi sostituire questo attributo di risorsa con altre dimensioni di categoria di attributi di risorsa.

* **Quali attributi dell’esperienza contribuiscono alle conversioni?**

  >[!NOTE]
  >
  >Questo pannello viene visualizzato solo se nella configurazione di Content Analytics hai [incluso delle esperienze](/help/content-analytics/config/guided.md#experience-capture-and-definition).
  > 

  Mentre gli attributi delle risorse si concentrano sulle qualità visive delle immagini, gli attributi delle esperienze si concentrano sul testo presente nella pagina. Le visualizzazioni seguenti consentono di esplorare gli attributi di esperienza che contribuiscono alla conversione. Anche questi attributi vengono assegnati automaticamente utilizzando modelli di intelligenza artificiale e IA generativa.

  Il pannello è costituito dalle visualizzazioni seguenti:

   * **Attributi esperienza con più conversioni**
Visualizzazione a [barre orizzontali](/help/analysis-workspace/visualizations/horizontal-bar.md) che mostra gli attributi esperienza con più conversioni in base alla metrica di conversione selezionata.
   * **Attributi esperienza con più conversioni rispetto ai 30 giorni precedenti**
Visualizzazione a [barre orizzontali](/help/analysis-workspace/visualizations/horizontal-bar.md) che mostra gli attributi esperienza con più conversioni rispetto ai 30 giorni precedenti, in base alla metrica di conversione selezionata.
   * **Dati attributo esperienza con più conversioni**
Una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) che mostra le esperienze con più conversioni in base alla metrica di conversione selezionata. Seleziona una riga nella tabella per aggiornare la visualizzazione a linee.
   * **Linee**
Una visualizzazione [a linee](/help/analysis-workspace/visualizations/line.md) che mostra la tendenza dell’attributo esperienza con più conversioni.
   * **Parole chiave per l’esperienza**
Una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) che mostra le parole chiave per l’esperienza in base alla metrica di conversione selezionata.

* **Dove vengono visualizzate le risorse sul sito?**
Un pannello costituito da una tabella a forma libera che specifica dove vengono visualizzate sul sito le risorse più visualizzate. Questa analisi ti aiuta a capire quali pagine o sezioni traggono il massimo vantaggio dalle risorse con prestazioni migliori e dove ottimizzare il posizionamento.

  Il pannello è composto da una visualizzazione:

   * **Dove si trovano le risorse più visualizzate?**
Puoi suddividere qualsiasi risorsa per dimensioni per capire meglio dove viene visualizzata l’immagine.

     Nell&#39;esempio [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (incluse [miniature](#thumbnails) e [anteprime](#previews)) viene utilizzato **[!UICONTROL ID percezione risorsa]** anziché [!UICONTROL ID risorsa]. A volte, la stessa esatta immagine può essere duplicata sul sito con un URL immagine diverso. L&#39;attributo [!UICONTROL ID percezione risorsa] consente di raggruppare questi duplicati in un singolo ID.

     Poiché le risorse possono cambiare in una pagina, ogni risorsa viene suddivisa per **[!UICONTROL ID esperienza]**, per identificare la versione della pagina in cui è apparsa la risorsa. Puoi sostituire [!UICONTROL Experience Id] con altre dimensioni che ti aiutano a capire la posizione di una risorsa sul tuo sito. [!UICONTROL Nome pagina], [!UICONTROL URL pagina] o [!UICONTROL Sezione sito].

     È inoltre possibile scambiare [!UICONTROL ID percezione risorsa] con [!UICONTROL ID risorsa] per ottenere un record in cui viene fatto riferimento a URL immagine specifici.


>[!MORELIKETHIS]
>
>[Componenti di Content Analytics](components.md)
>[Utilizzare i modelli](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
