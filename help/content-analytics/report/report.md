---
title: Generazione di rapporti per l’analisi dei contenuti
description: Come creare rapporti su Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: 0712253f53de6e2ad19d0180f598e2f6f6b5ca5e
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 0%

---

# Panoramica reportistica di Content Analytics

>[!WARNING]
>
>Questo articolo è una bozza preliminare non ufficiale di una versione finale di prossima pubblicazione e fa parte della documentazione di Content Analytics. Tutti i contenuti sono soggetti a modifiche e nessun obbligo legale può essere derivato dalla versione corrente di questo articolo.
>

{{release-limited-testing}}

La generazione di rapporti sull’analisi dei contenuti viene eseguita all’interno di Analysis Workspace. È disponibile un [modello](#template) Workspace specifico, che consente di accedere immediatamente a un progetto Workspace precompilato con informazioni rilevanti sul contenuto.

Per iniziare a generare rapporti su Content Analytics da zero:

1. [Crea un nuovo](/help/analysis-workspace/build-workspace-project/create-projects.md) o [apri un progetto](/help/analysis-workspace/build-workspace-project/open-projects.md) esistente in Workspace.
1. Assicurati di [selezionare una visualizzazione dati](/help/analysis-workspace/c-panels/panels.md#data-view) per la generazione di rapporti di Content Analytics. Il reporting di Content Analytics è disponibile solo per le visualizzazioni dati [configurate](/help/content-analytics/config/configuration.md) per Content Analytics.
1. Trascina una visualizzazione ![Tabella](/help/assets/icons/Table.svg) [Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) nell&#39;area di lavoro.
1. Utilizza [componenti specifici di Content Analytics](components.md) e altri [componenti](/help/components/overview.md) generici (come filtri, intervalli di date, annotazioni) per creare informazioni approfondite di Content Analytics. In alternativa, utilizzare il [modello di analisi dei contenuti](#template).

## Miniature

In base alle dimensioni specifiche di Content Analytics che utilizzi nel progetto, vengono visualizzate le miniature per le risorse e le dimensioni.

![Miniature di Content Analytics](../assets/aca-thumbnails.png)

## Anteprime

Per le dimensioni che hanno miniature (come Nome risorsa, Nome esperienza e altre), puoi aprire una finestra a comparsa di anteprima.

Per aprire l&#39;anteprima con i dettagli seguenti:

* Selezionare ![InfoOutline](/help/assets/icons/InfoOutline.svg). Vengono visualizzati i dettagli seguenti.

  | Anteprima esperienza | Anteprima risorsa |
  |---|---|
  | ![Anteprima esperienza analisi contenuti](../assets/aca-experience-preview.png) | ![Anteprima risorse di analisi dei contenuti](../assets/aca-asset-preview.png) |
  | **[!UICONTROL Name of the experience]** | **[!UICONTROL Name of the asset]** |
  | **[!UICONTROL Impressions (all times)]**: numero di impression per l&#39;esperienza. | **[!UICONTROL Impressions (all times)]**: numero di impression per la risorsa. |
  | **[!UICONTROL Assets]**: numero di risorse contenute in questa esperienza. Seleziona ![Raggruppamento](/help/assets/icons/Breakdown.svg) **[!UICONTROL Breakdown]** per controllare le risorse. | **[!UICONTROL Experiences]**: numero di esperienze in cui questa risorsa viene visualizzata. ![Raggruppamento](/help/assets/icons/Breakdown.svg) **[!UICONTROL Breakdown]** per controllare le risorse. |
  | **[!UICONTROL First impression]**: data della prima impressione dell&#39;esperienza. | **[!UICONTROL First impression]**: data della prima impression della risorsa. |
  | **[!UICONTROL  Most recent impression]**: data dell&#39;impression più recente dell&#39;esperienza. | **[!UICONTROL Most recent impression]**: data dell&#39;impression più recente della risorsa. |
  | **[!UICONTROL Experience attributes]**: attributi dell&#39;esperienza. | **[!UICONTROL Asset attributes]**: attributi della risorsa. |


## Modello

È disponibile un [modello](/help/analysis-workspace/templates/use-templates.md) di analisi dei contenuti che consente di individuare gli attributi di contenuto e contenuto con prestazioni migliori. Il modello fa parte del caso d&#39;uso [Canale web e Coinvolgimento](/help/analysis-workspace/templates/use-templates.md#web-engagement) e descrive le prestazioni del contenuto a livello granulare. Puoi esaminare le prestazioni di singole risorse o attributi specifici.

In base a ciò che si impara, si potrebbero fare un certo numero di cose. Come promuovere le risorse ad alte prestazioni nella pagina principale, personalizzare il contenuto per segmenti specifici in modo da includere attributi ad alte prestazioni o ruotare il contenuto che ha iniziato a non essere più aggiornato.

Per utilizzare il modello:

1. Selezionare **[!UICONTROL Workspace]** dal menu principale.
1. Assicurati di aver selezionato una visualizzazione dati configurata per Content Analytics.
1. Cercare o utilizzare i filtri (**[!UICONTROL Web]** per **[!UICONTROL Channel]** e **[!UICONTROL Engagement]** per **[!UICONTROL Use Case]**s) per trovare e selezionare il modello **[!UICONTROL Content analytics]**.
1. Seleziona **[!UICONTROL Use template]**.
1. Nella finestra di dialogo **[!UICONTROL Set up your template]**, seleziona una metrica dalla finestra di dialogo **[!UICONTROL Select a conversion metric]**. Ad esempio: **[!UICONTROL Asset CTR]**.
1. Seleziona **[!UICONTROL Continue]**.

Un progetto **[!UICONTROL Content Analytics Overview]** viene aperto in Workspace. Il progetto si articola in quattro gruppi, ciascuno dei quali risponde a domande specifiche:

* **Quali sono le prestazioni migliori?**
Questo pannello ti aiuta a capire quali esperienze e quali risorse in esse sono alla base del coinvolgimento e della conversione. Le esperienze sono una pagina web completa, acquisita in un momento specifico. Un’esperienza può contenere sia testo che più singole risorse di immagine. Una risorsa è una singola immagine.

  Il pannello è costituito dalle seguenti visualizzazioni:

   * **Esperienze**

      * **Experience CTR**: una visualizzazione di riepilogo delle modifiche che mostra Experience CTR.
      * **Prime esperienze di conversione**: visualizzazione con grafico a barre orizzontale che mostra le prime esperienze di conversione in base alla metrica di conversione selezionata.
      * **Esperienze dalle prestazioni migliori**: una tabella a forma libera (con anteprime e anteprime) per le esperienze dalle prestazioni migliori.

   * **Assets**

      * **CTR risorsa**
Una visualizzazione [summary change](/help/analysis-workspace/visualizations/summary-number-change.md) che mostra Asset CTR.
      * **Migliori risorse da convertire**
Una visualizzazione con [barra orizzontale](/help/analysis-workspace/visualizations/horizontal-bar.md) che mostra le risorse di conversione principali in base alla metrica di conversione selezionata.
      * **Risorse dalle prestazioni migliori**
Una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (incluse [miniature](#thumbnails) e [anteprime](#previews)) per le risorse con prestazioni migliori.
      * **Assets - visualizzazioni e conversione.**
Visualizzazione [grafico a dispersione](/help/analysis-workspace/visualizations/scatterplot.md) che mostra un grafico a dispersione delle visualizzazioni delle risorse rispetto alle conversioni delle risorse.

* **Quali attributi di risorsa contribuiscono alle conversioni?**
Content Analytics utilizza l’intelligenza artificiale e GenAI per assegnare automaticamente ogni metadati di risorse, come soggetti, scene, colori in primo piano e così via. Un attributo è un tag di metadati assegnato dall’intelligenza artificiale che descrive cosa c’è in una risorsa o in un’esperienza. Ad esempio: <code>colore di primo piano: rosso</code> è un attributo assegnato automaticamente. Le visualizzazioni consentono di identificare gli attributi delle risorse che contribuiscono maggiormente alla conversione.

  Il pannello è costituito dalle seguenti visualizzazioni:

   * **Primi attributi di conversione risorse**
[barra orizzontale](/help/analysis-workspace/visualizations/horizontal-bar.md) che mostra i principali attributi di conversione delle risorse in base alla metrica di conversione selezionata.
   * **Primi attributi di conversione risorse rispetto ai 30 giorni precedenti**
Visualizzazione [horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md) che mostra i principali attributi di conversione delle risorse rispetto ai 30 giorni precedenti, in base alla metrica di conversione selezionata.
   * **Migliore conversione dei dati degli attributi delle risorse**
Una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) che mostra i principali attributi di conversione in base alla metrica di conversione selezionata. Seleziona una riga nella tabella per aggiornare la visualizzazione della tendenza degli attributi.
   * **Tendenza attributo**
Una visualizzazione [riga](/help/analysis-workspace/visualizations/line.md) che mostra la tendenza dell&#39;attributo per l&#39;attributo di conversione superiore selezionato delle risorse.
   * **Colore di primo piano risorsa**
Esempio di [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) che confronta le prestazioni degli elementi di una singola categoria di attributi di risorsa: Colori di primo piano. Puoi sostituire questo attributo di risorsa con altre dimensioni di categoria dell’attributo di risorsa.

* **Quali attributi esperienza contribuiscono alle conversioni?**
Mentre gli attributi della risorsa si concentrano sulle qualità visive delle immagini, gli attributi dell’esperienza si concentrano sul testo della pagina. Le visualizzazioni seguenti consentono di esplorare quali attributi di esperienza contribuiscono alla conversione. Questi attributi vengono inoltre assegnati automaticamente utilizzando i modelli AI e GenAI.

  Il pannello è costituito dalle seguenti visualizzazioni:

   * **Attributi esperienza di conversione principali**
Visualizzazione [horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md) che mostra i principali attributi dell&#39;esperienza di conversione in base alla metrica di conversione selezionata.
   * **Attributi esperienza di conversione principali rispetto ai 30 giorni precedenti**
Visualizzazione [horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md) che mostra i principali attributi dell&#39;esperienza di conversione rispetto ai 30 giorni precedenti, in base alla metrica di conversione selezionata.
   * **Primi dati attributo esperienza di conversione**
Una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) che mostra le prime esperienze di conversione in base alla metrica di conversione selezionata. Seleziona una riga nella tabella per aggiornare la visualizzazione Linee.
   * **Riga**
Una visualizzazione [line](/help/analysis-workspace/visualizations/line.md) che mostra la tendenza per l&#39;attributo esperienza di conversione superiore selezionato.
   * **Parole chiave esperienza**
Una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) che mostra le parole chiave dell&#39;esperienza principale in base alla metrica di conversione selezionata.

* **Dove vengono visualizzate le risorse nel sito?**
Un pannello costituito da una tabella a forma libera che specifica dove vengono visualizzate più risorse di visualizzazioni sul sito.

  Il pannello è costituito da una visualizzazione:

   * **Dove vengono visualizzate le risorse più visualizzate?**
Puoi suddividere qualsiasi ID risorsa per dimensioni che ti aiutino a capire meglio dove viene visualizzata l’immagine.

     In questo esempio [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (incluse [miniature](#thumbnails) e [anteprime](#previews)) viene utilizzato [!UICONTROL *ID percezione risorsa*] anziché [!UICONTROL *ID risorsa*]. A volte, la stessa immagine può essere duplicata sul sito con un URL immagine diverso. L&#39;attributo [!UICONTROL _Percezione risorsa_] consente di raggruppare questi duplicati in un singolo ID. Poiché le risorse possono cambiare in una pagina, ogni risorsa viene suddivisa per [!UICONTROL _ID esperienza_], per identificare la versione della pagina in cui è stata visualizzata la risorsa.

     Puoi sostituire [!UICONTROL _Experience ID_] con altre dimensioni che ti aiutano a comprendere la posizione di una risorsa sul tuo sito. [!UICONTROL _Nome pagina_], [!UICONTROL _URL pagina_] o [!UICONTROL _Sezione sito_].

     È inoltre possibile scambiare [!UICONTROL _ID percezione_] con [!UICONTROL _ID risorsa_] per ottenere un record in cui viene fatto riferimento a URL immagine specifici.


>[!MORELIKETHIS]
>
>[Componenti di analisi dei contenuti](components.md)
>[Usa modelli](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
