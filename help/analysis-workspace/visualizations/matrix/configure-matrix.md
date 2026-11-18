---
title: Configurare una visualizzazione a matrice in Analysis Workspace
description: Scopri come configurare la visualizzazione a matrice in Customer Journey Analytics Analysis Workspace, inclusi i componenti, le opzioni di visualizzazione e le impostazioni.
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 4%
---

# Configurare una visualizzazione a matrice

La visualizzazione della matrice è una griglia di valori che mostra in che modo gli elementi dimensionali di due dimensioni si sovrappongono o si correlano tra loro. Ogni cella mostra l’intersezione dell’elemento dimensione della riga con quello dell’elemento dimensione della colonna.

![Visualizzazione matrice](assets/matrix-overview.png)

## Panoramica sulla matrice

Consulta [Panoramica matrice](/help/analysis-workspace/visualizations/matrix/matrix.md) per ulteriori informazioni sulla visualizzazione della matrice, tra cui:

* Funzioni chiave

* Insight potenziali

* Differenze tra le visualizzazioni a matrice, a forma libera, a Venn e a dispersione

## Creare una visualizzazione a matrice

1. Aggiungi un pannello vuoto al progetto, seleziona l&#39;icona [!UICONTROL **Visualizzazioni**] nella barra a sinistra, quindi trascina la visualizzazione [!UICONTROL **Matrice**] nel pannello. <!-- FOLLOW-UP: add the Matrix icon before the name when it's available in help/assets/icons. -->

   Oppure

   Aggiungere una visualizzazione della matrice in uno dei modi descritti nella sezione [Aggiungere visualizzazioni a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) in [Panoramica delle visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

   <!-- add screenshot of the Matrix configuration fields -->

1. Specifica le seguenti informazioni per configurare la visualizzazione della matrice:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Dimensione riga**] | Dimensione i cui elementi vengono visualizzati come righe nella matrice. |
   | [!UICONTROL **Dimensione colonna**] | Dimensione i cui elementi vengono visualizzati come colonne nella matrice. <p>Se selezioni la stessa dimensione sia per la dimensione riga che per la dimensione colonna, la visualizzazione Matrice confronta gli elementi dimensionali tra loro. Ad esempio, se entrambe le dimensioni sono _Tipo dispositivo_, ogni cella mostra la sovrapposizione o la correlazione tra due tipi di dispositivi, ad esempio _Telefono cellulare_ e _Tablet_. I valori sopra e sotto la diagonale si riflettono a vicenda.</p> |
   | [!UICONTROL **Metrica**] | La metrica visualizzata da ogni cella per la combinazione del relativo elemento dimensione riga e elemento dimensione colonna. |
   | [!UICONTROL **Contenitore**] | Contenitore che determina l’ambito della sovrapposizione tra elementi dimensione riga e elementi dimensione colonna. Se i nomi dei contenitori sono diversi da quelli predefiniti mostrati di seguito, significa che sono stati personalizzati nella visualizzazione dati.<ul><li>**Persona:** (impostazione predefinita) Un elemento dimensione riga e un elemento dimensione colonna si sovrappongono quando si verificano per la stessa persona, in un numero qualsiasi di sessioni.</li><li>**Sessione:** un elemento dimensione riga e un elemento dimensione colonna si sovrappongono quando si verificano nella stessa sessione.</li><li>**Evento:** un elemento dimensione riga e un elemento dimensione colonna si sovrappongono quando si verificano nello stesso evento.</li></ul><!-- SME CHECK: confirm how each container defines overlap. --> |

1. (Facoltativo) Modificare una delle seguenti impostazioni:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Limite righe**] | Il numero massimo di righe mostrato nella visualizzazione della matrice. Il valore predefinito è 10. <!-- SME CHECK: Which items are shown (top items by the metric?)? Does the limit also apply to columns? What's the maximum? --> |
   | [!UICONTROL **Tavolozza di sovrapposizione**] | La scala dei colori per le celle quando la matrice mostra [conteggi di sovrapposizione](#view-overlap-count-or-correlation-strength). |
   | [!UICONTROL **Tavolozza di correlazione**] | La scala dei colori per le celle quando la matrice mostra [la forza di correlazione](#view-overlap-count-or-correlation-strength). Le correlazioni negative e positive utilizzano colori diversi. |
   | [!UICONTROL **Granularità correlazione**] | Granularità temporale utilizzata per calcolare [la forza di correlazione](#view-overlap-count-or-correlation-strength), ad esempio **[!UICONTROL Giorno]**. Questo valore viene impostato automaticamente in base all’intervallo di date del pannello. Non puoi cambiarlo. <p>A seconda dell’intervallo di date del pannello, vengono scelte le seguenti granularità:</p><ul><li>[!UICONTROL **Ora**]: scelta per intervalli di date di 7 giorni o meno</li><li>[!UICONTROL **Giorno**]: scelto per intervalli di date superiori a 7 giorni, fino a 3 mesi</li><li>[!UICONTROL **Settimana**]: scelta per intervalli di date superiori a 3 mesi, fino a 1 anno</li><li>[!UICONTROL **Mese**]: scelto per intervalli di date superiori a 1 anno</li></ul><!-- SME CHECK: The granularities and date range thresholds in this list are a best guess. Confirm which granularities are used for which date ranges. --> |
   | [!UICONTROL **Valori cella diagonale**] | Come la visualizzazione della matrice mostra le celle in cui un elemento dimensione si incontra da solo. Questa impostazione è disponibile solo quando la dimensione riga e la dimensione colonna sono uguali.<ul><li>**[!UICONTROL Mostra]:** Mostra il valore.</li><li>**[!UICONTROL Trattino]:** Mostra un trattino invece del valore.</li><li>**[!UICONTROL Vuoto]:** Lascia vuota la cella.</li></ul> |

1. Seleziona [!UICONTROL **Genera**].

   <!-- add screenshot -->

1. Continua con la sezione seguente, [Visualizza conteggio di sovrapposizione o forza di correlazione](#view-overlap-count-or-correlation-strength).

## Visualizza conteggio sovrapposizioni o forza correlazione

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_matrix_overlap_correlation"
>title="Conteggio delle sovrapposizioni e forza di correlazione"
>abstract="<p>**Conteggio sovrapposizioni** è il valore della metrica selezionata in cui si sovrappongono un elemento dimensione riga e un elemento dimensione colonna.</p><p>**L&#39;intensità della correlazione** è una correlazione lineare, da -1 a +1, che indica la vicinanza con cui la metrica per i due elementi dimensionali si sposta insieme nel tempo. Il valore +1 indica che si alzano e cadono insieme, 0 indica che non esiste alcuna relazione e -1 indica che si muovono in direzioni opposte. La forza di correlazione viene calcolata separatamente dalla sovrapposizione, pertanto gli elementi dimensionali con poca sovrapposizione possono avere ancora una forte correlazione.</p>"

<!-- markdownlint-enable MD034 -->

Puoi attivare o disattivare la visualizzazione della matrice per visualizzare il conteggio di sovrapposizione o la forza di correlazione. Il conteggio delle sovrapposizioni viene visualizzato per impostazione predefinita.

1. In Analysis Workspace, apri una visualizzazione Matrice o [creane una nuova](#build-a-matrix-visualization).

1. Nell’angolo in alto a sinistra della visualizzazione Matrice, seleziona una delle seguenti opzioni:

   * [!UICONTROL **Conteggio sovrapposizioni**]: mostra il livello di sovrapposizione esistente per ogni elemento dimensione riga con ogni elemento dimensione colonna. Ogni cella mostra il valore della metrica selezionata per le persone, le sessioni o gli eventi (a seconda del contenitore) in cui si verificano entrambi gli elementi dimensionali.

   * [!UICONTROL **Intensità di correlazione**]: mostra con quale precisione la metrica selezionata per ogni elemento dimensione riga e per ogni elemento dimensione colonna si sposta insieme nell&#39;intervallo di date del pannello, come correlazione lineare da -1 a +1. Un valore pari a +1 indica che i due elementi dimensionali si alzano e cadono sempre insieme, 0 significa che non c’è alcuna relazione e -1 significa che si muovono sempre in direzioni opposte. La forza di correlazione viene calcolata separatamente dalla sovrapposizione, pertanto gli elementi dimensionali con poca sovrapposizione possono avere ancora una forte correlazione. La correlazione viene calcolata con la granularità temporale mostrata nell&#39;impostazione [!UICONTROL **Granularità correlazione**]. <!-- SME CHECK: Confirm that the linear correlation is Pearson. -->

   Una legenda nell’angolo superiore destro della visualizzazione della matrice mostra la scala di colori per la visualizzazione corrente: da basso a alto per il conteggio di sovrapposizione oppure da negativo (-1) a positivo (+1) per la forza di correlazione.

## Visualizza approfondimenti

<!-- FOLLOW-UP: Draft based on a prototype screenshot. Add a screenshot of the insight card. -->

Una scheda di insight nella parte inferiore della visualizzazione della matrice descrive i pattern rilevanti nei dati della matrice.

<!-- SME CHECK: How are insights generated (AI)? What does the label on the card (such as ABSOLUTE) mean, and what other labels are there? Do the insights differ between the Overlap count and Correlation strength views? Are they updated when you change the settings or the panel date range? Can you hide the card? Are any permissions, entitlements, or AI settings required? -->

Per visualizzare le informazioni:

1. In una visualizzazione a matrice, visualizza la scheda insight nella parte inferiore della visualizzazione.

1. Utilizza le frecce sulla scheda insight per scorrere gli approfondimenti disponibili.

## Modificare le impostazioni della matrice

Dopo aver generato una visualizzazione a matrice, puoi modificarne le impostazioni, ad esempio le dimensioni, la metrica o il contenitore.

Per modificare le impostazioni della matrice:

1. In una visualizzazione a matrice, seleziona ![Modifica](/help/assets/icons/Edit.svg) accanto al sottotitolo nella parte superiore della visualizzazione. Il sottotitolo riepiloga le impostazioni correnti, ad esempio la metrica e le dimensioni.

1. Modificare le impostazioni descritte in [Creare una visualizzazione della matrice](#build-a-matrix-visualization).

1. Seleziona [!UICONTROL **Genera**].

<!-- SME CHECK: Confirm that the Edit icon reopens the build settings. Does the Matrix keep the Overlap count or Correlation strength view after you rebuild it? -->

## Visualizzare dati di tendenza

Puoi visualizzare i dati di tendenza per una cella in una [visualizzazione righe](/help/analysis-workspace/visualizations/line.md). La visualizzazione delle linee mostra come cambia la metrica selezionata nell’intervallo di date del pannello. Le righe visualizzate dipendono dal fatto che la matrice mostri [conteggio di sovrapposizione o forza di correlazione](#view-overlap-count-or-correlation-strength).

Per visualizzare i dati di tendenza:

1. In una visualizzazione a matrice, fai clic con il pulsante destro del mouse sulla cella per la quale desideri visualizzare i dati delle tendenze.

1. Seleziona [!UICONTROL **Tendenza**].

   Al pannello, sopra la visualizzazione della matrice, viene aggiunta una visualizzazione a linee:

   * [!UICONTROL **Conteggio sovrapposizioni**]: una singola riga mostra la metrica selezionata, filtrata sia dall&#39;elemento dimensione riga che dall&#39;elemento dimensione colonna.

   * [!UICONTROL **Forza di correlazione**]: due righe mostrano la metrica selezionata, una per l&#39;elemento dimensione riga e una per l&#39;elemento dimensione colonna. Confronta le righe per vedere con quale intensità i due elementi dimensionali tendono insieme.

   <!-- SME CHECK: Does the overlap count filter use the Matrix container? Is the time granularity the panel default or the Correlation granularity? Can you select multiple cells? Is the option available for diagonal cells? -->

## Visualizzare la sovrapposizione in una visualizzazione Venn

È possibile visualizzare la sovrapposizione tra l&#39;elemento dimensione riga e l&#39;elemento dimensione colonna per una cella in una [visualizzazione Venn](/help/analysis-workspace/visualizations/venn.md).

Per ulteriori informazioni su quando utilizzare una visualizzazione Matrice o Venn, vedere [Scegliere tra le visualizzazioni Matrice, Tabella a forma libera, Venn o Dispersione](/help/analysis-workspace/visualizations/matrix/matrix.md#choose-between-matrix-freeform-table-venn-or-scatter-visualizations) in [Panoramica matrice](/help/analysis-workspace/visualizations/matrix/matrix.md).

Per visualizzare la sovrapposizione in una visualizzazione Venn:

1. In una visualizzazione a matrice, fai clic con il pulsante destro del mouse sulla cella di cui desideri visualizzare la sovrapposizione.

1. Seleziona [!UICONTROL **Mostra in Venn**].

   Al pannello viene aggiunta una visualizzazione Venn. Un cerchio rappresenta l’elemento dimensione riga e l’altro cerchio rappresenta l’elemento dimensione colonna. La visualizzazione di Venn utilizza la stessa metrica della visualizzazione della matrice. <!-- SME CHECK: Where is the Venn visualization added? Are segments created for each dimension item, and do they use the Matrix container? Is the option available for diagonal cells and in the Correlation strength view? -->

## Applicare un raggruppamento

È possibile suddividere i dati di una cella per un’altra dimensione per vedere quali elementi dimensionali contribuiscono al valore della cella.

Per applicare una suddivisione:

1. In una visualizzazione a matrice, fai clic con il pulsante destro del mouse sulla cella per la quale desideri applicare un raggruppamento.

1. Seleziona [!UICONTROL **Raggruppamento**].

1. Seleziona la dimensione da utilizzare per il raggruppamento.

   Gli elementi dimensionali principali per la dimensione di raggruppamento sono mostrati in una nuova tabella a forma libera. <!-- SME CHECK: Where is the table added? Does the breakdown use the Matrix metric and container? Can you select multiple cells? Is the option available for diagonal cells and in the Correlation strength view? -->


