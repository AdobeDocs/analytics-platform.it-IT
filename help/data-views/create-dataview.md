---
title: Creare O Modificare Una Visualizzazione Dati
description: Scopri tutte le impostazioni che puoi configurare quando crei o modifichi una visualizzazione dati.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
role: Admin
TQID: https://experienceleague.adobe.com/EXiKrWVfmMRgZ4GF0OR410Mr2-P5IEjPy3Hf0FmRDJ8
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 28959f1ea858dee686e6d13025621c4a6164c319
workflow-type: tm+mt
source-wordcount: 3152
ht-degree: 74%

---

# Creare o modificare una visualizzazione di dati

Per creare una visualizzazione dati occorre creare metriche e dimensioni dagli elementi dello schema o utilizzare componenti standard. Gli elementi dello schema sono prevalentemente dimensioni o metriche, a seconda dei requisiti aziendali. Una volta trascinato un elemento schema in una visualizzazione dati, a destra vengono visualizzate le opzioni con cui è possibile regolare il funzionamento della dimensione o metrica in Customer Journey Analytics.


>[!BEGINSHADEBOX]

Per un video demo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Creare o modificare una visualizzazione dati](https://experienceleague.adobe.com/it/docs/customer-journey-analytics-learn/tutorials/data-views/overview-of-configuring-data-views-for-cja){target="_blank"}.

>[!ENDSHADEBOX]


Creare o modificare una visualizzazione dati:

1. Accedi a [Customer Journey Analytics](https://analytics.adobe.com) e seleziona **[!UICONTROL Visualizzazioni dati]**, facoltativamente da **[!UICONTROL Gestione dati]**, nel menu superiore.
1. Per creare una visualizzazione dati, seleziona **[!UICONTROL Crea nuova visualizzazione dati]**. In alternativa, puoi selezionare una visualizzazione dati esistente dal relativo elenco per modificarla.


## Configurare {#configure}

Per configurare una visualizzazione dati nuova o esistente:

![Configurare la visualizzazione dati con la scheda dei contenitori separati](assets/data-view-configure-containers.png)



1. Seleziona la scheda **[!UICONTROL Configura]**, se non è già attiva.
1. Specificare **[!UICONTROL Impostazioni]**, **[!UICONTROL Compatibilità]**, **[!UICONTROL Impostazioni IA]** e **[!UICONTROL Dettagli calendario]** (vedere di seguito).
1. Seleziona **[!UICONTROL Salva e continua]** per continuare a configurare la visualizzazione dati nuova o esistente. Seleziona **[!UICONTROL Salva]** per salvare la configurazione per la visualizzazione dati esistente.


### Impostazioni {#configure-settings}

>[!CONTEXTUALHELP]
>id="dataview_externalid"
>title="ID esterno"
>abstract="La modifica dell’ID esterno influisce sul modo in cui il nome della visualizzazione dati viene visualizzato nelle origini esterne, ad esempio negli strumenti di business intelligence."


Impostazioni generali per la visualizzazione dati.

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL Connessione]** | Questo campo collega la visualizzazione dati alla connessione stabilita in precedenza, che contiene uno o più set di dati Adobe Experience Platform. |
| **[!UICONTROL Nome]** | Obbligatorio. Nome della visualizzazione dati. Questo valore viene visualizzato nel menu a discesa in alto a destra in Analysis Workspace. |
| **[!UICONTROL ID esterno]** | Obbligatorio. Il nome della visualizzazione dati che è possibile utilizzare in origini esterne, ad esempio in strumenti di business intelligence. Il valore predefinito è `unspecified`. Se non specifichi un ID esterno, il nome verrà generato dal Nome della visualizzazione dati, sostituendo gli spazi con trattini bassi. |
| **[!UICONTROL Descrizione]** | Facoltativo. Adobe consiglia di specificare una descrizione dettagliata, che consenta agli utenti di capire lo scopo della visualizzazione dati e per chi è progettata. |

{style="table-layout:auto"}

### Compatibilità {#compatibility}


>[!CONTEXTUALHELP]
>id="dataview_dataviewsinadobejourneyoptimizer"
>title="Visualizzazioni dati in Journey Optimizer"
>abstract="Customer Journey Analytics richiede una connessione e una visualizzazione dati compatibili con Adobe Journey Optimizer. Per impostazione predefinita, il sistema crea una connessione e una visualizzazione dati. In alternativa, abilita questa opzione per impostare questa come visualizzazione dati predefinita per il reporting di Adobe Journey Optimizer, che aggiunge i componenti necessari alla visualizzazione dati e i set di dati alla connessione."
>additional-url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/integrations/ajo#connection" text="Quali componenti e set di dati vengono aggiunti."


Fornisce le impostazioni applicabili quando si utilizza AJO oltre a Customer Journey Analytics.

Questa sezione è visibile solo per gli amministratori che dispongono del provisioning di AJO.

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL **Impostare come predefinito una visualizzazione dati in AJO**] | Questa opzione di configurazione standardizza il reporting tra AJO e Customer Journey Analytics. Consente inoltre di eseguire analisi avanzate dei dati AJO in Customer Journey Analytics (selezionando ![Apri](https://spectrum.adobe.com/static/icons/workflow_18/Smock_OpenInLight_18_N.svg) [!UICONTROL **Analisi in CJA**] quando in AJO).<p>Per eseguire questo tipo di analisi, è necessario che AJO acceda a una visualizzazione dati di Customer Journey Analytics.<p>Abilita questa opzione per rendere questa, la visualizzazione dati predefinita utilizzata nel reporting di AJO relativo alla sandbox.</p><p>Automaticamente, questa opzione di configurazione:</p><ul><li>Configura tutti i set di dati AJO richiesti nella connessione associata in Customer Journey Analytics per l’utilizzo con AJO.</li><li>Crea un set di metriche e dimensioni di AJO nella visualizzazione dati (inclusi campi derivati e metriche calcolate). Le etichette di contesto vengono impostate automaticamente su tutte queste metriche e dimensioni.</li><li>Abilita automaticamente l’opzione **[!UICONTROL Utilizza in CJA]** nella connessione associata alla visualizzazione dati. Per ulteriori informazioni su questa opzione, consulta [Utilizzare una connessione Journey Optimizer in Customer Journey Analytics](/help/connections/manage-connections.md).<p>Se disabiliti manualmente questa impostazione dopo averla abilitata, la connessione e le visualizzazioni dati associate vengono ripristinate allo stato predefinito. Ciò può comportare modifiche ai dati nei rapporti.</p></li></ul><p><p>Quando abiliti questa opzione, prendi in considerazione quanto segue: <ul><li>Puoi modificare la visualizzazione dati predefinita in un secondo momento, ma così facendo si potrebbero alterare i dati di reporting di AJO. Se si sceglie di disabilitare questa opzione dopo averla abilitata, verrà richiesto di selezionare una nuova visualizzazione dati predefinita.</li><li>Se hai già eseguito personalizzazioni manuali per i set di dati, le dimensioni o le metriche nella visualizzazione dati di Customer Journey Analytics, le personalizzazioni manuali rimarranno intatte quando abiliti questa opzione di configurazione. Questa opzione apporta ulteriori personalizzazioni che standardizzano ulteriormente il reporting in AJO e in Customer Journey Analytics. Dopo l’abilitazione di questa opzione, puoi effettuare anche personalizzazioni manuali.</li><li>Quando questa opzione è selezionata, la connessione associata alla visualizzazione dati non può essere eliminata.</li></ul>Consulta [Integrare Adobe Journey Optimizer con Adobe Customer Journey Analytics](/help/integrations/ajo.md) per ulteriori informazioni. |

{style="table-layout:auto"}


### Impostazioni IA

Selezionare **[!UICONTROL Abilita per Data Insights Agent]** per abilitare la visualizzazione dati per [Data Insights Agent](/help/data-analysis-ai.md). Data Insights Agent è un agente di conversazione di intelligenza artificiale generativo accessibile dall’Assistente di intelligenza artificiale in Customer Journey Analytics. Consente di analizzare rapidamente i dati con prompt di testo. L’agente crea visualizzazioni rilevanti in Analysis Workspace utilizzando i componenti della visualizzazione dati e i dati effettivi.


### Calendario

Indica il formato del calendario da applicare alla visualizzazione dati. Puoi avere più visualizzazioni dati basate sulla stessa [Connessione](/help/connections/create-connection.md) e assegnare loro diversi tipi di calendario o fusi orari. Tali visualizzazioni dati possono consentire ai team che utilizzano diversi tipi di calendario di soddisfare le rispettive esigenze, utilizzando gli stessi dati sottostanti.

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL **Fuso orario**] | Scegli il fuso orario da applicare ai dati che vengono presentati. Se scegli un fuso orario con ora legale, i dati vengono automaticamente regolati in base a tale impostazione. In primavera, quando si va avanti di un’ora, vi sarà un vuoto di un’ora. In autunno, quando si va indietro di un’ora, verrà ripetuta un’ora al momento del passaggio all’ora solare. |
| [!UICONTROL **Tipo di calendario**] | Determina il raggruppamento delle settimane del mese.<br>**Gregoriano:** Formato calendario standard. I trimestri sono raggruppati per mese.<br>**4-5-4 Retail:** Un calendario 4-5-4 standard per la vendita al dettaglio. Il primo e l’ultimo mese del trimestre contengono ciascuno 4 settimane; il secondo mese del trimestre è invece composto di 5 settimane.<br>**Custom (4-5-4):** simile al calendario 4-5-4 eccetto che è possibile scegliere il primo giorno dell’anno e in quale anno si verifica la settimana “extra”.<br>**Custom (4-4-5):** il primo e l’ultimo mese di ogni trimestre contengono ciascuno 4 settimane; l’ultimo mese di ogni trimestre è invece composto di 5 settimane.<br>**Custom (5-4-4):** il primo mese di ogni trimestre è composto di 5 settimane; il secondo e il terzo mese di ogni trimestre contengono ciascuno 4 settimane. |
| [!UICONTROL **Primo mese dell’anno**] e [!UICONTROL **Primo giorno della settimana**] | Visibile per il calendario di tipo gregoriano. Specifica il mese da cui vuoi iniziare l’anno solare e il giorno da cui vuoi iniziare ogni settimana. |
| [!UICONTROL **Primo giorno dell’anno corrente**] | Visibile per i calendari di tipo personalizzato. Specifica il giorno dell’anno da utilizzare come inizio dell’anno corrente. Il calendario formatta automaticamente il primo giorno di ogni settimana in base a tale valore. |
| [!UICONTROL **Anno in cui si verifica la settimana “extra”**] | Per la maggior parte dei calendari di 364 giorni (52 settimane di 7 giorni ciascuna), ogni anno i giorni rimanenti vengono accumulati fino a formare una settimana aggiuntiva. Questa viene quindi aggiunta all’ultimo mese dell’anno. Specifica a quale anno desideri aggiungere la settimana aggiungere.<br><br/>**Settimane extra e anni bisestili**<br/> Quando selezioni un **[!UICONTROL Tipo di calendario]** personalizzato (**[!UICONTROL Personalizzato (4-5-4)]**, **[!UICONTROL Personalizzato (4-4-5)]** o **[!UICONTROL Personalizzato (5-4-4)]**), i giorni rimanenti si accumulano ogni anno fino a raggiungere una settimana extra completa (7 giorni). La settimana extra viene aggiunta all’anno selezionato in **[!UICONTROL Anno in cui si verifica la settimana “extra”]**.<br/><br/>Gli anni bisestili non vengono visualizzati intenzionalmente nell’**[!UICONTROL Anno in cui si verifica la settimana “extra”]**. Tuttavia, un anno bisestile può contenere ancora 53 settimane. Per forzare un anno bisestile a contenere 53 settimane, seleziona un anno non bisestile da **[!UICONTROL Anno in cui si verifica la settimana “extra”]** per garantire che la deriva cumulativa della data corrisponda a 7 giorni per l’anno bisestile di destinazione. Ad esempio: per avere 53 settimane nel 2024, seleziona **[!UICONTROL 2019]**. Dal 2019 al 2024, la deriva totale delle date è di 7 giorni (2020 (+2), 2021 (+1), 2022 (+1), 2023 (+1) e 2024 (+2)), che si traduce in una 53a settimana nel 2024.<br/><br/>La selezione per **[!UICONTROL Primo giorno dell&#39;anno corrente]** influisce su dove cade la settimana supplementare. Conferma la configurazione utilizzando l’anteprima del calendario. |

{style="table-layout:auto"}

## Contenitori

{{release-limited-testing-section}}


>[!BEGINTABS]

>[!TAB Standard]

![Configurare una visualizzazione dati](assets/data-view-containers-b2c.png)

>[!TAB B2B Edition]

![Configurare una visualizzazione dati B2B](assets/data-view-containers-b2b.png)

>[!ENDTABS]

Nella scheda **[!UICONTROL Contenitori]** è possibile rinominare i contenitori di sistema e aggiungere contenitori personalizzati.

### Contenitori di sistema

Definisce il nome dei contenitori per la visualizzazione dati. I nomi dei contenitori vengono spesso utilizzati nei [segmenti](/help/components/segments/seg-overview.md#containers).

| Nome contenitore | Nome visualizzato (impostazione predefinita) | Descrizione |
| --- | --- | --- |
| globalAccount | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Account globale &#x200B;]** | Il contenitore [!UICONTROL Account globale] include ogni sessione ed evento di account globali entro l’arco temporale specificato. Se la tua organizzazione utilizza un termine diverso, qui puoi rinominare il contenitore. |
| persona | **[!UICONTROL Persona]** | Il contenitore [!UICONTROL Persona] include ogni sessione ed evento per le persone entro l’arco temporale specificato. Se l’organizzazione utilizza un termine diverso (ad esempio, “Visitatore” o “Utente”), qui puoi rinominare il contenitore. |
| sessione | **[!UICONTROL Sessione]** | Il contenitore [!UICONTROL Sessione] consente di identificare le interazioni nelle pagine, le campagne o le conversioni per una sessione specifica. Puoi rinominarlo in “Visita” o con qualsiasi altro termine preferito dalla tua organizzazione. |
| opportunità | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Opportunità&#x200B;]** | Il contenitore [!UICONTROL Opportunità] include ogni sessione ed evento di opportunità entro l’arco temporale specificato. Se la tua organizzazione utilizza un termine diverso, qui puoi rinominare il contenitore. |
| buyGroup | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Gruppo di acquisto &#x200B;]** | Il contenitore [!UICONTROL Gruppo acquisti] include ogni sessione ed evento di gruppi acquisti entro l’arco temporale specificato. Se la tua organizzazione utilizza un termine diverso, qui puoi rinominare il contenitore. |
| evento | **[!UICONTROL Evento]** | Il contenitore [!UICONTROL Evento] definisce singoli eventi in un set di dati. Se l’organizzazione utilizza un termine diverso (ad esempio, “Hit” o “Visualizzazioni pagine”), qui puoi rinominare il contenitore. |
| account | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Account &#x200B;]** | Il contenitore [!UICONTROL Account] include ogni sessione ed evento di account entro l’arco temporale specificato. Se la tua organizzazione utilizza un termine diverso, qui puoi rinominare il contenitore. |

Per rinominare i contenitori di sistema:

1. Seleziona ![Modifica](/help/assets/icons/Edit.svg) per modificare **[!UICONTROL Nome visualizzato]** del contenitore.
1. Definisci un nuovo nome per il contenitore.
1. Seleziona **[!UICONTROL Salva]**.


### Contenitori personalizzati

Aggiungi contenitori personalizzati alla visualizzazione dati in modo da poter utilizzare questi contenitori per [analisi sub-evento](/help/components/segments/sub-event.md). I contenitori personalizzati possono essere definiti da:

* oggetti o array disponibili nei set di dati che fanno parte della connessione. Ad esempio, **[!UICONTROL productListItems]**, **[!UICONTROL content_assets]** o **[!UICONTROL placeContext.activePOIs]**.
* campi derivati che restituiscono un array tramite la funzione [Split](/help/data-views/derived-fields/derived-fields.md#split).
* componenti di visualizzazione dati configurati per restituire un array utilizzando le impostazioni del componente [Substring](/help/data-views/component-settings/substring.md) con l&#39;opzione [Delimiter](/help/data-views/component-settings/substring.md#delimiter).

Per aggiungere un contenitore personalizzato:

1. Seleziona **[!UICONTROL Aggiungi contenitore personalizzato]**.
1. Nella finestra di dialogo **[!UICONTROL Aggiungi contenitore]**:
   1. Selezionare un contenitore dal menu a discesa **[!UICONTROL Contenitore]**. Ad esempio: **[!UICONTROL productListItems.productCategories]**. Al momento della selezione, vengono visualizzati i valori aggiornati per **[!UICONTROL Percorso schema]** e **[!UICONTROL Tipo schema]**.

   1. Immetti un **[!UICONTROL Nome visualizzato]** per il contenitore. Ad esempio: `Product Categories`.
   1. Seleziona **[!UICONTROL Salva]**.

Per modificare un contenitore personalizzato:

1. Selezionare ![Altro](/help/assets/icons/More.svg) per il contenitore personalizzato nella colonna **[!UICONTROL Nome visualizzato]**.
1. Seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Modifica]** dal menu di scelta rapida.
1. Nella finestra di dialogo **[!UICONTROL Modifica contenitore]**:
   1. Modificare **[!UICONTROL Contenitore]** o **[!UICONTROL Nome visualizzato]** o entrambi.
   1. Seleziona **[!UICONTROL Salva]**.

Per eliminare un contenitore personalizzato:

1. Selezionare ![Altro](/help/assets/icons/More.svg) per il contenitore personalizzato nella colonna Nome visualizzato.
1. Selezionare ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Elimina]** dal menu di scelta rapida.

   >[!NOTE]
   >
   >Il contenitore personalizzato viene eliminato senza conferma.
   >

Per modificare l’elenco dei contenitori personalizzati:

1. Selezionare ![ColumnSetting](/help/assets/icons/ColumnSetting.svg).
1. In **[!UICONTROL Personalizza tabella]**:
   1. Selezionare le colonne da visualizzare.
   1. Seleziona **[!UICONTROL Salva]**.


## Componenti

Successivamente, puoi impostare i componenti di una visualizzazione dati e quindi creare metriche e dimensioni dagli elementi dello schema. Puoi anche utilizzare i componenti standard.

>[!IMPORTANT]
>
>Puoi aggiungere fino a 5.000 metriche e 5.000 dimensioni a una singola visualizzazione dati.

1. Seleziona la scheda **[!UICONTROL Componenti]**.

   ![Scheda Componenti](assets/dataview-components.png)

   La [!UICONTROL Connessione] è visibile in alto a sinistra, e contiene i set di dati e i relativi [!UICONTROL Campi dello schema] di seguito.  Tutte le visualizzazioni dati includono componenti standard come Eventi, Persone, Metriche sessione e dimensioni temporali.<ul><li>Quando si definiscono [contenitori personalizzati](#containers-1), le metriche vengono aggiunte automaticamente come ![ShowAllLayer](/help/assets/icons/ShowAllLayer.svg) **[!UICONTROL _nome contenitore personalizzato _Occorrenze]**.</li><li>Il sistema applica il filtro **[!UICONTROL is not deprecated]** per impostazione predefinita, in modo che vengano visualizzati solo i campi schema non obsoleti.</li></ul>

1. Cerca un campo dello schema utilizzando ![icona Ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) **[!UICONTROL Cerca campi dello schema]** o trova un campo spostandoti in una delle raccolte di set di dati, ad esempio ![Cartella](/help/assets/icons/Folder.svg) **[!UICONTROL Set di dati evento]** o ![Cartella](/help/assets/icons/Folder.svg) **[!UICONTROL Set di dati di ricerca]**. Per i set di dati evento, sono disponibili raccolte separate per ![Cartella](/help/assets/icons/Folder.svg) **[!UICONTROL Campi XDM]** e ![Cartella](/help/assets/icons/Folder.svg) **[!UICONTROL Campi ad hoc e relazionali]**.<br/>In alternativa, è possibile creare un campo derivato utilizzando ![Icona dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) **Crea campo derivato**. Per ulteriori informazioni, consulta [Campi derivati](./derived-fields/derived-fields.md).

1. Dopo aver trovato il campo dello schema specifico o definito il campo derivato, trascina il campo, ad esempio ![Icona Handle](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg) **[!UICONTROL Nome pagina]**, dalla barra a sinistra alla sezione **[!UICONTROL Metriche]** o **[!UICONTROL Dimensioni]** sotto **[!UICONTROL Componenti inclusi]**.
Puoi trascinare più volte lo stesso campo dello schema nelle sezioni delle dimensioni o metriche, e configurare una stessa dimensione o metrica in modi diversi. Ad esempio, dal campo pageName, creare le dimensioni `Product Pages` e `Error pages` utilizzando diverse [impostazioni dei componenti](component-settings/overview.md) a destra.
Se trascini una cartella campo dello schema dalla barra a sinistra, i campi nella cartella vengono ordinati automaticamente nelle sezioni appropriate. I campi stringa finiscono nella sezione [!UICONTROL Dimensioni], mentre i tipi di schema numerico finiscono nella sezione [!UICONTROL Metriche]. Se fai clic su **[!UICONTROL Aggiungi tutto]**, tutti i campi dello schema vengono aggiunti alle rispettive sezioni.

1. Quando selezioni il componente, a destra vengono visualizzate le impostazioni.

   ![Componente visualizzazione dati selezionato](assets/dataview-component-pagename.png)

   Configura il componente utilizzando le [impostazioni del componente](component-settings/overview.md). Le impostazioni disponibili dipendono dal tipo di componente (dimensione o metrica) e il tipo di dati dello schema. Le impostazioni includono:

   * [[!UICONTROL Attribuzione]](component-settings/attribution.md)
   * [[!UICONTROL Comportamento]](component-settings/behavior.md)
   * [[!UICONTROL Formato]](component-settings/format.md)
   * [[!UICONTROL Includi valori di esclusione]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Deduplica delle metriche]](component-settings/metric-deduplication.md)
   * [[!UICONTROL Opzioni per “Nessun valore”]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistenza]](component-settings/persistence.md)
   * [[!UICONTROL Bucketing dei valori]](component-settings/value-bucketing.md)

1. Seleziona **[!UICONTROL Salva e continua]** per continuare a configurare la visualizzazione dati nuova o esistente. Seleziona **[!UICONTROL Salva]** per salvare la configurazione per la visualizzazione dati esistente.

### Duplicare metriche o dimensioni

Duplicare metriche o dimensioni e quindi modificare impostazioni specifiche è un modo efficiente per creare più metriche o dimensioni da un singolo campo schema. Seleziona l&#39;impostazione [!UICONTROL Duplica] sotto il nome della metrica o della dimensione, in alto a destra. Modifica la nuova dimensione o metrica e salvala con un nome più descrittivo.

### Filtrare i campi o i set di dati dello schema

Puoi filtrare i campi dello schema ![icona Filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) nella barra a sinistra per [!UICONTROL tipo di dati], [!UICONTROL set di dati], [!UICONTROL governance dei dati] e [!UICONTROL altri] criteri, [!UICONTROL contiene dati], [!UICONTROL è identità] e [!UICONTROL non è obsoleto]:

![Filtrare i campi](assets/dataview-components-filter.png)

>[!TIP]
>
>Se i componenti non vengono caricati correttamente nella visualizzazione dati e viene visualizzato un messaggio di errore, fare riferimento a [Autorizzazioni mancanti](../troubleshooting/lack-of-permissions.md) per una risoluzione.


### Componenti inclusi {#included-components}

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_custom"
>title="Etichette personalizzate"
>abstract="Oltre alle etichette fornite da Adobe, puoi anche definire etichette personalizzate per la tua organizzazione."
>additional-url="https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/overview" text="Panoramica sulle etichette di utilizzo dei dati"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_contract"
>title="Etichette per contratti"
>abstract="Le etichette per contratti (C) vengono utilizzate per categorizzare i dati con obblighi contrattuali o relativi ai criteri di governance dei dati della tua organizzazione."
>additional-url="https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/overview" text="Panoramica sulle etichette di utilizzo dei dati"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_identity"
>title="Etichette di identità"
>abstract="Le etichette di identità (I) vengono utilizzate per categorizzare i dati che possono identificare o contattare una persona specifica."
>additional-url="https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/overview" text="Panoramica sulle etichette di utilizzo dei dati"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_sensitive"
>title="Etichette per dati sensibili"
>abstract="Le etichette per dati sensibili (S) vengono utilizzate per categorizzare i dati considerati sensibili dall’utente e dall’organizzazione."
>additional-url="https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/overview" text="Panoramica sulle etichette di utilizzo dei dati"


>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_partnerecosystem"
>title="Ecosistema partner"
>abstract="Le etichette per l’ecosistema partner (P) vengono utilizzate per categorizzare i dati condivisi con partner di terze parti."
>additional-url="https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/overview" text="Panoramica sulle etichette di utilizzo dei dati"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_policies"
>title="Criteri"
>abstract="Per supportare la conformità dei dati, implementa le policy di utilizzo dei dati. Questi criteri descrivono azioni di marketing consentite o limitate sui dati in Experience Platform. I filtri Criteri applicano il criterio abilitato alla visualizzazione dati."
>additional-url="https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/overview" text="Panoramica sulle etichette di utilizzo dei dati"


>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_responsibleengagement"
>title="Etichette di coinvolgimento responsabile"
>abstract="Le etichette di coinvolgimento responsabile vengono utilizzate per supportare il coinvolgimento responsabile."
>additional-url="https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/overview" text="Panoramica sulle etichette di utilizzo dei dati"


La sezione **[!UICONTROL Componenti inclusi]** contiene l&#39;elenco di **[!UICONTROL Metriche]** e **[!UICONTROL Dimensioni]** configurate per la visualizzazione dati.

* Per cercare componenti, utilizza ![Cerca](/help/assets/icons/Search.svg) **[!UICONTROL _Cerca componenti_]**.
* Per filtrare i componenti inclusi elencati, seleziona ![Filtro](/help/assets/icons/Filter.svg).

  ![Finestra di dialogo filtro componenti inclusi](assets/dataview_includedcomponents_filter.png)

  Nella finestra di dialogo **[!UICONTROL Filtra campo per]**, puoi filtrare in base alle seguenti categorie:

   * **[!UICONTROL Tipo di dati]**: puoi selezionare uno o più dei seguenti tipi di dati: [!UICONTROL Stringa], [!UICONTROL Numero intero], [!UICONTROL Breve], [!UICONTROL Booleano], [!UICONTROL Doppio], [!UICONTROL Byte], [!UICONTROL Lungo], [!UICONTROL Data] o [!UICONTROL Data e ora].
   * **[!UICONTROL Set di dati]**: seleziona uno o più set di dati.
   * **[!UICONTROL Governance dei dati]**: selezionare una o più etichette dalle sottocategorie [!UICONTROL Etichette personalizzate], [!UICONTROL Etichette contratto], [!UICONTROL Etichette identità], [!UICONTROL Etichette sensibilità], [!UICONTROL Ecosistema partner] o [!UICONTROL Criteri].
   * **[!UICONTROL Altro]**: seleziona una o più opzioni tra [!UICONTROL Contiene dati], [!UICONTROL È identità] o [!UICONTROL Non è obsoleto].

  Seleziona **[!UICONTROL Applica]** per applicare i filtri.



## Impostazioni {#dataview-settings}

1. Seleziona la scheda **[!UICONTROL Impostazioni]**.

   ![Impostazioni della visualizzazione dati](assets/dataview-settings.png)

1. Configura i segmenti da applicare all’intera visualizzazione dati. Consulta [Impostazioni (segmenti)](#settings-filters) di seguito.
1. Configura il timeout e le metriche della sessione. Consulta [Impostazioni sessione](#session-settings) di seguito.

1. Seleziona **[!UICONTROL Salva e continua]** per continuare a configurare la visualizzazione dati nuova o esistente. Seleziona **[!UICONTROL Salva]** per salvare la configurazione per la visualizzazione dati esistente.

### Impostazioni (segmenti) {#segment-settings}

Puoi aggiungere segmenti applicabili a un’intera visualizzazione dati. Il segmento viene applicato a qualsiasi rapporto eseguito in Workspace. Trascina un segmento dai componenti nella barra a sinistra al campo **[!UICONTROL Aggiungi segmenti]**.

### Impostazioni di sessione

Determina quanto tempo di inattività deve trascorrere tra gli eventi prima che la sessione scada e che venga iniziata una nuova sessione. È necessario specificare un periodo di tempo. Facoltativamente, puoi forzare l’inizio di una nuova sessione quando un evento contiene una determinata metrica. Per altre informazioni consulta la parte relativa alle [Impostazioni della sessione](session-settings.md).

### Anteprima dati

L’anteprima dati confronta (per i vari contenitori) i dati di questa visualizzazione dati con quelli della connessione. La percentuale di anteprima è basata sul numero totale nella connessione per gli ultimi 90 giorni.

Se l’anteprima non viene caricata, la connessione continua a essere in modalità di backfill.

Una volta specificate tutte le impostazioni, fai clic su **[!UICONTROL Salva e completa]**.
