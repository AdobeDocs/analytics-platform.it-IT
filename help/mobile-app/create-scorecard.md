---
description: Come creare e condividere le scorecard per le dashboard di Analytics
title: Creare e condividere le scorecard
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
solution: Customer Journey Analytics
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '2624'
ht-degree: 98%

---

# Creare una scorecard per dispositivi mobili {#create-a-mobile-scorecard}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="mobilescorecard_annotations"
>title="Annotazioni"
>abstract="Le annotazioni possono essere create nella gestione componenti all’interno di un progetto Workspace."

<!-- markdownlint-enable MD034 -->


Le informazioni seguenti spiegano ai curatori di dati di Customer Journey Analytics come configurare e presentare le dashboard per gli utenti direzionali. Per iniziare, puoi visualizzare il video Generatore di scorecard per le dashboard di Analytics:


>[!BEGINSHADEBOX]

Per un video dimostrativo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Creare una scorecard per dispositivi mobili](https://video.tv.adobe.com/v/3409730?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Le schermate della scorecard di Analytics per questa pagina sono state riprese dall’interfaccia utente di Adobe Analytics, non da quella di Customer Journey Analytics. Tuttavia le due interfacce utente sono quasi identiche.

Una scorecard di Analytics mostra le visualizzazioni dei dati chiave per gli utenti direzionali in un layout affiancato, come mostrato di seguito:

![Esempio di scorecard di Analytics che mostra la demo della scorecard per dispositivi mobili](assets/intro_scorecard.png)

In qualità di curatore di questa scorecard, puoi usare il generatore di scorecard per configurare le sezioni che appariranno nella scorecard per l’utente direzionale. Puoi anche configurare il modo in cui le viste dettagliate, o i raggruppamenti, possono essere regolati una volta che le sezioni vengono toccate. L’interfaccia del generatore di scorecard è mostrata di seguito:

![Generatore di scorecard che mostra la finestra nuova scorecard per dispositivi mobili. &#x200B;](assets/scorecard_builder.png)

Per creare la scorecard, dovrai effettuare le seguenti operazioni:

1. Accedi al modello [!UICONTROL Blank mobile scorecard] in Workspace.
2. Configura la scorecard con i dati e salvala.

## Accedi al modello [!UICONTROL Blank Mobile Scorecard] {#template}

Puoi accedere al modello [!UICONTROL Blank Mobile Scorecard] creando un nuovo progetto o dal menu degli strumenti.

### Creare un nuovo progetto {#create}

1. Apri Customer Journey Analytics e fai clic sulla scheda **[!UICONTROL Workspace]**.
1. Nella barra a sinistra fai clic su **[!UICONTROL Projects]**.
1. Fai clic sul pulsante **[!UICONTROL Create project]** e seleziona il modello di progetto **[!UICONTROL Blank mobile scorecard]**.
1. Fai clic su **[!UICONTROL Create]**.

![Finestra Tutti i modelli con la scorecard per dispositivi mobili vuota selezionata.](assets/new_template.png)

### Menu Strumenti

1. Dal menu **[!UICONTROL Tools]**, seleziona **[!UICONTROL Analytics dashboards (Mobile App)]**.
1. Nella schermata successiva, fai clic su **[!UICONTROL Create new scorecard]**.

## Configurare la scorecard con i dati e salvarla {#configure}

Per implementare il modello della scorecard:

1. Alla voce **[!UICONTROL Scorecard properties]** (nella barra a destra), specifica la **[!UICONTROL Project data view]** della quale desideri utilizzare i dati.

   ![Finestra Nuova scorecard per dispositivi mobili con la selezione della visualizzazione dati evidenziata](assets/properties_save.png)

1. Per aggiungere una nuova sezione alla scorecard, trascina una metrica dal pannello a sinistra e rilasciala nella zona **[!UICONTROL Drag and Drop Metrics Here]**. È anche possibile inserire una metrica tra due sezioni utilizzando un flusso di lavoro simile.

   ![Finestra Nuova scorecard per dispositiivi mobili con una freccia che punta a una metrica (Nuovo KPI) rilasciata nella scorecard. &#x200B;](assets/build_list.png)


1. Da ogni sezione, è possibile accedere a una vista dettagliata che visualizza informazioni aggiuntive sulla metrica, come gli elementi principali di un elenco di dimensioni correlate.

## Aggiungere dimensioni o metriche {#dimsmetrics}

Per aggiungere una dimensione correlata a una metrica, trascina una dimensione dal pannello di sinistra e rilasciala su una tessera.

Ad esempio, puoi aggiungere dimensioni appropriate (come **[!DNL Marketing Channel]**, in questo esempio) alla metrica **[!UICONTROL Unique Visitors]** trascinandola e rilasciandola sulla sezione. I raggruppamenti delle singole dimensioni vengono visualizzati nell’area [!UICONTROL Drill Ins] (Approfondimenti) delle **[!UICONTROL Properties]** della specifica sezione. Puoi aggiungere più dimensioni a ogni sezione.

![Finestra Nuova scorecard per dispositivi mobili con una freccia che dall’elenco delle dimensioni punta al riquadro scorecard.](assets/layer_dimensions.png)

## Applicare i segmenti {#segments}

Per applicare segmenti alle singole sezioni, trascina un segmento dal pannello di sinistra e rilascialo direttamente sulla sezione.

Se vuoi applicare il segmento a tutte le sezioni della scorecard, rilascia la sezione sopra la scorecard. Oppure, puoi anche applicare i segmenti selezionandoli nel menu dei segmenti sotto gli intervalli di date. Puoi [configurare e applicare i segmenti per le scorecard](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=it) nello stesso modo in cui lo faresti in Customer Journey Analytics Workspace.

![Selettore a discesa dei segmenti che evidenzia la creazione di segmenti](assets/segment_ui.png)

## Aggiungere intervalli di date {#dates}

Aggiungi e rimuovi combinazioni di intervalli di date che possono essere selezionate nella scorecard mediante il menu a discesa dell’intervallo di date.

![Nuova scorecard per dispositivi mobili che evidenzia Ieri e Stesso giorno della settimana scorsa](assets/new_score_card.png)

Ogni nuova scorecard inizia con 6 combinazioni di intervalli di date incentrate sui dati di oggi e ieri. Per rimuovere gli intervalli di date di cui non hai bisogno, fai clic sulla x. Per modificare una combinazione di intervalli di date, fai clic sull’icona della matita.

![Nuova scorecard per dispositiivi mobili che evidenzia l’icona a forma di matita](assets/new_score_card2.png)

Per creare o modificare una data primaria, utilizza il menu a discesa per selezionare uno degli intervalli di date disponibili oppure trascina un componente data dalla barra a destra fino alla zona di rilascio.

![Nuova scorecard per dispositivi mobili che evidenzia gli intervalli di date con Data principale/Ieri selezionati](assets/new_score_card3.png)

Per creare una data di confronto, puoi scegliere tra i pratici predefiniti per i confronti temporali più comuni, disponibili nel menu a discesa. Puoi anche trascinare un componente data dalla barra a destra.

![Nuova scorecard per dispositivi mobili che evidenzia gli intervalli di date con Data di confronto impostata su Stesso giorno della settimana scorsa selezionato](assets/new_score_card4.png)

Se l’intervallo di date desiderato non è ancora stato creato, puoi crearne uno nuovo facendo clic sull’icona del Calendario.

![Calendar icon](assets/new_score_card5.png)

Viene visualizzato il generatore di intervalli di date, in cui è possibile creare e salvare un nuovo componente Intervallo di date.

### Mostrare o nascondere intervalli di date di confronto {#show-comparison-dates}

Per includere intervalli di date di confronto, attiva l’impostazione **Includi date di confronto**.

![Nuova scorecard per dispositivi mobili che evidenzia Ieri e Giorno precedente e Includi date di confronto](assets/include-comparison-dates.png)

L’impostazione è *attiva* per impostazione predefinita. Se non desideri visualizzare le date del confronto, puoi *disattivarla*.

![Nuova scorecard per dispositivi mobili che evidenzia Ieri e Includi date di confronto](assets/no-comparison-dates.png)

## Applicare le visualizzazioni {#viz}

Le dashboard di Analytics offrono quattro visualizzazioni che consentono di ottenere informazioni approfondite su elementi e metriche delle dimensioni. Applica una visualizzazione diversa modificando l’area [!UICONTROL chart type] delle [!UICONTROL Properties] di una sezione. Seleziona la sezione destra e modifica il tipo di grafico.

![Proprietà delle sezioni](assets/properties.png)

Oppure, fai clic sull’icona [!UICONTROL Visualizations] nella barra a sinistra, quindi trascina la visualizzazione a destra sulla sezione:

![Visualizzazioni](assets/vizs.png)

### [!UICONTROL Summary Number]

Utilizza la visualizzazione Numero di riepilogo per evidenziare un numero elevato importante in un progetto.

![Nuova scorecard per dispositivi mobili con visualizzazione Numero di riepilogo che evidenzia 13.300 visite](assets/summary-number.png)

### [!UICONTROL Donut]

Questa visualizzazione è simile al grafico a torta e presenta i dati come parti o segmenti di un intero. Puoi utilizzare un grafico ad anello per confrontare le percentuali di un totale. Ad esempio, vuoi capire quale piattaforma di annunci ha contribuito al numero totale di visitatori univoci:

![Nuova scorecard per dispositivi mobili che mostra una visualizzazione ad anello](assets/donut-viz.png)

### [!UICONTROL Line]

La visualizzazione a linee rappresenta le metriche con linee che mostrano come cambiano i valori nel tempo. Un grafico a linee mostra le dimensioni nel tempo, ma funziona con qualsiasi visualizzazione. Questo esempio presenta la dimensione della categoria di prodotto.

![Nuova scorecard per dispositivi mobili che mostra una visualizzazione a linee](assets/line.png)

### [!UICONTROL Horizontal Bar]

Questa visualizzazione mostra barre orizzontali che rappresentano diversi valori per una o più metriche. Ad esempio, per vedere facilmente quali sono i tuoi prodotti migliori, utilizza la visualizzazione [!UICONTROL Horizontal Bar].

![Nuova scorecard per dispositivi mobili con una barra orizzontale](assets/horizontal.png)

## Denomina scorecard {#name}

Per denominare la scorecard, fai clic sullo spazio dei nomi in alto a sinistra dello schermo e digita il nuovo nome.

![Assegnare_un_nome_alle_scorecard](assets/new_name.png)

### Rimuovere l’elemento di dimensione [!UICONTROL Unspecified] {#remove-dims}

Se desideri rimuovere dai dati gli elementi di dimensione [!UICONTROL Unspecified], effettua le seguenti operazioni:

1. Seleziona la sezione corretta.
1. Nella barra a destra, sotto **[!UICONTROL Drill ins]**, seleziona la freccia destra accanto all’elemento di dimensione di cui vuoi rimuovere gli elementi **[!UICONTROL Unspecified]**.

   ![Proprietà con freccia che punta alla freccia destra accanto al nome della dimensione.](assets/unspecified.png)

1. Fai clic sull’icona accanto a **[!UICONTROL Unspecified]** per rimuovere i dati non specificati dalle attività di reporting. È inoltre possibile rimuovere qualsiasi altro elemento di dimensione.

## Visualizzare e configurare le proprietà delle sezioni {#tiles}

Quando fai clic su una sezione nel generatore di scorecard, la barra di destra mostra le proprietà e le caratteristiche associate a quella sezione e alla relativa diapositiva di dettaglio. In questa barra puoi fornire un nuovo **Titolo** per il riquadro e in alternativa configurare il riquadro applicando dei segmenti.

![Proprietà di una sezione](assets/properties-tile-new.png)

## Visualizza diapositive di dettaglio {#view-detail-slides}

Quando si fa clic su un riquadro, un pop-up dinamico mostra come la diapositiva di dettaglio apparirà all’utente esecutivo nell’app. Puoi aggiungere dimensioni per suddividere i dati in base alle tue esigenze specifiche. Se non è stata applicata alcuna dimensione, la dimensione del raggruppamento sarà di **ore** o **giorni**, a seconda dell’intervallo date predefinito.

I raggruppamenti consentono di perfezionare l’analisi suddividendo le metriche per elementi dimensionali come i seguenti:

* Metrica Visitatori univoci suddivisa per piattaforma di annunci (AMO ID)
* Visite suddivise per categoria di prodotto (al dettaglio)
* Entrate totali suddivise per nome prodotto

![Vista_Raggruppamento](assets/break_view.png)

Ogni dimensione aggiunta alla tessera viene visualizzata in un menu a discesa nella vista dettagliata dell’app. L’utente esecutivo può quindi scegliere tra le opzioni elencate nel menu a discesa.

## Personalizzare le diapositive di dettaglio {#customize-detail-slide}

Le diapositive di dettaglio personalizzate consentono di essere ancora più mirati sulle informazioni condivise con il pubblico.


>[!BEGINSHADEBOX]

Per un video dimostrativo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualizzazioni dei dettagli personalizzate.](https://video.tv.adobe.com/v/3413788?quality=12&learn=on&captions=ita){target="_blank"}.

{{videoaa}}

>[!ENDSHADEBOX]

È possibile modificare il layout di ogni diapositiva di dettaglio e aggiungere un testo per spiegare meglio ciò che l’utente finale può visualizzare nei dati. È inoltre possibile modificare il tipo di grafico utilizzando il menu a discesa.

![Diapositiva di dettaglio personalizzata](assets/custom-detail-slide.png)

### Modificare il layout della diapositiva

Puoi modificare il layout della diapositiva per concentrarti sulle informazioni più importanti. Ad esempio, puoi modificare il layout per visualizzare solo un grafico o una tabella. Per modificare il layout della diapositiva, seleziona uno dei formati predefiniti.

![Layout diapositiva](assets/layout.png)

Puoi anche modificare il layout della diapositiva trascinando i componenti per la visualizzazione dalla barra a sinistra nell’area di lavoro. Ciascuna diapositiva di dettaglio può contenere solo due visualizzazioni alla volta.

![Modifica del layout della diapositiva](assets/slide-layout-change.png)

### Aggiungere testo descrittivo a una diapositiva

È possibile aggiungere un testo per fornire informazioni significative su ciò che è contenuto nei grafici oppure dettagli sui dati.

Per aggiungere testo a una diapositiva di dettaglio, seleziona un layout che mostri il simbolo `T` oppure trascina il componente della Visualizzazione testo dalla barra a sinistra. Quando si aggiunge una nuova visualizzazione di testo oppure si sceglie un layout di diapositiva con testo, l’editor di testo si apre automaticamente. L’editor di testo fornisce tutte le opzioni standard per la formattazione del testo. È possibile applicare stili di testo quali paragrafi, intestazioni e sottotitoli e applicare font in grassetto e corsivo. È possibile giustificare il testo, aggiungere elenchi puntati e numerati e aggiungere collegamenti. Al termine della modifica, seleziona il pulsante Riduci a icona nell’angolo superiore a destra dell’editor di testo per chiuderlo. Per modificare il testo già aggiunto, seleziona l’icona a forma di matita per aprire nuovamente l’editor di testo.

![Modifica del layout della diapositiva](assets/add-descriptive-text.png)

## Rimuovere i componenti {#remove}

Allo stesso modo, per rimuovere un componente applicato all’intera scorecard, fai clic sulla scorecard al di fuori delle sezioni, quindi fai clic sulla **x** che compare quando passi il puntatore sul componente, come mostrato di seguito per **Nuovi visitatori**:

![Rimuovere_componenti](assets/new_remove.png)

## Creare presentazioni di dati {#create-data-story}

Una presentazione di dati è una raccolta di punti dati di supporto, contesto aziendale e metriche correlate basata su un tema o una metrica centrale.

Ad esempio, se ti concentri sul traffico web, la metrica più importante potrebbe riguardare le visite, ma potresti anche essere interessato a nuovi visitatori, visitatori univoci, e potresti voler vedere i dati suddivisi per pagina web o per tipo di dispositivo da cui proviene il traffico. Le presentazioni di dati nei progetti di scorecard per dispositivi mobili ti consentono di mettere le metriche più importanti al centro e in primo piano presentando il significato complessivo dietro le metriche con più diapositive di dettaglio.

Per ulteriori informazioni sulla creazione di presentazioni di dati nei progetti di scorecard per dispositivi mobili in Analysis Workspace, guarda questo video.


>[!BEGINSHADEBOX]

Per un video dimostrativo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Presentazioni di dati per un progetto di scorecard per dispositivi mobili](https://video.tv.adobe.com/v/3420561/?quality=12&learn=on&captions=ita){target="_blank"} .

{{videoaa}}

>[!ENDSHADEBOX]


**Creazione di una presentazione di dati** {#data-story-create}

Crea la presentazione di dati aggiungendo più diapositive di dettaglio a una sezione.

1. Inizia con un progetto di scorecard per dispositivi mobili.
1. Seleziona una sezione da cui desideri creare una presentazione.
   ![Creare una presentazione di dati](assets/data-story1.png)
   ![Creare icone della presentazione di dati](assets/create-data-story.png){width=".50%"}
1. Aggiungi le diapositive per creare una presentazione di dati personale. La prima diapositiva viene generata per impostazione predefinita.
Per aggiungere nuove diapositive, passa il puntatore oppure fai clic su una diapositiva, quindi seleziona una delle opzioni disponibili:
   * Tocca il segno + per creare una nuova diapositiva.
   * Tocca l’icona Duplica per duplicare la diapositiva esistente.
1. Se crei una diapositiva vuota, trascina i componenti dalla barra a sinistra oppure scegli un layout per popolare automaticamente la diapositiva con i dati della sezione.
   ![Creare una presentazione di dati](assets/data-story2.png)
Per eliminare una diapositiva, tocca l’icona del cestino.

### Personalizzare una presentazione di dati {#customize-data-story}

Le presentazioni di dati sono interamente personalizzabili, per condividere le informazioni che desideri ed escludere tutto quello che non ti serve. Puoi personalizzare le sezioni e le singole diapositive per aggiungere segmenti, mostrare raggruppamenti, modificare il layout e cambiare le visualizzazioni.

**Personalizzazione delle sezioni**

1. Tocca una sezione. La sezione selezionata è evidenziata in blu e il pannello a destra mostra le Proprietà della sezione.
1. Modifica il titolo, il tipo di grafico e altre opzioni della sezione.
1. Trascina un componente sulla sezione.
   ![Creare una presentazione di dati](assets/data-story3.png)
Quando trascini un componente, ad esempio una visualizzazione, su una sezione, il componente viene applicato a tutte le diapositive della presentazione di dati.
1. Per applicare una modifica solo al titolo, tieni premuto il tasto Maiusc per applicarla.
   ![Creare di una presentazione di dati](assets/data-story4.png)

>[!NOTE]
>Le diapositive ereditano i componenti dalla sezione, ma le sezioni non ereditano i componenti dalle diapositive.

**Personalizzazione di singole diapositive**

È possibile modificare la visualizzazione per singole diapositive di una presentazione di dati. Ad esempio, puoi trasformare una barra orizzontale in un grafico ad anello per una diapositiva specifica. Puoi anche modificare il layout. Consulta [Personalizzare le diapositive in dettaglio](#customize-detail-slide).

### Anteprima di una presentazione di dati {#preview-data-story}

Dopo aver creato una presentazione di dati, utilizza il pulsante **Anteprima** per visualizzare e interagire con essa come se fossi un utente dell’app. Per informazioni sull’anteprima della presentazione di dati, consulta [Anteprima di una scorecard](#preview)

### Spostarsi tra sezioni e diapositive {#navigate-tiles-slides}

Nella barra di navigazione sono visualizzate icone che rappresentano gli elementi presenti in ciascuna diapositiva. La barra di navigazione facilita il passaggio a una diapositiva specifica se sono presenti molte diapositive.

Per spostarsi tra la sezione e le diapositive, tocca la barra di navigazione.
![Creare una presentazione di dati](assets/data-story5.png)
![Creare una presentazione di dati](assets/data-story-nav.png){width="45%"}

Puoi anche spostarti avanti e indietro utilizzando le frecce sulla tastiera oppure selezionando un componente e tenendolo a sinistra o a destra dello schermo per scorrere.

## Anteprima delle scorecard {#preview}

Puoi visualizzare in anteprima come si presenterà e funzionerà la scorecard una volta pubblicata nell’app delle dashboard di Adobe Analytics.

1. Fai clic su **[!UICONTROL Preview]** in alto a destra.

   ![Preview_scorecards](assets/preview.png)

1. Per visualizzare come si presenta la scorecard su dispositivi diversi, seleziona un dispositivo dal menu a discesa [!UICONTROL Device preview].

   ![Device_preview](assets/device-preview.png)

1. Per interagire con l’anteprima:

   * Fai clic con il pulsante sinistro del mouse per simulare il tocco sullo schermo del telefono.

   * Utilizza la funzione di scorrimento del computer per simulare lo scorrimento dello schermo del telefono con un dito.

   * Fai clic e tieni premuto per simulare la pressione del dito sullo schermo del telefono. Questo è utile per interagire con le visualizzazioni nella vista dettagliata.

## Condividere le scorecard {#share}

Per condividere la scorecard con un utente direzionale:

1. Fai clic sul menu **[!UICONTROL Share]** e seleziona **[!UICONTROL Share scorecard]**.

1. Nel modulo **[!UICONTROL Share Mobile Scorecard]**, compila i campi:

   * Inserimento del nome della scorecard
   * Inserimento di una descrizione della scorecard
   * Aggiungendo tag rilevanti
   * Specificare i destinatari della scorecard

1. Fai clic su **[!UICONTROL Share]**.

![Condividere_scorecard](assets/new_share.png)

Dopo che hai condiviso una scorecard, i destinatari possono accedervi sulle loro dashboard di Analytics. Se apporti successive modifiche alla scorecard nel Generatore di scorecard, queste verranno automaticamente aggiornate nella scorecard condivisa. Gli utenti direzionali vedranno poi i cambiamenti dopo aver aggiornato la scorecard nella loro app.

Se aggiorni la scorecard aggiungendo nuovi componenti, ti consigliamo di condividerla nuovamente (e di selezionare l’opzione **[!UICONTROL Share embedded components]**) per assicurarti che gli utenti direzionali abbiano accesso a queste modifiche.

### Condividere le scorecard mediante un collegamento condivisibile

L’utilizzo di un collegamento condivisibile semplifica la condivisione di una scorecard in un’e-mail, in un documento o in un’app di messaggistica testuale. Il collegamento condivisibile consente ai destinatari di aprire la scorecard sul desktop o sull’app per dispositivi mobili delle dashboard. Il deep linking condivisibile consente di condividere i progetti in modo ancora più semplice e di aumentare il coinvolgimento degli stakeholder.

Per condividere una scorecard utilizzando un collegamento condivisibile

1. Fai clic sul menu **[!UICONTROL Share]** e seleziona **[!UICONTROL Share scorecard]**.

   ![Condividere_scorecard](assets/share-scorecard.png)

1. Copia il collegamento e incollalo in un’e-mail, in un documento o in un’app di messaggistica istantanea.

   Quando un destinatario utilizza un’app desktop o un browser per aprire il collegamento, il progetto della scorecard per dispositivi mobili si aprirà in Workspace.

   Quando un destinatario apre il collegamento su un dispositivo mobile, la scorecard si aprirà direttamente nell’app delle dashboard di Adobe Analytics.

   Se un destinatario non ha scaricato l’app per dispositivi mobili, verrà indirizzato all’elenco delle app nell’App Store o in Google Play Store dove può scaricarla.

