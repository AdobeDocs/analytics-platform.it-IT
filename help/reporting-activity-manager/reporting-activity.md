---
title: Visualizzare l’attività di reporting in Reporting Activity Manager
description: Scopri come utilizzare il Reporting Activity Manager per diagnosticare e risolvere i problemi di capacità durante i periodi in cui si verificano picchi di reporting.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 57124124254f5ca9eb2a9f63a7478cd288c19b0e
workflow-type: tm+mt
source-wordcount: '1704'
ht-degree: 10%

---

# Visualizzare l’attività di reporting in Reporting Activity Manager

{{release-limited-testing}}

Il [!UICONTROL Reporting Activity Manager] consente agli amministratori di diagnosticare e risolvere rapidamente i problemi di capacità di reporting durante i periodi di picco.

Per ulteriori informazioni su Reporting Activity Manager, inclusi i vantaggi chiave e i requisiti delle autorizzazioni, vedere [Panoramica di Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md).

## Visualizza attività di reporting per tutte le connessioni {#view-all-report-suites}

1. In Customer Journey Analytics, vai a **[!UICONTROL Tools]** > **[!UICONTROL Reporting Activity Manager]**.

   Viene visualizzato un elenco delle connessioni di base abilitate.

   ![coda dei rapporti](assets/reporting-activity1.png)

1. (Facoltativo) Puoi cercare o filtrare l’elenco delle connessioni:

   * Utilizza il campo di ricerca per cercare una connessione specifica. Inizia a digitare il nome o l’ID della connessione e l’elenco degli aggiornamenti delle connessioni durante la digitazione.

   * Seleziona la [!UICONTROL **Filtro**] icona ![Icona Filtro](assets/filter-icon.png) per espandere l&#39;elenco delle opzioni di filtro. Puoi filtrare per [!UICONTROL **Preferiti**] o [!UICONTROL **Stato**].

     Per contrassegnare una connessione come preferita, seleziona l’icona a forma di stella a sinistra del nome della connessione.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Visualizza le informazioni sull&#39;utilizzo di ogni connessione. È possibile selezionare un&#39;intestazione di colonna per ordinare la tabella in base a tale colonna.

   Sono disponibili le seguenti colonne:

   | Elemento nell’interfaccia utente | Descrizione |
   | --- | --- |
   | **[!UICONTROL Connection]** | La connessione di cui si sta monitorando l’attività di reporting. |
   | **[!UICONTROL Data Views]** | Mostra tutte le visualizzazioni dati che confluiscono nella connessione. Le visualizzazioni dati aggiungono complessità alle richieste di reporting a causa di livelli aggiuntivi di filtraggio e segmentazione applicati. Tutte le richieste provenienti dalla visualizzazione dati vengono combinate nella connessione.<p>Ad esempio, se disponi di 10 richieste provenienti da 5 visualizzazioni dati, nella connessione sono 50 le richieste. In questo modo, si possono raggiungere molto rapidamente i limiti di capacità. |
   | **[!UICONTROL Capacity utilization]** | Percentuale della capacità di reporting della connessione utilizzata, in tempo reale. <p>**Nota** Una capacità di utilizzo pari al 100% non indica necessariamente che è necessario iniziare immediatamente ad annullare le richieste di reporting. La capacità di utilizzo del 100% può essere integra se il tempo medio di attesa è ragionevole. D’altra parte, una capacità di utilizzo del 100% potrebbe indicare un problema se anche il numero di richieste in coda è in crescita.</p> |
   | **[!UICONTROL Queued requests]** | Numero di richieste in attesa di elaborazione. <!-- ??? --> |
   | **[!UICONTROL Queue wait time]** | Tempo medio di attesa prima dell’elaborazione delle richieste. <!-- ???? --> |
   | **[!UICONTROL Status]** | I possibili stati sono: <ul><li>[!UICONTROL **Attivo**] (blu): sono stati eseguiti rapporti sulla connessione che ora è monitorata per l’attività.</li><li>[!UICONTROL **Inattivo**] (grigio): non è mai stato eseguito alcun rapporto sulla connessione. Questo stato viene visualizzato solo al momento della creazione delle connessioni.</li></ul> |

   {style="table-layout:auto"}

## Visualizzare l’attività di reporting per una singola connessione

1. In Customer Journey Analytics, seleziona [!UICONTROL **Strumenti**] > [!UICONTROL **Reporting Activity Manager**].

1. Selezionare il titolo collegato della connessione per la quale si desidera visualizzare i dettagli.

   I dati dell’attività di reporting vengono visualizzati per la connessione selezionata.

   <!-- Need to update this screenshot: ![connection](assets/indiv-report-ste.png) -->

1. Utilizza i grafici e la tabella disponibili per comprendere l’attività di reporting nella connessione.

   * [Visualizzare grafici](#view-graphs)

   * [Visualizza tabella](#view-table)

### Visualizzare grafici

I seguenti grafici sono disponibili per aiutarti a comprendere meglio l’attività che si verifica nella connessione.

Se i grafici non sono visibili, selezionare [!UICONTROL **Mostra grafici**] pulsante.

#### Grafico Utilizzo {#utilization}

Il grafico Utilizzo mostra l&#39;utilizzo dei rapporti per la connessione selezionata nelle ultime 2 ore.

Passa il cursore del mouse sul grafico per visualizzare i punti nel tempo in cui la percentuale di capacità di utilizzo era più alta per quel minuto.

* **Asse X**: capacità di utilizzo dei rapporti nelle ultime 2 ore.
* **Asse Y**: percentuale di capacità di utilizzo dei rapporti, in minuti.

  ![grafico di utilizzo](assets/utilization-graph.png)

#### Grafico Utenti distinti

Il grafico Utenti distinti mostra l’attività di reporting per la connessione selezionata nelle ultime 2 ore.

Passa il cursore del mouse sul grafico per visualizzare i punti nel tempo in cui il numero massimo di utenti era più alto per quel minuto.

* **Asse X**: l’attività di reporting nell’ultimo intervallo di tempo di 2 ore.
* **Asse Y**: numero di utenti che hanno effettuato richieste di reporting per minuto.

  ![Grafico Utenti distinti](assets/distinct-users-graph.png)

#### Grafico Richieste

Il grafico Richieste mostra il numero di richieste elaborate e completate per la connessione selezionata nelle ultime 2 ore.

Passa il cursore del mouse sul grafico per visualizzare i punti nel tempo in cui il numero massimo di richieste era più alto per quel minuto.

* **Asse X**: numero di richieste elaborate e completate nell’ultimo intervallo di 2 ore.
* **Asse Y**: numero di richieste elaborate (in viola) e completate (in verde), al minuto.

  ![Grafico Utenti distinti](assets/requests-graph.png)

#### Grafico in coda

Il grafico di accodamento mostra il tempo medio di attesa della coda (in secondi) per le richieste di reporting per la connessione selezionata nelle ultime 2 ore.

Passa il cursore del mouse sul grafico per visualizzare i punti nel tempo in cui il tempo medio di attesa massimo era più alto per quel minuto.

* **Asse X**: tempo medio di attesa della coda per le richieste di reporting nell’ultimo intervallo di tempo di 2 ore.
* **Asse Y**: tempo medio di attesa (in secondi).

  ![Grafico Utenti distinti](assets/queueing-graph.png)

### Visualizza tabella {#view-table}

È possibile scegliere di visualizzare i dati scegliendo una delle seguenti schede nella parte superiore della tabella dati: [!UICONTROL **Richiesta**], [!UICONTROL **Utente**], [!UICONTROL **Progetto**], o [!UICONTROL **Applicazione**].

>[!TIP]
>
>Puoi selezionare [!UICONTROL **Nascondere i grafici**] per visualizzare solo la tabella.

![tabulazioni tabella](assets/indiv-report-ste-table-tabs.png)

#### Visualizza dati per richiesta

Quando selezioni il [!UICONTROL **Richiesta**] nella tabella sono disponibili le seguenti colonne:

| Colonna | Descrizione |
| --- | --- |
| [!UICONTROL **ID richiesta**] | Può essere utilizzato per la risoluzione dei problemi. |
| [!UICONTROL **Esecuzione temporale**] | Da quanto tempo la richiesta è in esecuzione. |
| [!UICONTROL **Ora di inizio**] | Quando la richiesta ha iniziato l’elaborazione (in base all’ora locale dell’amministratore). |
| [!UICONTROL **Tempo di attesa**] | Tempo di attesa della richiesta prima dell’elaborazione. Questo valore è generalmente a &quot;0&quot; quando la capacità è sufficiente. |
| [!UICONTROL **Applicazione**] | Le applicazioni supportate dalla [!UICONTROL Reporting Activity Manager] sono: <ul><li>Interfaccia utente di Analysis Workspace</li><li>Progetti pianificati in Workspace</li><li>Report Builder</li><li>Interfaccia utente di Builder: segmento, metriche calcolate, annotazioni, pubblico, ecc.</li><li>Chiamate API da 1.4 o 2.0 API</li><li>Avvisi intelligenti</li></ul> |
| [!UICONTROL **Utente**] | Utente che ha avviato la richiesta. <p>**Nota:** Se il valore di questa colonna è [!UICONTROL **Non riconosciuto**], significa che l’utente si trova in una società di accesso per la quale non disponi di autorizzazioni amministrative.</p> |
| [!UICONTROL **Progetto**] | Nomi di progetto Workspace salvati, ID di report API e così via (I metadati possono variare tra le varie applicazioni). |
| [!UICONTROL **Stato**] | Indicatori di stato: <ul><li>**In esecuzione**: richiesta in fase di elaborazione.</li><li>**In sospeso**: richiesta in attesa di elaborazione.</li></ul> |
| [!UICONTROL **Complessi**] | Non tutte le richieste richiedono la stessa quantità di tempo per essere elaborate. La complessità delle richieste può essere utile per avere un’idea generale sul tempo necessario per elaborarle. <p>Possibili valori:</p> <ul><li>[!UICONTROL **Bassa**]</li><li>[!UICONTROL **Canale**]</li><li>[!UICONTROL **Alta**]</li></ul>Questo valore è influenzato dai valori delle colonne seguenti:<ul><li>[!UICONTROL **Limiti del mese**]</li><li>[!UICONTROL **Colonne**]</li><li>[!UICONTROL **Segmenti**]</li></ul> |
| [!UICONTROL **Limiti del mese**] | Il numero di mesi inclusi in una richiesta. L’aumento dei limiti di mese aggiunge complessità alla richiesta. |
| [!UICONTROL **Colonne**] | Il numero di metriche e raggruppamenti nella richiesta. Più colonne aumenta la complessità della richiesta. |
| [!UICONTROL **Segmenti**] | Il numero di segmenti applicati alla richiesta. Altri segmenti aumentano la complessità della richiesta. |

{style="table-layout:auto"}

#### Visualizza dati per utente

Quando selezioni il [!UICONTROL **Utente**] nella tabella sono disponibili le seguenti colonne:

| Colonna | Descrizione |
| --- | --- |
| [!UICONTROL **Utente**] | Utente che ha avviato la richiesta. Se il valore di questa colonna è [!UICONTROL **Non riconosciuto**], significa che l’utente si trova in una società di accesso per la quale non disponi di autorizzazioni amministrative. |
| [!UICONTROL **Numero di richieste**] | Numero di richieste avviate dall&#39;utente. |
| [!UICONTROL **Numero di progetti**] | Il numero di progetti associati all’utente. <!-- ??? --> |
| [!UICONTROL **Applicazione**] | Le applicazioni supportate dalla [!UICONTROL Reporting Activity Manager] sono: <ul><li>Interfaccia utente di Analysis Workspace</li><li>Progetti pianificati in Workspace</li><li>Report Builder</li><li>Interfaccia utente di Builder: segmento, metriche calcolate, annotazioni, pubblico, ecc.</li><li>Chiamate API da 1.4 o 2.0 API</li><li>Avvisi intelligenti</li></ul> |
| [!UICONTROL **Complessità media**] | La complessità media delle richieste avviate dall’utente. <p>Non tutte le richieste richiedono la stessa quantità di tempo per essere elaborate. La complessità delle richieste può essere utile per avere un’idea generale sul tempo necessario per elaborarle.</p><p>Il valore di questa colonna si basa su un punteggio determinato dai valori delle colonne seguenti:</p><ul><li>[!UICONTROL **Limiti medi del mese**]</li><li>[!UICONTROL **Media colonne**]</li><li>[!UICONTROL **Segmenti medi**]</li></ul> |
| [!UICONTROL **Limiti medi del mese**] | Numero medio di mesi inclusi nelle richieste. L’aumento dei limiti di mese aggiunge complessità alla richiesta. |
| [!UICONTROL **Media colonne**] | Il numero medio di metriche e raggruppamenti nelle richieste incluse. Più colonne aumenta la complessità della richiesta. |
| [!UICONTROL **Segmenti medi**] | Numero medio di segmenti applicati alle richieste incluse. Altri segmenti aumentano la complessità della richiesta. |

{style="table-layout:auto"}

#### Visualizza dati per progetto

Quando selezioni il [!UICONTROL **Progetto**] nella tabella sono disponibili le seguenti colonne:

| Colonna | Descrizione |
| --- | --- |
| [!UICONTROL **Progetto**] | Progetto in cui sono state avviate le query. |
| [!UICONTROL **Numero di richieste**] | Il numero di richieste associate al progetto. |
| [!UICONTROL **Numero di utenti**] | Il numero di utenti associati al progetto. <!-- ??? --> |
| [!UICONTROL **Applicazione**] | Le applicazioni supportate dalla [!UICONTROL Reporting Activity Manager] sono: <ul><li>Interfaccia utente di Analysis Workspace</li><li>Progetti pianificati in Workspace</li><li>Report Builder</li><li>Interfaccia utente di Builder: segmento, metriche calcolate, annotazioni, pubblico, ecc.</li><li>Chiamate API da 1.4 o 2.0 API</li><li>Avvisi intelligenti</li></ul> |
| [!UICONTROL **Complessità media**] | La complessità media delle richieste incluse nel progetto. <p>Non tutte le richieste richiedono la stessa quantità di tempo per essere elaborate. La complessità delle richieste può essere utile per avere un’idea generale sul tempo necessario per elaborarle.</p><p>Il valore di questa colonna si basa su un punteggio determinato dai valori delle colonne seguenti:</p><ul><li>[!UICONTROL **Limiti medi del mese**]</li><li>[!UICONTROL **Media colonne**]</li><li>[!UICONTROL **Segmenti medi**]</li></ul> |
| [!UICONTROL **Limiti medi del mese**] | Numero medio di mesi inclusi nelle richieste. L’aumento dei limiti di mese aggiunge complessità alla richiesta. |
| [!UICONTROL **Media colonne**] | Il numero medio di metriche e raggruppamenti nelle richieste incluse. Più colonne aumenta la complessità della richiesta. |
| [!UICONTROL **Segmenti medi**] | Numero medio di segmenti applicati alle richieste incluse. Altri segmenti aumentano la complessità della richiesta. |

{style="table-layout:auto"}

#### Visualizza dati per applicazione

Quando selezioni il [!UICONTROL **Applicazione**] nella tabella sono disponibili le seguenti colonne:

| Colonna | Descrizione |
| --- | --- |
| [!UICONTROL **Applicazione**] | L’applicazione in cui sono state avviate le query. |
| [!UICONTROL **Numero di richieste**] | Il numero di richieste associate all’applicazione. |
| [!UICONTROL **Numero di utenti**] | Il numero di utenti associati all’applicazione. <!--???--> |
| [!UICONTROL **Numero di progetti**] | Numero di progetti associati all&#39;applicazione. <!--???--> |
| [!UICONTROL **Complessità media**] | La complessità media delle richieste associate all’applicazione. <p>Non tutte le richieste richiedono la stessa quantità di tempo per essere elaborate. La complessità delle richieste può essere utile per avere un’idea generale sul tempo necessario per elaborarle.</p><p>Il valore di questa colonna si basa su un punteggio determinato dai valori delle colonne seguenti:</p>Il valore di questa colonna si basa su un punteggio determinato dai valori delle colonne seguenti:<ul><li>[!UICONTROL **Limiti medi del mese**]</li><li>[!UICONTROL **Media colonne**]</li><li>[!UICONTROL **Segmenti medi**]</li></ul> |
| [!UICONTROL **Limiti medi del mese**] | Numero medio di mesi inclusi nelle richieste. L’aumento dei limiti di mese aggiunge complessità alla richiesta. |
| [!UICONTROL **Media colonne**] | Il numero medio di metriche e raggruppamenti nelle richieste incluse. Più colonne aumenta la complessità della richiesta. |
| [!UICONTROL **Segmenti medi**] | Numero medio di segmenti applicati alle richieste incluse. Altri segmenti aumentano la complessità della richiesta. |

{style="table-layout:auto"}

<!--

### Filter

You can filter the table by Application (see list in the table below), by User, and by Project.

![filter](/help/admin/admin/assets/filter.png)

### Summary Numbers {#summary}

![filter](/help/admin/admin/assets/summary_numbers.png)

The Summary Numbers show the following information:

| Summary Number | Description |
| --- | --- |
| [!UICONTROL **Users**] | The number of users that are currently sending reporting requests to this connection. |
| [!UICONTROL **Projects**] | Workspace projects, Report Builder workbooks, etc.  | 
| [!UICONTROL **Queries**] | The number of queries currently running. |
| [!UICONTROL **Average Wait Time**] | The average wait time for all running queries.  |
| [!UICONTROL **Usage Capacity**] | The current usage capacity for this connection. |

{style="table-layout:auto"}

-->
