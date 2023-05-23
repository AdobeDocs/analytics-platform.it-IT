---
description: Il Generatore di metriche calcolate fornisce un’area di lavoro per trascinare e rilasciare Dimension, metriche, filtri e funzioni per creare metriche personalizzate basate sulla logica gerarchica del contenitore, sulle regole e sugli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o metriche calcolate avanzate complesse.
title: Creare metriche
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: 901ddcd814c71504ff056d91fd25445d94a6f56e
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 9%

---

# Creare metriche

Il Generatore di metriche calcolate fornisce un’area di lavoro per trascinare e rilasciare Dimension, metriche, filtri e funzioni per creare metriche personalizzate basate sulla logica gerarchica del contenitore, sulle regole e sugli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o metriche calcolate avanzate complesse.

Esistono diversi modi per arrivare al Generatore di metriche calcolate:

* In Analysis Workspace, apri un progetto e fai clic  **[!UICONTROL + New]** > **[!UICONTROL Create Metric]** .
* In entrata [!DNL Analytics], vai a **[!UICONTROL Components]** > **[!UICONTROL Calculated Metrics]**.

* Clic **[!UICONTROL + Add]** nella parte superiore della [Gestione metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-manager.md), o

* Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**, apri qualsiasi rapporto e fai clic sull’icona Metriche  ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) per visualizzare la barra Metriche, fai clic su **[!UICONTROL Add]**.

![](assets/cm_builder_ui.png)

## Componenti interfaccia utente {#ui-components}

| Campo | Descrizione |
| --- | --- |
| Titolo | La denominazione della metrica è obbligatoria. Non puoi salvare la metrica a meno che non sia denominata. |
| Descrizione | Fornisci una descrizione intuitiva per mostrare a cosa serve e distinguerla da altre simili. La descrizione viene visualizzata anche all’interno di un rapporto. È meglio NON inserire la formula nella descrizione, ma descrivere a cosa deve e non deve essere utilizzata questa metrica. La formula viene generata durante la creazione della metrica, sotto l’intestazione Riepilogo. Non è quindi necessario aggiungere la formula alla descrizione.) |
| Formato | Le opzioni disponibili sono Decimale, Tempo, Percentuale e Valuta. |
| Cifre decimali | Mostra il numero di posizioni decimali da visualizzare nel rapporto. Il numero massimo di cifre decimali che è possibile specificare è 10. |
| Mostra tendenza verso l&#39;alto come... | Questa impostazione di polarità della metrica indica se Analytics deve considerare una tendenza verso l’alto nella metrica come buona (verde) o cattiva (rossa). Di conseguenza, il grafico del rapporto verrà visualizzato in verde o rosso quando si procede verso l’alto. |
| Valuta | Valuta di base per la visualizzazione dati. |
| Tag | L’assegnazione tag è un buon modo per organizzare le metriche. Tutti gli utenti possono creare tag e applicarne uno o più a una metrica. Tuttavia, puoi visualizzare solo i tag dei segmenti di tua proprietà o che sono stati condivisi con te. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili:<ul><li>Tag basati sui nomi dei team, ad esempio Social Marketing e Mobile Marketing.</li><li>Tag del progetto (tag di analisi), ad esempio Analisi per pagina di ingresso.</li><li>Tag di categorie: maschile; geografia.</li><li>Tag del flusso di lavoro: Da approvare; Curato per (una specifica unità aziendale).</li></ul> |
| Riepilogo | Il [!UICONTROL Summary] La formula viene aggiornata ogni volta che si apporta una modifica alla definizione della metrica. Questa formula viene visualizzata anche nella barra delle metriche a sinistra, quando passi il cursore del mouse su una metrica e fai clic sull’icona. |
| Definizione | È qui che puoi trascinare metriche/metriche calcolate, filtri e/o funzioni per creare la metrica calcolata. Se trascini una metrica calcolata, la relativa definizione di metrica verrà espansa automaticamente. È possibile nidificare le definizioni con i contenitori. Tuttavia, a differenza dei contenitori di segmenti, questi contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. |
| Operatore | [!UICONTROL Divided by] è l’operatore predefinito, con l’aggiunta degli operatori +, - e x. |
| Anteprima | Fornisce una lettura rapida su eventuali errori. L’anteprima copre gli ultimi 90 giorni. Questo è un modo per valutare inizialmente se hai selezionato i componenti giusti per la metrica. Un risultato imprevisto richiederebbe una seconda occhiata alla definizione della metrica. |
| Compatibilità dei prodotti | La compatibilità del prodotto mostra se la metrica è compatibile con i dati completamente elaborati. |
| Add | Per tutti i tipi di metriche calcolate, puoi aggiungere contenitori e numeri statici alla definizione. Per le metriche calcolate avanzate, puoi anche aggiungere filtri e funzioni.<ul><li>I contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. Pertanto, qualsiasi elemento in un contenitore verrà elaborato prima dell’operazione successiva.</li><li>Trascinare un segmento in un contenitore segmenta tutto ciò che si trova in quel contenitore. (Solo metriche calcolate avanzate)</li><li>Puoi impilare più filtri in un contenitore.</li></ul> |
| Icona ingranaggio (tipo di metrica, attribuzione) | Selezionando l’icona a forma di ingranaggio accanto a una metrica puoi specificare il tipo di metrica e i modelli di attribuzione. |
| + Nuovo | Consente di creare un nuovo componente, ad esempio un nuovo filtro (che porta al Generatore di filtri ). |
| Componenti ricerca | Questa barra di ricerca consente di cercare dimensioni, metriche, segmenti (solo per metriche calcolate avanzate) e funzioni (solo per metriche calcolate avanzate). |
| Elenco dei Dimension | Invece di uscire dal Generatore della metrica calcolata per creare un filtro semplice (nel Generatore di filtri), ad esempio &quot;Pagina = Home page&quot;, puoi trascinare la pagina e selezionare la pagina iniziale direttamente dal Generatore della metrica calcolata. Questo si traduce in un flusso di lavoro molto più semplice per la creazione di metriche calcolate filtrate. |
| Elenco delle metriche | Le metriche sono disponibili in 3 categorie:<ul><li>Metriche standard</li><li>Metriche calcolate</li><li>Modelli di metriche: in fondo all’elenco.</li></ul>Quando passi il cursore su una metrica, puoi vedere l’icona Info a destra di essa. Facendo clic su questa icona si ottengono le seguenti informazioni:<ul><li>La formula di calcolo.</li><li>Tendenza di anteprima della metrica.</li><li>Un’icona di modifica (matita) in alto a destra che ti porta al Generatore di metriche calcolate dove puoi modificare questa metrica calcolata.</li></ul> |
| Elenco filtri | Solo per metriche calcolate avanzate. In qualità di amministratore, questo elenco mostra tutti i filtri creati nella società di accesso. Se non sei un utente amministratore, in questo elenco vengono visualizzati i filtri di tua proprietà e quelli condivisi con te. |
| Elenco delle funzioni | (Solo per metriche calcolate avanzate) Le funzioni sono suddivise in due elenchi: Base (utilizzato più spesso) e Avanzate. |
| Selettore visualizzazione dati | Questo selettore (in alto a destra) consente di passare a una visualizzazione dati diversa. |
