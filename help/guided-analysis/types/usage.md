---
title: Visualizzazione utilizzo
description: Misura il coinvolgimento degli utenti nel tempo.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Guided Analysis
keywords: analisi dei prodotti
source-git-commit: 170737214fea4dbd4d90d33ebf770920c8344fb1
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 2%

---

# [!UICONTROL Usage] view

Il **[!UICONTROL Usage]** fornisce informazioni utili sulle prestazioni del prodotto o sul comportamento degli utenti nel tempo. L’asse orizzontale di questo rapporto è un intervallo di tempo, mentre l’asse verticale misura gli eventi desiderati.

>[!VIDEO](https://video.tv.adobe.com/v/3421666/?learn=on)

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Valutare le prestazioni del prodotto**: le tendenze ti consentono di valutare le prestazioni complessive del prodotto in un determinato periodo di tempo. Analizzando metriche quali coinvolgimento degli utenti, tassi di adozione o di conversione, puoi verificare se le prestazioni del prodotto stanno migliorando, stagnando o diminuendo.
* **Adozione di funzioni**: le tendenze ti consentono di comprendere in che modo gli utenti adottano nuove funzioni o aggiornamenti che rilasci. È possibile determinare quali feature sono popolari e quali feature richiedono miglioramenti. Queste informazioni ti consentono di prendere decisioni basate sui dati sulle funzioni per dare priorità alle tue attività di sviluppo.
* **Comportamento dell’utente**: le tendenze possono fornire informazioni sul comportamento degli utenti nel tempo. Esaminando le azioni specifiche intraprese dagli utenti, è possibile identificare i pattern in cui gli utenti potrebbero abbandonarsi. Puoi combinare le informazioni provenienti da questa visualizzazione con [Attrito](friction.md) per ulteriori informazioni sul comportamento.
* **Test A/B e sperimentazione**: se esegui test A/B all’interno del prodotto, puoi utilizzare le Tendenze per determinare quali test hanno più successo nel tempo.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Events]**: gli eventi che desideri misurare. Ogni evento selezionato viene rappresentato come una serie di grafici e una riga di tabella. Puoi includere fino a cinque eventi.
* **[!UICONTROL People]**: i segmenti che desideri misurare. Ogni segmento selezionato raddoppia il numero delle serie del grafico e delle righe della tabella. Puoi includere fino a cinque segmenti.
* **[!UICONTROL Breakdown property]**: suddivide le serie del grafico e le righe della tabella in base ai valori della proprietà selezionata. È supportata una singola proprietà di suddivisione. Nella tabella vengono visualizzati i primi 20 valori e nel grafico è possibile visualizzare fino a dieci valori. È possibile nascondere o esporre una riga nel grafico attivando/disattivando ![Mostra icona Nascondi](../assets/hide-in-chart.png) icona.

## Impostazioni grafico

Il [!UICONTROL Usage] visualizza offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Metric]**: la metrica da misurare. Le opzioni includono Eventi, Sessioni, Utenti, Eventi per sessione ed Eventi per utente.
* **[!UICONTROL Chart type]**: tipo di visualizzazione che desideri utilizzare. Le opzioni disponibili sono Linea, Barre, Barre sovrapposte e Area sovrapposta.

## Sovrapposizioni

Aggiungi dati aggiuntivi al grafico. Quando sul grafico sono visibili più serie, le sovrapposizioni vengono visualizzate solo al passaggio del mouse.

* **[!UICONTROL Anomaly detection]**: Esecuzioni [rilevamento delle anomalie](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) sull&#39;analisi delle tendenze. I valori anomali vengono visualizzati sotto forma di punti su cui è possibile passare il cursore del mouse per ottenere ulteriori informazioni.
* **[!UICONTROL Trendline overlay]**: aggiunge al grafico una linea di tendenza che consente di rappresentare un pattern più chiaro nei dati.
   * [!UICONTROL Linear]: crea una linea di regressione retta. Consigliato per dati lineari semplici che aumentano o diminuiscono a una velocità costante. Equazione: `y = a + b * x`
   * [!UICONTROL Logarithmic]: crea una linea di regressione curva. Consigliato per i dati che aumentano o diminuiscono rapidamente, quindi diventano di più livello. Equazione: `y = a + b * log(x)`
   * [!UICONTROL Moving average]: Crea una linea di tendenza uniforme in base a un insieme di medie. Anche nota come media continua, la media mobile utilizza un numero specifico di punti di dati precedenti (determinati dalla selezione), ne calcola la media e utilizza tale media come punto sulla linea. Alcuni esempi includono la media mobile di sette giorni o di quattro settimane. Le opzioni disponibili per la media mobile dipendono dall’intervallo e dall’intervallo di date selezionati.

## Applica confronto temporale

{{apply-time-comparison}}

![Confronto tempo di utilizzo](../assets/usage-compare.png)

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono Orario, Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi che influiscono sul numero di coordinate nel grafico e sul numero di colonne nella tabella. Ad esempio, la visualizzazione di un’analisi con granularità giornaliera della durata di tre giorni mostrerebbe solo tre punti di dati, mentre un’analisi con granularità oraria della durata di tre giorni mostrerebbe 72 punti di dati.
* **[!UICONTROL Date]**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.
