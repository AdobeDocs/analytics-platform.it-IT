---
title: Analisi delle tendenze di conversione
description: Tieni traccia delle modifiche del tasso di conversione nel tempo.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 100%

---

# [!UICONTROL Conversion trends] analisi {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_conversiontrends_button"
>title="Tendenze di conversione"
>abstract="Tieni traccia delle modifiche nei tassi di conversione nel tempo."

<!-- markdownlint-enable MD034 -->


L’analisi delle ![tendenze di conversione](/help/assets/icons/ConversionTrends.svg) **[!UICONTROL Conversion trends]** fornisce una visualizzazione con le tendenze dei tassi di conversione nel tempo. L’asse orizzontale è un intervallo di tempo, mentre l’asse verticale rappresenta il tasso di conversione.


>[!VIDEO](https://video.tv.adobe.com/v/3423488/?captions=ita&quality=12&learn=on)


## Casi d’uso

I casi d’uso per questa analisi includono:

* **Tracciare le attività di ottimizzazione**: dopo aver identificato i colli di bottiglia chiave che desideri migliorare tramite l’analisi [Funnel](funnel.md), è possibile utilizzare questa analisi per tenere traccia dell’impatto di tali ottimizzazioni sul tasso di conversione nel tempo.
* **Valutazione test A/B**: valuta l’efficacia dei test A/B o degli esperimenti condotti nel contesto di un funnel. Confrontando i tassi di conversione tra diverse varianti, puoi facilmente determinare quali test forniscono tassi di conversione più elevati, per cui puoi decidere in base ai dati quali varianti implementare in modo permanente.
* **Valutazione della campagna nel tempo**: misura l’efficacia delle campagne di marketing nel tempo. Puoi creare un segmento incentrato sugli utenti che sono entrati in contatto con una determinata campagna e confrontare i loro tassi di conversione con altre campagne. Puoi anche confrontare i tassi di conversione correnti con campagne simili eseguite in passato.

## Interfaccia

Per una panoramica dell’interfaccia dell’analisi guidata, consulta [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL View]**: passa da questa analisi a [Funnel](funnel.md).
* **[!UICONTROL Steps]**: i punti di contatto dell’evento di cui desideri tenere traccia. Ogni barra del grafico rappresenta un passaggio. Puoi includere fino a dieci passaggi.
* **[!UICONTROL Counted as]**: il metodo di conteggio che desideri applicare agli eventi selezionati. Le opzioni includono [!UICONTROL Users] e [!UICONTROL Sessions].
* **[!UICONTROL Segments]**: i segmenti che desideri confrontare nel funnel. Ogni segmento selezionato suddivide ogni passaggio in più barre. Ogni colore rappresenta un segmento diverso. Puoi includere fino a tre segmenti.

### Impostazioni del grafico

L’analisi della[!UICONTROL Conversion trends] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Chart type]**: il tipo di visualizzazione che desideri utilizzare. Le opzioni includono [!UICONTROL Line].
* **[!UICONTROL Conversion from]**: determina il calcolo della percentuale da un passaggio all’altro. Le opzioni includono il calcolo della conversione da [!UICONTROL First step] o [!UICONTROL Previous step].

>[!NOTE]
>
>La colonna **Media** nella tabella di analisi delle tendenze di conversione è diversa dalla colonna **Totale** nella tabella [Analisi funnel](funnel.md). La prima rappresenta una media delle colonne dell’intervallo (ad esempio, media dei tassi di conversione giornalieri), mentre la seconda rappresenta un calcolo aggregato per l’intero intervallo di date.

### Confronto temporale

{{apply-time-comparison}}


### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è costituita da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono: Oraria, Giornaliera, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere una granularità diversa, da cui dipende il numero di punti dati nel grafico e il numero di colonne nella tabella. Nella visualizzazione di un’analisi di tre giorni con granularità giornaliera, ad esempio, saranno presenti solo tre punti dati, mentre in quella di un’analisi di tre giorni con granularità oraria ne saranno presenti 72.
* **[!UICONTROL Date]**: la data di inizio e di fine. Per comodità, sono disponibili intervalli di date continui predefiniti e intervalli personalizzati salvati in precedenza; in alternativa, puoi utilizzare il selettore del calendario per scegliere un intervallo di date fisso.

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
