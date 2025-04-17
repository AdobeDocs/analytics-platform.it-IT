---
title: Gestire segmenti
description: Scopri come gestire i segmenti in Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 66ec61ea64f1265d887d4941a22e1f9757120daa
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 33%

---

# Gestire segmenti


Puoi [condividere](filters-share.md), [segmento](filters-filter.md), [tag](filters-tag.md), [approvare](filters-approve.md), rinominare, [copiare](filters-copy.md), eliminare, esportare segmenti e contrassegnarli come [preferiti](filters-favorite.md) da un&#39;interfaccia di gestione [!UICONTROL Segment] centrale. Per gestire i segmenti:

* Seleziona **[!UICONTROL Components]** nell’interfaccia principale, quindi seleziona **[!UICONTROL Segments]**.


>[!NOTE]
>
>I segmenti rapidi creati all&#39;interno di un progetto Workspace specifico non vengono visualizzati nel gestore [!UICONTROL Filters], a meno che il segmento non sia stato reso disponibile per tutti i progetti.
>

## Gestore segmenti

Il Gestore segmenti dispone dei seguenti elementi dell’interfaccia:

![Interfaccia segmento](assets/filters-manager.png)

### Elenco segmenti

Nell’elenco dei segmenti vengono visualizzati tutti i segmenti di tua proprietà, quelli con ambito in tutti i tuoi progetti e quelli condivisi con te. L’elenco dispone delle seguenti colonne:

| Colonna | Descrizione |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Seleziona questa opzione per favorire ![Star](/help/assets/icons/Star.svg) o per non favorire ![StarOutline](/help/assets/icons/StarOutline.svg) un segmento. Vedi [Segmento contrassegnato come preferito](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Title and description]** | Per modificare il segmento, seleziona il collegamento del titolo, che apre il generatore di [filtri](filter-builder.md). Un segmento condiviso è indicato con ![Condividi](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Data view]** | Le visualizzazioni dati a cui si applica questo segmento. |
| **[!UICONTROL Owner]** | Il proprietario del segmento. In qualità di utente, puoi visualizzare solo i segmenti di tua proprietà o le annotazioni condivise con te. |
| **[!UICONTROL Tags]** | I tag per questo segmento. |
| **[!UICONTROL Shared with]** | Quanti singoli utenti o gruppi hai condiviso il segmento con. Seleziona per aprire la finestra di dialogo **[!UICONTROL Share Component]**. Consulta [Condividi segmenti](filters-share.md) per ulteriori informazioni. |
| **[!UICONTROL Date modified]** | La data e l’ora dell’ultima modifica apportata al segmento. |
| **[!UICONTROL Used in]** | Mostra dove sono attualmente utilizzati i segmenti e quante volte in ciascuna area. <p>Ad esempio, se il segmento viene utilizzato in 40 progetti e 2 avvisi, il valore di questa colonna viene visualizzato come [!UICONTROL **42 componenti**].</p> <p>Seleziona il valore in questa colonna per visualizzare il raggruppamento in cui vengono utilizzati i segmenti (ad esempio, [!UICONTROL **Progetti (40)**], [!UICONTROL **Scorecard per dispositivi mobili (2)**]). Inoltre, puoi visualizzare l’elenco degli elementi in cui vengono utilizzati i segmenti. Ad esempio, per visualizzare l’elenco dei progetti in cui vengono utilizzati, seleziona il collegamento [!UICONTROL **Progetti (40)**].</p><p>Ciascuna delle seguenti aree mostra il numero di istanze di segmenti utilizzati in quell’area:</p>  <ul><li>[!UICONTROL **Progetti**]<p>Contiene i segmenti creati [nel Generatore di segmenti](/help/components/filters/filter-builder.md#) e disponibili per tutti i progetti.</p></li><li>[!UICONTROL **Componenti ad hoc**]<p>Contiene segmenti creati come [segmenti rapidi](/help/components/filters/quick-filters.md) e disponibili solo all&#39;interno di un singolo progetto.</p></li><li>[!UICONTROL **Progetti programmati**]</li><li>[!UICONTROL **Scorecard per dispositivi mobili**]</li><li>[!UICONTROL **Annotazioni**]</li><li>[!UICONTROL **Metriche calcolate**]</li><li>[!UICONTROL **Report Builder**]<p>Selezionando questa opzione viene scaricato un file CSV con le seguenti colonne di dati:</p><ul><li>Nome Report Builder</li><li>Ultimo accesso</li><li>ID utente IMS ultimo accesso</li><li>Nome utente ultimo accesso</li></ul></li></ul><p>Queste informazioni possono essere d’aiuto per determinare se un componente è utile agli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato.</p><p>Quando visualizzi questa colonna, prendi in considerazione quanto segue:</p><ul><li>Questa informazione è disponibile solo per gli amministratori di sistema.</li><li>La colonna [!UICONTROL **Usato in**] non viene visualizzata per impostazione predefinita. Utilizza ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per configurare la visualizzazione di questa colonna.</li><li>Queste informazioni non includono l’utilizzo dall’API o da Data Warehouse.</li><li>Se non sono presenti dati in questa colonna per un determinato componente ma il componente ha una data [!UICONTROL **Ultimo utilizzo**], è possibile che il componente sia stato utilizzato in un’analisi senza essere stato salvato.</li><li>Le informazioni sull’utilizzo sono disponibili a partire da settembre 2023.</li></ul><p>Puoi utilizzare il [dizionario dei dati](/help/components/data-dictionary/data-dictionary-overview.md) insieme a queste informazioni per tenere traccia di come vengono utilizzati i componenti nell’organizzazione e per comprenderne meglio il funzionamento.</p> |
| **[!UICONTROL Last Used]** | Data dell’ultimo utilizzo del segmento. |

Utilizza ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per specificare quali colonne vuoi visualizzare.

### Barra delle azioni

È possibile eseguire azioni sui segmenti utilizzando la barra delle azioni di. La barra delle azioni contiene le azioni seguenti:

| Azione | Descrizione |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Aggiungi un altro segmento utilizzando il [Generatore di filtri](filter-builder.md). |
| ![Ricerca](/help/assets/icons/Search.svg) [!UICONTROL *Ricerca per titolo*] | Se nell’elenco non è selezionato alcun segmento, cerca i segmenti utilizzando questo campo di ricerca. |
| ![Etichetta](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Assegna tag ai segmenti selezionati. Nella finestra di dialogo **[!UICONTROL Tag Segment]**, seleziona o deseleziona i tag per i segmenti selezionati. Selezionare **[!UICONTROL Save]** per salvare i tag per i segmenti selezionati. Per ulteriori informazioni, consulta [Segmenti di tag](/help/components/filters/filters-tag.md). |
| ![Condividi](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share]** | Condividi i segmenti selezionati. Nella finestra di dialogo **[!UICONTROL Share Segment]**, puoi effettuare una ![Ricerca](/help/assets/icons/Search.svg) *Ricerca di singoli utenti o gruppi* oppure puoi selezionare **[!UICONTROL Organization]** o **[!UICONTROL Groups]**. Selezionare **[!UICONTROL Save]** per salvare i dettagli di condivisione per i segmenti selezionati. Consulta [Condividi segmenti](filters-share.md) per ulteriori informazioni. |
| ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Elimina i segmenti selezionati. Viene richiesta una conferma. |
| ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Rinomina un singolo segmento selezionato. Se questa opzione è selezionata, è possibile rinominare il segmento in linea. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Approva i segmenti selezionati. Per ulteriori informazioni, consulta [Approvare segmenti](filters-approve.md). |
| ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** | Copia il segmento selezionato. I nuovi segmenti vengono creati con lo stesso nome e suffisso `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Esporta i segmenti in un file `Filters List.csv`. |

### Barra dei segmenti attiva

La barra dei segmenti mostra i segmenti attivi applicati dal pannello dei segmenti all’elenco dei segmenti (se presenti). È possibile rimuovere rapidamente un segmento utilizzando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se sono specificati più segmenti, è possibile rimuoverli tutti utilizzando **[!UICONTROL Remove all]**.

### Pannello Segment

È possibile segmentare l&#39;elenco dei segmenti utilizzando il pannello sinistro ![Segmento](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** di Windows Live. Il pannello del segmento visualizza il tipo di segmento e il numero di segmenti che lo rispettano. Seleziona ![Segmento](/help/assets/icons/Filter.svg) per attivare/disattivare la visualizzazione del pannello dei segmenti.

Vedi [Filtra l&#39;elenco dei segmenti](filters-filter.md) per ulteriori informazioni.
