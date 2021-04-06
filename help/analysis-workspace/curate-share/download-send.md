---
description: Puoi scaricare i dati da Analysis Workspace copiandoli oppure in formato PDF e CSV.
title: Scaricare file PDF o CSV
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 11%

---

# Scaricare file PDF o CSV

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Esistono diversi modi per esportare dati da Analysis Workspace, a seconda del set di dati da analizzare all’esterno dello strumento e di chi deve ricevere le informazioni. I dati esportati possono essere sotto forma di dati copiati, file CSV o PDF. Un PDF è generalmente preferito se si desidera includere le visualizzazioni nel file, mentre un CSV (o i dati copiati) è preferito se si desidera semplicemente dati di testo normale.

## Scarica il progetto come CSV o PDF {#download-project}

Puoi scaricare un progetto completo da **[!UICONTROL Project > Download as PDF (or as CSV)]**. Il file scaricato contiene tutte le tabelle e visualizzazioni visualizzate (visibili) nel progetto. Un PDF è in genere preferito se desideri che le visualizzazioni siano incluse nel file, mentre un CSV è preferito se desideri semplicemente dati di testo normale.

![](assets/download-project.png)

Per i download dei progetti, ricorda:

* Il progetto può essere salvato o non salvato quando si richiede il download di un progetto. Tuttavia, solo i progetti salvati possono essere [pianificati](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html).
* I PDF scaricati nel browser possono richiedere alcuni minuti per l’esportazione, perché il progetto viene rieseguito sui server di Adobe prima del rendering in formato PDF. È consigliabile non uscire dal progetto fino al completamento del download del PDF nel browser. Tuttavia, puoi continuare ad apportare modifiche al progetto mentre attendi. Se il rendering di un PDF richiede più di 5 minuti, viene richiesto di inviarlo tramite e-mail.
* I download dei PDF vengono riprodotti come una singola pagina senza applicazione dell’impaginazione.
* Quando viene eseguito il rendering di un progetto in PDF, questo conterrà ciò che si trova sulla pagina. Se un progetto contiene pannelli e visualizzazioni di dimensione personalizzata, dovrai impostarne ridimensionamento automatico (con il pulsante in alto a destra) in modo da evitare che alcuni contenuti vengano troncati.

## Copia dati negli Appunti (tasto di scelta rapida: Ctrl+C) {#copy-data}

L’opzione di scelta rapida **[!UICONTROL Copy to clipboard]** consente di copiare rapidamente i dati da Workspace e incollarli altrove.

* Se si desidera copiare la tabella visualizzata, fare clic con il pulsante destro del mouse sull&#39;intestazione della tabella e scegliere **Copia dati negli Appunti**.
* Se desideri copiare un sottoinsieme di dati, effettua una selezione nella tabella e fai clic con il pulsante destro del mouse > **Copia selezione negli Appunti**.

Inoltre, il tasto di scelta rapida `Ctrl+C` copia la selezione negli Appunti. Una volta copiato, puoi passare in un altro strumento e incollare le informazioni (o premere `Ctrl+V`).

![](assets/copy-selection.png)

## Scarica i dati come CSV {#download-data}

L’opzione di scelta rapida **[!UICONTROL Download data as CSV]** consente di scaricare come CSV una tabella di dati o l’origine dati di qualsiasi visualizzazione.

* Nell’intestazione di una tabella o visualizzazione, fai clic con il pulsante destro del mouse su **[!UICONTROL Download data as CSV]**. In questo modo i dati visualizzati nella tabella o nell’origine dati sottostante per una visualizzazione vengono scaricati come CSV. Nota: la visualizzazione Mappa non supporta questa opzione.
* Se nella tabella viene effettuata una selezione, l’opzione indica **[!UICONTROL Download selection as CSV]**. Questa opzione consente di scaricare solo la selezione, anziché la tabella visualizzata completa.

![](assets/download-data-viz.png)

## Scarica gli elementi come CSV {#download-items}

Per analizzare più righe di dati visibili in una tabella, fai clic con il pulsante destro del mouse sull’intestazione della tabella o su una riga qualsiasi e seleziona **Scarica elementi come CSV (nome Dimension)**. Questa opzione consente di esportare fino a 50.000 elementi dimensionali (in base all’ordinamento della tabella) per la dimensione selezionata, con l’applicazione di filtri e filtri. Se scegli questa opzione nella parte superiore della tabella, verrà esportata la prima dimensione della tabella. Anche se nella tabella a forma libera non vengono applicati limiti, si consiglia di utilizzare l’opzione Scarica elementi in tabelle con meno di 20 colonne per garantire prestazioni ottimali.

>[!TIP]
>
> Se la dimensione supera i 50.000 elementi, scarica il file con diverse metriche di ordinamento applicate o applica un filtro. Ad esempio, ordina in base a Visite in un download e poi in base a Visite in un secondo download. Questo suggerimento può aiutare a recuperare gli elementi più lunghi-tail.

Puoi eseguire più attività all’interno del progetto e persino passare a un nuovo progetto Workspace nella stessa scheda mentre il download è in corso. Il download verrà messo in pausa se apri una nuova scheda del browser. Il download verrà annullato se si esce completamente da Workspace o si chiude la scheda del browser.

![](assets/download-items.png)

### File di elementi scaricati

Le funzioni della tabella vengono applicate al file scaricato come segue:

* Tutti i filtri dei pannelli vengono applicati come filtri.
* Suddivisioni **sopra** la dimensione selezionata nella tabella viene applicata come filtri sopra ogni colonna.
* Le suddivisioni **sotto** della dimensione selezionata nella tabella vengono rimosse.

Nell’esempio precedente, gli elementi pagina vengono scaricati con il filtro del pannello (Clienti nuovi visitatori) e i componenti sopra (Canale marketing = E-mail) applicati come filtri, e i componenti sotto (Tipo di dispositivo mobile) rimossi dal CSV scaricato.

![](assets/downloaded-file.png)

### Download delle notifiche

Quando il file viene scaricato, viene visualizzata una notifica informativa sull’avanzamento. In qualsiasi momento, puoi annullare il download facendo clic su **[!UICONTROL Cancel download]**. La chiusura del toast **non** annulla il download.

Al termine del file, verrà visualizzata una notifica di completamento e il file verrà scaricato sul browser.

Se richiedi più di un download alla volta, riceverai una notifica secondo cui ogni download aggiuntivo sarà messo in coda fino al completamento del download precedente.

![](assets/toast.png)

## Domande frequenti {#faq}

| Domanda | Risposta |
| --- | --- |
| Perché il mio PDF scaricato è una pagina? | Al momento, Workspace non impagina i PDF scaricati. |
| Posso esportare più di 50.000 elementi con l’opzione &quot;Scarica elementi come CSV&quot;? | Mentre ogni download può contenere fino a 50.000 elementi dimensionali, puoi modificare il tipo di tabella per recuperare elementi tail più lunghi o applicare un filtro per scaricare elementi più specifici. |
| Cosa fa **[!UICONTROL Copy visualization]**? | **[!UICONTROL Copy visualization]** non è un’opzione di esportazione. Consente di copiare una visualizzazione o un pannello da una posizione in Workspace a un’altra. Ad esempio, da un pannello all’altro nello stesso progetto o da un progetto a un altro. [Video intra-link](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html) |
