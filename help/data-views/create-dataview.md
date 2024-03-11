---
title: Creare o modificare una visualizzazione di dati
description: Tutte le impostazioni disponibili per creare o modificare una visualizzazione dati.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '1304'
ht-degree: 100%

---

# Creare o modificare una visualizzazione di dati

Per creare una visualizzazione dati occorre creare metriche e dimensioni dagli elementi dello schema o utilizzare componenti standard. Gli elementi dello schema sono prevalentemente dimensioni o metriche, a seconda dei requisiti aziendali. Una volta trascinato un elemento schema in una visualizzazione dati, a destra vengono visualizzate le opzioni con cui è possibile regolare il funzionamento della dimensione o metrica in Customer Journey Analytics.

Video sull’argomento:

>[!VIDEO](https://video.tv.adobe.com/v/35110/?quality=12&learn=on)

Creare o modificare una visualizzazione dati:

1. Accedi a [Customer Journey Analytics](https://analytics.adobe.com) e passa alla scheda **[!UICONTROL Data views]**.
1. Per creare una visualizzazione dati, seleziona **[!UICONTROL Create new data view]**. In alternativa, puoi selezionare una visualizzazione dati esistente dal relativo elenco per modificarla.


## Configurare

Per configurare una visualizzazione dati nuova o esistente:

1. Seleziona la scheda **[!UICONTROL Configure]** (se non è già attiva).

   ![Configurare una visualizzazione dati](assets/dataview-configure.png)
1. Specifica i dettagli [!UICONTROL Settings], [!UICONTROL Container], e [!UICONTROL Calendar] (vedi di seguito).
1. Seleziona **[!UICONTROL Save and continue]** per continuare a configurare la visualizzazione dati nuova o esistente. Seleziona **[!UICONTROL Save]** per salvare la configurazione per la visualizzazione dati esistente.


### Impostazioni

Impostazioni generali per la visualizzazione dati.

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Connection] | Questo campo collega la visualizzazione dati alla connessione stabilita in precedenza, che contiene uno o più set di dati Adobe Experience Platform. |
| [!UICONTROL Name] | Obbligatorio. Nome della visualizzazione dati. Questo valore viene visualizzato nell’elenco a discesa in alto a destra in Analysis Workspace. |
| [!UICONTROL Description] | Facoltativo. Adobe consiglia di specificare una descrizione dettagliata, che consenta agli utenti di capire lo scopo della visualizzazione dati e per chi è progettata. |

{style="table-layout:auto"}

### Contenitori

Definisce il nome dei contenitori per la visualizzazione dati. I nomi dei contenitori vengono spesso utilizzati nei [filtri](/help/components/filters/filters-overview.md#Filter-containers).

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Person container name] | [!UICONTROL Person] (impostazione predefinita). Il contenitore [!UICONTROL Person] include ogni sessione ed evento per le persone entro l’arco temporale specificato. Se l’organizzazione utilizza un termine diverso (ad esempio, “Visitatore” o “Utente”), qui puoi rinominare il contenitore. |
| [!UICONTROL Session container name] | [!UICONTROL Session] (impostazione predefinita). Il contenitore [!UICONTROL Session] consente di identificare le interazioni con pagine, campagne o conversioni per una specifica sessione. Puoi rinominarlo “Visita” o con qualsiasi altro termine secondo le esigenze della tua organizzazione. |
| [!UICONTROL Event container name] | [!UICONTROL Event] (impostazione predefinita). Il contenitore [!UICONTROL Event] definisce singoli eventi in un set di dati. Se l’organizzazione utilizza un termine diverso (ad esempio, “Hit” o “Visualizzazioni pagine”), qui puoi rinominare il contenitore. |

{style="table-layout:auto"}

### Calendario

Indica il formato del calendario da applicare alla visualizzazione dati. Puoi avere più visualizzazioni dati basate sulla stessa [Connessione](/help/connections/create-connection.md) e assegnare loro diversi tipi di calendario o fusi orari. Tali visualizzazioni dati possono consentire ai team che utilizzano diversi tipi di calendario di soddisfare le rispettive esigenze, utilizzando gli stessi dati sottostanti.

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Time zone] | Scegli il fuso orario da applicare ai dati che vengono presentati. Se scegli un fuso orario con ora legale, i dati vengono automaticamente regolati in base a tale impostazione. In primavera, quando si va avanti di un’ora, vi sarà un vuoto di un’ora. In autunno, quando si va indietro di un’ora, verrà ripetuta un’ora al momento del passaggio all’ora solare. |
| [!UICONTROL Calendar Type] | Determina in che modo vengono raggruppate le settimane del mese.<br>**Gregoriano:** formato di calendario standard. I trimestri sono raggruppati per mese.<br>**4-5-4 Retail:** calendario 4-5-4 standard nel settore retail. Il primo e l’ultimo mese del trimestre contengono ciascuno 4 settimane; il secondo mese del trimestre è invece composto di 5 settimane.<br>**Custom (4-5-4):** simile al calendario 4-5-4 eccetto che è possibile scegliere il primo giorno dell’anno e in quale anno si verifica la settimana “extra”.<br>**Custom (4-4-5):** il primo e l’ultimo mese di ogni trimestre contengono ciascuno 4 settimane; l’ultimo mese di ogni trimestre è invece composto di 5 settimane.<br>**Custom (5-4-4):** il primo mese di ogni trimestre è composto di 5 settimane; il secondo e il terzo mese di ogni trimestre contengono ciascuno 4 settimane. |
| [!UICONTROL First month of the year] e [!UICONTROL First day of week] | Visibile per il calendario di tipo gregoriano. Specifica il mese da cui vuoi iniziare l’anno solare e il giorno da cui vuoi iniziare ogni settimana. |
| [!UICONTROL First day of current year] | Visibile per i calendari di tipo personalizzato. Specifica il giorno dell’anno da utilizzare come inizio dell’anno corrente. Il calendario formatta automaticamente il primo giorno di ogni settimana in base a tale valore. |
| [!UICONTROL Year in which the "extra" week occurs] | Per la maggior parte dei calendari di 364 giorni (52 settimane di 7 giorni ciascuna), ogni anno i giorni rimanenti vengono accumulati fino a formare una settimana aggiuntiva. Questa viene quindi aggiunta all’ultimo mese dell’anno. Specifica a quale anno desideri aggiungere la settimana aggiungere. |

{style="table-layout:auto"}

## Componenti

Successivamente, puoi impostare i componenti di una visualizzazione dati e quindi creare metriche e dimensioni dagli elementi dello schema. Puoi anche utilizzare i componenti standard.

>[!IMPORTANT]
>
>Puoi aggiungere fino a 5.000 metriche e 5.000 dimensioni a una singola visualizzazione dati.

1. Seleziona la scheda **[!UICONTROL Components]**.

   ![Scheda Componenti](assets/dataview-components.png)

   La [!UICONTROL Connection] è visibile in alto a sinistra, e contiene i set di dati e i relativi [!UICONTROL Schema fields].  I componenti già inclusi sono componenti standard (generati dal sistema) necessari per tutte le visualizzazioni dati (come Eventi, Persone, Metriche sessioni e dimensioni Minuto, Trimestre, Settimana). Adobe applica anche il filtro **[!UICONTROL Contains data]** e **[!UICONTROL is not deprecated]** per impostazione predefinita, in modo che vengano visualizzati solo i campi schema che contengono dati e che non sono obsoleti.

1. Cerca un campo schema tramite l’![icona Ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) **[!UICONTROL Search schema fields]** oppure trova un campo spostandoti in una qualsiasi delle raccolte di set di dati, come ![icona Cartella](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg) **[!UICONTROL Event datasets]**.<br/>In alternativa, puoi creare un campo derivato utilizzando l’![icona Dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) **Crea campo derivato**. Per ulteriori informazioni, consulta [Campi derivati](./derived-fields/derived-fields.md).

1. Una volta trovato il campo schema specifico o definito il campo derivato, trascinalo, ad esempio ![icona Gestisci](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg) **[!UICONTROL Page Name]**, dalla barra a sinistra alla sezione Metriche o Dimensioni.
Puoi trascinare più volte lo stesso campo schema nelle sezioni delle dimensioni o metriche, e configurare una stessa dimensione o metrica in modi diversi. Ad esempio, dal campo pageName, puoi creare una dimensione denominata “Pagine prodotto” e un’altra denominata “Pagine errore”, applicando a ciascuna diverse [impostazioni componente](component-settings/overview.md) a destra.
Se trascini una cartella di campi schema dalla barra a sinistra, vengono disposti automaticamente nelle sezioni appropriate. I campi stringa vanno nella sezione [!UICONTROL Dimensions], mentre i campi schema di tipo numerico vanno nella sezione [!UICONTROL Metrics]. Se fai clic su **[!UICONTROL Add all]**, tutti i campi schema vengono aggiunti alle rispettive posizioni.

1. Quando selezioni il componente, a destra vengono visualizzate le impostazioni.

   ![Componente visualizzazione dati selezionato](assets/dataview-component-pagename.png)

   Configura il componente utilizzando le [impostazioni del componente](component-settings/overview.md). Le impostazioni disponibili dipendono dal tipo di componente (dimensione o metrica) e il tipo di dati dello schema. Le impostazioni includono:

   * [[!UICONTROL Attribution]](component-settings/attribution.md)
   * [[!UICONTROL Behavior]](component-settings/behavior.md)
   * [[!UICONTROL Format]](component-settings/format.md)
   * [[!UICONTROL Include exclude values]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Metric deduplication]](component-settings/metric-deduplication.md)
   * [[!UICONTROL No value options]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistence]](component-settings/persistence.md)
   * [[!UICONTROL Value bucketing]](component-settings/value-bucketing.md)

1. Seleziona **[!UICONTROL Save and continue]** per continuare a configurare la visualizzazione dati nuova o esistente. Seleziona **[!UICONTROL Save]** per salvare la configurazione per la visualizzazione dati esistente.

**Duplicare metriche o dimensioni**

È possibile duplicare metriche o dimensioni e quindi modificarne le impostazioni specifiche per creare facilmente più metriche o dimensioni da un singolo campo schema. Seleziona l’impostazione [!UICONTROL Duplicate] sotto il nome della metrica o delle dimensioni, in alto a destra. Modifica la nuova dimensione o metrica e salvala con un nome descrittivo.

**Filtrare i campi o set di dati dello schema**

Puoi filtrare i campi schema ![icona Filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) nella barra a sinistra per i criteri [!UICONTROL data type], [!UICONTROL datasets], [!UICONTROL data governance], e [!UICONTROL other] ([!UICONTROL contains data], [!UICONTROL is identity], e [!UICONTROL is not deprecated]):

![Filtrare i campi](assets/dataview-components-filter.png)

>[!TIP]
>
>Se i componenti non vengono caricati correttamente nella visualizzazione dati e viene invece visualizzato un messaggio di errore, consulta [Mancanza di autorizzazioni](../troubleshooting/lack-of-permissions.md) per ottenere una soluzione.



## Impostazioni

1. Seleziona la scheda **[!UICONTROL Settings]**.
1. Configura i filtri da applicare all’intera visualizzazione dati. Consulta [Impostazioni (filtri)](#settings-filters) di seguito.
1. Configura il timeout e le metriche della sessione. Consulta [Impostazioni sessione](#session-settings) di seguito.
1. Seleziona **[!UICONTROL Save and continue]** per continuare a configurare la visualizzazione dati nuova o esistente. Seleziona **[!UICONTROL Save]** per salvare la configurazione per la visualizzazione dati esistente.

### Impostazioni (filtri)

Puoi aggiungere dei filtri applicabili a un’intera visualizzazione dati. Questo filtro viene applicato a qualsiasi rapporto eseguito in Workspace. Trascina un filtro dall’elenco nella barra a sinistra e rilascialo sul campo [!UICONTROL Add filters].

### Impostazioni di sessione

Determina quanto tempo di inattività deve trascorrere tra gli eventi prima che la sessione scada e che venga iniziata una nuova sessione. È necessario specificare un periodo di tempo. Facoltativamente, puoi anche forzare l’inizio di una nuova sessione quando un evento contiene una determinata metrica. Per altre informazioni consulta la parte relativa alle [Impostazioni della sessione](session-settings.md).

Una volta specificate tutte le impostazioni desiderate, fai clic su **[!UICONTROL Save and finish]**.
