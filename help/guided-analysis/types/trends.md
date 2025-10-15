---
title: Analisi delle tendenze
description: Misura il coinvolgimento degli utenti nel tempo.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
source-git-commit: e42f04eaa06a761803e76b64a5a16674fb4af57d
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 96%

---

# [!UICONTROL Trends] analisi {#trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_trends_button"
>title="Tendenze"
>abstract="Misura il coinvolgimento degli utenti nel tempo."

<!-- markdownlint-enable MD034 -->

L’analisi delle ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Trends]** fornisce informazioni utili sulle prestazioni del prodotto o sul comportamento degli utenti nel tempo. L’asse orizzontale di questo rapporto è un intervallo di tempo, mentre l’asse verticale misura gli eventi desiderati.


>[!VIDEO](https://video.tv.adobe.com/v/3423441/?captions=ita&quality=12&learn=on)

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

* **[!UICONTROL View]**: passa da questa analisi a [Frequenza](frequency.md).
* **[!UICONTROL Events & Metrics]**: gli eventi o le metriche che desideri misurare. Ogni selezione è rappresentata da una serie di grafici e da una riga di tabella. Non è possibile combinare eventi e metriche nella query. Dopo aver effettuato la prima selezione, le altre selezioni delle query devono essere dello stesso tipo. Puoi includere fino a cinque selezioni.
* **[!UICONTROL Counted as]**: metodo di conteggio da applicare agli eventi selezionati. <ul><li>**[!UICONTROL Options]** include [!UICONTROL Users], [!UICONTROL Events], [!UICONTROL Sessions], [!UICONTROL Percentage of users], [!UICONTROL Events per session] e [!UICONTROL Events per user].</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Ulteriori **[!UICONTROL B2B options]** sono disponibili per Customer Journey Analytics B2B edition: [!UICONTROL Global accounts], [!UICONTROL Accounts], [!UICONTROL Buying groups], [!UICONTROL Opportunities], [!UICONTROL Percentage of global accounts], [!UICONTROL Percentage of accounts], [!UICONTROL Percentage of buying groups], [!UICONTROL Percentage of opportunities], [!UICONTROL Events per global account], [!UICONTROL Events per account], [!UICONTROL Events per buying group] e [!UICONTROL Events per opportunity].</li></ul>Conteggiati come opzioni, sono applicabili solo alle query evento e vengono rimossi per le query metriche.
* **[!UICONTROL Segments]**: i segmenti che desideri misurare. Ogni segmento selezionato raddoppia il numero delle serie di grafici e delle righe di tabella. Puoi includere fino a cinque segmenti.
* **[!UICONTROL Breakdown property]**: suddivide le serie dei grafici e le righe di tabella per i valori della proprietà selezionata. È supportata una singola proprietà di raggruppamento. Nella tabella vengono visualizzati i primi 20 valori e nel grafico è possibile visualizzare fino a dieci valori. Puoi nascondere o esporre una riga nel grafico attivando l’icona ![Show hide icon](../assets/hide-in-chart.png).

### Impostazioni del grafico

L’analisi della[!UICONTROL Trends] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Chart type]**: tipo di visualizzazione da usare. Le opzioni includono: linea, barre, barre sovrapposte e superfici sovrapposte.

### Sovrapposizioni

Aggiungi altri dati al grafico. Quando sul grafico sono visibili più serie, le sovrapposizioni vengono visualizzate solo al passaggio del mouse.

* **[!UICONTROL Anomaly detection]**: esegue [il rilevamento delle anomalie](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) nell’analisi con tendenze. I valori anomali vengono visualizzati sotto forma di punti su cui è possibile passare il puntatore per ottenere ulteriori informazioni.
* **[!UICONTROL Trendline overlay]**: aggiunge una linea di tendenza al grafico che aiuta a rappresentare un pattern più chiaro nei dati.
   * [!UICONTROL Linear]: crea una retta di regressione. Consigliata per dati lineari semplici che aumentano o diminuiscono a un tasso costante. Equazione: `y = a + b * x`
   * [!UICONTROL Logarithmic]: crea una curva di regressione. Consigliata per i dati che aumentano o diminuiscono rapidamente, quindi si livellano. Equazione: `y = a + b * log(x)`
   * [!UICONTROL Moving average]: crea una linea di tendenza uniforme in base a un insieme di medie. Nota anche come media continua, la media mobile utilizza un numero specifico di punti di dati precedenti (determinati dalla selezione), ne calcola la media e utilizza tale media come punto sulla linea. Gli esempi includono la media mobile di sette giorni o la media mobile di quattro settimane. Le opzioni disponibili per la media mobile dipendono dall’intervallo e dall’intervallo di date selezionati.

### Confronto temporale

{{apply-time-comparison}}


### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è costituita da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono: Oraria, Giornaliera, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere una granularità diversa, da cui dipende il numero di punti dati nel grafico e il numero di colonne nella tabella. Nella visualizzazione di un’analisi di tre giorni con granularità giornaliera, ad esempio, saranno presenti solo tre punti dati, mentre in quella di un’analisi di tre giorni con granularità oraria ne saranno presenti 72.
* **[!UICONTROL Date]**: la data di inizio e di fine. Per comodità, sono disponibili intervalli di date continui predefiniti e intervalli personalizzati salvati in precedenza; in alternativa, puoi utilizzare il selettore del calendario per scegliere un intervallo di date fisso.


<!--

## Example

See below for an example of the analysis.

![Trends compare](../assets/trends-compare.png)

-->