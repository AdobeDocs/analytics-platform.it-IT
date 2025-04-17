---
title: Gestire i filtri
description: Scopri come gestire i filtri in Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: ht
source-wordcount: '842'
ht-degree: 100%

---

# Gestire i filtri


Puoi [condividere](filters-share.md), [filtrare](filters-filter.md), [assegnare tag](filters-tag.md), [approvare](filters-approve.md), rinominare, [copiare](filters-copy.md), eliminare, esportare filtri e contrassegnarli come [preferiti](filters-favorite.md) da un’interfaccia di gestione [!UICONTROL Filters] centrale. Per gestire i filtri:

* Seleziona **[!UICONTROL Components]** nell’interfaccia principale, quindi seleziona **[!UICONTROL Filters]**.


>[!NOTE]
>
>I filtri rapidi creati all’interno di un progetto Workspace specifico non vengono visualizzati nel Gestore [!UICONTROL Filters], a meno che il filtro non sia stato reso disponibile per tutti i progetti.
>

## Gestore filtri

Il Gestore filtri dispone dei seguenti elementi dell’interfaccia:

![Interfaccia filtri](assets/filters-manager.png)

### Elenco filtri

L’elenco filtri ➊ mostra tutti i filtri di tua proprietà, i filtri che sono stati definiti per tutti i tuoi progetti e i filtri che sono stati condivisi con te. L’elenco dispone delle seguenti colonne:

| Colonna | Descrizione |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Seleziona ![Star](/help/assets/icons/Star.svg) per contrassegnare come preferito o ![StarOutline](/help/assets/icons/StarOutline.svg) come non preferito un filtro. Consulta [Contrassegnare un filtro come preferito](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Title and description]** | Per modificare il filtro, seleziona il collegamento del titolo e verrà aperto il [Generatore di filtri](filter-builder.md). Un filtro condiviso è indicato con ![Share](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Data view]** | Visualizzazioni dati a cui viene applicato questo filtro. |
| **[!UICONTROL Owner]** | Il proprietario del filtro. Come utente, puoi visualizzare solo i filtri di tua proprietà o quelli che sono stati condivisi con te. |
| **[!UICONTROL Tags]** | I tag per questo filtro. |
| **[!UICONTROL Shared with]** | Quanti singoli utenti o gruppi con cui hai condiviso il filtro. Seleziona per aprire la finestra di dialogo **[!UICONTROL Share Component]**. Per ulteriori informazioni, consulta [Condividere i filtri](filters-share.md). |
| **[!UICONTROL Date modified]** | La data e l’ora dell’ultima volta che il filtro è stato modificato. |
| **[!UICONTROL Used in]** | Mostra dove sono attualmente utilizzati i filtri e quante volte sono stati utilizzati in ciascuna area. <p>Ad esempio, se il filtro viene utilizzato in 40 progetti e 2 avvisi, il valore di questa colonna viene visualizzato come [!UICONTROL **42 componenti**].</p> <p>Seleziona il valore in questa colonna per visualizzare il raggruppamento della posizione in cui vengono utilizzati i filtri (ad esempio, [!UICONTROL **Progetti (40)**], [!UICONTROL **Scorecard per dispositivi mobili (2)**]). Inoltre, puoi visualizzare l’elenco degli elementi in cui vengono utilizzati i filtri. Ad esempio, per visualizzare l’elenco dei progetti in cui vengono utilizzati, seleziona il collegamento [!UICONTROL **Progetti (40)**].</p><p>Ciascuna delle seguenti aree mostra il numero di istanze di filtri utilizzati in quell’area:</p>  <ul><li>[!UICONTROL **Progetti**]<p>Contiene i filtri [creati nel generatore di filtri](/help/components/filters/filter-builder.md#) e disponibili per tutti i progetti.</p></li><li>[!UICONTROL **Componenti ad hoc**]<p>Contiene i filtri [creati come filtri rapidi](/help/components/filters/quick-filters.md) e disponibili solo all’interno di un singolo progetto.</p></li><li>[!UICONTROL **Progetti programmati**]</li><li>[!UICONTROL **Scorecard per dispositivi mobili**]</li><li>[!UICONTROL **Annotazioni**]</li><li>[!UICONTROL **Metriche calcolate**]</li><li>[!UICONTROL **Report Builder**]<p>Selezionando questa opzione viene scaricato un file CSV con le seguenti colonne di dati:</p><ul><li>Nome Report Builder</li><li>Ultimo accesso</li><li>ID utente IMS ultimo accesso</li><li>Nome utente ultimo accesso</li></ul></li></ul><p>Queste informazioni possono essere d’aiuto per determinare se un componente è utile agli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato.</p><p>Quando visualizzi questa colonna, prendi in considerazione quanto segue:</p><ul><li>Questa informazione è disponibile solo per gli amministratori di sistema.</li><li>La colonna [!UICONTROL **Usato in**] non viene visualizzata per impostazione predefinita. Utilizza ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per configurare la visualizzazione di questa colonna.</li><li>Queste informazioni non includono l’utilizzo dall’API o da Data Warehouse.</li><li>Se non sono presenti dati in questa colonna per un determinato componente ma il componente ha una data [!UICONTROL **Ultimo utilizzo**], è possibile che il componente sia stato utilizzato in un’analisi senza essere stato salvato.</li><li>Le informazioni sull’utilizzo sono disponibili a partire da settembre 2023.</li></ul><p>Puoi utilizzare il [dizionario dei dati](/help/components/data-dictionary/data-dictionary-overview.md) insieme a queste informazioni per tenere traccia di come vengono utilizzati i componenti nell’organizzazione e per comprenderne meglio il funzionamento.</p> |
| **[!UICONTROL Last Used]** | Data dell’ultimo utilizzo del filtro. |

{style="table-layout:auto"}

Utilizza ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per specificare quali colonne vuoi visualizzare.

### Barra delle azioni

Puoi eseguire azioni sui filtri utilizzando la barra delle azioni ➋. La barra delle azioni contiene le azioni seguenti:

| Azione | Descrizione |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Aggiungi un altro filtro utilizzando il [Generatore di filtri](filter-builder.md). |
| ![Ricerca](/help/assets/icons/Search.svg) [!UICONTROL *Ricerca per titolo*] | Se nell’elenco non è selezionato alcun filtro, utilizza questo campo di ricerca per trovarli. |
| ![Etichetta](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Assegna tag ai filtri selezionati. Nella finestra di dialogo **[!UICONTROL Tag Filter]**, seleziona o deseleziona i tag per i filtri selezionati. Seleziona **[!UICONTROL Save]** per salvare i tag dei filtri selezionati. Per ulteriori informazioni, consulta [Filtri con tag](/help/components/filters/filters-tag.md). |
| ![Condividi](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share]** | Condividi i filtri selezionati. Nella finestra di dialogo **[!UICONTROL Share Filter]**, puoi effettuare una ![Ricerca](/help/assets/icons/Search.svg) *Ricerca di singoli utenti o gruppi* oppure puoi selezionare **[!UICONTROL Organization]** o **[!UICONTROL Groups]**. Seleziona **[!UICONTROL Save]** per salvare i dettagli di condivisione dei filtri selezionati. Per ulteriori informazioni, consulta [Condividere i filtri](filters-share.md). |
| ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Elimina i filtri selezionati. Viene richiesta una conferma. |
| ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Rinomina un singolo filtro selezionato. Se questa opzione è selezionata, puoi rinominare il filtro direttamente nel testo. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Approva i filtri selezionati. Per ulteriori informazioni, consulta [Approvare i filtri](filters-approve.md). |
| ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** | Copia i filtri selezionati. I nuovi filtri vengono creati con lo stesso nome e suffisso `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Esporta i filtri in un file `Filters List.csv`. |

### Barra dei filtri attivi

La barra dei filtri ➌ mostra i filtri attivi applicati dal pannello dei filtri al relativo elenco (se presente). Puoi rimuovere rapidamente un filtro utilizzando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se sono specificati più filtri, puoi rimuoverli tutti utilizzando **[!UICONTROL Remove all]**.

### Pannello dei filtri

Puoi filtrare l’elenco dei filtri utilizzando il pannello ➍ a sinistra ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** di controllo. Nel pannello dei filtri viene visualizzato il tipo e il numero di filtri che rispettano il filtro specificato. Seleziona ![Filtro](/help/assets/icons/Filter.svg) per attivare/disattivare la visualizzazione del pannello dei filtri.

Per ulteriori informazioni, consulta [Filtrare l’elenco dei filtri](filters-filter.md).
