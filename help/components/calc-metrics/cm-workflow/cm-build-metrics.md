---
description: Il Generatore di metriche calcolate fornisce un’area di lavoro per trascinare e rilasciare Dimension, metriche, filtri e funzioni per creare metriche personalizzate basate sulla logica gerarchica del contenitore, sulle regole e sugli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o metriche calcolate avanzate complesse.
title: Creare metriche
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 5%

---

# Creare metriche

Il Customer Journey Analytics fornisce un’area di lavoro per trascinare e rilasciare dimensioni, metriche, filtri e funzioni per creare metriche personalizzate in base alla logica gerarchica del contenitore, alle regole e agli operatori. Questo strumento di sviluppo integrato consente di generare e salvare metriche calcolate semplici o metriche calcolate avanzate complesse.

## Inizio della creazione di una metrica calcolata

Puoi iniziare a creare una metrica calcolata in uno dei seguenti modi:

* In Analysis Workspace, apri un progetto, quindi seleziona **[!UICONTROL Components]** > **[!UICONTROL Create metric]**.
* In Analysis Workspace, apri un progetto, quindi seleziona la **Più** accanto al simbolo [!UICONTROL **Metriche**] nella barra a sinistra.
* In entrata [!DNL Customer Journey Analytics], vai a **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**, quindi seleziona **[!UICONTROL + Add]** nella parte superiore della pagina Metriche calcolate.

## Aree del generatore di metriche calcolate

L’immagine seguente e la tabella che l’accompagna illustrano alcune delle aree e delle funzioni principali del generatore di metriche calcolate.

![](assets/cm_builder_ui.png)

| Campo | Descrizione |
| --- | --- |
| Titolo | La denominazione della metrica è obbligatoria. Non puoi salvare la metrica a meno che non sia denominata. |
| Descrizione | Fornisci una descrizione intuitiva per mostrare a cosa serve e distinguerla da altre simili. <p>La descrizione viene visualizzata anche all’interno di un rapporto. È meglio NON inserire la formula nella descrizione, ma descrivere a cosa deve e non deve essere utilizzata questa metrica. La formula viene generata durante la creazione della metrica, sotto l’intestazione Riepilogo. Non è quindi necessario aggiungere la formula alla descrizione.) </p> |
| Formato | Le opzioni disponibili sono Decimale, Tempo, Percentuale e Valuta. |
| Cifre decimali | Mostra il numero di posizioni decimali da visualizzare nel rapporto. Il numero massimo di cifre decimali che è possibile specificare è 10. |
| Mostra tendenza verso l&#39;alto come... | Questa impostazione di polarità della metrica indica se Analytics deve considerare una tendenza verso l’alto nella metrica come buona (verde) o cattiva (rossa). Di conseguenza, il grafico del rapporto verrà visualizzato in verde o rosso quando si procede verso l’alto. |
| Valuta | Valuta di base per la visualizzazione dati. |
| Tag | L’assegnazione tag è un buon modo per organizzare le metriche. Tutti gli utenti possono creare tag e applicarne uno o più a una metrica. Tuttavia, puoi visualizzare solo i tag dei filtri di tua proprietà o che sono stati condivisi con te. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili:<ul><li>**Nomi team**, ad esempio Social Marketing e Mobile Marketing.</li><li>**Progetti** (tag di analisi), ad esempio Analisi per pagina di ingresso.</li><li>**Categorie**, ad esempio Donne; Geografia.</li><li>**Flussi di lavoro**, come Da approvare; Curato per (una specifica unità aziendale)</li></ul> |
| Riepilogo | <p>La formula di riepilogo viene aggiornata ogni volta che si apporta una modifica alla definizione della metrica. Questa formula viene visualizzata anche nella barra delle metriche a sinistra, quando passi il cursore su una metrica e fai clic su <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> icona. </p> |
| Definizione | È qui che puoi trascinare metriche/metriche calcolate, filtri e/o funzioni per creare la metrica calcolata. <ul><li>Se trascini una metrica calcolata, la relativa definizione di metrica verrà espansa automaticamente. </li> <li>È possibile nidificare le definizioni con i contenitori. Tuttavia, a differenza dei contenitori di filtri, questi contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. </li> </ul> |
| Operatore | Diviso per ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) è l&#39;operatore predefinito e sono presenti gli operatori +, - e x. |
| Anteprima | Fornisce una lettura rapida su eventuali errori. L’anteprima copre gli ultimi 90 giorni. Questo è un modo per valutare inizialmente se hai selezionato i componenti giusti per la metrica. Un risultato imprevisto richiederebbe una seconda occhiata alla definizione della metrica. |
| Compatibilità del prodotto | Per qualsiasi metrica calcolata creata in Customer Journey Analytics, questo valore viene sempre elencato come [!UICONTROL **Dati completamente elaborati**]. Le metriche calcolate possono includere solo dati provenienti da set di dati evento. |
| Add | Per tutti i tipi di metriche calcolate, puoi aggiungere contenitori e numeri statici alla definizione. Per le metriche calcolate avanzate, puoi anche aggiungere filtri e funzioni.<ul><li>I contenitori funzionano come un’espressione matematica e determinano l’ordine delle operazioni. Pertanto, qualsiasi elemento in un contenitore verrà elaborato prima dell’operazione successiva.</li><li>Trascinare un filtro in un contenitore filtra tutto ciò che contiene. (Solo metriche calcolate avanzate)</li><li>Puoi impilare più filtri in un contenitore.</li></ul> |
| Icona ingranaggio (tipo di metrica, attribuzione) | Selezionando l’icona a forma di ingranaggio accanto a una metrica puoi specificare il tipo di metrica e i modelli di attribuzione. |
| Icona più (+) | Consente di creare un nuovo componente, ad esempio un nuovo filtro (che porta al Generatore di filtri ). |
| Componenti ricerca | Questa barra di ricerca consente di cercare dimensioni, metriche, filtri (solo per metriche calcolate avanzate) e funzioni (solo per metriche calcolate avanzate). |
| Elenco dei Dimension | Invece di uscire dal generatore di metriche calcolate per creare un filtro semplice (nel generatore di filtri), ad esempio &quot;Pagina = Home page&quot;, puoi trascinare la pagina e selezionare la pagina iniziale direttamente dal generatore di metriche calcolate. Questo si traduce in un flusso di lavoro molto più semplice per la creazione di metriche calcolate filtrate. |
| Elenco delle metriche | Le metriche sono disponibili in 3 categorie:<ul><li>Metriche standard</li><li>Metriche calcolate</li><li>Modelli di metriche: in fondo all’elenco.</li></ul>Quando passi il cursore su una metrica, puoi vedere l’icona Info a destra di essa. Facendo clic su questa icona si ottengono le seguenti informazioni:<ul><li>La formula di calcolo.</li><li>Tendenza di anteprima della metrica.</li><li>Un’icona di modifica (matita) in alto a destra che ti porta al generatore di metriche calcolate dove puoi modificare questa metrica calcolata.</li></ul> |
| Elenco filtri | Solo per metriche calcolate avanzate. In qualità di amministratore, questo elenco mostra tutti i filtri creati nella società di accesso. Se non sei un utente amministratore, in questo elenco vengono visualizzati i filtri di tua proprietà e quelli condivisi con te. |
| Elenco delle funzioni | (Solo per metriche calcolate avanzate) Le funzioni sono suddivise in due elenchi: Base (utilizzato più spesso) e Avanzate. |
| Selettore visualizzazione dati | Questo selettore (in alto a destra) consente di passare a una visualizzazione dati diversa. |
