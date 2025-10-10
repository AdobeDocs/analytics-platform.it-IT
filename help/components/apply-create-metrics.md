---
description: Scopri cosa sono le metriche e come utilizzarle in Analysis Workspace.
title: Metriche
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 5%

---

# Metriche

Le metriche consentono di quantificare i punti di dati in Analysis Workspace. Sono solitamente utilizzate come colonne in una visualizzazione e associate alle dimensioni.

## Utilizzare le metriche in Analysis Workspace

Le metriche sono flessibili per quanto riguarda il loro utilizzo in Analysis Workspace. Trascina una metrica in una tabella a forma libera vuota per visualizzare la tendenza della metrica nel periodo della data del progetto. Puoi anche trascinare una metrica quando è presente una dimensione per visualizzarla rispetto a ciascun elemento dimensione. Trascinare una metrica sopra un’intestazione di metrica esistente la sostituisce e trascinare una metrica accanto a un’intestazione consente di vedere entrambe le metriche una accanto all’altra.

Per informazioni su come aggiungere metriche e altri tipi di componenti ad Analysis Workspace, vedi [Utilizzare componenti in Analysis Workspace](/help/components/use-components-in-workspace.md).


## Tipi di metriche

Adobe offre diversi tipi di metriche da utilizzare in Analysis Workspace:


* **Metriche standard**: esempio di metriche standard: persone, sessioni, eventi.

  A differenza di Adobe Analytics, Customer Journey Analytics consente di definire le metriche standard in modo flessibile all’interno dell’ambito di una connessione e di una visualizzazione dati.

   * **Persone**: la metrica Persone in Customer Journey Analytics è il conteggio distinto degli ID persona. A seconda di quello che scegli come ID persona quando configuri i set di dati nella connessione, la metrica Persone può significare cose diverse.
   * **Sessioni**: la metrica Sessioni in Customer Journey Analytics è ciò che si definisce come parte della configurazione delle Impostazioni sessioni nella visualizzazione dati. Vedere [Impostazioni sessione](/help/data-views/session-settings.md).
   * **Eventi**: la metrica Eventi in Customer Journey Analytics è costituita dagli eventi che fanno parte di qualsiasi set di dati evento configurato come parte della connessione.

  Per l&#39;elenco completo delle metriche standard, vedere [Metriche standard](#standard-metrics).

* **Metriche calcolate** ![Calcolatore](/help/assets/icons/Calculator.svg): metriche definite dall&#39;utente basate su metriche standard, numeri statici o funzioni algoritmiche.

* **Modelli di metriche calcolate** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg): metriche definite da Adobe che si comportano in modo simile alle metriche calcolate. Puoi utilizzarli così come sono nei progetti Workspace o salvarne una copia per personalizzare la logica. Vedi [Metriche calcolate predefinite](calc-metrics/cm-workflow/../default-calcmetrics.md).

Puoi vedere se una metrica è approvata ![Icona Approvata](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) o meno. Per ulteriori dettagli su una metrica, passa il cursore del mouse sulla metrica e seleziona ![Icona informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Per ulteriori informazioni, vedere [Informazioni sul componente](use-components-in-workspace.md#component-info).


## Metriche standard

L’elenco completo delle metriche standard in Customer Journey Analytics:
{{standard-metrics}}


## Creare metriche calcolate

Le metriche calcolate consentono di configurare facilmente il modo in cui le metriche si relazionano tra loro, utilizzando semplici operatori o funzioni statistiche. Per ulteriori informazioni, vedere [Panoramica delle metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md).

Esistono diversi modi per creare metriche calcolate. Il metodo scelto determina se la metrica calcolata è disponibile nell’elenco dei componenti in tutti i progetti o solo nel progetto in cui è stata creata.

### Creare metriche calcolate per tutti i progetti

È possibile utilizzare il [generatore di metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) per [creare metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-workflow.md). Quando vengono create in questo modo, le metriche calcolate sono disponibili nell’elenco dei componenti e possono quindi essere utilizzate nei progetti di tutta l’organizzazione.

### Creare metriche calcolate per un singolo progetto

Puoi creare rapidamente una metrica di calcolo disponibile solo per il progetto in cui è stata creata.

Per creare una metrica calcolata per un singolo progetto:

1. In Analysis Workspace, apri il progetto in cui desideri creare la metrica calcolata.

1. In una tabella a forma libera, fai clic con il pulsante destro del mouse sull’intestazione di colonna di una singola colonna.

   Oppure

   Selezionare due colonne tenendo premuto il tasto Maiusc, quindi fare clic con il pulsante destro del mouse su una delle colonne selezionate.

1. Seleziona **[!UICONTROL Create metric from selection]**

   ![Evidenziazione del pannello Workspace Crea da selezione](assets/create-metric-from-selection.png)

1. Per creare una metrica calcolata solo per questo progetto, scegli tra le opzioni disponibili.

   Quando è selezionata una singola colonna, sono disponibili le seguenti opzioni:

   * [!UICONTROL **Media**]: crea una nuova colonna che mostra il valore medio nel set di elementi dimensionali della colonna. Questa opzione utilizza la funzione [Media](/help/components/calc-metrics/cm-functions.md#mean).

   * [!UICONTROL **Mediana**]: crea una nuova colonna che mostra il valore mediano nel set di elementi dimensionali della colonna. Questa opzione utilizza la funzione [Mediana](/help/components/calc-metrics/cm-functions.md#median).

   * [!UICONTROL **Colonna max**]: crea una nuova colonna che mostra il valore più grande nel set di elementi dimensionali della colonna. Questa opzione utilizza la funzione [Column Maximum](/help/components/calc-metrics/cm-functions.md#column-maximum).

   * [!UICONTROL **Colonna min**]: crea una nuova colonna che mostra il valore più piccolo nel set di elementi dimensionali della colonna. Questa opzione utilizza la funzione [Column Minimum](/help/components/calc-metrics/cm-functions.md#column-minimum).

   * [!UICONTROL **Somma colonna**]:Creates una nuova colonna che aggiunge tutti i valori numerici per una metrica all&#39;interno di una colonna (negli elementi di una dimensione). Questa opzione utilizza la funzione [Somma colonne](/help/components/calc-metrics/cm-functions.md#column-sum).

   Quando sono selezionate due colonne, sono disponibili le seguenti opzioni:

   * [!UICONTROL **Dividi**]: crea una nuova colonna che divide i valori delle due colonne selezionate.

   * [!UICONTROL **Sottrai**]: crea una nuova colonna che sottrae i valori delle due colonne selezionate.

   * [!UICONTROL **Aggiungi**]: crea una nuova colonna che aggiunge i valori delle due colonne selezionate.

   * [!UICONTROL **Moltiplica**]: crea una nuova colonna che moltiplica i valori delle due colonne selezionate.

   * [!UICONTROL **Modifica percentuale**]: crea una nuova colonna che mostra la modifica percentuale tra le due colonne selezionate.


## Confrontare metriche con diversi modelli di attribuzione

Per confrontare rapidamente un modello di attribuzione con un altro per una metrica, selezionare **[!UICONTROL Compare attribution models]** dal menu di scelta rapida per una metrica.

![Evidenziazione del pannello Workspace Confronta modelli di attribuzione](assets/compare-attribution.png)

Questa scelta rapida consente di confrontare un modello di attribuzione con un altro senza trascinare una metrica e configurarla due volte.


