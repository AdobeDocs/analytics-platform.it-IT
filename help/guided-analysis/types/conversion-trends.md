---
title: Analisi delle tendenze di conversione
description: Tieni traccia delle modifiche del tasso di conversione nel tempo.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Analisi [!UICONTROL Conversion trends] {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_conversiontrends_button"
>title="Tendenze di conversione"
>abstract="Tieni traccia delle modifiche nei tassi di conversione nel tempo."

<!-- markdownlint-enable MD034 -->


L&#39;analisi delle ![tendenze di conversione](/help/assets/icons/ConversionTrends.svg) **[!UICONTROL Conversion trends]** fornisce una visualizzazione delle tendenze dei tassi di conversione nel tempo. L’asse orizzontale è un intervallo di tempo, mentre l’asse verticale rappresenta il tasso di conversione.


>[!VIDEO](https://video.tv.adobe.com/v/3421662/?learn=on)


## Casi d’uso

I casi di utilizzo per questa analisi includono:

* **Tracciare gli sforzi di ottimizzazione**: dopo aver identificato i colli di bottiglia chiave che si desidera migliorare utilizzando l&#39;analisi [Funnel](funnel.md), è possibile utilizzare questa analisi per tenere traccia di come tali ottimizzazioni influiscono sul tasso di conversione nel tempo.
* **Valutazione test A/B**: valutare l&#39;efficacia dei test A/B o degli esperimenti condotti nel contesto di un funnel. Confrontando i tassi di conversione tra diverse varianti, puoi facilmente determinare quali test forniscono tassi di conversione più elevati, per cui puoi decidere in base ai dati su quali varianti implementare in modo permanente.
* **Valutazione delle campagne nel tempo**: misura l’efficacia delle campagne di marketing nel tempo. Puoi creare un segmento che si concentra sugli utenti che hanno toccato una determinata campagna e confrontare i loro tassi di conversione con altre campagne. Puoi anche confrontare i tassi di conversione correnti con campagne simili eseguite in passato.

## Interfaccia

Per una panoramica dell&#39;interfaccia di analisi guidata, vedere [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL View]**: passa da questa analisi a [Funnel](funnel.md).
* **[!UICONTROL Steps]**: i punti di contatto dell&#39;evento di cui si desidera tenere traccia. Ogni barra del grafico rappresenta un passo. Puoi includere fino a dieci passaggi.
* **[!UICONTROL Counted as]**: metodo di conteggio da applicare agli eventi selezionati. Le opzioni includono [!UICONTROL Users] e [!UICONTROL Sessions].
* **[!UICONTROL Segments]**: i segmenti in cui si desidera confrontare il funnel. Ogni segmento selezionato suddivide ogni passaggio in più barre. Ogni colore rappresenta un segmento diverso. Puoi includere fino a tre segmenti.

### Impostazioni grafico

L&#39;analisi [!UICONTROL Conversion trends] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Chart type]**: tipo di visualizzazione che si desidera utilizzare. Le opzioni includono [!UICONTROL Line].
* **[!UICONTROL Conversion from]**: determina il calcolo della percentuale da un passaggio all&#39;altro. Le opzioni includono il calcolo della conversione da [!UICONTROL First step] o [!UICONTROL Previous step].

>[!NOTE]
>
>La colonna **Media** nella tabella di analisi delle tendenze di conversione è diversa dalla colonna **Totale** nella tabella [Analisi funnel](funnel.md). La prima rappresenta una media delle colonne dell’intervallo (ad esempio, media dei tassi di conversione giornalieri), mentre la seconda rappresenta un calcolo aggregato per l’intero intervallo di date.

### Confronto temporale

{{apply-time-comparison}}


### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono Orario, Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi, che influiscono sul numero di coordinate nel grafico e sul numero di colonne nella tabella. Ad esempio, la visualizzazione di un’analisi con granularità giornaliera della durata di tre giorni mostrerebbe solo tre punti di dati, mentre un’analisi con granularità oraria della durata di tre giorni mostrerebbe 72 punti di dati.
* **[!UICONTROL Date]**: la data di inizio e di fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
