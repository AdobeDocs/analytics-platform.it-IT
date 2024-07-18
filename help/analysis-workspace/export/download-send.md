---
description: Puoi scaricare i dati da Analysis Workspace copiandoli oppure esportandoli in formato PDF e CSV.
title: Scarica dati Customer Journey Analytics
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: cd4722cc2eb95d7d5e4000361c8f96a30a3589e9
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 65%

---

# Scarica dati Customer Journey Analytics

È possibile scaricare i dati di Customer Journey Analytics sulla propria workstation personale. Può essere sotto forma di dati copiati, CSV o PDF. Un PDF è in genere consigliato se desideri includere le visualizzazioni nel file scaricato. Se desideri semplicemente dati in formato testo, puoi usare CSV e dati copiati.

Sono disponibili anche altri metodi di esportazione dei dati del Customer Journey Analytics, come descritto in [Panoramica sull&#39;esportazione](/help/analysis-workspace/export/export-project-overview.md).

## Scarica come CSV o PDF {#download-project}

Quando si scaricano i progetti, considera quanto segue:

* Quando si scaricano i progetti come file CSV o PDF, il progetto può essere salvato o non salvato quando si richiede il download di un progetto. Tuttavia, solo i progetti salvati possono essere [pianificati](/help/analysis-workspace/export/t-schedule-report.md).

* Quando si scaricano progetti come PDF:
   * L’esportazione dei download può richiedere alcuni minuti, perché il progetto viene rieseguito su server Adobe prima del rendering in formato PDF. È consigliabile non uscire dal progetto fino al completamento del download del PDF nel browser. Tuttavia, puoi continuare ad apportare modifiche al progetto mentre attendi. Se la generazione di un PDF richiede più di 5 minuti, ti verrà chiesto di usare l’e-mail.
   * I download vengono riprodotti come una singola pagina senza impaginazione.
   * I rendering PDF contengono ciò che si trova sulla pagina in Workspace. Se un progetto contiene pannelli e visualizzazioni di dimensione personalizzata, dovrai impostarne ridimensionamento automatico (con il pulsante in alto a destra) in modo da evitare che alcuni contenuti vengano troncati.
   * Tutti i [collegamenti ipertestuali](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) presenti nelle tabelle a forma libera non funzionano in PDF scaricato.

Per scaricare un progetto come file CSV o PDF:

1. Effettua una delle seguenti operazioni, a seconda del formato in cui desideri che si trovi il download:

   * **PDF:** seleziona **[!UICONTROL Project]** > **[!UICONTROL Download PDF]**.

     Scegli questa opzione se vuoi che il file scaricato contenga tutte le tabelle e le visualizzazioni mostrate (visibili) nel progetto.

   * **CSV:** seleziona **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**.

     Scegliere questa opzione se si desidera che il file scaricato sia in formato testo normale.

   ![Menu a discesa Progetto con le opzioni Scarica CSV e Scarica PDF evidenziate.](assets/download-project.png)

1. (Condizionale) Se hai scelto di scaricare un file PDF, dopo che il progetto è pronto per essere scaricato, viene visualizzato un messaggio. Seleziona [!UICONTROL **Scarica**].

## Copia negli Appunti (scelta rapida: Ctrl+C) {#copy-data}

L&#39;opzione di scelta rapida **[!UICONTROL Copy to clipboard]** consente di copiare rapidamente i dati di Customer Journey Analytics da Workspace e incollarli in uno strumento di terze parti.

* Se desideri copiare la tabella visualizzata, fai clic con il pulsante destro del mouse sull’intestazione della tabella e scegli **Copia dati negli Appunti**.
* Se desideri copiare un sottoinsieme di dati, effettua una selezione nella tabella, quindi fai clic con il pulsante destro del mouse e scegli **Copia selezione negli Appunti**.

>[!TIP]
>
>È possibile utilizzare il tasto di scelta rapida `Ctrl+C` per copiare la selezione negli Appunti, quindi `Ctrl+V` per incollarlo in uno strumento di terze parti.


![Opzione Copia selezione negli Appunti. ](assets/copy-selection.png)

## Scarica come CSV {#download-data}

L&#39;opzione di scelta rapida **[!UICONTROL Download data as CSV]** consente di scaricare come CSV una tabella di dati di Customer Journey Analytics o l&#39;origine dati di qualsiasi visualizzazione.

* Nell’intestazione di una tabella o visualizzazione, fai clic con il pulsante destro del mouse e scegli **[!UICONTROL Download data as CSV]**. In questo modo i dati di Customer Journey Analytics visualizzati nella tabella o nell’origine dati sottostante per una visualizzazione vengono scaricati come CSV.

  >[!NOTE]
  >
  >  Nota: la visualizzazione Mappa non supporta questa opzione.


* All’interno di una tabella, fai clic con il pulsante destro del mouse e scegli **[!UICONTROL Download selection as CSV]**. Questa opzione consente di scaricare solo la selezione, anziché tutta la tabella visualizzata.

![Opzione Scarica dati come CSV.](assets/download-data-viz.png)

## Scaricare elementi come CSV {#download-items}

Per analizzare più delle 400 righe di dati visibili in una tabella, fai clic con il pulsante destro del mouse sull’intestazione della tabella o su una riga qualsiasi e seleziona **Scarica elementi come CSV (_nome dimensione_)**. Questa opzione consente di esportare fino a 50.000 elementi dimensionali (in base all’ordinamento della tabella) per la dimensione selezionata, con opzioni di ordinamento e filtri applicati. Se scegli questa opzione nella parte superiore della tabella, verrà esportata la prima dimensione della tabella. Anche se la tabella a forma libera non prevede alcun limite, per prestazioni ottimali si consiglia di utilizzare l’opzione Scarica elementi solo per le tabelle con meno di 20 colonne.

>[!TIP]
>
> Se la dimensione supera i 50.000 elementi, scarica il file con diverse metriche di ordinamento oppure applica un filtro. Ad esempio, esegui un download con i dati in ordine decrescente in base a Visite, quindi un secondo download in ordine crescente. Questo consente di recuperare gli elementi in fondo alle liste.

Mentre il download è in corso, puoi eseguire più attività all’interno del progetto e persino passare a un nuovo progetto Workspace nella stessa scheda. Se apri una nuova scheda del browser, il download verrà messo in pausa. Se esci completamente da Workspace o se chiudi la scheda del browser, il download verrà annullato.

![Opzione Scarica elementi come CSV (pagina).](assets/download-items.png)

### File di elementi scaricati {#items-file}

Le funzioni della tabella vengono applicate al file scaricato come segue:

* Tutti i filtri dei pannelli vengono applicati come filtri.
* Le suddivisioni **al di sopra** della dimensione selezionata nella tabella vengono applicate come filtri sopra ogni colonna.
* Le suddivisioni **al di sotto** della dimensione selezionata nella tabella vengono rimosse.

Nell’esempio precedente, gli elementi Pagina vengono scaricati con il filtro del pannello (Clienti nuovi visitatori) e i componenti al di sopra (Canale marketing = E-mail) vengono applicati come filtri. I componenti al di sotto (Tipo di dispositivo mobile) vengono rimossi dal CSV scaricato.

![Il file .csv scaricato è stato aperto in Excel.](assets/downloaded-file.png)

### Notifiche relative al download {#notifications}

Quando il file viene scaricato, viene visualizzata una notifica informativa sull’avanzamento. In qualsiasi momento, puoi annullare il download facendo clic su **[!UICONTROL Cancel download]**. La chiusura dell’avviso popup **non** annulla il download.

Al termine, verrà visualizzata una notifica di completamento e il file verrà scaricato sul browser.

Se richiedi più di un download alla volta, una notifica ti segnala che ogni download aggiuntivo sarà messo in coda fino al completamento del download precedente.

![La notifica dello stato di download che mostra la percentuale di completamento e un collegamento per annullare il download.](assets/toast.png)

## Scaricare dati sensibili {#sensitive}

Se il **[!UICONTROL Enforce Download]** [criterio di governance dei dati](/help/data-views/data-governance.md) è attivato nella visualizzazione dati su cui stai eseguendo il reporting, qualsiasi download (ad esempio invio di e-mail o condivisione di file PDF) di progetti Workspace eseguirà l&#39;hashing dei campi dati etichettati come sensibili. Puoi comunque eseguire l’analisi di questi campi in Workspace, ma se tenti di inviare un messaggio e-mail o di condividere in altro modo un progetto, i campi bloccati verranno visualizzati come vuoti nel file .pdf o .csv.

Se in [!UICONTROL Data View] sono inclusi campi dati etichettati come sensibili, l&#39;opzione per selezionare e copiare i dati dalla schermata è limitata per tutti i dati in [!UICONTROL Data View].

## Domande frequenti {#faq}

| Domanda | Risposta |
| --- | --- |
| Perché il PDF scaricato ha una sola pagina? | Al momento, Workspace non impagina i PDF scaricati. |
| Posso esportare più di 50.000 elementi con l’opzione “Scarica elementi come CSV”? | Anche se ogni download può contenere un masimo di 50.000 elementi dimensionali, puoi cambiare l’ordine nella tabella in modo da recuperare gli elementi che erano in fondo alla tabella secondo il precedente ordine, o applicare un filtro per scaricare specifici elementi. |
| Che funzione svolge **[!UICONTROL Copy visualization]**? | A differenza di [!UICONTROL **Copia i dati negli Appunti**] o [!UICONTROL **Copia selezione negli Appunti**], l’opzione con clic del tasto destro del mouse su **[!UICONTROL Copy visualization]** non è un’opzione di esportazione. Consente di copiare una visualizzazione o un pannello da una posizione in Workspace a un’altra. Ad esempio, da un pannello all’altro nello stesso progetto oppure da un progetto a un altro. [Video sui collegamenti interni al progetto](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=it) |
