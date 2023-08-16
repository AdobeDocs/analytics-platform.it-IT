---
title: Connettore SQL
description: Scopri come utilizzare Query Service, Power BI e/o Tableau per accedere alle visualizzazioni dati utilizzando il connettore SQL.
solution: Customer Journey Analytics
feature: SQL Connector
hide: true
hidefromtoc: true
exl-id: 80feadef-3e2d-4901-8c82-25c56d296e9f
source-git-commit: 7ae94bb46d542181c6438e87f204bd49c2128c8c
workflow-type: tm+mt
source-wordcount: '2918'
ht-degree: 1%

---

# Connettore SQL

{{release-limited-testing}}

{{select-package}}

Il [!DNL Customer Journey Analytics SQL Connector] abilita l&#39;accesso SQL al [visualizzazioni dati](./data-views.md) che hai definito nel Customer Journey Analytics. I data engineer e gli analisti potrebbero avere più familiarità con Power BI, Tableau o altri strumenti di business intelligence e visualizzazione (denominati anche strumenti BI). Ora possono creare reporting e dashboard basati sulle stesse visualizzazioni dati utilizzate dagli utenti del Customer Journey Analytics durante la creazione dei loro progetti Analysis Workspace.

Adobe Experience Platform [Servizio query](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=it) è l’interfaccia SQL per i dati disponibili nel data lake di Experienci Platform. Con il [!DNL Customer Journey Analytics SQL Connector] abilitato, la funzionalità di [!DNL Query Service] è esteso per visualizzare le visualizzazioni dati di Customer Journey Analytics come tabelle o viste in un [!DNL Query Service] sessione. Di conseguenza, gli strumenti di business intelligence che utilizzano [!DNL Query Service] come la loro interfaccia PostgresSQL beneficiare perfettamente di questa funzionalità estesa.

I principali vantaggi sono i seguenti:

- Non è necessario ricreare una rappresentazione equivalente delle visualizzazioni dati di Customer Journey Analytics all&#39;interno dello strumento BI stesso. <br/>Consulta [Visualizzazione dati](data-views.md) per ulteriori informazioni sulla funzionalità delle Visualizzazioni dati per capire cosa deve essere ricreato.<br/>

- Maggiore coerenza nelle attività di reporting e analisi tra strumenti di business intelligence e Customer Journey Analytics.

- Combinare i dati di Customer Journey Analytics con altre origini dati già disponibili negli strumenti BI.

## Prerequisiti

Per utilizzare questa funzionalità, è necessario

<!---   Enable the [!UICONTROL Customer Journey Analytics SQL Connector] in your Experience Platform organization. -->

- Configura la funzionalità per i profili di prodotto, i gruppi di utenti e/o i singoli utenti pertinenti.<br/>
Gli utenti devono avere accesso a:
   - Experienci Platform Query Service
   - progetti Customer Journey Analytics Workspace e
   - Visualizzazioni dati di Customer Journey Analytics che desiderano utilizzare.

- Utilizzare le credenziali senza scadenza per connettere gli strumenti BI al connettore SQL di Customer Journey Analytics. Gio [Guida alle credenziali](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) fornisce ulteriori informazioni sull&#39;impostazione di credenziali in scadenza o non in scadenza.

Consulta [Controllo dell’accesso](../admin/cja-access-control.md) per ulteriori informazioni, consulta la sezione Amministrazione del Customer Journey Analytics.


## Utilizzo

Per utilizzare [!DNL Customer Journey Analytics SQL Connector] funzionalità, è possibile utilizzare direttamente SQL o utilizzare l&#39;esperienza di trascinamento disponibile nello strumento BI specifico.

### SQL

È possibile utilizzare la funzionalità direttamente nelle istruzioni SQL utilizzando Query Editor o un client CLI (Command Line Interface) PostgresSQL standard.

+++ Editor query

Nell’interfaccia utente di Experience Platform:

1. Seleziona **[!UICONTROL ** Query **]** da **[!UICONTROL ** GESTIONE DATI **]** nella barra a sinistra.

2. Seleziona ![Crea query](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Crea query **]**.

3. Per eseguire la query, digitare l&#39;istruzione SQL e selezionare ![Play](assets/Smock_Play_18_N.svg) (o premere SHIFT + ENTER).

+++


+++ CLI PostgresSQL

1. Nell’interfaccia utente di Experience Platform, cerca e copia le credenziali PostgresSQL:

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (sotto **[!UICONTROL ** GESTIONE DATI **]**).

   2. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   3. Per copiare la stringa di connessione, utilizzare ![Copia](assets/Smock_Copy_18_N.svg) nel **[!UICONTROL ** comando PSQL **]** sezione.

2. Apri PostgresSQL CLI.

3. Per accedere e avviare l&#39;esecuzione delle query, incollare la stringa di connessione nella CLI PostgresSQL.

+++

Consulta [Guida dell’interfaccia utente di Query Editor](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) per ulteriori informazioni.


### Strumenti BI

Attualmente, il connettore SQL di Customer Journey Analytics è supportato e testato solo per Power BI e Tableau. Anche altri strumenti BI che utilizzano l’interfaccia PSQL potrebbero funzionare, ma non sono ancora ufficialmente supportati.

+++ Power BI

1. Nell’interfaccia utente di Adobe Experience Platform, cerca i dettagli delle credenziali PostgresSQL.

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (sotto **[!UICONTROL ** GESTIONE DATI **]**).

   2. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   3. Utilizzare ![ copy ](assets/Smock_Copy_18_N.svg) per copiare ciascuno dei parametri di credenziali Postgres ( [!UICONTROL Host] , [!UICONTROL Port] [!UICONTROL Database] [!UICONTROL Username] ,, e altri) quando necessario in Power bi.

2. In Power BI:

   1. Nella finestra principale, selezionate **[!UICONTROL ** Ottieni dati **]** dalla barra degli strumenti superiore.

   2. Seleziona **[!UICONTROL ** altro... **]** nella barra a sinistra.

   3. In **Ottieni dati** schermo, cerca `PostgresSQL` e seleziona la **[!UICONTROL ** Database PostgresSQL **]** dall&#39;elenco.

   4. In **[!UICONTROL ** Database PostgressSQL **]** finestra di dialogo:

      1. Incolla **[!UICONTROL ** Host **]** parametro da query Experienci Platform [!UICONTROL Credentials] in **[!UICONTROL ** Server **]** campo di testo.

      2. Incolla **[!UICONTROL ** Database **]** parametro da query Experienci Platform [!UICONTROL Credentials] in **[!UICONTROL ** Database **]** campo di testo.

         Aggiungi `?FLATTEN` al **[!UICONTROL ** Database **]** , in modo che si legga come `prod:all?FLATTEN` ad esempio. Consulta [Flatten delle strutture di dati nidificate da utilizzare con strumenti BI di terze parti](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) per ulteriori informazioni.

      3. Quando richiesto **[!UICONTROL ** Connettività dati **]** modalità, seleziona **[!UICONTROL ** DirectQuery **]** per garantire che le strutture di dati siano appiattite correttamente.

      4. Viene chiesto di **[!UICONTROL ** Nome utente **]** e **[!UICONTROL ** Password **]**. Utilizzare i parametri equivalenti dalle query Experienci Platform [!UICONTROL Credentials].


   5. Dopo aver effettuato correttamente l’accesso, le tabelle Visualizzazione dati di Customer Journey Analytics vengono visualizzate nel file del Power BI **[!UICONTROL ** Navigatore **]**. Le tabelle delle visualizzazioni dati sono identificate tramite `dv_` nel loro nome.


   6. Selezionare le tabelle delle visualizzazioni dati che si desidera utilizzare e selezionare **[!UICONTROL ** Carica **]**.

   Tutte le dimensioni e le metriche associate a una o più tabelle selezionate vengono visualizzate nel riquadro di destra, pronte per essere utilizzate nelle visualizzazioni.

   Consulta [Connetti Power BI a Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) per ulteriori informazioni.

+++

+++Tableau

1. Nell’interfaccia utente di Experience Platform, cerca i dettagli delle credenziali PostgresSQL.

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (sotto **[!UICONTROL ** GESTIONE DATI **]**).

   2. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   3. Utilizzare ![Copia](assets/Smock_Copy_18_N.svg) per copiare ciascuno dei parametri delle credenziali Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username]e altri) quando necessario a Tableau.

2. A Tableau:

   1. Seleziona **[!UICONTROL ** Altro **]** da **[!UICONTROL ** Su un server **]** nella barra a sinistra.

   2. Seleziona **[!UICONTROL ** PostgresSQL **]** dall&#39;elenco.

   3. Nella finestra di dialogo [!UICONTROL PostgresSQL] (Crea elemento dati):

      1. Incolla **[!UICONTROL ** Host **]** parametro da query Experienci Platform [!UICONTROL Credentials] in **[!UICONTROL ** Server **]** campo di testo.

      2. Incolla **[!UICONTROL ** Porta **]** parametro da query Experienci Platform [!UICONTROL Credentials] in **[!UICONTROL ** Porta **]** campo di testo.

      3. Incolla **[!UICONTROL ** Database **]** parametro da query Experienci Platform [!UICONTROL Credentials] in **[!UICONTROL ** Database **]** campo di testo.

         Aggiungi `%3FFLATTEN` al **[!UICONTROL ** Database **]** , in modo che si legga come `prod:all%3FFLATTEN` ad esempio. Consulta [Flatten delle strutture di dati nidificate da utilizzare con strumenti BI di terze parti](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) per ulteriori informazioni.

      4. Seleziona **[!UICONTROL ** Nome utente e password **]** da **[!UICONTROL ** Autenticazione **]** elenco.

      5. Incolla **[!UICONTROL ** Nome utente **]** parametro da query Experienci Platform [!UICONTROL Credentials] in **[!UICONTROL ** Nome utente **]** campo di testo.

      6. Incolla **[!UICONTROL ** password **]** parametro da Experience Platform query [!UICONTROL Credentials] in **[!UICONTROL ** password **]** campo di testo.

      7. Seleziona **[!UICONTROL ** Accedi **]** .

   4. Customer Journey Analytics visualizzazioni dei **[!UICONTROL ** dati vengono visualizzate come tabelle nell&#39;elenco tabella **]** . Le tabelle di visualizzazione dati sono precedute `dv_` da.

   5. Trascinate le tabelle da utilizzare nell&#39;area di disegno.

   È ora possibile utilizzare i dati delle tabelle di visualizzazione dati per versione i rapporti e le visualizzazioni.

   Consulta [Connettere Tableau a Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) per ulteriori informazioni.

+++

Consulta [Connettere i client a Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) per una panoramica e ulteriori informazioni sui vari strumenti disponibili.

## Funzionalità

Per impostazione predefinita, le visualizzazioni dati hanno un nome sicuro per la tabella generato dal loro nome descrittivo. Ad esempio, la visualizzazione dati denominata [!UICONTROL My Web Data] ha il nome della visualizzazione `dv_my_web_data`.

Se desideri utilizzare gli ID delle visualizzazioni dati come nomi delle tabelle, puoi aggiungere l’ `CJA_USE_IDS` impostazione del nome del database durante la connessione. Ad esempio: `prod:all?CJA_USE_IDS` mostra le visualizzazioni dati con nomi come `dv_ABC123`.

### Governance dei dati

Le impostazioni relative alla governance dei dati nel Customer Journey Analytics vengono ereditate da Adobe Experience Platform. L’integrazione tra Governance dei dati di Customer Journey Analytics e Governance dei dati di Adobe Experience Platform consente l’etichettatura dei dati sensibili di Customer Journey Analytics e l’applicazione delle politiche sulla privacy.

Le etichette per la privacy e i criteri creati sui set di dati utilizzati da Experienci Platform possono essere visualizzati nel flusso di lavoro delle visualizzazioni dati di Customer Journey Analytics. Pertanto, i dati interrogati tramite il connettore SQL di Customer Journey Analytics mostrano avvertenze o errori appropriati quando non sono conformi alle etichette e ai criteri di privacy definiti.

### Visualizzazioni dati elenco

Nella CLI PostgreSQL standard, è possibile elencare le viste utilizzando `\dv`

```sql
prod:all=> \dv
                                     List of relations
 Schema |                              Name                              | Type |  Owner             
--------+----------------------------------------------------------------+------+----------
 public | dv_adobe_analytics_spa                                         | view | postgres
 public | dv_adobe_analytics_spa_cja_adobe_users_only_                   | view | postgres
 public | dv_adobe_analytics_spa_cja_customers_only_                     | view | postgres
 public | dv_adobe_analytics_spa_core_aa_only_                           | view | postgres
 public | dv_adobe_analytics_spa_trad_aa_customers_only_                 | view | postgres
 public | dv_cja_audit_logs                                              | view | postgres
 public | dv_cja_connections_ui_prod_analytics_format_                   | view | postgres
 public | dv_cja_for_adobe_spark_usage                                   | view | postgres
 public | dv_cja_new_dimesnions                                          | view | postgres
 public | dv_cja_test_dimensions                                         | view | postgres
 public | dv_cja_usage_account_based_customers_only_                     | view | postgres
 public | dv_combined_trad_aa_apps                                       | view | postgres
 public | dv_customer_journey_analytics_sc_demo_users_                   | view | postgres
```

### Nidificato e appiattito

Per impostazione predefinita, lo schema delle visualizzazioni dati utilizza strutture nidificate, proprio come gli schemi XDM originali. L’integrazione supporta anche `FLATTEN` opzione. È possibile utilizzare questa opzione per forzare l’appiattimento dello schema per le visualizzazioni dati (e qualsiasi altra tabella nella sessione). L’appiattimento consente un utilizzo più semplice negli strumenti di business intelligence che non supportano schemi strutturati. Consulta [Utilizzo delle strutture di dati nidificati in Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) per ulteriori informazioni.

### SQL supportato

Consulta [Riferimento SQL di Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) per il riferimento completo sul tipo di SQL supportato.

Per esempi dell&#39;istruzione SQL utilizzabile, vedere la tabella seguente.

+++ Esempi

| Pattern | Esempio |
|---|---|
| Individuazione schema | <pre>Seleziona * da DV1 dove 1 = 0</pre> |
| Classifica/suddivisione | <pre>Seleziona Dim1, SUM (metric1) AS M1 <br/> da DV1 <br/> where \&#39; timestamp \&#39; tra&#39; 2022-01-01&#39; è 2022-01-02&#39; <br/> Group by Dim1</pre><pre>Seleziona Dim1, SUM (metric1) AS M1 <br/> da DV1 <br/> where \&#39; timestamp \&#39; tra&#39; 2022-01-01&#39; è 2022-01-02&#39; e <br/>  filterid =&#39; 12345&#39; <br/> Group by Dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39; E<br/>  E (dim2 = &#39;A&#39; O dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>RAGGRUPPA PER dim1</pre> |
| clausola HAVING | <pre>SELECT dim1, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>RAGGRUPPA PER dim1<br/>AVENTI m1 > 100</pre> |
| Distinct, top <br/>valori di dimensione | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>RAGGRUPPA PER dim1</pre><pre>SELECT dim1 AS dv1<br/>DA dv1<br/>DOVE \`timestamp\` >= &#39;2022-01-01&#39; E \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>RAGGRUPPA PER dim1<br/>ORDINA PER SOMMA(metrica1)<br/>LIMITE 15</pre> |
| Totali delle metriche | <pre>SELEZIONA SOMMA(metrica1) COME m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;</pre> |
| Multidimensionale<br/>raggruppamenti<br/>e top-distinct | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>RAGGRUPPA PER 1, 2<br/>ORDINA PER 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>DA dv1</pre> |
| Sottoselezione:<br/>Risultato aggiuntivo<br/>filtro | <pre>SELECT dim1, m1<br/>DA (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  DA dv1<br/>  DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;</br>  RAGGRUPPA PER dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Sottoselezione:<br/>Unione con<br/>set di dati non in<br/>Customer Journey Analytics | <pre>SELECT b.key, a.dim1, a.m1<br/>DA (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  DA dv1<br/>  DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  RAGGRUPPA PER dim1<br/>) a<br/>RICERCHE LEFT JOIN b ON a.dim1 = b.key</pre> |
| Sottoselezione:<br/>Query tra<br/>visualizzazioni dati | <pre>Tasto SELECT, SOMMA(m1) AS totale<br/>DA (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  DA dv1<br/>  DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  RAGGRUPPA PER dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  DA dv2<br/>  DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  RAGGRUPPA PER dim2<br/>Chiave GROUP BY<br/>ORDINA PER totale</pre> |
| Sottoselezione: <br/>Origine con livelli, <br/>filtraggio, <br/>e aggregazione | Livellato con sottoselezioni:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>DA (<br/>  SELECT \_.dim1,\_.m1<br/>  DA (<br/>    SELECT \* FROM dv1<br/>    DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  ) \_<br/>  DOVE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) righe<br/>RAGGRUPPA PER 1<br/>ORDINA PER totale</pre><br/>Livelli che utilizzano CTE CON:<br/><pre>CON RIGHE COME (<br/>  CON \_ COME (<br/>    SELECT * FROM data_ares<br/>    DOVE \`timestamp\` TRA &#39;2021-01-01&#39; E &#39;2021-02-01&#39;<br/>  )<br/>  SELEZIONA _.item, _.units DA _<br/>  DOVE _.item NON È NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS unità<br/>DA righe WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>Raggruppa per rows.item</pre> |
| Seleziona dove<br/>le metriche vengono prima<br/> o sono miscelati con<br/>le dimensioni | <pre>SELECT SUM(metric1) AS m1, dim1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>RAGGRUPPA PER 2</pre> |

{style="table-layout:auto"}

+++

### Dimensioni

Puoi selezionare una qualsiasi delle dimensioni disponibili per impostazione predefinita o definite nella visualizzazione dati. Selezionate una dimensione in base al relativo ID.

### Metriche

Le metriche disponibili per selezionare sono:

- qualsiasi metrica disponibile per impostazione predefinita,

- definito nella vista dati,

- metriche calcolate compatibili con i dati Visualizza a cui il utente è accesso.

Puoi selezionare una metrica in base al suo ID racchiuso in una `SUM(metric)` come per altre origini SQL.

È possibile utilizzare i:

- `SELECT COUNT(*)` o `COUNT(1)` per ottenere la metrica delle occorrenze.

- `SELECT COUNT(DISTINCT dimension)` o `SELECT APPROX_COUNT_DISTINCT(dimension)` per contare i valori distinti approssimativi di una dimensione. Vedi i dettagli in [Distinte di conteggio](#counting-distincts).

- [Calcoli in linea](#inline-calculations) combinare al volo le metriche e/o fare matematica su di esse.

#### Distinte di conteggio

A causa della natura sottostante del funzionamento del Customer Journey Analytics, l’unica dimensione per la quale puoi ottenere un conteggio distinto esatto è `adobe_personid` dimensione. Le istruzioni SQL seguenti `SELECT COUNT(DISTINCT adobe_personid)` o `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` restituisce il valore della metrica persone predefinita, che è il conteggio di persone distinte. Per le altre quote, viene restituito un conteggio distinto approssimativo.

#### Metriche condizionali

È possibile incorporare un `IF` o `CASE` clausola nel `SUM` o `COUNT` funzioni per aggiungere un filtro aggiuntivo specifico per una metrica selezionata. L’aggiunta di queste clausole è simile all’applicazione di un filtro a una colonna di metriche in una tabella di rapporti di Workspace.

Esempi:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Calcoli in linea

Puoi applicare espressioni metriche aggiuntive alle tue `SELECT` invece di avere la matematica definita in una metrica calcolata. Nella tabella seguente sono elencati i tipi di espressioni supportati.

| Operatore o funzione | Dettagli |
|---|---|
| `+`, `-`, `*`, `/`, e `%` | Aggiungere, sottrarre, moltiplicare, dividere e modulare/rimanente |
| `-X` o `+X` | Modifica del segno o di una metrica in cui X è l’espressione della metrica |
| `PI()` | Costante di |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`, e `TANH` | Funzioni matematiche unary |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Funzioni matematiche binario |

{style="table-layout:auto"}

### Colonne speciali

**Marca temporale**

Il `timestamp` per fornire gli intervalli di date per la query viene utilizzata una colonna speciale. Un intervallo di date può essere definito con un `BETWEEN` espressione o una coppia di `timestamp` `>`, `>=`, `<`, `<=` assegni `AND`Ed insieme.
Il `timestamp` è facoltativo; se non viene fornito un intervallo completo, vengono utilizzati i valori predefiniti:

- Se viene fornito solo un minimo (`timestamp > X` o ` timestamp >= X`), l’intervallo è da X a ora.

- Se viene fornito solo un massimo (`timestamp < X` o `timestamp <= X`), l’intervallo è compreso tra X-30 giorni e X.

- Se non viene fornito nulla, l’intervallo è da ora a 30 giorni.

L’intervallo di timestamp viene convertito in un filtro globale per intervalli di date in RankedRequest.
Il campo timestamp può essere utilizzato anche nelle funzioni data-ora per analizzare e troncare la marca temporale dell’evento.

**Intervallo date**

Il `daterange` la colonna speciale funziona in modo simile a  `timestamp`Tuttavia, il filtro è limitato a giorni interi. Il `daterange` è anche facoltativo e ha gli stessi valori predefiniti di intervallo di `timestamp`.
Il `daterange` Questo campo può essere utilizzato anche nelle funzioni data-ora per analizzare e troncare la data dell’evento.

**filterId**

Il `filterId` la colonna special è facoltativa e viene utilizzata per applicare alla query un filtro definito esternamente. L’applicazione di un filtro definito esternamente a una query è simile al trascinamento di un filtro su un pannello in Workspace. È possibile fornire più ID filtro tramite `AND`...e li manda.

### Clausola WHERE

La clausola WHERE viene gestita in tre passaggi:

1. Trovare l’intervallo di date dal `timestamp` campo speciale.

2. Trova qualsiasi definito esternamente `filterId`s da includere nel filtro.

3. Trasforma le espressioni rimanenti in filtri ad hoc.

La gestione viene eseguita analizzando il primo livello di `AND`s in `WHERE` clausola. Ogni livello superiore `AND`L’espressione end deve corrispondere a una delle precedenti. Qualsiasi elemento più profondo del primo livello di `AND`s, oppure, se `WHERE` utilizzi clausola `OR`come livello principale, viene gestito come filtro ad hoc.

### ORDINA PER

Per impostazione predefinita, la query ordina i risultati in base alla prima metrica selezionata in ordine decrescente. È possibile sovrascrivere l&#39;ordinamento predefinito specificando `ORDER BY ... ASC` o `ORDER BY ... DESC`. Se usa `ORDER BY`, è necessario specificare `ORDER BY` sulla prima metrica selezionata.

È inoltre possibile invertire l’ordine utilizzando `-` (meno) davanti alla metrica. Entrambe le istruzioni riportate di seguito determinano lo stesso ordinamento:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Supporto delle funzioni generali

| Funzione | Esempio | Dettagli |
|---|---|---|
| [CAST (colonna come tipo)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` o <br/> `` `timestamp`::string `` | Il tipo di casting non è attualmente supportato, ma non viene generato alcun errore. La `CAST` funzione viene ignorata. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analizzare una stringa di ora come marca temporale da utilizzare in una `WHERE` clausola. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analizzare una stringa di ora come marca temporale da utilizzare in una `WHERE` , fornendo facoltativamente un formato per tale stringa di tempo. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analizzare una stringa di data come marca temporale da utilizzare in una `WHERE` clausola. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analizzare una stringa di data come marca temporale da utilizzare in una `WHERE` , fornendo facoltativamente un formato per tale stringa di data. |

{style="table-layout:auto"}

### Supporto delle funzioni di Dimension

Queste funzioni possono essere utilizzate sulle dimensioni nel `SELECT`, `WHERE` nelle metriche condizionali.

**Funzioni stringa**

| Funzione | Esempio | Dettagli |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |

{style="table-layout:auto"}

**Funzioni data-ora**

| Funzione | Esempio | Dettagli |
|---|---|---|
| [YEAR(date o date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [MONTH(date o date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [DAY(date o date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [DAYOFWEEK(date o date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l’ID elemento invece del valore, in quanto non è necessario il nome descrittivo, ma il numero. |
| [DAYOFYEAR(date o date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [WEEK(date o date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [TRIMESTRE(data o data-ora)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [HOUR(date o date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l’ID elemento invece del valore, in quanto non è necessario il nome descrittivo, ma il numero. |
| [MINUTE(date o date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [EXTRACT(part FROM date o date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l’ID elemento invece del valore per alcune parti di questa funzione, in quanto è necessario il numero e non il nome descrittivo.<br/>Le parti supportate sono:<br>- Parole chiave: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Stringhe:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, o `'MINUTE'`. |
| [DATE_PART(parte, data o data-ora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l’ID elemento invece del valore per alcune parti di questa funzione, in quanto è necessario il numero e non il nome descrittivo.<br/>Le parti di stringa supportate sono: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, o `'MINUTE'`. |
| [DATE_TRUNC(granularità, data o data-ora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso.<br/>Le granularità di stringa supportate sono: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, o `'MINUTE'`. |

{style="table-layout:auto"}
