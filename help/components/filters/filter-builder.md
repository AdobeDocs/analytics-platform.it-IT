---
description: Il Generatore di filtri fornisce un’area di lavoro per trascinare e rilasciare Dimension di metriche, filtri ed eventi per filtrare i visitatori in base alla logica gerarchica del contenitore, alle regole e agli operatori. Questo strumento di sviluppo integrato ti consente di creare e salvare filtri semplici o complessi che identificano gli attributi e le azioni dei visitatori in visite ed eventi.
title: Crea filtri
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '1948'
ht-degree: 4%

---

# Generatore di filtri

Il [!UICONTROL Filter builder] consente di creare filtri semplici o complessi che identificano gli attributi e le azioni dei visitatori in visite ed eventi. Fornisce un’area di lavoro per trascinare e rilasciare dimensioni metriche, eventi o altri filtri per filtrare i visitatori in base a logica gerarchica, regole e operatori.

Per informazioni su come creare filtri rapidi applicabili solo al progetto in cui sono stati creati, consulta [Filtri rapidi](/help/components/filters/quick-filters.md).

## Accedere al Generatore di filtri

Puoi accedere al Generatore di filtri in uno dei seguenti modi:

* **Navigazione superiore di Analytics**: fai clic **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]**.
* **[!UICONTROL Analysis Workspace]**: con un progetto aperto in Analysis Workspace, seleziona **[!UICONTROL + Components]** > **[!UICONTROL Create filter]**.
* **[!UICONTROL Reports & Analytics]**: fai clic **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**, apri un rapporto esistente e fai clic su **Filtro** nella navigazione a sinistra, quindi fai clic su **[!UICONTROL Add]**.
* **[!UICONTROL Report Builder]**: [Aggiungere o modificare filtri nel Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html).

## Panoramica sui criteri di Builder {#section_F61C4268A5974C788629399ADE1E6E7C}

Puoi aggiungere definizioni di regole e contenitori per definire i filtri. Per informazioni sull’accesso al Generatore di filtri, consulta [Accedere al Generatore di filtri](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL Title]**: assegna un nome al filtro.
1. **[!UICONTROL Description]**: fornisci una descrizione del filtro.
1. **[!UICONTROL Tags]**: [Assegnare tag al filtro](/help/components/filters/manage-filters.md) per creare, fai clic su un elenco di tag esistenti o creane uno nuovo.
1. **[!UICONTROL Definitions]**: qui è dove [generare e configurare i filtri](/help/components/filters/filters-overview.md), aggiungi regole e nidifica contenitori e sequenze.
1. **[!UICONTROL Show]**: (selettore contenitore superiore). Consente di selezionare il livello superiore [contenitore](/help/components/filters/filters-overview.md) ( [!UICONTROL Person], [!UICONTROL Session], [!UICONTROL Event]). Il contenitore principale predefinito è il contenitore Evento.
1. **[!UICONTROL Options]** icona : (ingranaggio)

   * **[!UICONTROL + Add container]**: consente di aggiungere un nuovo contenitore (sotto il contenitore principale) alla definizione del filtro.
   * **[!UICONTROL Exclude]**: consente di definire il filtro escludendo una o più dimensioni, filtri o metriche.

1. **[!UICONTROL Dimensions]**: i componenti vengono trascinati e rilasciati dall’elenco Dimension (barra laterale arancione).
1. **[!UICONTROL Operator]**: puoi confrontare e vincolare i valori utilizzando gli operatori selezionati.
1. **[!UICONTROL Value]**: il valore immesso o selezionato per la dimensione, il filtro o la metrica.
1. **[!UICONTROL Attribution Models]**: disponibile solo per le dimensioni, questi modelli determinano i valori in una dimensione per cui filtrare. I modelli di Dimension sono particolarmente utili nei filtri sequenziali.

   * **[!UICONTROL Repeating]** (impostazione predefinita): include le istanze e i valori persistenti per la dimensione.
   * **[!UICONTROL Instance]**: include le istanze della dimensione.
   * **[!UICONTROL Non-repeating instance]**: include istanze univoche (non ripetute) della dimensione. Si tratta del modello applicato in Flusso quando le varianti di ripetizione sono escluse.

   ![](assets/attribution-models.jpg)

   **Esempio: filtro eventi in cui eVar 1 = A**

   | Esempio | A | A | A (persistente) | B | A | C |
   |---|---|---|---|---|---|---|
   | Ripetizione | X | X | X | - | X | - |
   | Istanza | X | X | - | - | X | - |
   | Istanza non ripetuta | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**: assegna il [!UICONTROL AND/OR/THEN] tra contenitori o regole. L’operatore THEN consente di: [definire filtri sequenziali](/help/components/filters/filters-overview.md).
1. **[!UICONTROL Metric]**: (barra laterale verde) metrica trascinata e rilasciata dall’elenco Metriche.
1. **[!UICONTROL Comparison]** operatore: è possibile confrontare e vincolare i valori utilizzando gli operatori selezionati.
1. **[!UICONTROL Value]**: il valore immesso o selezionato per la dimensione, il filtro o la metrica.
1. **[!UICONTROL X]**: (Elimina) consente di eliminare questa parte della definizione del filtro.
1. **[!UICONTROL Experience Cloud publishing]**: pubblicando un filtro di Adobe Analytics nell’Experience Cloud puoi utilizzare il filtro per l’attività di marketing in [!DNL Audience Manager] e in altri canali di attivazione. [Ulteriori informazioni...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=it)
1. **[!UICONTROL Audience library]**: i servizi di pubblico di Adobe gestiscono la traduzione dei dati dei visitatori in filtri di pubblico. La creazione e la gestione dei tipi di pubblico sono simili alla creazione e all’utilizzo dei filtri, e in più permettono di condividere il filtro del pubblico nell’Experience Cloud. [Ulteriori informazioni...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=it)
1. **[!UICONTROL Search]**: esegue la ricerca nell’elenco di dimensioni, filtri o metriche.
1. **[!UICONTROL Dimensions]**: (Elenco) Fai clic sull’intestazione per espanderla.
1. **[!UICONTROL Metrics]**: fai clic sull’intestazione per espandere.
1. **[!UICONTROL Filters]**: fai clic sull’intestazione per espandere.
1. **[!UICONTROL Data View selector]**: consente di selezionare la suite di rapporti in cui verrà salvato il filtro. Puoi comunque utilizzare il filtro in tutte le visualizzazioni dati.
1. **[!UICONTROL Filter Preview]**: consente di visualizzare in anteprima le metriche chiave per verificare se disponi di un filtro valido e quanto è ampio il filtro. Rappresenta il raggruppamento del set di dati previsto per verificare se si applica questo filtro. Mostra 3 cerchi concentrici e un elenco per mostrare il numero e la percentuale di corrispondenze per [!UICONTROL Event], [!UICONTROL Person], e [!UICONTROL Session] per un filtro eseguito su un set di dati. Questo grafico viene aggiornato subito dopo la creazione o la modifica della definizione del filtro.
1. **[!UICONTROL Product Compatibility]**: fornisce un elenco dei prodotti Adobe Analytics (Analysis Workspace, [!UICONTROL Reports & Analytics], Data Warehouse) con cui è compatibile il filtro creato. La maggior parte dei filtri è compatibile con tutti i prodotti. Tuttavia, non tutti gli operatori e le dimensioni sono compatibili con tutti i prodotti Analytics, in particolare [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html). Questo grafico viene aggiornato subito dopo aver apportato modifiche alla definizione del filtro.
1. **[!UICONTROL Save]** o **[!UICONTROL Cancel]**: salva o annulla il filtro. Dopo aver fatto clic su **[!UICONTROL Save]**, ti indirizzano al Gestore filtri per gestire il filtro.

I filtri con intervalli di date incorporati continuano a funzionare diversamente in Analysis Workspace rispetto a [!UICONTROL Reports & Analytics]: in Workspace, un filtro con un intervallo di date incorporato sovrascrive l’intervallo di date del pannello. Per contro, [!UICONTROL Reports & Analytics] ti fornisce l’intersezione dell’intervallo di date del rapporto con l’intervallo di date integrato del filtro.

## Creare un filtro {#build-filters}

1. È sufficiente trascinare un evento di Dimension, filtro o metrica dal riquadro di sinistra al [!UICONTROL Definitions] campo.

   ![](assets/drag_n_drop_dimension.png)

1. Imposta il [operatore](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=it) dal menu a discesa.
1. Immettere o selezionare un valore per l&#39;elemento selezionato.
1. Se necessario, aggiungi altri contenitori utilizzando **[!UICONTROL And]**, **[!UICONTROL Or]**, o **[!UICONTROL Then]** regole.
1. Dopo aver inserito i contenitori e aver impostato le regole, vedi i risultati del filtro nel grafico di convalida in alto a destra. La convalida indica la percentuale e il numero assoluto di visualizzazioni di pagina, visite e visitatori univoci che corrispondono al filtro creato.
1. Sotto **[!UICONTROL Tags]**, [tag](/help/components/filters/manage-filters.md) il contenitore selezionando un tag esistente o creandone uno nuovo.
1. Clic **[!UICONTROL Save]** per salvare il filtro.

   Sei portato al [Gestore filtri](/help/components/filters/manage-filters.md), dove puoi assegnare tag, condividere e gestire il filtro in più modi.

## Aggiungere contenitori {#section_1C38F15703B44474B0718CEF06639EFD}

È possibile [creare un framework di contenitori](/help/components/filters/filters-overview.md) e quindi posiziona regole logiche e operatori tra.

1. Fai clic su **[!UICONTROL Options > Add container]** (Usa modello di attribuzione non predefinito).

   Una nuova [!UICONTROL **Evento**] il contenitore si apre senza un [!UICONTROL **Evento**] (Visualizzazione pagina) identificata.

   ![](assets/new_container.png)

1. Modifica il tipo di contenitore in base alle esigenze.
1. Trascina un Dimension, un filtro o un evento dal riquadro di sinistra al contenitore.
1. Continua ad aggiungere nuovi contenitori dal livello superiore **[!UICONTROL Options]** > **[!UICONTROL Add container]** nella parte superiore della definizione, oppure aggiungi contenitori da un contenitore alla logica di nidificazione.

   **O**

   Seleziona una o più regole, quindi fai clic su **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**. In questo modo la selezione diventa un contenitore separato.

## Utilizzare intervalli di date {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Puoi creare filtri che contengono intervalli di date continui per rispondere a domande su campagne o eventi in corso.

Ad esempio, puoi facilmente creare un filtro che includa &quot;tutti coloro che hanno effettuato un acquisto negli ultimi 60 giorni&quot;.

Crea un contenitore Sessione e al suo interno aggiungi [!UICONTROL Last 60 days] l’intervallo di tempo e la metrica [!UICONTROL Orders is greater than or equal to 1], con un operatore AND.

Ecco un video sull’utilizzo degli intervalli di date continui nei filtri:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Sovrapponi filtri {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

L’impilamento dei filtri funziona combinando i criteri in ciascun filtro utilizzando un operatore &quot;and&quot; e applicando i criteri combinati. Questa operazione può essere eseguita direttamente in un progetto Workspace o nel Generatore di filtri.

Ad esempio, impilando un filtro &quot;utenti di telefonia mobile&quot; e un filtro &quot;geografia USA&quot; si restituiscono dati solo per gli utenti di telefonia mobile negli Stati Uniti.

Considera questi filtri come blocchi predefiniti o moduli che puoi includere in una libreria di filtri, per consentirne l’utilizzo da parte degli utenti. In questo modo, puoi ridurre drasticamente il numero di filtri necessari. Ad esempio, supponiamo di disporre di 40 filtri:

* 20 per gli utenti di telefoni cellulari in diversi paesi (US_mobile, Germany_mobile, France_mobile, Brazil_mobile, ecc.)
* 20 per utenti di tablet in diversi paesi (US_tablet, Germany_tablet, France_tablet, Brazil_tablet, ecc.)

Utilizzando lo stacking dei filtri, puoi ridurre il numero di filtri a 22 e sovrapporli in base alle esigenze. Dovrai creare i seguenti filtri:

* un filtro per gli utenti di dispositivi mobili
* un filtro per gli utenti tablet
* 20 filtri per le diverse aree geografiche

>[!NOTE]
>
>Quando si sovrappongono due filtri, per impostazione predefinita questi sono collegati da un’istruzione AND. Non può essere modificata in un&#39;istruzione OR.

1. Passa al Generatore di filtri.

1. Fornisci un titolo e una descrizione per il filtro.

1. Clic **[!UICONTROL Show filters]** per visualizzare l’elenco dei filtri nella navigazione a sinistra.

1. Trascina i filtri da sovrapporre nell’area di lavoro di definizione del filtro.

1. Seleziona [!UICONTROL **Salva**].

## Filtra modelli {#concept_5098446CC78D441E93B8E4D1D1EA6558}

Sono forniti modelli di filtro per i casi di utilizzo comuni dei filtri, ad esempio &quot;Prime visite&quot; o &quot;Visite da dispositivi mobili&quot;. Sono disponibili nei progetti Workspace e nel generatore di filtri come blocchi predefiniti per i nuovi filtri.

I modelli sono identificati dal logo &quot;A&quot; dell&#39;Adobe. Di seguito è riportato un esempio di modelli:

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome modello </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Abbandona carrello </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno aggiunto elementi ai loro carrelli ma non hanno ordinato nulla. Nella definizione del filtro, il contenitore è Visita. La regola per questo filtro sequenziale è <p> Aggiunte carrello non è nullo </p> <p>Then </p> <p>Ordini è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prime visite </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno visitato un massimo di una [1] volte. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Il numero di visite è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Non acquirenti </td> 
   <td colname="col2">Visualizza i dati per i visitatori che non hanno partecipato a un evento di ordine. Nella Definizione del filtro, il contenitore è Visitatore. Questo filtro utilizza la logica Exclude. La regola è <p>Ordini non nulli. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visita non a pagina singola (non rimbalzate) </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno visitato più di una volta. Nella Definizione del filtro, il contenitore è Visitatore. Questo filtro utilizza la logica Exclude. La regola è <p>L'accesso singolo non è nullo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricerca a pagamento </td> 
   <td colname="col2">Visualizzare i dati dei visitatori provenienti da una ricerca a pagamento. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Ricerca a pagamento è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Acquirenti </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno partecipato a un evento di ordine. Nella Definizione del filtro, il contenitore è Visitatore. La regola è <p>Ordini non nulli. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite di ritorno </td> 
   <td colname="col2">Visualizza i dati dei visitatori che hanno visitato almeno una volta. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Il numero di visite è maggiore di 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite a pagina singola </td> 
   <td colname="col2"> Visualizzare i dati delle visite in cui viene visualizzato il valore di una singola pagina, anche se durante tale visita è possibile inviare più visualizzazioni di pagina. Le visite a pagina singola con eventi di collegamento di uscita sono incluse nel filtro. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Visite a pagina singola è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Il prodotto visualizzato non è stato aggiunto al carrello </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno visualizzato i prodotti ma senza aggiunte al carrello. Nella definizione del filtro, il contenitore è Visita. La regola per questo filtro sequenziale è <p>Visualizzazioni prodotto non nulle </p> <p>Then </p> <p> Aggiunte al carrello è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da Campaign </td> 
   <td colname="col2">Visualizza i dati dei visitatori a cui fanno riferimento le campagne. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Il codice di tracciamento non è nullo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da dispositivi mobili </td> 
   <td colname="col2">Visualizza i dati dei visitatori tramite dispositivi mobili. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Il dispositivo mobile non è nullo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da ricerca naturale </td> 
   <td colname="col2">Visualizzare i dati dei visitatori che non provengono da una ricerca a pagamento. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Ricerca a pagamento è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da dispositivi non mobili </td> 
   <td colname="col2">Visualizza i dati dei visitatori che non utilizzano dispositivi mobili. Nella definizione del filtro, il contenitore è Visita. Questo filtro utilizza la logica Exclude. La regola è <p>Tipo di dispositivo mobile è uguale a Telefono cellulare </p> <p>Oppure </p> <p>Tipo di dispositivo mobile è uguale a Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite dai telefoni </td> 
   <td colname="col2">Visualizza i dati dei visitatori tramite telefono. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Tipo di dispositivo è uguale a Telefono cellulare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite dai motori di ricerca </td> 
   <td colname="col2">Visualizza i dati dei visitatori a cui fanno riferimento i motori di ricerca. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Tipo referrer è uguale a Motori di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite dai siti social </td> 
   <td colname="col2">Visualizza i dati dei visitatori a cui fanno riferimento i siti di social networking. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Tipo di referrer è uguale a Social network. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da tablet </td> 
   <td colname="col2">Visualizza i dati dei visitatori utilizzando le tavolette. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Tipo di dispositivo è uguale a Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite con il cookie ID visitatore </td> 
   <td colname="col2">Visualizza i dati dai visitatori al tuo sito, dove è richiesto un cookie persistente. Nella definizione del filtro, il contenitore è Visita. La regola è <p>Il cookie persistente è uguale a 1. </p> </td> 
  </tr> 
 </tbody> 
</table>