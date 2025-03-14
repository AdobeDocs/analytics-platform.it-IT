---
title: Estensione Customer Journey Analytics BI
description: Scopri come utilizzare Power BI o Tableau Desktop per accedere alle visualizzazioni dati utilizzando l’estensione Customer Journey Analytics BI.
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: 2f9cfc3fc7edaa21175d44dfb3f9bface5cf0d81
workflow-type: tm+mt
source-wordcount: '3188'
ht-degree: 2%

---

# Estensione Customer Journey Analytics BI

{{select-package}}

[!DNL Customer Journey Analytics BI extension] abilita l&#39;accesso SQL alle [visualizzazioni dati](./data-views.md) definite in Customer Journey Analytics. I data engineer e gli analisti potrebbero avere più familiarità con Power BI, Tableau Desktop o altri strumenti di business intelligence e visualizzazione (denominati anche strumenti BI). Ora possono creare reporting e dashboard basati sulle stesse visualizzazioni dati utilizzate dagli utenti di Customer Journey Analytics durante la creazione dei loro progetti Analysis Workspace.

Adobe Experience Platform [Query Service](https://experienceleague.adobe.com/it/docs/experience-platform/query/home) è l&#39;interfaccia SQL per i dati disponibili nel data lake di Experience Platform. Con [!DNL Customer Journey Analytics BI extension] abilitato, la funzionalità di [!DNL Query Service] viene estesa per visualizzare le visualizzazioni dati di Customer Journey Analytics come tabelle o visualizzazioni in una sessione di [!DNL Query Service]. Di conseguenza, gli strumenti di business intelligence che utilizzano [!DNL Query Service] come interfaccia PostgresSQL usufruiscono senza soluzione di continuità di questa funzionalità estesa.

I principali vantaggi sono i seguenti:

* Non è necessario ricreare una rappresentazione equivalente delle visualizzazioni dati di Customer Journey Analytics all’interno dello strumento BI stesso. <br/>Consulta [Visualizzazioni dati](data-views.md) per ulteriori informazioni sulla funzionalità delle visualizzazioni dati per capire cosa deve essere ricreato.
* Maggiore coerenza nelle attività di reporting e analisi tra gli strumenti di business intelligence e Customer Journey Analytics.
* Combinare i dati di Customer Journey Analytics con altre origini dati già disponibili negli strumenti BI.

## Prerequisiti

Per utilizzare questa funzionalità, è possibile utilizzare credenziali in scadenza o non in scadenza per connettere gli strumenti BI a [!DNL Customer Journey Analytics BI extension]. La [Guida alle credenziali](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials) fornisce ulteriori informazioni sull&#39;impostazione di credenziali in scadenza o non in scadenza.
Di seguito sono riportati i passaggi aggiuntivi per impostare le autorizzazioni di CJA
<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

### Credenziali in scadenza

Per utilizzare le credenziali in scadenza, è possibile:

* Concedere l’accesso ad Experience Platform e Customer Journey Analytics.
* Concedi all’amministratore del prodotto l’accesso a Customer Journey Analytics per visualizzare, modificare, aggiornare o eliminare connessioni e visualizzazioni dati.

Oppure puoi:

* Concedi l’accesso alle visualizzazioni dati a cui desideri accedere.
* Concedere l’accesso all’estensione Customer Journey Analytics BI.

### Credenziali non in scadenza

Per utilizzare credenziali senza scadenza:

* Crea credenziali senza scadenza in Experience Platform.
* Concedi l&#39;accesso alle credenziali senza scadenza seguendo i passaggi indicati in [Credenziali in scadenza](#Expiring-credentials).

Consulta [Controllo dell&#39;accesso del Percorso clienti](../technotes/access-control.md) per ulteriori informazioni, in particolare [Autorizzazioni aggiuntive per l&#39;amministratore del prodotto](../technotes/access-control.md#product-admin-additional-permissions) e [Autorizzazioni Customer Journey Analytics in Admin Console](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console).


## Utilizzo

Per utilizzare la funzionalità [!DNL Customer Journey Analytics BI extension], è possibile utilizzare direttamente SQL o utilizzare l&#39;esperienza di trascinamento disponibile nello strumento BI specifico.

### SQL

È possibile utilizzare la funzionalità direttamente nelle istruzioni SQL utilizzando Query Editor o un client CLI (Command Line Interface) PostgresSQL standard.

+++ Editor query

In Adobe Experience Platform:

1. Seleziona **[!UICONTROL ** Query **]** da **[!UICONTROL ** GESTIONE DATI **]** nella barra a sinistra.

1. Selezionare ![Crea query](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Crea query **]**.

1. Selezionare il database `cja` per la sandbox dall&#39;elenco dei database nel menu a discesa **[!UICONTROL Database]**. Ad esempio `prod:cja`.

1. Per eseguire la query, digitare l&#39;istruzione SQL e selezionare il pulsante ![Esegui](assets/Smock_Play_18_N.svg) (oppure premere `[SHIFT]` + `[ENTER]`).

+++


+++ CLI PostgresSQL

1. Cercare e copiare le credenziali PostgresSQL in Adobe Experience Platform:

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (in **[!UICONTROL ** GESTIONE DATI **]**).

   1. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   1. Selezionare il database `cja` per la sandbox dall&#39;elenco dei database nel menu a discesa **[!UICONTROL Database]**. Ad esempio `prod:cja`.

   1. Per copiare la stringa di comando, utilizzare ![Copia](assets/Smock_Copy_18_N.svg) nella sezione **[!UICONTROL ** Comando PSQL **]**.

1. Aprire una finestra di comando o terminale.

1. Per accedere e avviare l’esecuzione delle query, incolla la stringa di comando nel terminale.

+++

Per ulteriori informazioni, vedere la [Guida dell&#39;interfaccia utente di Query Editor](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/user-guide).


### Strumenti BI

Attualmente, [!DNL Customer Journey Analytics BI extension] è supportato e testato per gli strumenti elencati di seguito. Anche altri strumenti di business intelligence che utilizzano l&#39;interfaccia PSQL potrebbero funzionare, ma non sono ancora ufficialmente supportati.

+++ Power BI

1. Cercare i dettagli delle credenziali PostgresSQL in Adobe Experience Platform:

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (in **[!UICONTROL ** GESTIONE DATI **]**).

   1. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   1. Selezionare il database `cja` per la sandbox dall&#39;elenco dei database nel menu a discesa **[!UICONTROL Database]**. Ad esempio `prod:cja`.

   1. Utilizza ![Copia](assets/Smock_Copy_18_N.svg) per copiare ciascuno dei parametri delle credenziali Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username] e altri) quando necessario in Power BI.

1. In Power BI:

   1. Nella finestra principale, seleziona **[!UICONTROL ** Ottieni dati **]** dalla barra degli strumenti superiore.

   1. Seleziona **[!UICONTROL More...]** (Elementi dati) nella barra a sinistra.

   1. Nella schermata **Ottieni dati**, cercare `PostgresSQL` e selezionare il database **[!UICONTROL ** PostgresSQL **]** dall&#39;elenco.

   1. Nella finestra di dialogo **[!UICONTROL ** Database PostgressSQL **]**:

      1. Incolla il parametro **[!UICONTROL ** Host **]** dalle query Experience Platform [!UICONTROL Credentials] nel campo di testo **[!UICONTROL ** Server **]**.

      1. Incolla il parametro **[!UICONTROL ** Database **]** dalle query Experience Platform [!UICONTROL Credentials] nel campo di testo **[!UICONTROL ** Database **]**.

         Aggiungere `?FLATTEN` al parametro **[!UICONTROL ** Database **]**, ad esempio `prod:cja?FLATTEN`. Per ulteriori informazioni, vedere [Flatten nested data structures per l&#39;utilizzo con strumenti BI di terze parti](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data).

      1. Quando viene richiesta la modalità **[!UICONTROL Data Connectivity]**, selezionare **[!UICONTROL DirectQuery]**.

      1. Viene richiesto di **[!UICONTROL Username]** e **[!UICONTROL Password]**. Utilizzare i parametri equivalenti dalle query Experience Platform [!UICONTROL Credentials].


   1. Dopo aver eseguito correttamente l&#39;accesso, le tabelle delle visualizzazioni dati di Customer Journey Analytics vengono visualizzate in Power BI **[!UICONTROL ** Navigator **]**.

   1. Selezionare le tabelle di visualizzazione dati che si desidera utilizzare e selezionare **[!UICONTROL ** Carica **]**.

   Tutte le dimensioni e le metriche associate a una o più tabelle selezionate vengono visualizzate nel riquadro di destra, pronte per essere utilizzate nelle visualizzazioni.

   Per ulteriori informazioni, vedere [Connessione di Power BI a Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi). Vedi anche [casi d&#39;uso dell&#39;estensione BI](/help/use-cases/data-views/bi-extension-usecases.md) per un esempio dettagliato.

+++

+++Desktop Tableau

1. Cercare i dettagli delle credenziali PostgresSQL in Adobe Experience Platform:

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (in **[!UICONTROL ** GESTIONE DATI **]**).

   1. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   1. Selezionare il database `cja` per la sandbox dall&#39;elenco dei database nel menu a discesa **[!UICONTROL Database]**. Ad esempio `prod:cja`.

   1. Utilizza ![Copia](assets/Smock_Copy_18_N.svg) per copiare ciascuno dei parametri delle credenziali Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username] e altri) quando necessario in Tableau Desktop.

1. In Tableau Desktop:

   1. Seleziona **[!UICONTROL ** Altro **]** da **[!UICONTROL ** A un server **]** nella barra a sinistra.

   1. Selezionare **[!UICONTROL ** PostgresSQL **]** dall&#39;elenco.

   1. Nella finestra di dialogo [!UICONTROL PostgresSQL] (Crea elemento dati):

      1. Incolla il parametro **[!UICONTROL ** Host **]** dalle query Experience Platform [!UICONTROL Credentials] nel campo di testo **[!UICONTROL ** Server **]**.

      1. Incolla il parametro **[!UICONTROL ** Porta **]** dalle query Experience Platform [!UICONTROL Credentials] nel campo di testo **[!UICONTROL ** Porta **]**.

      1. Incollare il parametro **[!UICONTROL ** Database **]** dalle query Experience Platform [!UICONTROL Credentials] nel campo di testo **[!UICONTROL ** Database **]**.

         Aggiungere `%3FFLATTEN` al parametro **[!UICONTROL ** Database **]**, ad esempio `prod:cja%3FFLATTEN`. Per ulteriori informazioni, vedere [Flatten nested data structures per l&#39;utilizzo con strumenti BI di terze parti](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data).

      1. Selezionare **[!UICONTROL ** Nome utente e password **]** dall&#39;elenco **[!UICONTROL ** Autenticazione **]**.

      1. Incolla il parametro **[!UICONTROL ** Username **]** dalle query Experience Platform [!UICONTROL Credentials] nel campo di testo **[!UICONTROL ** Username **]**.

      1. Incolla il parametro **[!UICONTROL ** Password **]** dalle query Experience Platform [!UICONTROL Credentials] nel campo di testo **[!UICONTROL ** Password **]**.

      1. Seleziona **[!UICONTROL ** Accedi **]**.

   1. Le visualizzazioni dati di Customer Journey Analytics vengono visualizzate come tabelle nell&#39;elenco **[!UICONTROL ** Tabella **]**.

   1. Trascinare le tabelle che si desidera utilizzare nell&#39;area di lavoro.

   Ora puoi lavorare con i dati delle tabelle delle visualizzazioni dati per creare rapporti e visualizzazioni.

   Per ulteriori informazioni, vedere [Connetti Tableau a Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau). Vedi anche [casi d&#39;uso dell&#39;estensione BI](/help/use-cases/data-views/bi-extension-usecases.md) per un esempio dettagliato.

+++

+++ Looker

1. Cercare i dettagli delle credenziali PostgresSQL in Adobe Experience Platform:

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (in **[!UICONTROL ** GESTIONE DATI **]**).

   1. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   1. Selezionare il database `cja` per la sandbox dall&#39;elenco dei database nel menu a discesa **[!UICONTROL Database]**. Ad esempio `prod:cja`.

   1. Utilizza ![Copia](assets/Smock_Copy_18_N.svg) per copiare ciascuno dei parametri delle credenziali Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username] e altri) quando necessario in Looker.

1. In Looker:

   1. Seleziona **[!UICONTROL Admin]** nella barra a sinistra.
   1. Seleziona **[!UICONTROL Connections]**.
   1. Seleziona **[!UICONTROL Add Connection]** (Salva).
   1. Nella schermata **[!UICONTROL Connect your database to Looker]**, incolla i valori appropriati quando configuri la nuova connessione. Assicurarsi di selezionare **[!UICONTROL PostgreSQL 9.5+]** come dialetto.
   1. Seleziona **[!UICONTROL Test]** per verificare la connessione.
   1. Dopo aver eseguito correttamente l&#39;operazione, selezionare **[!UICONTROL Update]** per salvare la connessione.

   Ora puoi lavorare con i dati delle tabelle delle visualizzazioni dati per creare rapporti e visualizzazioni.

   Per ulteriori informazioni, vedere [Connessione di Looker a Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/looker). Vedi anche [casi d&#39;uso dell&#39;estensione BI](/help/use-cases/data-views/bi-extension-usecases.md) per un esempio dettagliato.

+++

+++ Jupyter Notebook

1. Cercare i dettagli delle credenziali PostgresSQL in Adobe Experience Platform:

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (in **[!UICONTROL ** GESTIONE DATI **]**).

   1. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   1. Selezionare il database `cja` per la sandbox dall&#39;elenco dei database nel menu a discesa **[!UICONTROL Database]**. Ad esempio `prod:cja`.

   1. Utilizza ![Copia](assets/Smock_Copy_18_N.svg) per copiare ciascuno dei parametri delle credenziali Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username] e altri) quando necessario in Jupyter Notebook.

1. In Jupyter Notebook:

   1. Assicurati di utilizzare le librerie richieste.
   1. Utilizza i valori appropriati durante la configurazione e l’esecuzione della connessione.
   1. Verifica la connessione eseguendo una query rilevante.

   In caso di esito positivo, puoi lavorare con i dati per creare rapporti e visualizzazioni.

   Per ulteriori informazioni, vedere [Connettere Jupyter Notebook a Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/jupyter-notebook). Vedi anche [casi d&#39;uso dell&#39;estensione BI](/help/use-cases/data-views/bi-extension-usecases.md) per un esempio dettagliato.

+++

+++ Studio

1. Cercare i dettagli delle credenziali PostgresSQL in Adobe Experience Platform:

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (in **[!UICONTROL ** GESTIONE DATI **]**).

   1. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   1. Selezionare il database `cja` per la sandbox dall&#39;elenco dei database nel menu a discesa **[!UICONTROL Database]**. Ad esempio `prod:cja`.

   1. Utilizza ![Copia](assets/Smock_Copy_18_N.svg) per copiare ciascuno dei parametri delle credenziali Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username] e altri) quando necessario in Jupyter Notebook.

1. In Studio:

   1. Assicurati di utilizzare le librerie richieste.
   1. Utilizza i valori appropriati durante la configurazione e l’esecuzione della connessione.
   1. Verifica la connessione eseguendo una query rilevante.

   In caso di esito positivo, puoi lavorare con i dati per creare rapporti e visualizzazioni.

   Per ulteriori informazioni, vedere [Connetti RSudio a Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/rstudio). Vedi anche [casi d&#39;uso per estensioni BI](/help/use-cases/data-views/bi-extension-usecases.md) per un esempio dettagliato (che utilizza invece il pacchetto RPostgres).

+++

Per una panoramica e ulteriori informazioni sui vari strumenti disponibili, vedere [Connettere i client a Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview).

Consulta [Casi d&#39;uso](/help/use-cases/data-views/bi-extension-usecases.md) su come eseguire una serie di casi d&#39;uso utilizzando l&#39;estensione Customer Journey Analytics BI.

## Funzionalità

Per impostazione predefinita, le visualizzazioni dati hanno un nome sicuro per la tabella generato dal loro nome descrittivo. Ad esempio, la visualizzazione dati denominata [!UICONTROL My Web Data View] ha il nome `my_web_data_view`. È possibile definire un nome da utilizzare nello strumento BI per la visualizzazione dati. Per ulteriori informazioni, vedere [Impostazioni visualizzazione dati](create-dataview.md#settings).

Se si desidera utilizzare gli ID delle visualizzazioni dati come nomi di tabella, è possibile aggiungere l&#39;impostazione facoltativa `CJA_USE_IDS` al nome del database durante la connessione. Ad esempio, `prod:cja?CJA_USE_IDS` mostra le tue visualizzazioni dati con nomi come `dv_ABC123`.

### Governance dei dati

Le impostazioni relative alla governance dei dati in Customer Journey Analytics vengono ereditate da Adobe Experience Platform. L’integrazione tra Customer Journey Analytics e Governance dei dati di Adobe Experience Platform consente l’etichettatura dei dati Customer Journey Analytics sensibili e l’applicazione delle politiche sulla privacy.

Le etichette per la privacy e i criteri creati sui set di dati utilizzati da Experience Platform possono essere visualizzati nel flusso di lavoro delle visualizzazioni dati di Customer Journey Analytics. Pertanto, i dati interrogati utilizzando [!DNL Customer Journey Analytics BI extension] mostrano avvertenze o errori appropriati quando non sono conformi alle etichette e ai criteri definiti per la privacy.

### Visualizzazioni dati elenco

Nella CLI PostgreSQL standard è possibile elencare le visualizzazioni utilizzando `\dv`

```sql
prod:all=> \dv
                       List of relations
 Schema |                    Name                    | Type |  Owner             
--------+--------------------------------------------+------+----------
 public | my_web_data_view                           | view | postgres
 public | my_mobile_data_view                        | view | postgres
```

### Nidificato e appiattito

Per impostazione predefinita, lo schema delle visualizzazioni dati utilizza strutture nidificate, proprio come gli schemi XDM originali. L&#39;integrazione supporta anche l&#39;opzione `FLATTEN`. È possibile utilizzare questa opzione per forzare l’appiattimento dello schema per le visualizzazioni dati (e qualsiasi altra tabella nella sessione). L’appiattimento consente un utilizzo più semplice negli strumenti di business intelligence che non supportano schemi strutturati. Per ulteriori informazioni, vedere [Utilizzo delle strutture di dati nidificate in Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data).


### Valori predefiniti e limitazioni

Quando si utilizza l’estensione BI, vengono applicati i seguenti valori predefiniti e limitazioni aggiuntivi:

* L&#39;estensione BI richiede un limite di righe per i risultati della query. Il valore predefinito è 50, ma è possibile eseguire l&#39;override in SQL utilizzando `LIMIT n`, dove `n` è 1 - 50000.
* L’estensione BI richiede un intervallo di date per limitare le righe utilizzate per i calcoli. L&#39;impostazione predefinita corrisponde agli ultimi 30 giorni, ma è possibile ignorarla nella clausola SQL `WHERE` utilizzando le colonne speciali [`timestamp`](#timestamp) o [`daterange`](#date-range).
* L&#39;estensione BI richiede query di aggregazione. Impossibile utilizzare SQL come `SELECT * FROM ...` per ottenere le righe sottostanti non elaborate. A un livello avanzato, le query aggregate devono utilizzare:
   * Selezionare i totali utilizzando `SUM` e/o `COUNT`.<br/> Ad esempio, `SELECT SUM(metric1), COUNT(*) FROM ...`
   * Seleziona le metriche suddivise per dimensione. <br/>Ad esempio, `SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * Seleziona valori di metrica distinti.<br/>Ad esempio, `SELECT DISTINCT dimension1 FROM ...`

     Per ulteriori dettagli, vedere [SQL supportato](#supported-sql).


### SQL supportato

Per il riferimento completo al tipo di SQL supportato, vedere [Riferimento SQL servizio query](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/overview).

Per esempi delle istruzioni SQL utilizzabili, vedere la tabella seguente.

+++ Esempi

<table style="table-layout:auto">
    <thead>
        <tr>
            <th>Pattern</th>
            <th>Esempio</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Individuazione schema </td>
            <td>
                <pre><code>SELECT * FROM dv1 WHERE 1=0</code></pre>
            </td>
        </tr>
        <tr>
            <td>Classificazione o raggruppamento </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  filterId = '12345'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  AND (dim2 = 'A' OR dim3 IN ('X', 'Y', 'Z'))
GROUP BY dim1</code></pre>
            </td>
        </tr>
        <tr>
            <td><code>HAVING</code> clausola </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1
HAVING m1 > 100</code></pre>
            </td>
        </tr>
        <tr>
            <td>Distinct, top 
valori di dimensione </td>
            <td>
                <pre><code>SELECT DISTINCT dim1 FROM dv1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` >= '2022-01-01' AND `timestamp` < '2022-01-02'
GROUP BY dim1
ORDER BY SUM(metric1)
LIMIT 15</code></pre>
            </td>
        </tr>
        <tr>
            <td>Totali delle metriche </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</code></pre>
            </td>
        </tr>
        <tr>
            <td>Multidimensionale
raggruppamenti
e top-distinct </td>
            <td>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1, dim2</code></pre>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 1, 2
ORDER BY 1, 2</code></pre>
                <pre><code>SELECT DISTINCT dim1, dim2
FROM dv1</code></pre>
            </td>
        </tr>
        <tr>
            <td>Sottoseleziona:
Filtra informazioni aggiuntive
risultati </td>
            <td>
                <pre><code>SELECT dim1, m1
FROM (
  SELECT dim1, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</br>  RAGGRUPPA PER dim1
)
WHERE dim1 in ('A', 'B')</code></pre>
            </td>
        </tr>
        <tr>
            <td>Sottoseleziona:
Query tra
visualizzazioni dati </td>
            <td>
                <pre><code>SELECT key, SUM(m1) AS total
FROM (
  SELECT dim1 AS key, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim1
<br>
  UNION
<br>
  SELECT dim2 AS key, SUM(m1) AS m1
  FROM dv2
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim2
)
GROUP BY key
ORDER BY total</code></pre>
            </td>
        </tr>
        <tr>
            <td>Sottoseleziona: 
Origine con livelli, 
filtraggio, 
e aggregazione </td>
            <td>Livellato con sottoselezioni:
<pre><code>SELECT rows.dim1, SUM(rows.m1) AS total
FROM (
  SELECT _.dim1,_.m1
  FROM (
    SELECT * FROM dv1
    WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  ) _
  WHERE _.dim1 in ('A', 'B', 'C')
) rows
GROUP BY 1
ORDER BY total</code></pre>
Livelli che utilizzano CTE CON:
<pre><code>WITH rows AS (
  WITH _ AS (
    SELECT * FROM data_ares
    WHERE `timestamp` BETWEEN '2021-01-01' AND '2021-02-01'
  )
  SELECT _.item, _.units FROM _
  WHERE _.item IS NOT NULL
)
SELECT rows.item, SUM(rows.units) AS units
FROM rows WHERE rows.item in ('A', 'B', 'C')
GROUP BY rows.item</code></pre>
        </td>
        </tr>
        <tr>
            <td>Seleziona dove
le metriche vengono prima
 o sono miscelati con
le dimensioni </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1, dim1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 2</code></pre>
            </td>
        </tr>
    </tbody>
</table>

+++

### Dimensioni

Puoi selezionare una qualsiasi delle dimensioni disponibili per impostazione predefinita o definite nella visualizzazione dati. Puoi selezionare una dimensione in base al relativo ID.

### Metriche

Le metriche disponibili per la selezione sono:

* Una qualsiasi delle metriche disponibili per impostazione predefinita;
* Definito nella visualizzazione dati;
* Metriche calcolate compatibili con la visualizzazione dati a cui l’utente ha accesso.

È possibile selezionare una metrica in base al relativo ID racchiuso in un&#39;espressione `SUM(metric)` come si farebbe con altre origini SQL.

Puoi utilizzare:

* `SELECT COUNT(*)` o `COUNT(1)` per ottenere la metrica delle occorrenze.
* `SELECT COUNT(DISTINCT dimension)` o `SELECT APPROX_COUNT_DISTINCT(dimension)` per contare i valori distinti approssimativi di una dimensione. Vedi i dettagli in [Conteggio valori distinti](#counting-distinct-values).
* [Calcoli in linea](#inline-calculations) per combinare al volo le metriche e/o eseguire calcoli matematici.

#### Conteggio dei valori distinti

A causa della natura sottostante del funzionamento di Customer Journey Analytics, l&#39;unica dimensione per la quale è possibile ottenere un conteggio distinto esatto è la dimensione `adobe_personid`. Le istruzioni SQL seguenti `SELECT COUNT(DISTINCT adobe_personid)` o `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` restituiscono il valore della metrica persone predefinita, che corrisponde al numero di persone distinte. Per le altre quote, viene restituito un conteggio distinto approssimativo.

#### Metriche condizionali

È possibile incorporare una clausola `IF` o `CASE` nelle funzioni `SUM` o `COUNT` per aggiungere un filtro aggiuntivo specifico per una metrica selezionata. L’aggiunta di queste clausole è simile all’applicazione di un filtro a una colonna di metriche in una tabella di rapporti di Workspace.

Esempi:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### Calcoli in linea

È possibile applicare calcoli aggiuntivi alle espressioni metriche in `SELECT`. Puoi usare questa matematica invece di definirla in una metrica calcolata. Nella tabella seguente sono elencati i tipi di espressioni supportati.

| Operatore o funzione | Dettagli |
|---|---|
| `+`, `-`, `*`, `/` e `%` | Aggiungere, sottrarre, moltiplicare, dividere e modulare/rimanente |
| `-X` o `+X` | Modifica del segno o di una metrica in cui X è l’espressione della metrica |
| `PI()` | Costante di |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH` e `TANH` | Funzioni matematiche unarie |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Funzioni matematiche binarie |

{style="table-layout:auto"}

### Colonne speciali

#### Marca temporale

La colonna speciale `timestamp` viene utilizzata per fornire gli intervalli di date per la query. È possibile definire un intervallo di date con un&#39;espressione `BETWEEN` o una coppia di `timestamp` `>`, `>=`, `<`, `<=` controlla `AND` insieme.
`timestamp` è facoltativo e se non viene fornito un intervallo completo, vengono utilizzati i valori predefiniti:

* Se viene specificato solo un minimo (`timestamp > X` o ` timestamp >= X`), l&#39;intervallo è compreso tra X e ora.
* Se viene fornito solo un massimo (`timestamp < X` o `timestamp <= X`), l&#39;intervallo è compreso tra X meno 30 giorni e X.
* Se non viene fornito nulla, l’intervallo è da ora meno 30 giorni a ora.

L’intervallo di marca temporale viene convertito in un filtro globale per intervalli di date in RankedRequest.
Il campo timestamp può essere utilizzato anche nelle funzioni data/ora per analizzare o troncare la marca temporale dell’evento.

#### Intervallo date

La colonna speciale `daterange` funziona in modo simile a `timestamp`, tuttavia il filtro è limitato a giorni interi. Anche `daterange` è facoltativo e ha gli stessi valori predefiniti di intervallo di `timestamp`.
Il campo `daterange` può essere utilizzato anche nelle funzioni data/ora per analizzare o troncare la data evento.

La colonna speciale `daterangeName` può essere utilizzata per filtrare la query utilizzando un intervallo di date denominato come `Last Quarter`.

>[!NOTE]
>
>Power BI non supporta `daterange` metriche inferiori a un giorno (ore, 30 minuti, 5 minuti, ecc.).
>

#### ID filtro

La colonna speciale `filterId` è facoltativa e viene utilizzata per applicare un filtro definito esternamente alla query. L’applicazione di un filtro definito esternamente a una query è simile al trascinamento di un filtro su un pannello in Workspace. È possibile utilizzare più ID di filtro inviandoli a `AND`.

Insieme a `filterId`, è possibile utilizzare `filterName` per utilizzare il nome di un filtro invece dell&#39;ID.

### Clausola Where

La clausola `WHERE` viene gestita in tre passaggi:

1. Trovare l&#39;intervallo di date dai campi speciali `timestamp`, `daterange` o `daterangeName`.

1. Trova qualsiasi `filterId` o `filterName` definito esternamente da includere nel filtro.

1. Trasforma le espressioni rimanenti in filtri ad hoc.

La gestione viene eseguita analizzando il primo livello di `AND` nella clausola `WHERE`. Ogni espressione di primo livello `AND` deve corrispondere a una delle precedenti. Qualsiasi elemento più profondo del primo livello di `AND` o, se la clausola `WHERE` utilizza `OR` al livello superiore, viene gestito come filtro ad hoc.

### Ordinamento

Per impostazione predefinita, la query ordina i risultati in base alla prima metrica selezionata in ordine decrescente. È possibile sovrascrivere l&#39;ordinamento predefinito specificando `ORDER BY ... ASC` o `ORDER BY ... DESC`. Se utilizzi `ORDER BY`, devi specificare `ORDER BY` sulla prima metrica selezionata.

È inoltre possibile invertire l&#39;ordine utilizzando `-` (meno) davanti alla metrica. Entrambe le istruzioni riportate di seguito determinano lo stesso ordinamento:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Supporto di funzioni generali

| Funzione | Esempio | Dettagli |
|---|---|---|
| [Cast](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` o <br/> `` `timestamp`::string `` | Il cast dei tipi non è attualmente supportato, ma non viene generato alcun errore. Funzione `CAST` ignorata. |
| [Marca temporale](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analizzare una stringa di ora come timestamp da utilizzare in una clausola `WHERE`. |
| [A timestamp](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analizzare una stringa temporale come marca temporale da utilizzare all&#39;interno di una clausola `WHERE`, fornendo facoltativamente un formato per tale stringa temporale. |
| [Data](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analizzare una stringa di data come timestamp da utilizzare in una clausola `WHERE`. |
| [Fino alla data](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analizzare una stringa di data come timestamp da utilizzare all&#39;interno di una clausola `WHERE`, fornendo facoltativamente un formato per tale stringa di data. |

{style="table-layout:auto"}

### Supporto delle funzioni di Dimension

Queste funzioni possono essere utilizzate sulle dimensioni nella clausola `SELECT`, `WHERE` o nelle metriche condizionali.

**Funzioni stringa**

| Funzione | Esempio | Dettagli |
|---|---|---|
| [Inferiore](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |

{style="table-layout:auto"}

**Funzioni data-ora**

| Funzione | Esempio | Dettagli |
|---|---|---|
| [Anno](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [Mese](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [Giorno](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [Giorno della settimana](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l’ID elemento invece del valore, in quanto non è necessario il nome descrittivo, ma il numero. |
| [Giorno dell’anno](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [Settimana](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [Trimestre](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [Ora](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l’ID elemento invece del valore, in quanto non è necessario il nome descrittivo, ma il numero. |
| [Minuto](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [Estrai](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l’ID elemento invece del valore per alcune parti di questa funzione, in quanto è necessario il numero e non il nome descrittivo.<br/>Parti supportate:<br>- Parole chiave: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Stringhe: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` o `'MINUTE'`. |
| [Data (parte)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l’ID elemento invece del valore per alcune parti di questa funzione, in quanto è necessario il numero e non il nome descrittivo.<br/>Parti di stringa supportate: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` o `'MINUTE'`. |
| [Data (troncata)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso.<br/>Le granularità della stringa supportate sono: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` o `'MINUTE'`. |

{style="table-layout:auto"}

### Supporto parziale

Alcune funzionalità SQL sono supportate solo parzialmente con l&#39;estensione BI e non restituiscono gli stessi risultati visualizzati con altri database.  Questa funzionalità specifica viene utilizzata in SQL generato da vari strumenti BI, per i quali l’estensione BI non ha una corrispondenza esatta. Di conseguenza, l’estensione BI si concentra su un’implementazione limitata che copre l’utilizzo minimo dello strumento BI senza generare errori. Per ulteriori informazioni, consulta la tabella seguente.

| Funzione | Esempio | Dettagli |
|---|---|---|
| MIN() E MAX() | ``MIN(daterange)`` o <br/> ``MAX(daterange)`` | `MIN()` il `timestamp`, `daterange` o uno qualsiasi dei `daterangeX` come `daterangeday` tornerà 2 anni fa.<br/><br/> `MAX()` il `timestamp`, `daterange` o uno qualsiasi dei `daterangeX` come `daterangeday` restituirà la data/ora corrente.<br/><br/>`MIN()` o `MAX()` su qualsiasi altra dimensione, metrica o espressione restituiranno 0. |

{style="table-layout:auto"}
