---
description: Quick Insights è uno strumento per i nuovi utenti di Workspace che li guida nella creazione di tabelle e visualizzazioni di dati
title: Pannello Quick Insights
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 28%

---

# Pannello Quick Insights {#quick-insights-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_quickinsights_button"
>title="Quick Insights"
>abstract="Crea un pannello per creare rapidamente una tabella a forma libera e una relativa visualizzazione per analizzare e individuare più rapidamente le informazioni approfondite."

<!-- markdownlint-enable MD034 -->


[!UICONTROL Quick Insights] fornisce indicazioni ai non analisti e ai nuovi utenti di [!UICONTROL Analysis Workspace] affinché scoprano come rispondere alle domande aziendali in modo rapido e semplice. È anche un ottimo strumento per gli utenti avanzati che desiderano rispondere rapidamente a una semplice domanda senza dover creare personalmente una tabella.

Quando si inizia a utilizzare [!UICONTROL Analysis Workspace], ci si potrebbe chiedere:

* quali visualizzazioni sarebbero più utili,
* quali dimensioni e metriche potrebbero facilitare gli approfondimenti,
* dove trascinare gli elementi,
* dove creare un filtro,
* e altro ancora.

Per risolvere queste domande, [!UICONTROL Quick insights] sfrutta un algoritmo che ti presenta le dimensioni, le metriche, i filtri e gli intervalli di date più comuni utilizzati dalla tua azienda. Questo algoritmo si basa sull&#39;utilizzo dei componenti dati in [!UICONTROL Analysis Workspace] da parte della tua azienda. Vedrai infatti dimensioni, metriche e filtri con tag [!UICONTROL POPULAR] nell&#39;elenco a discesa, come mostrato di seguito:

![Pannello Quick Insights.](assets/popular-tag.png)

[!UICONTROL Quick Insights] ti aiuta a:

* Creare correttamente una tabella di dati e una relativa visualizzazione in [!UICONTROL Analysis Workspace].
* Imparare la terminologia e il vocabolario dei componenti ed elementi di base di [!UICONTROL Analysis Workspace].
* Effettuare semplici raggruppamenti di dimensioni, aggiungere metriche multiple o confrontare facilmente filtri all’interno di una [!UICONTROL Freeform table].
* Modificare o provare vari tipi di visualizzazione per trovare lo strumento di ricerca per la tua analisi in modo rapido e intuitivo.

## Terminologia chiave di base

Di seguito sono riportati alcuni dei termini di base che è necessario conoscere. Ogni tabella di dati è costituita da 2 o più blocchi (componenti) utilizzati per spiegare la storia dei dati.

| Blocco predefinito (componente) | Definizione |
|---|---|
| **[!UICONTROL Dimension]** | Le dimensioni sono descrizioni o caratteristiche dei dati di metriche che possono essere visualizzate, raggruppate e confrontate in un progetto. Sono valori non numerici e date raggruppati in elementi dimensionali. Ad esempio, *browser* o *pagina* è una dimensione. |
| **[!UICONTROL Dimension item]** | Gli elementi dimensionali sono valori singoli per una dimensione. Ad esempio, gli elementi dimensionali per la dimensione del browser sarebbero *Chrome*, *Firefox*, *Edge* o altri. |
| [!UICONTROL Metric] | Le metriche corrispondono a informazioni quantitative sull’attività della persona come visualizzazioni, click-through, ricaricamenti delle pagine, tempo medio trascorso, unità, ordini, ricavi e così via. |
| **[!UICONTROL Visualization]** | Workspace offre [diverse visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) per creare rappresentazioni visive dei dati. Ad esempio grafici a barre, grafici ad anello, istogrammi, grafici a linee, mappe, grafici a dispersione e altri. |
| **[!UICONTROL Dimension Breakdown]** | Un raggruppamento di dimensioni è un modo per raggruppare una dimensione per altre dimensioni. Ad esempio, puoi suddividere gli Stati Uniti per Dispositivi mobili per ottenere le visite dei dispositivi mobili per stato. Oppure puoi suddividere i dispositivi mobili per tipo di dispositivo, per regione, per campagne interne e altro ancora. |
| **[!UICONTROL Filter]** | I filtri ti consentono di identificare sottoinsiemi di persone in base a caratteristiche o interazioni con siti web. Ad esempio, puoi creare [!UICONTROL People] filtri in base a <li>attributi: tipo di browser, dispositivo, numero di visite, paese, genere o</li><li>interazioni: campagne, ricerca di parole chiave, motore di ricerca o</li><li>uscite e entrate: persone da Facebook, una pagina di destinazione definita, un dominio di riferimento o</li><li> variabili personalizzate: campo modulo, categorie definite, ID cliente. |

## Seleziona

Per utilizzare un pannello **[!UICONTROL Quick insights]**:

1. Crea un pannello **[!UICONTROL Quick insights]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Quando utilizzi un pannello **[!UICONTROL Quick insights]** per la prima volta, potrebbe essere utile esaminare il breve [!UICONTROL Intro tutorial] che illustra alcune delle nozioni di base. Seleziona ![HelpOutline](/help/assets/icons/HelpOutline.svg) accanto al titolo del pannello Quick Insights e seleziona **[!UICONTROL Intro tutorial]** dal popup.

1. Specifica [input](#panel-input) per il pannello.

1. Osserva [output](#panel-output) per il pannello.


### Input del pannello

Seleziona i blocchi predefiniti:

* **[!UICONTROL Analyze]** - specifica una dimensione (arancione)
* **[!UICONTROL by]** - specifica una metrica (verde)
* **[!UICONTROL filter by]** - specificare un filtro (blu)
* **[!UICONTROL on]** - specificare un intervallo di dati (viola).

Per il corretto funzionamento della visualizzazione, devi selezionare almeno una dimensione e una metrica.



È possibile specificare i blocchi predefiniti in tre modi:

* Trascina i componenti dal pannello a sinistra.
* Inizia a digitare in uno dei campi del blocco predefinito. Quando viene trovato un input, il campo blocco predefinito viene compilato automaticamente con i valori possibili.
* Specificare un elenco a discesa del blocco predefinito (ad esempio `Country` in **[!UICONTROL Analyze]**) e cercare nell&#39;elenco dei valori possibili (utilizzando ![ChevronRight](/help/assets/icons/ChevronRight.svg)) il valore che si desidera utilizzare (ad esempio **[!UICONTROL Country code]**).

Selezionare **[!UICONTROL Clear]** per cancellare tutti i campi di input.


### Output del pannello

1. Dopo aver aggiunto almeno una dimensione e una metrica, puoi visualizzare i risultati.

   ![Tabella a forma libera che mostra la dimensione in verticale e la metrica in orizzontale.](assets/quick-insights-output.png)

   * Tabella a forma libera con dimensione (Codice paese) e metrica (Sessioni), filtrata per sessioni web per gli ultimi 12 mesi.

   * Una visualizzazione associata, in questo caso un [grafico a barre](/help/analysis-workspace/visualizations/bar.md). La visualizzazione generata si basa sul tipo di dati che hai aggiunto alla tabella. Per impostazione predefinita, qualsiasi dato basato sul tempo (ad esempio [!UICONTROL Sessions] al giorno/mese) viene visualizzato in un grafico a [!UICONTROL Line]. Per impostazione predefinita, qualsiasi dato non basato sul tempo (ad esempio [!UICONTROL Sessions] per [!UICONTROL Device]) viene visualizzato in un grafico a [!UICONTROL Bar]. Puoi modificare il tipo di visualizzazione facendo clic sulla freccia dell’elenco a discesa accanto al tipo di visualizzazione.

1. Prova ad aggiungere altri miglioramenti come descritto di seguito in [Altri suggerimenti](#more-tips)

1. È possibile salvare il progetto utilizzando **[!UICONTROL Project > Save]**.

## Ulteriori suggerimenti

Altri utili suggerimenti vengono visualizzati in [!UICONTROL Quick Insights Builder], alcuni a seconda dell&#39;ultima azione.

* Innanzitutto, potrebbe essere utile completare l&#39;esercitazione di **[!UICONTROL More tips]**. Questo tutorial viene visualizzato 24 ore dopo la creazione di un progetto con almeno una dimensione e una metrica. Seleziona ![HelpOutline](/help/assets/icons/HelpOutline.svg) accanto al titolo del pannello Quick Insights e seleziona **[!UICONTROL More tips]** dal popup.

  ![La notifica del pannello Quick Insights viene visualizzata dopo aver selezionato l&#39;icona della Guida.](assets/qibuilder4.png)

* Puoi analizzare più dimensioni e metriche, combinare o confrontare filtri e specificare un intervallo di dati:

  ![Risultato Generatore Quick Insights](assets/qibuilder-result.png)

   * **[!UICONTROL Analyze]** dimensione **[!UICONTROL Broken-Down by]**: è possibile utilizzare fino a 3 livelli di raggruppamenti sulle dimensioni per eseguire il drill-down dei dati effettivamente necessari. Consulta le sezioni, E.

   * Aggiungi altre metriche **[!UICONTROL by]**: è possibile aggiungere fino a 2 ulteriori metriche. Consulta la sezione su come e ➎.

   * **[!UICONTROL filter by]**: è possibile aggiungere fino a 2 ulteriori filtri. Ad esempio, aggiungi Prenotazioni come filtro e combina tale filtro con i filtri Prenotazioni frequenti e Volantini per la prima volta che confronti. Consulta ➏, ➐ e ➑.

   * on: è possibile specificare l’intervallo di dati. Consulta ➒.

## Limitazioni note

Se si tenta di modificare direttamente all&#39;interno della tabella, il pannello [!UICONTROL Quick Insights] potrebbe non essere sincronizzato. Seleziona **[!UICONTROL Resync Builder]** in alto a destra nel pannello per ripristinarlo alle impostazioni [!UICONTROL Quick Insights] precedenti.

Viene visualizzato un avviso prima di aggiungere qualsiasi elemento direttamente alla tabella:

![Avviso dell’opzione Resync Builder.](assets/qibuilder-outofsync.png)

In caso contrario, la creazione diretta fa sì che la tabella si comporti come una tabella a forma libera tradizionale, senza le funzioni utili per i nuovi utenti.


>[!MORELIKETHIS]
>
>[Crea un pannello](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>