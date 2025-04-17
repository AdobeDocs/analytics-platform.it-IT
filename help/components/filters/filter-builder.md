---
description: Il Generatore di filtri fornisce un area di lavoro per trascinare metriche, dimensioni, filtri ed eventi per filtrare le persone in base alla logica gerarchica dei contenitori, alle regole e agli operatori. Questo strumento di sviluppo integrato consente di generare e salvare filtri semplici o complessi che identificano gli attributi e le azioni della persona tra visite ed eventi.
title: Generare i filtri
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '1466'
ht-degree: 92%

---

# Generare i filtri {#build-filters}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="Crea un pubblico"
>abstract="I tipi di pubblico possono essere creati da un filtro e condivisi con Adobe Experience Platform per l’attivazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="Anteprima dati"
>abstract="Confronta i dati di questo filtro con i dati della visualizzazione dati. La percentuale di anteprima è basata sul numero totale della visualizzazione dati a partire dagli **ultimi 90 giorni**.<br><br/>Se l’anteprima non viene caricata, è possibile che la connessione sia ancora in retrocompilazione."

<!-- markdownlint-enable MD034 -->



La finestra di dialogo **[!UICONTROL Filter builder]** viene utilizzata per creare nuovi filtri o modificare quelli esistenti. La finestra di dialogo si chiama **[!UICONTROL New filter]** o **[!UICONTROL Edit filter]** per i filtri creati o gestiti dal [[!UICONTROL Filters] gestore](/help/components/filters/manage-filters.md).

>[!BEGINTABS]

>[!TAB Generatore di filtri]

![Finestra dei dettagli del filtro con i campi e le opzioni descritti nella sezione successiva.](assets/filter-builder.png)

>[!TAB Creare o modificare il filtro]

![Finestra dei dettagli del filtro con i campi e le opzioni descritti nella sezione successiva.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Specifica i dettagli seguenti (![Obbligatorio](/help/assets/icons/Required.svg) indica i dati obbligatori):

   | Elemento | Descrizione |
   | --- | --- |
   | **[!UICONTROL Data view]** | Puoi selezionare la visualizzazione dati per il filtro.  Il filtro definito è disponibile come filtro nella scheda [Impostazioni](/help/data-views/create-dataview.md#settings-filters) di una visualizzazione dati. |
   | **[!UICONTROL Project-only filter]** | Casella di informazioni per spiegare che il filtro è visibile solo nel progetto in cui viene creato e che non verrà aggiunto all’elenco dei componenti. Consenti a **[!UICONTROL Make this filter available to all your projects and add it to your component list]** di modificare tale impostazione. Questa casella di informazioni è visibile solo quando si crea un [filtro rapido](quick-filters.md) e si trasformano le informazioni del filtro rapido in un filtro normale utilizzando **[!UICONTROL Open builder]** dall’interfaccia [!UICONTROL Quick filter]. |
   | **[!UICONTROL Title]** ![Obbligatorio](/help/assets/icons/Required.svg) | Assegna un nome al filtro, ad esempio `Last month mobile customers`. |
   | **[!UICONTROL Description]** | Fornisci una descrizione per il filtro, ad esempio `Filter to define the mobile customers for the last month`. |
   | **[!UICONTROL Tags]** | Organizza il filtro creando o applicando uno o più tag. Inizia a digitare per trovare i tag esistenti che puoi selezionare. Oppure premi **[!UICONTROL ENTER]** per aggiungere un nuovo tag. Seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un tag. |
   | **[!UICONTROL Definition]** ![Obbligatorio](/help/assets/icons/Required.svg) | Definisci il filtro utilizzando il [Generatore di definizioni](#definition-builder). |

   {style="table-layout:auto"}

1. Per verificare se la definizione del filtro è corretta, utilizza l’anteprima costantemente aggiornata dei risultati del filtro, in alto a destra.
1. Per creare un pubblico dal filtro e condividerlo con Experience Platform, seleziona **[!UICONTROL Create audience from filter]**. Per ulteriori informazioni, consulta [Creare e pubblicare tipi di pubblico](/help/components/audiences/publish.md).
1. Seleziona:
   * **[!UICONTROL Save]** per salvare il filtro.
   * **[!UICONTROL Save As]** per salvare una copia del filtro.
   * **[!UICONTROL Delete]** per eliminare il filtro.
   * **[!UICONTROL Cancel]** per annullare le modifiche apportate a un filtro o annullare la creazione di un nuovo filtro.


## Generatore di definizioni

Utilizza il Generatore di definizioni per creare la tua definizione di filtro. In questa creazione vengono utilizzati componenti, contenitori, operatori e logica.

Puoi configurare il tipo e l’ambito della definizione:

1. Per specificare il tipo di definizione, indica se desideri creare una definizione di inclusione o esclusione. Seleziona ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Options]** e il pulsante di attivazione/disattivazione a discesa **[!UICONTROL Include]** o **[!UICONTROL Exclude]**.
1. Per specificare l&#39;ambito della definizione, selezionare dall&#39;elenco a discesa **[!UICONTROL Include]** o **[!UICONTROL Exclude]** se si desidera che l&#39;ambito della definizione sia **[!UICONTROL Event]**, **[!UICONTROL Session]**, **[!UICONTROL Person]**, **[!UICONTROL Global Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} o **[!UICONTROL Buying Group]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}

È sempre possibile modificare queste impostazioni in un secondo momento.

### Componenti

Una parte fondamentale della costruzione della definizione del filtro consiste nell’utilizzare dimensioni, metriche, filtri esistenti e intervalli di date. Tutti questi componenti sono disponibili dal pannello dei componenti nel Generatore di filtri.

![Inizia a creare una definizione](assets/start-building-filter.gif){width=100%}

Per aggiungere un componente:

1. Trascina un componente dal pannello dei componenti su **[!UICONTROL Drag and drop Metric(s), Filter(s), and/or Dimensions here]**. Puoi usare ![Ricerca](/help/assets/icons/Search.svg) nella barra dei componenti per cercare componenti specifici.
1. Specifica i dettagli del componente. Ad esempio, seleziona un valore da **[!UICONTROL Select value]**. Oppure inserisci un valore. Cosa e come specificare uno o più valori dipende dal componente e dall’operatore.
1. Facoltativamente, modifica l’operatore predefinito. Ad esempio, da **[!UICONTROL equals]** a **[!UICONTROL equals any of]**. Consulta [Operatori](operators.md) per una panoramica dettagliata degli operatori disponibili.

Per modificare un componente:

* Seleziona un nuovo operatore per il componente dal menu a discesa operatore.
* Se è il caso, seleziona o specifica un valore diverso per l’operatore.
* Se il tipo di componente è una dimensione, puoi definire il modello di attribuzione. Per ulteriori informazioni, consulta [Modello di attribuzione](#attribution-models).

Per eliminare un componente:

* Seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) in un componente.

### Contenitori

Puoi raggruppare più componenti in uno o più contenitori e definire la logica all’interno e tra contenitori. I contenitori consentono di creare definizioni complesse per il filtro.

![Aggiungi un contenitore](assets/add-container.gif){Width=100%}

* Per aggiungere un contenitore, seleziona **[!UICONTROL Add container]** da ![Impostazioni](/help/assets/icons/Setting.svg) **[!UICONTROL Options]**.
* Per aggiungere un componente esistente al contenitore, trascinalo nel contenitore.
* Per aggiungere un altro componente al contenitore, trascinalo dal pannello dei componenti al contenitore. Utilizza la linea di inserimento blu come guida.
* Per aggiungere un altro componente all’esterno del contenitore, trascinalo dal pannello dei componenti all’esterno del contenitore, ma all’interno del contenitore di definizione principale. Utilizza la linea di inserimento blu come guida.
* Per modificare la logica tra i componenti di un contenitore, tra contenitori o tra un contenitore e un componente, seleziona **[!UICONTROL And]**, **[!UICONTROL Or]**, **[!UICONTROL Then]** appropriati. Quando selezioni Then, il filtro diventa sequenziale. Per ulteriori informazioni, consulta la sezione [Creare un filtro sequenziale](seg-sequential-build.md).
* Per cambiare il livello del contenitore, selezionare ![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL Global Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Account](/help/assets/icons/Account.svg) **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Opportunità](/help/assets/icons/Opportunity.svg) **[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![BuyingGroup](/help/assets/icons/BuyingGroup.svg) **[!UICONTROL Buying Group]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![WebPage](/help/assets/icons/WebPage.svg) **[!UICONTROL Event]**, ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Session]** o ![Utente](/help/assets/icons/User.svg) **[!UICONTROL Person]**.

È possibile utilizzare ![Impostazioni](/help/assets/icons/Setting.svg) in un contenitore per le azioni seguenti:

| Azione contenitore | Descrizione |
|---|---|
| **[!UICONTROL Add container]** | Aggiungi un contenitore nidificato al contenitore. |
| **[!UICONTROL Exclude]** | Escludi il risultato dal contenitore nella definizione del filtro. Una barra a sinistra rossa sottile identifica un contenitore di esclusione. |
| **[!UICONTROL Include]** | Includi il risultato dal contenitore nella definizione del filtro. “Includi” è l’impostazione predefinita. Una sottile barra grigia a sinistra identifica un contenitore di inclusione. |
| **[!UICONTROL Name container]** | Rinomina il contenitore dalla relativa descrizione predefinita. Digita un nome nel campo di testo. Se non fornisci alcun input, viene utilizzata la descrizione predefinita. |
| **[!UICONTROL Delete container]** | Elimina il contenitore dalla definizione. |


## Intervalli di date

Puoi creare filtri che contengono intervalli di date continui. Potrai quindi rispondere alle domande relative alle campagne o agli eventi in corso. Ad esempio, puoi creare un filtro che include *tutte le persone che hanno fatto un acquisto online negli ultimi 60 giorni*.

![Filtrare utilizzando un intervallo di date continuo](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

Per un video dimostrativo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Intervalli di date continui nei segmenti](https://video.tv.adobe.com/v/25403/?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


## Sovrapporre filtri {#stack}

Puoi creare un filtro utilizzando i filtri. Quando si utilizzano i filtri in un filtro, è possibile ottimizzarli e ridurne la complessità.

Immagina di voler filtrare in base alla combinazione di tipo di dispositivo (2) e stati USA (50). Potresti creare 100 filtri, ciascuno per la combinazione univoca di tipo di dispositivo (telefono cellulare rispetto a tablet) e stato USA. Per ottenere gli utenti di tablet della California, potresti utilizzare uno dei 100 filtri:

![Filtro semplice per CA e tablet](assets/filter-ca-tablet-single.png)

Oppure potresti definire 52 filtri: 50 filtri per gli stati USA, uno per il telefono cellulare e uno per il tablet. Quindi sovrapponi i filtri per ottenere gli stessi risultati. Per ottenere gli utenti di tablet della California, devi sovrapporre due filtri:

![Sovrapporre filtri per CA e tablet](assets/filter-ca-tablet-stacked.png)


## Attribution {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="Ripetizione"
>abstract="Include le istanze e i valori persistenti per la dimensione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="Istanza"
>abstract="Include le istanze e i valori persistenti per la dimensione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="Istanza di non ripetizione"
>abstract="Include istanze univoche (non ripetute) per la dimensione."

<!-- markdownlint-enable MD034 -->



Quando utilizzi una dimensione nel Generatore di filtri, hai la possibilità di specificare il modello di attribuzione per tale dimensione. Il modello di attribuzione selezionato determina se i dati sono idonei per la condizione specificata per il componente dimensione.

Seleziona ![Impostazione](/help/assets/icons/Setting.svg) all’interno del componente dimensione e seleziona uno dei modelli di attribuzione dalla finestra a comparsa:

| Modelli | Descrizione |
|---|---|
| **[!UICONTROL Repeating model (default)]** | Includi l’istanza e i valori persistenti per la dimensione per determinare la qualifica. |
| **[!UICONTROL Instance]** | Includi solo i valori di istanza per la dimensione per determinare la qualifica. |
| **[!UICONTROL Non-repeating instance]** | Includi valori univoci di istanza (non ripetuti) per la dimensione per determinare la qualifica. |


![Modello di attribuzione sulla dimensione durante la creazione di un filtro](assets/filter-dimension-attribution.png)

### Esempio

Come parte della definizione di un filtro hai specificato la seguente condizione: Nome pagina è uguale a Donne. Simile all’esempio precedente. Ripeti questa definizione di filtro utilizzando gli altri due modelli di attribuzione. In questo modo hai tre filtri, ciascuno con il proprio modello di attribuzione:

* Pagina Donne - Attribuzione - Ripetuta (per impostazione predefinita)
* Pagina Donne - Attribuzione - Istanza
* Pagina Donne - Attribuzione - Istanza non ripetuta


La tabella seguente spiega, per ogni modello di attribuzione, quali eventi in arrivo sono qualificati ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) per tale condizione.


| Pagina Donne - Attribuzione - <br/>*modello di attribuzione* | Evento 1:<br/>Il Nome pagina è uguale a<br/>Donne | Evento 2:<br/>Il Nome pagina è uguale a<br/>Uomini | Evento 3:<br/>Il Nome pagina è uguale a<br/>Donne | Evento 4:<br/>Il Nome pagina è uguale a<br/>Donne<br/>(persistente) | Evento 5:<br/>Il Nome pagina è uguale a<br/>Pagamento | Evento 6:<br/>Il Nome pagina è uguale a<br/>Donne | Evento 7:<br/>Il Nome pagina è uguale a<br/>Pagina Home |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Ripetizione (per impostazione predefinita) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Rimuovi](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Rimuovi](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remove](/help/assets/icons/Remove.svg) |
| Istanza | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Rimuovi](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remove](/help/assets/icons/Remove.svg) | ![Remove](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remove](/help/assets/icons/Remove.svg) |
| Istanza di non ripetizione | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Rimuovi](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remove](/help/assets/icons/Remove.svg) | ![Remove](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remove](/help/assets/icons/Remove.svg) |

Un esempio di rapporto sugli eventi che utilizza i tre filtri è simile al seguente:

![Filtra i risultati del modello di attribuzione](assets/filter-dimension-attribution-results.png)
