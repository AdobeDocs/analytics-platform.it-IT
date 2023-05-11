---
title: Connettore SQL
description: Scopri come utilizzare Query Service, Power BI e/o Tableau per accedere alle visualizzazioni dati utilizzando il connettore SQL.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
source-git-commit: 4205995fdc54e4d7626f17de79573751a5c63d26
workflow-type: tm+mt
source-wordcount: '2856'
ht-degree: 3%

---

# Connettore SQL

{{release-limited-testing}}

La [!DNL Customer Journey Analytics (CJA) SQL Connector] abilita l&#39;accesso SQL al [visualizzazioni dati](./data-views.md) che hai definito in CJA. I tuoi ingegneri e analisti di dati potrebbero avere più familiarità con Power BI, Tableau o altri strumenti di business intelligence e visualizzazione (ulteriormente denominati strumenti BI). Ora possono creare rapporti e dashboard in base alle stesse visualizzazioni dati utilizzate dagli utenti di CJA durante la creazione dei loro progetti Analysis Workspace.

Adobe Experience Platform [Servizio query](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=it) è l&#39;interfaccia SQL per i dati disponibili nel data lake di Experience Platform. Con la [!DNL CJA SQL Connector] abilitato, funzionalità di [!DNL Query Service] è esteso per visualizzare le visualizzazioni dati CJA come tabelle o visualizzazioni in una [!DNL Query Service] sessione. Di conseguenza, gli strumenti di business intelligence che utilizzano [!DNL Query Service] poiché l&#39;interfaccia PostgresSQL offre vantaggi diretti a questa funzionalità estesa.

I principali vantaggi sono i seguenti:

- Non è necessario ricreare una rappresentazione equivalente delle visualizzazioni dati CJA all’interno dello strumento BI stesso. <br/>Vedi [Visualizzazione dati](data-views.md) per ulteriori informazioni sulle funzionalità delle visualizzazioni dati per comprendere cosa deve essere ricreato.<br/>

- Maggiore coerenza nel reporting e nell’analisi tra gli strumenti BI e CJA.

- Combina i dati CJA con altre origini dati già disponibili negli strumenti BI.

## Prerequisiti

Per utilizzare questa funzionalità, devi

- Abilita la [!UICONTROL CJA SQL Connector] nell’organizzazione Experience Platform.

- Configura le funzionalità per i profili di prodotto, i gruppi di utenti e/o i singoli utenti pertinenti.<br/>
Gli utenti devono avere accesso a:
   - Experience Platform Query Service,
   - progetti di CJA Workspace e
   - Visualizzazioni di dati CJA che desiderano utilizzare.

- Utilizzare le credenziali in scadenza per collegare gli strumenti BI al connettore SQL CJA. Vedi [Guida alle credenziali](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) per ulteriori informazioni sull&#39;impostazione delle credenziali in scadenza o sulle credenziali in scadenza.


## Utilizzo

Per utilizzare [!DNL CJA SQL Connector] È possibile utilizzare direttamente SQL oppure utilizzare l&#39;esperienza di trascinamento disponibile nello strumento BI specifico.

### SQL

È possibile utilizzare la funzionalità direttamente nelle istruzioni SQL utilizzando l’Editor query o un client CLI standard.

+++ Editor query

Nell’interfaccia utente di Experience Platform:

1. Seleziona **[!UICONTROL ** Query **]** da **[!UICONTROL ** GESTIONE DATI **]** nella barra a sinistra.

2. Seleziona ![Crea query](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Crea query **]**.

3. Per eseguire la query, digitare l&#39;istruzione SQL e selezionare la ![Play](assets/Smock_Play_18_N.svg) o premere MAIUSC + INVIO.

+++


+++ CLI PostgresSQL

1. Nell&#39;interfaccia utente di Experience Platform, cerca e copia le credenziali PostgresSQL:

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (sotto **[!UICONTROL ** GESTIONE DATI **]**).

   2. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   3. Per copiare la stringa di connessione, utilizza ![Copia](assets/Smock_Copy_18_N.svg) in **[!UICONTROL ** Comando PSQL **]** sezione .

2. Apri la CLI di PostgresSQL.

3. Per accedere e iniziare a eseguire le query, incolla la stringa di connessione nella CLI di PostgresSQL.

+++

Vedi [Guida all’interfaccia utente dell’editor delle query](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) per ulteriori informazioni.


### Strumenti BI

Attualmente, il connettore SQL CJA è supportato per Power BI e Tableau.

+++ Power BI

1. Nell&#39;interfaccia utente di Adobe Experience Platform, cerca i dettagli delle credenziali PostgresSQL.

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (sotto **[!UICONTROL ** GESTIONE DATI **]**).

   2. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   3. Utilizzo ![Copia](assets/Smock_Copy_18_N.svg) per copiare ciascuno dei parametri delle credenziali di Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username]e altri) quando necessario in Power BI.

2. In Power BI:

   1. Nella finestra principale, seleziona **[!UICONTROL ** Ottieni dati **]** dalla barra degli strumenti superiore.

   2. Seleziona **[!UICONTROL ** Altro...**]** nella barra a sinistra.

   3. In **Ottieni dati** schermata, ricerca `PostgresSQL` e seleziona la **[!UICONTROL ** Database PostgresSQL **]** dall&#39;elenco.

   4. In **[!UICONTROL ** Database PostgressSQL **]** finestra di dialogo:

      1. Incolla **[!UICONTROL ** Host **]** parametro da query Experience Platform [!UICONTROL Credentials] in **[!UICONTROL ** Server **]** campo di testo.

      2. Incolla **[!UICONTROL ** Database **]** parametro da query Experience Platform [!UICONTROL Credentials] in **[!UICONTROL ** Database **]** campo di testo.

         Aggiungi `?FLATTEN` al **[!UICONTROL ** Database **]** quindi si legge come `prod:all?FLATTEN` ad esempio. Vedi [Strutture di dati nidificate appiattite per l’utilizzo con strumenti BI di terze parti](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) per ulteriori informazioni.

      3. Quando richiesto **[!UICONTROL ** Connettività dati **]** modalità, seleziona **[!UICONTROL ** DirectQuery **]** assicurare che le strutture di dati siano appiattite correttamente.

      4. Viene richiesto di **[!UICONTROL ** Nome utente **]** e **[!UICONTROL ** Password **]**. Utilizzare i parametri equivalenti dalle query Experience Platform [!UICONTROL Credentials].
   5. Dopo l’accesso, le tabelle della Visualizzazione dati CJA vengono visualizzate in Power BI’s **[!UICONTROL ** Navigatore **]**. Le tabelle di Visualizzazione dati sono identificate utilizzando `dv_` a nome loro.


   6. Selezionare le tabelle di visualizzazione dati da utilizzare e selezionare **[!UICONTROL ** Load **]**.

   Tutte le dimensioni e le metriche associate a una o più tabelle selezionate vengono visualizzate nel riquadro di destra, pronte per essere utilizzate nelle visualizzazioni.

   Vedi [Connetti Power BI a Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) per ulteriori informazioni.

+++

+++Tableau

1. Nell&#39;interfaccia utente di Experience Platform, cerca i dettagli delle credenziali PostgresSQL.

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (sotto **[!UICONTROL ** GESTIONE DATI **]**).

   2. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   3. Utilizzo ![Copia](assets/Smock_Copy_18_N.svg) per copiare ciascuno dei parametri delle credenziali di Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username]e altri) quando necessario a Tableau.

2. A Tableau:

   1. Seleziona **[!UICONTROL ** Altro **]** da **[!UICONTROL ** A un server **]** nella barra a sinistra.

   2. Seleziona **[!UICONTROL ** PostgresSQL **]** dall&#39;elenco.

   3. Nella finestra di dialogo [!UICONTROL PostgresSQL] (Crea elemento dati):

      1. Incolla **[!UICONTROL ** Host **]** parametro da query Experience Platform [!UICONTROL Credentials] in **[!UICONTROL ** Server **]** campo di testo.

      2. Incolla **[!UICONTROL ** Porta **]** parametro da query Experience Platform [!UICONTROL Credentials] in **[!UICONTROL ** Porta **]** campo di testo.

      3. Incolla **[!UICONTROL ** Database **]** parametro da query Experience Platform [!UICONTROL Credentials] in **[!UICONTROL ** Database **]** campo di testo.

         Aggiungi `%3FFLATTEN` al **[!UICONTROL ** Database **]** quindi si legge come `prod:all%3FFLATTEN` ad esempio. Vedi [Strutture di dati nidificate appiattite per l’utilizzo con strumenti BI di terze parti](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) per ulteriori informazioni.

      4. Seleziona **[!UICONTROL ** Nome utente e password **]** da **[!UICONTROL ** Autenticazione **]** elenco.

      5. Incolla **[!UICONTROL ** Nome utente **]** parametro da query Experience Platform [!UICONTROL Credentials] in **[!UICONTROL ** Nome utente **]** campo di testo.

      6. Incolla **[!UICONTROL ** Password **]** parametro da query Experience Platform [!UICONTROL Credentials] in **[!UICONTROL ** Password **]** campo di testo.

      7. Seleziona **[!UICONTROL ** Accesso **]**.
   4. Le visualizzazioni dati CJA vengono visualizzate come tabelle nella **[!UICONTROL ** Tabella **]** elenco. Le tabelle della visualizzazione dati hanno il prefisso `dv_`.

   5. Trascinare le tabelle che si desidera utilizzare nell&#39;area di lavoro.

   Ora puoi lavorare con i dati delle tabelle di visualizzazione dati per creare rapporti e visualizzazioni.

   Vedi [Connetti Tableau a Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) per ulteriori informazioni.

+++

Vedi [Connettere i client al servizio query](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) per una panoramica e ulteriori informazioni sui vari strumenti disponibili.

## Funzionalità

Per impostazione predefinita, le visualizzazioni dati hanno un nome sicuro per tabella generato dal nome descrittivo. Ad esempio, la visualizzazione dati denominata [!UICONTROL My Web Data] ha il nome della visualizzazione `dv_my_web_data`.

Se desideri utilizzare gli ID della visualizzazione dati come nomi di tabella, puoi aggiungere l’facoltativo `CJA_USE_IDS` impostazione del nome del database durante la connessione. Ad esempio: `prod:all?CJA_USE_IDS` mostra le visualizzazioni dati con nomi come `dv_ABC123`.

### Governance dei dati

Le impostazioni relative alla governance dei dati nel Customer Journey Analytics vengono ereditate da Adobe Experience Platform. L’integrazione tra CJA e Governance dei dati di Adobe Experience Platform consente di etichettare i dati CJA sensibili e di applicare i criteri di privacy.

Le etichette per la privacy e i criteri creati sui set di dati utilizzati da Experience Platform possono essere visualizzati nel flusso di lavoro delle visualizzazioni dati di CJA. Pertanto, i dati interrogati utilizzando CJA SQL Connector mostrano avvisi o errori appropriati quando non si rispettano le etichette e i criteri definiti per la privacy.

### Elenca visualizzazioni dati

Nella CLI standard di PostgreSQL, è possibile elencare le visualizzazioni utilizzando `\dv`

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

Per impostazione predefinita, lo schema delle visualizzazioni dati utilizza strutture nidificate, proprio come gli schemi XDM originali. L&#39;integrazione supporta anche i `FLATTEN` opzione . È possibile utilizzare questa opzione per forzare l’appiattimento dello schema per le visualizzazioni dati (e di qualsiasi altra tabella della sessione). L’appiattimento consente un utilizzo più semplice negli strumenti BI che non supportano schemi strutturati. Vedi [Utilizzo delle strutture dati nidificate nel servizio query](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) per ulteriori informazioni.

### SQL supportato

Vedi [Riferimento SQL di Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) per il riferimento completo sul tipo di SQL supportato.

Per una panoramica dei pattern e degli esempi, vedere la tabella Pattern.

+++Pattern

| Pattern | Esempio |
|---|---|
| Individuazione dello schema | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| Classifica/Suddivisione | <pre>SELECT dim1, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GRUPPO PER Dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39; E<br/>  filterId = &#39;12345&#39;<br/>GRUPPO PER Dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39; E<br/>  AND (dim2 = &#39;A&#39; O dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;)<br/>GRUPPO PER Dim1</pre> |
| Clausola HAVING | <pre>SELECT dim1, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GRUPPO PER Dim1<br/>AVENTI m1 > 100 |
| Distinto, superiore <br/>valori delle dimensioni | <pre>SELEZIONARE DISTINCT1 DA dv1</pre><pre>SELECT dim1 AS dv1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GRUPPO PER Dim1</pre><pre>SELECT dim1 AS dv1<br/>DA dv1<br/>DOVE \`timestamp\` >= &#39;2022-01-01&#39; E \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GRUPPO PER Dim1<br/>ORDINE PER SOMMA(metrica1)<br/>LIMITE 15</pre> |
| Totali delle metriche | <pre>SELECT SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;</pre> |
| Multi-dimensione<br/>disaggregazioni<br/>e distintivi | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GRUPPO BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GRUPPO PER 1, 2<br/>ORDINARE PER 1, 2</pre><pre>SELEZIONARE DISTINCT dim1, dim2<br/>DA dv1</pre> |
| Selezione secondaria:<br/>Risultato aggiuntivo<br/>filtro | <pre>SELECT dim1, m1<br/>DA (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  DA dv1<br/>  DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;</br>  GRUPPO PER Dim1<br/>)<br/>DOVE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Selezione secondaria:<br/>Unione con<br/>set di dati non presente<br/>CJA | <pre>SELECT b.key, a.dim1, a.m1<br/>DA (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  DA dv1<br/>  DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  GRUPPO PER Dim1<br/>a<br/>LEFT JOIN cerca b ON a.dim1 = b.key</pre> |
| Selezione secondaria:<br/>Query in corso<br/>visualizzazioni dati | <pre>Tasto SELECT, SUM(m1) AS totale<br/>DA (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  DA dv1<br/>  DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  GRUPPO PER Dim1<br/><br/>  UNIONE<br/><br/>  Tasto SELECT dim2 AS, SUM(m1) AS m1<br/>  DA dv2<br/>  DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  GRUPPO PER Dim2<br/>Tasto GROUP BY<br/>ORDINE PER totale</pre> |
| Selezione secondaria: <br/>Sorgente a strati, <br/>filtraggio, <br/>e aggregazione | Con livelli utilizzando le sottoselezioni:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>DA (<br/>  SELEZIONARE \_.dim1,\_.m1<br/>  DA (<br/>    SELEZIONA \* DA dv1<br/>    DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  ) \_<br/>  DOVE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) righe<br/>GRUPPO PER 1<br/>ORDINE PER totale</pre><br/>Livelli che utilizzano CTE CON:<br/><pre>CON le righe AS (<br/>  CON \_ AS (<br/>    SELECT * FROM data_ares<br/>    DOVE \`timestamp\` TRA &#39;2021-01-01&#39; E &#39;2021-02-01&#39;<br/>  )<br/>  SELEZIONA _.item, _.units DA _<br/>  WHERE _.item NON È NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>DA righe WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Seleziona dove<br/>metriche precedenti<br/> o sono mescolati con<br/>le dimensioni | <pre>SELECT SUM(metric1) AS m1, dim1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GRUPPO PER 2</pre> |

{style="table-layout:auto"}

+++

### Dimensioni

Puoi selezionare una qualsiasi delle dimensioni disponibili per impostazione predefinita o definite nella visualizzazione dati. Seleziona una dimensione per il relativo ID.

### Metriche

Le metriche disponibili per la selezione sono:

- una delle metriche disponibili per impostazione predefinita,

- definiti nella visualizzazione dati,

- metriche calcolate compatibili con la visualizzazione dati a cui l’utente ha accesso.

Seleziona una metrica dal relativo ID racchiuso in un `SUM(metric)` come per altre origini SQL.

È possibile utilizzare i:

- `SELECT COUNT(*)` o `COUNT(1)` per ottenere la metrica occorrenze.

- `SELECT COUNT(DISTINCT dimension)` o `SELECT APPROX_COUNT_DISTINCT(dimension)` per contare i valori univoci approssimativi di una dimensione. Vedi i dettagli in [Conteggio dei valori univoci](#counting-distincts).

- [Calcoli in linea](#inline-calculations) combinare le metriche al volo e/o fare matematica su di esse.

#### Conteggio dei valori univoci

A causa della natura sottostante del funzionamento di CJA, l’unica dimensione per la quale puoi ottenere un conteggio distinto esatto è la `adobe_personid` dimensione. Le seguenti istruzioni SQL `SELECT COUNT(DISTINCT adobe_personid)` o `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` restituisce il valore della metrica visitatori predefinita che è il conteggio di persone distinte. Per altre dimensioni, viene restituito un conteggio distinto approssimativo.

#### Metriche condizionali

È possibile incorporare un `IF` o `CASE` nella `SUM` o `COUNT` funzioni per aggiungere un filtro aggiuntivo specifico per una metrica selezionata. L’aggiunta di queste clausole è simile all’applicazione di un filtro a una colonna di metriche in una tabella di rapporti di Workspace.

Esempi:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Calcoli in linea

Puoi applicare altre espressioni metriche nelle `SELECT` invece di avere la matematica definita in una metrica calcolata. Nella tabella seguente sono elencati i tipi di espressioni supportati.

| Operatore o funzione | Dettagli |
|---|---|
| `+`, `-`, `*`, `/`, e `%` | Aggiungi, sottrai, moltiplica, dividi e modulare/resto |
| `-X` o `+X` | Modifica del segno o di una metrica in cui X è l’espressione metrica |
| `PI()` | costante π |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`e `TANH` | Funzioni matematiche unarie |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Funzioni matematiche binarie |

{style="table-layout:auto"}

### Colonne speciali

**Marca temporale**

La `timestamp` viene utilizzata una colonna speciale per fornire gli intervalli di date della query. Un intervallo di date può essere definito con un `BETWEEN` espressione o una coppia di `timestamp` `>`, `>=`, `<`, `<=` assegni `AND`insieme.
La `timestamp` è facoltativo e, se non viene fornito alcun intervallo completo, vengono utilizzati i valori predefiniti:

- Se viene fornito solo un minimo (`timestamp > X` o ` timestamp >= X`), l&#39;intervallo è da X a ora.

- Se viene fornito solo un valore massimo (`timestamp < X` o `timestamp <= X`), l&#39;intervallo va da X-30 giorni a X.

- Se non viene fornito nulla, l&#39;intervallo va da ora a 30 giorni a oggi.

L’intervallo di marche temporali viene convertito in un filtro globale dell’intervallo di date nella richiesta di classificazione.
Il campo timestamp può essere utilizzato anche nelle funzioni Date-Time per analizzare e troncare la marca temporale dell’evento.

**Intervallo date**

La `daterange` la colonna speciale funziona in modo simile a  `timestamp`Tuttavia, il filtro è limitato ai giorni interi. La `daterange` è anche opzionale e ha le stesse impostazioni predefinite dell&#39;intervallo `timestamp`.
La `daterange` può essere utilizzato anche in Funzioni data-ora per analizzare e troncare la data dell’evento.

**filterId**

La `filterId` la colonna speciale è facoltativa e viene utilizzata per applicare alla query un filtro definito esternamente. L’applicazione di un filtro definito esternamente a una query è simile al trascinamento di un filtro su un pannello in Workspace. È possibile fornire più ID filtro tramite `AND`-Le tira.

### Clausola WHERE

La clausola WHERE viene gestita in tre fasi:

1. Trova l’intervallo di date dal `timestamp` campo speciale.

2. Trova qualsiasi definizione esterna `filterId`s da includere nel filtro.

3. Trasforma le espressioni rimanenti in filtri ad hoc.

La gestione viene eseguita analizzando il primo livello di `AND`s nei `WHERE` clausola . Ogni livello superiore `AND`l&#39;espressione ed deve corrispondere a una delle precedenti. Qualsiasi cosa più profonda del primo livello di `AND`s, o se il `WHERE` usi della clausola `OR`s al livello superiore, viene gestito come filtro ad hoc.

### ORDINA PER

Per impostazione predefinita, la query ordina i risultati per la prima metrica selezionata in ordine decrescente. È possibile sovrascrivere l’ordinamento predefinito specificando `ORDER BY ... ASC` o `ORDER BY ... DESC`. Se utilizzi `ORDER BY`, devi specificare `ORDER BY` sulla prima metrica selezionata.

È inoltre possibile capovolgere l’ordine utilizzando `-` (meno) davanti alla metrica. Entrambe le istruzioni riportate di seguito determinano lo stesso ordine:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Supporto generale delle funzioni

| Funzione | Esempio | Dettagli |
|---|---|---|
| [CAST(tipo AS colonna)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` o <br/> `` `timestamp`::string `` | Il casting del tipo non è attualmente supportato, ma non viene generato alcun errore. La `CAST` La funzione viene ignorata. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analizzare una stringa ora come timestamp da utilizzare all&#39;interno di un `WHERE` clausola . |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analizzare una stringa ora come timestamp da utilizzare all&#39;interno di un `WHERE` , fornendo facoltativamente un formato per la stringa di ora. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analizzare una stringa di data come timestamp da utilizzare all’interno di un `WHERE` clausola . |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analizzare una stringa di data come timestamp da utilizzare all’interno di un `WHERE` , fornendo facoltativamente un formato per la stringa di data. |

{style="table-layout:auto"}

### Supporto delle funzioni del Dimension

Queste funzioni possono essere utilizzate sulle dimensioni nel `SELECT`, `WHERE` o nelle metriche condizionali.

**Funzioni stringa**

| Funzione | Esempio | Dettagli |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |

{style="table-layout:auto"}

**Funzioni di data e ora**

| Funzione | Esempio | Dettagli |
|---|---|---|
| [ANNO(data o ora)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [MONTH(data o ora)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [DAY(data o ora)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [DAYOFWEEK(data o ora)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l’ID dell’elemento invece del valore in quanto hai bisogno del numero e non del nome descrittivo. |
| [DAYOFYEAR(data o ora)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [SETTIMANA(data o ora)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [TRIMESTRE(data o ora)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [ORA(data o ora)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l’ID dell’elemento invece del valore in quanto hai bisogno del numero e non del nome descrittivo. |
| [MINUTO(data o ora)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. |
| [EXTRACT(parte DA data o data-ora)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l&#39;ID dell&#39;elemento invece del valore per alcune parti di questa funzione in quanto hai bisogno del numero e non del nome descrittivo.<br/>Le parti supportate sono:<br>- Parole chiave: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Stringhe:  `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&quot;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`oppure `'MINUTE'`. |
| [DATE_PART(parte, data o ora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l&#39;ID dell&#39;elemento invece del valore per alcune parti di questa funzione in quanto hai bisogno del numero e non del nome descrittivo.<br/>Le parti stringa supportate sono: `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&quot;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`oppure `'MINUTE'`. |
| [DATE_TRUNC(granularità, data o ora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso.<br/>Le granularità delle stringhe supportate sono: `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&quot;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`oppure `'MINUTE'`. |

{style="table-layout:auto"}

