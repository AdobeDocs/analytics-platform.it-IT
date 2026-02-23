---
title: Analisi delle tendenze
description: Misura il coinvolgimento degli utenti nel tempo.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 74%

---

# Analisi delle [!UICONTROL tendenze] {#trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_trends_button"
>title="Tendenze"
>abstract="Misura il coinvolgimento degli utenti nel tempo."

<!-- markdownlint-enable MD034 -->

L&#39;analisi ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Trends]** fornisce a insight informazioni preziose sulle prestazioni del prodotto o sul comportamento degli utenti nel tempo. L’asse orizzontale di questo rapporto è un intervallo di tempo, mentre l’asse verticale misura gli eventi desiderati.


>[!VIDEO](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/trends)

## Casi d’uso

I casi d’uso per questa analisi includono:

* **Valutazione delle prestazioni del prodotto**: le tendenze consentono di valutare le prestazioni complessive del prodotto in un determinato periodo. Analizzando metriche quali coinvolgimento degli utenti, tassi di adozione o di conversione, puoi verificare se le prestazioni del prodotto stanno migliorando, ristagnando o peggiorando.
* **Adozione di funzioni**: le tendenze consentono di comprendere in che modo gli utenti adottano nuove funzioni o nuovi aggiornamenti rilasciati. Puoi determinare quali funzioni sono popolari e quali funzioni richiedono miglioramenti. Queste informazioni ti consentono di prendere decisioni basate sui dati riguardo alle funzioni a cui dare priorità nelle tue attività di sviluppo.
* **Comportamento degli utenti**: le tendenze possono fornire informazioni sul comportamento degli utenti nel tempo. Esaminando le azioni specifiche intraprese dagli utenti, puoi identificare i pattern di possibile abbandono degli utenti. Puoi combinare le informazioni provenienti da questa analisi con il [Funnel](funnel.md) per ottenere ulteriori informazioni sul comportamento.
* **Test A/B e sperimentazione**: se esegui dei test A/B all’interno del prodotto, puoi utilizzare le Tendenze per misurare quali test sono più efficaci nel tempo.

## Interfaccia

Per una panoramica dell’interfaccia dell’analisi guidata, consulta [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Visualizzazione]**: passa da questa analisi a [Frequenza](frequency.md).
* **[!UICONTROL Eventi e metriche]**: eventi o metriche da misurare. Ogni selezione è rappresentata da una serie di grafici e da una riga di tabella. Non è possibile combinare eventi e metriche nella query. Dopo aver effettuato la prima selezione, le altre selezioni delle query devono essere dello stesso tipo. Puoi includere fino a cinque selezioni.
* **[!UICONTROL Conteggiato come]**: metodo di conteggio che desideri applicare agli eventi selezionati. <ul><li>**[!UICONTROL Le opzioni]** includono [!UICONTROL Utenti], [!UICONTROL Eventi], [!UICONTROL Sessioni], [!UICONTROL Percentuale di utenti], [!UICONTROL Eventi per sessione] e [!UICONTROL Eventi per utente].</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Ulteriori **[!UICONTROL opzioni B2B]** sono disponibili per Customer Journey Analytics B2B edition: [!UICONTROL Account globali], [!UICONTROL Account], [!UICONTROL Gruppi di acquisto], [!UICONTROL Opportunità], [!UICONTROL Percentuale di account globali], [!UICONTROL Percentuale di account], [!UICONTROL Percentuale di gruppi di acquisto], [!UICONTROL Percentuale di opportunità], [!UICONTROL Eventi per account globale], [!UICONTROL Eventi per account], [!UICONTROL Eventi per gruppo di acquisto] e [!UICONTROL Eventi per opportunità].</li></ul>Conteggiati come opzioni, sono applicabili solo alle query evento e vengono rimossi per le query metriche.
* **[!UICONTROL Segmenti]**: i segmenti che desideri misurare. Ogni segmento selezionato raddoppia il numero delle serie di grafici e delle righe di tabella. Puoi includere fino a cinque segmenti.
* **[!UICONTROL Proprietà raggruppamento]**: suddivide le serie di grafici e le righe di tabella in base ai valori della proprietà selezionata. È supportata una singola proprietà di raggruppamento. Nella tabella vengono visualizzati i primi 20 valori e nel grafico è possibile visualizzare fino a dieci valori. Puoi nascondere o esporre una riga nel grafico attivando l’icona ![Show hide icon](../assets/hide-in-chart.png).

### Impostazioni del grafico

L&#39;analisi [!UICONTROL Tendenze] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Tipo di grafico]**: tipo di visualizzazione che si desidera utilizzare. Le opzioni includono: linea, barre, barre sovrapposte e superfici sovrapposte.

### Sovrapposizioni

Aggiungi altri dati al grafico. Quando sul grafico sono visibili più serie, le sovrapposizioni vengono visualizzate solo al passaggio del mouse.

* **[!UICONTROL Rilevamento delle anomalie]**: esegue [il rilevamento delle anomalie](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) nell&#39;analisi con tendenze. I valori anomali vengono visualizzati sotto forma di punti su cui è possibile passare il puntatore per ottenere ulteriori informazioni.
* **[!UICONTROL Sovrapposizione linea di tendenza]**: aggiunge una linea di tendenza al grafico per meglio evidenziare un pattern nei dati.
   * [!UICONTROL Lineare]: crea una linea di regressione retta. Consigliata per dati lineari semplici che aumentano o diminuiscono a un tasso costante. Equazione: `y = a + b * x`
   * [!UICONTROL Logaritmica]: crea una linea di regressione curva. Consigliata per i dati che aumentano o diminuiscono rapidamente, quindi si livellano. Equazione: `y = a + b * log(x)`
   * [!UICONTROL Media mobile]: crea una linea di tendenza uniforme basata su un insieme di medie. Nota anche come media continua, la media mobile utilizza un numero specifico di punti di dati precedenti (determinati dalla selezione), ne calcola la media e utilizza tale media come punto sulla linea. Gli esempi includono la media mobile di sette giorni o la media mobile di quattro settimane. Le opzioni disponibili per la media mobile dipendono dall’intervallo e dall’intervallo di date selezionati.

### Confronto temporale

{{apply-time-comparison}}


### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è costituita da due componenti:

* **[!UICONTROL Intervallo]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono: Oraria, Giornaliera, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere una granularità diversa, da cui dipende il numero di punti dati nel grafico e il numero di colonne nella tabella. Nella visualizzazione di un’analisi di tre giorni con granularità giornaliera, ad esempio, saranno presenti solo tre punti dati, mentre in quella di un’analisi di tre giorni con granularità oraria ne saranno presenti 72.
* **[!UICONTROL Data]**: la data di inizio e di fine. Per comodità, sono disponibili intervalli di date continui predefiniti e intervalli personalizzati salvati in precedenza; in alternativa, puoi utilizzare il selettore del calendario per scegliere un intervallo di date fisso.


<!--

## Example

See below for an example of the analysis.

![Trends compare](../assets/trends-compare.png)

-->