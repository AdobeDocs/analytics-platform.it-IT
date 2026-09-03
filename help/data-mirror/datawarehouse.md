---
title: Configurare soluzioni native di Data Warehouse
description: Come configurare soluzioni native per data warehouse per Experience Platform Data Mirror per Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
autotag-review: '2026-05-19T08:56:46.637Z'
TQID: 'https://experienceleague.adobe.com/A3GkkNVAO9qpbOqCrZnf6PNJfRuwMaodJVOOuSRg0w8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 441
ht-degree: 0%

---

# Configurare soluzioni native di Data Warehouse

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

* [Crea una [!DNL Azure Databricks] connessione di base](https://experienceleague.adobe.com/it/docs/experience-platform/sources/api-tutorials/create/databases/databricks).
* [Creare una connessione di origine per un database](https://experienceleague.adobe.com/it/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Google BigQuery]

Per utilizzare Change Data Capture nella connessione di origine [!DNL Google BigQuery], passare alla pagina [!DNL Google BigQuery] nella console [!DNL Google Cloud] e impostare `enable_change_history` su `TRUE`. Questa proprietà abilita la cronologia delle modifiche per la tabella dati.

Per ulteriori informazioni, leggere la guida sulle [istruzioni del linguaggio di definizione dei dati in [!DNL GoogleSQL]](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list).

Per i passaggi su come abilitare l&#39;acquisizione dei dati di modifica per la connessione di origine [!DNL Google BigQuery], leggere la seguente documentazione:

* [Crea una [!DNL Google BigQuery] connessione di base](https://experienceleague.adobe.com/it/docs/experience-platform/sources/api-tutorials/create/databases/bigquery).
* [Creare una connessione di origine per un database](https://experienceleague.adobe.com/it/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Snowflake]

Abilita **rilevamento modifiche** nelle tabelle [!DNL Snowflake] per utilizzare l&#39;acquisizione dati modifiche nelle connessioni di origine.

In [!DNL Snowflake], abilitare il rilevamento delle modifiche utilizzando `ALTER TABLE` e impostando `CHANGE_TRACKING` su `TRUE`.

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

Per ulteriori informazioni, leggere la [[!DNL Snowflake] guida sull&#39;utilizzo della clausola changes](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes).

Per i passaggi su come abilitare l&#39;acquisizione dei dati di modifica per la connessione di origine [!DNL Snowflake], leggere la seguente documentazione:

* [Crea una [!DNL Snowflake] connessione di base](https://experienceleague.adobe.com/it/docs/experience-platform/sources/api-tutorials/create/databases/snowflake).
* [Creare una connessione di origine per un database](https://experienceleague.adobe.com/it/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).


>[!MORELIKETHIS]
>
>[Guida rapida di Data Mirror: mirroring e utilizzo dei dati relazionali](relational.md)
>
