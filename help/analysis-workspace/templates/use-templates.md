---
description: Scopri i modelli predefiniti in Analysis Workspace e come utilizzarli.
title: Utilizzare i modelli
feature: Workspace Basics
role: User, Admin
exl-id: d61f215d-9089-4014-9c5a-97f5d7134f34
source-git-commit: f41162d1c4c44f79c59585d1311cd2e431725103
workflow-type: tm+mt
source-wordcount: '20234'
ht-degree: 100%

---

# Utilizzare i modelli

I modelli (o i modelli aziendali) in Analysis Workspace forniscono informazioni rapide sugli scenari di reporting più comuni. Di seguito sono riportati alcuni esempi di domande a cui puoi rispondere con i modelli:

* quante persone visitano il sito
* quanti di questi visitatori sono visitatori univoci (conteggiati una sola volta)
* come sono arrivati al sito (ad esempio, se hanno seguito un collegamento o ci sono arrivati direttamente)
* quali parole chiave hanno utilizzato i visitatori per cercare il contenuto del sito
* per quanto tempo i visitatori sono rimasti su una determinata pagina o sull’intero sito
* su quali collegamenti i visitatori hanno fatto clic e quando hanno lasciato il sito
* quali canali di marketing sono più efficaci nel generare ricavi o eventi di conversione
* quanto tempo hanno trascorso a guardare un video
* quali browser e dispositivi hanno utilizzato per visitare il sito

Le informazioni seguenti descrivono come accedere e utilizzare i modelli della scheda [!UICONTROL Templates] in Analysis Workspace.

## Accedere ed eseguire un modello

1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**].

   ![Schede modelli](assets/view-prebuilt-templates-full.png)

1. Nella sezione [!UICONTROL **Modelli**] seleziona una delle schede seguenti:

   * **[!UICONTROL Adobe templates]**: mostra tutti i modelli forniti da Adobe.

   * **[!UICONTROL _modelli login_company_name _]**: mostra tutti i modelli aziendali creati per la tua organizzazione.

     Solo gli amministratori possono creare modelli aziendali. Per informazioni su come creare un modello aziendale, consulta [Creare e gestire modelli](/help/analysis-workspace/templates/create-templates.md).

1. Per modificare la modalità di visualizzazione dei modelli disponibili, utilizza una delle opzioni seguenti:

   * Scegli se visualizzare i modelli in una vista a colonne o in una vista a schede selezionando l’icona della vista a colonne ![ViewColumn](/help/assets/icons/ViewColumn.svg) o della vista a schede ![Card](/help/assets/icons/Card.svg).

   * Quando utilizzi la vista a schede ![Card](/help/assets/icons/Card.svg), scegli uno dei seguenti criteri di ordinamento: **[!UICONTROL Most recently used]**, **[!UICONTROL Most popular]**, **[!UICONTROL Alphabetical]**, **[!UICONTROL Categorical]**.

1. Nel campo di ricerca, inizia a digitare il nome del modello che desideri trovare, quindi selezionalo dall’elenco dei modelli.

   Oppure

   Seleziona la categoria di modelli che desideri visualizzare, quindi seleziona il modello dall’elenco dei modelli.

   >[!TIP]
   >
   >Per spostarti nel menu utilizzando i tasti freccia, premi il tasto Barra obliqua (/), quindi premi il tasto Freccia giù. Premi Invio per caricare il modello selezionato.

   Per un elenco di modelli disponibili, consulta la sezione [Modelli disponibili](#available-templates) di seguito.

1. (Facoltativo) Puoi visualizzare i modelli che contengono componenti non disponibili nella visualizzazione dati. Per impostazione predefinita, i modelli vengono visualizzati solo se utilizzano componenti disponibili nella visualizzazione dati.

   >[!NOTE]
   >
   >Prima che tu possa utilizzare questi modelli, un amministratore deve innanzitutto aggiungere alla visualizzazione dati le etichette di contesto richieste per i componenti mancanti. Per ulteriori informazioni, consulta [Aggiungere componenti mancanti alla visualizzazione dati per un modello specificato](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) in [Gestire i modelli](/help/analysis-workspace/templates/create-templates.md).
   >
   >Per ulteriori informazioni sulle etichette di contesto, consulta [Impostazioni dei componenti](/help/data-views/component-settings/overview.md).

   1. Seleziona l’icona del segmento.

   1. Seleziona **[!UICONTROL Not ready for use]** per visualizzare i modelli che richiedono componenti aggiuntivi.

      ![Usa un modello con componenti mancanti](assets/template-not-ready.png)

1. Seleziona il modello per creare un rapporto basato sul modello scelto.

1. (Condizionale) Se il modello contiene componenti non disponibili nella visualizzazione dati, viene visualizzata la finestra di dialogo Visualizzazione dati incompatibile, in cui viene indicato che la visualizzazione dati è incompatibile con il modello e vengono mostrati i componenti mancanti.

   Esegui una delle operazioni seguenti:

   * Scegli una visualizzazione dati diversa nel menu a discesa **[!UICONTROL Change data view]**.

   * Seleziona **[!UICONTROL Continue anyway]** per visualizzare il modello con i componenti mancanti.

## Creare un progetto basato su un modello {#use-reports}

Un modello potrebbe non soddisfare esattamente le tue esigenze, ma può avvicinarvisi. In questi casi, puoi utilizzare il modello come punto di partenza per il progetto, quindi personalizzarlo in base ai tuoi scopi specifici.

Se esci da un modello dopo aver effettuato modifiche, ti viene richiesto di salvare o eliminare le modifiche. Quando si salvano le modifiche a un modello, questo viene salvato come un nuovo progetto.

Per personalizzare un modello e salvarlo come progetto:

1. In Customer Journey Analytics, seleziona la scheda [!UICONTROL **Area di lavoro**].

1. Seleziona la scheda [!UICONTROL **Modelli**] 

1. Seleziona il modello che desideri visualizzare. Ad esempio, in [!UICONTROL **Più popolari**], seleziona il modello [!UICONTROL **Pagine**].

   Come mostrato in Analysis Workspace, il modello Pagine mostra due [visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Grafico a barre](/help/analysis-workspace/visualizations/bar.md) e [Numero di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md)) e una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). La metrica utilizzata è Occorrenze.

   <!--update screenshot. The following is AA -->

   ![Modello Pagine](assets/pages-report.png)

1. Esegui una delle operazioni seguenti:

   * Visualizza il modello.
   * Puoi trascinare uno o più segmenti nella zona di rilascio Segmento, nella parte superiore. Ad esempio, trascina il segmento [!UICONTROL **Clienti mobile**] e visualizza i risultati.
   * Modifica l’intervallo di date andando sul calendario in alto a destra.
   * Aggiungi raggruppamenti di dimensioni, trascina altre metriche e personalizza il modello a livello generale in base alle tue esigenze.

1. (Facoltativo) Salva il modello come progetto selezionando [!UICONTROL **Progetto**] > [!UICONTROL **Salva**].

   Il rapporto viene salvato come nuovo progetto e non viene modificato il rapporto esistente. Per ulteriori informazioni sul salvataggio dei progetti, consulta [Salvare i progetti](/help/analysis-workspace/build-workspace-project/save-projects.md).

## Modelli disponibili

Per accedere a tutti i modelli predfiniti disponibili:

1. In Adobe Analytics, seleziona la scheda [!UICONTROL **Area di lavoro**], quindi scegli la scheda [!UICONTROL **Modelli**].

   I modelli predefiniti sono organizzati per categoria.

   <!--add screenshot-->

1. Seleziona una categoria per visualizzare i modelli al suo interno.

   Le sezioni seguenti corrispondono alle categorie disponibili e forniscono informazioni su ciascun modello.

   * **[[!UICONTROL Most popular]](#most-popular)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Engagement]](#engagement)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Conversion]](#web-conversion)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Audience]](#web-audience)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Acquisition]](#web-acquisition)**

   * **[[!UICONTROL Mobile]** > **[!UICONTROL Mobile App]](#mobile-mobile-app)**

   * **[[!UICONTROL Mobile]** > **[!UICONTROL Mobile Device Information]](#mobile-mobile-device-information)**

   * **[[!UICONTROL Time Parting]](#time-parting)**

   * **[[!UICONTROL Cross-Channel]](#cross-channel)**

   * **[[!UICONTROL Other Channels]](#other-channels)**

   * **[[!UICONTROL AJO]](#ajo)**

### Most popular (Più popolari) {#most-popular}

<!--AA only-->

>[!CONTEXTUALHELP]
>id="aa-template--unitsOvertimeReport"
>title="Visualizza il numero totale di unità acquistate in tutti gli ordini. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio come le vendite delle unità aumentano o diminuiscono nel tempo. Puoi applicare un segmento per scoprire quale clientela o quali aree geografiche acquistano il maggior numero di unità e quale sia la tendenza delle rispettive vendite nel tempo.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando le vendite di unità prima e dopo l’avvio della campagna. Oppure è possibile confrontare le vendite di unità durante le festività rispetto all’anno precedente.<br/>Questo modello utilizza la dimensione Giorno e la metrica Unità."


<!--both AA and CJA-->

>[!CONTEXTUALHELP]
>id="template--training"
>title="Modello per le esercitazioni"
>abstract="Scopri la terminologia e i passaggi più comuni di Analysis Workspace per creare la tua prima analisi."

>[!CONTEXTUALHELP]
>id="template--pagesRankedReport"
>title="Identifica le pagine più popolari e quelle meno popolari."
>abstract="**Questo può aiutarti** a comprendere meglio il tuo pubblico e il tipo di informazioni a cui è più interessato.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare i metadati della pagina per aumentare la visibilità delle pagine meno visualizzate oppure dedicare del tempo al miglioramento dei contenuti delle pagine più visualizzate.<br/>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina."

>[!CONTEXTUALHELP]
>id="template--pageViewsOvertimeReport"
>title="Visualizza il numero totale di visualizzazioni di pagina. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. "
>abstract="**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l’avvio della campagna. Oppure è possibile confrontare il traffico nel periodo delle festività rispetto all’anno precedente.<br/>Questo modello utilizza la dimensione Giorno e la metrica Visualizzazioni pagina."

>[!CONTEXTUALHELP]
>id="template--visitsOvertimeReport"
>title="Visualizza il numero totale di visite. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l’avvio della campagna. Oppure è possibile confrontare il traffico nel periodo delle festività rispetto all’anno precedente.<br/>Questo modello utilizza la dimensione Giorno e la metrica Visite."

>[!CONTEXTUALHELP]
>id="template--visitorsOvertimeReport"
>title="Visualizza il numero totale di visitatori univoci. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. "
>abstract="**Questo può aiutarti** a comprendere meglio come la portata e la dimensione del pubblico del tuo sito aumentano o diminuiscono nel tempo o rispetto a un periodo precedente.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se una campagna di marketing avviata di recente è riuscita ad attirare nuove persone sul sito confrontando i visitatori univoci prima e dopo l’avvio della campagna. Oppure è possibile confrontare il numero di persone che visitano il sito durante le festività rispetto all’anno precedente.<br/>Questo modello utilizza la dimensione Giorno e la metrica Visitatori univoci. "

>[!CONTEXTUALHELP]
>id="template--keyMetricsReport"
>title="Visualizza un rapporto che mostra fianco a fianco le metriche relative a visualizzazioni pagina, visite e visitatori univoci. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a confrontare queste metriche importanti per ottenere un quadro più completo del numero di persone univoche che visitano il sito, del numero di volte che le pagine sono state visitate e del numero di sessioni.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare il numero medio di pagine visualizzate da ogni persona durante la visita al sito in una determinata settimana o mese e come è cambiato durante determinati periodi dell’anno o prima e dopo l’esecuzione di campagne di marketing. <br/>Questo modello utilizza la dimensione Giorno e le metriche di Visualizzazioni pagina, Visite e Visitatori univoci."

>[!CONTEXTUALHELP]
>id="template--siteSectionRankedReport"
>title="Visualizza le sezioni del sito più popolari o con le prestazioni migliori."
>abstract="**Questo può aiutarti** a comprendere meglio quali sezioni del tuo sito sono più visitate.<br>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali tra i prodotti o i servizi che fornisci generano maggiore interesse.<br/>Questo modello utilizza la dimensione Sezione sito e la metrica Visite."

>[!CONTEXTUALHELP]
>id="template--next-page-report"
>title="Visualizza i luoghi più comuni in cui le persone vanno immediatamente dopo aver visitato una determinata pagina."
>abstract="**Questo può aiutarti** a comprendere meglio il comportamento degli utenti dopo aver visitato una determinata pagina.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se la progettazione o il layout della pagina può essere ottimizzato per indirizzare gli utenti verso le pagine più desiderate, ad esempio una pagina dove effettuare un acquisto o lasciare una recensione.<br/>Questo modello utilizza la dimensione Pagina e la metrica Eventi."

>[!CONTEXTUALHELP]
>id="template--previous-page-report"
>title="Visualizza i luoghi più comuni in cui le persone vanno immediatamente prima di visitare una determinata pagina."
>abstract="**Questo può aiutarti** a comprendere meglio quali pagine indirizzano il traffico maggiore verso una determinata pagina.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se le pagine che non sono visualizzate come le pagine precedenti necessitano di collegamenti più evidenti alla pagina corrente."

>[!CONTEXTUALHELP]
>id="template--campaignRankedReport"
>title="Visualizza i collegamenti che sono stati più efficaci nel generare traffico verso il tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali codici di tracciamento (e i collegamenti associati a essi) sono stati più utilizzati per accedere al tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare la strategia su dove aggiungere i collegamenti al tuo sito.<br/>Questo modello utilizza la dimensione Codice di tracciamento e la metrica Visite."

>[!CONTEXTUALHELP]
>id="template--productsRankedReport"
>title="Visualizza il numero di ordini per prodotto. I dati vengono visualizzati in un periodo di tempo."
>abstract="**Questo può aiutarti** a comprendere quali sono i prodotti con la domanda più alta o più bassa.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare le strategie di marketing per promuovere prodotti con prestazioni elevate oppure per migliorare o interrompere prodotti con prestazioni insufficienti. Puoi anche modificare l’inventario dei prodotti in base all’analisi dei dati.<br/>Questo modello utilizza la dimensione Prodotto e la metrica Ordini."

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelRankedReport"
>title="Visualizza i canali di marketing più recenti con cui i visitatori corrispondono durante il periodo di coinvolgimento (30 giorni per impostazione predefinita)."
>abstract="**Questo può aiutarti** a comprendere quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito e che hanno generato delle conversioni.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse ai canali con prestazioni elevate o meno risorse ai canali con prestazioni insufficienti.<br/>Questo modello utilizza la dimensione Canale di ultimo contatto e la metrica Visitatori univoci."

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelDetailRankedReport"
>title="Visualizza i dettagli sui canali di marketing più recenti con cui i visitatori corrispondono durante il periodo di coinvolgimento (30 giorni per impostazione predefinita)."
>abstract="**Questo può aiutarti** a comprendere non solo quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito generando conversioni, ma anche i dettagli su tali canali di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing “Ricerca a pagamento”, puoi utilizzare i dettagli del canale per visualizzare quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse ai canali con prestazioni elevate o meno risorse ai canali con prestazioni insufficienti.<br/>Questo modello utilizza la dimensione Dettaglio canale di ultimo contatto e la metrica Visitatori univoci. "

>[!CONTEXTUALHELP]
>id="template--revenueOvertimeReport"
>title="Visualizza l’importo monetario dei prodotti acquistati in tutti gli ordini. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere il modo in cui i ricavi aumentano o diminuiscono nel tempo. Puoi combinare questa metrica con qualsiasi dimensione per scoprire quali elementi della dimensione hanno contribuito ai ricavi.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio proiettare i ricavi futuri in base alle tendenze precedenti. Puoi anche aggiungere un’altra dimensione, come la dimensione Codice di tracciamento, per scoprire quali campagne generano maggiori ricavi.<br/>Questo modello utilizza la dimensione Giorno e la metrica Ricavi."

>[!CONTEXTUALHELP]
>id="template--ordersOvertimeReport"
>title="Visualizza il numero totale di eventi di acquisto. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio come aumenta o diminuisce nel tempo l’interesse per i tuoi prodotti e servizi. Puoi applicare un segmento per scoprire quale clientela o quali aree geografiche stanno effettuando il maggior numero di ordini e quale sia la tendenza di tali ordini nel tempo.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando gli ordini prima e dopo l’avvio della campagna. Oppure potresti confrontare gli ordini relativi alle festività anno per anno.<br/>Questo modello utilizza la dimensione Giorno e la metrica Ordini."


 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Tutorial di formazione**] | Scopri la terminologia e i passaggi più comuni di Analysis Workspace per creare la tua prima analisi. |
| [!UICONTROL **Pagine**] | <!--duplicated in Engagement section--> Identifica le pagine più popolari e quelle meno popolari. <p>**Questo può aiutarti** a comprendere meglio il tuo pubblico e il tipo di informazioni a cui è più interessato.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare i metadati della pagina per aumentare la visibilità delle pagine meno visualizzate oppure dedicare del tempo al miglioramento dei contenuti delle pagine più visualizzate.</p><p>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina.</p> |
| [!UICONTROL **Visualizzazioni pagina**] | <!--duplicated in Engagement section--> Visualizza il numero totale di visualizzazioni di pagina. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l’avvio della campagna. Oppure è possibile confrontare il traffico nel periodo delle festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Visualizzazioni pagina.</p> |
| [!UICONTROL **Visite Web**] | <!--duplicated in Engagement section--> Visualizza il numero totale di visite. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l’avvio della campagna. Oppure è possibile confrontare il traffico nel periodo delle festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Visite.</p> |
| [!UICONTROL **Visitatori Web**] | <!--duplicated in Engagement section--> Visualizza il numero totale di visitatori univoci. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come la portata e la dimensione del pubblico del tuo sito aumentano o diminuiscono nel tempo o rispetto a un periodo precedente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se una campagna di marketing avviata di recente è riuscita ad attirare nuove persone sul sito confrontando i visitatori univoci prima e dopo l’avvio della campagna. Oppure è possibile confrontare il numero di persone che visitano il sito durante le festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Visitatori univoci.</p> |
| [!UICONTROL **Metriche chiave**] | <!--duplicated in Engagement section--> Visualizza un rapporto che mostra fianco a fianco le metriche relative a visualizzazioni pagina, visite e visitatori univoci. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a confrontare queste metriche importanti per ottenere un quadro più completo del numero di persone univoche che visitano il sito, del numero di volte che le pagine sono state visitate e del numero di sessioni.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare il numero medio di pagine visualizzate da ogni persona durante la visita al sito in una determinata settimana o mese e come è cambiato durante determinati periodi dell’anno o prima e dopo l’esecuzione di campagne di marketing. </p><p>Questo modello utilizza la dimensione Giorno e le metriche di Visualizzazioni pagina, Visite e Visitatori univoci.</p> |
| [!UICONTROL **Sezioni del sito**] | Visualizza le sezioni del sito più popolari o con le prestazioni migliori. <p>**Questo può aiutarti** a comprendere meglio quali sezioni del tuo sito sono più visitate.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali tra i prodotti o i servizi che fornisci generano maggiore interesse.</p> <p>Questo modello utilizza la dimensione Sezione del sito e la metrica Visite.</p> |
| [!UICONTROL **Pagina successiva**] | Visualizza i luoghi più comuni in cui le persone vanno immediatamente dopo aver visitato una determinata pagina. <p>**Questo può aiutarti** a comprendere meglio il comportamento degli utenti dopo aver visitato una determinata pagina.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se la progettazione o il layout della pagina può essere ottimizzato per indirizzare gli utenti verso le pagine più desiderate, ad esempio una pagina dove effettuare un acquisto o lasciare una recensione.</p> <p>Questo modello utilizza la dimensione Pagina e la metrica Eventi.</p> |
| [!UICONTROL **Pagina precedente**] | Visualizza i luoghi più comuni in cui le persone vanno immediatamente prima di visitare una determinata pagina. <p>**Questo può aiutarti** a comprendere meglio quali pagine indirizzano il traffico maggiore verso una determinata pagina.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se le pagine che non sono visualizzate come le pagine precedenti necessitano di collegamenti più evidenti alla pagina corrente.</p><p>Questo modello utilizza la dimensione Pagina e la metrica Eventi.</p> |
| [!UICONTROL **Codice di tracking**] | Visualizza i collegamenti che sono stati più efficaci nel generare traffico verso il tuo sito. <p>**Questo può aiutarti** a comprendere meglio quali codici di tracciamento (e i collegamenti associati a essi) sono stati più utilizzati per accedere al tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare la strategia su dove aggiungere i collegamenti al tuo sito.</p><p>Questo modello utilizza la dimensione Codice di tracciamento e la metrica Visite.</p> |
| [!UICONTROL **Prodotti**] | Visualizza il numero di ordini per prodotto. I dati vengono visualizzati in un periodo di tempo. <p>**Questo può aiutarti** a comprendere quali sono i prodotti con la domanda più alta o più bassa.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare le strategie di marketing per promuovere prodotti con prestazioni elevate oppure per migliorare o interrompere prodotti con prestazioni insufficienti. Puoi anche modificare l’inventario dei prodotti in base all’analisi dei dati.</p><p>Questo modello utilizza la dimensione Prodotto e la metrica Ordini.</p> |
| [!UICONTROL **Canale di ultimo contatto**] | Visualizza i canali di marketing più recenti con cui i visitatori corrispondono durante il periodo di coinvolgimento (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a comprendere quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito e che hanno generato delle conversioni.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse ai canali con prestazioni elevate o meno risorse ai canali con prestazioni insufficienti.</p><p>Questo modello utilizza la dimensione Canale di ultimo contatto e la metrica Visitatori univoci.</p> |
| [!UICONTROL **Dettaglio del canale di ultimo contatto**] | Visualizza i dettagli sui canali di marketing più recenti con cui i visitatori corrispondono durante il periodo di coinvolgimento (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a comprendere non solo quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito generando conversioni, ma anche i dettagli su tali canali di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing “Ricerca a pagamento”, puoi utilizzare i dettagli del canale per visualizzare quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse ai canali con prestazioni elevate o meno risorse ai canali con prestazioni insufficienti.</p><p>Questo modello utilizza la dimensione Dettaglio del canale di ultimo contatto e la metrica Visitatori univoci.</p> |
| [!UICONTROL **Ricavi**] | <!--duplicated in Web Conversion section-->Visualizza l’importo monetario dei prodotti acquistati in tutti gli ordini. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti.<p>**Questo può aiutarti** a comprendere il modo in cui i ricavi aumentano o diminuiscono nel tempo. Puoi combinare questa metrica con qualsiasi dimensione per scoprire quali elementi della dimensione hanno contribuito ai ricavi.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio proiettare i ricavi futuri in base alle tendenze precedenti. Puoi anche aggiungere un’altra dimensione, come la dimensione Codice di tracciamento, per scoprire quali campagne generano maggiori ricavi.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Ricavi.</p> |
| [!UICONTROL **Ordini**] | <!--duplicated in Web Conversion section-->Visualizza il numero totale di eventi di acquisto. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come aumenta o diminuisce nel tempo l’interesse per i tuoi prodotti e servizi. Puoi applicare un segmento per scoprire quale clientela o quali aree geografiche stanno effettuando il maggior numero di ordini e quale sia la tendenza di tali ordini nel tempo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando gli ordini prima e dopo l’avvio della campagna. Oppure potresti confrontare gli ordini relativi alle festività anno per anno.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Ordini.</p> |

### Web: coinvolgimento {#web-engagement}

<!--AA only-->

>[!CONTEXTUALHELP]
>id="aa-template--real-time"
>title="Visualizza le dimensioni e le metriche attualmente raccolte sul tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio le tendenze sul tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio rispondere a e gestire attivamente le prestazioni dei contenuti e delle campagne di marketing correnti."

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentVisitOvertimeReport"
>title="Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio il livello di coinvolgimento dei visitatori e quanto tempo trascorrono sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori trascorrono più tempo sul sito.<br/>Questo modello utilizza la dimensione Giorno e la metrica Tempo trascorso per visita (secondi)."

>[!CONTEXTUALHELP]
>id="aa-template--timePriorRankedReport"
>title="Visualizza il tempo medio trascorso dagli utenti prima di un evento di successo."
>abstract="**Questo può aiutarti** a comprendere meglio quanto tempo impiegano i visitatori per eseguire un’azione desiderata, ad esempio per effettuare un acquisto.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori possono raggiungere più rapidamente un evento di successo.<br/>Questo modello utilizza la dimensione Tempo prima dell’evento e la metrica Visitatori univoci."

>[!CONTEXTUALHELP]
>id="aa-template--falloutReport"
>title="Visualizza il punto in cui le persone abbandonano o proseguono attraverso una sequenza di pagine predefinita."
>abstract="**Questo può aiutarti** a comprendere meglio dove le persone abbandonano il percorso dell’utente.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come analizzare i tassi di conversione per processi specifici (come un processo di acquisto o di registrazione) oppure analizzare le correlazioni tra gli eventi. Ad esempio, la percentuale di persone che ha visualizzato l’informativa sulla privacy e ha poi acquistato un prodotto. Puoi anche utilizzare questo modello per eseguire confronti paralleli di due segmenti diversi dello stesso rapporto.<br/>Questo modello utilizza la visualizzazione Fallout."

>[!CONTEXTUALHELP]
>id="aa-template--cross-device-analysis"
>title="Visualizza quali dispositivi le persone hanno utilizzato in tutti i punti del percorso."
>abstract="**Questo può aiutarti** a comprendere meglio quante persone interagiscono col tuo brand, i tipi di dispositivi che utilizzano e come l’utilizzo di più dispositivi influisce sulla loro esperienza. Ad esempio, con quale frequenza le persone iniziano un’attività da un dispositivo mobile e successivamente passano a un PC desktop per completare tale attività? Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo? E così via.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio ottimizzare determinate parti del percorso dell’utente per un’esperienza mobile.<br/>Questo modello utilizza le visualizzazioni Flusso e Fallout, l’analisi Coorte, e le metriche Persone e Dispositivi univoci."

>[!CONTEXTUALHELP]
>id="aa-template--web-retention"
>title="Visualizza chi sono gli utenti più fedeli e cosa fanno sul sito."
>abstract="**Questo può aiutarti** a comprendere quante volte una persona visita il tuo sito in media, la frequenza con cui le persone ritornano al sito e quanti giorni passano tra visite successive.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio analizzare quali sono i contenuti più efficaci nel riportare le persone sul sito.<br/>Questo modello utilizza le metriche Visite e Visitatori univoci."

>[!CONTEXTUALHELP]
>id="aa-template--audio-consumption-template"
>title="Visualizza le tendenze e le metriche principali relative al consumo di audio su tutti i dispositivi digitali."
>abstract="**Questo può aiutarti** a comprendere meglio come i visitatori consumano contenuti audio sul tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio analizzare quali sono i contenuti maggiormente consultati.<br/>Questo modello utilizza le metriche Visite e Visitatori univoci."

>[!CONTEXTUALHELP]
>id="aa-template--media-recency-frequency-loyalty"
>title="Visualizza le tendenze e le metriche principali relative al consumo di contenuti multimediali su tutti i dispositivi digitali."
>abstract="**Questo può aiutarti** a comprendere meglio quante volte una persona visita il tuo sito in media, la frequenza con cui le persone ritornano al sito e quanti giorni passano tra visite successive.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio analizzare quali sono i contenuti più efficaci nel riportare le persone sul sito.<br/>Questo modello utilizza le metriche Visite e Visitatori univoci."

>[!CONTEXTUALHELP]
>id="aa-template--reloadsRankedReport"
>title="Visualizza quante volte un elemento dimensione è stato presente durante un ricaricamento. In genere un ricaricamento si verifica quando un visitatore aggiorna la finestra del browser."
>abstract="**Questo può aiutarti** a individuare quando su una determinata pagina potrebbero verificarsi problemi che inducono il visitatore a ricaricarla.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali pagine presentano problemi da risolvere.<br/>Questo modello utilizza la metrica Ricaricamenti."

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentPageRankedReport"
>title="Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio il livello di coinvolgimento dei visitatori e quanto tempo trascorrono sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori trascorrono più tempo sul sito.<br/>Questo modello utilizza la dimensione Giorno e la metrica Tempo trascorso per visita (secondi)."

>[!CONTEXTUALHELP]
>id="aa-template--entryPageOriginalRankedReport"
>title="Visualizza le pagine principali a cui le persone accedono alla prima visita del tuo sito durante il ciclo di vita di un visitatore."
>abstract="**Questo può aiutarti** a comprendere meglio quali pagine generano maggior traffico verso il tuo sito o quali sono le prime impressioni dei visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare l’esperienza iniziale o assicurarsi che le pagine visualizzate per prima, all’accesso, siano accoglienti e forniscano i collegamenti necessari verso altre aree del sito.<br/>Questo modello utilizza la metrica Sessioni. Utilizza anche le visualizzazioni a barre e tabella a forma libera."

>[!CONTEXTUALHELP]
>id="aa-template--singlePageVisitsRankedReport"
>title="Visualizza il numero di visite in cui è stata visitata una singola pagina univoca."
>abstract="**Questo può aiutarti** a comprendere meglio il livello di coinvolgimento dei visitatori e quanto tempo trascorrono sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori trascorrono più tempo sul sito.<br/>Questo modello utilizza la dimensione Visite a pagina singola."

>[!CONTEXTUALHELP]
>id="aa-template--sitePerformanceOverview"
>title="Visualizza i dati sulle prestazioni per il sito Adobe Experience Manager."
>abstract="**Questo può aiutarti** a comprendere meglio la realizzazione del valore da Adobe Experience Manager.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare le impostazioni di Experience Manager."

>[!CONTEXTUALHELP]
>id="aa-template--formsPerformanceOverview"
>title="Visualizza i dati sulle prestazioni per Adobe Experience Manager Forms."
>abstract="**Questo può aiutarti** a comprendere meglio la realizzazione del valore da Adobe Experience Manager.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare le impostazioni di Experience Manager."

>[!CONTEXTUALHELP]
>id="aa-template--itp-impact"
>title="Visualizza e analizza gli effetti della Prevenzione intelligente del tracciamento (ITP) sulla raccolta dei dati e sul reporting."
>abstract="**Questo può aiutarti** a comprendere meglio la potenziale perdita di dati dovuta alle restrizioni sui cookie imposte dall’ITP.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio adattare la configurazione dell’analisi per ridurre al minimo l’impatto dell’ITP."


<!--Both AA and CJA-->

>[!CONTEXTUALHELP]
>id="template_time_spent"
>title="Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita, nonché il tempo medio trascorso dagli utenti prima di un evento di successo. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e quanto tempo impiegano per eseguire un’azione desiderata, ad esempio per effettuare un acquisto.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se le modifiche al tuo sito migliorano la possibilità dei visitatori di raggiungere rapidamente un evento di successo.<br/>Questo modello utilizza la dimensione Giorno e la metrica Tempo trascorso per visita (secondi)."

>[!CONTEXTUALHELP]
>id="template--web-content-consumption"
>title="Visualizza quali sono i contenuti web maggiormente consumati e che coinvolgono gli utenti."
>abstract="**Questo può aiutarti** a comprendere meglio dove vanno le persone che accedono per la prima volta al sito, quali sezioni visitano di più e quali pagine hanno più probabilità di allontanarle dallo stesso.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali percorsi del sito conducono le persone verso le pagine più importanti e quali pagine hanno maggiori probabilità di allontanarle dallo stesso.<br/>Questo modello utilizza la dimensione Pagina e le metriche Visualizzazioni pagina, Visite, Visitatori univoci, Percentuale di entrata, Percentuale di mancati recapiti, Percentuale di uscita e Velocità operazioni. Inoltre utilizza le visualizzazioni Flusso per le sezioni di entrata, uscita e principali."

>[!CONTEXTUALHELP]
>id="template--media-content-consumption"
>title="Visualizza quali sono i contenuti multimediali maggiormente utilizzati e che coinvolgono gli utenti."
>abstract="**Questo può aiutarti** a comprendere meglio dove vanno le persone che accedono per la prima volta al sito, quali sezioni visitano di più e quali pagine hanno più probabilità di allontanarle dallo stesso.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali percorsi del sito conducono le persone verso le pagine più importanti e quali pagine hanno maggiori probabilità di allontanarle dallo stesso.<br/>Questo modello utilizza la dimensione Pagina e le metriche Visualizzazioni pagina, Visite, Visitatori univoci, Percentuale di entrata, Percentuale di mancati recapiti, Percentuale di uscita e Velocità operazioni. Inoltre utilizza le visualizzazioni Flusso per le sezioni di ingresso, uscita e principali; una visualizzazione con grafico a dispersione che mostra le visualizzazioni delle pagine più comuni; una visualizzazione a barre che mostra le visualizzazioni di pagina per blocchi di tempo; e una visualizzazione a linee che mostra le tendenze del tempo medio trascorso sul sito."

>[!CONTEXTUALHELP]
>id="template--flowreport"
>title="Visualizza i luoghi più comuni in cui le persone vanno immediatamente dopo aver visitato o prima di visitare un determinato luogo."
>abstract="**Questo può aiutarti** a comprendere come il traffico si sposta da una determinata pagina ad altre parti del sito e i percorsi seguiti dalle persone per arrivare a una determinata pagina.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se la progettazione o il layout della pagina può essere ottimizzato per indirizzare gli utenti verso le pagine più desiderate, ad esempio una pagina dove effettuare un acquisto o lasciare una recensione. Oppure valuta se le informazioni presenti nella pagina corrente sono in grado di fornire la direzione o le azioni che le persone cercano quando arrivano dalle pagine precedenti. Oppure puoi valutare se le pagine che non sono visualizzate come pagine precedenti necessitano di collegamenti più evidenti alla pagina corrente.<br/>Questo modello utilizza il pannello Elemento successivo o precedente."

>[!CONTEXTUALHELP]
>id="template--page-summary-report"
>title="Visualizza informazioni chiave su qualsiasi pagina delle tue proprietà. Mostra le visualizzazioni di pagina, una linea di tendenza, una visualizzazione di flusso e altro ancora."
>abstract="**Questo può aiutarti** a comprendere meglio come le persone interagiscono con una determinata pagina.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come analizzare le prestazioni della pagina rispetto a un periodo di tempo o comprendere meglio cosa favorisce il traffico verso la pagina.<br/>Questo modello utilizza la metrica Visualizzazioni pagina. Utilizza anche le visualizzazioni a linee e flusso."

>[!CONTEXTUALHELP]
>id="template--entryPageRankedReport"
>title="Visualizza le pagine principali a cui gli utenti accedono quando visitano il tuo sito per la prima volta."
>abstract="**Questo può aiutarti** a comprendere meglio quali pagine generano maggior traffico verso il tuo sito o le prime impressioni che i visitatori hanno rispetto ad esso.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare l’esperienza iniziale o assicurarsi che le pagine visualizzate per prima, all’accesso, siano accoglienti e forniscano i collegamenti necessari verso altre aree del sito.<br/>Questo modello utilizza la metrica Sessioni. Utilizza anche le visualizzazioni a barre e tabella a forma libera."

>[!CONTEXTUALHELP]
>id="template--exitPageRankedReport"
>title="Visualizza le pagine principali a cui le persone accedono immediatamente prima di lasciare il sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali pagine allontanano le persone dal sito. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio aggiornare le pagine di uscita comuni per ottimizzare l’esperienza che le persone hanno del sito prima di lasciarlo, oppure includere contenuti o collegamenti per incoraggiarle a rimanere sullo stesso.<br/>Questo modello utilizza la metrica Sessioni. Utilizza anche le visualizzazioni a barre e tabella a forma libera."

>[!CONTEXTUALHELP]
>id="template--productUsageOverviewReport"
>title="Visualizza il modo in cui il prodotto Customer Journey Analytics viene utilizzato all’interno dell’organizzazione."
>abstract="**Questo può aiutarti** a comprendere meglio quante persone usano Customer Journey Analytics, con quale frequenza lo usano e le tendenze di utilizzo nel tempo. Puoi anche visualizzare il numero di progetti in fase di creazione e i dettagli su tali progetti (ad esempio, quali componenti, visualizzazioni e pannelli sono più comunemente utilizzati) e molte altre statistiche di utilizzo.<br/>**In base a ciò che hai appreso, potresti** fare diverse cose, ad esempio eliminare i progetti o i componenti inutilizzati o fornire agli utenti corsi di formazione sulle funzioni più comuni."

>[!CONTEXTUALHELP]
>id="template--content-analytics"
>title="Scopri quali sono i contenuti e gli attributi di contenuto con le migliori prestazioni."
>abstract="**Questo può aiutarti** a comprendere le prestazioni del contenuto a un livello granulare. Puoi esaminare le prestazioni di singole risorse o attributi specifici. Content Analytics utilizza l’intelligenza artificiale per generare automaticamente gli attributi e assegnarli ai contenuti tramite tag. <a href="https://experienceleague.adobe.com/it/docs/analytics-platform/using/content-analytics/content-analytics" target="&quot;_blank&quot;">Ulteriori informazioni</a>.<br/>**In base a ciò che hai appreso, potresti** fare diverse cose, come promuovere risorse ad alte prestazioni nella tua pagina Home, personalizzare il contenuto per segmenti specifici in modo da includere attributi ad alte prestazioni o sostituire il contenuto che ha iniziato a diventare obsoleto."


 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Metriche chiave**] | <!--duplicated in Most popular section--> Visualizza un rapporto che mostra fianco a fianco le metriche relative a visualizzazioni pagina, visite e visitatori univoci. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a confrontare queste metriche importanti per ottenere un quadro più completo del numero di persone univoche che visitano il sito, del numero di volte che le pagine sono state visitate e del numero di sessioni.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare il numero medio di pagine visualizzate da ogni persona durante la visita al sito in una determinata settimana o mese e come è cambiato durante determinati periodi dell’anno o prima e dopo l’esecuzione di campagne di marketing. </p><p>Questo modello utilizza la dimensione Giorno e le metriche di Visualizzazioni pagina, Visite e Visitatori univoci.</p> |
| [!UICONTROL **Visualizzazioni pagina**] | <!--duplicated in Most popular section-->Visualizza il numero totale di visualizzazioni di pagina. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l’avvio della campagna. Oppure è possibile confrontare il traffico nel periodo delle festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Visualizzazioni pagina.</p> |
| [!UICONTROL **Pagine**] | <!--duplicated in Most popular section-->Identifica le pagine più popolari e quelle meno popolari. <p>**Questo può aiutarti** a comprendere meglio il tuo pubblico e il tipo di informazioni a cui è più interessato.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare i metadati della pagina per aumentare la visibilità delle pagine meno visualizzate oppure dedicare del tempo al miglioramento dei contenuti delle pagine più visualizzate.</p><p>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina.</p> |
| [!UICONTROL **Visite**] | <!--duplicated in Most popular section-->Visualizza il numero totale di visite. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l’avvio della campagna. Oppure è possibile confrontare il traffico nel periodo delle festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Visite.</p> |
| [!UICONTROL **Visitatori**] | <!--duplicated in Most popular section-->Visualizza il numero totale di visitatori univoci. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come la portata e la dimensione del pubblico del tuo sito aumentano o diminuiscono nel tempo o rispetto a un periodo precedente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se una campagna di marketing avviata di recente è riuscita ad attirare nuove persone sul sito confrontando i visitatori univoci prima e dopo l’avvio della campagna. Oppure è possibile confrontare il numero di persone che visitano il sito durante le festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Visitatori univoci.</p> |
| [!UICONTROL **Tempo trascorso**] | Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita, nonché il tempo medio trascorso dagli utenti prima di un evento di successo. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e quanto tempo impiegano per eseguire un’azione desiderata, ad esempio per effettuare un acquisto.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se le modifiche al tuo sito migliorano la possibilità dei visitatori di raggiungere rapidamente un evento di successo.</p><p>Questo modello utilizza la dimensione Giorno e la metrica Tempo trascorso per visita (secondi).</p> |
| [!UICONTROL **Sezioni del sito**] | <!--duplicated in Most popular section-->Visualizza le sezioni del sito più popolari o con le prestazioni migliori. <p>**Questo può aiutarti** a comprendere meglio quali sezioni del tuo sito sono più visitate.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali tra i prodotti o i servizi che fornisci generano maggiore interesse.</p> <p>Questo modello utilizza la dimensione Sezione del sito e la metrica Visite.</p> |
| [!UICONTROL **Consumo di contenuti web**] | Visualizza quali sono i contenuti web maggiormente consumati e che coinvolgono gli utenti.<p>**Questo può aiutarti** a comprendere meglio dove vanno le persone che accedono per la prima volta al sito, quali sezioni visitano di più e quali pagine hanno più probabilità di allontanarle dallo stesso.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali percorsi del sito conducono le persone verso le pagine più importanti e quali pagine hanno maggiori probabilità di allontanarle dallo stesso.</p> <p>Questo modello utilizza la dimensione Pagina e le metriche Visualizzazioni pagina, Visite, Visitatori univoci, Percentuale di entrate, Percentuale di mancati recapiti, Percentuale di uscite e Velocità dei contenuti. Inoltre utilizza le visualizzazioni Flusso per le sezioni di entrata, uscita e principali.</p> |
| [!UICONTROL **Consumo di contenuti multimediali**] | Visualizza quali sono i contenuti multimediali maggiormente utilizzati e che coinvolgono gli utenti.<p>**Questo può aiutarti** a comprendere meglio dove vanno le persone che accedono per la prima volta al sito, quali sezioni visitano di più e quali pagine hanno più probabilità di allontanarle dallo stesso.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali percorsi del sito conducono le persone verso le pagine più importanti e quali pagine hanno maggiori probabilità di allontanarle dal sito<!-- not sure about these takeaways... -->.</p> <p>Questo modello utilizza la dimensione Pagina e le metriche Visualizzazioni pagina, Visite, Visitatori univoci, Percentuale di entrate, Percentuale di mancati recapiti, Percentuale di uscite e Velocità dei contenuti. Inoltre utilizza le visualizzazioni Flusso per le sezioni di ingresso, uscita e principali; una visualizzazione con grafico a dispersione che mostra le visualizzazioni delle pagine più comuni; una visualizzazione a barre che mostra le visualizzazioni di pagina per blocchi di tempo; e una visualizzazione a linee che mostra le tendenze del tempo medio trascorso sul sito.</p> |
| [!UICONTROL **Flusso pagina successivo e precedente**] | Visualizza una visualizzazione del flusso delle posizioni più comuni in cui le persone vanno immediatamente dopo aver visitato e immediatamente prima di visitare una determinata pagina. <p>**Questo può aiutarti** a comprendere come il traffico si sposta da una determinata pagina ad altre parti del sito e i percorsi seguiti dalle persone per arrivare a una determinata pagina.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se la progettazione o il layout della pagina può essere ottimizzato per indirizzare gli utenti verso le pagine più desiderate, ad esempio una pagina dove effettuare un acquisto o lasciare una recensione. Oppure valuta se le informazioni presenti nella pagina corrente sono in grado di fornire la direzione o le azioni che le persone cercano quando arrivano dalle pagine precedenti. Oppure puoi valutare se le pagine che non sono visualizzate come pagine precedenti necessitano di collegamenti più evidenti alla pagina corrente.</p><p>Questo modello utilizza il pannello Elemento successivo o precedente.</p> |
| **Riepilogo pagina** | Visualizza informazioni chiave su qualsiasi pagina delle tue proprietà. Mostra le visualizzazioni di pagina, una linea di tendenza, una visualizzazione di flusso e altro ancora.  <p>**Questo può aiutarti** a comprendere meglio come le persone interagiscono con una determinata pagina.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come analizzare le prestazioni della pagina rispetto a un periodo di tempo o comprendere meglio cosa favorisce il traffico verso la pagina.</p><p>Questo modello utilizza la metrica Visualizzazioni pagina. Utilizza anche le visualizzazioni a linee e flusso.</p> |
| **Pagine di ingresso** | Visualizza le pagine principali a cui gli utenti accedono quando visitano il tuo sito per la prima volta. <p>**Questo può aiutarti** a comprendere meglio quali pagine generano maggior traffico verso il tuo sito o le prime impressioni che i visitatori hanno rispetto ad esso.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare l’esperienza iniziale o assicurarsi che le pagine visualizzate per prima, all’accesso, siano accoglienti e forniscano i collegamenti necessari verso altre aree del sito.</p><p>Questo modello utilizza la metrica Sessioni. Utilizza anche le visualizzazioni a barre e tabella a forma libera.</p> |
| **Pagine di uscita** | Visualizza le pagine principali a cui le persone accedono immediatamente prima di lasciare il sito.<p>**Questo può aiutarti** a capire meglio quali pagine allontanano le persone dal sito. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio aggiornare le pagine di uscita comuni per ottimizzare l’esperienza che le persone hanno del sito prima di lasciarlo, oppure includere contenuti o collegamenti per incoraggiarle a rimanere sullo stesso.</p><p>Questo modello utilizza la metrica Sessioni. Utilizza anche le visualizzazioni a barre e tabella a forma libera.</p> |
| **Panoramica di utilizzo del prodotto** | Visualizza il modo in cui il prodotto Customer Journey Analytics viene utilizzato all’interno dell’organizzazione. <p>**Questo può aiutarti** a comprendere meglio quante persone usano Customer Journey Analytics, con quale frequenza lo usano e le tendenze di utilizzo nel tempo. Puoi anche visualizzare il numero di progetti in fase di creazione e i dettagli su tali progetti (ad esempio, quali componenti, visualizzazioni e pannelli sono più comunemente utilizzati) e molte altre statistiche di utilizzo.</p><p>**In base a ciò che hai appreso, potresti** fare diverse cose, ad esempio eliminare i progetti o i componenti inutilizzati o fornire agli utenti corsi di formazione sulle funzioni più comuni.</p> |
| **Content Analytics** | Scopri quali sono i contenuti e gli attributi di contenuto con le migliori prestazioni.<p>**Questo può aiutarti** a comprendere le prestazioni del contenuto a un livello granulare. Puoi esaminare le prestazioni di singole risorse o attributi specifici. Content Analytics utilizza l’intelligenza artificiale per generare automaticamente gli attributi e assegnarli ai contenuti tramite tag. Per ulteriori informazioni, consulta [Content Analytics](/help/content-analytics/content-analytics.md){target="_blank"}.</p><p>**In base a ciò che hai appreso, potresti** fare diverse cose, come promuovere risorse ad alte prestazioni nella tua pagina Home, personalizzare il contenuto per segmenti specifici in modo da includere attributi ad alte prestazioni o sostituire il contenuto che ha iniziato a diventare obsoleto.</p> |

### Web: conversione {#web-conversion}

<!--AA only-->

>[!CONTEXTUALHELP]
>id="aa-template--categoryRankedReport"
>title="Visualizza il numero di visite associate a ciascuna categoria di prodotto sul sito. Questa funzione è utile per le implementazioni che utilizzano la variabile prodotti e desiderano visualizzare metriche sulla categoria di prodotto. La dimensione che popola questo modello può essere intenzionalmente vuota se non hai prodotti sul sito."
>abstract="**Questo può aiutarti** a capire meglio i prodotti più venduti o più visualizzati. &lt;/br/>**In base a quanto appreso, potresti** fare diverse cose, ad esempio misurare l’efficacia di una campagna di marketing per un determinato prodotto.<br/>Questo modello utilizza la dimensione Categoria e la metrica Visite. "

>[!CONTEXTUALHELP]
>id="aa-template--commerce-and-marketing-management"
>title="Visualizza insight predefiniti per rivenditori sulle attività commerciali, per aiutare a migliorare le vendite. Questo è destinato agli utenti di Adobe Commerce, ma può essere utilizzato da qualsiasi rivenditore online."
>abstract="**Questo può aiutarti** a comprendere meglio come le tue attività commerciali contribuiscono ai numeri di vendita.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come regolare i budget per le attività che ottengono il maggior ROI."


<!--Both AA and CJA-->

>[!CONTEXTUALHELP]
>id="template--productConversionReport"
>title="Visualizza la conversione del prodotto in una visualizzazione funnel che mostra carrelli, pagamenti e ordini. È inoltre possibile visualizzare le percentuali di conversione e le medie dei ricavi, delle unità e degli ordini."
>abstract="**Questo può aiutarti** a comprendere meglio come le persone procedono e abbandonano durante il processo di conversione.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare il tuo sito web per facilitare un processo di pagamento più fluido."

>[!CONTEXTUALHELP]
>id="template--retail-products-template"
>title="Visualizza quali sono i prodotti più performanti."
>abstract="**Questo può aiutarti** a comprendere meglio quali sono i prodotti di maggior successo.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come aumentare i finanziamenti per i prodotti di successo e diminuirli per i prodotti di minore successo.<br/>Questo modello utilizza le metriche Visualizzazioni prodotto, Aggiunte carrello, Ordini, Ricavi e Unità. Utilizza anche la dimensione Prodotto."

>[!CONTEXTUALHELP]
>id="template--cartConversionReport"
>title="Visualizza il numero di volte in cui le persone hanno eseguito eventi chiave di pagamento, ad esempio l’aggiunta di articoli al carrello, la visualizzazione del carrello, la rimozione di articoli dal carrello e il pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio quali parti del funnel del processo di pagamento portano alla conversione e quali sono più soggette all’abbandono del carrello.<br/>**Sulla base di quanto appreso potresti** fare diverse cose, ad esempio ridurre l’attrito in determinati passaggi del processo di pagamento.<br/>Questo modello utilizza"

>[!CONTEXTUALHELP]
>id="template--cartsOvertimeReport"
>title="Visualizza il numero di persone che hanno aggiunto un prodotto al carrello."
>abstract="**Questo può aiutarti** a comprendere meglio il numero di persone che aggiungono un prodotto al carrello, rispetto al numero complessivo di prodotti aggiunti a un carrello.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio misurare l’efficacia delle tue pagine di prodotti.<br/>Questo modello utilizza la metrica Carrelli."

>[!CONTEXTUALHELP]
>id="template--cartViewsOvertimeReport"
>title="Visualizza il numero di volte in cui le persone hanno visualizzato il carrello."
>abstract="**Questo può aiutarti** a comprendere meglio l’esperienza di pagamento nel tentativo di ridurre le percentuali di abbandono del carrello o ad analizzare il tempo che intercorre tra le aggiunte al carrello e i pagamenti tra i diversi prodotti.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come offrire promozioni per i prodotti che rimangono più a lungo nei carrelli e che sono a maggior rischio di abbandono.<br/>Questo modello utilizza la metrica Visualizzazioni carrello."

>[!CONTEXTUALHELP]
>id="template--cartAdditionsOvertimeReport"
>title="Visualizza il numero di volte in cui le persone hanno aggiunto qualcosa al carrello."
>abstract="**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui l’interesse della clientela per un prodotto è abbastanza alto da spingerla ad aggiungerlo al carrello.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare i consigli sui prodotti per tutta la clientela. Questo può essere fatto analizzando quali prodotti vengono aggiunti frequentemente agli stessi carrelli e suggerendo prodotti correlati in base agli articoli già presenti nel carrello."

>[!CONTEXTUALHELP]
>id="template--cartRemovalsOvertimeReport"
>title="Visualizza il numero di volte in cui le persone hanno rimosso qualcosa dal carrello."
>abstract="**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui la clientela non è più interessata a un prodotto, oppure può aiutarti a capire dove potrebbero esserci problemi nel processo di pagamento.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio rimuovere eventuali barriere esistenti nel processo di pagamento, ad esempio un’esperienza utente complicata.<br/>Questo modello utilizza la metrica Rimozioni carrello."

>[!CONTEXTUALHELP]
>id="template--purchaseConversionReport"
>title="Visualizza la conversione dell’acquisto in una visualizzazione funnel che mostra sessioni, carrelli e ordini. È inoltre possibile visualizzare le percentuali di conversione e le medie dei ricavi, delle unità e degli ordini."
>abstract="**Questo può aiutarti** a comprendere meglio come le persone procedono e abbandonano durante il processo di conversione.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare il tuo sito web per facilitare un processo di pagamento più fluido."


 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Funnel conversione del prodotto**] | Visualizza la conversione del prodotto in una visualizzazione funnel che mostra carrelli, pagamenti e ordini. È inoltre possibile visualizzare le percentuali di conversione e le medie dei ricavi, delle unità e degli ordini.<p>**Questo può aiutarti** a comprendere meglio come le persone procedono e abbandonano durante il processo di conversione.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare il tuo sito web per facilitare un processo di pagamento più fluido.</p> |
| **Prodotti** | Visualizza quali prodotti sono più determinanti per le metriche chiave, ad esempio i più venduti o i più visualizzati. <p>**Questo può aiutarti** a comprendere meglio quali sono i prodotti di maggior successo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come aumentare i finanziamenti per i prodotti di successo e diminuirli per i prodotti di minore successo.</p><p>Questo modello utilizza la metrica Ordini e la dimensione Prodotto. |
| **Prestazioni del prodotto** | Visualizza quali sono i prodotti più performanti.<p>**Questo può aiutarti** a comprendere meglio quali sono i prodotti di maggior successo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come aumentare i finanziamenti per i prodotti di successo e diminuirli per i prodotti di minore successo.</p><p>Questo modello utilizza le metriche Visualizzazioni prodotto, Aggiunte al carrello, Ordini, Ricavi e Unità. Utilizza anche la dimensione Prodotto. |
| **Funnel conversione del carrello** | Visualizza il numero di volte in cui le persone hanno eseguito eventi chiave di pagamento, ad esempio l’aggiunta di articoli al carrello, la visualizzazione del carrello, la rimozione di articoli dal carrello e il pagamento. <p>**Questo può aiutarti** a comprendere meglio quali parti del funnel del processo di pagamento portano alla conversione e quali sono più soggette all’abbandono del carrello.</p><p>**Sulla base di quanto appreso potresti** fare diverse cose, ad esempio ridurre l’attrito in determinati passaggi del processo di pagamento.</p> |
| **Carrelli** | Visualizza il numero di persone che hanno aggiunto un prodotto al carrello.<p>**Questo può aiutarti** a comprendere meglio il numero di persone che aggiungono un prodotto al carrello, rispetto al numero complessivo di prodotti aggiunti a un carrello.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio misurare l’efficacia delle tue pagine di prodotti.</p><p>Questo modello utilizza la metrica Carrelli. |
| **Visualizzazioni del carrello** | Visualizza il numero di volte in cui le persone hanno visualizzato il carrello. <p>**Questo può aiutarti** a comprendere meglio l’esperienza di pagamento nel tentativo di ridurre le percentuali di abbandono del carrello o ad analizzare il tempo che intercorre tra le aggiunte al carrello e i pagamenti tra i diversi prodotti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come offrire promozioni per i prodotti che rimangono più a lungo nei carrelli e che sono a maggior rischio di abbandono.</p><p>Questo modello utilizza la metrica Visualizzazioni carrello. |
| **Aggiunte al carrello** | Visualizza il numero di volte in cui le persone hanno aggiunto qualcosa al carrello. <p>**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui l’interesse della clientela per un prodotto è abbastanza alto da spingerla ad aggiungerlo al carrello.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare i consigli sui prodotti per tutta la clientela. Questo può essere fatto analizzando quali prodotti vengono aggiunti frequentemente agli stessi carrelli e suggerendo prodotti correlati in base agli articoli già presenti nel carrello. |
| **Rimozioni dal carrello** | Visualizza il numero di volte in cui le persone hanno rimosso qualcosa dal carrello.<p>**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui la clientela non è più interessata a un prodotto, oppure può aiutarti a capire dove potrebbero esserci problemi nel processo di pagamento.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio rimuovere eventuali barriere esistenti nel processo di pagamento, ad esempio un’esperienza utente complicata.</p><p>Questo modello utilizza la metrica Rimozioni carrello. |
| **Funnel conversione dell’acquisto** | Visualizza la conversione dell’acquisto in una visualizzazione funnel che mostra sessioni, carrelli e ordini. È inoltre possibile visualizzare le percentuali di conversione e le medie dei ricavi, delle unità e degli ordini.<p>**Questo può aiutarti** a comprendere meglio come le persone procedono e abbandonano durante il processo di conversione.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare il tuo sito web per facilitare un processo di pagamento più fluido.</p> |
| **Ricavi** | <!--duplicated in Most popular section-->Visualizza l’importo monetario dei prodotti acquistati in tutti gli ordini.<p>**Questo può aiutarti** a comprendere meglio quali elementi dimensionali hanno contribuito ai ricavi, combinando la metrica Ricavi con qualsiasi dimensione. Ad esempio, puoi visualizzare le campagne principali (utilizzando la dimensione Codice di tracciamento) che hanno contribuito ai ricavi. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare le campagne che non soddisfano gli obiettivi di ricavo previsti.</p><p>Questo modello utilizza la metrica Entrate. |
| **Ordini** | <!--duplicated in Most popular section-->Visualizza il numero totale di eventi di acquisto effettuati sul sito. <p>**Questo può aiutarti** a capire meglio quali elementi dimensionali hanno contribuito a un ordine, combinando la metrica Ordini con qualsiasi dimensione. Ad esempio, puoi vedere le campagne principali (utilizzando la dimensione Codice di tracciamento) che hanno contribuito agli acquisti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare le campagne che non soddisfano i target di acquisto previsti. </p><p>Questo modello utilizza la metrica Ordini. |

### Web: pubblico {#web-audience}

<!--AA only-->

>[!CONTEXTUALHELP]
>id="template--people"
>title="Visualizza il numero di persone che interagiscono con il tuo brand."
>abstract="**Questo può aiutarti** a comprendere meglio le tendenze di utilizzo sul tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come misurare l’efficacia delle recenti attività di marketing nel generare nuovi visitatori per il tuo sito."

>[!CONTEXTUALHELP]
>id="template--bots"
>title="Visualizza le visualizzazioni di pagina e le tendenze relative al traffico da bot sul sito."
>abstract="**Questo può aiutarti** a comprendere meglio la quantità di traffico da bot filtrato dai tuoi rapporti, in base alle regole bot che hai configurato.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio continuare a monitorare l’attività dei bot per identificare nuovi pattern."

>[!CONTEXTUALHELP]
>id="template--firstvsrepeatvisitors"
>title="Visualizza un confronto tra visitatori nuovi e visitatori ripetuti."
>abstract="**Questo può aiutarti** a comprendere meglio l’efficacia del tuo sito nel mantenere la fedeltà della clientela oppure la velocità con cui ne acquisisci di nuova.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio offrire ai nuovi visitatori degli incentivi per acquisti futuri, così da invogliarli a ritornare."

>[!CONTEXTUALHELP]
>id="template--personid"
>title="Visualizza il comportamento di singoli utenti su vari canali."
>abstract="**Questo può aiutarti** a comprendere meglio il percorso cliente completo e le interazioni tra più punti di contatto.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come personalizzare le attività di marketing per indirizzare meglio le preferenze degli utenti."

>[!CONTEXTUALHELP]
>id="aa-template--timeZoneRankedReport"
>title="Visualizza i fusi orari principali dei visitatori che accedono al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio in quali fusi orari vivono i tuoi visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare la manutenzione del sito in orari che interessino il minor numero di persone."

>[!CONTEXTUALHELP]
>id="aa-template--location"
>title="Visualizza una panoramica della posizione del visitatore in una visualizzazione della mappa."
>abstract="**Questo può aiutarti** a comprendere meglio dove si trovano i visitatori che visitano il tuo sito. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come concentrare le risorse di marketing nelle posizioni in cui visualizzi maggiore interesse e opportunità."

>[!CONTEXTUALHELP]
>id="aa-template--domainRankedReport"
>title="Visualizza i domini principali dei visitatori che accedono al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio da quali organizzazioni provengono i tuoi visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio indirizzare i contenuti verso la clientela maggiore."

>[!CONTEXTUALHELP]
>id="aa-template--topLevelDomainRankedReport"
>title="Visualizza i domini principali dei visitatori che accedono al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio da quali organizzazioni provengono i tuoi visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio indirizzare i contenuti verso la clientela maggiore."

>[!CONTEXTUALHELP]
>id="aa-template--browserWidthRankedReport"
>title="Visualizza le dimensioni della larghezza dei browser principali che le persone utilizzano per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le dimensioni di larghezza dei browser più comuni. In questo modo è possibile massimizzare le attività di controllo qualità.<br/>Questo modello utilizza la dimensione Browser."

>[!CONTEXTUALHELP]
>id="aa-template--browserHeightRankedReport"
>title="Visualizza le dimensioni dell’altezza dei browser principali che le persone utilizzano per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le dimensioni di altezza dei browser più comuni. In questo modo è possibile massimizzare le attività di controllo qualità.<br/>Questo modello utilizza la dimensione Browser. "

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemRankedReport"
>title="Visualizza il nome e la versione dei sistemi operativi che le persone utilizzano per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio le versioni e i sistemi operativi più comuni utilizzati dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni tramite i principali sistemi operativi e relative versioni. In questo modo è possibile massimizzare le attività di controllo qualità."

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemTypeRankedReport"
>title="Visualizza il nome dei sistemi operativi utilizzati dalle persone per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio i sistemi operativi più comuni utilizzati dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con principali sistemi operativi. In questo modo è possibile massimizzare le attività di controllo qualità."

>[!CONTEXTUALHELP]
>id="aa-template--returnFrequencyRankedReport"
>title="Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili che le persone utilizzano per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle funzionalità di rete dei diversi operatori, in modo da garantire un’esperienza utente fluida.<br/>Questo modello utilizza la dimensione Operatore di telefonia mobile."

>[!CONTEXTUALHELP]
>id="aa-template--returnVisitorsOvertimeReport"
>title="Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili che le persone utilizzano per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle funzionalità di rete dei diversi operatori, in modo da garantire un’esperienza utente fluida.<br/>Questo modello utilizza la dimensione Operatore di telefonia mobile."

>[!CONTEXTUALHELP]
>id="aa-template--visitNumberRankedReport"
>title="Visualizza quante volte un visitatore ha visitato il sito."
>abstract="**Questo può aiutarti** a comprendere meglio quanto sono coinvolti i visitatori quando ritornano sul tuo sito. Questo viene applicato al ciclo di vita del visitatore, indipendentemente dall’intervallo di date del progetto.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare le attività di marketing per i visitatori frequenti.<br/>Questo modello utilizza la dimensione Numero di visite."

>[!CONTEXTUALHELP]
>id="aa-template--customerLoyaltyRankedReport"
>title="Visualizza il numero di visitatori del sito che hanno effettuato 0 acquisti precedenti, 1 acquisto precedente, 2 acquisti precedenti o 3+ acquisti precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio in che modo il tuo sito influisce sul comportamento d’acquisto.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrarti sui visitatori che tornano per fare un acquisto, in modo da poter incoraggiare un comportamento simile per i nuovi visitatori.<br/>Questo modello utilizza la dimensione Fedeltà della clientela."

>[!CONTEXTUALHELP]
>id="aa-template--daysBeforeFirstPurchaseRankedReport"
>title="Visualizza il numero di giorni che trascorrono tra la prima volta che un visitatore raggiunge il sito e il momento in cui effettua un acquisto. Ad esempio, se un visitatore effettua un acquisto un giorno dopo la prima visita, tutte le visite o gli eventi successivi appartengono all’elemento della dimensione 1 giorno."
>abstract="**Questo può aiutarti** a capire meglio quanto tempo impiegano i visitatori per effettuare un acquisto.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio aggiornare il tuo sito per incoraggiare un acquisto più veloce.<br/>Questo modello utilizza la dimensione Giorni prima del primo acquisto."

>[!CONTEXTUALHELP]
>id="aa-template--daysSinceLastPurchaseRankedReport"
>title="Visualizza il tempo trascorso tra l’hit corrente del visitatore e il suo acquisto più recente in quel momento."
>abstract="**Questo può aiutarti** a comprendere meglio il comportamento del visitatore dopo che ha acquistato qualcosa sul tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio aggiornare il tuo sito per incoraggiare gli acquisti successivi.<br/>Questo modello utilizza la dimensione Giorni dall’ultimo acquisto."

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenSizeRankedReport"
>title="Visualizza le dimensioni principali dello schermo dei dispositivi mobili che le persone utilizzano per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le dimensioni più comuni dello schermo dei dispositivi mobili. In questo modo è possibile massimizzare le attività di controllo qualità."

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenHeightRankedReport"
>title="Visualizza le dimensioni dell’altezza dello schermo dei dispositivi mobili principali che le persone utilizzano per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le altezze dello schermo dei dispositivi mobili più comuni. In questo modo è possibile massimizzare le attività di controllo qualità."

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenWidthRankedReport"
>title="Visualizzare le dimensioni della larghezza dello schermo dei dispositivi mobili principali che le persone utilizzano per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le larghezze dello schermo dei dispositivi mobili più comuni. In questo modo è possibile massimizzare le attività di controllo qualità."


<!--Both AA and CJA-->

>[!CONTEXTUALHELP]
>id="template--countryGeoReport"
>title="Visualizzare il Paese da cui provengono le persone che visitano il sito."
>abstract="**Questo può aiutarti** a capire meglio quali sono i Paesi più popolari da cui provengono i visitatori del tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in questi Paesi, oppure assicurarti che l’esperienza sul tuo sito sia ottimale in Paesi con lingue principali diverse.<br/>Questo modello utilizza la dimensione Paesi."

>[!CONTEXTUALHELP]
>id="template--stateGeoReport"
>title="Visualizza lo stato (negli Stati Uniti) da cui provengono le persone che visitano il sito. È simile al modello Aree geografiche, ma è specifico per gli Stati Uniti."
>abstract="**Questo può aiutarti** a comprendere meglio quali sono gli Stati Uniti più popolari da cui provengono i visitatori del tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in questi Stati.<br/>Questo modello utilizza la dimensione Stati Uniti."

>[!CONTEXTUALHELP]
>id="template--regionGeoReport"
>title="Visualizza l’area geografica da cui provengono le persone che visitano il sito. Un’area è un’area geografica più piccola di un Paese ma più grande di una città. In alcuni Paesi, un’area geografica è uno stato, una provincia o una prefettura. In altre aree, è un Paese costituente, un dipartimento o un’area metropolitana. "
>abstract="**Questo può aiutarti** a comprendere meglio le aree geografiche più popolari da cui provengono i visitatori del tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste aree geografiche, oppure assicurarti che l’esperienza del tuo sito sia ottimale nelle aree geografiche con lingue principali diverse. <br/>Questo modello utilizza le dimensioni ID(variables/geocountry) e Aree geografiche. "

>[!CONTEXTUALHELP]
>id="template--cityGeoReport"
>title="Visualizza la città da cui provengono le persone che visitano il sito."
>abstract="**Questo può aiutarti** a comprendere meglio le città più popolari da cui provengono i visitatori del tu sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste città. <br/>Questo modello utilizza la dimensione Città"

>[!CONTEXTUALHELP]
>id="template--dmaGeoReport"
>title="Visualizza le aree di marketing designate (DMA) all’interno degli Stati Uniti da cui provengono le persone che visitano il sito."
>abstract="**Questo può aiutarti** a comprendere meglio le aree geografiche più popolari da cui provengono i visitatori del tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing nelle aree geografiche di maggior successo. "

>[!CONTEXTUALHELP]
>id="template--languageRankedReport"
>title="Visualizza le lingue principali in cui i visitatori preferiscono visualizzare il contenuto."
>abstract="**Questo può aiutarti** a comprendere meglio le lingue preferite più frequentemente dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come concentrare le attività di localizzazione o di marketing per le lingue più popolari.<br/>Questo modello utilizza la dimensione Lingua."

>[!CONTEXTUALHELP]
>id="template--web-technology-template"
>title="Visualizza informazioni relative alla tecnologia che utilizzano le persone per accedere al tuo sito, ad esempio sistemi operativi, browser e dispositivi."
>abstract="**Questo può aiutarti** a comprendere meglio quali tecnologie vengono utilizzate più di frequente per accedere al tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare il tuo sito per le tecnologie in uso."

>[!CONTEXTUALHELP]
>id="template--browserRankedReport"
>title="Visualizza il nome e la versione dei principali browser che le persone utilizzano per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio i browser più comuni utilizzati dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando delle nuove versioni con i principali browser. In questo modo è possibile massimizzare le attività di controllo qualità.<br/>Questo modello utilizza la dimensione Browser."

>[!CONTEXTUALHELP]
>id="template--browserTypeRankedReport"
>title="Visualizza i nomi delle organizzazioni che hanno realizzato i principali browser utilizzati dalle persone per accedere al tuo sito. Questo si differenzia dal modello Browser in quanto non elenca le diverse versioni dello stesso browser come elementi della dimensione separati."
>abstract="**Questo può aiutarti** a comprendere meglio i browser più comuni utilizzati dai visitatori <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con l’utilizzo dei principali browser. In questo modo è possibile massimizzare le attività di controllo qualità. <br/>Questo modello utilizza la dimensione Tipo di browser. "


 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Visitatori nuovi e ripetuti**] | Visualizza un confronto tra visitatori nuovi e visitatori ripetuti. <p>**Questo può aiutarti** a comprendere meglio l’efficacia del tuo sito nel mantenere la fedeltà della clientela oppure la velocità con cui ne acquisisci di nuova.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio offrire ai nuovi visitatori degli incentivi per acquisti futuri, così da invogliarli a ritornare.</p><!-- This template uses the --> |
| **ID persona** | Visualizza il comportamento di singoli utenti su vari canali.<p>**Questo può aiutarti** a comprendere meglio il percorso cliente completo e le interazioni tra più punti di contatto.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come personalizzare le attività di marketing per indirizzare meglio le preferenze degli utenti.</p><!-- This template uses the --> |
| **Paesi** | Visualizzare il Paese da cui provengono le persone che visitano il sito.<p>**Questo può aiutarti** a capire meglio quali sono i Paesi più popolari da cui provengono i visitatori del tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in questi Paesi, oppure assicurarti che l’esperienza sul tuo sito sia ottimale in Paesi con lingue principali diverse.</p><p>Questo modello utilizza la dimensione Paesi. </p> |
| **Stati Uniti** | Visualizza lo stato (negli Stati Uniti) da cui provengono le persone che visitano il sito. È simile al modello Aree geografiche, ma è specifico per gli Stati Uniti.<p>**Questo può aiutarti** a comprendere meglio quali sono gli Stati Uniti più popolari da cui provengono i visitatori del tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in questi Stati.</p><p>Questo modello utilizza la dimensione Stati Uniti. </p> |
| **Aree geografiche** | Visualizza l’area geografica da cui provengono le persone che visitano il sito. Un’area è un’area geografica più piccola di un Paese ma più grande di una città. In alcuni Paesi, un’area geografica è uno stato, una provincia o una prefettura. In altre aree, è un Paese costituente, un dipartimento o un’area metropolitana. <p>**Questo può aiutarti** a comprendere meglio le aree geografiche più popolari da cui provengono i visitatori del tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività relative al marketing in queste aree geografiche oppure assicurarti che l’esperienza del tuo sito sia ottimale nelle aree geografiche con lingue principali diverse. </p><p>Questo modello utilizza le dimensioni ID(variabili/paese geografico) e Aree geografiche. </p> |
| **Città** | Visualizza la città da cui provengono le persone che visitano il sito. <p>**Questo può aiutarti** a comprendere meglio le città più popolari da cui provengono i visitatori del tu sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste città. </p><p>Questo modello utilizza la dimensione Città. </p> |
| **DMA USA** | Visualizza le aree di marketing designate (DMA) all’interno degli Stati Uniti da cui provengono le persone che visitano il sito.<p>**Questo può aiutarti** a comprendere meglio le aree geografiche più popolari da cui provengono i visitatori del tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing nelle aree geografiche di maggior successo. </p><!-- This template uses the --> |
| **Lingue** | Visualizza le lingue principali in cui i visitatori preferiscono visualizzare il contenuto. <p>**Questo può aiutarti** a comprendere meglio le lingue preferite più frequentemente dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come concentrare le attività di localizzazione o di marketing per le lingue più popolari.</p><p>Questo modello utilizza la dimensione Lingua.</p> |
| **Panoramica della tecnologia** | Visualizza informazioni relative alla tecnologia che le persone utilizzano per accedere al tuo sito, ad esempio sistemi operativi, browser e dispositivi. <p>**Questo può aiutarti** a comprendere meglio quali tecnologie vengono utilizzate più di frequente per accedere al tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare il tuo sito per le tecnologie in uso.</p> |
| **Browser** | Visualizza il nome e la versione dei principali browser che le persone utilizzano per accedere al tuo sito.<p>**Questo può aiutarti** a comprendere meglio i browser più comuni utilizzati dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando delle nuove versioni con i principali browser. In questo modo è possibile massimizzare le attività di controllo qualità.</p><p>Questo modello utilizza la dimensione Browser. </p> |
| **Tipi di browser** | Visualizza i nomi delle organizzazioni che hanno realizzato i principali browser utilizzati dalle persone per accedere al tuo sito. Questo si differenzia dal modello Browser in quanto non elenca le diverse versioni dello stesso browser come elementi della dimensione separati.<p>**Questo può aiutarti** a capire meglio i browser più comuni utilizzati dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando delle nuove versioni con i principali browser. In questo modo è possibile massimizzare le attività di controllo qualità. </p><p>Questo modello utilizza la dimensione Tipo di browser. </p> |

### Web: acquisizione {#web-acquisition}

<!--AA only-->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-acquisition-template"
>title="Visualizza in che modo il sito web ottiene visitatori sui dispositivi mobili."
>abstract="**Questo può aiutarti** a comprendere meglio i vari fattori che portano all’acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sui canali più efficaci.<br/>Questo modello utilizza le metriche Percentuale di mancati recapiti e Mancato recapito. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer."

>[!CONTEXTUALHELP]
>id="aa-template--advertisingAnalyticsPaidSearch"
>title="Visualizza i dati Google e di ricerca a pagamento di Bing affiancati."
>abstract="**Questo può aiutarti** a comprendere meglio la quantità di traffico che arriva al tuo sito e se la clientela si sta convertendo.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio stimare in termini di costi l’efficacia di una campagna pubblicitaria."

>[!CONTEXTUALHELP]
>id="aa-template--searchEngineRankRankedReport"
>title="Visualizza quale pagina dei risultati di ricerca su cui un visitatore ha fatto clic per arrivare sul sito. Ad esempio, se il sito viene visualizzato nella seconda pagina dei risultati di ricerca di un motore di ricerca, l’elemento della dimensione per questa variabile è Pagina di ricerca 2."
>abstract="**Questo può aiutarti** a comprendere meglio il posizionamento delle pagine nei risultati di ricerca.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la strategia SEO per garantire che i tuoi contenuti vengano visualizzati nella prima pagina dei risultati di ricerca."


<!--Both AA and CJA-->

>[!CONTEXTUALHELP]
>id="template--marketing-channel-overview-template"
>title="Quando viene utilizzata l’attribuzione personalizzata, questo modello mostra il modo in cui i visitatori arrivano sul tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali dei tuoi canali di marketing sono i più efficaci.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio investire maggiormente su canali di marketing efficaci e disinvestire da quelli meno influenti.<br/>Questo modello utilizza la dimensione ID(variables/marketingchannel) e la metrica Ricavi."

>[!CONTEXTUALHELP]
>id="template--firstouchChannelRankedReport"
>title="Visualizza il primo canale di marketing a cui un visitatore corrisponde durante il relativo periodo di coinvolgimento (30 giorni per impostazione predefinita)."
>abstract="**Questo può aiutarti** a comprendere meglio quali canali di marketing favoriscono il traffico iniziale verso il tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing nelle aree più efficaci.<br/>Questo modello utilizza la dimensione Canale di primo contatto."

>[!CONTEXTUALHELP]
>id="template--firstouchChannelDetailRankedReport"
>title="Visualizza i dettagli sul primo canale di marketing a cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita)."
>abstract="**Questo può aiutarti** a comprendere meglio cosa ha contribuito all’hit corrispondente a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing “Ricerca a pagamento”, puoi utilizzare i dettagli del canale per visualizzare quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing nelle aree più efficaci.<br/>Questo modello utilizza la dimensione Dettaglio canale di primo contatto."

>[!CONTEXTUALHELP]
>id="template--campaignConversionReport"
>title="Visualizza il numero di click-through e di pagamenti per le campagne."
>abstract="**Questo può aiutarti** a comprendere meglio il modo in cui le campagne di marketing promuovono una conversione.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio individuare quali campagne di marketing generano il maggior ROI."

>[!CONTEXTUALHELP]
>id="template--retail-campaign-performance-template"
>title="Visualizza i dettagli sulle prestazioni delle campagne di marketing."
>abstract="**Questo può aiutarti** a comprendere meglio i vari indicatori di successo associati alle campagne, come ricavi, visualizzazioni prodotti, ordini e così via.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sulle campagne che generano maggiori ricavi. <br/>Questo modello utilizza le metriche Ricavi, Visualizzazioni prodotto, Aggiunte carrello, Ordini e Unità. Utilizza inoltre le dimensioni Codice di tracciamento e Dominio di riferimento."

>[!CONTEXTUALHELP]
>id="template--web-acquisition-template"
>title="Visualizza come il tuo sito web ottiene visitatori."
>abstract="**Questo può aiutarti** a comprendere meglio i vari fattori che portano all’acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sui canali più efficaci.<br/>Questo modello utilizza le metriche Percentuale di mancati recapiti e Mancato recapito. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer."

>[!CONTEXTUALHELP]
>id="template--searchKeywordRankedReport"
>title="Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito, indipendentemente dal fatto che siano a pagamento o naturali."
>abstract="**Questo può aiutarti** a comprendere meglio le parole chiave che le persone utilizzano nelle ricerche che generano traffico sul sito. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che favoriscono il traffico del sito.<br/>Questo modello utilizza la dimensione Parola chiave di ricerca."

>[!CONTEXTUALHELP]
>id="template--searchPaidKeywordRankedReport"
>title="Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il sito e che corrispondono al rilevamento della ricerca a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio le parole chiave che le persone utilizzano nelle ricerche che generano traffico sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che favoriscono il traffico del sito. <br/>Questo modello utilizza la dimensione Parola chiave di ricerca - A pagamento. "

>[!CONTEXTUALHELP]
>id="template--searchNaturalKeywordRankedReport"
>title="Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il tuo sito e che non corrispondono al rilevamento della ricerca a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio le parole chiave che le persone utilizzano nelle ricerche che generano traffico sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che favoriscono il traffico del sito.<br/>Questo modello utilizza la dimensione Parola chiave di ricerca - Naturale. "

>[!CONTEXTUALHELP]
>id="template--searchRankedReport"
>title="Visualizza i motori di ricerca utilizzati dai visitatori per raggiungere il sito, indipendentemente dal fatto che siano a pagamento o naturali."
>abstract="**Questo può aiutarti** a comprendere meglio i motori di ricerca che le persone utilizzano e che generano traffico sul sito. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività SEO sui motori di ricerca che favoriscono maggiore traffico verso il tuo sito.<br/>Questo modello utilizza la dimensione Motore di ricerca. "

>[!CONTEXTUALHELP]
>id="template--searchPaidRankedReport"
>title="Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il sito e che corrispondono al rilevamento della ricerca a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio i motori di ricerca che le persone utilizzano e che generano traffico sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività SEO sui motori di ricerca che favoriscono maggiore traffico verso il tuo sito. <br/>Questo modello utilizza la dimensione Motore di ricerca - A pagamento."

>[!CONTEXTUALHELP]
>id="template--searchNaturalRankedReport"
>title="Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il tuo sito e che non corrispondono al rilevamento della ricerca a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio i motori di ricerca che le persone utilizzano e che generano traffico sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività SEO sui motori di ricerca che favoriscono maggiore traffico verso il tuo sito.<br/>Questo modello utilizza la dimensione Motore di ricerca - Naturale."

>[!CONTEXTUALHELP]
>id="template--referringDomainRankedReport"
>title="Visualizza i domini su cui le persone fanno clic per raggiungere il tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali siti di terze parti favoriscono maggiore traffico verso il tuo sito. Affinché l’elemento dimensione venga visualizzato, deve esistere un collegamento sul sito esterno e un visitatore deve fare clic su di esso.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come creare o adattare il contenuto per allinearlo maggiormente agli interessi dei visitatori provenienti dai principali domini di riferimento. <br/>Questo modello utilizza la dimensione Dominio di riferimento."

>[!CONTEXTUALHELP]
>id="template--referringDomainOriginalRankedReport"
>title="Visualizza il primo dominio di riferimento su cui le persone hanno fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intero ciclo di vita dell’ID visitatore."
>abstract="**Questo può aiutarti** a comprendere meglio quali siti di terze parti inizialmente favoriscono il traffico verso il tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come creare o adattare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali domini di riferimento. <br/>Questo modello utilizza la dimensione Dominio di riferimento originale."

>[!CONTEXTUALHELP]
>id="template--referrerRankedReport"
>title="Visualizza su quali URL si trovano i visitatori quando fanno clic per raggiungere il sito. Affinché l’elemento della dimensione venga visualizzato, deve esistere un collegamento sull’URL esterno e un visitatore deve fare clic su di esso."
>abstract="**Questo può aiutarti** a comprendere meglio quali URL specifici favoriscono maggiore traffico verso il tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come creare o adattare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali URL. <br/>Questo modello utilizza la dimensione Dominio di riferimento.</p>"

>[!CONTEXTUALHELP]
>id="template--referrerTypeRankedReport"
>title="Visualizza i canali generici su cui i visitatori hanno fatto clic per arrivare al tuo sito. Adobe gestisce le regole per ciascun canale. I canali possibili includono motori di ricerca, social network, altri siti web, disco rigido o e-mail."
>abstract="**Questo può aiutarti** a comprendere meglio quale tipo di referrer favorisce maggior traffico verso il tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come creare o adattare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti da un determinato canale.<br/>Questo modello utilizza la dimensione Tipo referrer."


 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Canali di marketing**] > [!UICONTROL **Rapporto di panoramica sul canale**] | Quando viene utilizzata l’attribuzione personalizzata, questo modello mostra il modo in cui i visitatori arrivano sul tuo sito.<p>**Questo può aiutarti** a comprendere meglio quali dei tuoi canali di marketing sono i più efficaci.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio investire maggiormente su canali di marketing efficaci e disinvestire da quelli meno influenti.</p><p>Questo modello utilizza la dimensione ID(variables/marketingchannel) e la metrica Ricavi.</p> |
| [!UICONTROL **Canali di marketing**] > [!UICONTROL **Canale di primo contatto**] | Visualizza il primo canale di marketing a cui un visitatore corrisponde durante il relativo periodo di coinvolgimento (30 giorni per impostazione predefinita). <p>**Questo può aiutarti** a comprendere meglio quali canali di marketing favoriscono il traffico iniziale verso il tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing nelle aree più efficaci.</p><p>Questo modello utilizza la dimensione Canale di primo contatto.</p> |
| [!UICONTROL **Canali di marketing**] > [!UICONTROL **Dettaglio canale di primo contatto**] | Visualizza i dettagli sul primo canale di marketing a cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a comprendere meglio cosa ha contribuito all’hit corrispondente a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing “Ricerca a pagamento”, puoi utilizzare i dettagli del canale per visualizzare quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing nelle aree più efficaci.</p><p>Questo modello utilizza la dimensione Dettaglio canale di primo contatto.</p> |
| [!UICONTROL **Canali di marketing**] > [!UICONTROL **Canale di ultimo contatto**] | Visualizza il canale di marketing più recente a cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a comprendere meglio quali canali di marketing favoriscono il traffico iniziale verso il tuo sito che si traduce in conversioni.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing nelle aree più efficaci.</p><p>Questo modello utilizza la dimensione Canale di ultimo contatto.  </p> |
| [!UICONTROL **Canali di marketing**] > [!UICONTROL **Dettagli canale di ultimo contatto**] | Visualizza i dettagli sul canale di marketing più recente a cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a comprendere meglio cosa ha contribuito all’hit corrispondente a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing “Ricerca a pagamento”, puoi utilizzare i dettagli del canale per visualizzare quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing nelle aree più efficaci. </p><p>Questo modello utilizza la dimensione Dettaglio del canale di primo contatto. </p> |
| [!UICONTROL **Campagne**] > [!UICONTROL **Codice di tracciamento**] | Visualizza i nomi dei codici di tracciamento sul tuo sito. Puoi inserire collegamenti con valori di parametri delle stringhe di query diversi in posizioni diverse su Internet.<p>**Questo ti aiuta** a capire meglio quali collegamenti sono stati più efficaci nel portare traffico sul tuo sito. L’aggiunta di stringhe di query del codice di tracciamento è comune nelle e-mail, negli annunci pubblicitari, nei post sui social media e in altre attività di marketing utilizzate dalla tua organizzazione.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sulle campagne che generano maggiori entrate.</p><p>Questo modello utilizza la dimensione Codice di tracciamento. </p> |
| [!UICONTROL **Campagne**] > [!UICONTROL **Funnel di conversione campagna**] | Visualizza il numero di click-through e di pagamenti per le campagne. <p>**Questo può aiutarti** a comprendere meglio il modo in cui le campagne di marketing promuovono una conversione.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio individuare quali campagne di marketing generano il maggior ROI.</p> |
| [!UICONTROL **Campagne**] > [!UICONTROL **Prestazioni campagna**] | Visualizza i dettagli sulle prestazioni delle campagne di marketing.<p>**Questo può aiutarti** a comprendere meglio i vari indicatori di successo associati alle campagne, come ricavi, visualizzazioni prodotti, ordini e così via.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sulle campagne che generano maggiori entrate. </p><p>Questo modello utilizza le metriche Entrate, Visualizzazioni prodotto, Aggiunte al carrello, Ordini e Unità. Utilizza inoltre le dimensioni Codice di tracciamento e Dominio di riferimento. </p> |
| **Acquisizione web** | Visualizza come il tuo sito web ottiene visitatori.<p>**Questo può aiutarti** a comprendere meglio i vari fattori che portano all’acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sui canali più efficaci.</p><p>Questo modello utilizza le metriche Percentuale di mancati recapiti e Mancati recapiti. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer.  </p> |
| **Parole chiave di ricerca: tutte** | Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito, indipendentemente dal fatto che siano a pagamento o naturali. <p>**Questo può aiutarti** a comprendere meglio le parole chiave che le persone utilizzano nelle ricerche che generano traffico sul sito. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che favoriscono il traffico del sito.</p><p>Questo modello utilizza la dimensione Parola chiave di ricerca. </p> |
| **Parole chiave di ricerca: a pagamento** | Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il sito e che corrispondono al rilevamento della ricerca a pagamento.<p>**Questo può aiutarti** a comprendere meglio le parole chiave che le persone utilizzano nelle ricerche che generano traffico sul sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che favoriscono il traffico del sito. </p><p>Questo modello utilizza la dimensione Parola chiave di ricerca: a pagamento. </p> |
| **Parole chiave di ricerca: naturale** | Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il tuo sito e che non corrispondono al rilevamento della ricerca a pagamento.<p>**Questo può aiutarti** a comprendere meglio le parole chiave che le persone utilizzano nelle ricerche che generano traffico sul sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che favoriscono il traffico del sito.</p><p>Questo modello utilizza la dimensione Parola chiave di ricerca: naturale. </p> |
| **Motori di ricerca: tutti** | Visualizza i motori di ricerca utilizzati dai visitatori per raggiungere il sito, indipendentemente dal fatto che siano a pagamento o naturali. <p>**Questo può aiutarti** a comprendere meglio i motori di ricerca che le persone utilizzano e che generano traffico sul sito. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività SEO sui motori di ricerca che favoriscono maggiore traffico verso il tuo sito.</p><p>Questo modello utilizza la dimensione Motore di ricerca. </p> |
| **Motori di ricerca: a pagamento** | Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il sito e che corrispondono al rilevamento della ricerca a pagamento.<p>**Questo può aiutarti** a comprendere meglio i motori di ricerca che le persone utilizzano e che generano traffico sul sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività SEO sui motori di ricerca che favoriscono maggiore traffico verso il tuo sito. </p><p>Questo modello utilizza la dimensione Motore di ricerca: a pagamento. </p> |
| **Motori di ricerca: naturale** | Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il tuo sito e che non corrispondono al rilevamento della ricerca a pagamento.<p>**Questo può aiutarti** a comprendere meglio i motori di ricerca che le persone utilizzano e che generano traffico sul sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività SEO sui motori di ricerca che favoriscono maggiore traffico verso il tuo sito.</p><p>Questo modello utilizza la dimensione Motore di ricerca: naturale. </p> |
| **Domini di riferimento** | Visualizza i domini su cui le persone fanno clic per raggiungere il tuo sito.<p>**Questo può aiutarti** a comprendere meglio quali siti di terze parti favoriscono maggiore traffico verso il tuo sito. Affinché l’elemento dimensione venga visualizzato, deve esistere un collegamento sul sito esterno e un visitatore deve fare clic su di esso.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come creare o adattare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali domini di riferimento. </p><p>Questo modello utilizza la dimensione Dominio di riferimento. </p> |
| **Domini di riferimento originali** | Visualizza il primo dominio di riferimento su cui le persone hanno fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intero ciclo di vita dell’ID visitatore.<p>**Questo può aiutarti** a comprendere meglio quali siti di terze parti inizialmente favoriscono il traffico verso il tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come creare o adattare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali domini di riferimento originali. </p><p>Questo modello utilizza la dimensione Dominio di riferimento originale. </p> |
| **Riferimenti** | Visualizza su quali URL si trovano i visitatori quando fanno clic per raggiungere il sito. Affinché l’elemento della dimensione venga visualizzato, deve esistere un collegamento sull’URL esterno e un visitatore deve fare clic su di esso.  <p>**Questo può aiutarti** a comprendere meglio quali URL specifici favoriscono maggiore traffico verso il tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come creare o adattare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali URL. </p><p>Questo modello utilizza la dimensione Dominio di riferimento. </p><p>Questo modello utilizza la dimensione Referrer. </p> |
| **Tipi di referrer** | Visualizza i canali generici su cui i visitatori hanno fatto clic per arrivare al tuo sito. Adobe gestisce le regole per ciascun canale. I canali possibili includono motori di ricerca, social network, altri siti web, disco rigido o e-mail.<p>**Questo può aiutarti** a comprendere meglio quale tipo di referrer favorisce maggior traffico verso il tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come creare o adattare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti da un determinato canale.</p><p>Questo modello utilizza la dimensione Tipo di referrer.</p> |

### Mobile: app mobile {#mobile-app}

>[!CONTEXTUALHELP]
>id="template--mobileappscreens"
>title="Visualizza il numero di eventi, sessioni e persone associati a ciascuna schermata nell’app mobile."
>abstract="**Questo può aiutarti** a comprendere meglio quali schermate del tuo sito sono più popolari.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare i contenuti delle schermate più popolari."

>[!CONTEXTUALHELP]
>id="template--mobileappactions"
>title="Visualizza le azioni che le persone eseguono sull’app mobile."
>abstract="**Questo può aiutarti** a comprendere meglio come le persone utilizzano la tua app e il valore che ne traggono.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come sviluppare funzioni che completino o perfezionino quelle più popolari."


<!--CJA only-->

>[!CONTEXTUALHELP]
>id="template--mobile-lifecycle-metrics-app-usage-template"
>title="Visualizza il numero di utenti, avvii e primi avvii sull’app, nonché la durata media di una sessione."
>abstract="**Questo può aiutarti** a comprendere meglio quanto viene utilizzata l’applicazione. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare le prestazioni dell’app in modo che possa essere adattata alla quantità di utilizzo."

>[!CONTEXTUALHELP]
>id="template--mobile-app-journeys"
>title="Visualizza i pattern di utilizzo in primo piano per l’app mobile."
>abstract="**Questo può aiutarti** a comprendere meglio il modo in cui le persone utilizzano la tua app. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare il modo in cui le persone passano da una schermata all’altra per identificare i flussi di lavoro più comuni."

>[!CONTEXTUALHELP]
>id="template--mobile-app-key-metrics"
>title="Visualizza alcune delle metriche più comuni per le app mobili."
>abstract="**Questo può aiutarti** a comprendere meglio le prestazioni di base della tua app mobile.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare lo stato e le prestazioni complessive dell’app."

>[!CONTEXTUALHELP]
>id="template--mobile-app-messaging"
>title="Visualizza i dati sulle prestazioni per la messaggistica in-app e push dell’applicazione."
>abstract="**Questo può aiutarti** a comprendere meglio come le persone utilizzano le funzionalità di messaggistica in-app e l’efficacia delle notifiche push nell’indirizzare più traffico verso la tua app.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare l’esperienza di notifica push in-app."

>[!CONTEXTUALHELP]
>id="template--mobile-app-performance-template"
>title="Visualizza le prestazioni dell’app e i punti in cui gli utenti riscontrano problemi."
>abstract="**Questo può aiutarti** a comprendere meglio se chi utilizza la tua app riscontra rallentamenti o prestazioni ridotte. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come risolvere i problemi esistenti o migliorare le prestazioni dell’app prima che si verifichino."

>[!CONTEXTUALHELP]
>id="template--mobile-app-retention"
>title="Visualizza quali utenti sono i più fedeli all’applicazione e cosa fanno all’interno di essa."
>abstract="**Questo può aiutarti** a comprendere meglio come i tuoi utenti più fedeli utilizzano la tua applicazione.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare le attività di marketing per le funzioni utilizzate dalla clientela più fedele."


 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Schermate app mobile**] | Visualizza il numero di eventi, sessioni e persone associati a ciascuna schermata nell’app mobile.<p>**Questo può aiutarti** a comprendere meglio quali schermate del tuo sito sono più popolari.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare i contenuti delle schermate più popolari.</p><p>Questo modello utilizza le metriche Eventi, Sessioni, Persone e Variazione percentuale. Utilizza anche la dimensione Titolo pagina.</p> |
| **Azioni app mobile** | Visualizza le azioni che le persone eseguono sull’app mobile. <p>**Questo può aiutarti** a comprendere meglio il modo in cui le persone utilizzano la tua app e il valore che ne traggono.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come migliorare lo sviluppo di funzioni che completino o perfezionino quelle più popolari.</p><p>Questo modello utilizza le metriche Eventi, Sessioni, Persone e Variazione percentuale. |
| **Utilizzo app mobile** | Visualizza il numero di utenti, avvii e primi avvii sull’app, nonché la durata media di una sessione.<p>**Questo può aiutarti** a comprendere meglio quanto viene utilizzata l’applicazione. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare le prestazioni dell’app in modo che possa essere adattata alla quantità di utilizzo.</p><!-- This template uses the --> |
| **Percorsi app mobile** | Visualizza i pattern di utilizzo in primo piano per l’app mobile. <p>**Questo può aiutarti** a comprendere meglio il modo in cui le persone utilizzano la tua app. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare il modo in cui le persone passano da una schermata all’altra per i flussi di lavoro più comuni. </p><!-- This template uses the --> |
| **Metriche app mobile** | Visualizza alcune delle metriche più comuni per le app mobili. <p>**Questo può aiutarti** a comprendere meglio le prestazioni di base della tua app mobile.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare lo stato e le prestazioni complessive dell’app.</p><!-- This template uses the --> |
| **Messagistica app mobile** | Visualizza i dati sulle prestazioni per la messaggistica in-app e push dell’applicazione.<p>**Questo può aiutarti** a comprendere meglio come le persone utilizzano le funzionalità di messaggistica in-app e l’efficacia delle notifiche push nell’indirizzare più traffico verso la tua app.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare l’esperienza di notifica push in-app.</p><!-- This template uses the --> |
| **Prestazioni app mobile** | Visualizza le prestazioni dell’app e i punti in cui gli utenti riscontrano problemi. <p>**Questo può aiutarti** a comprendere meglio se chi utilizza la tua app riscontra rallentamenti o prestazioni ridotte. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come risolvere dei problemi esistenti o migliorare le prestazioni dell’app prima che si verifichino dei problemi.</p><!-- This template uses the --> |
| **Conservazione app mobile** | Visualizza quali utenti sono i più fedeli all’applicazione e cosa fanno all’interno di essa. <p>**Questo può aiutarti** a comprendere meglio come i tuoi utenti più fedeli utilizzano la tua applicazione.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare le attività di marketing per le funzioni utilizzate dalla clientela più fedele.</p><!-- This template uses the --> |

### Mobile: informazioni sui dispositivi mobili {#mobile-devices}

>[!CONTEXTUALHELP]
>id="template--mobileCarrierRankedReport"
>title="Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili che le persone utilizzano per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle funzionalità di rete dei diversi operatori, in modo da garantire un’esperienza utente fluida.<br/>Questo modello utilizza la dimensione Operatore di telefonia mobile."

>[!CONTEXTUALHELP]
>id="template--mobileDeviceNameRankedReport"
>title="Visualizza la marca e il modello dei dispositivi mobili utilizzati dalle persone per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali siano i dispositivi mobili più popolari nella tua base di utenti.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio ottimizzare il rendering del sito per i dispositivi mobili più comuni.<br/>Questo modello utilizza la dimensione Nome dispositivo mobile."

>[!CONTEXTUALHELP]
>id="template--mobileDeviceTypeRankedReport"
>title="Visualizza i tipi di dispositivi mobili utilizzati dalle persone per accedere al sito, ad esempio telefoni e tablet."
>abstract="**Questo può aiutarti** a comprendere meglio i vari tipi di dispositivi mobili che vengono utilizzati per accedere al tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare il tuo sito per i tipi di dispositivi mobili più utilizzati.<br/>Questo modello utilizza la dimensione Tipo di dispositivo mobile."

>[!CONTEXTUALHELP]
>id="template--mobileManufacturerRankedReport"
>title="Visualizza i produttori dei dispositivi mobili utilizzati per accedere al sito, ad esempio Apple e Samsung."
>abstract="**Questo può aiutarti** a comprendere meglio quali produttori sono più popolari nella tua base di utenti.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle capacità dei diversi produttori, in modo da garantire un’esperienza utente fluida.<br/>Questo modello utilizza la dimensione Produttore dispositivi mobili."


 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Gestore di telefonia mobile**] | Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili che le persone utilizzano per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle funzionalità di rete dei diversi operatori, in modo da garantire un’esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Gestore di telefonia mobile.</p> |
| **Dispositivi** | Visualizza la marca e il modello dei dispositivi mobili utilizzati dalle persone per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio quali siano i dispositivi mobili più popolari nella tua base di utenti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio ottimizzare il rendering del sito per i dispositivi mobili più comuni.</p><p>Questo modello utilizza la dimensione Nome dispositivo mobile.</p> |
| **Tipo di dispositivo** | Visualizza i tipi di dispositivi mobili utilizzati dalle persone per accedere al sito, ad esempio telefoni e tablet.<p>**Questo può aiutarti** a comprendere meglio i vari tipi di dispositivi mobili che vengono utilizzati per accedere al tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare il tuo sito per i tipi di dispositivi mobili più utilizzati.</p><p>Questo modello utilizza la dimensione Tipo di dispositivo mobile.</p> |
| **Produttore** | Visualizza i produttori dei dispositivi mobili utilizzati per accedere al sito, ad esempio Apple e Samsung.<p>**Questo può aiutarti** a comprendere meglio quali produttori sono più popolari nella tua base di utenti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle capacità dei diversi produttori, in modo da garantire un’esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Produttore dispositivi mobili.</p> |

### Suddivisione temporale {#time-parting}

<!--CJA only-->

>[!CONTEXTUALHELP]
>id="cja-template--minuteOfHour"
>title="Visualizza il numero di eventi, sessioni e persone sul sito, suddivisi per minuto. Ad esempio, se disponi di un rapporto con un arco temporale di un singolo giorno, il primo minuto di ogni ora del giorno viene raggruppato nello stesso elemento dimensionale."
>abstract="**Questo può aiutarti** a comprendere meglio le tendenze a livello granulare.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio ottimizzare le risorse per le ore di punta, minuto per minuto.<br/>Questo modello utilizza la dimensione Minuto dell’ora."

>[!CONTEXTUALHELP]
>id="cja-template--hourOfDay"
>title="Visualizza eventi, sessioni e persone sul sito, suddivisi per ora del giorno. Ad esempio, se disponi di un rapporto che copre il periodo dal 1° gennaio al 7 gennaio, la prima ora di ogni giorno viene raggruppata nello stesso elemento dimensionale."
>abstract="**Questo può aiutarti** a comprendere meglio l’ora del giorno in cui il tuo sito viene visitato più e meno frequentemente.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse di elaborazione al sito durante le ore con più traffico.<br/>Questo modello utilizza la dimensione Ora del giorno."

>[!CONTEXTUALHELP]
>id="cja-template--am-pm"
>title="Visualizza eventi, sessioni e persone sul tuo sito, suddivisi per ore AM e PM. Ad esempio, se disponi di un rapporto che copre il periodo dal 1° gennaio al 7 gennaio, le ore prima di mezzogiorno di ciascun giorno vengono raggruppate nello stesso elemento della dimensione."
>abstract="**Questo può aiutarti** a comprendere meglio l’ora del giorno in cui il tuo sito viene visitato più e meno frequentemente.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse di elaborazione al sito durante le ore con traffico elevato.<br/>Questo modello utilizza la dimensione AM/PM."

>[!CONTEXTUALHELP]
>id="cja-template--dayOfWeek"
>title="Visualizza eventi, sessioni e persone sul sito, suddivisi per giorno della settimana. Ad esempio, se disponi di un rapporto che copre il mese di gennaio, ogni giorno della settimana viene raggruppato nello stesso elemento della dimensione."
>abstract="**Questo può aiutarti** a comprendere meglio quali giorni della settimana il tuo sito viene visitato più e meno frequentemente.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio predisporre in maniera più appropriata il personale del call center nei giorni con traffico elevato.<br/>Questo modello utilizza la dimensione Giorno della settimana."

>[!CONTEXTUALHELP]
>id="cja-template--dayOfMonth"
>title="Visualizza eventi, sessioni e persone sul sito, suddivisi per giorno del mese. Ad esempio, se disponi di un rapporto che copre un intero anno, ogni giorno del mese viene raggruppato nello stesso elemento della dimensione."
>abstract="**Questo può aiutarti** a comprendere meglio quali giorni di ogni mese il tuo sito viene visitato più e meno frequentemente.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio predisporre in maniera più appropriata il personale del call center nei giorni con traffico elevato.<br/>Questo modello utilizza la dimensione Giorno del mese."

>[!CONTEXTUALHELP]
>id="cja-template--dayOfYear"
>title="Visualizza eventi, sessioni e persone sul sito, suddivisi per giorno dell’anno. Ad esempio, se disponi di un rapporto che ricopre più anni, ogni giorno dell’anno viene raggruppato nello stesso elemento della dimensione."
>abstract="**Questo può aiutarti** a comprendere meglio quali giorni di ogni anno il tuo sito viene visitato più e meno frequentemente.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio predisporre in maniera più appropriata il personale del call center nei giorni con traffico elevato.<br/>Questo modello utilizza la dimensione Giorno dell’anno."

>[!CONTEXTUALHELP]
>id="cja-template--weekdayWeekend"
>title="Visualizza eventi, sessioni e persone sul sito, suddivisi per giorni del fine settimana e giorni feriali. Ad esempio, se disponi di un rapporto che ricopre il mese di gennaio, i giorni feriali e i fine settimana sono raggruppati in elementi di dimensione separati."
>abstract="**Questo può aiutarti** a comprendere meglio le differenze nel traffico del sito durante i giorni feriali rispetto ai giorni del fine settimana.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio aumentare il personale del call center nei fine settimana, se il rapporto indica che tali giorni sono più impegnativi rispetto a quelli feriali.<br/>Questo modello utilizza la dimensione Giorno feriale/Fine settimana."

>[!CONTEXTUALHELP]
>id="cja-template--weekOfYear"
>title="Visualizza eventi, sessioni e persone sul sito, suddivisi per settimana dell’anno. Ad esempio, se disponi di un rapporto che copre più anni, ogni settimana viene raggruppata nello stesso elemento della dimensione."
>abstract="**Questo può aiutarti** a comprendere meglio quali settimane dell’anno il tuo sito viene visitato più e meno frequentemente.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio predisporre in maniera più appropriata il personale del call center nelle settimane con traffico elevato, ad esempio durante le vacanze.<br/>Questo modello utilizza la dimensione Settimana dell’anno."

>[!CONTEXTUALHELP]
>id="cja-template--monthOfYear"
>title="Visualizza eventi, sessioni e persone sul sito, suddivisi per mese dell’anno. Ad esempio, se disponi di un rapporto che copre più anni, ogni mese viene raggruppato nello stesso elemento della dimensione."
>abstract="**Questo può aiutarti** a comprendere meglio in quali mesi il tuo sito viene visitato più e meno frequentemente.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio predisporre in maniera più appropriata il personale del call center nei mesi con traffico elevato, ad esempio durante le vacanze.<br/>Questo modello utilizza la dimensione Mese dell’anno."

>[!CONTEXTUALHELP]
>id="cja-template--quarterOfYear"
>title="Visualizza eventi, sessioni e persone sul sito, suddivisi per trimestre dell’anno. Ad esempio, se disponi di un rapporto che copre più anni, ogni trimestre viene raggruppato nello stesso elemento della dimensione."
>abstract="**Questo può aiutarti** a comprendere meglio quali sono i trimestri in cui il tuo sito viene visitato più e meno frequentemente.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio programmare il lancio dei prodotti in modo da potenziare i trimestri storicamente a basso traffico.<br/>Questo modello utilizza la dimensione Trimestre dell’anno."


 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Minuto dell’ora**] | Visualizza il numero di eventi, sessioni e persone sul sito, suddivisi per minuto. Ad esempio, se disponi di un rapporto con un arco temporale di un singolo giorno, il primo minuto di ogni ora del giorno viene raggruppato nello stesso elemento dimensionale.<p>**Questo può aiutarti** a comprendere meglio le tendenze a livello granulare.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio ottimizzare le risorse per le ore di punta, minuto per minuto.</p><p>Questo modello utilizza la dimensione Minuto dell’ora.</p> |
| **Ora del giorno** | Visualizza eventi, sessioni e persone sul sito, suddivisi per ora del giorno. Ad esempio, se disponi di un rapporto che copre il periodo dal 1° gennaio al 7 gennaio, la prima ora di ogni giorno viene raggruppata nello stesso elemento dimensionale.<p>**Questo può aiutarti** a comprendere meglio l’ora del giorno in cui il tuo sito viene visitato più e meno frequentemente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse di elaborazione al sito durante le ore con più traffico.</p><p>Questo modello utilizza la dimensione Ora del giorno.</p> |
| **AM/PM** | Visualizza eventi, sessioni e persone sul tuo sito, suddivisi per ore AM e PM. Ad esempio, se disponi di un rapporto che copre il periodo dal 1° gennaio al 7 gennaio, le ore prima di mezzogiorno di ciascun giorno vengono raggruppate nello stesso elemento della dimensione.<p>**Questo può aiutarti** a comprendere meglio l’ora del giorno in cui il tuo sito viene visitato più e meno frequentemente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse di elaborazione al sito durante le ore con più traffico.</p><p>Questo modello utilizza la dimensione AM/PM.</p> |
| **Giorno della settimana** | Visualizza eventi, sessioni e persone sul sito, suddivisi per giorno della settimana. Ad esempio, se disponi di un rapporto che copre il mese di gennaio, ogni giorno della settimana viene raggruppato nello stesso elemento della dimensione. <p>**Questo può aiutarti** a comprendere meglio quali giorni della settimana il tuo sito viene visitato più e meno frequentemente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio predisporre in maniera più appropriata il personale del call center nei giorni con traffico elevato.</p><p>Questo modello utilizza la dimensione Giorno della settimana.</p> |
| **Giorno del mese** | Visualizza eventi, sessioni e persone sul sito, suddivisi per giorno del mese. Ad esempio, se disponi di un rapporto che copre un intero anno, ogni giorno del mese viene raggruppato nello stesso elemento della dimensione. <p>**Questo può aiutarti** a comprendere meglio quali giorni di ogni mese il tuo sito viene visitato più e meno frequentemente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio predisporre in maniera più appropriata il personale del call center nei giorni con traffico elevato.</p><p>Questo modello utilizza la dimensione Giorno del mese.</p> |
| **Giorno dell’anno** | Visualizza eventi, sessioni e persone sul sito, suddivisi per giorno dell’anno. Ad esempio, se disponi di un rapporto che ricopre più anni, ogni giorno dell’anno viene raggruppato nello stesso elemento della dimensione. <p>**Questo può aiutarti** a comprendere meglio quali giorni di ogni anno il tuo sito viene visitato più e meno frequentemente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio predisporre in maniera più appropriata il personale del call center nei giorni con traffico elevato.</p><p>Questo modello utilizza la dimensione Giorno dell’anno.&lt;/> |
| **Giorno feriale/Fine settimana** | Visualizza eventi, sessioni e persone sul sito, suddivisi per giorni del fine settimana e giorni feriali. Ad esempio, se disponi di un rapporto che ricopre il mese di gennaio, i giorni feriali e i fine settimana sono raggruppati in elementi di dimensione separati. <p>**Questo può aiutarti** a comprendere meglio le differenze nel traffico del sito durante i giorni feriali rispetto ai giorni del fine settimana.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio aumentare il personale del call center nei fine settimana, se il rapporto indica che tali giorni sono più impegnativi rispetto a quelli feriali.</p><p>Questo modello utilizza la dimensione Giorno feriale/Fine settimana.</p> |
| **Settimana dell’anno** | Visualizza eventi, sessioni e persone sul sito, suddivisi per settimana dell’anno. Ad esempio, se disponi di un rapporto che copre più anni, ogni settimana viene raggruppata nello stesso elemento della dimensione.<p>**Questo può aiutarti** a comprendere meglio quali settimane dell’anno il tuo sito viene visitato più e meno frequentemente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio predisporre in maniera più appropriata il personale del call center nelle settimane con traffico elevato, ad esempio durante le vacanze.</p><p>Questo modello utilizza la dimensione Settimana dell’anno.</p> |
| **Mese dell’anno** | Visualizza eventi, sessioni e persone sul sito, suddivisi per mese dell’anno. Ad esempio, se disponi di un rapporto che copre più anni, ogni mese viene raggruppato nello stesso elemento della dimensione.<p>**Questo può aiutarti** a comprendere meglio in quali mesi il tuo sito viene visitato più e meno frequentemente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio predisporre in maniera più appropriata il personale del call center nei mesi con traffico elevato, ad esempio durante le vacanze.</p><p>Questo modello utilizza la dimensione Mese dell’anno.</p> |
| **Trimestre dell’anno** | Visualizza eventi, sessioni e persone sul sito, suddivisi per trimestre dell’anno. Ad esempio, se disponi di un rapporto che copre più anni, ogni trimestre viene raggruppato nello stesso elemento della dimensione.<p>**Questo può aiutarti** a comprendere meglio quali sono i trimestri in cui il tuo sito viene visitato più e meno frequentemente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio programmare il lancio dei prodotti in modo da potenziare i trimestri storicamente a basso traffico.</p><p>Questo modello utilizza la dimensione Trimestre dell’anno.</p> |

### Cross-channel {#cross-channel}

<!--CJA only-->

>[!CONTEXTUALHELP]
>id="cja-template--multiChannelOverview"
>title="Visualizza la distribuzione del traffico su più canali."
>abstract="**Questo può aiutarti** a comprendere meglio quali canali favoriscono maggior traffico e coinvolgimento con successo. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sui canali che ottengono il massimo ritorno sugli investimenti.<br/>Questo modello utilizza le metriche utente, sessione ed evento."

>[!CONTEXTUALHELP]
>id="cja-template--callCenterDeflection"
>title="Visualizza come il traffico web influisce sul traffico del call center."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto self-service del tuo sito web stia deviando il traffico verso il call center.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare i contenuti self-service in modo da ridurre il traffico verso il call center, oppure misurare il ROI dei contenuti self-service calcolando l’importo risparmiato grazie a un minor numero di chiamate di supporto.<br/>Questo modello utilizza le metriche Sessioni web, Sessioni app mobile e Sessioni web+app cross-channel."

>[!CONTEXTUALHELP]
>id="cja-template--webAppTemplate"
>title="Visualizza il traffico web e il traffico sui dispositivi mobili insieme."
>abstract="**Questo può aiutarti** a comprendere meglio la distribuzione del traffico web e sui dispositivi mobili sul tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio dedicare più risorse all’esperienza della tua app mobile quando raggiunge un certo livello di traffico.<br/>Questo modello utilizza le metriche Sessioni web, Sessioni app mobile e Sessioni web+app cross-channel."

>[!CONTEXTUALHELP]
>id="cja-template--onlineOffline"
>title="Visualizza il traffico online e il traffico non in linea insieme."
>abstract="**Questo può aiutarti** a comprendere meglio la distribuzione del traffico online e non in linea sul tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio dedicare più risorse alla tua esperienza online quando raggiunge un certo livello di traffico."


 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Panoramica multicanale**] | Visualizza la distribuzione del traffico su più canali. <p>**Questo può aiutarti** a capire meglio quali canali sono più efficaci nel portare traffico e coinvolgimento. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sui canali che ottengono il massimo ritorno sugli investimenti.</p><p>Questo modello utilizza le metriche utente, sessione ed evento.</p> |
| **Web+App** | Visualizza il traffico web e il traffico sui dispositivi mobili insieme.<p>**Questo può aiutarti** a comprendere meglio la distribuzione del traffico web e sui dispositivi mobili sul tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio dedicare più risorse all’esperienza della tua app mobile quando raggiunge un certo livello di traffico.</p><p>Questo modello utilizza le metriche Sessioni web, Sessioni app per dispositivi mobili e Sessioni web+app cross-channel.</p> |
| **Online/Offline** | Visualizza il traffico online e il traffico non in linea insieme.<p>**Questo può aiutarti** a comprendere meglio la distribuzione del traffico online e non in linea sul tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio dedicare più risorse alla tua esperienza online quando raggiunge un certo livello di traffico.</p><!-- This template uses the ... --> |
| **Deviazione del call center** | Visualizza come il traffico web influisce sul traffico del call center.<p>**Questo può aiutarti** a comprendere meglio come il contenuto self-service del tuo sito web stia deviando il traffico verso il call center.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare i contenuti self-service in modo da ridurre il traffico verso il call center, oppure misurare il ROI dei contenuti self-service calcolando l’importo risparmiato grazie a un minor numero di chiamate di supporto.</p><p>Questo modello utilizza le metriche Sessioni web, Sessioni app per dispositivi mobili e Sessioni web+app cross-channel.</p> |

### Altri canali {#other-channels}

>[!CONTEXTUALHELP]
>id="cja-template--callcenterdashboard"
>title="Visualizza i dati del call center, includendo il motivo per cui la clientela ha chiamato e il numero di volte."
>abstract="**Questo può aiutarti** a comprendere meglio dove si verificano problemi con la clientela e dove vengono spese le risorse relative al call center.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio risolvere problemi relativi a un prodotto che determinano un aumento del traffico del call center, migliorando in ultima analisi la redditività del prodotto."

>[!CONTEXTUALHELP]
>id="cja-template--pointOfSale"
>title="Visualizza i dati sulle transazioni POS (Point of Sale), inclusi i ricavi ottenuti, gli ordini effettuati e le unità vendute. Questo modello include anche visualizzazioni che mostrano informazioni sui principali negozi, prodotti e categorie di prodotti, nonché sulle vendite online e non in linea."
>abstract="**Questo può aiutarti** a comprendere meglio quali sono i tuoi prodotti più venduti nei vari punti vendita e online.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse di marketing ai prodotti e i canali con le prestazioni più elevate."

>[!CONTEXTUALHELP]
>id="cja-template--ajo-email"
>title="Visualizza in che modo le e-mail progettate e inviate tramite Adobe Journey Optimizer generano nuove iscrizioni, membri fedeltà e opportunità di cross-selling."
>abstract="**Questo può aiutarti** a comprendere meglio l’efficacia delle e-mail progettate e inviate tramite Adobe Journey Optimizer.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare la tua strategia e-mail per una determinata campagna e-mail."

>[!CONTEXTUALHELP]
>id="cja-template--survey"
>title="Visualizza il coinvolgimento dell’utente nei sondaggi. Visualizza il numero di avvii e completamenti, domande e risposte principali e numero di partecipanti nuovi rispetto a quelli ripetuti."
>abstract="**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento e il tasso di successo dei tuoi sondaggi.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare i sondaggi futuri per ottenere una migliore partecipazione."

>[!CONTEXTUALHELP]
>id="cja-template--product-usage"
>title="Visualizza come la tua organizzazione utilizza Customer Journey Analytics."
>abstract="**Questo può aiutarti** a comprendere meglio quante persone utilizzano Customer Journey Analytics, con quale frequenza e le tendenze di utilizzo nel tempo. Puoi anche visualizzare il numero di progetti creati e i dettagli su tali progetti. Scopri quali componenti, visualizzazioni e pannelli sono più comunemente utilizzati, tra le altre statistiche di utilizzo.<br/>**In base a ciò che hai appreso, potresti** fare diverse cose, ad esempio eliminare i progetti o i componenti inutilizzati o fornire agli utenti corsi di formazione sulle funzioni più comuni."


 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Dashboard del call center**] | Visualizza i dati del call center, includendo il motivo per cui la clientela ha chiamato e il numero di volte. <p>**Questo può aiutarti** a comprendere meglio dove si verificano problemi con la clientela e dove vengono spese le risorse relative al call center.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio risolvere problemi relativi a un prodotto che determinano un aumento del traffico del call center, migliorando in ultima analisi la redditività del prodotto.</p> |
| **Punto vendita** | Visualizza i dati sulle transazioni POS (Point of Sale), inclusi i ricavi ottenuti, gli ordini effettuati e le unità vendute. Questo modello include anche visualizzazioni che mostrano informazioni sui principali negozi, prodotti e categorie di prodotti, nonché sulle vendite online e non in linea. <p>**Questo può aiutarti** a capire meglio quali sono i tuoi prodotti più venduti nei vari punti vendita e online.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse di marketing ai prodotti e i canali con le migliori prestazioni.</p><p>Questo modello utilizza le metriche Utenti, Entrate e Ordini.</p> |
| **Analisi e-mail di Journey Optimizer** | Visualizza in che modo le e-mail progettate e inviate tramite Adobe Journey Optimizer generano nuove iscrizioni, membri fedeltà e opportunità di cross-selling. <p>**Questo può aiutarti** a comprendere meglio l’efficacia delle e-mail progettate e inviate tramite Adobe Journey Optimizer.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare la tua strategia e-mail per una determinata campagna e-mail.</p> |
| **Sondaggio** | Visualizza il coinvolgimento dell’utente nei sondaggi. Visualizza il numero di avvii e completamenti, domande e risposte principali e numero di partecipanti nuovi rispetto a quelli ripetuti.<p>**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento e il tasso di successo dei tuoi sondaggi.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare i sondaggi futuri per ottenere una migliore partecipazione.</p><p>Questo modello utilizza le metriche Utenti, Eventi, Avvii sondaggio, Completamento sondaggio e Percentuale di completamento sondaggio.</p> |
| **Panoramica di utilizzo del prodotto** | Visualizza come la tua organizzazione utilizza Customer Journey Analytics.<p>**Questo può aiutarti** a comprendere meglio quante persone utilizzano Customer Journey Analytics, con quale frequenza e le tendenze di utilizzo nel tempo. Puoi anche visualizzare il numero di progetti creati e i dettagli su tali progetti. Scopri quali componenti, visualizzazioni e pannelli sono più comunemente utilizzati, tra le altre statistiche di utilizzo. [Ulteriori informazioni](/help/tools/product-usage/usage-overview.md)</p><p>**In base a ciò che hai appreso, potresti** fare diverse cose, ad esempio eliminare i progetti o i componenti inutilizzati o fornire agli utenti corsi di formazione sulle funzioni più comuni.</p> |

### Journey Optimizer {#AJO-templates}

<!--CJA only-->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-campaign"
>title="Visualizza le metriche essenziali per le campagne Journey Optimizer, tra cui campagne e-mail, sperimentazione, in-app, SMS e altro ancora."
>abstract="**Questo può aiutarti** a comprendere dettagli quali il numero di clic e il numero di messaggi inviati, offrendo una visione completa sull’efficacia della tua campagna e sul livello di coinvolgimento.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare le campagne in base ai livelli di coinvolgimento del pubblico target."

>[!CONTEXTUALHELP]
>id="cja-template--ajo-journey"
>title="Visualizza le metriche essenziali per i percorsi Journey Optimizer, tra cui percorsi e-mail, sperimentazione, in-app, SMS e altro ancora."
>abstract="**Questo può aiutarti** a comprendere dettagli quali il numero di clic e il numero di messaggi inviati, offrendo una visione completa sull’efficacia del tuo percorso e sul livello di coinvolgimento.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare le campagne in base ai livelli di coinvolgimento del pubblico target."

>[!CONTEXTUALHELP]
>id="cja-template--ajo-landing-page"
>title="Visualizza il comportamento degli utenti, i pattern di coinvolgimento, i tassi di conversione e altre metriche chiave."
>abstract="**Questo può aiutarti** a comprendere meglio l’efficacia della tua pagina di destinazione. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio ottimizzare le prestazioni della tua pagina di destinazione."

>[!CONTEXTUALHELP]
>id="cja-template--ajo-channel"
>title="Visualizza un riepilogo completo delle metriche di traffico e coinvolgimento per tutte le campagne e i percorsi all’interno del tuo ambiente."
>abstract="**Questo può aiutarti** a comprendere meglio l’efficacia ad alto livello delle tue campagne e dei tuoi percorsi. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare le campagne e i percorsi in base ai livelli di coinvolgimento del pubblico target."

>[!CONTEXTUALHELP]
>id="cja-template--ajo-subscription"
>title="Visualizza abbonamenti e annullamenti di abbonamenti dei profili associati a determinati elenchi."
>abstract="**Questo può aiutarti** a comprendere meglio l’efficacia delle diverse campagne di abbonamento e delle iniziative nel promuovere il coinvolgimento e le conversioni.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare le campagne di abbonamento in base ai livelli di coinvolgimento del pubblico target."

 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Campagne di Journey Optimizer**] | Visualizza le metriche essenziali per le campagne Journey Optimizer, tra cui campagne e-mail, sperimentazione, in-app, SMS e altro ancora.<p>**Questo può aiutarti** a comprendere dettagli quali il numero di clic e il numero di messaggi inviati, offrendo una visione completa sull’efficacia della tua campagna e sul livello di coinvolgimento.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare le campagne in base ai livelli di coinvolgimento del pubblico target.</p> |
| **Percorsi di Journey Optimizer** | Visualizza le metriche essenziali per i percorsi Journey Optimizer, tra cui percorsi e-mail, sperimentazione, in-app, SMS e altro ancora.<p>**Questo può aiutarti** a comprendere dettagli quali il numero di clic e il numero di messaggi inviati, offrendo una visione completa sull’efficacia del tuo percorso e sul livello di coinvolgimento.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare le campagne in base ai livelli di coinvolgimento del pubblico target.</p> |
| **Pagine di destinazione di Journey Optimizer** | Visualizza il comportamento degli utenti, i pattern di coinvolgimento, i tassi di conversione e altre metriche chiave.<p>**Questo può aiutarti** a capire meglio l’efficacia della pagina di destinazione. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio ottimizzare le prestazioni della tua pagina di destinazione.</p> |
| **Rapporto di panoramica su Journey Optimizer** | Visualizza un riepilogo completo delle metriche di traffico e coinvolgimento per tutte le campagne e i percorsi all’interno del tuo ambiente.<p>**Questo può aiutarti** a capire meglio l’efficacia di alto livello delle tue campagne e dei tuoi percorsi. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare le campagne e i percorsi in base ai livelli di coinvolgimento del pubblico target.</p> |
| **Abbonamenti a Journey Optimizer** | Visualizza abbonamenti e annullamenti di abbonamenti dei profili associati a determinati elenchi.<p>**Questo può aiutarti** a comprendere meglio l’efficacia delle diverse campagne di abbonamento e delle iniziative nel promuovere il coinvolgimento e le conversioni.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare le campagne di abbonamento in base ai livelli di coinvolgimento del pubblico target.</p> |




### Modelli B2B {#b2b-templates}

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}


<!-- CJA B2B Edition only -->

>[!CONTEXTUALHELP]
>id="cja-template--b2b-account-engagement"
>title="Scopri quanto sono attivi i tuoi account tra eventi, persone e opportunità."
>abstract="**Questo può aiutarti** a capire meglio se il coinvolgimento a livello di account sta aumentando o diminuendo, a confrontare le attività tra gli account e a decidere dove concentrare le attività di conservazione o acquisizione.<br/>**In base a quanto appreso, potresti** fare diverse cose, come concentrare nuovamente l’attenzione sugli account meno coinvolti ma che richiedono più attenzione a causa dell’importanza dell’account."

>[!CONTEXTUALHELP]
>id="cja-template--b2b-opportunity-engagement"
>title="Tieni traccia del coinvolgimento a livello di opportunità e degli accordi di superficie che acquisiscono o perdono interesse."
>abstract="**Questo può aiutarti** a prevedere la progressione dell’accordo in modo più preciso e a concentrare l’abilitazione dove il coinvolgimento aumenta o si arresta.<br/>**In base a quanto appreso, potresti** fare diverse cose, ad esempio dedicare ulteriori sforzi agli accordi quasi conclusi e cercare il motivo per cui invece altri stanno perdendo interesse."

>[!CONTEXTUALHELP]
>id="cja-template--b2b-buying-group-activity"
>title="Visualizza l’attività del gruppo acquisti all’interno di ogni account per informare sulle azioni di marketing relative a gruppi acquisti ed account."
>abstract="**Questo può aiutarti** a visualizzare i gruppi acquisti e le persone più coinvolte all’interno di tali gruppi, evidenziando le lacune nella partecipazione al gruppo.<br/>**In base a quanto appreso, potresti** fare diverse cose, ad esempio cercare di coinvolgere maggiormente le persone di gruppi acquisti che non sembrano essere coinvolte."

 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Panoramica sul coinvolgimento dell’account B2B**] | Scopri quanto sono attivi i tuoi account tra eventi, persone e opportunità.<p>**Questo può aiutarti** a capire meglio se il coinvolgimento a livello di account sta aumentando o diminuendo, a confrontare le attività tra gli account e a decidere dove concentrare le attività di conservazione o acquisizione.</p><p>**In base a quanto appreso, potresti** fare diverse cose, come concentrare nuovamente l’attenzione sugli account meno coinvolti ma che richiedono più attenzione a causa dell’importanza dell’account.</p> |
| [!UICONTROL **Panoramica sul coinvolgimento dell’opportunità B2B**] | Tieni traccia del coinvolgimento a livello di opportunità e degli accordi di superficie che acquisiscono o perdono interesse.<p>**Questo può aiutarti** a prevedere la progressione dell’accordo in modo più preciso e a concentrare l’abilitazione dove il coinvolgimento aumenta o si arresta.</p><p>**In base a quanto appreso, potresti** fare diverse cose, ad esempio dedicare ulteriori sforzi agli accordi quasi conclusi e cercare il motivo per cui invece altri stanno perdendo interesse.</p> |
| [!UICONTROL **Attività del gruppo acquisti B2B**] | Visualizza l’attività del gruppo acquisti all’interno di ogni account per informare sulle azioni di marketing relative a gruppi acquisti ed account.<p>**Questo può aiutarti** a visualizzare i gruppi acquisti e le persone più coinvolte all’interno di tali gruppi, evidenziando le lacune nella partecipazione al gruppo.</p><p>**In base a ciò che hai appreso, potresti** fare diverse cose, ad esempio cercare di coinvolgere maggiormente le persone di gruppi acquisti che non sembrano essere coinvolte.</p> |
