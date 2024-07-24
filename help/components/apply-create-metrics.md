---
description: In Analysis Workspace, le metriche possono essere utilizzate in due modi.
title: Metriche
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: cdab5d8b674527a1c3f950284daac65d0ab01900
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 10%

---

# Metriche

Le metriche consentono di quantificare i punti dati in Analysis Workspace. Sono più comunemente utilizzate come colonne in una visualizzazione e legate alle dimensioni.

## Tipi di metriche

Adobe offre diversi tipi di metriche da utilizzare in Analysis Workspace:

* **Metriche standard**: esempio di metriche standard: persone, sessioni, eventi.

* **Metriche calcolate** ![Icona metrica calcolata](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg): metriche definite dall&#39;utente basate su metriche standard, numeri statici o funzioni algoritmiche.

* **Modelli di metriche calcolate**  <img src="./assets/adobe-logo.svg" width="18"> : metriche definite dall&#39;Adobe che si comportano in modo simile alle metriche calcolate. Puoi utilizzarli così come sono nei progetti Workspace o salvarne una copia per personalizzarne la logica.


![Evidenziazione delle metriche nel pannello di Workspace nel riquadro di sinistra.](assets/cja-metrics.png)

Puoi vedere se una metrica è approvata ![Icona Approvata](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) o meno. Per ulteriori dettagli su una metrica, passa il cursore del mouse sulla metrica e seleziona ![Icona informazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


Le metriche sono flessibili per quanto riguarda il loro utilizzo in Analysis Workspace. Trascina una metrica in una tabella a forma libera vuota per visualizzare la tendenza della metrica nel periodo della data del progetto. Puoi anche trascinare una metrica quando è presente una dimensione per visualizzarla rispetto a ciascun elemento dimensione. Trascinare una metrica sopra un’intestazione di metrica esistente la sostituisce e trascinare una metrica accanto a un’intestazione consente di vedere entrambe le metriche una accanto all’altra.

## Utilizzare le metriche in Analysis Workspace

Le metriche possono essere utilizzate in vari modi all’interno di Analysis Workspace. Per informazioni su come aggiungere metriche e altri tipi di componenti ad Analysis Workspace, vedi [Utilizzare componenti in Analysis Workspace](/help/components/use-components-in-workspace.md).

## Creare metriche calcolate

Le metriche calcolate consentono di vedere facilmente in che modo le metriche si relazionano tra loro utilizzando semplici operatori o funzioni statistiche.

Esistono diversi modi per creare metriche calcolate. Il metodo scelto determina se la metrica calcolata è disponibile nell’elenco dei componenti in tutti i progetti o solo nel progetto in cui è stata creata.

### Creare metriche calcolate per tutti i progetti

Puoi utilizzare il generatore di metriche calcolate per creare metriche calcolate. Quando vengono create in questo modo, le metriche calcolate sono disponibili nell’elenco dei componenti e possono quindi essere utilizzate nei progetti di tutta l’organizzazione.

Per informazioni su come accedere al generatore di metriche calcolate, vedere [Genera metriche](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Creare metriche calcolate per un singolo progetto

Puoi creare metriche calcolate rapide disponibili solo per il progetto in cui sono state create.

Per creare una metrica calcolata per un singolo progetto:

1. In Analysis Workspace, apri il progetto in cui desideri creare la metrica calcolata.

1. In una tabella a forma libera, fare clic con il pulsante destro del mouse su una o più celle di colonna di intestazione, quindi selezionare **[!UICONTROL Create metric from selection]**

   ![Evidenziazione del pannello Workspace Crea da selezione](assets/create-metric-from-selection.png)

1. Per creare una metrica calcolata solo per questo progetto, scegli una delle seguenti opzioni:

   * [!UICONTROL **Dividi**]

   * [!UICONTROL **Sottrai**]

   * [!UICONTROL **Aggiungi**]

   * [!UICONTROL **Moltiplica**]

   In alternativa, per aprire il generatore di metriche calcolate e creare la metrica calcolata per tutti i progetti, selezionare [!UICONTROL **Apri nel generatore di metriche calcolate**], quindi continuare con [Genera metriche](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

[Metriche calcolate: metriche senza implementazione](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=it) (3:42)

## Confrontare metriche con diversi modelli di attribuzione

Per confrontare in modo rapido e semplice un modello di attribuzione con un altro, fare clic con il pulsante destro del mouse su una metrica e selezionare **[!UICONTROL Compare Attribution Models]**:

![Evidenziazione del pannello Workspace Confronta modelli di attribuzione](assets/compare-attribution.png)

Questa scorciatoia ti consente di confrontare in maniera facile e veloce un modello di attribuzione con un altro senza trascinare una metrica e configurarla due volte.
