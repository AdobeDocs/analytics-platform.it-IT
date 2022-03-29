---
title: Creare o modificare una visualizzazione di dati
description: Tutte le impostazioni che è possibile modificare per creare o modificare una visualizzazione dati.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 59d9fa8d4e4fa4aa3d297e70a619a7456527c5cd
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 4%

---

# Creare o modificare una visualizzazione di dati

La creazione di una visualizzazione dati comporta la creazione di metriche e dimensioni dagli elementi dello schema o l’utilizzo di componenti standard. La maggior parte degli elementi dello schema può essere una dimensione o una metrica a seconda dei requisiti aziendali. Una volta trascinato un elemento dello schema in una visualizzazione dati, le opzioni vengono visualizzate a destra del punto in cui è possibile regolare il funzionamento della dimensione o della metrica in CJA.

Panoramica video sull’argomento:

>[!VIDEO](https://video.tv.adobe.com/v/35110/?quality=12&learn=on)

## Configurare una visualizzazione dati

1. Accedi a [Customer Journey Analytics](https://analytics.adobe.com) e vai al **[!UICONTROL Data Views]** scheda .
2. Fai clic su **[!UICONTROL Add]** per creare una visualizzazione dati, oppure fare clic su una visualizzazione dati esistente per modificarla.

![Nuova visualizzazione dati](assets/new-data-view.png)

### Impostazioni della visualizzazione dati

Fornisce impostazioni generali per la visualizzazione dati.

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Connection] | Questo campo collega la visualizzazione dati alla connessione stabilita in precedenza, che contiene uno o più set di dati Adobe Experience Platform. |
| [!UICONTROL Name] | Obbligatorio. Nome della visualizzazione dati. Questo valore viene visualizzato nel menu a discesa in alto a destra in Analysis Workspace. |
| [!UICONTROL Description] | Facoltativo. L’Adobe consiglia una descrizione dettagliata in modo che gli utenti comprendano perché esiste la visualizzazione dati e per chi è progettata. |

### Contenitori

Designa il nome dei contenitori per la visualizzazione dati. I nomi dei contenitori vengono spesso utilizzati in [Filtri](/help/components/filters/filters-overview.md#Filter-containers).

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Person container name] | [!UICONTROL Person] (impsotazione predefinita). La [!UICONTROL Person] Il contenitore include ogni sessione e evento per i visitatori entro l’intervallo di tempo specificato. Se l’organizzazione utilizza un termine diverso (ad esempio, &quot;Visitatore&quot; o &quot;Utente&quot;), puoi rinominare il contenitore qui. |
| [!UICONTROL Session container name] | [!UICONTROL Session] (impsotazione predefinita). La [!UICONTROL Session] Il contenitore ti consente di identificare le interazioni di pagina, le campagne o le conversioni per una sessione specifica. Puoi rinominare questo contenitore in &quot;Visita&quot; o in qualsiasi altro termine preferito dalla tua organizzazione. |
| [!UICONTROL Event container name] | [!UICONTROL Event] (impsotazione predefinita). La [!UICONTROL Event] Il contenitore definisce singoli eventi in un set di dati. Se l’organizzazione utilizza un termine diverso (ad esempio, &quot;Hits&quot; o &quot;Page Views&quot;), è possibile rinominare il contenitore qui. |

### Calendario

Indica il formato del calendario che si desidera che venga seguito dalla visualizzazione dati. Puoi avere più visualizzazioni dati basate sullo stesso [Connessione](/help/connections/create-connection.md) e assegnare loro diversi tipi di calendario o fusi orari. Queste visualizzazioni dati possono consentire ai team che utilizzano diversi tipi di calendario di soddisfare le rispettive esigenze con gli stessi dati sottostanti.

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Time zone] | Scegli il fuso orario in cui dovranno essere presentati i dati. Se scegli un fuso orario che funziona in base all’ora legale, i dati vengono automaticamente regolati in base a tale impostazione. In primavera, quando gli orologi si aggiustano un&#39;ora in avanti, è presente un intervallo di un&#39;ora. In autunno quando gli orologi regolano un&#39;ora indietro, un&#39;ora viene ripetuta durante il turno DST. |
| [!UICONTROL Calendar Type] | Determinare il raggruppamento di settimane del mese.<br>**Gregoriano:** Formato calendario standard. I trimestri sono raggruppati per mese.<br>**4-5-4 Retail:** Un calendario 4-5-4 standard per la vendita al dettaglio. Il primo e l&#39;ultimo mese del trimestre contiene 4 settimane, mentre il secondo mese del trimestre è costituito da 5 settimane.<br>**Personalizzato (4-5-4):** Simile al calendario 4-5-4 tranne che è possibile scegliere il primo giorno dell&#39;anno e l&#39;anno in cui si verifica la settimana &quot;extra&quot;.<br>**Personalizzato (4-4-5):** Il primo e il secondo mese di ogni trimestre contengono 4 settimane, mentre l&#39;ultima settimana di ogni trimestre consiste di 5 settimane.<br>**Personalizzato (5-4-4):** Il primo mese di ciascun trimestre è costituito da 5 settimane, mentre il secondo e il terzo mese di ciascun trimestre sono costituiti da 4 settimane. |
| [!UICONTROL First month of the year] e [!UICONTROL First day of week] | Visibile per il tipo di calendario gregoriano. Specifica il mese in cui vuoi iniziare l&#39;anno solare e il giorno in cui vuoi che inizi ogni settimana. |
| [!UICONTROL First day of current year] | Visibile per tipi di calendario personalizzati. Specificare il giorno dell&#39;anno che si desidera che inizi l&#39;anno corrente. Il calendario formatta automaticamente il primo giorno di ogni settimana in base a questo valore. |
| [!UICONTROL Year in which the "extra" week occurs] | Con la maggior parte dei calendari di 364 giorni (52 settimane di 7 giorni ciascuno), ogni anno accumula i giorni rimasti fino a formare una settimana supplementare. Questa settimana supplementare viene quindi aggiunta all’ultimo mese dell’anno. Specifica a quale anno desideri aggiungere la settimana supplementare. |

## Impostare i componenti di una visualizzazione dati

Successivamente, puoi creare metriche e dimensioni dagli elementi dello schema. Puoi anche utilizzare i componenti Standard .

1. Accedi a [Customer Journey Analytics](https://analytics.adobe.com) e vai al **[!UICONTROL Data Views]** scheda .
1. Fai clic su **[!UICONTROL Add]** per creare una visualizzazione dati, oppure fare clic su una visualizzazione dati esistente per modificarla.
1. Fai clic sulla scheda **[!UICONTROL Components]**.

   ![Scheda Componenti](assets/components-tab.png)

   È possibile visualizzare le [!UICONTROL Connection] in alto a sinistra, che contiene i set di dati e i relativi [!UICONTROL Schema fields] sotto. I componenti già inclusi sono componenti standard richiesti (generati dal sistema) per tutte le visualizzazioni dati. L’Adobe applica anche il filtro **[!UICONTROL Contains data]** per impostazione predefinita, in modo che vengano visualizzati solo i campi Schema contenenti dati. Se desideri un campo che non contenga dati, rimuovi questo filtro.

1. Trascina un campo dello schema, ad esempio `pageTitle`, dalla barra a sinistra alla sezione Metriche o Dimension .

   Puoi trascinare più volte lo stesso campo schema nelle sezioni di dimensioni o metriche e configurare la stessa dimensione o metrica in modi diversi. Ad esempio, dal `pageTitle` È possibile creare una dimensione denominata &quot;Pagine prodotto&quot; e un’altra denominata &quot;Pagine errore&quot; utilizzando diversi [Impostazioni dei componenti](component-settings/overview.md) a destra.

   ![Scheda 3](assets/components-tab-3.png)

   Se si trascina una cartella di campi dello schema dalla barra a sinistra, queste vengono ordinate automaticamente in sezioni tipiche. I campi stringa finiscono in [!UICONTROL Dimensions] i tipi di sezione e schema numerico si concludono nel [!UICONTROL Metrics] sezione . Puoi anche fare clic su **[!UICONTROL Add all]** e tutti i campi dello schema vengono aggiunti alle rispettive posizioni.

1. Dopo aver selezionato il componente, a destra vengono visualizzate alcune impostazioni. Configura il componente utilizzando [Impostazioni dei componenti](component-settings/overview.md). Le impostazioni disponibili per i componenti dipendono dal fatto che il componente sia una dimensione/metrica e il tipo di dati dello schema. Le impostazioni includono:

   * [[!UICONTROL Attribution]](component-settings/attribution.md)
   * [[!UICONTROL Behavior]](component-settings/behavior.md)
   * [[!UICONTROL Format]](component-settings/format.md)
   * [[!UICONTROL Include exclude values]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Metric deduplication]](component-settings/metric-deduplication.md)
   * [[!UICONTROL No value options]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistence]](component-settings/persistence.md)
   * [[!UICONTROL Value bucketing]](component-settings/value-bucketing.md)

## Duplicare metriche o dimensioni

Duplicare metriche o dimensioni e quindi modificare impostazioni specifiche è un modo semplice per creare più metriche o dimensioni da un singolo campo dello schema. Seleziona la [!UICONTROL Duplicate] sotto il nome della metrica o delle dimensioni in alto a destra. Modifica la nuova dimensione o metrica e salvala con un nome più descrittivo.

![Duplica](assets/duplicate.png)

## Filtrare campi o set di dati dello schema

Puoi filtrare i campi dello schema nella barra a sinistra in base ai seguenti tipi di dati:

![Campi filtro](assets/filter-fields.png)

Puoi anche filtrare per set di dati e specificando se un campo di schema contiene dati o se si tratta di un’identità. Per impostazione predefinita, l’Adobe applica inizialmente il **[!UICONTROL Contains data]** applica il filtro a tutte le visualizzazioni dati.

![Filtra altri](assets/filter-other.png)

## Scheda Impostazioni

1. Accedi a [Customer Journey Analytics](https://analytics.adobe.com) e vai al **[!UICONTROL Data Views]** scheda .
1. Fai clic su **[!UICONTROL Add]** per creare una visualizzazione dati, oppure fare clic su una visualizzazione dati esistente per modificarla.
1. Fai clic sulla scheda **[!UICONTROL Settings]**.

### Filtro globale

Puoi aggiungere filtri applicabili a un’intera visualizzazione dati. Questo filtro viene applicato a qualsiasi rapporto eseguito in Workspace. Trascina un filtro dall’elenco nella barra a sinistra fino al [!UICONTROL Add filters] campo .

### Impostazioni sessione

Determina il periodo di tempo di inattività tra gli eventi prima della scadenza di una sessione e l’avvio di una nuova.

È necessario un periodo di tempo. Facoltativamente, puoi anche forzare l’avvio di una nuova sessione quando un evento contiene una determinata metrica.

Una volta specificate tutte le impostazioni desiderate, fai clic su **[!UICONTROL Save and finish]**.
