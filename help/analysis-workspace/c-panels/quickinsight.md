---
description: Quick Insights è uno strumento per i nuovi utenti di Workspace che li guida nella creazione di tabelle e visualizzazioni di dati
title: Pannello Quick Insights
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
role: User
source-git-commit: b14bc43a0cdf4901c5df171a116943beb2124991
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 87%

---

# Pannello Quick Insights {#quick-insights-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_quickinsights_button"
>title="Quick Insights"
>abstract="Crea un pannello per generare rapidamente una tabella a forma libera e una relativa visualizzazione per analizzare e individuare più rapidamente le informazioni."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo descrive il pannello Quick Insights in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Consulta [Pannello Quick Insights](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/panels/quickinsight) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]


[!UICONTROL Quick Insights] fornisce indicazioni ai non analisti e ai nuovi utenti di [!UICONTROL Analysis Workspace] affinché scoprano come rispondere alle domande aziendali in modo rapido e semplice. È anche un ottimo strumento per gli utenti avanzati che desiderano rispondere rapidamente a una semplice domanda senza dover creare personalmente una tabella.

Quando inizi a utilizzare [!UICONTROL Analysis Workspace], potresti chiederti:

* quali visualizzazioni sarebbero più utili,
* quali dimensioni e metriche potrebbero facilitare le informazioni approfondite,
* dove trascinare gli elementi,
* dove creare un segmento,
* e altro ancora.

Per risolvere queste domande, [!UICONTROL Quick insights] sfrutta un algoritmo che ti presenta le dimensioni, le metriche, i segmenti e gli intervalli di date più comuni utilizzati dalla tua azienda. Questo algoritmo si basa sull’utilizzo dei componenti dei dati in [!UICONTROL Analysis Workspace] da parte della tua azienda. Vedrai infatti dimensioni, metriche e segmenti con tag [!UICONTROL POPULAR] nell&#39;elenco a discesa, come mostrato di seguito:

![Pannello Quick Insights.](assets/popular-tag.png)

[!UICONTROL Quick Insights] ti aiuta a:

* Creare correttamente una tabella di dati e una relativa visualizzazione in [!UICONTROL Analysis Workspace].
* Imparare la terminologia e il vocabolario dei componenti ed elementi di base di [!UICONTROL Analysis Workspace].
* Effettuare semplici raggruppamenti di dimensioni, aggiungere metriche multiple o confrontare facilmente segmenti all’interno di una [!UICONTROL Freeform table].
* Modificare o provare vari tipi di visualizzazione per trovare lo strumento di ricerca per la tua analisi in modo rapido e intuitivo.

## Terminologia chiave di base

Di seguito sono riportati alcuni dei termini di base con cui è necessario che tu abbia familiarità. Ogni tabella di dati è composta da 2 o più blocchi (componenti) utilizzati per spiegare la storia dei dati.

| Blocco predefinito (componente) | Definizione |
|---|---|
| **[!UICONTROL Dimension]** | Le dimensioni sono descrizioni o caratteristiche dei dati di metriche che possono essere visualizzate, raggruppate e confrontate in un progetto. Sono valori non numerici e date raggruppati in elementi dimensionali. Ad esempio, un *browser* o una *pagina* è una dimensione. |
| **[!UICONTROL Dimension item]** | Gli elementi dimensionali sono valori singoli per una dimensione. Ad esempio, gli elementi dimensionali per la dimensione del browser sarebbero *Chrome*, *Firefox*, *Edge* oppure altri. |
| [!UICONTROL Metric] | Le metriche corrispondono a informazioni quantitative sull’attività della persona come visualizzazioni, click-through, ricaricamenti delle pagine, tempo medio trascorso, unità, ordini, ricavi e così via. |
| **[!UICONTROL Visualization]** | Workspace offre [diverse visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) per creare rappresentazioni visive dei dati. Ad esempio grafici a barre, grafici ad anello, istogrammi, grafici a linee, mappe, grafici di dispersione e altri. |
| **[!UICONTROL Dimension Breakdown]** | Un raggruppamento di dimensioni è un modo per raggruppare una dimensione secondo altre dimensioni. Ad esempio, puoi raggruppare gli Stati Uniti per dispositivi mobili per ottenere le visite da parte di dispositivi mobili per stato. Oppure puoi raggruppare i dispositivi mobili per tipo di dispositivo mobile, per aree geografiche, per campagne interne e altro ancora. |
| **[!UICONTROL Segment]** | I segmenti ti consentono di identificare sottoinsiemi di persone in base a caratteristiche o interazioni con siti web. Ad esempio, puoi creare [!UICONTROL People] segmenti in base a <li>attributi: tipo di browser, dispositivo, numero di visite, paese, genere o</li><li>interazioni: campagne, ricerca di parole chiave, motore di ricerca o</li><li>uscite ed entrate: persone da Facebook, una pagina di destinazione definita, un dominio di riferimento o</li><li> variabili personalizzate: campo modulo, categorie definite, ID cliente. |

## Utilizzo

Per usare un pannello **[!UICONTROL Quick insights]**:

1. Crea un pannello **[!UICONTROL Quick insights]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Quando utilizzi un pannello **[!UICONTROL Quick insights]** per la prima volta, potrebbe essere utile consultare il breve [!UICONTROL Intro tutorial] che insegna alcune delle nozioni di base. Seleziona ![HelpOutline](/help/assets/icons/HelpOutline.svg) accanto al titolo del pannello Quick Insights e seleziona **[!UICONTROL Intro tutorial]** dal popup.

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.


### Input del pannello

Seleziona i blocchi:

* **[!UICONTROL Analyze]**: specifica una dimensione (arancione)
* **[!UICONTROL by]**: specifica una metrica (verde)
* **[!UICONTROL segment by]** - specifica un segmento (blu)
* **[!UICONTROL on]**: specifica un intervallo di date (viola).

Per il corretto funzionamento della visualizzazione, devi selezionare almeno una dimensione e una metrica.



Puoi specificare i blocchi in tre modi:

* Trascina i componenti dal pannello a sinistra.
* Inizia a digitare in uno dei campi del blocco. Quando viene trovato un input, il campo del blocco viene compilato automaticamente con i valori possibili.
* Specifica un elenco a discesa del blocco (ad esempio `Country` in **[!UICONTROL Analyze]**) e cerca nell’elenco dei valori possibili (utilizzando ![ChevronRight](/help/assets/icons/ChevronRight.svg)) il valore da utilizzare (ad esempio **[!UICONTROL Country code]**).

Seleziona **[!UICONTROL Clear]** per cancellare tutti i campi di input.


### Output del pannello

1. Dopo aver aggiunto almeno una dimensione e una metrica, puoi visualizzare i risultati.

   ![Tabella a forma libera che mostra la dimensione in verticale e la metrica in orizzontale.](assets/quick-insights-output.png)

   * Tabella a forma libera con dimensione (Codice paese) e metrica (Sessioni), segmentata per sessioni web per gli ultimi 12 mesi.

   * Una visualizzazione associata, in questo caso un [grafico a barre](/help/analysis-workspace/visualizations/bar.md). La visualizzazione generata si basa sul tipo di dati che hai aggiunto alla tabella. Per impostazione predefinita, qualsiasi dato basato sul tempo (ad esempio [!UICONTROL Sessions] al giorno/mese) viene visualizzato in un grafico a [!UICONTROL Line]. Per impostazione predefinita, qualsiasi dato non basato sul tempo (ad esempio [!UICONTROL Sessions] per [!UICONTROL Device]) viene visualizzato in un grafico a [!UICONTROL Bar]. Puoi modificare il tipo di visualizzazione facendo clic sulla freccia dell’elenco a discesa accanto al tipo di visualizzazione.

1. Prova ad aggiungere altri miglioramenti come descritto di seguito in [Ulteriori suggerimenti](#more-tips)

1. Puoi salvare il progetto utilizzando **[!UICONTROL Project > Save]**.

## Ulteriori suggerimenti

Altri utili pop-up di suggerimenti in [!UICONTROL Quick Insights Builder], alcuni dipendono dall’ultima azione eseguita.

* Innanzitutto, potresti voler completare il tutorial **[!UICONTROL More tips]**. Questo tutorial viene visualizzato 24 ore dopo la creazione di un progetto con almeno una dimensione e una metrica. Seleziona ![HelpOutline](/help/assets/icons/HelpOutline.svg) accanto al titolo del pannello Quick Insights (Insight rapidi) e seleziona **[!UICONTROL More tips]** dal riquadro a comparsa.

  ![Notifica nel pannello Quick Insights visualizzata dopo aver selezionato l’icona Aiuto.](assets/qibuilder4.png)

* Puoi analizzare più dimensioni e metriche, combinare o confrontare segmenti e specificare un intervallo di date:

  ![Generatore di risultati di insight rapidi](assets/qibuilder-result.png)

   * **[!UICONTROL Analyze]** **[!UICONTROL Broken-Down by]** dimensioni: puoi utilizzare fino a 3 livelli di raggruppamenti delle dimensioni per esaminare i dati che ti servono. Consulta ➊, ➋ e ➌.

   * Aggiungi altre metriche **[!UICONTROL by]**: puoi aggiungere fino a 2 ulteriori metriche. Consulta ➍ e ➎.

   * **[!UICONTROL segment by]**: è possibile aggiungere fino a 2 ulteriori segmenti. Ad esempio, aggiungi Prenotazioni come segmento e combina quel segmento con i segmenti Prenotazioni frequenti e Volantini per la prima volta che confronti. Consulta ➏, ➐ e ➑.

   * on: puoi specificare l’intervallo di date. Consulta ➒.

## Limitazioni note

Se tenti di apportare modifiche direttamente nella tabella, il pannello [!UICONTROL Quick Insights] potrebbe non essere più sincronizzato. Seleziona **[!UICONTROL Resync Builder]** in alto a destra nel pannello per ripristinare le impostazioni [!UICONTROL Quick Insights] precedenti.

Prima di aggiungere qualsiasi elemento direttamente alla tabella, viene visualizzato un avviso:

![Avviso dell’opzione Resync Builder.](assets/qibuilder-outofsync.png)

In caso contrario, la creazione diretta farà sì che la tabella si comporti come una tabella a forma libera tradizionale, senza le funzioni utili per i nuovi utenti.


>[!MORELIKETHIS]
>
>[Creare un pannello](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>