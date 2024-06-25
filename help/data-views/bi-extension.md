---
title: Estensione Customer Journey Analytics BI
description: Scopri come utilizzare Power BI o Tableau per accedere alle visualizzazioni dati utilizzando l’estensione Customer Journey Analytics BI.
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: 483f74408cfb81f2cbbbb25df9402aa829be09b1
workflow-type: tm+mt
source-wordcount: '2770'
ht-degree: 1%

---

# Estensione Customer Journey Analytics BI

{{select-package}}

Il [!DNL Customer Journey Analytics BI extension] abilita l&#39;accesso SQL al [visualizzazioni dati](./data-views.md) che hai definito nel Customer Journey Analytics. I data engineer e gli analisti potrebbero avere più familiarità con Power BI, Tableau o altri strumenti di business intelligence e visualizzazione (denominati anche strumenti BI). Ora possono creare reporting e dashboard basati sulle stesse visualizzazioni dati utilizzate dagli utenti del Customer Journey Analytics durante la creazione dei loro progetti Analysis Workspace.

Adobe Experience Platform [Servizio query](https://experienceleague.adobe.com/it/docs/experience-platform/query/home) è l’interfaccia SQL per i dati disponibili nel data lake di Experienci Platform. Con il [!DNL Customer Journey Analytics BI extension] abilitato, la funzionalità di [!DNL Query Service] è esteso per visualizzare le visualizzazioni dati di Customer Journey Analytics come tabelle o viste in un [!DNL Query Service] sessione. Di conseguenza, gli strumenti di business intelligence che utilizzano [!DNL Query Service] come la loro interfaccia PostgresSQL beneficiare perfettamente di questa funzionalità estesa.

I principali vantaggi sono i seguenti:

* Non è necessario ricreare una rappresentazione equivalente delle visualizzazioni dati di Customer Journey Analytics all&#39;interno dello strumento BI stesso. <br/>Consulta [Visualizzazioni dati](data-views.md) per ulteriori informazioni sulla funzionalità delle visualizzazioni dati per capire cosa deve essere ricreato.
* Maggiore coerenza nelle attività di reporting e analisi tra strumenti di business intelligence e Customer Journey Analytics.
* Combinare i dati di Customer Journey Analytics con altre origini dati già disponibili negli strumenti BI.

## Prerequisiti

Per utilizzare questa funzionalità, è necessario disporre di:

<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

* Accesso concesso agli Experienci Platform e ai Customer Journey Analytics.
* Accesso concesso dall’amministratore di prodotto al Customer Journey Analytics per visualizzare, modificare, aggiornare o eliminare connessioni e visualizzazioni dati.
* Accesso consentito alle visualizzazioni dati a cui desideri accedere.
* Accesso concesso all’estensione CJA BI.
* Utilizzare le credenziali senza scadenza per connettere gli strumenti BI al [!DNL Customer Journey Analytics BI extension]. Il [Guida alle credenziali](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials) fornisce ulteriori informazioni sull&#39;impostazione di credenziali in scadenza o non in scadenza.

Consulta [Controllo accesso Percorso clienti](../technotes/access-control.md) per ulteriori informazioni, in particolare [Autorizzazioni aggiuntive per l’amministratore di prodotto](../technotes/access-control.md#product-admin-additional-permissions) e [Autorizzazioni di Customer Journey Analytics nell’Admin Console](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console).


## Utilizzo

Per utilizzare [!DNL Customer Journey Analytics BI extension] funzionalità, è possibile utilizzare direttamente SQL o utilizzare l&#39;esperienza di trascinamento disponibile nello strumento BI specifico.

### SQL

È possibile utilizzare la funzionalità direttamente nelle istruzioni SQL utilizzando Query Editor o un client CLI (Command Line Interface) PostgresSQL standard.

+++ Editor query

In Adobe Experience Platform:

1. Seleziona **[!UICONTROL ** Query **]** da **[!UICONTROL ** GESTIONE DATI **]** nella barra a sinistra.

1. Seleziona ![Crea query](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Crea query **]**.

1. Seleziona la `cja` **[!UICONTROL ** Database **]**.

1. Per eseguire la query, digitare l&#39;istruzione SQL e selezionare ![Play](assets/Smock_Play_18_N.svg) (o premere `[SHIFT]` + `[ENTER]`).

+++


+++ CLI PostgresSQL

1. Cercare e copiare le credenziali PostgresSQL in Adobe Experience Platform:

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (sotto **[!UICONTROL ** GESTIONE DATI **]**).

   1. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   1. Seleziona la `cja` **[!UICONTROL ** Database **]**.

   1. Per copiare la stringa di comando, utilizzare ![Copia](assets/Smock_Copy_18_N.svg) nel **[!UICONTROL ** comando PSQL **]** sezione.

1. Aprire una finestra di comando o terminale.

1. Per accedere e avviare l’esecuzione delle query, incolla la stringa di comando nel terminale.

+++

Consulta la [Guida dell’interfaccia utente di Query Editor](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/user-guide) per ulteriori informazioni.


### Strumenti BI

Attualmente, il [!DNL Customer Journey Analytics BI extension] è supportato e testato solo per Power BI e Tableau. Anche altri strumenti di business intelligence che utilizzano l&#39;interfaccia PSQL potrebbero funzionare, ma non sono ancora ufficialmente supportati.

+++ Power BI

1. Cercare i dettagli delle credenziali PostgresSQL in Adobe Experience Platform:

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (sotto **[!UICONTROL ** GESTIONE DATI **]**).

   1. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   1. Seleziona la `cja` **[!UICONTROL ** Database **]**.

   1. Utilizzare ![Copia](assets/Smock_Copy_18_N.svg) per copiare ciascuno dei parametri delle credenziali Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username]e altri) quando necessario in Power BI.

1. In Power BI:

   1. Nella finestra principale, seleziona **[!UICONTROL ** Ottieni dati **]** dalla barra degli strumenti superiore.

   1. Seleziona **[!UICONTROL More...]** (Elementi dati) nella barra a sinistra.

   1. In **Ottieni dati** schermo, cerca `PostgresSQL` e seleziona la **[!UICONTROL ** Database PostgresSQL **]** dall&#39;elenco.

   1. In **[!UICONTROL ** Database PostgressSQL **]** finestra di dialogo:

      1. Incolla il **[!UICONTROL ** Host **]** parametro da query Experienci Platform [!UICONTROL Credentials] nel  **[!UICONTROL ** Server **]** campo di testo.

      1. Incolla il **[!UICONTROL ** Database **]** parametro da query Experienci Platform [!UICONTROL Credentials] nel **[!UICONTROL ** Database **]** campo di testo.

         Aggiungi `?FLATTEN` al **[!UICONTROL ** Database **]** , in modo che si legga come `prod:cja?FLATTEN` ad esempio. Consulta [Flatten delle strutture di dati nidificate da utilizzare con strumenti BI di terze parti](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) per ulteriori informazioni.

      1. Quando richiesto **[!UICONTROL Data Connectivity]** modalità, seleziona **[!UICONTROL DirectQuery]**.

      1. Viene chiesto di **[!UICONTROL Username]** e **[!UICONTROL Password]**. Utilizzare i parametri equivalenti dalle query Experienci Platform [!UICONTROL Credentials].


   1. Dopo aver eseguito correttamente l&#39;accesso, le tabelle di visualizzazione dati del Customer Journey Analytics vengono visualizzate in Power BI **[!UICONTROL ** Navigatore **]**.

   1. Selezionare le tabelle delle visualizzazioni dati che si desidera utilizzare e selezionare **[!UICONTROL ** Carica **]**.

   Tutte le dimensioni e le metriche associate a una o più tabelle selezionate vengono visualizzate nel riquadro di destra, pronte per essere utilizzate nelle visualizzazioni.

   Consulta [Connetti Power BI a Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi) per ulteriori informazioni.

+++

+++Tableau

1. Cercare i dettagli delle credenziali PostgresSQL in Adobe Experience Platform:

   1. Seleziona **[!UICONTROL ** Query **]** dalla barra a sinistra (sotto **[!UICONTROL ** GESTIONE DATI **]**).

   1. Seleziona **[!UICONTROL ** Credenziali **]** dalla barra superiore.

   1. Seleziona la ` cja` **[!UICONTROL ** Database **]**.

   1. Utilizzare ![Copia](assets/Smock_Copy_18_N.svg) per copiare ciascuno dei parametri delle credenziali Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username]e altri) quando necessario a Tableau.

1. A Tableau:

   1. Seleziona **[!UICONTROL ** Altro **]** da **[!UICONTROL ** Su un server **]** nella barra a sinistra.

   1. Seleziona **[!UICONTROL ** PostgresSQL **]** dall&#39;elenco.

   1. Nella finestra di dialogo [!UICONTROL PostgresSQL] (Crea elemento dati):

      1. Incolla il **[!UICONTROL ** Host **]** parametro da query Experienci Platform [!UICONTROL Credentials] in **[!UICONTROL ** Server **]** campo di testo.

      1. Incolla il **[!UICONTROL ** Porta **]** parametro da query Experienci Platform [!UICONTROL Credentials] in **[!UICONTROL ** Porta **]** campo di testo.

      1. Incolla il **[!UICONTROL ** Database **]** parametro da query Experienci Platform [!UICONTROL Credentials] in **[!UICONTROL ** Database **]** campo di testo.

         Aggiungi `%3FFLATTEN` al **[!UICONTROL ** Database **]** , in modo che si legga come `prod:cja%3FFLATTEN` ad esempio. Consulta [Flatten delle strutture di dati nidificate da utilizzare con strumenti BI di terze parti](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) per ulteriori informazioni.

      1. Seleziona **[!UICONTROL ** Nome utente e password **]** da **[!UICONTROL ** Autenticazione **]** elenco.

      1. Incolla **[!UICONTROL ** Nome utente **]** parametro da query Experienci Platform [!UICONTROL Credentials] in **[!UICONTROL ** Nome utente **]** campo di testo.

      1. Incolla il **[!UICONTROL ** Password **]** parametro da query Experienci Platform [!UICONTROL Credentials] in **[!UICONTROL ** Password **]** campo di testo.

      1. Seleziona la **[!UICONTROL ** Accedi **]**.

   1. Le visualizzazioni dati di Customer Journey Analytics vengono visualizzate come tabelle nella **[!UICONTROL ** Tabella **]** elenco.

   1. Trascinare le tabelle che si desidera utilizzare nell&#39;area di lavoro.

   Ora puoi lavorare con i dati delle tabelle delle visualizzazioni dati per creare rapporti e visualizzazioni.

   Consulta [Connettere Tableau a Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau) per ulteriori informazioni.

+++

Consulta [Connettere i client a Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview) per una panoramica e ulteriori informazioni sui vari strumenti disponibili.

## Funzionalità

Per impostazione predefinita, le visualizzazioni dati hanno un nome sicuro per la tabella generato dal loro nome descrittivo. Ad esempio, la visualizzazione dati denominata [!UICONTROL My Web Data View] ha il nome della visualizzazione `my_web_data_view`. È possibile definire un nome da utilizzare nello strumento BI per la visualizzazione dati. Consulta [Impostazioni della visualizzazione dati](create-dataview.md#settings) per ulteriori informazioni.

Se desideri utilizzare gli ID delle visualizzazioni dati come nomi delle tabelle, puoi aggiungere l’ `CJA_USE_IDS` impostazione del nome del database durante la connessione. Ad esempio: `prod:cja?CJA_USE_IDS` mostra le visualizzazioni dati con nomi come `dv_ABC123`.

### Governance dei dati

Le impostazioni relative alla governance dei dati nel Customer Journey Analytics vengono ereditate da Adobe Experience Platform. L’integrazione tra Governance dei dati di Customer Journey Analytics e Governance dei dati di Adobe Experience Platform consente l’etichettatura dei dati sensibili di Customer Journey Analytics e l’applicazione delle politiche sulla privacy.

Le etichette per la privacy e i criteri creati sui set di dati utilizzati da Experienci Platform possono essere visualizzati nel flusso di lavoro delle visualizzazioni dati di Customer Journey Analytics. Pertanto, i dati interrogati utilizzando [!DNL Customer Journey Analytics BI extension] mostra avvertenze o errori appropriati quando non si rispettano le etichette e i criteri per la privacy definiti.

### Visualizzazioni dati elenco

Nella CLI PostgreSQL standard, è possibile elencare le viste utilizzando `\dv`

```sql
prod:all=> \dv
                       List of relations
 Schema |                    Name                    | Type |  Owner             
--------+--------------------------------------------+------+----------
 public | my_web_data_view                           | view | postgres
 public | my_mobile_data_view                        | view | postgres
```

### Nidificato e appiattito

Per impostazione predefinita, lo schema delle visualizzazioni dati utilizza strutture nidificate, proprio come gli schemi XDM originali. L’integrazione supporta anche `FLATTEN` opzione. È possibile utilizzare questa opzione per forzare l’appiattimento dello schema per le visualizzazioni dati (e qualsiasi altra tabella nella sessione). L’appiattimento consente un utilizzo più semplice negli strumenti di business intelligence che non supportano schemi strutturati. Consulta [Utilizzo delle strutture di dati nidificati in Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) per ulteriori informazioni.

### SQL supportato

Consulta [Riferimento SQL di Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/overview) per il riferimento completo sul tipo di SQL supportato.

Per esempi delle istruzioni SQL utilizzabili, vedere la tabella seguente.

+++ Esempi

| Pattern | Esempio |
|---|---|
| Individuazione schema | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| Classificazione o raggruppamento | <pre>SELECT dim1, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>RAGGRUPPA PER dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39; E<br/>  filterId = &#39;12345&#39;<br/>RAGGRUPPA PER dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39; E<br/>  E (dim2 = &#39;A&#39; O dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>RAGGRUPPA PER dim1</pre> |
| `HAVING` clausola | <pre>SELECT dim1, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>RAGGRUPPA PER dim1<br/>AVENTI m1 > 100</pre> |
| Distinct, top <br/>valori di dimensione | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>RAGGRUPPA PER dim1</pre><pre>SELECT dim1 AS dv1<br/>DA dv1<br/>DOVE \`timestamp\` >= &#39;2022-01-01&#39; E \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>RAGGRUPPA PER dim1<br/>ORDINA PER SOMMA(metrica1)<br/>LIMITE 15</pre> |
| Totali delle metriche | <pre>SELEZIONA SOMMA(metrica1) COME m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;</pre> |
| Multidimensionale<br/>raggruppamenti<br/>e top-distinct | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>RAGGRUPPA PER 1, 2<br/>ORDINA PER 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>DA dv1</pre> |
| Sottoseleziona:<br/>Filtra informazioni aggiuntive<br/>risultati | <pre>SELECT dim1, m1<br/>DA (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  DA dv1<br/>  DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;</br>  RAGGRUPPA PER dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Sottoseleziona:<br/>Query tra<br/>visualizzazioni dati | <pre>Tasto SELECT, SOMMA(m1) AS totale<br/>DA (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  DA dv1<br/>  DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  RAGGRUPPA PER dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  DA dv2<br/>  DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  RAGGRUPPA PER dim2<br/>Chiave GROUP BY<br/>ORDINA PER totale</pre> |
| Sottoseleziona: <br/>Origine con livelli, <br/>filtraggio, <br/>e aggregazione | Livellato con sottoselezioni:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>DA (<br/>  SELECT \_.dim1,\_.m1<br/>  DA (<br/>    SELECT \* FROM dv1<br/>    DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  ) \_<br/>  DOVE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) righe<br/>RAGGRUPPA PER 1<br/>ORDINA PER totale</pre><br/>Livelli che utilizzano CTE CON:<br/><pre>CON RIGHE COME (<br/>  CON \_ COME (<br/>    SELECT * FROM data_ares<br/>    DOVE \`timestamp\` TRA &#39;2021-01-01&#39; E &#39;2021-02-01&#39;<br/>  )<br/>  SELEZIONA \_.item, \_.units DA \_<br/>  DOVE \_.item NON È NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS unità<br/>DA righe WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>Raggruppa per rows.item</pre> |
| Seleziona dove<br/>le metriche vengono prima<br/> o sono miscelati con<br/>le dimensioni | <pre>SELECT SUM(metric1) AS m1, dim1<br/>DA dv1<br/>DOVE \`timestamp\` TRA &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>RAGGRUPPA PER 2</pre> |

{style="table-layout:auto"}

+++

### Dimensioni

Puoi selezionare una qualsiasi delle dimensioni disponibili per impostazione predefinita o definite nella visualizzazione dati. Puoi selezionare una dimensione in base al relativo ID.

### Metriche

Le metriche disponibili per la selezione sono:

* Una qualsiasi delle metriche disponibili per impostazione predefinita;
* Definito nella visualizzazione dati;
* Metriche calcolate compatibili con la visualizzazione dati a cui l’utente ha accesso.

Puoi selezionare una metrica in base al suo ID racchiuso in una `SUM(metric)` come per altre origini SQL.

Puoi utilizzare:

* `SELECT COUNT(*)` o `COUNT(1)` per ottenere la metrica delle occorrenze.
* `SELECT COUNT(DISTINCT dimension)` o `SELECT APPROX_COUNT_DISTINCT(dimension)` per contare i valori distinti approssimativi di una dimensione. Vedi i dettagli in [Conteggio dei valori distinti](#counting-distinct-values).
* [Calcoli in linea](#inline-calculations) combinare al volo le metriche e/o fare matematica su di esse.

#### Conteggio dei valori distinti

A causa della natura sottostante del funzionamento del Customer Journey Analytics, l’unica dimensione per la quale puoi ottenere un conteggio distinto esatto è `adobe_personid` dimensione. Le istruzioni SQL seguenti `SELECT COUNT(DISTINCT adobe_personid)` o `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` restituisce il valore della metrica persone predefinita, che è il conteggio di persone distinte. Per le altre quote, viene restituito un conteggio distinto approssimativo.

#### Metriche condizionali

È possibile incorporare un `IF` o `CASE` clausola nel `SUM` o `COUNT` funzioni per aggiungere un filtro aggiuntivo specifico per una metrica selezionata. L’aggiunta di queste clausole è simile all’applicazione di un filtro a una colonna di metriche in una tabella di rapporti di Workspace.

Esempi:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### Calcoli in linea

Puoi applicare calcoli aggiuntivi alle espressioni metriche nelle tue `SELECT`. Puoi usare questa matematica invece di definirla in una metrica calcolata. Nella tabella seguente sono elencati i tipi di espressioni supportati.

| Operatore o funzione | Dettagli |
|---|---|
| `+`, `-`, `*`, `/`, e `%` | Aggiungere, sottrarre, moltiplicare, dividere e modulare/rimanente |
| `-X` o `+X` | Modifica del segno o di una metrica in cui X è l’espressione della metrica |
| `PI()` | Costante di |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`, e `TANH` | Funzioni matematiche unarie |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Funzioni matematiche binarie |

{style="table-layout:auto"}

### Colonne speciali

#### Marca temporale

Il `timestamp` per fornire gli intervalli di date per la query viene utilizzata una colonna speciale. Un intervallo di date può essere definito con un `BETWEEN` espressione o una coppia di `timestamp` `>`, `>=`, `<`, `<=` assegni `AND`Ed insieme.
Il `timestamp` è facoltativo; se non viene fornito un intervallo completo, vengono utilizzati i valori predefiniti:

* Se viene fornito solo un minimo (`timestamp > X` o ` timestamp >= X`), l’intervallo è da X a ora.
* Se viene fornito solo un massimo (`timestamp < X` o `timestamp <= X`), l&#39;intervallo è compreso tra X meno 30 giorni e X.
* Se non viene fornito nulla, l’intervallo è da ora meno 30 giorni a ora.

L’intervallo di marca temporale viene convertito in un filtro globale per intervalli di date in RankedRequest.
Il campo timestamp può essere utilizzato anche nelle funzioni data/ora per analizzare o troncare la marca temporale dell’evento.

#### Intervallo date

Il `daterange` la colonna speciale funziona in modo simile a `timestamp`; tuttavia il filtro è limitato a giorni interi. Il `daterange` è anche facoltativo e ha gli stessi valori predefiniti di intervallo di `timestamp`.
Il `daterange` Questo campo può essere utilizzato anche nelle funzioni data/ora per analizzare o troncare la data evento.

Il `daterangeName` una colonna speciale può essere utilizzata per filtrare la query utilizzando un intervallo di date denominato come `Last Quarter`.

>[!NOTE]
>
>Il Power BI non supporta `daterange` metriche inferiori a un giorno (ora, 30 minuti, 5 minuti, ecc.).


#### ID filtro

Il `filterId` la colonna special è facoltativa e viene utilizzata per applicare alla query un filtro definito esternamente. L’applicazione di un filtro definito esternamente a una query è simile al trascinamento di un filtro su un pannello in Workspace. È possibile utilizzare più ID filtro di `AND`...e li manda.

Insieme a `filterId`, è possibile utilizzare `filterName` per utilizzare il nome di un filtro invece dell’ID.

### Clausola Where

Il `WHERE` La clausola viene gestita in tre passaggi:

1. Trovare l’intervallo di date dal `timestamp`, `daterange`, o `daterangeName` campi speciali.

1. Trova qualsiasi definito esternamente `filterId`s o `filterName`s da includere nel filtro.

1. Trasforma le espressioni rimanenti in filtri ad hoc.

La gestione viene eseguita analizzando il primo livello di `AND`s in `WHERE` clausola. Ogni livello superiore `AND`L&#39;espressione -ed deve corrispondere a una delle precedenti. Qualsiasi elemento più profondo del primo livello di `AND`s, oppure, se `WHERE` utilizzi clausola `OR`come livello principale, viene gestito come filtro ad hoc.

### Ordinamento

Per impostazione predefinita, la query ordina i risultati in base alla prima metrica selezionata in ordine decrescente. È possibile sovrascrivere l&#39;ordinamento predefinito specificando `ORDER BY ... ASC` o `ORDER BY ... DESC`. Se usa `ORDER BY`, è necessario specificare `ORDER BY` sulla prima metrica selezionata.

È inoltre possibile invertire l’ordine utilizzando `-` (meno) davanti alla metrica. Entrambe le istruzioni riportate di seguito determinano lo stesso ordinamento:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Supporto di funzioni generali

| Funzione | Esempio | Dettagli |
|---|---|---|
| [Cast](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` o <br/> `` `timestamp`::string `` | Il cast dei tipi non è attualmente supportato, ma non viene generato alcun errore. Il `CAST` viene ignorata. |
| [Marca temporale](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analizzare una stringa di ora come marca temporale da utilizzare in una `WHERE` clausola. |
| [A timestamp](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analizzare una stringa di ora come marca temporale da utilizzare in una `WHERE` , fornendo facoltativamente un formato per tale stringa di tempo. |
| [Data](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analizzare una stringa di data come marca temporale da utilizzare in una `WHERE` clausola. |
| [Alla data](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analizzare una stringa di data come marca temporale da utilizzare in una `WHERE` , fornendo facoltativamente un formato per tale stringa di data. |

{style="table-layout:auto"}

### Supporto delle funzioni di Dimension

Queste funzioni possono essere utilizzate sulle dimensioni nel `SELECT`, `WHERE` nelle metriche condizionali.

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
| [Extract](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l’ID elemento invece del valore per alcune parti di questa funzione, in quanto è necessario il numero e non il nome descrittivo.<br/>Le parti supportate sono:<br>- Parole chiave: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Stringhe:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, o `'MINUTE'`. |
| [Data (parte)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso. Utilizza l’ID elemento invece del valore per alcune parti di questa funzione, in quanto è necessario il numero e non il nome descrittivo.<br/>Le parti di stringa supportate sono: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, o `'MINUTE'`. |
| [Data (troncata)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Genera un’identità di dimensione dinamica nel campo trasmesso.<br/>Le granularità di stringa supportate sono: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, o `'MINUTE'`. |

{style="table-layout:auto"}
