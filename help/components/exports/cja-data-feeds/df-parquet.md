---
title: Utilizzare file Parquet da feed dati di Customer Journey Analytics
description: Scopri perché i feed di dati di Customer Journey Analytics distribuiscono file Parquet, come Parquet si confronta con CSV, TSV e JSON e come eseguire query o caricare i file.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: f77f416ad958b28a8489d7a6eb13100ba699236e
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 0%
---
# Utilizzare i file Parquet nei feed di dati

{{release-limited-testing}}

I feed di dati di Customer Journey Analytics distribuiscono file in formato Parquet. La maggior parte dei data warehouse moderni può leggere direttamente i file Parquet, quindi di solito non è necessario convertire i file prima di utilizzarli.

Utilizza le seguenti informazioni per comprendere perché i feed di dati utilizzano Parquet, come Parquet si confronta con altri formati di file e come eseguire query o caricare file Parquet nel tuo data warehouse.

## Vantaggi dell’utilizzo di Parquet per feed di dati

Il parquet è più adatto all’output di feed di dati rispetto a CSV, TSV o JSON per i seguenti motivi:

* **Feed larghi**: i feed di dati possono contenere centinaia di colonne. Parquet consente a una query di leggere solo le colonne necessarie.

* **Campi nidificati**: il parquet rappresenta in modo nativo campi nidificati, ad esempio un elenco di prodotti. CSV e TSV possono rappresentarli solo codificandoli in stringhe. Per ulteriori informazioni, vedere [Componenti evento secondario nei feed di dati](/help/components/exports/cja-data-feeds/df-sub-event.md).

* **Schema incorporato**: ogni file Parquet memorizza il proprio schema, inclusi i nomi delle colonne, i tipi di dati e le strutture nidificate. Poiché lo schema si trova nel file, il data warehouse può creare tabelle direttamente dai file. Non è necessario fornire un file di intestazione o una definizione di schema separati, né il data warehouse deve dedurre i tipi di dati.

* **Esportazioni di grandi dimensioni**: Parquet riduce in genere i costi di archiviazione e trasferimento. Evita inoltre l’analisi del testo quando si caricano i dati.

## Confronto tra Parquet e CSV, TSV e JSON

CSV, TSV e JSON sono formati di file comuni basati su testo:

* **CSV e TSV**: ogni riga di dati è una riga di testo normale, con valori separati da virgole (CSV) o tabulazioni (TSV). I feed di dati di Adobe Analytics distribuiscono file TSV. Per altre differenze tra i feed dati in Customer Journey Analytics e Adobe Analytics, vedi [Confrontare i feed dati in Customer Journey Analytics e Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

* **JSON**: ogni record viene archiviato come testo con campi denominati e può includere array e oggetti nidificati.

La tabella seguente illustra le differenze tra Parquet, CSV, TSV e JSON:

| Caratteristica | Parquet | CSV o TSV | JSON |
| --- | --- | --- | --- |
| **Velocità query** | Veloce. Una query legge solo le colonne necessarie. | Più lento. È necessario leggere e analizzare intere righe. | Più lento. È necessario leggere e analizzare intere righe. |
| **Tipi di dati** | Digitato. Schema incorporato nel file. | Non digitato. Tutti i valori sono testo e i tipi vengono dedotti quando si caricano i dati. | È stato digitato liberamente. |
| **Dati nidificati** | Gli array e gli oggetti sono supportati in modalità nativa. | Non supportato. Le matrici e gli oggetti devono essere appiattiti o codificati come stringhe. | Gli array e gli oggetti sono supportati in modalità nativa. |
| **Leggibilità** | Richiede uno strumento come data warehouse, DuckDB o Python. | Si apre in un editor di testo o in un foglio di calcolo. | Si apre in un editor di testo. |

## Eseguire query o caricare file Parquet

I file di feed dati vengono consegnati in formato Parquet nel percorso di archiviazione cloud selezionato al momento della [creazione del feed dati](/help/components/exports/cja-data-feeds/create-feed.md).

Anziché scaricare i file, in genere si collega il data warehouse al percorso di archiviazione. Potete quindi utilizzare i file Parquet in uno dei seguenti modi:

### Eseguire una query sui file in posizione

Definisci una tabella esterna che punti ai file nell’archiviazione cloud. Il data warehouse legge i file quando si esegue una query.

* **Snowflake**: tabelle o query esterne rispetto a una fase esterna
* **Database**: tabelle esterne su Amazon S3, Azure Data Lake Storage (ADLS) o Google Cloud Storage
* **BigQuery**: tabelle esterne su Google Cloud Storage
* **Amazon Redshift**: spettro Redshift su Amazon S3

### Caricare i file nelle tabelle gestite

Il caricamento di file nelle tabelle gestite è una scelta comune per i carichi di lavoro ricorrenti. Ad esempio:

* **Snowflake**: `COPY INTO`
* **BigQuery**: caricamento dei processi
* **Database**: `COPY INTO` o caricatore automatico

## Conversione dei dati Parquet in CSV o JSON

Se i processi a valle richiedono file CSV o JSON, la maggior parte dei data warehouse e degli strumenti può esportare i dati di Parquet in entrambi i formati dopo averli caricati. In Snowflake, ad esempio, è possibile scaricare i risultati della query come CSV o JSON con `COPY INTO`.
