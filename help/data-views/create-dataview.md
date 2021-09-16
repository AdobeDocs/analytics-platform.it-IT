---
title: Creare una visualizzazione dati
description: Tutte le impostazioni che è possibile modificare per creare o modificare una visualizzazione dati.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
source-git-commit: 49b4998194274eec2ab8eca231029ccb5ccf648d
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 4%

---

# Creare una visualizzazione dati

La creazione di una visualizzazione dati comporta la creazione di metriche e dimensioni dagli elementi dello schema o l’utilizzo di componenti standard. La maggior parte degli elementi dello schema può essere una dimensione o una metrica a seconda dei requisiti aziendali. Una volta trascinato un elemento dello schema in una visualizzazione dati, le opzioni vengono visualizzate a destra del punto in cui è possibile regolare il funzionamento della dimensione o della metrica in CJA.

## Configurare le impostazioni e i contenitori delle visualizzazioni dati

1. In Customer Journey Analytics, accedi alla scheda **[!UICONTROL Data Views]**.
2. Fai clic su **[!UICONTROL Add]** per creare una nuova visualizzazione dati e configurarne le impostazioni.

![Nuova visualizzazione dati](assets/new-data-view.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Connection] | Questo campo collega la visualizzazione dati alla connessione stabilita in precedenza, che contiene uno o più set di dati Adobe Experience Platform. |
| [!UICONTROL Name] | È obbligatorio assegnare un nome alla visualizzazione dati. |
| [!UICONTROL Description] | Una descrizione dettagliata non è obbligatoria, ma è consigliata. |
| [!UICONTROL Time zone] | Scegli il fuso orario in cui dovranno essere presentati i dati. |
| [!UICONTROL Tags] | [!UICONTROL Tags] consente di organizzare le visualizzazioni dati in categorie. |
| [!UICONTROL Containers] | Puoi rinominare i contenitori qui per determinare come vengono visualizzati in qualsiasi progetto Workspace basato su questa visualizzazione dati. [!UICONTROL Containers] sono utilizzati nei filtri e nell’abbandono/flusso e così via per definire l’ampiezza o la restringenza dell’ambito o del contesto. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) |
| [!UICONTROL Person container name is…] | [!UICONTROL Person] (impsotazione predefinita). Il contenitore [!UICONTROL Person] include ogni visita e visualizzazione di pagina per i visitatori entro un intervallo di tempo specificato. Puoi rinominare il contenitore in &quot;Utente&quot; o in qualsiasi altro termine preferito. |
| [!UICONTROL Session container name is…] | [!UICONTROL Session] (impsotazione predefinita). Il contenitore [!UICONTROL Session] ti consente di identificare le interazioni di pagina, le campagne o le conversioni per una sessione specifica. Puoi rinominare questo contenitore in &quot;Visita&quot; o in qualsiasi altro termine preferito. |
| [!UICONTROL Event container name is…] | [!UICONTROL Event] (impsotazione predefinita). Il contenitore [!UICONTROL Event] definisce gli eventi di pagina da includere o escludere da un filtro. |

Successivamente, puoi creare metriche e dimensioni dagli elementi dello schema. Puoi anche utilizzare i componenti Standard .

## Creare metriche e dimensioni dagli elementi dello schema

1. In [!UICONTROL Customer Journey Analytics] > [!UICONTROL Data Views], fai clic sulla scheda [!UICONTROL Components] .

![Scheda Componenti](assets/components-tab.png)

Puoi vedere il [!UICONTROL Connection] in alto a sinistra, che contiene i set di dati, e il relativo [!UICONTROL Schema fields] qui sotto. Nota bene:

* I componenti già inclusi sono i componenti standard richiesti (generati dal sistema).
* Ad Adobe, il filtro **[!UICONTROL Contains data]** viene applicato per impostazione predefinita, in modo che vengano visualizzati solo i campi dello schema contenenti dati. Se stai cercando un campo che non contiene dati, rimuovi il filtro .

1. Ora trascina un campo schema, ad esempio [!UICONTROL pageTitle], dalla barra a sinistra nella sezione Metriche o Dimension .

   Puoi trascinare più volte lo stesso campo schema nelle sezioni di dimensioni o metriche e configurare la stessa dimensione o metrica in modi diversi.
Ad esempio, dal campo **[!UICONTROL pageTitle]** puoi creare una dimensione denominata &quot;Pagine di prodotto&quot; e un’altra denominata &quot;Pagine di errore&quot;, ecc., rinominando **[!UICONTROL Component Name]** a destra. dal **[!UICONTROL pageTitle]**; Puoi anche creare metriche da un valore stringa. Ad esempio, puoi creare una o più metriche **[!UICONTROL Orders]** con diverse impostazioni di attribuzione e diversi valori di inclusione/esclusione.

   ![Scheda 3](assets/components-tab-3.png)

   >[!NOTE]
   >
   >Puoi trascinare cartelle di campi schema intere dalla barra a sinistra e queste vengono ordinate automaticamente nelle sezioni tradizionali. I campi stringa terminano nella sezione [!UICONTROL Dimensions] e le cifre nella sezione [!UICONTROL Metrics]. In alternativa, puoi fare clic su **[!UICONTROL Add all]** per aggiungere tutti i campi dello schema.

1. Una volta selezionato il componente, vengono visualizzate una serie di impostazioni a destra. Configura il componente utilizzando le impostazioni descritte in

* [[!UICONTROL Component] panoramica delle impostazioni](/help/data-views/component-settings/overview.md)
* [[!UICONTROL Attribution] impostazioni dei componenti](/help/data-views/component-settings/attribution.md)
* [[!UICONTROL Behavior] impostazioni dei componenti](/help/data-views/component-settings/behavior.md)
* [[!UICONTROL Format] impostazioni dei componenti](/help/data-views/component-settings/format.md)
* [[!UICONTROL Include|exclude] impostazioni dei componenti](/help/data-views/component-settings/include-exclude-values.md)
* [[!UICONTROL Metric deduplication] impostazioni dei componenti](/help/data-views/component-settings/metric-deduplication.md)
* [[!UICONTROL No value] impostazioni dei componenti](/help/data-views/component-settings/no-value-options.md)
* [[!UICONTROL Persistence] impostazioni dei componenti](/help/data-views/component-settings/persistence.md)
   [[!UICONTROL Value bucketing] impostazioni dei componenti](/help/data-views/component-settings/value-bucketing.md)

## Utilizzare la funzione [!UICONTROL Duplicate]

Duplicare metriche o dimensioni e quindi modificare impostazioni specifiche è un modo semplice per creare più metriche o dimensioni da un singolo campo dello schema. Seleziona l’impostazione [!UICONTROL Duplicate] sotto il nome della metrica o delle dimensioni in alto a destra. Quindi modifica la nuova metrica o dimensione e salvala con un nome più descrittivo.

![Duplica](assets/duplicate.png)

## Filtrare campi e dimensioni/metriche dello schema

Puoi filtrare i campi dello schema nella barra a sinistra in base ai seguenti tipi di dati:

![Campi filtro](assets/filter-fields.png)

Puoi anche filtrare per set di dati e specificando se un campo di schema contiene dati o se si tratta di un’identità. Per impostazione predefinita, il filtro **[!UICONTROL Contains data]** viene applicato a tutte le visualizzazioni di dati.

![Filtra altri](assets/filter-other.png)

## Aggiungere un filtro globale alla visualizzazione dati

Puoi aggiungere filtri applicabili a un’intera visualizzazione dati. Questo filtro viene applicato a qualsiasi rapporto eseguito in Workspace.

1. Fare clic sulla scheda [!UICONTROL Settings] in [!UICONTROL Data views].
1. Trascina un filtro dall’elenco nella barra a sinistra fino al campo [!UICONTROL Add filters] .
