---
description: Gestione metriche calcolate offre diversi modi per curare le metriche, ad esempio condividere, filtrare, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferite.
title: Gestore metriche calcolate
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 11%

---

# Gestione metriche calcolate

La pagina Metrica calcolata offre diversi modi per curare le metriche, ad esempio condividere, filtrare, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferite.

Il gestore delle metriche calcolate mostra tutti i filtri di tua proprietà e quelli che sono stati condivisi con te. Gli utenti a livello di amministratore possono visualizzare tutte le metriche personalizzate all’interno dell’organizzazione. Questa panoramica presenta l’interfaccia utente e le funzionalità del gestore della metrica calcolata.

![Finestra delle metriche calcolate con i filtri disponibili.](assets/calc-metric-manager.png)

## Accedere al gestore delle metriche calcolate

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Metriche calcolate**].

## Azioni disponibili nel gestore delle metriche calcolate

Nel Gestore metriche calcolate puoi effettuare le seguenti operazioni:

* [Filtrare le metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Contrassegnare le metriche calcolate come preferite](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Approvare le metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Assegnare tag alle metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Condividere le metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Esporta una metrica calcolata in un file CSV.

* [Copiare le metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Elimina metriche calcolate

## Configurare le colonne

Puoi configurare le informazioni visualizzate per ogni metrica calcolata nel gestore delle metriche calcolate configurando le colonne visualizzate.

Per configurare le colonne visibili in Gestione metriche calcolate:

1. In Customer Journey Analytics, seleziona la **[!UICONTROL Components]** , quindi seleziona **[!UICONTROL Calculated metrics]**.

1. In Gestione metriche calcolate, seleziona la **Personalizza colonne** icona ![Icona Personalizza colonne](assets/customize-columns-icon.png), quindi seleziona le colonne che desideri visualizzare nel Gestore delle metriche calcolate.

   Sono disponibili le seguenti colonne:

   | Titolo colonna | Descrizione |
   |---|---|
   | Preferiti | Visualizza icone a forma di stella accanto a ciascuna metrica calcolata, che consentono di contrassegnare le metriche calcolate come preferite. Per ulteriori informazioni, consulta [Contrassegnare le metriche calcolate come preferite](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Titolo e descrizione | Questi valori vengono forniti nel generatore di metriche calcolate. Per modificare il titolo e la descrizione, seleziona il collegamento del titolo per aprire il generatore di metriche calcolate. |
   | Suite di rapporti | Indica in quale suite di rapporti la metrica è stata salvata l’ultima volta. |
   | Proprietario | Indica il proprietario della metrica personalizzata. In qualità di non amministratore, puoi visualizzare solo le metriche che possiedi o quelle che sono state condivise con te. |
   | Tag | Mostra i tag applicati alla metrica, da te o da altri utenti che hanno condiviso con te la metrica calcolata. |
   | Condiviso con | Elenca singoli utenti o gruppi (solo amministratori) o tutti coloro (solo amministratori) con cui hai condiviso la metrica calcolata. <p>Quando una metrica calcolata viene condivisa, accanto al nome della metrica calcolata viene visualizzata un’icona di condivisione.</p> |
   | Data di modifica | Indica la data dell’ultima modifica apportata alla metrica personalizzata. |
   | Utilizzato in | Mostra in quanti componenti è attualmente utilizzata la metrica calcolata. <p>Ad esempio, se la metrica calcolata viene utilizzata in 40 progetti e 2 avvisi, il valore di questa colonna viene visualizzato come [!UICONTROL **42 componenti**].</p> <p>Seleziona il valore in questa colonna per visualizzare il raggruppamento della posizione in cui viene utilizzata la metrica calcolata (ad esempio, [!UICONTROL **Progetti (40)**], [!UICONTROL **Avvisi (2)**]).</p><p>Le metriche calcolate possono essere utilizzate in uno qualsiasi dei seguenti tipi di componenti:</p> <ul><li>Progetti</li><li>Progetti programmati</li></ul><p>Queste informazioni possono essere d’aiuto per determinare se un componente è utile agli utenti dell’organizzazione, dove viene utilizzato, e se deve essere eliminato o modificato.</p><p>Quando visualizzi questa colonna, tieni presente quanto segue:</p><ul><li>Queste informazioni non includono l’utilizzo da API, Report Builder o Data Warehouse.</li><li>Il [!UICONTROL **Utilizzato in**] non viene visualizzata per impostazione predefinita. [Configurare le colonne](#configure-columns) per visualizzarlo.</li><li>Se non sono presenti dati in questa colonna per un determinato componente, ma è presente un [!UICONTROL **Ultimo utilizzo**] data, il componente potrebbe essere stato utilizzato in un’analisi senza essere stato salvato.</li></ul><p>È possibile utilizzare [Dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md) oltre a queste informazioni, ti aiuteranno a tenere traccia di come i componenti vengono utilizzati nella tua organizzazione e a comprenderne meglio il funzionamento.</p> |
   | Ultimo utilizzo | Mostra la data dell’ultimo utilizzo della metrica calcolata in uno qualsiasi dei seguenti tipi di componenti: <ul><li>Metriche calcolate</li><li>Progetti</li><li>Progetti programmati</li></ul> <p>Queste informazioni possono essere utili per determinare se un componente è utile per gli utenti dell’organizzazione o se deve essere eliminato.</p><p>Quando visualizzi questa colonna, tieni presente quanto segue:</p><ul><li>Queste informazioni non includono l’utilizzo da API, Report Builder o Data Warehouse.</li><li>Per alcuni componenti, questa colonna potrebbe non contenere dati se il componente è stato utilizzato l’ultima volta prima di settembre 2023.</li></ul><p>È possibile utilizzare [Dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md) oltre a queste informazioni, ti aiuteranno a tenere traccia di come i componenti vengono utilizzati nella tua organizzazione e a comprenderne meglio il funzionamento. |

   {style="table-layout:auto"}
