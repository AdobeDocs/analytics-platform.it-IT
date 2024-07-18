---
description: Il Generatore di filtri fornisce un’area di lavoro per trascinare e rilasciare Dimension di metriche, filtri ed eventi per filtrare le persone in base alla logica gerarchica del contenitore, alle regole e agli operatori. Questo strumento di sviluppo integrato ti consente di creare e salvare filtri semplici o complessi che identificano gli attributi e le azioni delle persone in visite ed eventi.
title: Creare filtri
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: e1f1e37293f1a18616b11fea685d372ec499c407
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 2%

---

# Generatore di filtri

[!UICONTROL Filter builder] consente di creare filtri semplici o complessi che identificano gli attributi e le azioni delle persone in visite ed eventi. Fornisce un’area di lavoro per trascinare e rilasciare dimensioni metriche, eventi o altri filtri per filtrare le persone in base a logica gerarchica, regole e operatori.

Per informazioni su come creare filtri rapidi applicabili solo al progetto in cui sono stati creati, vedere [Filtri rapidi](/help/components/filters/quick-filters.md).

## Accedere al Generatore di filtri

Puoi accedere al Generatore di filtri in uno dei seguenti modi:

* **Navigazione superiore**: fare clic su **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]**.
* **[!UICONTROL Analysis Workspace]**: con un progetto aperto in Analysis Workspace, seleziona **[!UICONTROL + Components]** > **[!UICONTROL Create filter]**.
* **[!UICONTROL Report Builder]**: [Utilizzare i filtri nel Report Builder](/help/report-builder/work-with-filters.md).

## Panoramica sui criteri di Builder {#section_F61C4268A5974C788629399ADE1E6E7C}

Puoi aggiungere definizioni di regole e contenitori per definire i filtri. Per informazioni sull&#39;accesso al Generatore di filtri, vedere [Accedere al Generatore di filtri](#access-the-filter-builder).

![Generatore di filtri con le nuove opzioni di filtro descritte in questa sezione.](assets/segment_builder_ui_2.png)

| Elemento nell’interfaccia utente | Descrizione |
| --- | --- |
| **[!UICONTROL Title]** | Denomina il filtro |
| **[!UICONTROL Description]** | Fornisci una descrizione dettagliata del filtro. |
| **[!UICONTROL Tags]** | [Assegna tag al filtro](/help/components/filters/manage-filters.md) che stai creando scegliendo da un elenco di tag esistenti o creando un nuovo tag. |
| **[!UICONTROL Definitions]** | In questa posizione vengono [creati e configurati i filtri](/help/components/filters/filters-overview.md), vengono aggiunte le regole e vengono nidificati i contenitori di sequenza. |
| **[!UICONTROL Include]** | (Selettore contenitore superiore). Consente di selezionare il contenitore [principale](/help/components/filters/filters-overview.md) ( [!UICONTROL Person], [!UICONTROL Session], [!UICONTROL Event]). Il contenitore principale predefinito è il contenitore Evento. |
| **[!UICONTROL Options]** | icona (ingranaggio) | <ul><li>**[!UICONTROL + Add container]**: consente di aggiungere un nuovo contenitore (sotto il contenitore principale) alla definizione del filtro.</li><li>**[!UICONTROL Exclude]**: consente di definire il filtro escludendo una o più dimensioni, filtri o metriche.</li></ul> |
| **[!UICONTROL Dimensions]** | I componenti vengono trascinati e rilasciati dall’elenco Dimension (barra laterale arancione). |
| **[!UICONTROL Operator]** | È possibile confrontare e vincolare i valori utilizzando gli operatori selezionati. (è uguale a, non è uguale a, contiene, contiene tutte, ecc.) |
| **[!UICONTROL Value]** | Il valore immesso o selezionato per la dimensione, il filtro o la metrica. |
| **[!UICONTROL Attribution Models]** | Disponibile solo per le quote, questi modelli determinano i valori di una quota da filtrare. I modelli di Dimension sono particolarmente utili nei filtri sequenziali.<ul><li>**[!UICONTROL Repeating]** (impostazione predefinita): include istanze e valori persistenti per la dimensione.</li><li>**[!UICONTROL Instance]**: include istanze per la dimensione.</li><li>**[!UICONTROL Non-repeating instance]**: include istanze univoche (non ripetute) per la dimensione. Si tratta del modello applicato in Flusso quando le varianti di ripetizione sono escluse.</li></ul>Ad esempio, consulta la sezione &quot;Modelli di attribuzione&quot; di seguito. |
| **[!UICONTROL And/Or/Then]** | Assegna gli operatori [!UICONTROL AND/OR/THEN] tra contenitori o regole. L&#39;operatore THEN ti consente di [definire filtri sequenziali](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Metric]** | (Barra laterale verde) Metrica trascinata e rilasciata dall’elenco Metriche. |
| **[!UICONTROL X]** | (Elimina) Consente di eliminare questa parte della definizione del filtro. |
| **[!UICONTROL Create audience from filter]** | La creazione di un pubblico da un filtro consente di condividere il filtro con Adobe Experience Platform per l’attivazione. [Ulteriori informazioni...](/help/components/audiences/audiences-overview.md) |
| **[!UICONTROL Search component]** | Cerca nell&#39;elenco di dimensioni, filtri o metriche. |
| **[!UICONTROL Dimensions]** | (Elenco) L’elenco delle dimensioni che puoi includere nel filtro. Fai clic sull’intestazione per espanderla. |
| **[!UICONTROL Metrics]** | L’elenco delle metriche che puoi includere nel filtro. Fai clic sull’intestazione per espanderla. |
| **[!UICONTROL Filters]** | Elenco dei filtri esistenti che è possibile includere nel filtro. Fai clic sull’intestazione per espanderla. |
| **[!UICONTROL Data View selector]** | Consente di selezionare la suite di rapporti in cui salvare il filtro. Puoi comunque utilizzare il filtro in tutte le visualizzazioni dati. |
| **[!UICONTROL Filter Preview]** | Consente di visualizzare in anteprima le metriche chiave per verificare se disponi di un filtro valido e quanto è ampio il filtro. Rappresenta il raggruppamento del set di dati previsto per verificare se si applica questo filtro. Mostra 3 cerchi concentrici e un elenco per mostrare il numero e la percentuale di corrispondenze per [!UICONTROL People], [!UICONTROL Sessions] e [!UICONTROL Reports Run] per un filtro eseguito su un set di dati.<p>Questo grafico viene aggiornato subito dopo la creazione o la modifica della definizione del filtro. |
| **[!UICONTROL Save]** o **[!UICONTROL Cancel]** | Salva o annulla il filtro. Dopo aver fatto clic su **[!UICONTROL Save]**, si passa al Gestore filtri per gestire il filtro. |

## Creare un filtro {#build-filters}

1. È sufficiente trascinare un evento di Dimension, filtro o metrica dal riquadro di sinistra al campo [!UICONTROL Definitions].

   ![](assets/drag_n_drop_dimension.png)

1. Imposta l&#39;operatore [operator](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=it) dal menu a discesa.
1. Immettere o selezionare un valore per l&#39;elemento selezionato.
1. Se necessario, aggiungere altri contenitori utilizzando **[!UICONTROL And]**, **[!UICONTROL Or]** o **[!UICONTROL Then]** regole.
1. Dopo aver inserito i contenitori e aver impostato le regole, vedi i risultati del filtro nel grafico di convalida in alto a destra. La convalida indica la percentuale e il numero assoluto di visualizzazioni di pagina, visite e persone univoche che corrispondono al filtro creato.
1. In **[!UICONTROL Tags]**, [tag](/help/components/filters/filters-tag.md) il contenitore selezionando un tag esistente o creandone uno nuovo.
1. Fare clic su **[!UICONTROL Save]** per salvare il filtro.

   Sei portato al [Gestore filtri](/help/components/filters/manage-filters.md), dove puoi assegnare tag, condividere e gestire il filtro in più modi.

## Aggiungere contenitori {#containers}

Puoi [creare un framework di contenitori](/help/components/filters/filters-overview.md) e inserire regole logiche e operatori tra.

1. Fai clic su **[!UICONTROL Options > Add container]**.

   Viene aperto un nuovo contenitore [!UICONTROL **Event**] senza un [!UICONTROL **Event**] (Visualizzazione pagina) identificato.

   ![](assets/new_container.png)

1. Modifica il tipo di contenitore in base alle esigenze.
1. Trascina un Dimension, un filtro o un evento dal riquadro di sinistra al contenitore.
1. Continua ad aggiungere nuovi contenitori dal pulsante **[!UICONTROL Options]** > **[!UICONTROL Add container]** di primo livello nella parte superiore della definizione oppure aggiungi contenitori all&#39;interno di un contenitore per nidificare la logica.

   **OR**

   Selezionare una o più regole, quindi fare clic su **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**. In questo modo la selezione diventa un contenitore separato.

## Utilizzare intervalli di date {#date-ranges}

Puoi creare filtri che contengono intervalli di date continui per rispondere a domande su campagne o eventi in corso.

Ad esempio, puoi facilmente creare un filtro che includa &quot;tutti coloro che hanno effettuato un acquisto negli ultimi 60 giorni&quot;.

Creare un contenitore Sessione e al suo interno aggiungere l&#39;intervallo di tempo [!UICONTROL Last 60 days] e la metrica [!UICONTROL Orders is greater than or equal to 1] con un operatore AND.

Ecco un video sull’utilizzo degli intervalli di date continui nei filtri:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Sovrapponi filtri {#stack}

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

1. Fai clic su **[!UICONTROL Show filters]** per visualizzare l&#39;elenco dei filtri nel menu di navigazione a sinistra.

1. Trascina i filtri da sovrapporre nell’area di lavoro di definizione del filtro.

1. Seleziona [!UICONTROL **Salva**].

## Modelli di attribuzione {#attribution}

![](assets/attribution-models.jpg)

**Esempio: filtro eventi in cui eVar1 = A**

| Esempio | A | A | A (persistente) | B | A | C |
|---|---|---|---|---|---|---|
| Ripetizione | X | X | X | - | X | - |
| Istanza | X | X | - | - | X | - |
| Istanza non ripetuta | X | - | - | - | X | - |
