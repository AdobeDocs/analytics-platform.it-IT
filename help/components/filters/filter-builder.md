---
description: Il Generatore di filtri fornisce un’area di lavoro per trascinare e rilasciare Dimension metriche, filtri ed eventi per filtrare i visitatori in base alla logica gerarchica del contenitore, alle regole e agli operatori. Questo strumento di sviluppo integrato ti consente di generare e salvare filtri semplici o complessi che identificano gli attributi e le azioni dei visitatori in visite e hit pagina.
title: Crea filtri
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 74ec307b878b77a40ef1f5dbf54f2b59d88b41fe
workflow-type: tm+mt
source-wordcount: '1950'
ht-degree: 5%

---

# Generatore di filtri

La [!UICONTROL Filter builder] consente di creare filtri semplici o complessi che identificano gli attributi e le azioni dei visitatori in visite e hit di pagina. Fornisce un’area di lavoro per trascinare e rilasciare dimensioni metriche, eventi o altri filtri al fine di filtrare i visitatori in base alla logica gerarchica, alle regole e agli operatori.

Per informazioni su come creare filtri rapidi applicabili solo al progetto in cui sono stati creati, consulta [Filtri rapidi](/help/components/filters/quick-filters.md).

## Accedere al Generatore di filtri

Puoi accedere al Generatore di filtri in uno dei seguenti modi:

* **Navigazione superiore in Analytics**: Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]**.
* **[!UICONTROL Analysis Workspace]**: Con un progetto aperto in Analysis Workspace, seleziona **[!UICONTROL + Components]** > **[!UICONTROL Create filter]**.
* **[!UICONTROL Reports & Analytics]**: Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**, apri un rapporto esistente e fai clic su **Filtro** nella navigazione a sinistra, quindi fai clic su **[!UICONTROL Add]**.
* **[!UICONTROL Report Builder]**: [Aggiungere o modificare filtri nel Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html).

## Panoramica sui criteri di generazione {#section_F61C4268A5974C788629399ADE1E6E7C}

Puoi aggiungere definizioni di regole e contenitori per definire i filtri. (Per informazioni sull&#39;accesso al Generatore di filtri, vedi [Accedere al Generatore di filtri](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL Title]**: Denomina il filtro.
1. **[!UICONTROL Description]**: Fornisci una descrizione del filtro.
1. **[!UICONTROL Tags]**: [Assegnare tag al filtro](/help/components/filters/manage-filters.md) per creare i tag, scegli da un elenco di tag esistenti o crei un nuovo tag.
1. **[!UICONTROL Definitions]**: Qui è dove [creare e configurare i filtri](/help/components/filters/filters-overview.md), aggiungere regole e nidificare e sequenziare contenitori.
1. **[!UICONTROL Show]**: (Selettore contenitore superiore). Consente di selezionare il livello principale [container](/help/components/filters/filters-overview.md) ( [!UICONTROL Person], [!UICONTROL Session], [!UICONTROL Event]). Il contenitore principale predefinito è il contenitore Evento .
1. **[!UICONTROL Options]**: Icona (ingranaggio)

   * **[!UICONTROL + Add container]**: Consente di aggiungere un nuovo contenitore (sotto il contenitore principale) alla definizione del filtro.
   * **[!UICONTROL Exclude]**: Consente di definire il filtro escludendo una o più dimensioni, filtri o metriche.

1. **[!UICONTROL Dimensions]**: I componenti vengono trascinati e rilasciati dall’elenco Dimension (barra laterale arancione).
1. **[!UICONTROL Operator]**: Puoi confrontare e vincolare i valori utilizzando gli operatori selezionati.
1. **[!UICONTROL Value]**: Il valore immesso o selezionato per la dimensione, il filtro o la metrica.
1. **[!UICONTROL Attribution Models]**: Disponibile solo per le dimensioni, questi modelli determinano per quali valori in una dimensione filtrare. I modelli di Dimension sono particolarmente utili nei filtri sequenziali.

   * **[!UICONTROL Repeating]** (predefinito): Include istanze e valori persistenti per la dimensione.
   * **[!UICONTROL Instance]**: Include le istanze per la dimensione.
   * **[!UICONTROL Non-repeating instance]**: Include istanze univoche (non ripetute) per la dimensione. Questo è il modello applicato in Flusso quando le istanze ripetute sono escluse.

   ![](assets/attribution-models.jpg)

   **Esempio: Filtro evento in cui eVar1 = A**

   | Esempio | A | A | A (persistente) | B | A | C |
   |---|---|---|---|---|---|---|
   | Ripetuto | X | X | X | - | X | - |
   | Istanza | X | X | - | - | X | - |
   | Istanza non ripetuta | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**: Assegna la [!UICONTROL AND/OR/THEN] operatori tra contenitori o regole. L’operatore THEN consente di: [definire filtri sequenziali](/help/components/filters/filters-overview.md).
1. **[!UICONTROL Metric]**: (Barra laterale verde) Metrica trascinata dall’elenco Metriche.
1. **[!UICONTROL Comparison]** operatore: Puoi confrontare e vincolare i valori utilizzando gli operatori selezionati.
1. **[!UICONTROL Value]**: Il valore immesso o selezionato per la dimensione, il filtro o la metrica.
1. **[!UICONTROL X]**: (Elimina) Consente di eliminare questa parte della definizione del filtro.
1. **[!UICONTROL Experience Cloud publishing]**: La pubblicazione di un filtro Adobe Analytics nell’Experience Cloud consente di utilizzare il filtro per l’attività di marketing in [!DNL Audience Manager] e in altri canali di attivazione. [Ulteriori informazioni...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=it)
1. **[!UICONTROL Audience library]**: I servizi di pubblico di Adobe gestiscono la traduzione dei dati dei visitatori in filtri del pubblico. La creazione e la gestione dei tipi di pubblico sono simili alla creazione e all’uso dei filtri, e in più permettono di condividere il filtro per l’audience nell’Experience Cloud. [Ulteriori informazioni...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=it)
1. **[!UICONTROL Search]**: Cerca nell’elenco di dimensioni, filtri o metriche.
1. **[!UICONTROL Dimensions]**: (Elenco) Fai clic sull’intestazione da espandere.
1. **[!UICONTROL Metrics]**: Fai clic sull’intestazione da espandere.
1. **[!UICONTROL Filters]**: Fai clic sull’intestazione da espandere.
1. **[!UICONTROL Data View selector]**: Consente di selezionare la suite di rapporti in cui verrà salvato il filtro. Puoi comunque utilizzare il filtro in tutte le visualizzazioni dati.
1. **[!UICONTROL Filter Preview]**: Consente di visualizzare in anteprima le metriche chiave per verificare se disponi di un filtro valido e la sua ampiezza. Rappresenta il raggruppamento del set di dati che si prevede di vedere se si applica questo filtro. Mostra 3 cerchi concentrici e un elenco per mostrare il numero e la percentuale di corrispondenze per [!UICONTROL Event], [!UICONTROL Person]e [!UICONTROL Session] per un filtro eseguito su un set di dati. Questo grafico viene aggiornato immediatamente dopo che hai creato o apportato modifiche alla definizione del filtro.
1. **[!UICONTROL Product Compatibility]**: Fornisce un elenco dei prodotti Adobe Analytics (Analysis Workspace, [!UICONTROL Reports & Analytics], Data Warehouse) con cui è compatibile il filtro creato. La maggior parte dei filtri è compatibile con tutti i prodotti. Tuttavia, non tutti gli operatori e le dimensioni sono compatibili con tutti i prodotti Analytics, in particolare [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html). Questo grafico viene aggiornato immediatamente dopo aver apportato modifiche alla definizione del filtro.
1. **[!UICONTROL Save]** o **[!UICONTROL Cancel]**: Salva o annulla il filtro. Dopo aver fatto clic su **[!UICONTROL Save]**, vai al Gestore filtri dove puoi gestire il filtro.

I filtri con intervalli di date incorporati continuano a funzionare diversamente in Analysis Workspace rispetto a [!UICONTROL Reports & Analytics]: In Workspace, un filtro con un intervallo di date integrato sostituisce l’intervallo di date del pannello. Per contro, [!UICONTROL Reports & Analytics] fornisce l’intersezione dell’intervallo di date del rapporto e dell’intervallo di date integrato del filtro.

## Creare un filtro {#build-filters}

1. Trascina semplicemente un evento Dimension, filtro o metrica dal riquadro a sinistra al [!UICONTROL Definitions] campo .

   ![](assets/drag_n_drop_dimension.png)

1. Imposta la [operatore](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=it) dal menu a discesa.
1. Immettere o selezionare un valore per l&#39;elemento selezionato.
1. Aggiungi altri contenitori, se necessario, utilizzando **[!UICONTROL And]**, **[!UICONTROL Or]** oppure **[!UICONTROL Then]** regole.
1. Dopo aver posizionato i contenitori e impostato le regole, vedere i risultati del filtro nel grafico di convalida in alto a destra. La convalida indica la percentuale e il numero assoluto di visualizzazioni di pagina, visite e visitatori unici che corrispondono al filtro creato.
1. Sotto **[!UICONTROL Tags]**, [tag](/help/components/filters/manage-filters.md) selezionando un tag esistente o creandone uno nuovo.
1. Fai clic su **[!UICONTROL Save]** per salvare il filtro.

   Sei portato al [Gestore filtri](/help/components/filters/manage-filters.md), in cui puoi assegnare tag, condividere e gestire il filtro in più modi.

## Aggiungi contenitori {#section_1C38F15703B44474B0718CEF06639EFD}

È possibile [creare una struttura di contenitori](/help/components/filters/filters-overview.md) e quindi inserire regole logiche e operatori tra .

1. Fai clic su **[!UICONTROL Options > Add container]** (Usa modello di attribuzione non predefinito).

   Nuovo [!UICONTROL **Evento**] il contenitore si apre senza [!UICONTROL **Evento**] (Visualizzazione pagina) identificata.

   ![](assets/new_container.png)

1. Modifica il tipo di contenitore in base alle esigenze.
1. Trascina un Dimension, un filtro o un evento dal riquadro a sinistra al contenitore .
1. Continua ad aggiungere nuovi contenitori dal livello principale **[!UICONTROL Options]** > **[!UICONTROL Add container]** nella parte superiore della definizione, oppure aggiungi contenitori all’interno di un contenitore per nidificare la logica.

   **O**

   Seleziona una o più regole e fai clic su **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**. In questo modo la selezione viene trasformata in un contenitore separato.

## Usa intervalli di date {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Puoi creare filtri che contengono intervalli di date dinamici per rispondere a domande su campagne o eventi in corso.

Ad esempio, puoi facilmente creare un filtro che include &quot;tutti coloro che hanno effettuato un acquisto negli ultimi 60 giorni&quot;.

Crea un contenitore Sessione e al suo interno aggiungi la [!UICONTROL Last 60 days] intervallo di tempo e la metrica [!UICONTROL Orders is greater than or equal to 1], con un operatore AND.

Ecco un video sull’uso degli intervalli di date continui nei filtri:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Filtri di stack {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

I filtri di stack funzionano combinando i criteri in ciascun filtro utilizzando un operatore &quot;e&quot; e quindi applicando i criteri combinati. Questa operazione può essere eseguita direttamente in un progetto Workspace o nel generatore di filtri.

Ad esempio, impilare un filtro &quot;utenti di telefonia mobile&quot; e un filtro &quot;geografia USA&quot; restituirebbe i dati solo agli utenti di telefonia mobile negli Stati Uniti.

Considera questi filtri come blocchi o moduli costitutivi che puoi includere in una libreria di filtri, affinché gli utenti possano utilizzarli secondo le proprie esigenze. In questo modo, puoi ridurre notevolmente il numero di filtri necessari. Ad esempio, si supponga di disporre di 40 filtri:

* 20 per gli utenti di telefoni cellulari in diversi paesi (US_mobile, Germany_mobile, France_mobile, Brazil_mobile, ecc.)
* 20 per gli utenti di tablet in diversi paesi (US_tablet, Germany_tablet, France_tablet, Brazil_tablet, ecc.)

Utilizzando la sovrapposizione dei filtri, puoi ridurre il conteggio dei filtri a 22 e impilarli in base alle esigenze. È necessario creare i seguenti filtri:

* un filtro per gli utenti di dispositivi mobili
* un filtro per gli utenti di tablet
* 20 filtri per le diverse aree geografiche

>[!NOTE]
>
>Quando si sovrappongono due filtri, per impostazione predefinita sono collegati da un’istruzione AND. Non è possibile modificare questo valore in un&#39;istruzione OR.

1. Passa al Generatore di filtri.

1. Specifica un titolo e una descrizione per il filtro.

1. Fai clic su **[!UICONTROL Show filters]** per visualizzare l’elenco dei filtri nel menu di navigazione a sinistra.

1. Trascina i filtri che vuoi impilare nell’area di lavoro della definizione del filtro.

1. Seleziona [!UICONTROL **Salva**].

## Filtrare i modelli {#concept_5098446CC78D441E93B8E4D1D1EA6558}

I modelli di filtro sono forniti per i casi d’uso più comuni, ad esempio &quot;Prime visite&quot; o &quot;Viste da dispositivi mobili&quot;. Sono disponibili nei progetti Workspace e nel Generatore di filtri come blocchi predefiniti per i nuovi filtri.

I modelli sono contraddistinti dal logo &quot;A&quot; dell’Adobe. Di seguito è riportato un esempio di modelli:

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome modello </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Carrello abbandonato </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno aggiunto elementi ai loro carrelli ma non hanno ordinato nulla. Nella definizione del filtro, il contenitore è Visita. La regola per questo filtro sequenziale è <p> Aggiunte carrello non è nullo </p> <p>Then </p> <p>Ordini è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prime visite </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno visitato un massimo di 1 [1] volte. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Numero visita è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Non acquirenti </td> 
   <td colname="col2">Visualizza i dati per i visitatori che non hanno partecipato a un evento dell’ordine. Nella definizione del filtro, il contenitore è Visitatore. Questo filtro utilizza la logica di esclusione. La regola è <p>Ordini non nulli. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visita non a pagina singola (senza rimbalzi) </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno visitato più di una volta. Nella definizione del filtro, il contenitore è Visitatore. Questo filtro utilizza la logica di esclusione. La regola è <p>Accesso singolo non nullo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricerca a pagamento </td> 
   <td colname="col2">Visualizza i dati dei visitatori provenienti da una ricerca a pagamento. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Ricerca a pagamento è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Acquirenti </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno partecipato a un evento dell’ordine. Nella definizione del filtro, il contenitore è Visitatore. La regola è <p>Ordini non nulli. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite di ritorno </td> 
   <td colname="col2">Visualizza i dati dei visitatori che hanno visitato almeno una volta. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Numero visita maggiore di 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite a pagina singola </td> 
   <td colname="col2"> Visualizza i dati delle visite in cui viene visualizzato un singolo valore di pagina, anche se durante tale visita è possibile inviare più visualizzazioni di pagina. Nel filtro sono incluse le visite a pagina singola con eventi di collegamento di uscita. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Visite a pagina singola è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prodotto visualizzato non aggiunto al carrello </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno visualizzato prodotti ma non hanno aggiunto carrello. Nella definizione del filtro, il contenitore è Visita. La regola per questo filtro sequenziale è <p>Visualizzazioni prodotto non nulle </p> <p>Then </p> <p> Aggiunte carrello è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da Campaign </td> 
   <td colname="col2">Visualizza i dati dei visitatori a cui fanno riferimento le campagne. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Il codice di tracciamento non è null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da dispositivi mobili </td> 
   <td colname="col2">Visualizzare i dati dei visitatori che utilizzano dispositivi mobili. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Dispositivo mobile non nullo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da ricerca naturale </td> 
   <td colname="col2">Visualizza i dati dei visitatori non provenienti da una ricerca a pagamento. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Ricerca a pagamento è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da dispositivi non mobili </td> 
   <td colname="col2">Visualizza i dati dei visitatori che non utilizzano dispositivi mobili. Nella definizione del filtro, il contenitore è Visita. Questo filtro utilizza la logica di esclusione. La regola è <p>Tipo di dispositivo mobile uguale a Telefono cellulare </p> <p>Oppure </p> <p>Tipo di dispositivo mobile è uguale a Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da telefoni </td> 
   <td colname="col2">Visualizza i dati dei visitatori che utilizzano i telefoni. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Tipo di dispositivo è uguale a Telefono cellulare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite dai motori di ricerca </td> 
   <td colname="col2">Visualizza i dati dei visitatori a cui fanno riferimento i motori di ricerca. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Tipo referente è uguale a Motori di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite dai siti social </td> 
   <td colname="col2">Visualizza i dati dei visitatori a cui fanno riferimento i siti social. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Tipo referente è uguale a Social Networks. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da Tablet </td> 
   <td colname="col2">Visualizza i dati dei visitatori utilizzando i tablet. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Tipo di dispositivo è uguale a Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite con il cookie ID visitatore </td> 
   <td colname="col2">Visualizza i dati dei visitatori del tuo sito, dove è richiesto un cookie permanente. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Cookie persistente uguale a 1. </p> </td> 
  </tr> 
 </tbody> 
</table>