---
description: Scopri le varie possibilità di scaricare dati dal progetto Analysis Workspace.
title: Scaricare Progetti E Dati Di Analysis Workspace
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: 084c995658a5cf698d253f1c15229f621a8c55d5
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 25%

---

# Scaricare progetti e dati

Puoi scaricare i progetti e i dati di Analysis Workspace sul tuo dispositivo locale. Questo download può essere un file di dati copiato, un file CSV (valori separati da virgole) o un documento PDF (formato di documento portatile).

* Se vuoi includere le visualizzazioni nel file scaricato, seleziona l’opzione PDF.
* Se hai semplicemente bisogno di dati in formato testo, seleziona le opzioni CSV e dati copiati.

Ulteriori metodi per esportare i dati di Customer Journey Analytics sono descritti nella [Panoramica sull&#39;esportazione](/help/analysis-workspace/export/export-project-overview.md).

## Scaricare come file CSV o PDF {#download-project}

![Menu a discesa Progetto con le opzioni Scarica CSV e Scarica PDF evidenziate.](assets/download-project.png)

Quando scarichi un progetto come PDF, considera quanto segue:

* Il download può richiedere alcuni minuti, poiché il progetto viene rieseguito sui server Adobe per essere riprodotto in formato PDF. Non uscire dal progetto fino al download del progetto nel browser.  Puoi continuare ad apportare modifiche al progetto mentre viene eseguito il rendering del download. Se il rendering di un PDF richiede più di 5 minuti, ti viene richiesto di [inviare un&#39;e-mail a PDF](../curate-share/send-schedule-files.md).
* I file scaricati vengono riprodotti come una singola pagina senza impaginazione.
* Il PDF contiene ciò che è visibile nella pagina del browser in Analysis Workspace. È necessario ridimensionare automaticamente visualizzazioni e pannelli di dimensioni personalizzate per evitare contenuti troncati. Seleziona ![Ridimensiona](/help/assets/icons/Resize.svg) per ridimensionare automaticamente una visualizzazione o un pannello di dimensioni personalizzate.
* [Collegamenti ipertestuali](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) nelle tabelle a forma libera come collegamenti ipertestuali nel PDF scaricato.



Per scaricare un progetto come file PDF:

1. Selezionare **[!UICONTROL Project]** > **[!UICONTROL Download PDF]**.
Viene visualizzata una barra verde con il messaggio ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Your download has been requested. Please wait.]**.

1. Non appena il download è pronto, una barra verde con il messaggio ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL *Nome del progetto *PDF è pronta.]**.
Selezionare**[!UICONTROL Download]**per scaricare il PDF. Il modo in cui PDF viene presentato o scaricato dipende dalla configurazione del browser in uso per la gestione dei documenti PDF.


Per scaricare un progetto come file CSV:

* Selezionare **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**. Il progetto viene scaricato direttamente nella cartella di download configurata come parte della configurazione del browser. Il nome file è composto da *nome progetto* - *nome suite di rapporti* - *data*, ad esempio `Example Project - Omni-Channel - Luma - Jun 30, 2025.csv`.

## Copia negli Appunti {#copy-data}

L&#39;opzione **[!UICONTROL Copy to clipboard]** del menu di scelta rapida consente di copiare rapidamente i dati da Analysis Workspace e incollarli in uno strumento di terze parti.

* Se si desidera copiare i dati della tabella visualizzata, selezionare l&#39;intestazione della tabella e selezionare **Copia dati negli Appunti** dal menu di scelta rapida.
* Se desideri copiare un sottoinsieme di dati, effettua una selezione nella tabella e seleziona **Copia selezione negli Appunti** dal menu di scelta rapida.

>[!TIP]
>
>È possibile utilizzare il tasto di scelta rapida **_cmd + c_** (macOS) o **_ctrl + c_** (Windows) per copiare la selezione negli Appunti. Quindi utilizzare **_cmd + v_** (macOS) o **_ctrl + v_** (Windows) per incollare i dati.


![Opzione Copia selezione negli Appunti. ](assets/copy-clipboard.png){zoomable="yes"}

## Scarica come CSV {#download-data}

Le opzioni Scarica come CSV del menu di scelta rapida consentono di scaricare come CSV una tabella di dati o l’origine dati di qualsiasi visualizzazione.

A tale scopo, effettua le seguenti operazioni:

* Dall&#39;intestazione di qualsiasi tabella o visualizzazione, selezionare **[!UICONTROL Download data as CSV]** dal menu di scelta rapida. In questo modo i dati mostrati nella tabella o nell’origine dati sottostante per una visualizzazione vengono scaricati come CSV.

<!-- Only relevant as soon as CJA supports Map visualization 
  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.
-->

* In una tabella, selezionare **[!UICONTROL Download selection as CSV]** dal menu di scelta rapida. Questa opzione consente di scaricare solo la selezione, anziché tutta la tabella visualizzata.

![Opzione Scarica dati come CSV.](assets/download-data-as-csv.png)

## Scaricare elementi come CSV {#download-items}

Per analizzare più delle 400 righe di dati visibili in una tabella, seleziona **Scarica elementi come CSV (_Nome Dimension_)** dal menu di scelta rapida dell&#39;intestazione della tabella o di qualsiasi riga. Questa opzione consente di esportare fino a 50.000 elementi dimensionali (in base all’ordinamento della tabella) per la dimensione selezionata, con l’applicazione di opzioni di ordinamento e filtri. Se si seleziona questa opzione nella parte superiore della tabella, viene esportata la prima dimensione della tabella.

![Opzione Scarica elementi come CSV (pagina).](assets/download-items-as-csv.png)

La tabella a forma libera non prevede alcun limite. Per garantire prestazioni ottimali, si consiglia di utilizzare questa opzione nelle tabelle con meno di 20 colonne.

>[!TIP]
>
> Se la dimensione supera i 50.000 elementi, scarica il file con diverse metriche di ordinamento oppure applica un segmento. Ad esempio, esegui un download con i dati in ordine decrescente in base a Visite, quindi un secondo download in ordine crescente. Questo consente di recuperare gli elementi in fondo alle liste.

Mentre il download è in corso, puoi eseguire più attività all’interno del progetto e persino passare a un nuovo progetto Workspace nella stessa scheda. Se apri una nuova scheda del browser, il download verrà messo in pausa. Se esci completamente da Workspace o se chiudi la scheda del browser, il download verrà annullato.


### File di elementi scaricati {#items-file}

Al file scaricato vengono applicate le seguenti funzioni di una tabella a forma libera:

* Tutti i segmenti dei pannelli vengono applicati come filtri.
* Le suddivisioni **al di sopra** della dimensione selezionata nella tabella vengono applicate come filtri sopra ogni colonna.
* Le suddivisioni **al di sotto** della dimensione selezionata nella tabella vengono rimosse.

![Il file .csv scaricato è stato aperto in Excel.](assets/download-items-file.png)

### Notifiche relative al download {#notifications}

Durante il download del file vengono visualizzate le notifiche seguenti:

* È stato richiesto un **[!UICONTROL _nome tabella _blu -_Dimension _.csv._x _% completato]**che indica l&#39;avanzamento. Per annullare il download, selezionare **[!UICONTROL Cancel download]**. Selezionare ![CrossSize100](/help/assets/icons/CrossSize100.svg) se si desidera chiudere il messaggio senza annullare il download.
* Una notifica di completamento verde **[!UICONTROL _Nome tabella _-_Dimension _.csv è stato scaricato]**una volta completato il download del file. Il file viene scaricato nella cartella dei download configurata per il browser.

Se richiedi più di un download alla volta, ricevi una notifica che indica che ogni download aggiuntivo è in coda fino al completamento del download precedente.


## Scaricare dati sensibili {#sensitive}

Immagina un [criterio di governance dei dati](/help/data-views/data-governance.md) che impedisca il download dei dati. E che questo criterio è attivato nella visualizzazione dati su cui stai eseguendo il reporting. Di conseguenza, qualsiasi download di progetti (ad esempio quando invii un messaggio e-mail o condividi file PDF) ha come hash i campi di dati etichettati come sensibili. Puoi comunque eseguire l’analisi di questi campi in Analysis Workspace. Se tenti di inviare un messaggio e-mail o di condividere in altro modo un progetto, i campi dei dati sensibili vengono visualizzati come vuoti nel file PDF o CSV.

Se i campi dati etichettati come sensibili sono inclusi nella visualizzazione dati, l’opzione per selezionare e copiare i dati dalla schermata è limitata a tutti i dati nella visualizzazione dati.

## Domande frequenti {#faq}

| Domanda | Risposta |
| --- | --- |
| Perché il mio PDF scaricato è costituito da una sola pagina? | La funzionalità [Scarica PDF](#download-as-csv-or-pdf) non impagina i PDF scaricati. |
| È possibile esportare più di 50.000 elementi con l&#39;opzione **[!UICONTROL Download items as CSV]**? | Anche se ogni download può contenere un masimo di 50.000 elementi dimensionali, puoi cambiare l’ordine nella tabella in modo da recuperare gli elementi che erano in fondo alla tabella secondo il precedente ordine, o applicare un filtro per scaricare specifici elementi. |
| Che funzione svolge **[!UICONTROL Copy visualization]**? | A differenza di [!UICONTROL **Copia dati negli Appunti**] o [!UICONTROL **Copia selezione negli Appunti**], l&#39;opzione del menu di scelta rapida **[!UICONTROL Copy visualization]** non è un&#39;opzione di esportazione. Questa opzione ti consente di [copiare una visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu) o [copiare un pannello](/help/analysis-workspace/c-panels/panels.md#context-menu) da una posizione in Workspace a un&#39;altra. Ad esempio, da un pannello all’altro nello stesso progetto o da un progetto a un altro. |
