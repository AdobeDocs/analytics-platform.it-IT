---
description: Quick Insights è uno strumento per i nuovi utenti di Workspace che li guida nella creazione di tabelle e visualizzazioni di dati
title: Pannello Quick Insights
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
source-git-commit: 702d03b95b6689e1441fbdd8b2ef3a5a3fcfbad0
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 100%

---

# Pannello Quick Insights

[!UICONTROL Quick Insights] fornisce indicazioni ai non analisti e ai nuovi utenti di [!UICONTROL Analysis Workspace] affinché scoprano come rispondere alle domande aziendali in modo rapido e semplice. È anche un ottimo strumento per gli utenti avanzati che desiderano rispondere rapidamente a una semplice domanda senza dover creare personalmente una tabella.

Quando inizi a utilizzare questo [!UICONTROL Analysis Workspace], potresti chiederti quali visualizzazioni sarebbero più utili, quali dimensioni e metriche potrebbero semplificare gli approfondimenti, dove trascinare e rilasciare elementi, dove creare un filtro, ecc.

Per aiutarti con questo, e in base all’utilizzo dei componenti dati da parte della tua azienda in [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] sfrutta un algoritmo che ti mostrerà le dimensioni, le metriche, i filtri e gli intervalli di date più comuni utilizzati dalla tua azienda. Vedrai infatti dimensioni, metriche e filtri taggati come [!UICONTROL Popular] nell’elenco a discesa, come mostrato di seguito:

![](assets/popular-tag.png)

[!UICONTROL Quick Insights] ti aiuta a:

* Creare correttamente una tabella di dati e una relativa visualizzazione in [!UICONTROL Analysis Workspace].
* Imparare la terminologia e il vocabolario dei componenti ed elementi di base di [!UICONTROL Analysis Workspace].
* Effettuare semplici raggruppamenti di dimensioni, aggiungere metriche multiple o confrontare facilmente filtri all’interno di una [!UICONTROL Freeform table].
* Modificare o provare vari tipi di visualizzazione per trovare lo strumento di ricerca per la tua analisi in modo rapido e intuitivo.

## Terminologia chiave di base

Di seguito sono riportati alcuni dei termini di base con cui è necessario tu abbia familiarità. Ogni tabella di dati è composta da 2 o più blocchi (componenti) utilizzati per spiegare la storia dei dati.

| Blocco predefinito (componente) | Definizione |
|---|---|
| [!UICONTROL Dimension] | Le dimensioni sono descrizioni o caratteristiche dei dati di metriche che possono essere visualizzate, raggruppate e confrontate in un progetto. Sono valori non numerici e date raggruppati in elementi dimensionali. Ad esempio, “browser” o “pagina” sono dimensioni. |
| [!UICONTROL Dimension item] | Gli elementi dimensionali sono valori singoli per una dimensione. Ad esempio, gli elementi dimensionali per la dimensione del browser sarebbero “Chrome”, “Firefox”, “Edge”, ecc. |
| [!UICONTROL Metric] | Le metriche corrispondono a informazioni quantitative sull’attività del visitatore come visualizzazioni, click-through, ricaricamenti delle pagine, tempo medio trascorso, unità, ordini, ricavi e così via. |
| [!UICONTROL Visualization] | Workspace offre [diverse visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) per creare rappresentazioni visive dei dati, ad esempio grafici a barre, grafici ad anello, istogrammi, grafici a linee, mappe, grafici a dispersione e altri. |
| [!UICONTROL Dimension Breakdown] | Un raggruppamento di dimensioni è un modo per raggruppare letteralmente una dimensione secondo altre dimensioni. Nel nostro esempio, potresti raggruppare gli Stati Uniti per dispositivi mobili per ottenere le visite dei dispositivi mobili per stato, oppure potresti raggruppare i dispositivi mobili per tipo di dispositivo mobile, per regioni, per campagne interne, ecc. |
| [!UICONTROL filter] | I filtri ti consentono di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni con siti web. Ad esempio, puoi creare filtri [!UICONTROL Visitor] in base agli attributi (tipo di browser, dispositivo, numero di visite, paese, genere), in base alle interazioni (campagne, ricerca di parole chiave, motore di ricerca), in base a uscite e entrate (visitatori da Facebook, una pagina di destinazione definita, un dominio di riferimento) o in base a variabili personalizzate (campo modulo, categorie definite, ID cliente). |

## Introduzione a Quick Insights

1. Effettua l’accesso ad Customer Journey Analytics utilizzando le credenziali che ti sono state fornite.
1. Vai su [!UICONTROL Workspace], fai clic su **[!UICONTROL Create New Project]** e quindi su **[!UICONTROL Quick Insights]**. Puoi accedere a questo pannello anche dal menu **[!UICONTROL Panel]** nella barra a sinistra.

   ![](assets/qibuilder.png)

   ![](assets/qi-panel.png)

1. La prima volta, segui il breve tutorial che illustra alcune delle nozioni di base di [!UICONTROL Quick Insights panel]. Oppure, fai clic per **[!UICONTROL Skip Tutorial]**.
1. Seleziona i blocchi predefiniti (noti anche come componenti): dimensioni (arancione), metriche (verde), filtri (blu) o intervalli di date (viola). Devi selezionare almeno una dimensione e una metrica affinché una tabella possa essere generata automaticamente.

   ![](assets/qibuilder2.png)

   Sono disponibili tre modi per selezionare i blocchi predefiniti:
   * Trascinali e rilasciali dalla barra a sinistra.
   * Se sai cosa stai cercando, inizia a digitare e [!UICONTROL Quick Insights] riempirà gli spazi vuoti.
   * Fai clic sull’elenco a discesa ed cerca nell’elenco.

1. Dopo aver aggiunto almeno una dimensione e una metrica, verrà creato quanto segue:

   * Una tabella a forma libera con la dimensione (in questo caso US States) in verticale e la metrica (in questo caso Visits) in orizzontale nella parte superiore. Osserva questa tabella:

   ![](assets/qibuilder3.png)

   * Una visualizzazione associata, in questo caso un [grafico a barre](/help/analysis-workspace/visualizations/bar.md). La visualizzazione generata si basa sul tipo di dati che hai aggiunto alla tabella. Per impostazione predefinita, qualsiasi dato basato sul tempo (ad esempio [!UICONTROL Visits] al giorno/mese) viene visualizzato in un grafico a [!UICONTROL Line]. Per impostazione predefinita, qualsiasi dato non basato sul tempo (ad esempio [!UICONTROL Visits] per [!UICONTROL Device]) viene visualizzato in un grafico a [!UICONTROL Bar]. Puoi modificare il tipo di visualizzazione facendo clic sulla freccia dell’elenco a discesa accanto al tipo di visualizzazione.


1. Per eseguire un drill-down delle dimensioni e vedere gli elementi dimensionali, fai clic sulla freccia rivolta a destra > accanto alla dimensione (facoltativo).

1. Prova ad aggiungere altri miglioramenti come descritto di seguito in “Ulteriori suggerimenti”.

1. Salva il progetto facendo clic su **[!UICONTROL Project > Save]**.

## Ulteriori suggerimenti

Altri utili suggerimenti compariranno nel pannello [!UICONTROL Quick Insights Builder], alcuni a seconda dell’ultima azione.

* Innanzitutto, completa il tutorial **[!UICONTROL More tips]**: puoi accedervi tramite l’icona di aiuto (?) accanto al titolo [!UICONTROL Quick Insights]. Questo tutorial viene visualizzato 24 ore dopo la creazione di un progetto con almeno una dimensione e una metrica.

   ![](assets/qibuilder4.png)

* **Raggruppamento per**: puoi utilizzare fino a 3 livelli di raggruppamenti sulle dimensioni per eseguire un drill-down dei dati effettivamente necessari.

   ![](assets/qibuilder5.png)

* **Aggiungi altre metriche**: puoi aggiungere fino a 2 ulteriori metriche utilizzando l’operatore AND per aggiungerle alla tabella.

   ![](assets/qibuilder6.png)

* **Aggiungi altri filtri**: puoi aggiungere fino a 2 ulteriori filtri utilizzando gli operatori AND o OR per aggiungerli alla tabella. Osserva cosa succede alla tabella quando aggiungi Mobile Users OR Loyal Visitors. Si trovano l’uno accanto all’altro, sopra le metriche. Se hai aggiunto Mobile Users AND Loyal Visitors, vedrai i risultati di entrambi i filtri insieme e saranno l’uno sopra l’altro nella tabella.

   ![](assets/qibuilder7.png)

## Limitazioni note

Se tenti di modificare direttamente all’interno della tabella, il pannello [!UICONTROL Quick Insights] non sarà sincronizzato. Per ripristinare le impostazioni precedenti di [!UICONTROL Quick Insights], fai clic su **[!UICONTROL Resync Builder]** in alto a destra del pannello.

![](assets/qibuilder9.png)

Visualizzerai un avviso prima di aggiungere qualsiasi elemento direttamente alla tabella:

![](assets/qibuilder8.png)

In caso contrario, la creazione diretta farà sì che la tabella ora si comporti come una tabella a forma libera tradizionale, senza le funzioni utili per i nuovi utenti.
