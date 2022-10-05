---
description: Come creare una scorecard per le dashboard di Adobe Analytics
title: Creare una scorecard
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
solution: Customer Journey Analytics
source-git-commit: e2a79bc9d39d1c7758c1ff61c5de5af31c92d34c
workflow-type: tm+mt
source-wordcount: '1700'
ht-degree: 70%

---

# Creare una scorecard per dispositivi mobili

Le informazioni riportate di seguito spiegano ai curatori di dati di Adobe Analytics come configurare e presentare dashboard per gli utenti direzionali. Per iniziare, puoi visualizzare il video Creazione di scorecard per le dashboard di Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/343458)

>[!NOTE]
>Le schermate delle scorecard per questa pagina sono state riprese dall’interfaccia di Adobe Analytics, non da CJA. Tuttavia le due interfacce utente sono quasi identiche.

Una scorecard Adobe Analytics mostra le visualizzazioni dei dati chiave per gli utenti direzionali in un layout a sezioni affiancate, come mostrato di seguito:

![Esempio di scorecard](assets/intro_scorecard.png)

In qualità di curatore di questa scorecard, puoi usare la funzione di creazione scorecard per configurare le sezioni da presentare all’utente direzionale sulla scorecard. Puoi anche configurare il modo in cui le viste dettagliate, o i raggruppamenti, possono essere regolati una volta che le sezioni vengono toccate. L’interfaccia del Creatore di scorecard è mostrata di seguito:

![Creatore di scorecard](assets/scorecard_builder.png)

Per creare la scorecard, dovrai procedere in questo modo:

1. Accedi al modello [!UICONTROL Blank Mobile Scorecard].
2. Configura la scorecard con i dati e salvala.

## Accedi al modello [!UICONTROL Blank Mobile Scorecard] {#template}

Puoi accedere al modello [!UICONTROL Blank Mobile Scorecard] creando un nuovo progetto o dal menu degli strumenti.

### Creare un nuovo progetto {#create}

1. Apri Adobe Analytics e fai clic sulla scheda **[!UICONTROL Workspace]**.
1. Fai clic sul pulsante **[!UICONTROL Create project]** e seleziona il modello di progetto **[!UICONTROL Blank mobile scorecard]**.
1. Fai clic su **[!UICONTROL Create]**.

![Template Scorecard](assets/new_template.png)

### Menu Strumenti

1. Dal menu **[!UICONTROL Tools]**, seleziona **[!UICONTROL Analytics dashboards (Mobile App)]**.
1. Nella schermata successiva, fai clic su **[!UICONTROL Create new scorecard]**.

## Configurare la scorecard con i dati e salvarla {#configure}

Per implementare il template della scorecard:

1. Alla voce **[!UICONTROL Properties]** (nella barra a destra), specifica la **[!UICONTROL Project report suite]** della quale desideri utilizzare i dati. Le suite di rapporti sono visualizzazioni di dati in CJA.

   ![Selezione di suite di rapporti](assets/properties_save.png)

1. Per aggiungere una nuova sezione alla scorecard, trascina una metrica dal pannello a sinistra e rilasciala nella zona **[!UICONTROL Drag and Drop Metrics Here]**. È anche possibile inserire una metrica tra due sezioni utilizzando un flusso di lavoro simile.

   ![Aggiungere sezioni](assets/build_list.png)


1. Da ogni sezione, è possibile accedere a una vista dettagliata che visualizza informazioni aggiuntive sulla metrica, come gli elementi principali di un elenco di dimensioni correlate.

## Aggiungere dimensioni o metriche {#dimsmetrics}

Per aggiungere una dimensione correlata a una metrica, trascina una dimensione dal pannello di sinistra e rilasciala su una tessera.

Ad esempio, puoi aggiungere dimensioni appropriate (come **[!DNL Marketing Channel]**, in questo esempio) alla metrica **[!UICONTROL Unique Visitors]** trascinandola e rilasciandola sulla sezione. Le suddivisioni delle singole dimensioni vengono visualizzate nell’area [!UICONTROL Drill Ins] (Approfondimenti) delle **[!UICONTROL Properties]** della sezione. Puoi aggiungere più dimensioni a ogni sezione.

![Aggiunta di dimensioni](assets/layer_dimensions.png)

## Applicazione di filtri {#filters}

Per applicare filtri ai singoli riquadri, trascina un filtro (i segmenti sono filtri in CJA) dal pannello a sinistra e rilascialo direttamente sulla tessera.

Se vuoi applicare il filtro a tutte le tessere della scorecard, rilascia la tessera sopra la scorecard. Oppure, puoi anche applicare i filtri selezionandoli nel menu dei filtri sotto gli intervalli di date. Puoi [configurare e applicare filtri per le scorecard](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=it) nello stesso modo che utilizzeresti in Adobe Analytics Workspace.

![Creare filtri](assets/segment_ui.png)

## Aggiungere intervalli di date {#dates}

Aggiungi e rimuovi combinazioni di intervalli di date che possono essere selezionate nella scorecard mediante il menu a discesa dell’intervallo di date.

![Nuova scorecard](assets/new_score_card.png)

Ogni nuova scorecard inizia con 6 combinazioni di intervalli di date incentrate sui dati di oggi e ieri. Per rimuovere gli intervalli di date di cui non hai bisogno, fai clic sulla x. Per modificare una combinazione di intervalli di date, fai clic sull’icona della matita.

![Nuova scorecard2](assets/new_score_card2.png)

Per creare o modificare una data primaria, utilizza il menu a discesa per selezionare uno degli intervalli di date disponibili oppure trascina un componente data dalla barra a destra fino alla zona di rilascio.

![Nuova scorecard3](assets/new_score_card3.png)

Per creare una data di confronto, puoi scegliere tra i pratici predefiniti per i confronti temporali più comuni, disponibili nel menu a discesa. Puoi anche trascinare un componente data dalla barra a destra.

![Nuova scorecard4](assets/new_score_card4.png)

Se l’intervallo di date desiderato non è ancora stato creato, puoi crearne uno nuovo facendo clic sull’icona Calendario.

![Nuova scorecard5](assets/new_score_card5.png)

Viene visualizzato il generatore di intervalli di date, in cui è possibile creare e salvare un nuovo componente Intervallo di date.

## Applicare visualizzazioni {#viz}

Le dashboard di Analytics offrono quattro visualizzazioni che consentono di ottenere informazioni approfondite su elementi e metriche delle dimensioni. Applica una visualizzazione diversa modificando l’area [!UICONTROL chart type] delle [!UICONTROL Properties] di una sezione. Seleziona la sezione destra e modifica il tipo di grafico.

![Proprietà delle sezioni](assets/properties.png)

Oppure, fai clic sull’icona [!UICONTROL Visualizations] nella barra a sinistra, quindi trascina la visualizzazione a destra sulla sezione:

![Visualizzazioni](assets/vizs.png)

### [!UICONTROL Summary Number]

Utilizza la visualizzazione Numero di riepilogo per evidenziare un numero elevato importante in un progetto.

![Numero di riepilogo](assets/summary-number.png)

### [!UICONTROL Donut]

Simile a un grafico a torta, questa visualizzazione mostra i dati come parti di un intero. Puoi utilizzare un grafico ad anello per confrontare le percentuali di un totale. Ad esempio, per capire quale piattaforma di annunci ha contribuito al numero totale di visitatori univoci:

![Visualizzazione ad anello](assets/donut-viz.png)

### [!UICONTROL Line]

La visualizzazione a linee rappresenta le metriche con linee che mostrano come cambiano i valori nel tempo. Un grafico a linee mostra le dimensioni nel tempo, ma funziona con qualsiasi visualizzazione. Questo esempio presenta la dimensione della categoria di prodotto.

![Visualizzazione a linee](assets/line.png)

### [!UICONTROL Horizontal Bar]

Questa visualizzazione mostra barre orizzontali che rappresentano diversi valori per una o più metriche. Ad esempio, per vedere facilmente quali sono i tuoi prodotti migliori, utilizza la visualizzazione [!UICONTROL Horizontal Bar].

![barre orizzontali](assets/horizontal.png)

### Rimuovere l’elemento di dimensione [!UICONTROL Unspecified]

Se desideri rimuovere dai dati gli elementi di dimensione [!UICONTROL Unspecified], effettua le seguenti operazioni:

1. Seleziona la sezione corretta.
1. Nella barra a destra, sotto **[!UICONTROL Drill ins]**, seleziona la freccia destra accanto all’elemento di dimensione di cui vuoi rimuovere gli elementi **[!UICONTROL Unspecified]**.

   ![non specificato](assets/unspecified.png)

1. Fai clic sull’icona accanto a **[!UICONTROL Unspecified]** per rimuovere i dati non specificati dalle attività di reporting. È inoltre possibile rimuovere qualsiasi altro elemento di dimensione.

## Visualizzare e configurare le proprietà delle sezioni {#tiles}

Quando fai clic su una tessera nel Creatore di scorecard, la barra a destra mostra le proprietà e le caratteristiche associate a tale tessera e alla relativa diapositiva di dettaglio. In questa barra puoi fornire un nuovo **Titolo** per la tessera e in alternativa configura la tessera applicando dei filtri. I segmenti sono filtri in CJA.

![Proprietà di una sezione](assets/properties-tile-new.png)

## Visualizza diapositive dettagliate {#view-detail-slides}

Quando fai clic sulle tessere, una finestra a comparsa dinamica mostra come la diapositiva dei dettagli viene visualizzata dall’utente esecutivo nell’app. Puoi aggiungere dimensioni per suddividere i dati in base alle tue esigenze specifiche. Se non è stata applicata una dimensione, la dimensione di suddivisione sarà **ora** o **giorni**, a seconda dell’intervallo di date predefinito.

Le suddivisioni consentono di perfezionare l’analisi suddividendo le metriche per elementi dimensionali come i seguenti:

* Metrica Visitatori univoci suddivisa per piattaforma di annunci (AMO ID)
* Visite suddivise per categoria di prodotto (al dettaglio)
* Entrate totali suddivise per nome prodotto

![Vista_Raggruppamento](assets/break_view.png)

Ogni dimensione aggiunta alla sezione viene visualizzata in un elenco a discesa nella vista dettagliata dell’app. L’utente direzionale può quindi scegliere tra le opzioni elencate nell’elenco a discesa.

## Personalizzare le diapositive dettagliate {#customize-detail-slide}

Le diapositive di dettaglio personalizzate consentono di essere ancora più mirati sulle informazioni condivise con il pubblico. È possibile modificare il layout di ogni diapositiva di dettaglio e aggiungere testo per spiegare meglio ciò che l&#39;utente finale può vedere nei dati. È inoltre possibile modificare il tipo di grafico utilizzando il menu a discesa.

![Diapositiva dettaglio personalizzata](assets/custom-detail-slide.png)

### Modificare il layout della diapositiva

Modificate il layout della diapositiva per concentrarvi sulle informazioni più importanti. Ad esempio, è possibile modificare il layout per visualizzare solo un grafico o una tabella. Per modificare il layout della diapositiva, selezionare uno dei formati predefiniti.

![Layout diapositiva](assets/layout.png)

Puoi anche modificare il layout della diapositiva trascinando i componenti di visualizzazione dalla barra a sinistra nell’area di lavoro. Ciascuna diapositiva di dettaglio può contenere solo due visualizzazioni alla volta.

![Modifica del layout della diapositiva](assets/slide-layout-change.png)

### Aggiungere testo descrittivo a una diapositiva

È possibile aggiungere testo per fornire informazioni significative su ciò che è contenuto nei grafici o sfumature sui dati.

Per aggiungere testo a una diapositiva di dettaglio, selezionare un layout che mostri il `T` oppure trascina e rilascia il componente Visualizzazione testo dalla barra a sinistra. L’editor di testo si apre automaticamente quando si aggiunge una nuova visualizzazione di testo o si sceglie un layout di diapositiva con testo. L’editor di testo fornisce tutte le opzioni standard per la formattazione del testo. È possibile applicare stili di testo quali paragrafi, intestazioni e sottotitoli e applicare font in grassetto e corsivo. È possibile giustificare il testo, aggiungere elenchi puntati e numerati e aggiungere collegamenti. Al termine della modifica, seleziona il pulsante Riduci a icona nell’angolo superiore destro dell’editor di testo per chiuderlo. Per modificare il testo già aggiunto, seleziona l’icona a forma di matita per aprire nuovamente l’editor di testo.

![Modifica del layout della diapositiva](assets/add-descriptive-text.png)

## Rimuovere i componenti {#remove}

Allo stesso modo, per rimuovere un componente applicato all’intera scorecard, fai clic in un punto qualsiasi della scorecard al di fuori delle tessere e poi rimuovilo facendo clic sul pulsante **x** che viene visualizzato quando passi il puntatore del mouse sul componente, come illustrato di seguito per **Prime visite**:

![Rimuovere_componenti](assets/new_remove.png)

## Anteprima delle scorecard {#preview}

Puoi visualizzare in anteprima come si presenterà e funzionerà una scorecard una volta pubblicata nell’app delle dashboard di Analytics.

1. Fai clic su **[!UICONTROL Preview]** in alto a destra.

   ![Preview_scorecards](assets/preview.png)

1. Per visualizzare come si presenta la scorecard su dispositivi diversi, seleziona un dispositivo dal menu a discesa [!UICONTROL Device preview].

   ![Device_preview](assets/device-preview.png)

1. Per interagire con l’anteprima:

   * Fai clic con il pulsante sinistro del mouse per simulare il tocco sullo schermo del telefono.

   * Utilizza la funzione di scorrimento del computer per simulare lo scorrimento dello schermo del telefono con un dito.

   * Fai clic e tieni premuto per simulare la pressione del dito sullo schermo del telefono. Questo è utile per interagire con le visualizzazioni nella vista dettagliata.

## Assegnare un nome a una scorecard {#name}

Per dare un nome alla scorecard, fai clic sullo spazio del nome in alto a sinistra dello schermo e digita il nuovo nome.

![Assegnare_un_nome_alle_scorecard](assets/new_name.png)

## Condividere una scorecard {#share}

Per condividere la scorecard con un direzionale:

1. Fai clic sul menu **[!UICONTROL Share]** e seleziona **[!UICONTROL Share scorecard]**.

1. Nel modulo **[!UICONTROL Share mobile scorecard]**, compila i campi:

   * Inserimento del nome della scorecard
   * Inserimento di una descrizione della scorecard
   * Aggiungendo tag rilevanti
   * Specificare i destinatari della scorecard

1. Fai clic su **[!UICONTROL Share]**.

![Condividere_scorecard](assets/new_share.png)

Dopo che hai condiviso una scorecard, i destinatari possono accedervi sulle loro dashboard di Analytics. Se apporti successive modifiche alla scorecard nel Creatore di scorecard, queste verranno automaticamente aggiornate nella scorecard condivisa. Gli utenti direzionali vedranno poi i cambiamenti dopo aver aggiornato la scorecard nella loro app.

Se aggiorni la scorecard aggiungendo nuovi componenti, ti consigliamo di condividerla nuovamente (e di selezionare l’opzione **[!UICONTROL Share embedded components]**) per assicurarti che gli utenti direzionali abbiano accesso a queste modifiche.
