---
description: Il Generatore di metriche calcolate fornisce un’area di lavoro per trascinare Dimension, metriche, filtri e funzioni per creare metriche personalizzate basate sulla logica gerarchica dei contenitori, sulle regole e sugli operatori. Questo strumento di sviluppo integrato consente di generare e salvare semplici metriche calcolate o metriche calcolate avanzate complesse.
title: Creare metriche
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 9%

---

# Creare metriche

Il Generatore di metriche calcolate fornisce un’area di lavoro per trascinare Dimension, metriche, filtri e funzioni per creare metriche personalizzate basate sulla logica gerarchica dei contenitori, sulle regole e sugli operatori. Questo strumento di sviluppo integrato consente di generare e salvare semplici metriche calcolate o metriche calcolate avanzate complesse.

Esistono diversi modi per accedere al Generatore di metriche calcolate:

* In Analysis Workspace, apri un progetto e fai clic su  **[!UICONTROL + New]** > **[!UICONTROL Create Metric]** .
* In [!DNL Analytics], vai a **[!UICONTROL Components]** > **[!UICONTROL Calculated Metrics]**.

* Fai clic su **[!UICONTROL + Add]** nella parte superiore del [Gestore della metrica calcolata](/help/components/calc-metrics/cm-workflow/cm-manager.md)oppure

* Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**, apri un rapporto e fai clic sull’icona Metriche  ![](assets/metrics_icon.png) per visualizzare la barra Metriche , fai clic su **[!UICONTROL Add]**.

![](assets/cm_builder_ui.png)

## Componenti dell’interfaccia utente {#ui-components}

| Campo | Descrizione |
| --- | --- |
| Title | La denominazione della metrica è obbligatoria. Non è possibile salvare la metrica a meno che non sia denominata. |
| Descrizione | Dategli una descrizione facile da usare per mostrare ciò che viene utilizzato e per distinguerlo da quelli simili. La descrizione viene visualizzata anche all’interno di un rapporto. È meglio NON inserire la formula nella descrizione, ma descrivere per cosa questa metrica dovrebbe e non deve essere utilizzata. La formula viene generata durante la creazione della metrica, sotto l’intestazione Riepilogo . Di conseguenza, non è necessario aggiungere la formula alla descrizione.) |
| Formato | Le scelte includono Decimale, Tempo, Percentuale e Valuta. |
| Luoghi decimali | Mostra il numero di posizioni decimali da visualizzare nel rapporto. Il numero massimo di posizioni decimali è 10. |
| Mostra tendenza verso l&#39;alto come.. | Questa impostazione di polarità della metrica indica se Analytics deve considerare una tendenza al rialzo nella metrica buona (verde) o cattiva (rossa). Di conseguenza, il grafico del rapporto sarà visualizzato in verde o rosso quando cresce. |
| Valuta | La valuta di base per la visualizzazione dati. |
| Tag | L’assegnazione tag è un buon modo per organizzare le metriche. Tutti gli utenti possono creare tag e applicare uno o più tag a una metrica. Tuttavia, puoi visualizzare solo i tag dei segmenti di tua proprietà o che sono stati condivisi con te. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili:<ul><li>Tag basati sui nomi dei team, ad esempio Social Marketing e Mobile Marketing.</li><li>Tag del progetto (tag di analisi), ad esempio Analisi per pagina di ingresso.</li><li>Tag di categorie: maschile; geografia.</li><li>Tag del flusso di lavoro: Da approvare; Curato per (una specifica unità aziendale).</li></ul> |
| Riepilogo | La [!UICONTROL Summary] La formula viene aggiornata ogni volta che apporti una modifica alla definizione della metrica. Questa formula viene visualizzata anche nella barra delle metriche a sinistra quando passi il cursore su una metrica e fai clic sull’icona. |
| Definizione | È qui che trascina metriche/metriche calcolate, filtri e/o funzioni per creare la metrica calcolata. Se trascini una metrica calcolata, la definizione della metrica viene automaticamente espansa. È possibile nidificare le definizioni con i contenitori. Tuttavia, a differenza dei contenitori di segmenti, questi contenitori funzionano come un&#39;espressione matematica e determinano l&#39;ordine delle operazioni. |
| Operatore | [!UICONTROL Divided by] è l’operatore predefinito, oltre agli operatori +, - e x. |
| Anteprima | Fornisce una lettura rapida di eventuali errori. L’anteprima copre gli ultimi 90 giorni. Questo è un modo per verificare inizialmente se hai selezionato i componenti giusti per la metrica. Un risultato imprevisto implica la necessità di dare un&#39;occhiata alla definizione della metrica. |
| Compatibilità del prodotto | La compatibilità del prodotto mostra se la metrica è compatibile con i dati completamente elaborati. |
| Add | Per tutti i tipi di metriche calcolate, puoi aggiungere contenitori e numeri statici alla definizione. Per le metriche calcolate avanzate, puoi anche aggiungere filtri e funzioni.<ul><li>I contenitori funzionano come un&#39;espressione matematica e determinano l&#39;ordine delle operazioni. Pertanto, qualsiasi elemento in un contenitore viene elaborato prima dell’operazione successiva.</li><li>Quando si trascina un segmento su un contenitore, vengono segmentati tutti gli elementi presenti in tale contenitore. (Solo metriche calcolate avanzate)</li><li>Puoi raggruppare più filtri in un contenitore.</li></ul> |
| Icona a forma di ruota dentata (tipo di metrica, attribuzione) | Selezionando l’icona a forma di ingranaggio accanto a una metrica puoi specificare il tipo di metrica e i modelli di attribuzione. |
| + Nuovo | Consente di creare un nuovo componente, ad esempio un nuovo filtro (che consente di passare al Generatore di filtri ). |
| Componenti di ricerca | Questa barra di ricerca consente di cercare dimensioni, metriche, segmenti (solo metriche calcolate avanzate) e funzioni (solo metriche calcolate avanzate). |
| Elenco dei Dimension | Anziché uscire dal Generatore di metriche calcolate per creare un filtro semplice (nel Generatore di filtri), ad esempio &quot;Pagina = Home page&quot;, puoi trascinare in Pagina e selezionare Home page direttamente dal Generatore di metriche calcolate. Questo semplifica notevolmente il flusso di lavoro per la creazione di metriche calcolate filtrate. |
| Elenco delle metriche | Le metriche sono suddivise in 3 categorie:<ul><li>Metriche standard</li><li>Metriche calcolate</li><li>Modelli di metriche - in fondo all’elenco.</li></ul>Quando passi il cursore del mouse su una metrica, puoi vedere l’icona Informazioni a destra di essa. Fai clic su questa icona per ottenere le seguenti informazioni:<ul><li>La formula di calcolo.</li><li>Una tendenza di anteprima della metrica.</li><li>Icona di modifica (matita) in alto a destra per passare al generatore di metriche calcolate, dove è possibile modificare la metrica calcolata.</li></ul> |
| Elenco dei filtri | (Solo metriche calcolate avanzate) In qualità di Amministratore, questo elenco mostra tutti i filtri creati nella società di accesso. Se non sei un utente amministratore, questo elenco mostra i filtri che possiedi e quelli condivisi con te. |
| Elenco delle funzioni | (Solo metriche calcolate avanzate) Le funzioni sono suddivise in due elenchi: Base (utilizzato più spesso) e Avanzate . |
| Selettore della visualizzazione dati | Questo selettore (in alto a destra) consente di passare a una visualizzazione dati diversa. |
