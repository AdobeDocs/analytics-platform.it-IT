---
title: Gestire i filtri
description: Scopri come gestire i filtri nel Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 3%

---

# Gestire i filtri


È possibile [condividere](filters-share.md), [filtrare](filters-filter.md), [tag](filters-tag.md), [approvare](filters-approve.md), rinominare, [copiare](filters-copy.md), eliminare, esportare filtri e contrassegnarli come [preferiti](filters-favorite.md) da un&#39;interfaccia di gestione [!UICONTROL Filters] centrale. Per gestire i filtri:

* Seleziona **[!UICONTROL Components]** nell&#39;interfaccia principale, quindi seleziona **[!UICONTROL Filters]**.


>[!NOTE]
>
>I filtri rapidi creati all&#39;interno di un progetto Workspace specifico non vengono visualizzati nel gestore [!UICONTROL Filters], a meno che il filtro non sia stato reso disponibile per tutti i progetti.
>

## Gestione filtri

Il gestore dei filtri dispone dei seguenti elementi di interfaccia:

![Interfaccia filtri](assets/filters-manager.png)

### Elenco filtri

Nell’elenco dei filtri vengono visualizzati tutti i filtri di tua proprietà, quelli con ambito per tutti i tuoi progetti e quelli condivisi con te. L’elenco include le colonne seguenti:

| Colonna | Descrizione |
| --- | --- | 
| ![ContornoStella](/help/assets/icons/StarOutline.svg) | Seleziona questa opzione per favorire ![Star](/help/assets/icons/Star.svg) o per non favorire ![StarOutline](/help/assets/icons/StarOutline.svg) un filtro. Vedi [Contrassegna il filtro come preferito](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Title and description]** | Per modificare il filtro, seleziona il collegamento del titolo, che apre il generatore di [filtri](filter-builder.md). Un filtro condiviso è indicato con ![Condividi](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Data view]** | Visualizzazioni dati a cui si applica questo filtro. |
| **[!UICONTROL Owner]** | Proprietario del filtro. In qualità di utente, puoi visualizzare solo i filtri di tua proprietà o le annotazioni condivise con te. |
| **[!UICONTROL Tags]** | I tag per questo filtro. |
| **[!UICONTROL Shared with]** | Quanti singoli utenti o gruppi hai condiviso il filtro con. Selezionare per aprire la finestra di dialogo **[!UICONTROL Share Component]**. Per ulteriori informazioni, vedere [Condividi filtri](filters-share.md). |
| **[!UICONTROL Date modified]** | Data e ora dell’ultima modifica apportata al filtro. |
| **[!UICONTROL Used in]** | Mostra dove sono attualmente utilizzati i filtri e quante volte in ciascuna area. <p>Ad esempio, se il filtro viene utilizzato in 40 progetti e 2 avvisi, il valore di questa colonna viene visualizzato come [!UICONTROL **42 componenti**].</p> <p>Seleziona il valore in questa colonna per visualizzare il raggruppamento della posizione in cui vengono utilizzati i filtri (ad esempio, [!UICONTROL **Progetti (40)**], [!UICONTROL **Scorecard per dispositivi mobili (2)**]). Inoltre, puoi visualizzare l’elenco degli elementi in cui vengono utilizzati i filtri. Ad esempio, per visualizzare l&#39;elenco dei progetti in cui vengono utilizzati, seleziona il collegamento [!UICONTROL **Progetti (40)**].</p><p>Ciascuna delle seguenti aree mostra il numero di istanze di filtri utilizzati in quell’area:</p>  <ul><li>[!UICONTROL **Progetti**]<p>Contiene i filtri [creati nel generatore di filtri](/help/components/filters/filter-builder.md#) e disponibili per tutti i progetti.</p></li><li>[!UICONTROL **Componenti ad hoc**]<p>Contiene i filtri [creati come filtri rapidi](/help/components/filters/quick-filters.md) e disponibili solo all&#39;interno di un singolo progetto.</p></li><li>[!UICONTROL **Progetti programmati**]</li><li>[!UICONTROL **Scorecard per dispositivi mobili**]</li><li>[!UICONTROL **Annotazioni**]</li><li>[!UICONTROL **Metriche calcolate**]</li><li>[!UICONTROL **Report Builder**]<p>Selezionando questa opzione viene scaricato un file CSV con le seguenti colonne di dati:</p><ul><li>Nome Report Builder</li><li>Ultimo accesso</li><li>ID utente IMS ultimo accesso</li><li>Nome utente ultimo accesso</li></ul></li></ul><p>Queste informazioni consentono di determinare se un componente è utile per gli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato.</p><p>Quando visualizzi questa colonna, prendi in considerazione quanto segue:</p><ul><li>Queste informazioni sono disponibili solo per gli amministratori di sistema.</li><li>La colonna [!UICONTROL **Usato in**] non viene visualizzata per impostazione predefinita. Utilizza ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per configurare la visualizzazione di questa colonna.</li><li>Queste informazioni non includono l’utilizzo dall’API o da Data Warehouse.</li><li>Se non sono presenti dati in questa colonna per un determinato componente ma il componente ha una data [!UICONTROL **Ultimo utilizzo**], è possibile che il componente sia stato utilizzato in un&#39;analisi senza essere stato salvato.</li><li>Le informazioni sull’utilizzo sono disponibili a partire da settembre 2023.</li></ul><p>Puoi usare il [Dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md) insieme a queste informazioni per tenere traccia di come vengono utilizzati i componenti nell&#39;organizzazione e per comprenderne meglio il funzionamento.</p> |
| **[!UICONTROL Last Used]** | Data dell’ultimo utilizzo del filtro. |

{style="table-layout:auto"}

Utilizzare ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per specificare quali colonne si desidera visualizzare.

### Barra delle azioni

È possibile eseguire azioni sui filtri utilizzando la barra delle azioni di. La barra delle azioni contiene le azioni seguenti:

| Azione | Descrizione |
|---|---|
| ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Aggiungere un altro filtro utilizzando [Generatore di filtri](filter-builder.md). |
| ![Cerca](/help/assets/icons/Search.svg) [!UICONTROL *Cerca per titolo*] | Se nell’elenco non è selezionato alcun filtro, cerca i filtri utilizzando questo campo di ricerca. |
| ![Etichetta](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Assegna tag ai filtri selezionati. Nella finestra di dialogo **[!UICONTROL Tag Filter]**, seleziona o deseleziona i tag per i filtri selezionati. Selezionare **[!UICONTROL Save]** per salvare i tag per i filtri selezionati. Per ulteriori informazioni, vedere [Tag dei filtri](/help/components/filters/filters-tag.md). |
| ![Condividi](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share]** | Condividi i filtri selezionati. Nella finestra di dialogo **[!UICONTROL Share Filter]**, puoi ![Cercare](/help/assets/icons/Search.svg) *Cercare singoli utenti o gruppi* oppure selezionare **[!UICONTROL Organization]** o **[!UICONTROL Groups]**. Selezionare **[!UICONTROL Save]** per salvare i dettagli di condivisione per i filtri selezionati. Per ulteriori informazioni, vedere [Condividi filtri](filters-share.md). |
| ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Elimina i filtri selezionati. Viene richiesta una conferma. |
| ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Rinomina un singolo filtro selezionato. Se questa opzione è selezionata, è possibile rinominare il filtro in linea. |
| ![CerchioSegnoDiSpunta](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Approva i filtri selezionati. Per ulteriori informazioni, vedere [Approvare i filtri](filters-approve.md). |
| ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** | Copia il filtro selezionato. I nuovi filtri vengono creati con lo stesso nome e suffisso `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Esporta i filtri in un file `Filters List.csv`. |

### Barra dei filtri attiva

La barra dei filtri mostra i filtri attivi applicati dal pannello dei filtri all’elenco dei filtri (se presenti). È possibile rimuovere rapidamente un filtro utilizzando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se sono specificati più filtri, è possibile rimuovere tutti utilizzando **[!UICONTROL Remove all]**.

### Pannello Filtro

È possibile filtrare l&#39;elenco dei filtri utilizzando il ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** pannello sinistro di controllo. Nel pannello dei filtri viene visualizzato il tipo di filtro e il numero di filtri che rispettano il filtro specifico. Seleziona ![Filtro](/help/assets/icons/Filter.svg) per attivare/disattivare la visualizzazione del pannello dei filtri.

Per ulteriori informazioni, vedere [Filtrare l&#39;elenco dei filtri](filters-filter.md).
