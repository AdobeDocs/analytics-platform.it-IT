---
title: Gestione filtri
description: Gestire i filtri in Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: e994a53934ae25802fb16e912d0fdee32d5ea524
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 18%

---

# Gestione filtri

Il gestore Filtri offre diversi modi per curare i filtri, ad esempio condividere, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferiti.

Il Gestore filtri mostra tutti i filtri di tua proprietà e che sono stati condivisi con te. Gli utenti a livello di amministratore possono visualizzare tutti i filtri dell’organizzazione. Questa panoramica presenta l’interfaccia utente e le funzionalità del gestore Filtri.

![](assets/filter-manager-ui.png)

## Accedere al Gestore filtri

1. In Customer Journey Analytics, selezionare la scheda **[!UICONTROL Components]**, quindi selezionare **[!UICONTROL Filters]**.

## Azioni disponibili in Gestione filtri

In Gestione filtri puoi effettuare le seguenti operazioni:

* [Filtrare l’elenco dei filtri](/help/components/filters/filters-filter.md)

* [Contrassegnare i filtri come preferiti](/help/components/filters/filters-favorite.md)

* [Approvare i filtri](/help/components/filters/filters-approve.md)

* [Assegnare tag ai filtri](/help/components/filters/filters-tag.md)

* [Condividere i filtri](/help/components/filters/filters-share.md)

* Esporta un filtro in un file CSV.

* [Copiare filtri](/help/components/filters/filters-copy.md)

* Elimina filtri

## Configurare le colonne

Puoi configurare le informazioni visualizzate per ciascun filtro in Gestione filtri configurando le colonne visualizzate.

Per configurare le colonne visibili in Gestione filtri:

1. In Customer Journey Analytics, selezionare la scheda **[!UICONTROL Components]**, quindi selezionare **[!UICONTROL Filers]**.

1. In Gestione filtri, seleziona l&#39;icona **Personalizza colonne** ![Personalizza colonne icona](assets/customize-columns-icon.png), quindi seleziona le colonne da visualizzare in Gestione filtri.

   Sono disponibili le seguenti colonne:

   | Titolo colonna | Descrizione |
   |---|---|
   | Titolo e descrizione | Questi valori vengono forniti nel Generatore di filtri. Per modificare il titolo e la descrizione, seleziona il collegamento del titolo per aprire il Generatore di filtri. |
   | Preferiti | Visualizza icone a forma di stella accanto a ciascun filtro, che consentono di contrassegnare i filtri come preferiti. Per ulteriori informazioni, vedere [Contrassegnare i filtri come preferiti](/help/components/filters/filters-favorite.md). |
   | Visualizzazione dati | Questa colonna indica in quale visualizzazione dati il filtro è stato salvato l’ultima volta. |
   | Proprietario | Indica il proprietario del filtro. Come non amministratore, puoi visualizzare solo i filtri che possiedi o quelli che sono stati condivisi con te. |
   | Tag (non selezionato nel selettore colonna, di conseguenza la colonna non viene visualizzata) | I tag applicati al filtro, da te stesso o da altri utenti che lo hanno condiviso con te. |
   | Condiviso con | Elenca singoli utenti o gruppi (solo amministratore) o tutti coloro (solo amministratore) con cui hai condiviso il filtro. <p>Quando un filtro viene condiviso da te o con te, accanto al nome del filtro viene visualizzata un’icona di condivisione.</p> |
   | Data di modifica | Mostra la data dell’ultima modifica apportata al filtro. |
   | Utilizzate in | Mostra dove sono attualmente utilizzati i filtri e quante volte in ciascuna area. <p>Ad esempio, se il filtro viene utilizzato in 40 progetti e 2 avvisi, il valore di questa colonna viene visualizzato come [!UICONTROL **42 componenti**].</p> <p>Seleziona il valore in questa colonna per visualizzare il raggruppamento della posizione in cui vengono utilizzati i filtri (ad esempio, [!UICONTROL **Progetti (40)**], [!UICONTROL **Scorecard per dispositivi mobili (2)**]). Inoltre, puoi visualizzare l’elenco degli elementi in cui vengono utilizzati i filtri. Ad esempio, per visualizzare l&#39;elenco dei progetti in cui vengono utilizzati, seleziona il collegamento [!UICONTROL **Progetti (40)**].</p><p>Ciascuna delle seguenti aree mostra il numero di istanze di filtri utilizzati in quell’area:</p>  <ul><li>[!UICONTROL **Progetti**]<p>Contiene i filtri [creati nel generatore di filtri](/help/components/filters/filter-builder.md#) e disponibili per tutti i progetti.</p></li><li>[!UICONTROL **Componenti ad hoc**]<p>Contiene i filtri [creati come filtri rapidi](/help/components/filters/quick-filters.md) e disponibili solo all&#39;interno di un singolo progetto.</p></li><li>[!UICONTROL **Progetti programmati**]</li><li>[!UICONTROL **Scorecard per dispositivi mobili**]</li><li>[!UICONTROL **Annotazioni**]</li><li>[!UICONTROL **Metriche calcolate**]</li><li>[!UICONTROL **Report Builder**]<p>Selezionando questa opzione viene scaricato un file CSV con le seguenti colonne di dati:</p><ul><li>Nome Report Builder</li><li>Ultimo accesso</li><li>ID utente IMS ultimo accesso</li><li>Nome utente ultimo accesso</li></ul></li><p>Quando si visualizzano le informazioni per il Report Builder, le informazioni sull’utilizzo sono disponibili a partire da settembre 2024.</p></ul><p>Queste informazioni possono essere utili per determinare se un componente è utile per gli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato.</p><p>Quando visualizzi questa colonna, prendi in considerazione quanto segue:</p><ul><li>Queste informazioni sono disponibili solo per gli amministratori di sistema.</li><li>La colonna [!UICONTROL **Usato in**] non viene visualizzata per impostazione predefinita. [Configura le colonne](#configure-columns) per visualizzarlo.</li><li>Se un filtro include un altro filtro nella sua definizione, qualsiasi utilizzo di tale filtro non viene visualizzato nella colonna [!UICONTROL **Usato in**]. Se un filtro è incluso nella definizione di un altro tipo di componente (ad esempio una metrica calcolata), l&#39;utilizzo viene visualizzato nella colonna [!UICONTROL **Usato in**].</li><li>Queste informazioni non includono l’utilizzo dall’API o da Data Warehouse.</li><li>Se nella colonna non sono presenti dati per un determinato componente ma è presente la data [!UICONTROL **Ultimo utilizzo**], è possibile che il componente sia stato utilizzato in un&#39;analisi senza essere stato salvato.</li><li>Le informazioni sull’utilizzo sono disponibili a partire da settembre 2023.</li></ul><p>Puoi usare il [Dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md) insieme a queste informazioni per tenere traccia di come vengono utilizzati i componenti nell&#39;organizzazione e per comprenderne meglio il funzionamento.</p> |
   | Ultimo utilizzo | Mostra la data dell’ultimo utilizzo del filtro in uno dei seguenti tipi di componenti: <ul><li>Metriche calcolate</li><li>Progetti</li><li>Progetti programmati</li><li>Filtri</li></ul> <p>Queste informazioni possono essere utili per determinare se un componente è utile per gli utenti dell’organizzazione o se deve essere eliminato.</p><p>Quando visualizzi questa colonna, prendi in considerazione quanto segue:</p><ul><li>Queste informazioni non includono l’utilizzo da API, Report Builder o Data Warehouse.</li><li>Per alcuni componenti, questa colonna potrebbe non contenere dati se il componente è stato utilizzato l’ultima volta prima di settembre 2023.</li><li>Queste informazioni sono disponibili solo per gli amministratori di sistema.</li></ul><p>Puoi usare il [Dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md) insieme a queste informazioni per tenere traccia di come vengono utilizzati i componenti nell&#39;organizzazione e per comprenderne meglio il funzionamento. |

   {style="table-layout:auto"}
