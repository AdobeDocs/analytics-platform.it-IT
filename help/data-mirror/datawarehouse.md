---
title: Configurare soluzioni native di Data Warehouse
description: Come configurare soluzioni native per data warehouse per Experience Platform Data Mirror per Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
source-git-commit: c9d7a4596a842ab7d949364e3469747d20ca15b4
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Configurare soluzioni native di Data Warehouse

{{release-limited-testing}}

Per supportare Experience Platform Data Mirror per Customer Journey Analytics, i dati che si desidera utilizzare dalle tre soluzioni native per data warehouse supportate ([[!DNL Azure Databricks]](#azure-databricks), [[!DNL Google BigQuery]](#google-bigquery), [[!DNL Snowflake]](#snowflake)) devono essere abilitati per l&#39;acquisizione dei dati di modifica.


## [!DNL Azure Databricks]

Consenti a **change data feed** nelle tabelle [!DNL Azure Databricks] di utilizzare change data capture nella connessione di origine.

Utilizzare i seguenti comandi per abilitare il feed di dati di modifica nelle tabelle:

**Nuova tabella**

Per applicare il feed di dati di modifica a una nuova tabella, è necessario impostare la proprietà della tabella `delta.enableChangeDataFeed` su `TRUE` nel comando `CREATE TABLE`.

```sql
CREATE TABLE student (id INT, name STRING, age INT) TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**Tabella esistente**

Per applicare il feed di dati di modifica a una tabella esistente, è necessario impostare la proprietà della tabella `delta.enableChangeDataFeed` su `TRUE` nel comando `ALTER TABLE`.

```sql
ALTER TABLE myDeltaTable SET TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**Tutte le nuove tabelle**

Per applicare il feed dati di modifica a tutte le nuove tabelle, è necessario impostare le proprietà predefinite su `TRUE`.

```sql
set spark.databricks.delta.properties.defaults.enableChangeDataFeed = true;
```

Per ulteriori informazioni, leggere la [[!DNL Azure Databricks] guida sull&#39;abilitazione del feed di dati di modifica](https://docs.databricks.com/aws/en/delta/delta-change-data-feed#enable-change-data-feed).

Per i passaggi su come abilitare l&#39;acquisizione dei dati di modifica per la connessione di origine [!DNL Azure Databricks], leggere la seguente documentazione:

* [Crea una [!DNL Azure Databricks] connessione di base](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/databricks).
* [Creare una connessione di origine per un database](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Google BigQuery]

Per utilizzare Change Data Capture nella connessione di origine [!DNL Google BigQuery], passare alla pagina [!DNL Google BigQuery] nella console [!DNL Google Cloud] e impostare `enable_change_history` su `TRUE`. Questa proprietà abilita la cronologia delle modifiche per la tabella dati.

Per ulteriori informazioni, leggere la guida sulle [istruzioni del linguaggio di definizione dei dati in [!DNL GoogleSQL]](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list).

Per i passaggi su come abilitare l&#39;acquisizione dei dati di modifica per la connessione di origine [!DNL Google BigQuery], leggere la seguente documentazione:

* [Crea una [!DNL Google BigQuery] connessione di base](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/bigquery).
* [Creare una connessione di origine per un database](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Snowflake]

Abilita **rilevamento modifiche** nelle tabelle [!DNL Snowflake] per utilizzare l&#39;acquisizione dati modifiche nelle connessioni di origine.

In [!DNL Snowflake], abilitare il rilevamento delle modifiche utilizzando `ALTER TABLE` e impostando `CHANGE_TRACKING` su `TRUE`.

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

Per ulteriori informazioni, leggere la [[!DNL Snowflake] guida sull&#39;utilizzo della clausola changes](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes).

Per i passaggi su come abilitare l&#39;acquisizione dei dati di modifica per la connessione di origine [!DNL Snowflake], leggere la seguente documentazione:

* [Crea una [!DNL Snowflake] connessione di base](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/snowflake).
* [Creare una connessione di origine per un database](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).


>[!MORELIKETHIS]
>
>[Guida rapida di Data Mirror: mirroring e utilizzo dei dati relazionali](relational.md)
>
