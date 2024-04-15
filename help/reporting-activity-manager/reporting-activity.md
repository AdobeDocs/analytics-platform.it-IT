---
title: Visualizzare l’attività di reporting in Reporting Activity Manager
description: Scopri come utilizzare il Reporting Activity Manager per diagnosticare e risolvere i problemi di capacità durante i periodi in cui si verificano picchi di reporting.
solution: Customer Journey Analytics
feature: Basics
exl-id: 1f5b2a42-162e-45a7-9fd4-8c1557f48bb8
role: Admin
source-git-commit: 4cb3c61a518b93119d8ffd503fc8653076ad56a1
workflow-type: tm+mt
source-wordcount: '1980'
ht-degree: 6%

---

# Visualizzare l’attività di reporting in Reporting Activity Manager

Il [!UICONTROL Reporting Activity Manager] consente agli amministratori di diagnosticare e risolvere rapidamente i problemi di capacità di reporting durante i periodi di picco.

Per ulteriori informazioni su Reporting Activity Manager, inclusi i vantaggi chiave e i requisiti delle autorizzazioni, vedere [Panoramica di Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md).

## Visualizza attività di reporting per tutte le connessioni {#view-all-report-suites}

1. In Customer Journey Analytics, vai a **[!UICONTROL Tools]** > **[!UICONTROL Reporting Activity Manager]**.

   Viene visualizzato un elenco delle connessioni di base abilitate.

   ![Attività di reporting che mostra la coda dei rapporti](assets/reporting-activity1.png)

1. Per visualizzare il numero totale di richieste di rapporti per tutte le connessioni nell’organizzazione, espandi [!UICONTROL **Mostra altro**] per visualizzare [!UICONTROL **Richieste di rapporti mensili**] grafico.

   Puoi visualizzare il numero di richieste di rapporti all’interno della tua organizzazione per il mese corrente e il mese precedente.

   ![Attività di reporting che mostra la coda dei rapporti](assets/reporting-activity-monthly.png)

1. (Facoltativo) Puoi cercare o filtrare l’elenco delle connessioni:

   * Utilizza il campo di ricerca per cercare una connessione specifica. Inizia a digitare il nome o l’ID della connessione e l’elenco degli aggiornamenti delle connessioni durante la digitazione.

   * Seleziona la [!UICONTROL **Filtro**] icona ![Icona Filtro](assets/filter-icon.png) per espandere l&#39;elenco delle opzioni di filtro. Puoi filtrare per [!UICONTROL **Preferiti**] o [!UICONTROL **Stato**].

     Per contrassegnare una connessione come preferita, seleziona l’icona a forma di stella a sinistra del nome della connessione.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Visualizza le informazioni sull&#39;utilizzo di ogni connessione. I dati mostrati nella tabella rappresentano l’attività di reporting per la connessione al momento dell’ultimo caricamento della pagina.

   Sono disponibili le seguenti colonne:

   | Elemento nell’interfaccia utente | Descrizione |
   | --- | --- |
   | **[!UICONTROL Connection]** | La connessione di cui si sta monitorando l’attività di reporting. |
   | **[!UICONTROL Data Views]** | Mostra tutte le visualizzazioni dati che utilizzano la connessione. La configurazione della visualizzazione dati può aggiungere complessità alle richieste di reporting. |
   | **[!UICONTROL Capacity utilization]** | Percentuale della capacità di reporting della connessione utilizzata, in tempo reale. <p>**Nota** Una capacità di utilizzo pari al 100% non indica necessariamente che è necessario iniziare immediatamente ad annullare le richieste di reporting. La capacità di utilizzo del 100% può essere integra se il tempo medio di attesa è ragionevole. D’altra parte, una capacità di utilizzo del 100% potrebbe indicare un problema se anche il numero di richieste in coda è in crescita.</p> |
   | **[!UICONTROL Queued requests]** | Numero di richieste in attesa di elaborazione. <!-- ??? --> |
   | **[!UICONTROL Queue wait time]** | Tempo medio di attesa prima dell’elaborazione delle richieste. <!-- ???? --> |
   | **[!UICONTROL Status]** | I possibili stati sono: <ul><li>[!UICONTROL **Attivo**] (blu): I rapporti sulla connessione sono stati eseguiti nelle ultime 2 ore. I dati mostrati nella tabella rappresentano la capacità di reporting per la connessione al momento dell’ultimo caricamento della pagina.</li><li>[!UICONTROL **Inattivo**] (grigio): non sono mai stati eseguiti rapporti sulla connessione nelle ultime 2 ore, pertanto non vengono visualizzati dati per la connessione.</li></ul> |

   {style="table-layout:auto"}

## Visualizzare l’attività di reporting per una singola connessione

1. In Customer Journey Analytics, seleziona [!UICONTROL **Strumenti**] > [!UICONTROL **Reporting Activity Manager**].

1. Selezionare il titolo collegato della connessione per la quale si desidera visualizzare i dettagli.

   I dati dell’attività di reporting vengono visualizzati per la connessione selezionata.

1. (Facoltativo) Quando una connessione viene caricata per la prima volta in Reporting Activity Manager, i dati visualizzati rappresentano le metriche di utilizzo correnti. Per visualizzare le metriche aggiornate dopo il caricamento iniziale, seleziona la [!UICONTROL **Aggiorna**] per aggiornare manualmente la pagina.

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

Il grafico Richieste mostra il numero di richieste elaborate e in coda per la connessione selezionata nelle ultime 2 ore.

Passa il cursore del mouse sul grafico per visualizzare i punti nel tempo in cui il numero massimo di richieste era più alto per quel minuto.

* **Asse X**: numero di richieste elaborate e in coda negli ultimi due ore.
* **Asse Y**: numero di richieste elaborate (in verde) e di richieste in coda (in viola), al minuto.

  ![Grafico Utenti distinti](assets/requests-graph.png)

#### Grafico in coda

Il grafico di accodamento mostra il tempo medio di attesa della coda (in secondi) per le richieste di reporting per la connessione selezionata nelle ultime 2 ore.

Passa il cursore del mouse sul grafico per visualizzare i punti nel tempo in cui il tempo medio di attesa massimo era più alto per quel minuto.

* **Asse X**: tempo medio di attesa della coda per le richieste di reporting nell’ultimo intervallo di tempo di 2 ore.
* **Asse Y**: tempo medio di attesa (in secondi).

  ![Grafico Utenti distinti](assets/queueing-graph.png)

### Visualizza tabella {#view-table}

Quando visualizzi la tabella, considera quanto segue:

* È possibile scegliere di visualizzare i dati scegliendo una delle seguenti schede nella parte superiore della tabella dati: [!UICONTROL **Richiesta**], [!UICONTROL **Utente**], [!UICONTROL **Progetto**], o [!UICONTROL **Applicazione**].

* Puoi cercare o filtrare l’elenco delle connessioni:

   * Utilizza il campo di ricerca per cercare una connessione specifica. Inizia a digitare il nome o l’ID della connessione e l’elenco degli aggiornamenti delle connessioni durante la digitazione.

   * Seleziona la [!UICONTROL **Filtro**] icona ![Icona Filtro](assets/filter-icon.png) per espandere l&#39;elenco delle opzioni di filtro. Puoi filtrare per [!UICONTROL **Stato**], [!UICONTROL **Complessi**], [!UICONTROL **Applicazione**], [!UICONTROL **Utente**], o [!UICONTROL **Progetto**].

   * Puoi selezionare [!UICONTROL **Nascondere i grafici**] per visualizzare solo la tabella.

![tabulazioni tabella](assets/report-activity-tabs.png)

#### Visualizza dati per richiesta

Quando selezioni il [!UICONTROL **Richiesta**] nella tabella sono disponibili le seguenti colonne:

| Colonna | Descrizione |
| --- | --- |
| [!UICONTROL **ID richiesta**] | ID univoco che può essere utilizzato a scopo di risoluzione dei problemi. Per copiare l’ID, seleziona la richiesta, quindi l’opzione, [!UICONTROL **Copia ID richiesta**]. |
| [!UICONTROL **Esecuzione temporale**] | Da quanto tempo la richiesta è in esecuzione. |
| [!UICONTROL **Ora di inizio**] | Quando la richiesta ha iniziato l’elaborazione (in base all’ora locale dell’amministratore). |
| [!UICONTROL **Tempo di attesa**] | Tempo di attesa della richiesta prima dell’elaborazione. Questo valore è generalmente a &quot;0&quot; quando la capacità è sufficiente. |
| [!UICONTROL **Applicazione**] | Le applicazioni supportate dalla [!UICONTROL Reporting Activity Manager] sono: <ul><li>Interfaccia utente di Analysis Workspace</li><li>Progetti pianificati in Workspace</li><li>Report Builder</li><li>Interfaccia utente di Builder: segmento, metriche calcolate, annotazioni, pubblico e così via.</li><li>Chiamate API dall&#39;API 2.0</li><li>Avvisi intelligenti<li>Esportazione tabella completa</li><li>Condividi con qualsiasi collegamento</li><li>Analisi guidata</li><li>Qualsiasi altra applicazione che esegue query sul motore di reporting di Analytics</li></li></ul><p>**Nota:** Se il valore di questa colonna è [!UICONTROL **Sconosciuto**], significa che i metadati della richiesta non sono disponibili per l’utente.</p> |
| [!UICONTROL **Utente**] | Utente che ha avviato la richiesta. <p>**Nota:** Se il valore di questa colonna è [!UICONTROL **Sconosciuto**], significa che i metadati della richiesta non sono disponibili per l’utente.</p> |
| [!UICONTROL **Progetto**] | Nomi di progetto Workspace salvati, ID di report API e così via. (I metadati possono variare tra le varie applicazioni).<p>**Nota:** Se il valore di questa colonna è [!UICONTROL **Sconosciuto**], significa che il progetto non è stato salvato o che i metadati della richiesta non sono disponibili per l’utente.</p> |
| [!UICONTROL **Stato**] | Indicatori di stato: <ul><li>**In esecuzione**: richiesta in fase di elaborazione.</li><li>**In sospeso**: richiesta in attesa di elaborazione.</li></ul> |
| [!UICONTROL **Complessi**] | Non tutte le richieste richiedono la stessa quantità di tempo per essere elaborate. La complessità delle richieste può essere utile per avere un’idea generale sul tempo necessario per elaborarle. <p>Possibili valori:</p> <ul><li>[!UICONTROL **Basso**]</li><li>[!UICONTROL **Medio**]</li><li>[!UICONTROL **Alta**]</li></ul>Questo valore è influenzato dai valori delle colonne seguenti:<ul><li>[!UICONTROL **Limiti del mese**]</li><li>[!UICONTROL **Colonne**]</li><li>[!UICONTROL **Segmenti**]</li></ul> |
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
| [!UICONTROL **Applicazione**] | Le applicazioni supportate dalla [!UICONTROL Reporting Activity Manager] sono: <ul><li>Interfaccia utente di Analysis Workspace</li><li>Progetti pianificati in Workspace</li><li>Report Builder</li><li>Interfaccia utente di Builder: segmento, metriche calcolate, annotazioni, pubblico e così via.</li><li>Chiamate API dall&#39;API 2.0</li><li>Avvisi intelligenti<li>Esportazione tabella completa</li><li>Condividi con qualsiasi collegamento</li><li>Analisi guidata</li><li>Qualsiasi altra applicazione che esegue query sul motore di reporting di Analytics</li></li></ul> |
| [!UICONTROL **Complessità media**] | La complessità media delle richieste avviate dall’utente. <p>Non tutte le richieste richiedono la stessa quantità di tempo per essere elaborate. La complessità delle richieste può essere utile per avere un’idea generale sul tempo necessario per elaborarle.</p><p>Il valore di questa colonna si basa su un punteggio determinato dai valori delle colonne seguenti:</p><ul><li>[!UICONTROL **Limiti medi del mese**]</li><li>[!UICONTROL **Media colonne**]</li><li>[!UICONTROL **Segmenti medi**]</li></ul> |
| [!UICONTROL **Limiti medi del mese**] | Numero medio di mesi inclusi nelle richieste. L’aumento dei limiti di mese aggiunge complessità alla richiesta. |
| [!UICONTROL **Media colonne**] | Il numero medio di metriche e raggruppamenti nelle richieste incluse. Più colonne aumenta la complessità della richiesta. |
| [!UICONTROL **Segmenti medi**] | Numero medio di segmenti applicati alle richieste incluse. Altri segmenti aumentano la complessità della richiesta. |

{style="table-layout:auto"}

#### Visualizza dati per progetto

Quando selezioni il [!UICONTROL **Progetto**] nella tabella sono disponibili le seguenti colonne:

| Colonna | Descrizione |
| --- | --- |
| [!UICONTROL **Progetto**] | Progetto in cui sono state avviate le richieste. |
| [!UICONTROL **Numero di richieste**] | Il numero di richieste associate al progetto. |
| [!UICONTROL **Numero di utenti**] | Il numero di utenti associati al progetto. <!-- ??? --> |
| [!UICONTROL **Applicazione**] | Le applicazioni supportate dalla [!UICONTROL Reporting Activity Manager] sono: <ul><li>Interfaccia utente di Analysis Workspace</li><li>Progetti pianificati in Workspace</li><li>Report Builder</li><li>Interfaccia utente di Builder: segmento, metriche calcolate, annotazioni, pubblico e così via.</li><li>Chiamate API dall&#39;API 2.0</li><li>Avvisi intelligenti<li>Esportazione tabella completa</li><li>Condividi con qualsiasi collegamento</li><li>Analisi guidata</li><li>Qualsiasi altra applicazione che esegue query sul motore di reporting di Analytics</li></li></ul> |
| [!UICONTROL **Complessità media**] | La complessità media delle richieste incluse nel progetto. <p>Non tutte le richieste richiedono la stessa quantità di tempo per essere elaborate. La complessità delle richieste può essere utile per avere un’idea generale sul tempo necessario per elaborarle.</p><p>Il valore di questa colonna si basa su un punteggio determinato dai valori delle colonne seguenti:</p><ul><li>[!UICONTROL **Limiti medi del mese**]</li><li>[!UICONTROL **Media colonne**]</li><li>[!UICONTROL **Segmenti medi**]</li></ul> |
| [!UICONTROL **Limiti medi del mese**] | Numero medio di mesi inclusi nelle richieste. L’aumento dei limiti di mese aggiunge complessità alla richiesta. |
| [!UICONTROL **Media colonne**] | Il numero medio di metriche e raggruppamenti nelle richieste incluse. Più colonne aumenta la complessità della richiesta. |
| [!UICONTROL **Segmenti medi**] | Numero medio di segmenti applicati alle richieste incluse. Altri segmenti aumentano la complessità della richiesta. |

{style="table-layout:auto"}

#### Visualizza dati per applicazione

Quando selezioni il [!UICONTROL **Applicazione**] nella tabella sono disponibili le seguenti colonne:

| Colonna | Descrizione |
| --- | --- |
| [!UICONTROL **Applicazione**] | L’applicazione in cui sono state avviate le richieste. |
| [!UICONTROL **Numero di richieste**] | Il numero di richieste associate all’applicazione. |
| [!UICONTROL **Numero di utenti**] | Il numero di utenti associati all’applicazione. <!--???--> |
| [!UICONTROL **Numero di progetti**] | Numero di progetti associati all&#39;applicazione. <!--???--> |
| [!UICONTROL **Complessità media**] | La complessità media delle richieste associate all’applicazione. <p>Non tutte le richieste richiedono la stessa quantità di tempo per essere elaborate. La complessità delle richieste può essere utile per avere un’idea generale sul tempo necessario per elaborarle.</p><p>Il valore di questa colonna si basa su un punteggio determinato dai valori delle colonne seguenti:</p>Il valore di questa colonna si basa su un punteggio determinato dai valori delle colonne seguenti:<ul><li>[!UICONTROL **Limiti medi del mese**]</li><li>[!UICONTROL **Media colonne**]</li><li>[!UICONTROL **Segmenti medi**]</li></ul> |
| [!UICONTROL **Limiti medi del mese**] | Numero medio di mesi inclusi nelle richieste. L’aumento dei limiti di mese aggiunge complessità alla richiesta. |
| [!UICONTROL **Media colonne**] | Il numero medio di metriche e raggruppamenti nelle richieste incluse. Più colonne aumenta la complessità della richiesta. |
| [!UICONTROL **Segmenti medi**] | Numero medio di segmenti applicati alle richieste incluse. Altri segmenti aumentano la complessità della richiesta. |

{style="table-layout:auto"}

<!-- 

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
| | |

{style="table-layout:auto"}

-->
