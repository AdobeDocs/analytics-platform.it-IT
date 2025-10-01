---
title: Reporting di Content Analytics
description: Come creare rapporti in Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 96%

---

# Panoramica del reporting di Content Analytics

Puoi creare rapporti, eseguire analisi e ottenere insight da Content Analytics in [Analysis Workspace](/help/analysis-workspace/home.md). È disponibile un [modello](#template) Workspace specifico, che consente di accedere subito a un progetto Workspace precompilato con insight rilevanti sul contenuto.

Per iniziare a generare rapporti da zero con Content Analytics:

1. [Crea un nuovo progetto](/help/analysis-workspace/build-workspace-project/create-projects.md) o [apri un progetto esistente](/help/analysis-workspace/build-workspace-project/open-projects.md) in Workspace.
1. Assicurati di [selezionare una visualizzazione dati](/help/analysis-workspace/c-panels/panels.md#data-view) per la generazione di rapporti con Content Analytics. La funzione di reporting di Content Analytics è disponibile solo per le visualizzazioni dati [configurate](/help/content-analytics/config/configuration.md) per Content Analytics.
1. Trascina una visualizzazione ![Tabella](/help/assets/icons/Table.svg) [Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) nell’area di lavoro.
1. Utilizza [componenti specifici di Content Analytics](components.md) e altri [componenti](/help/components/overview.md) generici (come segmenti, intervalli di date, annotazioni) per creare le tue informazioni di Content Analytics.

## Miniature

In base alle dimensioni specifiche di Content Analytics utilizzate nel progetto, vengono visualizzate le miniature per le risorse e le dimensioni.

![Miniature di Content Analytics](../assets/aca-thumbnails.png)

Per impostazione predefinita, le miniature vengono visualizzate per le dimensioni Content Analytics pertinenti. Per configurare la visualizzazione delle miniature per una dimensione Content Analytics:

* Passa il puntatore su una riga di intestazione per una dimensione Content Analytics. Ad esempio, **[!UICONTROL Asset IDs]** o **[!UICONTROL Experience IDs]**.
* Seleziona ![Impostazione](/help/assets/icons/Setting.svg).
* Nel menu a comparsa **[!UICONTROL Row setting]**, sotto a **[!UICONTROL Settings]**, seleziona o deseleziona **[!UICONTROL Show Thumbnails]**.


## Anteprime

Per le righe di una dimensione Content Analytics che mostrano miniature, puoi aprire una finestra a comparsa di anteprima.

Per aprire l’anteprima con i dettagli seguenti:

* Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg). Vengono visualizzati i dettagli seguenti.

  | Anteprima esperienza | Anteprima risorsa |
  |---|---|
  | ![Anteprima esperienza di Content Analytics](../assets/aca-experience-preview.png) | ![Anteprima risorsa di Content Analytics](../assets/aca-asset-preview.png) |
  | Nome della dimensione (ad esempio, **[!UICONTROL Experience ID])** | Nome della dimensione della risorsa (ad esempio, **[!UICONTROL Asset ID])** |
  | **[!UICONTROL Impressions (all time)]**: numero di impression per l’esperienza. | **[!UICONTROL Impressions (all times)]**: numero di impression per la risorsa. |
  | **[!UICONTROL Assets]**: numero di risorse contenute in questa esperienza. <br/>Seleziona ![Raggruppamento](/help/assets/icons/Breakdown.svg) **[!UICONTROL Breakdown]** per ispezionare le risorse. | **[!UICONTROL Experiences]**: numero di esperienze in cui questa risorsa viene visualizzata. <br/>Seleziona ![Raggruppamento](/help/assets/icons/Breakdown.svg) **[!UICONTROL Breakdown]** per ispezionare le risorse. |
  | **[!UICONTROL First impression]**: data della prima impression dell’esperienza. | **[!UICONTROL First impression]**: data della prima impression della risorsa. |
  | **[!UICONTROL &#x200B; Most recent impression]**: data dell’impression più recente dell’esperienza. | **[!UICONTROL Most recent impression]**: data dell’impression più recente della risorsa. |
  | **[!UICONTROL Experience attributes]**: [attributi](/help/content-analytics/report/components.md#experience-attributes) dell’esperienza. | **[!UICONTROL Asset attributes]**: [attributi](/help/content-analytics/report/components.md#asset-attributes) della risorsa. |


## Modello

È disponibile un [modello](/help/analysis-workspace/templates/use-templates.md) di Content Analytics che consente di individuare gli attributi di contenuto e contenuto con prestazioni ottimali. Il modello fa parte del [caso d’uso Canale web e coinvolgimento](/help/analysis-workspace/templates/use-templates.md#web-engagement) e descrive le prestazioni dei contenuti a livello granulare. Puoi esaminare le prestazioni di singole risorse o attributi specifici.

In base ai risultati, potresti fare diverse cose. Ad esempio, promuovere le risorse ad alte prestazioni nella pagina Home; personalizzare i contenuti per segmenti specifici in modo da includere attributi ad alte prestazioni; o sostituire i contenuti che iniziano a perdere la loro attrattiva.

Per utilizzare il modello:

1. Seleziona **[!UICONTROL Workspace]** dal menu principale.
1. Assicurati di selezionare una visualizzazione dati configurata per Content Analytics.
1. Cerca o utilizza dei segmenti (**[!UICONTROL Web]** per **[!UICONTROL Channel]** e **[!UICONTROL Engagement]** per **[!UICONTROL Use Case]**) per trovare e selezionare il modello **[!UICONTROL Content Analytics]**.
1. Seleziona **[!UICONTROL Use template]**.
1. Nella finestra di dialogo **[!UICONTROL Set up your template]**, seleziona una metrica da **[!UICONTROL Select a conversion metric]**. Ad esempio: **[!UICONTROL Asset CTR]**.
1. Seleziona **[!UICONTROL Continue]**.

Un progetto **[!UICONTROL Content Analytics Overview]** viene aperto in [Analysis Workspace](/help/analysis-workspace/home.md). Il progetto è costituito da quattro [pannelli](/help/analysis-workspace/c-panels/panels.md) e ogni pannello fornisce [tabelle a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) e [visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) per rispondere a una domanda specifica:

* **Quale contenuto offre le prestazioni migliori?**
Questo pannello ti aiuta a capire quali esperienze e relative risorse contribuiscono al coinvolgimento e alla conversione. Le esperienze sono pagine web complete, acquisite in un momento specifico. Un’esperienza può contenere sia testo che più singole risorse di immagini. Una risorsa è una singola immagine.

  Il pannello è costituito dalle visualizzazioni seguenti:

   * **Esperienze**.

     >[!NOTE]
     >
     >Queste visualizzazioni sono disponibili solo quando [hai incluso esperienze](/help/content-analytics/config/guided.md#experience-capture-and-definition) nella configurazione di Content Analytics.
     > 

      * **CTR esperienza**: una visualizzazione [Variazione di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md) che mostra il CTR dell’esperienza.
      * **Esperienze con più conversioni**: una visualizzazione a [barre orizzontali](/help/analysis-workspace/visualizations/horizontal-bar.md) che mostra le esperienze con il maggior numero di conversioni in base alla metrica di conversione selezionata.
      * **Esperienze con prestazioni migliori**: una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (incluse [miniature](#thumbnails) e [anteprime](#previews)) per le esperienze dalle prestazioni migliori.

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
Content Analytics utilizza l’intelligenza artificiale e l’IA generativa per assegnare automaticamente a ogni risorsa metadati come soggetti, scene, colori di primo piano e così via. Un attributo è un tag di metadati assegnato dall’IA che descrive il contenuto di una risorsa o di un’esperienza. Ad esempio: <code>colore di primo piano: rosso</code> è un attributo assegnato automaticamente. Le visualizzazioni consentono di identificare gli attributi delle risorse che contribuiscono maggiormente alla conversione.

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
Un pannello costituito da una tabella a forma libera che specifica dove le risorse più visualizzate compaiono sul sito.

  Il pannello è composto da una visualizzazione:

   * **Dove si trovano le risorse più visualizzate?**
Puoi suddividere qualsiasi risorsa per dimensioni per capire meglio dove viene visualizzata l’immagine.

     Nell’esempio della [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (incluse [miniature](#thumbnails) e [anteprime](#previews)), viene utilizzato **[!UICONTROL Asset Perception ID]** anziché [!UICONTROL Asset Id]. A volte, la stessa esatta immagine può essere duplicata sul sito con un URL immagine diverso. L’attributo [!UICONTROL Asset Perception ID] consente di raggruppare questi duplicati sotto un singolo ID.

     Poiché le risorse possono cambiare in una pagina, ogni risorsa viene suddivisa per **[!UICONTROL Experience Id]**, in modo da identificare la versione della pagina in cui è apparsa la risorsa. È possibile sostituire [!UICONTROL Experience Id] con altre dimensioni che ti consentono di comprendere la posizione di una risorsa sul sito. Ad esempio, [!UICONTROL Page name], [!UICONTROL Page URL] o [!UICONTROL Site section].

     È inoltre possibile scambiare [!UICONTROL Asset Perception ID] con [!UICONTROL Asset Id] per ottenere un record in cui viene fatto riferimento a URL di immagini specifici.


>[!MORELIKETHIS]
>
>[Componenti di Content Analytics](components.md)
>&#x200B;>[Utilizzare i modelli](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
