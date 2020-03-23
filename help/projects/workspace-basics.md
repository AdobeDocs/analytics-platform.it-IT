---
title: Nozioni di base sull’area di lavoro
description: Descrive come eseguire il pulling dei rapporti di base in Workspace
translation-type: tm+mt
source-git-commit: eba2b60496976eb6027d58e0ce231ee046c8fc02

---


# Nozioni di base sull’area di lavoro

Se non hai ancora familiarità con lo strumento Area di lavoro, ecco alcuni suggerimenti per iniziare.

Workspace è lo strumento principale di Adobe per adottare decisioni fruibili in base ai dati a livello aziendale. La visualizzazione più comune, ovvero la tabella a forma libera, consente di creare facilmente rapporti personalizzati utilizzando dimensioni, metriche, segmenti e intervalli di date.

## Recuperare un report classifica di base in Workspace

Un report classifica mostra una visualizzazione totale aggregata di ciascun valore di dimensione, con i valori più grandi in alto. Questi tipi di report sono utili per identificare i componenti del sito più efficaci, ad esempio le pagine che ottengono il maggior traffico o quelle che generano più vendite.

1. Assicurati di aver effettuato l’accesso ad [analytics.adobe.com](https://analytics.adobe.com).
1. Nella barra di navigazione superiore, fai clic su **[!UICONTROL Workspace]**.
1. Fai clic su **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. A sinistra appare un elenco di dimensioni, metriche, segmenti e intervalli di date. Individua la dimensione Pages (Pagine) (di colore arancione) e trascinala sull’area di lavoro dove è indicato “Drop a Dimension Here” (Rilascia qui una dimensione).
1. È possibile visualizzare un rapporto che mostra le pagine principali per questo mese. Analysis Workspace ha popolato automaticamente il report con la metrica [Occorrenze](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html).
1. Individua la metrica Visite (di colore verde) e trascinala **sopra** o **accanto** all’intestazione della metrica Occorrenze (evita di posizionarla al di sopra della metrica). Se trascini la metrica Visite al di sopra di Occorrenze, la metrica viene sostituita durante la generazione del report. Se trascini la metrica Visite accanto a Occorrenze, entrambe le metriche vengono visualizzate una accanto all’altra.
1. Per salvare il progetto, fai clic su **[!UICONTROL Project] > [!UICONTROL Save]**nel menu in alto a sinistra.

## Recuperare un report con tendenze di base in Workspace

Un report con tendenze mostra una visualizzazione temporale delle metriche utilizzando l’intervallo di date selezionato. Questi tipi di report sono utili per identificare le tendenze nel tempo e possono essere utilizzati per misurare il successo o il fallimento delle decisioni aziendali attuate. Ad esempio, è possibile esaminare un report sulle visualizzazioni di pagina con tendenze nel tempo per verificare se una riprogettazione del sito ha contribuito ad aumentare o ridurre il traffico.

1. Assicurati di aver effettuato l’accesso ad [analytics.adobe.com](https://analytics.adobe.com).
1. Nella barra di navigazione superiore, fai clic su **[!UICONTROL Workspace]**.
1. Fai clic su **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. A sinistra appare un elenco di dimensioni, metriche, segmenti e intervalli di date. Locate the Page Views dimension, and drag it to the small space on the canvas labeled **[!UICONTROL Drop a Metric Here]**. Evita di rilasciarla nello spazio riservato alle dimensioni (almeno per questo esercizio).
1. Nota: se la suite di rapporti contiene dati, dovrebbe apparire un report di base sulle visualizzazioni di pagina indicante le tendenze nel corso del mese corrente. Analysis Workspace ha introdotto automaticamente l’intervallo di date “Day” (Giorno) per visualizzare la tendenza delle visualizzazioni di pagina nel corso del mese corrente.
1. Individua l’intervallo di data “Week” (Settimana) (di colore viola) nell’elenco dei componenti dell’intervallo di date a sinistra. Fai clic sul titolo dell’intervallo di date per espandere e visualizzare tutti i componenti dell’intervallo di date, oppure utilizza la barra di ricerca.
1. Trascina l’intervallo di date “Week” (Settimana) sopra l’intestazione dell’intervallo di date “Day” (Giorno) nell’area di lavoro per sostituirlo.
1. Il report con tendenze ora è aggregato per settimana anziché per giorno.
1. Per salvare il progetto, fai clic su **[!UICONTROL Project] > [!UICONTROL Save]**nel menu in alto a sinistra.

## Esercitarsi con lo strumento

Poiché Workspace è uno strumento di reporting, non ha alcun impatto sulla raccolta dei dati. Non ci saranno ripercussioni in seguito al trascinamento di componenti all’interno di un progetto per scoprire come funziona lo strumento. Trascina nel progetto Workspace diverse combinazioni di dimensioni e metriche per scoprire quali sono le opzioni disponibili.

Se trascini accidentalmente un componente non valido nel progetto Workspace o desideri tornare indietro di un passo, premi Ctrl+Z (Windows) o Comando+Z (Mac) per annullare l’ultima azione eseguita. È anche possibile iniziare con un’area di lavoro pulita facendo clic su **[!UICONTROL Project] > [!UICONTROL New]**nel menu in alto a sinistra.

## Risoluzione dei problemi

### Quando trascino una metrica, visualizzo un messaggio indicante che i dati non sono validi.

Il messaggio indicante che i dati non sono validi significa che Adobe non può restituire dati utilizzando la combinazione di dimensioni e metriche utilizzate nel report. Ad esempio, due metriche posizionate una sopra all’altra non possono essere restituite come dati, in quanto non è possibile visualizzare due metriche in questo modo. Piuttosto, posiziona le metriche una accanto all’altra.

### Quando trascino una metrica, non visualizzo dati effettivi, ma solo zeri.

Se crei correttamente un report Workspace ma non sono presenti dati, puoi controllare alcuni elementi:

* Controlla la suite di rapporti e assicurati che includa dati.
* Se utilizzi un segmento nel report, i criteri del segmento potrebbero non corrispondere ad alcun dato. Prova a rimuovere il segmento o a regolare la definizione del segmento.
* Controlla l’intervallo di date in alto a destra e accertati che sia impostato sul valore desiderato.
* Vai al tuo sito web e utilizza Debugger per convalidare i dati raccolti.

## Risorse aggiuntive

Tenete presente che le seguenti risorse possono fare riferimento all&#39;utilizzo di Workspace nel prodotto Adobe Analytics tradizionale, non in Analisi del percorso cliente.

* Post sul blog:
   * [Un’analisi più intelligente per dare più strumenti alle aziende](https://theblog.adobe.com/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Analysis Workspace: La salsa segreta sta diventando più gustosa](https://theblog.adobe.com/analysis-workspace-secret-sauce-getting-tastier/)
   * [Perché utilizzare Analysis Workspace](https://theblog.adobe.com/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)
   * [5 suggerimenti per massimizzare la produttività con Analysis Workspace](https://theblog.adobe.com/5-tips-maximize-productivity-analysis-workspace/)

## Passaggi successivi

Esistono altre risorse per approfondire le tue conoscenze di Workspace. Di seguito sono riportate alcune informazioni di base consigliate da Adobe:

### Per gli utenti finali che desiderano ampliare le conoscenze sull’utilizzo di Workspace

* [Dettagli sull’interfaccia Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/t-freeform-project.html): ora che hai creato un report di base, acquisisci maggiore familiarità con il resto dell’interfaccia.
* [Visualizzazioni in Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html): le tabelle a forma libera è solo uno dei tipi di visualizzazione disponibili in Analysis Workspace. Scopri come utilizzare altre visualizzazioni quali grafici a linee, grafici a barre e mappe geografiche.
* [Dimensioni in Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html): scopri di più sulle dimensioni e come utilizzarle in report classifica più elaborati.
* [Metriche in Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html): ulteriori informazioni sulle metriche e su come utilizzarle in altre sezioni delle tabelle a forma libera.
* [Introduzione alla segmentazione](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html): scopri cosa sono i segmenti e crea un report di base utilizzando un segmento.
* [Intervalli di date in Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html): scopri le date relative e continue e utilizzale nei progetti Workspace.
* [Condivisione di progetti in Workspace: mostra ai tuoi colleghi il fantastico progetto Workspace che hai creato.](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)

### Per analisti e amministratori che desiderano migliorare la qualità di Workspace nella propria organizzazione

* [Autorizzazioni di Analysis Workspace](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html): assegna agli utenti le autorizzazioni d’utilizzo di Workspace tramite Adobe Admin Console.
* [Modelli in Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html): puoi creare dei modelli in modo che i tuoi colleghi possano iniziare con uno spazio di progetto adatto alle loro esigenze.
* [Gestione di Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html): crea un progetto che limiti i componenti disponibili, rendendo Workspace più accessibile a chi ha meno familiarità con lo strumento.
