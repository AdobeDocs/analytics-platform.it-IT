---
description: Panoramica sull’utilizzo dei modelli predefiniti in Analysis Workspace.
title: Utilizzare i modelli
feature: Workspace Basics
role: User, Admin
hide: true
hidefromtoc: true
exl-id: d61f215d-9089-4014-9c5a-97f5d7134f34
source-git-commit: 8561f14d5b428e55614fe1465f75d2be6660468d
workflow-type: tm+mt
source-wordcount: '15430'
ht-degree: 1%

---

# Utilizzare i modelli

I modelli (o modelli aziendali) in Analysis Workspace forniscono informazioni rapide sugli scenari di reporting più comuni. Di seguito sono riportati alcuni esempi di domande a cui è possibile rispondere con i modelli:

* quante persone visitano il sito
* quanti di questi visitatori sono visitatori univoci (conteggiati una sola volta)
* come sono arrivati al sito (ad esempio, se hanno seguito un collegamento o ci sono arrivati direttamente)
* quali parole chiave hanno utilizzato i visitatori per cercare il contenuto del sito
* per quanto tempo i visitatori sono rimasti su una determinata pagina o sull’intero sito
* su quali collegamenti i visitatori hanno fatto clic e quando hanno lasciato il sito
* quali canali di marketing sono più efficaci nel generare ricavi o eventi di conversione
* quanto tempo hanno trascorso a guardare un video
* quali browser e dispositivi hanno utilizzato per visitare il sito

Le informazioni seguenti descrivono come accedere e utilizzare i modelli dalla scheda [!UICONTROL Templates] in Analysis Workspace.

## Accedere ed eseguire un modello

1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**].

   ![Schede modelli](assets/view-prebuilt-templates.png)

1. Nella sezione [!UICONTROL **Modelli**] selezionare una delle schede seguenti:

   * **[!UICONTROL Adobe templates]**: mostra tutti i modelli forniti da Adobe.

   * **[!UICONTROL _login_company_name _modelli]**: mostra tutti i modelli aziendali creati per la tua organizzazione.

     I modelli aziendali possono essere creati solo da un amministratore. Per informazioni su come creare un modello aziendale, vedere [Creare e gestire modelli](/help/analysis-workspace/templates/create-templates.md).

1. Per modificare la modalità di visualizzazione dei modelli disponibili, utilizzare una delle opzioni seguenti:

   * Scegli se visualizzare i modelli in una vista a colonne o in una vista a schede selezionando l&#39;icona della vista a colonne ![icona della vista a colonne](assets/column-view-icon.png) o l&#39;icona della vista a schede ![icona della vista a schede](assets/card-view-icon.png).

   * Quando si utilizza la vista a schede ![icona vista a schede](assets/card-view-icon.png), scegliere uno dei seguenti criteri di ordinamento: **[!UICONTROL Most recently used]**, **[!UICONTROL Most popular]**, **[!UICONTROL Alphabetical]**, **[!UICONTROL Categorical]**.

1. Nel campo di ricerca, iniziare a digitare il nome del modello che si desidera trovare, quindi selezionarlo dall&#39;elenco dei modelli.

   Oppure

   Selezionare la categoria di modello che si desidera visualizzare, quindi selezionare il modello dall&#39;elenco dei modelli.

   >[!TIP]
   >
   >Per spostarti nel menu utilizzando i tasti freccia, premi il tasto Barra obliqua (/), quindi premi il tasto Freccia giù. Premi Invio per caricare il modello selezionato.

   Per un elenco dei modelli disponibili, vedere la sezione [Modelli disponibili](#available-templates) di seguito.

1. (Facoltativo) Visualizza e utilizza modelli che contengono componenti non disponibili nella visualizzazione dati. Per impostazione predefinita, i modelli vengono visualizzati solo se utilizzano componenti disponibili nella visualizzazione dati.

   1. Seleziona l’icona del filtro.

   1. Selezionare **[!UICONTROL Not ready for use]** per visualizzare i modelli che richiedono componenti aggiuntivi.

      ![Usa un modello senza componenti](assets/template-not-ready.png)

1. Seleziona il modello per creare un rapporto basato sul modello scelto.

1. (Condizionale) Se il modello contiene componenti non disponibili nella visualizzazione dati, viene visualizzata la finestra di dialogo Visualizzazione dati non compatibile, in cui viene indicato che la visualizzazione dati è incompatibile con il modello e vengono indicati i componenti mancanti.

   Effettuare una delle seguenti operazioni:

   * Scegliere una visualizzazione dati diversa nel menu a discesa **[!UICONTROL Change data view]**.

   * Selezionare **[!UICONTROL Continue anyway]** per visualizzare il modello con i componenti mancanti.

## Creare un progetto basato su un modello {#use-reports}

Un modello potrebbe non soddisfare esattamente le tue esigenze, ma può avvicinarti. In questi casi, puoi utilizzare il modello come punto di partenza per il progetto, quindi personalizzarlo in base alle tue esigenze.

Se si esce da un modello dopo aver apportato modifiche, viene richiesto di salvare o eliminare le modifiche. Quando si salvano le modifiche apportate a un modello, questo viene salvato come nuovo progetto.

Per personalizzare un modello e salvarlo come progetto:

1. In Customer Journey Analytics selezionare la scheda [!UICONTROL **Workspace**].

1. Selezionare la scheda [!UICONTROL **Modelli**].

1. Seleziona il modello da visualizzare. Ad esempio, in [!UICONTROL **Più popolari**], seleziona il modello [!UICONTROL **Pagine**].

   Il modello Pagine, visualizzato in Analysis Workspace, mostra due [visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Grafico a barre](/help/analysis-workspace/visualizations/bar.md) e [Numero riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md)) e una [Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). La metrica utilizzata è Occorrenze.

   <!--update screenshot. The following is AA -->

   ![Modello pagine](assets/pages-report.png)

1. Esegui una delle operazioni seguenti:

   * Visualizza il modello.
   * Trascina uno o più filtri nella zona di rilascio Filtro, in alto. Ad esempio, trascina il filtro [!UICONTROL **Clienti dispositivi mobili**] e visualizza i risultati.
   * Modifica l’intervallo di date andando sul calendario in alto a destra.
   * Aggiungi suddivisioni dimensionali, trascina altre metriche e in genere personalizza il modello in base alle tue esigenze.

1. (Facoltativo) Salva il modello come progetto selezionando [!UICONTROL **Progetto**] > [!UICONTROL **Salva**].

   Il modello viene salvato come nuovo progetto e non modifica il modello esistente. Per ulteriori informazioni sul salvataggio dei progetti, vedere [Salva progetti](/help/analysis-workspace/build-workspace-project/save-projects.md).

## Modelli disponibili

Per accedere a tutti i modelli predefiniti disponibili:

1. In Adobe Analytics, seleziona la scheda [!UICONTROL **Workspace**], quindi la scheda [!UICONTROL **Modelli**].

   I modelli predefiniti sono organizzati per categoria.

   <!--add screenshot-->

1. Selezionare una categoria per visualizzare i modelli al suo interno.

   Le sezioni seguenti corrispondono alle categorie disponibili e forniscono informazioni su ciascun modello.

   * [[!UICONTROL ](#most-popular)

   * [[!UICONTROL ](#engagement)

   * [[!UICONTROL ](#web-conversion)

   * [[!UICONTROL ](#web-audience)

   * [[!UICONTROL ](#web-acquisition)

   * [[!UICONTROL ](#mobile-mobile-app)

   * [[!UICONTROL ](#mobile-mobile-device-information)

   * [[!UICONTROL ](#time-parting)

   * [[!UICONTROL ](#cross-channel)

   * [[!UICONTROL ](#other-channels)

   * [[!UICONTROL ](#ajo)

### Most popular (Più popolari) {#most-popular}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--training"
>title="Modello per le esercitazioni"
>abstract="Scopri la terminologia e i passaggi comuni di Analysis Workspace per creare la tua prima analisi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--pagesRankedReport"
>title="Identifica le pagine più popolari e meno popolari."
>abstract="**Questo può aiutarti** a comprendere meglio il tuo pubblico e il tipo di informazioni a cui sono più interessati.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio regolare i metadati della pagina per aumentare la visibilità sulle pagine visualizzate meno o passare del tempo a migliorare il contenuto delle pagine più visualizzate.<br/>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--pageViewsOvertimeReport"
>title="Visualizzare il numero totale di visualizzazioni di pagina. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. "
>abstract="**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.<br/>**In base a ciò che apprendi, potresti** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l&#39;avvio della campagna. Oppure puoi confrontare il traffico delle vacanze su base annua.<br/>Questo modello utilizza la dimensione Giorno e la metrica Visualizzazioni pagina."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--visitsOvertimeReport"
>title="Visualizza il numero totale di visite. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.<br/>**In base a ciò che apprendi, potresti** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l&#39;avvio della campagna. Oppure puoi confrontare il traffico delle vacanze su base annua.<br/>Questo modello utilizza la dimensione Giorno e la metrica Visite."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--visitorsOvertimeReport"
>title="Visualizza il numero totale di visitatori univoci. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. "
>abstract="**Questo può aiutarti** a comprendere meglio come la portata e la dimensione del pubblico del tuo sito aumentino o diminuiscano nel tempo o rispetto a un periodo precedente.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare se una campagna di marketing lanciata di recente è riuscita ad attirare nuove persone sul sito confrontando visitatori univoci prima e dopo il lancio della campagna. Oppure puoi confrontare il numero di persone che visitano il sito durante le festività anno su anno.<br/>Questo modello utilizza la dimensione Giorno e la metrica Visitatori univoci. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--keyMetricsReport"
>title="Visualizza un rapporto che mostra affiancate le metriche di visualizzazioni di pagina, visite e visitatori univoci. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo può aiutarti** a confrontare queste metriche importanti per ottenere un quadro più completo del numero di persone univoche che che visitano il sito, del numero di volte in cui sono state visitate le pagine e del numero di sessioni.<br/>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio valutare il numero medio di pagine visualizzate da ogni persona durante la visita al sito in una determinata settimana o mese e come è cambiato durante determinati periodi dell&#39;anno o prima e dopo l&#39;esecuzione di campagne di marketing. <br/>Questo modello utilizza la dimensione Giorno, la metrica Visualizzazioni pagina, la metrica Visite e la metrica Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--siteSectionRankedReport"
>title="Visualizza le sezioni più popolari o con le prestazioni più elevate del sito."
>abstract="**Questo può aiutarti** a capire meglio quali sezioni del tuo sito sono più visitate.<br>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare quali prodotti o servizi fornisci generano il maggior interesse.<br/>Questo modello utilizza la dimensione Sezione sito e la metrica Visite."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--next-page-report"
>title="Visualizzare i luoghi più comuni in cui le persone vanno immediatamente dopo la visita o immediatamente prima di visitare un determinato luogo."
>abstract="**Questo ti aiuta** a capire come il traffico si sposta da una determinata pagina ad altre parti del sito e i percorsi seguiti dalle persone per arrivare a una determinata pagina.<br/>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio valutare se la progettazione o il layout della pagina possa essere ottimizzato per indirizzare gli utenti a pagine più desiderate, ad esempio una pagina per effettuare un acquisto o lasciare una recensione. Oppure valuta se le informazioni sulla pagina corrente possano fornire la direzione o le azioni che le persone stanno cercando quando arrivano dalle pagine precedenti. Oppure puoi valutare se le pagine che non sono visualizzate come pagine precedenti richiedono collegamenti più prominenti alla pagina corrente.<br/>Questo modello utilizza il pannello Elemento successivo o precedente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignRankedReport"
>title="Visualizza i collegamenti più efficaci per indirizzare il traffico verso il tuo sito."
>abstract="**Questo può aiutarti** a capire meglio quali codici di tracciamento (e i collegamenti a essi associati) sono stati più utilizzati per accedere al tuo sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio modificare la tua strategia per la posizione in cui aggiungi collegamenti al tuo sito.<br/>Questo modello utilizza la dimensione Codice di tracciamento e la metrica Visite."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--productsRankedReport"
>title="Visualizza il numero di ordini per prodotto. I dati vengono visualizzati in un arco di tempo."
>abstract="**Questo ti aiuta** a capire quali prodotti sono più richiesti o meno.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio modificare le tue strategie di marketing per promuovere prodotti dalle prestazioni elevate o per migliorare o interrompere prodotti dalle prestazioni insoddisfacenti. Puoi anche regolare l’inventario dei prodotti in base all’analisi dei dati.<br/>Questo modello utilizza la dimensione Prodotto e la metrica Ordini."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--lastTouchChannelRankedReport"
>title="Visualizza i canali di marketing più recenti con cui i visitatori fanno riferimento durante il periodo di coinvolgimento (30 giorni per impostazione predefinita)."
>abstract="**Questo può aiutarti** a capire quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito e che hanno causato conversioni.<br/>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio allocare più risorse ai canali con prestazioni elevate o allocare meno risorse ai canali con prestazioni insoddisfacenti.<br/>Questo modello utilizza la dimensione Canale di ultimo contatto e la metrica Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--lastTouchChannelDetailRankedReport"
>title="Visualizza i dettagli sui canali di marketing più recenti con cui i visitatori corrispondono durante il periodo di coinvolgimento (30 giorni per impostazione predefinita)."
>abstract="**Questo può aiutarti** a capire non solo quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito che hanno generato conversioni, ma anche i dettagli su tali canali di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing &quot;Ricerca a pagamento&quot;, puoi utilizzare i dettagli del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.<br/>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio allocare più risorse ai canali con prestazioni elevate o allocare meno risorse ai canali con prestazioni insoddisfacenti.<br/>Questo modello utilizza la dimensione Dettaglio canale di ultimo contatto e la metrica Visitatori univoci. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--revenueOvertimeReport"
>title="Visualizza l&#39;importo monetario dei prodotti acquistati in tutti gli ordini. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo può aiutarti** a capire come i ricavi aumentano o diminuiscono nel tempo. Puoi combinare questa metrica con qualsiasi dimensione per scoprire quali elementi dimensionali hanno contribuito ai ricavi.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio proiettare i ricavi futuri in base alle tendenze precedenti. Puoi anche aggiungere un’altra dimensione, come la dimensione Codice di tracciamento, per scoprire quali campagne generano più ricavi.<br/>Questo modello utilizza la dimensione Giorno e la metrica Ricavi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ordersOvertimeReport"
>title="Visualizza il numero totale di eventi di acquisto. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo ti aiuta** a comprendere meglio come aumenta o diminuisce nel tempo l&#39;interesse per i tuoi prodotti e servizi. Puoi applicare un segmento per scoprire quali clienti o aree geografiche stanno effettuando il maggior numero di ordini e come questi ultimi tendono nel tempo.<br/>**In base a quanto appreso, è possibile** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando gli ordini prima e dopo il lancio della campagna. Oppure puoi confrontare gli ordini relativi alle festività su base annua.<br/>Questo modello utilizza la dimensione Giorno e la metrica Ordini."

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Esercitazione**] | Scopri la terminologia e i passaggi comuni di Analysis Workspace per creare la tua prima analisi |
| [!UICONTROL **Pagine**] | <!--duplicated in Engagement section--> Identifica le pagine più popolari e meno popolari. <p>**Questo può aiutarti** a comprendere meglio il tuo pubblico e il tipo di informazioni a cui sono più interessati.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio regolare i metadati della pagina per aumentare la visibilità sulle pagine visualizzate meno o passare del tempo a migliorare il contenuto delle pagine più visualizzate.</p><p>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina.</p> |
| [!UICONTROL **Visualizzazioni pagina**] | <!--duplicated in Engagement section--> Visualizzare il numero totale di visualizzazioni di pagina. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**In base a ciò che apprendi, potresti** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l&#39;avvio della campagna. Oppure puoi confrontare il traffico delle vacanze su base annua.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Visualizzazioni pagina.</p> |
| [!UICONTROL **Visite Web**] | <!--duplicated in Engagement section--> Visualizza il numero totale di visite. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**In base a ciò che apprendi, potresti** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l&#39;avvio della campagna. Oppure puoi confrontare il traffico delle vacanze su base annua.</p><p>Questo modello utilizza le dimensioni Giorno e Visite.</p> |
| [!UICONTROL **Visitatori Web**] | <!--duplicated in Engagement section--> Visualizza il numero totale di visitatori univoci. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come la portata e la dimensione del pubblico del tuo sito aumentino o diminuiscano nel tempo o rispetto a un periodo precedente.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare se una campagna di marketing lanciata di recente è riuscita ad attirare nuove persone sul sito confrontando visitatori univoci prima e dopo il lancio della campagna. Oppure puoi confrontare il numero di persone che visitano il sito durante le festività anno su anno.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Visitatori univoci.</p> |
| [!UICONTROL **Metriche chiave**] | <!--duplicated in Engagement section--> Visualizza un rapporto che mostra affiancate le metriche di visualizzazioni di pagina, visite e visitatori univoci. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a confrontare queste metriche importanti per ottenere un quadro più completo del numero di persone univoche che che visitano il sito, del numero di volte in cui sono state visitate le pagine e del numero di sessioni.</p><p>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio valutare il numero medio di pagine visualizzate da ogni persona durante la visita al sito in una determinata settimana o mese e come è cambiato durante determinati periodi dell&#39;anno o prima e dopo l&#39;esecuzione di campagne di marketing. </p><p>Questo modello utilizza la dimensione Giorno, la metrica Visualizzazioni pagina, la metrica Visite e la metrica Visitatori univoci.</p> |
| [!UICONTROL **Sezione sito**] | Visualizza le sezioni più popolari o con le prestazioni più elevate del sito. <p>**Questo può aiutarti** a capire meglio quali sezioni del tuo sito sono più visitate.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare quali prodotti o servizi fornisci generano il maggior interesse.</p> <p>Questo modello utilizza la dimensione Sezione sito e la metrica Visite.</p> |
| [!UICONTROL **Pagina successiva e precedente**] | Visualizzare i luoghi più comuni in cui le persone vanno immediatamente dopo la visita o immediatamente prima di visitare un determinato luogo. <p>**Questo ti aiuta** a capire come il traffico si sposta da una determinata pagina ad altre parti del sito e i percorsi seguiti dalle persone per arrivare a una determinata pagina.</p><p>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio valutare se la progettazione o il layout della pagina possa essere ottimizzato per indirizzare gli utenti a pagine più desiderate, ad esempio una pagina per effettuare un acquisto o lasciare una recensione. Oppure valuta se le informazioni sulla pagina corrente possano fornire la direzione o le azioni che le persone stanno cercando quando arrivano dalle pagine precedenti. Oppure puoi valutare se le pagine che non sono visualizzate come pagine precedenti richiedono collegamenti più prominenti alla pagina corrente.</p><p>Questo modello utilizza il pannello Elemento successivo o precedente.</p> |
| [!UICONTROL **Campagne (codice di tracciamento)**] | Visualizza i collegamenti più efficaci per indirizzare il traffico verso il tuo sito. <p>**Questo può aiutarti** a capire meglio quali codici di tracciamento (e i collegamenti a essi associati) sono stati più utilizzati per accedere al tuo sito.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio modificare la tua strategia per la posizione in cui aggiungi collegamenti al tuo sito.</p><p>Questo modello utilizza la dimensione Codice di tracciamento e la metrica Visite.</p> |
| [!UICONTROL **Prodotti**] | Visualizza il numero di ordini per prodotto. I dati vengono visualizzati in un arco di tempo. <p>**Questo ti aiuta** a capire quali prodotti sono più richiesti o meno.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio modificare le tue strategie di marketing per promuovere prodotti dalle prestazioni elevate o per migliorare o interrompere prodotti dalle prestazioni insoddisfacenti. Puoi anche regolare l’inventario dei prodotti in base all’analisi dei dati.</p><p>Questo modello utilizza la dimensione Prodotto e la metrica Ordini.</p> |
| [!UICONTROL **Canale marketing ultimo contatto**] | Visualizza i canali di marketing più recenti con cui i visitatori fanno riferimento durante il periodo di coinvolgimento (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a capire quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito e che hanno causato conversioni.</p><p>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio allocare più risorse ai canali con prestazioni elevate o allocare meno risorse ai canali con prestazioni insoddisfacenti.</p><p>Questo modello utilizza la dimensione Canale di ultimo contatto e la metrica Visitatori univoci.</p> |
| [!UICONTROL **Dettaglio canale marketing ultimo contatto**] | Visualizza i dettagli sui canali di marketing più recenti con cui i visitatori corrispondono durante il periodo di coinvolgimento (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a capire non solo quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito che hanno generato conversioni, ma anche i dettagli su tali canali di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing &quot;Ricerca a pagamento&quot;, puoi utilizzare i dettagli del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.</p><p>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio allocare più risorse ai canali con prestazioni elevate o allocare meno risorse ai canali con prestazioni insoddisfacenti.</p><p>Questo modello utilizza la dimensione Dettaglio canale di ultimo contatto e la metrica Visitatori univoci.</p> |
| [!UICONTROL **Ricavi**] | <!--duplicated in Web Conversion section-->Visualizza l&#39;importo monetario dei prodotti acquistati in tutti gli ordini. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti.<p>**Questo può aiutarti** a capire come i ricavi aumentano o diminuiscono nel tempo. Puoi combinare questa metrica con qualsiasi dimensione per scoprire quali elementi dimensionali hanno contribuito ai ricavi.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio proiettare i ricavi futuri in base alle tendenze precedenti. Puoi anche aggiungere un’altra dimensione, come la dimensione Codice di tracciamento, per scoprire quali campagne generano più ricavi.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Ricavi.</p> |
| [!UICONTROL **Ordini**] | <!--duplicated in Web Conversion section-->Visualizza il numero totale di eventi di acquisto. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo ti aiuta** a comprendere meglio come aumenta o diminuisce nel tempo l&#39;interesse per i tuoi prodotti e servizi. Puoi applicare un segmento per scoprire quali clienti o aree geografiche stanno effettuando il maggior numero di ordini e come questi ultimi tendono nel tempo.</p><p>**In base a quanto appreso, è possibile** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando gli ordini prima e dopo il lancio della campagna. Oppure puoi confrontare gli ordini relativi alle festività su base annua.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Ordini.</p> |

### Web: coinvolgimento {#web-engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_time_spent"
>title="Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita, nonché il tempo medio che gli utenti trascorrono prima di un evento di successo. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e il tempo necessario ai visitatori per eseguire un&#39;azione desiderata, ad esempio per effettuare un acquisto.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio valutare se le modifiche al tuo sito migliorano la capacità dei visitatori di raggiungere rapidamente un evento di successo.<br/>Questo modello utilizza la dimensione Giorno e la metrica Tempo trascorso per visita (secondi), la dimensione Giorno e la metrica Tempo trascorso per visita (secondi)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-content-consumption"
>title="Visualizzare i contenuti web più utilizzati e coinvolge maggiormente gli utenti."
>abstract="**Questo può aiutarti** a capire meglio dove vanno le persone al primo accesso al sito, quali sezioni del sito sono più visitate e quali pagine hanno più probabilità di allontanare le persone dal sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare quali percorsi sul sito indirizzano le persone alle pagine più importanti e quali sono le pagine che più probabilmente allontanano le persone dal sito.<br/>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina, la metrica Visite, la metrica Visitatori univoci, la metrica Tasso di ingresso, la metrica Tasso di rimbalzo, la metrica Tasso di uscita e la metrica Velocità contenuto. Vengono inoltre utilizzate le visualizzazioni Flusso per le sezioni di entrata, uscita e superiori."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--media-content-consumption"
>title="Visualizzare i contenuti multimediali più utilizzati e coinvolge maggiormente gli utenti."
>abstract="**Questo può aiutarti** a capire meglio dove vanno le persone al primo accesso al sito, quali sezioni del sito sono più visitate e quali pagine hanno più probabilità di allontanare le persone dal sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare quali percorsi sul sito indirizzano le persone alle pagine più importanti e quali sono le pagine che più probabilmente allontanano le persone dal sito.<br/>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina, la metrica Visite, la metrica Visitatori univoci, la metrica Tasso di ingresso, la metrica Tasso di rimbalzo, la metrica Tasso di uscita e la metrica Velocità contenuto. Inoltre, utilizza le visualizzazioni Flusso per le sezioni di entrata, uscita e principali; una visualizzazione grafico a dispersione che mostra le visualizzazioni di pagina per le pagine più comuni; una visualizzazione a barre che mostra le visualizzazioni di pagina per periodo fisso; e una visualizzazione a linee che mostra una visualizzazione con tendenze del tempo medio trascorso sul sito."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--page-summary-report"
>title="Visualizza informazioni chiave su qualsiasi pagina delle tue proprietà. Mostra le visualizzazioni di pagina, una linea di tendenza, una visualizzazione di flusso e altro ancora."
>abstract="**Questo ti aiuta** a capire meglio come le persone interagiscono con una determinata pagina.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come analizzare le prestazioni della pagina in un periodo di tempo o capire meglio cosa guida il traffico verso la pagina.<br/>Questo modello utilizza la metrica Visualizzazioni pagina. Utilizza anche la visualizzazione Linee e la visualizzazione Flusso."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--entryPageRankedReport"
>title="Visualizza le pagine principali a cui gli utenti accedono quando visitano il tuo sito per la prima volta."
>abstract="**Questo ti aiuta** a capire meglio quali pagine generano maggior traffico verso il tuo sito o le prime impressioni dei visitatori sul tuo sito.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come ottimizzare l&#39;esperienza iniziale che le persone trovano sul sito o assicurarti che le pagine che le persone vedono per la prima volta quando accedono al tuo sito siano accoglienti e forniscano i collegamenti necessari ad altre aree del sito.<br/>Questo modello utilizza la metrica Sessioni. Utilizza anche la visualizzazione a barre e la visualizzazione a forma libera della tabella."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--exitPageRankedReport"
>title="Visualizza le pagine principali a cui gli utenti accedono immediatamente prima di lasciare il sito."
>abstract="**Questo ti aiuta** a capire meglio quali pagine allontanano le persone dal sito. <br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio aggiornare le pagine di uscita comuni per ottimizzare l&#39;esperienza che le persone ottengono prima di partire, oppure includere contenuti o collegamenti per incoraggiare le persone a rimanere sul tuo sito.<br/>Questo modello utilizza la metrica Sessioni. Utilizza anche la visualizzazione a barre e la visualizzazione a forma libera della tabella."

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Metriche chiave**] | <!--duplicated in Most popular section--> Visualizza un rapporto che mostra affiancate le metriche di visualizzazioni di pagina, visite e visitatori univoci. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a confrontare queste metriche importanti per ottenere un quadro più completo del numero di persone univoche che che visitano il sito, del numero di volte in cui sono state visitate le pagine e del numero di sessioni.</p><p>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio valutare il numero medio di pagine visualizzate da ogni persona durante la visita al sito in una determinata settimana o mese e come è cambiato durante determinati periodi dell&#39;anno o prima e dopo l&#39;esecuzione di campagne di marketing. </p><p>Questo modello utilizza la dimensione Giorno, la metrica Visualizzazioni pagina, la metrica Visite e la metrica Visitatori univoci.</p> |
| [!UICONTROL **Visualizzazioni pagina**] | <!--duplicated in Most popular section-->Visualizzare il numero totale di visualizzazioni di pagina. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**In base a ciò che apprendi, potresti** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l&#39;avvio della campagna. Oppure puoi confrontare il traffico delle vacanze su base annua.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Visualizzazioni pagina.</p> |
| [!UICONTROL **Pagine**] | <!--duplicated in Most popular section-->Identifica le pagine più popolari e meno popolari. <p>**Questo può aiutarti** a comprendere meglio il tuo pubblico e il tipo di informazioni a cui sono più interessati.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio regolare i metadati della pagina per aumentare la visibilità sulle pagine visualizzate meno o passare del tempo a migliorare il contenuto delle pagine più visualizzate.</p><p>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina.</p> |
| [!UICONTROL **Visite**] | <!--duplicated in Most popular section-->Visualizza il numero totale di visite. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**In base a ciò che apprendi, potresti** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l&#39;avvio della campagna. Oppure puoi confrontare il traffico delle vacanze su base annua.</p><p>Questo modello utilizza le dimensioni Giorno e Visite.</p> |
| [!UICONTROL **Visitatori**] | <!--duplicated in Most popular section-->Visualizza il numero totale di visitatori univoci. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come la portata e la dimensione del pubblico del tuo sito aumentino o diminuiscano nel tempo o rispetto a un periodo precedente.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare se una campagna di marketing lanciata di recente è riuscita ad attirare nuove persone sul sito confrontando visitatori univoci prima e dopo il lancio della campagna. Oppure puoi confrontare il numero di persone che visitano il sito durante le festività anno su anno.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Visitatori univoci.</p> |
| [!UICONTROL **Durata**] | Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita, nonché il tempo medio che gli utenti trascorrono prima di un evento di successo. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e il tempo necessario ai visitatori per eseguire un&#39;azione desiderata, ad esempio per effettuare un acquisto.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio valutare se le modifiche al tuo sito migliorano la capacità dei visitatori di raggiungere rapidamente un evento di successo.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Tempo trascorso per visita (secondi), la dimensione Giorno e la metrica Tempo trascorso per visita (secondi).</p> |
| [!UICONTROL **Sezione sito**] | <!--duplicated in Most popular section-->Visualizza le sezioni più popolari o con le prestazioni più elevate del sito. <p>**Questo può aiutarti** a capire meglio quali sezioni del tuo sito sono più visitate.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare quali prodotti o servizi fornisci generano il maggior interesse.</p> <p>Questo modello utilizza la dimensione Sezione sito e la metrica Visite.</p> |
| [!UICONTROL **Consumo di contenuti Web**] | Visualizzare i contenuti web più utilizzati e coinvolge maggiormente gli utenti.<p>**Questo può aiutarti** a capire meglio dove vanno le persone al primo accesso al sito, quali sezioni del sito sono più visitate e quali pagine hanno più probabilità di allontanare le persone dal sito.</p><p>**In base a quanto appreso, è possibile** eseguire un&#39;operazione qualsiasi, ad esempio valutare quali percorsi sul sito indirizzano le persone alle pagine più importanti e quali pagine hanno più probabilità di allontanarle dal sito <!-- not sure about these takeaways... -->.</p> <p>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina, la metrica Visite, la metrica Visitatori univoci, la metrica Tasso di ingresso, la metrica Tasso di rimbalzo, la metrica Tasso di uscita e la metrica Velocità contenuto. Vengono inoltre utilizzate le visualizzazioni Flusso per le sezioni di entrata, uscita e superiori.</p> |
| [!UICONTROL **Consumo di contenuti multimediali**] | Visualizzare i contenuti multimediali più utilizzati e coinvolge maggiormente gli utenti.<p>**Questo può aiutarti** a capire meglio dove vanno le persone al primo accesso al sito, quali sezioni del sito sono più visitate e quali pagine hanno più probabilità di allontanare le persone dal sito.</p><p>**In base a quanto appreso, è possibile** eseguire un&#39;operazione qualsiasi, ad esempio valutare quali percorsi sul sito indirizzano le persone alle pagine più importanti e quali pagine hanno più probabilità di allontanarle dal sito <!-- not sure about these takeaways... -->.</p> <p>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina, la metrica Visite, la metrica Visitatori univoci, la metrica Tasso di ingresso, la metrica Tasso di rimbalzo, la metrica Tasso di uscita e la metrica Velocità contenuto. Inoltre, utilizza le visualizzazioni Flusso per le sezioni di entrata, uscita e principali; una visualizzazione grafico a dispersione che mostra le visualizzazioni di pagina per le pagine più comuni; una visualizzazione a barre che mostra le visualizzazioni di pagina per periodo fisso; e una visualizzazione a linee che mostra una visualizzazione con tendenze del tempo medio trascorso sul sito.</p> |
| [!UICONTROL **Pagina successiva e precedente**] | <!--duplicated in Most popular section-->Visualizza i luoghi più comuni in cui le persone vanno prima o dopo aver visitato un determinato luogo.<p>**Questo può aiutarti** a capire meglio dove vanno le persone al primo accesso al sito, quali sezioni del sito sono più visitate e quali sono le pagine più probabili da visitare prima di lasciare il sito.</p><p>**In base a quanto appreso, è possibile** eseguire un&#39;operazione qualsiasi, ad esempio valutare quali percorsi sul sito indirizzano le persone alle pagine più importanti e quali pagine allontanano più probabilmente le persone dal sito<!-- not sure about these takeaways... -->.</p> <p>Questo modello utilizza la dimensione Pagina, la metrica Visualizzazioni pagina, la metrica Visite, la metrica Visitatori univoci, la metrica Tasso di ingresso, la metrica Tasso di rimbalzo, la metrica Tasso di uscita e la metrica Velocità contenuto. Inoltre, utilizza le visualizzazioni Flusso per le sezioni di entrata, uscita e principali; una visualizzazione Grafico a dispersione che mostra le visualizzazioni di pagina per le pagine più comuni; una visualizzazione a barre che mostra le visualizzazioni di pagina per periodo fisso; e una visualizzazione a linee che mostra una visualizzazione con tendenze del tempo medio trascorso sul sito.</p> |
| **Riepilogo pagina** | Visualizza informazioni chiave su qualsiasi pagina delle tue proprietà. Mostra le visualizzazioni di pagina, una linea di tendenza, una visualizzazione di flusso e altro ancora.  <p>**Questo ti aiuta** a capire meglio come le persone interagiscono con una determinata pagina.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come analizzare le prestazioni della pagina in un periodo di tempo o capire meglio cosa guida il traffico verso la pagina.</p><p>Questo modello utilizza la metrica Visualizzazioni pagina. Utilizza anche la visualizzazione Linee e la visualizzazione Flusso.</p> |
| **Pagine di ingresso** | Visualizza le pagine principali a cui gli utenti accedono quando visitano il tuo sito per la prima volta. <p>**Questo ti aiuta** a capire meglio quali pagine generano maggior traffico verso il tuo sito o le prime impressioni dei visitatori sul tuo sito.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come ottimizzare l&#39;esperienza iniziale che le persone trovano sul sito o assicurarti che le pagine che le persone vedono per la prima volta quando accedono al tuo sito siano accoglienti e forniscano i collegamenti necessari ad altre aree del sito.</p><p>Questo modello utilizza la metrica Sessioni. Utilizza anche la visualizzazione a barre e la visualizzazione a forma libera della tabella.</p> |
| **Esci da pagine** | Visualizza le pagine principali a cui gli utenti accedono immediatamente prima di lasciare il sito.<p>**Questo ti aiuta** a capire meglio quali pagine allontanano le persone dal sito. </p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio aggiornare le pagine di uscita comuni per ottimizzare l&#39;esperienza che le persone ottengono prima di partire, oppure includere contenuti o collegamenti per incoraggiare le persone a rimanere sul tuo sito.</p><p>Questo modello utilizza la metrica Sessioni. Utilizza anche la visualizzazione a barre e la visualizzazione a forma libera della tabella.</p> |

### Web: Conversione {#web-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--productConversionReport"
>title="Modello Funnel di conversione prodotto"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-products-template"
>title="Visualizzare i prodotti con le prestazioni più elevate."
>abstract="**Questo ti aiuta** a capire meglio quali prodotti hanno più successo.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come aumentare i finanziamenti per i prodotti di successo e diminuire i finanziamenti per i prodotti di minor successo.<br/>Questo modello utilizza le metriche Visualizzazioni prodotto, Aggiunte carrello, Ordini, Entrate e Unità. Utilizza anche la dimensione Prodotto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartConversionReport"
>title="Visualizzare il numero di volte in cui le persone hanno eseguito eventi di pagamento chiave, ad esempio l&#39;aggiunta di articoli al carrello, la visualizzazione del carrello, la rimozione di articoli dal carrello e l&#39;estrazione."
>abstract="**Questo può aiutarti** a capire meglio quali parti del funnel del processo di pagamento che portano alla conversione e quali sono più soggette all&#39;abbandono del carrello.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio ridurre l&#39;attrito in determinati passaggi del processo di pagamento.<br/>Questo modello utilizza"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartsOvertimeReport"
>title="Visualizza il numero di persone che hanno aggiunto un prodotto al carrello."
>abstract="**Questo può aiutarti** a comprendere meglio il numero di persone che aggiungono un prodotto al carrello, rispetto al numero complessivo di prodotti che vengono aggiunti a un carrello.<br/>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio misurare l&#39;efficacia delle pagine dei tuoi prodotti.<br/>Questo modello utilizza la metrica Carrelli."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartViewsOvertimeReport"
>title="Visualizza il numero di volte in cui le persone hanno visualizzato il carrello."
>abstract="**Questo può aiutarti** a comprendere meglio l&#39;esperienza di pagamento nel tentativo di ridurre i tassi di abbandono del carrello o di analizzare il tempo tra le aggiunte al carrello e le estrazioni tra i diversi prodotti.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come offrire promozioni per prodotti che rimangono nei carrelli più a lungo e sono a maggior rischio di abbandono.<br/>Questo modello utilizza la metrica Visualizzazioni carrello."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartAdditionsOvertimeReport"
>title="Visualizza il numero di volte in cui le persone hanno aggiunto qualcosa al carrello."
>abstract="**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui l&#39;interesse del cliente per un prodotto è sufficientemente elevato da consentirne l&#39;aggiunta al carrello.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare i consigli di prodotto per tutti i clienti. Questo può essere fatto analizzando quali prodotti vengono spesso aggiunti agli stessi carrelli e suggerendo prodotti correlati in base agli articoli già nel carrello."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartRemovalsOvertimeReport"
>title="Visualizza il numero di volte in cui le persone hanno rimosso qualcosa dal carrello."
>abstract="**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui i clienti non sono più interessati a un prodotto, oppure può aiutarti a capire dove possono esistere problemi nel processo di pagamento.<br/>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio rimuovere eventuali barriere che potrebbero esistere nel processo di pagamento, ad esempio un&#39;esperienza utente complicata.<br/>Questo modello utilizza la metrica Rimozioni carrello."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--purchaseConversionReport"
>title="Modello funnel di conversione acquisto"
>abstract=""

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Funnel di conversione prodotto**] | <p>**Questo ti può aiutare** a comprendere meglio</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come </p><p>Questo modello utilizza |
| **Prodotti** | Scopri quali prodotti sono più determinanti per le metriche chiave, ad esempio i più venduti o i più visualizzati. <p>**Questo ti aiuta** a capire meglio quali prodotti hanno più successo.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come aumentare i finanziamenti per i prodotti di successo e diminuire i finanziamenti per i prodotti di minor successo.</p><p>Questo modello utilizza la metrica Ordini e la dimensione Prodotto. |
| **Prestazioni prodotto** | Visualizzare i prodotti con le prestazioni più elevate.<p>**Questo ti aiuta** a capire meglio quali prodotti hanno più successo.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come aumentare i finanziamenti per i prodotti di successo e diminuire i finanziamenti per i prodotti di minor successo.</p><p>Questo modello utilizza le metriche Visualizzazioni prodotto, Aggiunte carrello, Ordini, Ricavi e Unità. Utilizza anche la dimensione Prodotto. |
| **Funnel di conversione carrello** | Visualizzare il numero di volte in cui le persone hanno eseguito eventi di pagamento chiave, ad esempio l&#39;aggiunta di articoli al carrello, la visualizzazione del carrello, la rimozione di articoli dal carrello e l&#39;estrazione. <p>**Questo può aiutarti** a capire meglio quali parti del funnel del processo di pagamento che portano alla conversione e quali sono più soggette all&#39;abbandono del carrello.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio ridurre l&#39;attrito in determinati passaggi del processo di pagamento.</p><p>Questo modello utilizza |
| **Carrelli** | Visualizza il numero di persone che hanno aggiunto un prodotto al carrello.<p>**Questo può aiutarti** a comprendere meglio il numero di persone che aggiungono un prodotto al carrello, rispetto al numero complessivo di prodotti che vengono aggiunti a un carrello.</p><p>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio misurare l&#39;efficacia delle pagine dei tuoi prodotti.</p><p>Questo modello utilizza la metrica Carrelli. |
| **Visualizzazioni carrello** | Visualizza il numero di volte in cui le persone hanno visualizzato il carrello. <p>**Questo può aiutarti** a comprendere meglio l&#39;esperienza di pagamento nel tentativo di ridurre i tassi di abbandono del carrello o di analizzare il tempo tra le aggiunte al carrello e le estrazioni tra i diversi prodotti.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come offrire promozioni per prodotti che rimangono nei carrelli più a lungo e sono a maggior rischio di abbandono.</p><p>Questo modello utilizza la metrica Visualizzazioni carrello. |
| **Aggiunte carrello** | Visualizza il numero di volte in cui le persone hanno aggiunto qualcosa al carrello. <p>**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui l&#39;interesse del cliente per un prodotto è sufficientemente elevato da consentirne l&#39;aggiunta al carrello.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare i consigli di prodotto per tutti i clienti. Questo può essere fatto analizzando quali prodotti vengono spesso aggiunti agli stessi carrelli e suggerendo prodotti correlati in base agli articoli già nel carrello. |
| **Rimozioni carrello** | Visualizza il numero di volte in cui le persone hanno rimosso qualcosa dal carrello.<p>**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui i clienti non sono più interessati a un prodotto, oppure può aiutarti a capire dove possono esistere problemi nel processo di pagamento.</p><p>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio rimuovere eventuali barriere che potrebbero esistere nel processo di pagamento, ad esempio un&#39;esperienza utente complicata.</p><p>Questo modello utilizza la metrica Rimozioni carrello. |
| **Funnel di conversione acquisti** | <p>**Questo ti può aiutare** a comprendere meglio</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come </p><p>Questo modello utilizza |
| **Ricavi** | <!--duplicated in Most popular section-->Visualizza l&#39;importo monetario dei prodotti acquistati in tutti gli ordini.<p>**Questo può aiutarti** a capire meglio quali elementi dimensionali hanno contribuito ai ricavi, combinando la metrica Ricavi con qualsiasi dimensione. Ad esempio, puoi vedere le campagne principali (utilizzando la dimensione Codice di tracciamento) che hanno contribuito ai ricavi. </p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio regolare le campagne che non soddisfano gli obiettivi di ricavo previsti.</p><p>Questo modello utilizza la metrica Ricavi. |
| **Ordini** | <!--duplicated in Most popular section-->Visualizza il numero totale di eventi di acquisto effettuati sul sito. <p>**Questo può aiutarti** a capire meglio quali elementi dimensionali hanno contribuito a un ordine, combinando la metrica Ordini con qualsiasi dimensione. Ad esempio, puoi vedere le campagne principali (utilizzando la dimensione Codice di tracciamento) che hanno contribuito agli acquisti.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio regolare le campagne che non soddisfano i target di acquisto previsti. </p><p>Questo modello utilizza la metrica Ordini. |

### Web: audience {#web-audience}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--countryGeoReport"
>title="Visualizzare il paese da cui provengono le persone che visitano il sito."
>abstract="**Questo può aiutarti** a capire meglio da cosa provengono i visitatori dei paesi più popolari che visitano il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come utilizzare i dati per concentrarti sulle attività di marketing in questi paesi, o assicurarti che la tua esperienza sul sito sia ottimale in paesi che hanno diverse lingue primarie.<br/>Questo modello utilizza la dimensione Paesi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--stateGeoReport"
>title="Visualizza lo stato (negli Stati Uniti) da cui hanno avuto origine le persone che visitano il sito. È simile al modello Geo Regions, con la differenza che è specifico per gli Stati Uniti."
>abstract="**Questo può aiutarti** a comprendere meglio gli stati americani più popolari da cui provengono i visitatori che visitano il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come utilizzare i dati per concentrarsi sulle attività di marketing in questi stati.<br/>Questo modello utilizza la dimensione Stati Uniti."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--regionGeoReport"
>title="Visualizzare l&#39;area geografica da cui hanno avuto origine le persone che visitano il sito. Una regione è un&#39;area geografica più piccola di un paese ma più grande di una città. In alcuni paesi, una regione è uno stato, una provincia o una prefettura. In altre aree, è un paese costituente, un dipartimento o una regione metropolitana. "
>abstract="**Questo può aiutarti** a comprendere meglio le aree geografiche da cui provengono i visitatori più popolari che visitano il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste aree geografiche, oppure assicurarti che l&#39;esperienza del tuo sito sia ottimale nelle aree geografiche che hanno diverse lingue primarie. <br/>Questo modello utilizza le dimensioni ID(variabili/geocountry) e Region. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cityGeoReport"
>title="Visualizza la città da cui provengono le persone che visitano il sito."
>abstract="**Questo può aiutarti** a comprendere meglio le città più popolari da cui provengono i visitatori che visitano il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste città. <br/>Questo modello utilizza la dimensione Città"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dmaGeoReport"
>title="Visualizzare le aree di marketing designate (DMA) all’interno degli Stati Uniti da cui hanno avuto origine le persone che visitano il sito."
>abstract="**Questo può aiutarti** a comprendere meglio le aree geografiche da cui provengono i visitatori più popolari che visitano il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing nelle aree di maggior successo. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--languageRankedReport"
>title="Visualizza le lingue principali in cui i visitatori preferiscono visualizzare il contenuto."
>abstract="**Questo può aiutarti** a comprendere meglio le lingue preferite più frequentemente dai visitatori.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come concentrare le attività di localizzazione o di marketing per le lingue più popolari.<br/>Questo modello utilizza la dimensione Lingua."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-technology-template"
>title="Panoramica sulla tecnologia"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserRankedReport"
>title="Visualizza il nome e la versione dei principali browser utilizzati dagli utenti per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio i browser più comuni utilizzati dai visitatori.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando i browser principali. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.<br/>Questo modello utilizza la dimensione Browser."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserTypeRankedReport"
>title="Visualizza i nomi delle organizzazioni che hanno creato i browser principali utilizzati dagli utenti per accedere al sito. Questo è diverso dal modello Browser in quanto non elenca diverse versioni dello stesso browser come elementi dimensionali separati."
>abstract="**Questo ti aiuta** a comprendere meglio i browser più comuni utilizzati dai visitatori <br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando i browser principali. In questo modo è possibile massimizzare gli sforzi di controllo della qualità. <br/>Questo modello utilizza la dimensione Tipo di browser. "

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Utenti nuovi e ripetuti**] | Visualizza un confronto tra i visitatori nuovi e quelli ripetuti. <p>**Questo può aiutarti** a comprendere meglio l&#39;efficacia del tuo sito nel mantenere la fedeltà dei clienti o la velocità con cui acquisisci nuovi clienti.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio offrire incentivi per acquisti futuri ai nuovi visitatori per indurli a tornare.</p><!-- This template uses the --> |
| **ID persona/Spazio dei nomi** | <p>**Questo ti può aiutare** a comprendere meglio</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come </p><!-- This template uses the --> |
| **Panoramica sulla posizione** | Visualizza una panoramica della posizione del visitatore in una visualizzazione mappa.<p>**Questo può aiutarti** a capire meglio dove si trovano i visitatori che stanno visitando il tuo sito. </p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come concentrare le risorse di marketing nelle posizioni in cui visualizzi più interesse e opportunità.</p><!-- This template uses the --> |
| **Paesi geografici** | Visualizzare il paese da cui provengono le persone che visitano il sito.<p>**Questo può aiutarti** a capire meglio da cosa provengono i visitatori dei paesi più popolari che visitano il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come utilizzare i dati per concentrarti sulle attività di marketing in questi paesi, o assicurarti che la tua esperienza sul sito sia ottimale in paesi che hanno diverse lingue primarie.</p><p>Questo modello utilizza la dimensione Paesi. </p> |
| **Stati Geo USA** | Visualizza lo stato (negli Stati Uniti) da cui hanno avuto origine le persone che visitano il sito. È simile al modello Geo Regions, con la differenza che è specifico per gli Stati Uniti.<p>**Questo può aiutarti** a comprendere meglio gli stati americani più popolari da cui provengono i visitatori che visitano il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come utilizzare i dati per concentrarsi sulle attività di marketing in questi stati.</p><p>Questo modello utilizza la dimensione Stati Uniti. </p> |
| **Aree geografiche** | Visualizzare l&#39;area geografica da cui hanno avuto origine le persone che visitano il sito. Una regione è un&#39;area geografica più piccola di un paese ma più grande di una città. In alcuni paesi, una regione è uno stato, una provincia o una prefettura. In altre aree, è un paese costituente, un dipartimento o una regione metropolitana. <p>**Questo può aiutarti** a comprendere meglio le aree geografiche da cui provengono i visitatori più popolari che visitano il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste aree geografiche, oppure assicurarti che l&#39;esperienza del tuo sito sia ottimale nelle aree geografiche che hanno diverse lingue primarie. </p><p>Questo modello utilizza le dimensioni ID(variabili/geocountry) e Aree geografiche. </p> |
| **Città geografiche** | Visualizza la città da cui provengono le persone che visitano il sito. <p>**Questo può aiutarti** a comprendere meglio le città più popolari da cui provengono i visitatori che visitano il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste città. </p><p>Questo modello utilizza la dimensione Città. </p> |
| **Geo US DMA** | Visualizzare le aree di marketing designate (DMA) all’interno degli Stati Uniti da cui hanno avuto origine le persone che visitano il sito.<p>**Questo può aiutarti** a comprendere meglio le aree geografiche da cui provengono i visitatori più popolari che visitano il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing nelle aree di maggior successo. </p><!-- This template uses the --> |
| **Lingue** | Visualizza le lingue principali in cui i visitatori preferiscono visualizzare il contenuto. <p>**Questo può aiutarti** a comprendere meglio le lingue preferite più frequentemente dai visitatori.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come concentrare le attività di localizzazione o di marketing per le lingue più popolari.</p><p>Questo modello utilizza la dimensione Lingua.</p> |
| **Panoramica tecnologia** | <p>**Questo ti può aiutare** a comprendere meglio</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come </p><p>Questo modello utilizza </p> |
| **Browser** | Visualizza il nome e la versione dei principali browser utilizzati dagli utenti per accedere al tuo sito.<p>**Questo può aiutarti** a comprendere meglio i browser più comuni utilizzati dai visitatori.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando i browser principali. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.</p><p>Questo modello utilizza la dimensione Browser. </p> |
| **Tipi di browser** | Visualizza i nomi delle organizzazioni che hanno creato i browser principali utilizzati dagli utenti per accedere al sito. Questo è diverso dal modello Browser in quanto non elenca diverse versioni dello stesso browser come elementi dimensionali separati.<p>**Questo può aiutarti** a comprendere meglio i browser più comuni utilizzati dai visitatori</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando i browser principali. In questo modo è possibile massimizzare gli sforzi di controllo della qualità. </p><p>Questo modello utilizza la dimensione Tipo di browser. </p> |

### Web: Acquisizione {#web-acquisition}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--marketing-channel-overview-template"
>title="Quando si utilizza l’attribuzione personalizzata, questo modello mostra il modo in cui i visitatori arrivano sul sito."
>abstract="**Questo ti aiuta** a capire meglio quali dei tuoi canali di marketing sono più efficaci.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio investire di più in canali di marketing efficaci e disinvestire da canali di marketing meno influenti.<br/>Questo modello utilizza la dimensione ID(variables/marketingchannel) e la metrica Ricavi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelRankedReport"
>title="Visualizza il primo canale di marketing con cui un visitatore trova una corrispondenza durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita)."
>abstract="**Questo ti aiuta** a capire meglio quali canali di marketing indirizzano il traffico iniziale verso il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing nelle aree più efficaci.<br/>Questo modello utilizza la dimensione Canale di primo contatto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelDetailRankedReport"
>title="Visualizza i dettagli sul primo canale di marketing con cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita)."
>abstract="**Questo ti può aiutare** a capire meglio cosa ha contribuito all&#39;hit che corrisponde a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing &quot;Ricerca a pagamento&quot;, puoi utilizzare i dettagli del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing nelle aree più efficaci.<br/>Questo modello utilizza la dimensione Dettaglio canale di primo contatto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignConversionReport"
>title="Funnel di conversione campagna"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-campaign-performance-template"
>title="Visualizza i dettagli sulle prestazioni delle campagne di marketing."
>abstract="**Questo ti aiuta** a comprendere meglio i vari indicatori di successo associati alle campagne, come ricavi, visualizzazioni prodotti, ordini e così via.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio concentrare le attività di marketing sulle campagne che generano maggior fatturato. <br/>Questo modello utilizza la metrica Ricavi, la metrica Visualizzazioni prodotto, la metrica Aggiunte carrello, la metrica Ordini e la metrica Unità. Vengono inoltre utilizzate le dimensioni Codice di tracciamento e Dominio di riferimento."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-acquisition-template"
>title="Visualizza come il tuo sito web ottiene i visitatori."
>abstract="**Questo può aiutarti** a comprendere meglio i vari fattori che portano all&#39;acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing sui canali più efficaci.<br/>Questo modello utilizza la metrica Percentuale non recapitate e la metrica Rimbalzi. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchKeywordRankedReport"
>title="Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito, indipendentemente dal fatto che sia a pagamento o naturale."
>abstract="**Questo può aiutarti** a comprendere meglio le parole chiave che gli utenti usano nelle ricerche che generano traffico sul sito. <br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che stanno guidando il traffico del sito.<br/>Questo modello utilizza la dimensione Parola chiave di ricerca."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidKeywordRankedReport"
>title="Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito e corrispondenti al rilevamento di ricerche a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio le parole chiave che gli utenti usano nelle ricerche che generano traffico sul sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che stanno guidando il traffico del sito. <br/>Questo modello utilizza la dimensione Parola chiave di ricerca - Pagato. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalKeywordRankedReport"
>title="Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il tuo sito che non corrispondono al rilevamento di ricerche a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio le parole chiave che gli utenti usano nelle ricerche che generano traffico sul sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che stanno guidando il traffico del sito.<br/>Questo modello utilizza la dimensione Parola chiave di ricerca - Naturale. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchRankedReport"
>title="Visualizza i motori di ricerca utilizzati dai visitatori per raggiungere il tuo sito, indipendentemente dal fatto che sia a pagamento o naturale."
>abstract="**Questo può aiutarti** a comprendere meglio i motori di ricerca utilizzati dagli utenti che generano traffico sul sito. <br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come concentrare le tue attività SEO sui motori di ricerca che generano più traffico verso il sito.<br/>Questo modello utilizza la dimensione Motore di ricerca. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidRankedReport"
>title="Visualizza i motori di ricerca utilizzati dai visitatori per raggiungere il tuo sito, che corrispondono al rilevamento di ricerche a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio i motori di ricerca utilizzati dagli utenti che generano traffico sul sito.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come concentrare le tue attività SEO sui motori di ricerca che generano più traffico verso il sito. <br/>Questo modello utilizza la dimensione Motore di ricerca - Pagato."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalRankedReport"
>title="Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il tuo sito che non corrispondono al rilevamento di ricerche a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio i motori di ricerca utilizzati dagli utenti che generano traffico sul sito.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come concentrare le tue attività SEO sui motori di ricerca che generano più traffico verso il sito.<br/>Questo modello utilizza la dimensione Motore di ricerca - Naturale."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainRankedReport"
>title="Visualizza i domini su cui gli utenti fanno clic per raggiungere il tuo sito."
>abstract="**Questo ti aiuta** a capire meglio quali siti di terze parti indirizzano più traffico verso il tuo. Affinché l’elemento dimensione venga visualizzato, è necessario che nel sito esterno esista un collegamento e che un visitatore faccia clic su di esso.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come creare o regolare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali domini di riferimento. <br/>Questo modello utilizza la dimensione Dominio di riferimento."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainOriginalRankedReport"
>title="Visualizza il primo dominio di riferimento tramite il quale gli utenti hanno fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intera durata di vita dell’ID visitatore."
>abstract="**Questo può aiutarti** a capire meglio quali siti di terze parti originariamente indirizzano il traffico verso il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come creare o regolare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali domini di riferimento originali. <br/>Questo modello utilizza la dimensione Dominio di riferimento originale."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerRankedReport"
>title="Puoi vedere su quali URL si trovavano i visitatori quando facevano clic per raggiungere il tuo sito. Affinché l’elemento della dimensione venga visualizzato, è necessario che sull’URL esterno esista un collegamento e che un visitatore faccia clic su di esso."
>abstract="**Questo può aiutarti** a capire meglio quali URL specifici indirizzano il maggior traffico verso il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come creare o modificare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dagli URL principali. <br/>Questo modello utilizza la dimensione Dominio di riferimento.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerTypeRankedReport"
>title="Visualizza i canali generici attraverso i quali i visitatori hanno fatto clic per arrivare al sito. Adobe mantiene le regole per ogni canale. I canali possibili includono motori di ricerca, social network, altri siti web, disco rigido o e-mail."
>abstract="**Questo può aiutarti** a capire meglio quale tipo di referrer gestisce più traffico verso il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come creare o modificare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti da un determinato canale.<br/>Questo modello utilizza la dimensione Tipo referrer."

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Canali marketing**] > [!UICONTROL **Rapporto panoramica canale marketing**] | Quando si utilizza l’attribuzione personalizzata, questo modello mostra il modo in cui i visitatori arrivano sul sito.<p>**Questo ti aiuta** a capire meglio quali dei tuoi canali di marketing sono più efficaci.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio investire di più in canali di marketing efficaci e disinvestire da canali di marketing meno influenti.</p><p>Questo modello utilizza la dimensione ID(variables/marketingchannel) e la metrica Ricavi.</p> |
| [!UICONTROL **Canali marketing**] > [!UICONTROL **Canale marketing primo contatto**] | Visualizza il primo canale di marketing con cui un visitatore trova una corrispondenza durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita). <p>**Questo ti aiuta** a capire meglio quali canali di marketing indirizzano il traffico iniziale verso il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing nelle aree più efficaci.</p><p>Questo modello utilizza la dimensione Canale di primo contatto.</p> |
| [!UICONTROL **Canali Marketing**] > [!UICONTROL **Dettagli Canale Marketing Di Primo Contatto**] | Visualizza i dettagli sul primo canale di marketing con cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).<p>**Questo ti può aiutare** a capire meglio cosa ha contribuito all&#39;hit che corrisponde a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing &quot;Ricerca a pagamento&quot;, puoi utilizzare i dettagli del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing nelle aree più efficaci.</p><p>Questo modello utilizza la dimensione Dettaglio canale di primo contatto.</p> |
| [!UICONTROL **Canali marketing**] > [!UICONTROL **Canale marketing ultimo contatto**] | Visualizza il canale di marketing con cui un visitatore trova corrispondenza più recente durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).<p>**Questo ti può aiutare** a capire meglio quali canali di marketing indirizzano il traffico verso il tuo sito che dà luogo a conversioni.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing nelle aree più efficaci.</p><p>Questo modello utilizza la dimensione Canale di ultimo contatto.  </p> |
| [!UICONTROL **Canali Marketing**] > [!UICONTROL **Dettagli Canale Marketing Ultimo Contatto**] | Visualizza dettagli sul canale di marketing più recente con cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita)<p>**Questo ti può aiutare** a capire meglio cosa ha contribuito all&#39;hit che corrisponde a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing &quot;Ricerca a pagamento&quot;, puoi utilizzare i dettagli del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing nelle aree più efficaci. </p><p>Questo modello utilizza la dimensione Dettaglio canale di ultimo contatto. </p> |
| [!UICONTROL **Campagne**] > [!UICONTROL **Campagne (codice di tracciamento)**] | Visualizza i nomi dei codici di tracciamento sul tuo sito. Puoi inserire collegamenti con valori di parametri di stringhe di query diversi in posizioni diverse su Internet.<p>**Questo ti aiuta** a capire meglio quali collegamenti sono stati più efficaci nel traffico verso il tuo sito. L’aggiunta di stringhe di query del codice di tracciamento è comune nelle e-mail, negli annunci pubblicitari, nei post sui social media e in altre attività di marketing utilizzate dalla tua organizzazione</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio concentrare le attività di marketing sulle campagne che generano maggior fatturato.</p><p>Questo modello utilizza la dimensione Codice di tracciamento. </p> |
| [!UICONTROL **Campagne**] > [!UICONTROL **Funnel di conversione campagna**] | <p>**Questo ti può aiutare** a comprendere meglio</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come </p><p>Questo modello utilizza  </p> |
| [!UICONTROL **Campagne**] > [!UICONTROL **Prestazioni campagna**] | Visualizza i dettagli sulle prestazioni delle campagne di marketing.<p>**Questo ti aiuta** a comprendere meglio i vari indicatori di successo associati alle campagne, come ricavi, visualizzazioni prodotti, ordini e così via.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio concentrare le attività di marketing sulle campagne che generano maggior fatturato. </p><p>Questo modello utilizza la metrica Ricavi, la metrica Visualizzazioni prodotto, la metrica Aggiunte carrello, la metrica Ordini e la metrica Unità. Vengono inoltre utilizzate le dimensioni Codice di tracciamento e Dominio di riferimento. </p> |
| **Acquisizione Web** | Visualizza come il tuo sito web ottiene i visitatori.<p>**Questo può aiutarti** a comprendere meglio i vari fattori che portano all&#39;acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing sui canali più efficaci.</p><p>Questo modello utilizza le metriche Percentuale non recapitate e Percentuale non recapitate. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer.  </p> |
| **Parole chiave di ricerca - Tutto** | Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito, indipendentemente dal fatto che sia a pagamento o naturale. <p>**Questo può aiutarti** a comprendere meglio le parole chiave che gli utenti usano nelle ricerche che generano traffico sul sito. </p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che stanno guidando il traffico del sito.</p><p>Questo modello utilizza la dimensione Parola chiave di ricerca. </p> |
| **Parole chiave di ricerca - pagate** | Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito e corrispondenti al rilevamento di ricerche a pagamento.<p>**Questo può aiutarti** a comprendere meglio le parole chiave che gli utenti usano nelle ricerche che generano traffico sul sito.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che stanno guidando il traffico del sito. </p><p>Questo modello utilizza la dimensione Parola chiave di ricerca - A pagamento. </p> |
| **Parole chiave di ricerca - Naturale** | Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il tuo sito che non corrispondono al rilevamento di ricerche a pagamento.<p>**Questo può aiutarti** a comprendere meglio le parole chiave che gli utenti usano nelle ricerche che generano traffico sul sito.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che stanno guidando il traffico del sito.</p><p>Questo modello utilizza la dimensione Parola chiave di ricerca - Naturale. </p> |
| **Motori di ricerca - Tutti** | Visualizza i motori di ricerca utilizzati dai visitatori per raggiungere il tuo sito, indipendentemente dal fatto che sia a pagamento o naturale. <p>**Questo può aiutarti** a comprendere meglio i motori di ricerca utilizzati dagli utenti che generano traffico sul sito. </p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come concentrare le tue attività SEO sui motori di ricerca che generano più traffico verso il sito.</p><p>Questo modello utilizza la dimensione Motore di ricerca. </p> |
| **Motori di ricerca - Pagati** | Visualizza i motori di ricerca utilizzati dai visitatori per raggiungere il tuo sito, che corrispondono al rilevamento di ricerche a pagamento.<p>**Questo può aiutarti** a comprendere meglio i motori di ricerca utilizzati dagli utenti che generano traffico sul sito.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come concentrare le tue attività SEO sui motori di ricerca che generano più traffico verso il sito. </p><p>Questo modello utilizza la dimensione Motore di ricerca - Pagato. </p> |
| **Motori di ricerca - Naturale** | Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il tuo sito che non corrispondono al rilevamento di ricerche a pagamento.<p>**Questo può aiutarti** a comprendere meglio i motori di ricerca utilizzati dagli utenti che generano traffico sul sito.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come concentrare le tue attività SEO sui motori di ricerca che generano più traffico verso il sito.</p><p>Questo modello utilizza la dimensione Motore di ricerca - Naturale. </p> |
| **Domini di riferimento** | Visualizza i domini su cui gli utenti fanno clic per raggiungere il tuo sito.<p>**Questo ti aiuta** a capire meglio quali siti di terze parti indirizzano più traffico verso il tuo. Affinché l’elemento dimensione venga visualizzato, è necessario che nel sito esterno esista un collegamento e che un visitatore faccia clic su di esso.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come creare o regolare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali domini di riferimento. </p><p>Questo modello utilizza la dimensione Dominio di riferimento. </p> |
| **Domini di riferimento originali** | Visualizza il primo dominio di riferimento tramite il quale gli utenti hanno fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intera durata di vita dell’ID visitatore.<p>**Questo può aiutarti** a capire meglio quali siti di terze parti originariamente indirizzano il traffico verso il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come creare o regolare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali domini di riferimento originali. </p><p>Questo modello utilizza la dimensione Dominio di riferimento originale. </p> |
| **Riferimenti** | Puoi vedere su quali URL si trovavano i visitatori quando facevano clic per raggiungere il tuo sito. Affinché l’elemento della dimensione venga visualizzato, è necessario che sull’URL esterno esista un collegamento e che un visitatore faccia clic su di esso.  <p>**Questo può aiutarti** a capire meglio quali URL specifici indirizzano il maggior traffico verso il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come creare o modificare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dagli URL principali. </p><p>Questo modello utilizza la dimensione Dominio di riferimento </p><p>Questo modello utilizza la dimensione Referrer. </p> |
| **Tipi di riferimento** | Visualizza i canali generici attraverso i quali i visitatori hanno fatto clic per arrivare al sito. Adobe mantiene le regole per ogni canale. I canali possibili includono motori di ricerca, social network, altri siti web, disco rigido o e-mail.<p>**Questo può aiutarti** a capire meglio quale tipo di referrer gestisce più traffico verso il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come creare o modificare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti da un determinato canale.</p><p>Questo modello utilizza la dimensione Tipo referrer.</p> |

### Mobile: app mobile {#mobile-app}

<!-- add contextual help for Mobile app screens and mobile app actions -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-lifecycle-metrics-app-usage-template"
>title="Visualizza il numero di utenti, avvii e primi avvii nell&#39;app, nonché la durata media della sessione."
>abstract="**Questo ti aiuta** a capire meglio quanto viene utilizzata l&#39;app. <br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare le prestazioni dell&#39;app in modo che possano essere scalate in base alla quantità di utilizzo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-journeys"
>title="Visualizza i pattern di utilizzo principali per la tua app mobile."
>abstract="**Questo ti aiuta** a capire meglio come le persone usano la tua app. <br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare il modo in cui le persone possono passare da una schermata all&#39;altra per eseguire il targeting dei flussi di lavoro più comuni."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-key-metrics"
>title="Visualizza alcune delle metriche più comuni per le app mobili."
>abstract="**Questo può aiutarti** a comprendere meglio le prestazioni di base della tua app mobile.<br/>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio valutare lo stato e le prestazioni complessive dell&#39;app."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-messaging"
>title="Visualizza i dati sulle prestazioni per i messaggi in-app e push per la tua app."
>abstract="**Questo ti aiuta** a capire meglio come le persone utilizzano le funzionalità di messaggistica in-app e come le notifiche push indirizzino efficacemente il traffico verso la tua app.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare l&#39;esperienza di notifica push della messaggistica in-app."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-performance-template"
>title="Visualizza le prestazioni dell’app e dove gli utenti riscontrano problemi."
>abstract="**Questo può aiutarti** a capire meglio se gli utenti che usano la tua app riscontrano rallentamento o prestazioni ridotte. <br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come risolvere problemi esistenti o migliorare le prestazioni dell&#39;app prima che si verifichino dei problemi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-retention"
>title="Puoi vedere quali utenti sono i più fedeli all’app e cosa fanno all’interno dell’app."
>abstract="**Questo può aiutarti** a capire meglio come i tuoi utenti più fedeli stanno utilizzando la tua app.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio migliorare le tue attività di marketing per le funzionalità utilizzate dai tuoi utenti più fedeli."

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **App mobile Screens**] | Visualizza il numero di eventi, sessioni e persone associati a ciascuna schermata nell’app mobile.<p>**Questo può aiutarti** a capire meglio quali schermate del tuo sito sono più popolari.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare i contenuti sugli schermi più popolari.</p><p>Questo modello utilizza le metriche Eventi, Sessioni, Persone e Modifica percentuale. Utilizza anche la dimensione Titolo pagina.</p> |
| **Azioni app mobile** | Visualizza le azioni che gli utenti stanno intraprendendo sulla tua app mobile. <p>**Questo può aiutarti** a comprendere meglio come le persone usano la tua app e il valore che ricevono da essa.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come migliorare le funzionalità di sviluppo che si completano o migliorano rispetto a quelle più popolari.</p><p>Questo modello utilizza le metriche Eventi, Sessioni, Persone e Modifica percentuale. |
| **Utilizzo app mobile** | Visualizza il numero di utenti, avvii e primi avvii nell&#39;app, nonché la durata media della sessione.<p>**Questo ti aiuta** a capire meglio quanto viene utilizzata l&#39;app. </p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare le prestazioni dell&#39;app in modo che possano essere scalate in base alla quantità di utilizzo.</p><!-- This template uses the --> |
| **Percorsi di app mobili** | Visualizza i pattern di utilizzo principali per la tua app mobile. <p>**Questo ti aiuta** a capire meglio come le persone usano la tua app. </p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare il modo in cui le persone possono passare da una schermata all&#39;altra per eseguire il targeting dei flussi di lavoro più comuni. </p><!-- This template uses the --> |
| **Metriche app mobile** | Visualizza alcune delle metriche più comuni per le app mobili. <p>**Questo può aiutarti** a comprendere meglio le prestazioni di base della tua app mobile.</p><p>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio valutare lo stato e le prestazioni complessive dell&#39;app.</p><!-- This template uses the --> |
| **Messaggistica app mobile** | Visualizza i dati sulle prestazioni per i messaggi in-app e push per la tua app.<p>**Questo ti aiuta** a capire meglio come le persone utilizzano le funzionalità di messaggistica in-app e come le notifiche push indirizzino efficacemente il traffico verso la tua app.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare l&#39;esperienza di notifica push della messaggistica in-app.</p><!-- This template uses the --> |
| **Prestazioni app mobile** | Visualizza le prestazioni dell’app e dove gli utenti riscontrano problemi. <p>**Questo può aiutarti** a capire meglio se gli utenti che usano la tua app riscontrano rallentamento o prestazioni ridotte. </p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come risolvere problemi esistenti o migliorare le prestazioni dell&#39;app prima che si verifichino dei problemi.</p><!-- This template uses the --> |
| **Conservazione app mobile** | Puoi vedere quali utenti sono i più fedeli all’app e cosa fanno all’interno dell’app. <p>**Questo può aiutarti** a capire meglio come i tuoi utenti più fedeli stanno utilizzando la tua app.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio migliorare le tue attività di marketing per le funzionalità utilizzate dai tuoi utenti più fedeli.</p><!-- This template uses the --> |

### Mobile: informazioni dispositivo mobile {#mobile-devices}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileCarrierRankedReport"
>title="Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili.utilizzati dagli utenti per accedere al sito."
>abstract="**Questo può aiutarti** a capire meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio personalizzare la distribuzione dei contenuti in base alle funzionalità di rete di diversi gestori per garantire un&#39;esperienza utente fluida.<br/>Questo modello utilizza la dimensione Operatore mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileDeviceNameRankedReport"
>title="Visualizza la marca e il modello dei dispositivi mobili utilizzati dagli utenti per accedere al tuo sito."
>abstract="**Questo può aiutarti** a capire meglio quali dispositivi mobili sono più popolari nella tua base di utenti.<br/>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio ottimizzare il rendering del sito per i dispositivi mobili più comuni.<br/>Questo modello utilizza la dimensione Nome dispositivo mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileDeviceTypeRankedReport"
>title="Visualizza i tipi di dispositivi mobili utilizzati dagli utenti per accedere al sito, ad esempio telefoni e tablet."
>abstract="**Questo può aiutarti** a comprendere meglio i vari tipi di dispositivi mobili che vengono utilizzati per accedere al tuo sito.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come ottimizzare il tuo sito per i tipi di dispositivi mobili più utilizzati.<br/>Questo modello utilizza la dimensione Tipo di dispositivo mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileManufacturerRankedReport"
>title="Visualizza quali produttori producono i dispositivi mobili utilizzati dagli utenti per accedere al tuo sito, ad esempio Apple e Samsung."
>abstract="**Questo può aiutarti** a capire meglio quali produttori sono più popolari nella tua base di utenti.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio personalizzare la distribuzione dei contenuti in base alle capacità di diversi produttori per garantire un&#39;esperienza utente fluida.<br/>Questo modello utilizza la dimensione Produttore di dispositivi mobili."

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Gestore di telefonia mobile**] | Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili.utilizzati dagli utenti per accedere al sito.<p>**Questo può aiutarti** a capire meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio personalizzare la distribuzione dei contenuti in base alle funzionalità di rete di diversi gestori per garantire un&#39;esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Operatore mobile.</p> |
| **Dispositivi mobili** | Visualizza la marca e il modello dei dispositivi mobili utilizzati dagli utenti per accedere al tuo sito.<p>**Questo può aiutarti** a capire meglio quali dispositivi mobili sono più popolari nella tua base di utenti.</p><p>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio ottimizzare il rendering del sito per i dispositivi mobili più comuni.</p><p>Questo modello utilizza la dimensione Nome dispositivo mobile.</p> |
| **Tipo di dispositivo mobile** | Visualizza i tipi di dispositivi mobili utilizzati dagli utenti per accedere al sito, ad esempio telefoni e tablet.<p>**Questo può aiutarti** a comprendere meglio i vari tipi di dispositivi mobili che vengono utilizzati per accedere al tuo sito.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come ottimizzare il tuo sito per i tipi di dispositivi mobili più utilizzati.</p><p>Questo modello utilizza la dimensione Tipo di dispositivo mobile.</p> |
| **Produttore** | Visualizza quali produttori producono i dispositivi mobili utilizzati dagli utenti per accedere al tuo sito, ad esempio Apple e Samsung.<p>**Questo può aiutarti** a capire meglio quali produttori sono più popolari nella tua base di utenti.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio personalizzare la distribuzione dei contenuti in base alle capacità di diversi produttori per garantire un&#39;esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Produttore di dispositivi mobili.</p> |

### Suddivisione del tempo {#time-parting}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--minuteOfHour"
>title="Visualizza il numero di eventi, sessioni e persone sul sito, suddivisi per minuto. Ad esempio, in un rapporto con un arco temporale di reporting di un singolo giorno, il primo minuto di ogni ora del giorno viene raggruppato nello stesso elemento dimensionale."
>abstract="**Questo può aiutarti** a comprendere meglio le tendenze a livello granulare.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio ottimizzare le risorse per i momenti di picco, fino al minuto.<br/>Questo modello utilizza la dimensione Minuto dell&#39;ora."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--hourOfDay"
>title="Visualizza eventi, sessioni e persone sul sito, suddivisi per ora del giorno. Ad esempio, se un rapporto si estende dal 1° gennaio al 7 gennaio, la prima ora di ogni giorno viene raggruppata nello stesso elemento dimensionale."
>abstract="**Questo può aiutarti** a comprendere meglio l&#39;ora del giorno in cui il tuo sito viene visitato più frequentemente e meno frequentemente.<br/>**In base alle informazioni acquisite, è possibile** eseguire un&#39;operazione qualsiasi, ad esempio assegnare più risorse di elaborazione al sito durante le ore con traffico elevato.<br/>Questo modello utilizza la dimensione Ora del giorno."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--am-pm"
>title="Visualizza eventi, sessioni e persone sul tuo sito, suddivisi per AM e PM. Ad esempio, se un rapporto si estende dal 1° gennaio al 7 gennaio, le ore AM di ogni giorno sono raggruppate nello stesso elemento dimensionale."
>abstract="***Questo ti aiuta** a comprendere meglio l&#39;ora del giorno in cui il tuo sito viene visitato più frequentemente e meno frequentemente.<br/>**In base alle informazioni acquisite, è possibile** eseguire un&#39;operazione qualsiasi, ad esempio assegnare più risorse di elaborazione al sito durante le ore con traffico elevato.<br/>Questo modello utilizza la dimensione AM/PM."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfWeek"
>title="Visualizza eventi, sessioni e persone sul tuo sito, suddivisi per giorno della settimana. Ad esempio, in un rapporto che si estende sul mese di gennaio, ogni giorno della settimana è raggruppato nello stesso elemento dimensionale."
>abstract="**Questo può aiutarti** a capire meglio quali giorni della settimana il tuo sito viene visitato più frequentemente e meno frequentemente.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come assegnare al call center personale più appropriato per i giorni con traffico elevato.<br/>Questo modello utilizza la dimensione Giorno della settimana."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfMonth"
>title="Visualizza eventi, sessioni e persone sul sito, suddivisi per giorno del mese. Ad esempio, se un rapporto si estende su un anno intero, ogni giorno del mese viene raggruppato nello stesso elemento dimensionale."
>abstract="**Questo può aiutarti** a capire meglio quali giorni di ogni mese il tuo sito viene visitato più frequentemente e meno frequentemente.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come assegnare al call center personale più appropriato per i giorni con traffico elevato.<br/>Questo modello utilizza la dimensione Giorno del mese."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfYear"
>title="Visualizza eventi, sessioni e persone sul tuo sito, suddivisi per giorno dell’anno. Ad esempio, se un rapporto si estende su più anni, ogni giorno dell’anno viene raggruppato nello stesso elemento dimensionale."
>abstract="**Questo può aiutarti** a capire meglio quali giorni di ogni anno il tuo sito viene visitato più frequentemente e meno frequentemente.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come assegnare al call center personale più appropriato per i giorni con traffico elevato.<br/>Questo modello utilizza la dimensione Giorno dell&#39;anno."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--weekdayWeekend"
>title="Visualizza eventi, sessioni e persone sul tuo sito, suddivisi per giorni feriali e weekend. Ad esempio, in un rapporto che si estende sul mese di gennaio, i giorni feriali e i fine settimana sono raggruppati in elementi dimensionali separati."
>abstract="**Questo può aiutarti** a comprendere meglio le differenze nel traffico del sito nei giorni feriali rispetto ai fine settimana.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come fare più personale al call center nei fine settimana, se il rapporto indica che i fine settimana sono più occupati dei giorni feriali.<br/>Questo modello utilizza la dimensione Giorno feriale/Fine settimana."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--weekOfYear"
>title="Visualizza eventi, sessioni e persone sul sito, suddivisi per settimana dell’anno. Ad esempio, se un rapporto si estende su più anni, ogni settimana viene raggruppata nello stesso elemento dimensionale."
>abstract="**Questo può aiutarti** a capire meglio quali settimane dell&#39;anno il tuo sito viene visitato più frequentemente e meno frequentemente.<br/>**In base a ciò che hai appreso, potresti** fare più cose, come personale del call center più appropriato per le settimane a traffico elevato, ad esempio durante le vacanze.<br/>Questo modello utilizza la dimensione Settimana dell&#39;anno."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--monthOfYear"
>title="Visualizza eventi, sessioni e persone sul sito, suddivisi per mese dell’anno. Ad esempio, se un rapporto si estende su più anni, ogni mese viene raggruppato nello stesso elemento dimensionale."
>abstract="**Questo può aiutarti** a capire meglio in quali mesi il tuo sito viene visitato più frequentemente e meno frequentemente.<br/>**In base a ciò che hai appreso, potresti** fare più cose, come personale del call center più appropriato per i mesi a traffico elevato, ad esempio durante le vacanze.<br/>Questo modello utilizza la dimensione Mese dell&#39;anno."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--quarterOfYear"
>title="Visualizza eventi, sessioni e persone sul tuo sito, suddivisi per trimestre dell&#39;anno. Ad esempio, se un rapporto si estende su più anni, ogni trimestre viene raggruppato nello stesso elemento dimensionale."
>abstract="**Questo può aiutarti** a capire meglio quali sono i quartieri in cui il tuo sito viene visitato più frequentemente e meno frequentemente.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come ad esempio il tempo di lancio dei prodotti per aumentare i trimestri a traffico storicamente basso.<br/>Questo modello utilizza la dimensione Trimestre dell&#39;anno."

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Minuto dell&#39;Ora**] | Visualizza il numero di eventi, sessioni e persone sul sito, suddivisi per minuto. Ad esempio, in un rapporto con un arco temporale di reporting di un singolo giorno, il primo minuto di ogni ora del giorno viene raggruppato nello stesso elemento dimensionale.<p>**Questo può aiutarti** a comprendere meglio le tendenze a livello granulare.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio ottimizzare le risorse per i momenti di picco, fino al minuto.</p><p>Questo modello utilizza la dimensione Minuto dell’ora.</p> |
| **Ora del giorno** | Visualizza eventi, sessioni e persone sul sito, suddivisi per ora del giorno. Ad esempio, se un rapporto si estende dal 1° gennaio al 7 gennaio, la prima ora di ogni giorno viene raggruppata nello stesso elemento dimensionale.<p>**Questo può aiutarti** a comprendere meglio l&#39;ora del giorno in cui il tuo sito viene visitato più frequentemente e meno frequentemente.</p><p>**In base alle informazioni acquisite, è possibile** eseguire un&#39;operazione qualsiasi, ad esempio assegnare più risorse di elaborazione al sito durante le ore con traffico elevato.</p><p>Questo modello utilizza la dimensione Ora del giorno.</p> |
| **AM/PM** | Visualizza eventi, sessioni e persone sul tuo sito, suddivisi per AM e PM. Ad esempio, se un rapporto si estende dal 1° gennaio al 7 gennaio, le ore AM di ogni giorno sono raggruppate nello stesso elemento dimensionale.<p>**Questo ti aiuta** a comprendere meglio l&#39;ora del giorno in cui il tuo sito viene visitato più frequentemente e meno frequentemente.</p><p>**In base alle informazioni acquisite, è possibile** eseguire un&#39;operazione qualsiasi, ad esempio assegnare più risorse di elaborazione al sito durante le ore con traffico elevato.</p><p>Questo modello utilizza la dimensione AM/PM.</p> |
| **Giorno della settimana** | Visualizza eventi, sessioni e persone sul tuo sito, suddivisi per giorno della settimana. Ad esempio, in un rapporto che si estende sul mese di gennaio, ogni giorno della settimana è raggruppato nello stesso elemento dimensionale. <p>**Questo può aiutarti** a capire meglio quali giorni della settimana il tuo sito viene visitato più frequentemente e meno frequentemente.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come assegnare al call center personale più appropriato per i giorni con traffico elevato.</p><p>Questo modello utilizza la dimensione Giorno della settimana.</p> |
| **Giorno del mese** | Visualizza eventi, sessioni e persone sul sito, suddivisi per giorno del mese. Ad esempio, se un rapporto si estende su un anno intero, ogni giorno del mese viene raggruppato nello stesso elemento dimensionale. <p>**Questo può aiutarti** a capire meglio quali giorni di ogni mese il tuo sito viene visitato più frequentemente e meno frequentemente.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come assegnare al call center personale più appropriato per i giorni con traffico elevato.</p><p>Questo modello utilizza la dimensione Giorno del mese.</p> |
| **Giorno dell&#39;anno** | Visualizza eventi, sessioni e persone sul tuo sito, suddivisi per giorno dell’anno. Ad esempio, se un rapporto si estende su più anni, ogni giorno dell’anno viene raggruppato nello stesso elemento dimensionale. <p>**Questo può aiutarti** a capire meglio quali giorni di ogni anno il tuo sito viene visitato più frequentemente e meno frequentemente.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come assegnare al call center personale più appropriato per i giorni con traffico elevato.</p><p>Questo modello utilizza la dimensione Giorno dell’anno.&lt;/> |
| **Giorno feriale/Fine settimana** | Visualizza eventi, sessioni e persone sul tuo sito, suddivisi per giorni feriali e weekend. Ad esempio, in un rapporto che si estende sul mese di gennaio, i giorni feriali e i fine settimana sono raggruppati in elementi dimensionali separati. <p>**Questo può aiutarti** a comprendere meglio le differenze nel traffico del sito nei giorni feriali rispetto ai fine settimana.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come fare più personale al call center nei fine settimana, se il rapporto indica che i fine settimana sono più occupati dei giorni feriali.</p><p>Questo modello utilizza la dimensione Giorno feriale/Fine settimana.</p> |
| **Settimana dell&#39;anno** | Visualizza eventi, sessioni e persone sul sito, suddivisi per settimana dell’anno. Ad esempio, se un rapporto si estende su più anni, ogni settimana viene raggruppata nello stesso elemento dimensionale.<p>**Questo può aiutarti** a capire meglio quali settimane dell&#39;anno il tuo sito viene visitato più frequentemente e meno frequentemente.</p><p>**In base a ciò che hai appreso, potresti** fare più cose, come personale del call center più appropriato per le settimane a traffico elevato, ad esempio durante le vacanze.</p><p>Questo modello utilizza la dimensione Settimana dell’anno.</p> |
| **Mese dell&#39;anno** | Visualizza eventi, sessioni e persone sul sito, suddivisi per mese dell’anno. Ad esempio, se un rapporto si estende su più anni, ogni mese viene raggruppato nello stesso elemento dimensionale.<p>**Questo può aiutarti** a capire meglio in quali mesi il tuo sito viene visitato più frequentemente e meno frequentemente.</p><p>**In base a ciò che hai appreso, potresti** fare più cose, come personale del call center più appropriato per i mesi a traffico elevato, ad esempio durante le vacanze.</p><p>Questo modello utilizza la dimensione Mese dell’anno.</p> |
| **Trimestre dell&#39;anno** | Visualizza eventi, sessioni e persone sul tuo sito, suddivisi per trimestre dell&#39;anno. Ad esempio, se un rapporto si estende su più anni, ogni trimestre viene raggruppato nello stesso elemento dimensionale.<p>**Questo può aiutarti** a capire meglio quali sono i quartieri in cui il tuo sito viene visitato più frequentemente e meno frequentemente.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come ad esempio il tempo di lancio dei prodotti per aumentare i trimestri a traffico storicamente basso.</p><p>Questo modello utilizza la dimensione Trimestre dell’anno.</p> |

### Cross-Channel {#cross-channel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--multiChannelOverview"
>title="Visualizzare la distribuzione del traffico su più canali."
>abstract="**Questo può aiutarti** a capire meglio quali canali indirizzano con maggior successo il traffico e il coinvolgimento. <br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing sui canali che stanno ottenendo il massimo ritorno sull&#39;investimento.<br/>Questo modello utilizza le metriche utente, sessione ed evento."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--callCenterDeflection"
>title="Visualizzare come il traffico web influisce sul traffico del call center."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto self-service sul tuo sito web stia deviando il traffico verso il tuo call center.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare i contenuti self-service per ridurre il traffico verso il call center, o misurare il ROI dei contenuti self-service calcolando la quantità risparmiata attraverso meno chiamate di supporto.<br/>Questo modello utilizza le metriche Sessioni Web, Sessioni app mobile e Sessioni Web+App cross-channel."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--webAppTemplate"
>title="Visualizzare il traffico web e quello mobile insieme."
>abstract="**Questo ti aiuta** a comprendere meglio la distribuzione del traffico web e mobile sul tuo sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio dedicare più risorse all&#39;esperienza della tua app mobile quando raggiunge un certo livello di traffico.<br/>Questo modello utilizza le metriche Sessioni Web, Sessioni app mobile e Sessioni Web+App cross-channel."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--onlineOffline"
>title="Visualizza il traffico online e offline insieme."
>abstract="**Questo può aiutarti** a comprendere meglio la distribuzione del traffico online e offline sul tuo sito.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio dedicare più risorse alla tua esperienza online quando raggiunge un certo livello di traffico."

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Panoramica multicanale**] | Visualizzare la distribuzione del traffico su più canali. <p>**Questo può aiutarti** a capire meglio quali canali indirizzano con maggior successo il traffico e il coinvolgimento. </p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing sui canali che stanno ottenendo il massimo ritorno sull&#39;investimento.</p><p>Questo modello utilizza le metriche utente, sessione ed evento.</p> |
| **Deflessione del call center (Web+Call Center)** | Visualizzare come il traffico web influisce sul traffico del call center.<p>**Questo può aiutarti** a comprendere meglio come il contenuto self-service sul tuo sito web stia deviando il traffico verso il tuo call center.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare i contenuti self-service per ridurre il traffico verso il call center, o misurare il ROI dei contenuti self-service calcolando la quantità risparmiata attraverso meno chiamate di supporto.</p><p>Questo modello utilizza le metriche Sessioni Web, Sessioni app mobile e Sessioni Web+App cross-channel.</p> |
| **Web+App** | Visualizzare il traffico web e quello mobile insieme.<p>**Questo ti aiuta** a comprendere meglio la distribuzione del traffico web e mobile sul tuo sito.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio dedicare più risorse all&#39;esperienza della tua app mobile quando raggiunge un certo livello di traffico.</p><p>Questo modello utilizza le metriche Sessioni Web, Sessioni app mobile e Sessioni Web+App cross-channel.</p> |
| **Online/Offline** | Visualizza il traffico online e offline insieme.<p>**Questo può aiutarti** a comprendere meglio la distribuzione del traffico online e offline sul tuo sito.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio dedicare più risorse alla tua esperienza online quando raggiunge un certo livello di traffico.</p><!-- This template uses the ... --> |

### Altri canali {#other-channels}

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Dashboard del call center**] | <p>**Questo ti può aiutare** a comprendere meglio</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come </p><p>Questo modello utilizza |
| **POS/Offline** | Visualizza i dati sulle transazioni POS (Point of Sale), inclusi i ricavi ottenuti, gli ordini effettuati e le unità vendute. Questo modello include anche visualizzazioni che visualizzano informazioni sui negozi principali, i prodotti principali e le categorie di prodotti principali, nonché sulle vendite online e offline. <p>**Questo ti aiuta** a capire meglio quali sono i tuoi prodotti più venduti nel punto vendita e online.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio assegnare più risorse di marketing ai tuoi prodotti e canali dalle prestazioni più elevate.</p><p>Questo modello utilizza le metriche Utenti, Ricavi e Ordini.</p> |
| **E-mail/AJO** | <p>**Questo ti può aiutare** a comprendere meglio</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come </p><p>Questo modello utilizza |
| **Sondaggio** | Visualizzare il coinvolgimento degli utenti nei sondaggi. Visualizza il numero di avvii e completamenti, le domande e risposte principali e il numero di partecipanti nuovi rispetto a quelli ripetuti.<p>**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento e il tasso di successo dei tuoi sondaggi.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio regolare i sondaggi futuri per ottenere una migliore partecipazione.</p><p>Questo modello utilizza le metriche Utenti, Eventi, Inizio sondaggio, Completamento sondaggio e Tasso di completamento sondaggio.</p> |

### AJO {#AJO-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-campaign"
>title="Visualizza le metriche essenziali per le campagne Journey Optimizer, tra cui campagne e-mail, sperimentazione, in-app, SMS e altro ancora."
>abstract="**Questo ti aiuta** a comprendere meglio dettagli quali il numero di clic e il numero di messaggi inviati, offrendo una visione completa dell&#39;efficacia della tua campagna e del livello di coinvolgimento.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio modificare le campagne in base ai livelli di coinvolgimento del pubblico di destinazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-journey"
>title="Visualizzare le metriche essenziali per i percorsi Journey Optimizer, inclusi percorsi e-mail, sperimentazione, in-app, SMS e altro ancora."
>abstract="**Questo ti aiuta** a comprendere meglio dettagli quali il numero di clic e il numero di messaggi inviati, offrendo una visione completa dell&#39;efficacia e del livello di coinvolgimento del tuo percorso.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio modificare le campagne in base ai livelli di coinvolgimento del pubblico di destinazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-landing-page"
>title="Visualizzare il comportamento degli utenti, i pattern di coinvolgimento, i tassi di conversione e altre metriche chiave."
>abstract="**Questo può aiutarti** a comprendere meglio l&#39;efficacia della tua pagina di destinazione. <br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio ottimizzare le prestazioni della pagina di destinazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-channel"
>title="Visualizza un riepilogo completo delle metriche di traffico e coinvolgimento per tutte le campagne e i percorsi all’interno del tuo ambiente."
>abstract="**Questo ti può aiutare** a comprendere meglio l&#39;efficacia di alto livello delle tue campagne e dei tuoi percorsi. <br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio modificare le campagne e i percorsi in base ai livelli di coinvolgimento del pubblico di destinazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-subscription"
>title="Visualizzare gli abbonamenti e gli annullamenti degli abbonamenti dei profili associati a determinati elenchi."
>abstract="**Questo ti può aiutare** a comprendere meglio l&#39;efficacia delle diverse campagne e iniziative di abbonamento nel promuovere il coinvolgimento e le conversioni.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio regolare le campagne di abbonamento in base ai livelli di coinvolgimento del pubblico di destinazione."

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Campagne AJO**] | Visualizza le metriche essenziali per le campagne Journey Optimizer, tra cui campagne e-mail, sperimentazione, in-app, SMS e altro ancora.<p>**Questo ti aiuta** a comprendere meglio dettagli quali il numero di clic e il numero di messaggi inviati, offrendo una visione completa dell&#39;efficacia della tua campagna e del livello di coinvolgimento.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio modificare le campagne in base ai livelli di coinvolgimento del pubblico di destinazione.</p> |
| **Percorsi AJO** | Visualizzare le metriche essenziali per i percorsi Journey Optimizer, inclusi percorsi e-mail, sperimentazione, in-app, SMS e altro ancora.<p>**Questo ti aiuta** a comprendere meglio dettagli quali il numero di clic e il numero di messaggi inviati, offrendo una visione completa dell&#39;efficacia e del livello di coinvolgimento del tuo percorso.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio modificare le campagne in base ai livelli di coinvolgimento del pubblico di destinazione.</p> |
| **Pagine di destinazione di AJO** | Visualizzare il comportamento degli utenti, i pattern di coinvolgimento, i tassi di conversione e altre metriche chiave.<p>**Questo può aiutarti** a comprendere meglio l&#39;efficacia della tua pagina di destinazione. </p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio ottimizzare le prestazioni della pagina di destinazione.</p> |
| **Rapporto Panoramica di AJO** | Visualizza un riepilogo completo delle metriche di traffico e coinvolgimento per tutte le campagne e i percorsi all’interno del tuo ambiente.<p>**Questo ti può aiutare** a comprendere meglio l&#39;efficacia di alto livello delle tue campagne e dei tuoi percorsi. </p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio modificare le campagne e i percorsi in base ai livelli di coinvolgimento del pubblico di destinazione.</p> |
| **Iscrizioni AJO** | Visualizzare gli abbonamenti e gli annullamenti degli abbonamenti dei profili associati a determinati elenchi.<p>**Questo ti può aiutare** a comprendere meglio l&#39;efficacia delle diverse campagne e iniziative di abbonamento nel promuovere il coinvolgimento e le conversioni.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio regolare le campagne di abbonamento in base ai livelli di coinvolgimento del pubblico di destinazione.</p> |


<!-- deleted: 

| [!UICONTROL **Real-Time**] | View the dimensions and metrics that are currently being collected on your site. <p>**This can help you** better understand what is trending on your site.</p><p>**Based on what you learn, you might** respond to and actively manage the performance of your current marketing content and campaigns.</p> <p>This template uses the [Real-time report](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md).</p> | 
| [!UICONTROL **Fallout**] | View where people leave or continue through a predefined sequence of pages.<p>**This can help you** better understand where people are falling out of the user journey.</p><p>**Based on what you learn, you might** do any number of things, like analyze conversion rates through specific processes on your site (such as a purchase or registration process), or analyze correlations between events on your site. (For example, what percentage of people who looked at your privacy policy went on to purchase a product.) You can also use this template to perform side-by-side comparisons of two different segments in the same report.</p> <p>This template uses the [Fallout visualization](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md).</p> | 
| [!UICONTROL **Cross-device analysis**] | View which devices people used across all points of the journey.<p>**This can help you** better understand how many people interact with your brand, the types of devices they use, and how their use of multiple devices affects their experience. For example, how often do people begin a task on a mobile device and then later move to a desktop to complete a task? What are the most common paths users take from one device to another? Where do they drop out? Where do they succeed? And so forth.</p><p>**Based on what you learn, you might** do any number of things, like optimize certain parts of the user journey for a mobile experience.</p> <p>This template uses the [Flow visualization](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), [Fallout visualization](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md), [Cohort analysis](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), [the People metric](/help/components/metrics/people.md), and [the Unique devices metric](/help/components/metrics/unique-devices.md).</p> |
| [!UICONTROL **Web retention**] | View who your loyal users are and what they are doing on your site.<p>**This can help you** better understand the number of times the average person visits your site, the frequency with which people return to the site, and the number of days between return visits.</p><p>**Based on what you learn, you might** do any number of things, like analyze what content is most effective at bringing people back to the site.<p>This template uses the [Visits metric](/help/components/metrics/visits.md) and the [Unique visitors metric](/help/components/metrics/unique-visitors.md).</p> | 
| [!UICONTROL **Streaming Media Consumption**] | View  trends and top metrics of media consumption across all digital devices.<p>**This can help you** better understand the number of times the average person visits your site, the frequency with which people return to the site, and the number of days between return visits.</p><p>**Based on what you learn, you might** do any number of things, like analyze what content is most effective at bringing people back to the site.<p>This template uses the [Visits metric](/help/components/metrics/visits.md) and the [Unique visitors metric](/help/components/metrics/unique-visitors.md).</p> | 

-->

<!--

Ignore below this 

| Menu item | Reports under this menu item |
| --- | --- | 
| **[!UICONTROL Most Popular]** | <ul><li>Training Tutorial (Pre-existing Workspace template)</li><li>Pages (What are my top pages?)</li><li>Page views (How many page views am I generating?)</li><li>Visits (How many visits am I getting?)</li><li>Visitors (How many visitors am I getting?)</li><li>Key metrics (How are my most important metrics performing?)</li><li>Site sections (Which sections of my site generated the most page views?)</li><li>Real-Time (What is trending on my site, and why?)</li><li>Next page (What are the next pages my visitors go to?)</li><li>Previous page (What are the previous pages my visitors went to?)</li><li>Campaigns (What campaigns are driving my key metrics?)</li><li>Products (What products are driving my key metrics?)</li><li>Last touch channel (Which last touch channel is performing best?</li><li>Last touch channel detail (Which specific last touch channel is outperforming others?)</li><li>Revenue (How is my revenue performing?)</li><li>Orders (How are my orders performing?)</li><li>Units (How many units am I selling?)</li></ul> | 
| **[!UICONTROL Engagement]** | <ul><li>Key metrics (How are my most important metrics performing?)</li><li>Page views (How many page views am I generating?)</li><li>Pages (What are my top pages?)</li><li>Visits (How many visits am I getting?)</li><li>Visitors (How many visitors am I getting?)</li><li>Time spent per visit (How much time do my users spend per visit?)</li><li>Time prior to event (How much time do my users spend prior to a success event?)</li><li>Site sections (Which sections of my site generated the most page views?</li><li>Web content consumption (Which content is consumed most and is engaging users?)</li><li>Media content consumption (Which content is consumed most and is engaging users?)</li><li>Next and previous page flow (What are/were the next/previous paths my visitors take/took?)</li><li>Fallout (Where am I seeing fallout through my digital properties?)</li><li>Cross-device analysis (Using cross-device analysis in Analysis Workspace)</li><li>Web retention (Who are my loyal users and what do they do?)</li><li>Media audio consumption (What are trends and top metrics of audio consumption?)</li><li>Media recency, frequency, loyalty (Who are my loyal readers?)</li><li>Page analysis > Reloads (Which pages generate the most reloads?)</li><li>Page analysis > Time spent on page (How much time do my users spend on my pages?)</li><li>Entries & exits > Entry pages (What are my top entry pages?)</li><li>Entries & exits > Original entry pages (What page did my visitor originally enter from?)</li><li>Entries & exits > Single-page visits (Which pages generated the most single-page visits?)</li><li>Entries & exits > Exit pages (What are my top exit pages?)</li><li>Page Analysis > Page summary</li></ul> |
| **[!UICONTROL Conversion]** | <ul><li>Products > Products (Which products are driving my key metrics?)</li><li>Products > Product performance (Which products are performing best?)</li><li>Products > Categories (What are my best performing product categories?</li><li>Shopping cart > Carts (How many users added a product to cart?</li><li>Shopping cart > Cart views (How many times did my visitors view their carts?)</li><li>Shopping cart > Cart additions (How often are users adding a product to their cart?)</li><li>Shopping cart > Cart removals (How often are users removing a product from their cart?)</li><li>Purchases > Revenue (How is my revenue performing?)</li><li>Purchases > Orders (How are my orders performing?)</li><li>Purchases > Units (How many units am I selling?)</li><li>[Magento: marketing and commerce](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#commerce)</li></ul> |
| **[!UICONTROL Audience]** |<ul><li>People metric (How many people are interacting with my brand?)</li><li>Visitor profile > Location overview (Which locations are driving the most usage among users)</li><li>Visitor profile > Geosegmentation > Geo Counties, Geo US States, Geo Regions, Geo Cities, Geo US DMA (Which geographies are my users visiting from?)</li><li>Visitor profile > Languages (Which language do my users prefer?)</li><li>Visitor profile > Time zones (Which time zones are my users visiting from?)</li><li>Visitor profile > Domains (Which ISPs are my visitors using to access my site?)</li><li>Visitor profile > Top level domains (Which domains are driving traffic to my site?)</li><li>Visitor profile > Technology > Technology overview (What technologies are people using to access my site?)</li><li>Visitor profile > Technology > Browsers, Browser type, Browser width, Browser height (Which company's browser, browser version, and its width and height, are people using to access my site?)</li><li>Visitor profile > Technology > Operating system, Operating system types (Which OS and which version of it do my visitors use?)</li><li>Visitor profile > Technology > Mobile carrier (Which mobile carriers do my visitors use to access my site?)</li><li>Visitor retention > Return frequency (How much time passes between my user's current visit and previous visits?)</li><li>Visitor retention > Return visits (How many of my visits are returning users?)</li><li>Visitor retention > Visit number (Which visit number bucket drives most of my key metrics)</li><li>Visitor retention > Sales cycle > Customer loyalty (Which loyalty segment do my users belong to?)</li><li>Visitor retention > Sales cycle > Days before first purchase (How many days passed between my users' first visit and their first purchase?)</li><li>Visitor retention > Sales cycle > Days since last purchase (How many days have passed between my users' current visit and their last purchase? )</li><li>Visitor retention > Mobile > Devices and Device types (Which devices and device types are my visitors using?)</li><li>Visitor retention > Mobile > Manufacturer (Which mobile device manufacturer do my visitors use?)</li><li>Visitor retention > Mobile > Screen size, Screen height, Screen width (Which mobile screen size/height/width do my visitors have?)</li><li>Visitor retention > Mobile > [Mobile app usage](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app journeys](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app metrics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app messaging](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app performance](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app retention](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li></ul> |
| **[!UICONTROL Acquisition]** |<ul><li>Marketing channels > First touch channel, First touch channel detail (Which first touch channel, and which specific first touch channel is performing best?)</li><li>Marketing channels > First last channel, First last channel detail (Which last touch channel, and which specific last touch channel is performing best?)</li><li>Campaigns > Campaigns (Which campaigns are driving my key metrics?)</li><li>Campaigns > Campaign performance (What campaigns are driving the most revenue?)</li><li>Campaigns > Tracking code (Which campaign tracking codes perform the best?)</li><li>[Web acquisition](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#web)</li><li>[Mobile acquisition](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>[Advertising Analytics: paid search](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#advertising)</li><li>Search keywords - all, paid, natural (Which search keywords and paid/natural search keywords drive my key metrics the best?)</li><li>Search engines - all, paid, natural (Which search engines and paid/natural search engines drive my key metrics the best?)</li><li>All search page ranking (Which search page are my users visiting from?)</li><li>Referring domains (Which domains are driving traffic to my site?)</li><li>Original referring domains (What was the first domain users were on before visiting my site?)</li><li>Referrers (Which URLs were my users on before clicking through to my site?)</li><li>Referrer types (Which category do my referring URLs belong to?)</li></ul> |

-->
