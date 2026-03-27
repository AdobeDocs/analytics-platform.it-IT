---
description: Scopri come prepararti a mappare le colonne dei feed di dati da Adobe Analytics a Customer Journey Analytics.
keywords: clickstream;feed dati;datafeed;feed dati
title: Preparare la mappatura delle colonne di feed dati da Adobe Analytics a Customer Journey Analytics
feature: Components
hide: true
hidefromtoc: true
exl-id: d0a9e697-1e48-4cfb-8613-2f932bf5015b
source-git-commit: 9403a4c6d0e0389de19aa4627d9d952f0c31f1a2
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 2%

---

# Preparare il mapping delle colonne dei feed di dati da Adobe Analytics a Customer Journey Analytics

Customer Journey Analytics fornisce un’architettura più flessibile di Adobe Analytics per determinare le colonne disponibili da includere in un feed di dati. La maggior parte delle organizzazioni deve aspettarsi di esportare da Customer Journey Analytics colonne di feed dati diverse da quelle esportate da Adobe Analytics. Tali differenze sono dovute ai seguenti fattori:

* **[Architettura dello schema](#schema-architecture)**: le colonne del feed dati di Adobe Analytics sono derivate dalle variabili di Analytics, mentre le colonne del feed dati di Customer Journey Analytics sono derivate dallo schema della visualizzazione dati.

* **[Elaborazione dati](#data-processing)**: esistono differenze fondamentali tra Adobe Analytics e Customer Journey Analytics nell&#39;elaborazione dei dati, in particolare l&#39;esistenza di colonne pre e post-elaborazione per molte colonne di Adobe Analytics.

* **[Colonne inutilizzate](#unused-columns)**: Adobe Analytics contiene più di 1.100 colonne di feed dati. La maggior parte delle organizzazioni non utilizza i dati di tutte le colonne esportate.

* **[Colonne cross-channel](#cross-channel-columns)**: Customer Journey Analytics supporta i dati cross-channel (ad esempio i dati del call center), che non sono disponibili in Adobe Analytics.

Prima di iniziare a mappare le colonne dei feed dati di Adobe Analytics alle colonne dei feed dati di Customer Journey Analytics, controlla le sezioni seguenti per comprendere meglio questi fattori chiave che influiscono sulla mappatura.

Dopo aver esaminato queste informazioni, segui le istruzioni di mappatura per ogni colonna del feed dati di Adobe Analytics che intendi mantenere in Customer Journey Analytics, come descritto in [Riferimento colonna dati](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

## Architettura dello schema

Customer Journey Analytics offre un’architettura più flessibile di Adobe Analytics per determinare quali colonne sono disponibili da includere in un feed di dati:

### Architettura di Adobe Analytics

È disponibile un elenco statico predefinito di variabili da includere come colonne di feed dati.

È facile includere tutte le colonne, e molti clienti lo fanno, anche quando i dati contenuti in tali colonne non vengono utilizzati in tutta l’organizzazione.

### Architettura Customer Journey Analytics

Tutti i componenti inclusi nello schema della visualizzazione dati possono essere inclusi come colonne di feed dati. Per informazioni dettagliate su questo processo per ogni potenziale colonna del feed dati di Adobe Analytics, vedi [Riferimento colonna dati](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

I componenti vengono inclusi nello schema della visualizzazione dati in uno dei modi descritti nella tabella seguente:

| Metodo per l’inclusione nello schema della visualizzazione dati | Informazioni aggiuntive |
|---------|----------|
| I campi dello schema XDM vengono curati come componenti nella visualizzazione dati | I campi esistenti nello schema XDM diventano parte dello schema di visualizzazione dati in Customer Journey Analytics dopo essere stati curati come componenti nella visualizzazione dati. <p>Il numero di campi disponibili per impostazione predefinita nello schema XDM di Customer Journey Analytics può variare a seconda del modo in cui i dati vengono raccolti per l’implementazione di Customer Journey Analytics, come segue:</p><ul><li>**Nuove implementazioni di Web SDK**: se l&#39;implementazione di Customer Journey Analytics utilizza uno schema personalizzato, è probabile che molte colonne esistenti nei feed di dati di Adobe Analytics non esistano in Customer Journey Analytics. Allo stesso modo, Customer Journey Analytics può contenere campi che non esistono nei feed dati di Adobe Analytics.<p>Se possibile, consulta il team o la persona che ha progettato lo schema XDM per l’implementazione Customer Journey Analytics della tua organizzazione. Molte delle decisioni sui campi Adobe Analytics necessari in Customer Journey Analytics sono state prese al momento della creazione dello schema XDM. Per ulteriori informazioni, consulta [Progettare lo schema da utilizzare con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).</p></li><li>**Implementazioni del connettore Source di Analytics**: per impostazione predefinita, per molte colonne di feed dati esistono mappature di campi uno-a-uno perché il connettore Source di Analytics utilizza il gruppo di campi Evento esperienza di Analytics nello schema XDM. Per informazioni sui campi mappati da Adobe Analytics ai campi di questo gruppo di campi, vedi [Mappature dei campi di Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) nella documentazione di Experience Platform.</li></ul> |
| I componenti vengono creati all’interno della visualizzazione dati utilizzando campi derivati | Puoi creare componenti direttamente all’interno di una visualizzazione dati, creando in tal modo colonne di feed dati che non sono disponibili nello schema XDM. |

## Elaborazione dei dati

Le differenze di elaborazione dei dati tra Adobe Analytics e Customer Journey Analytics influiscono sulle colonne dei feed di dati disponibili per l’esportazione, come segue:

* **Adobe Analytics**: molti campi dei feed dati vengono esportati come due colonne separate: una contenente dati preelaborati e un&#39;altra contenente dati post-elaborati. I dati post-elaborati includono logica lato server, regole di elaborazione, regole VISTA, regole di persistenza delle dimensioni e così via.

  Poiché Adobe Analytics esporta i dati di alcuni campi in due colonne separate (una per i dati pre-elaborati e una per i dati post-elaborati), Adobe Analytics contiene più colonne di feed di dati rispetto a Customer Journey Analytics. Tieni presente questo aspetto durante la mappatura dei campi.

* **Customer Journey Analytics**: i campi sono disponibili per i feed di dati dopo essere stati creati nella visualizzazione dati. In genere, i campi nelle visualizzazioni dati di Customer Journey Analytics includono solo dati post-elaborati. Tuttavia, in genere è possibile approssimare la versione pre-elaborata di Adobe Analytics di un campo creando una seconda versione del campo all’interno della visualizzazione dati di Customer Journey Analytics e configurandola per scadere all’hit.

## Colonne non utilizzate

Sono disponibili oltre 1.100 colonne di feed dati da esportare in Adobe Analytics. Di queste colonne, non tutte verranno utilizzate nei feed di dati di Customer Journey Analytics. Questa discrepanza non indica che le colonne dei feed dati di Customer Journey Analytics sono insufficienti.

Identifica le colonne dei feed dati di Adobe Analytics utilizzate dalla tua organizzazione. Procedendo in questo modo si determineranno le colonne necessarie nei feed di dati di Customer Journey Analytics. Per determinare quali colonne utilizzare:

* **Identificare i campi che si applicano solo ad Adobe Analytics**: alcune colonne nei feed dati di Adobe Analytics sono specifiche per il motore di elaborazione dati di Adobe Analytics e pertanto non si applicano a Customer Journey Analytics. Esempi di tali colonne sono `exclude_hit` e `hit_source`.

* **Identifica i campi applicabili alla tua organizzazione**: anche se non tutti i clienti Adobe Analytics esportano tutte le colonne disponibili, molti clienti esportano più di quanto effettivamente utilizzano.

  Prima di iniziare l’esportazione dei feed dati da Customer Journey Analytics, è necessario determinare quali colonne di feed dati di Adobe Analytics vengono attualmente utilizzate dalla tua organizzazione, quindi verificare che tali componenti siano presenti nello schema di visualizzazione dati di Customer Journey Analytics. Per raccogliere queste informazioni, contatta i team o i singoli utenti dell’organizzazione che utilizzano i contenuti dei feed di dati per Adobe Analytics.

## Colonne cross-channel

Customer Journey Analytics supporta i dati cross-channel (come i dati del call center), che non sono disponibili in Adobe Analytics. Questi campi cross-channel sono esempi di nuove colonne che possono essere incluse nei feed di dati di Customer Journey Analytics e che non sono supportate in Adobe Analytics.

<!--

1. View the data views throughout your organization to make sure that corresponding dimensions are available. If a corresponding dimension does not exist in the data view, create it.

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view.

   

1. For each Adobe Analytics data feed field that is being used, ensure that a similar field exists in the XDM schema.

1. Verify that and that corresponding dimensions are available in the data view. If not, you need to create them. 

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 

## Map data feed columns from Adobe Analytics to Customer Journey Analytics

### Step 1 - Map the default columns included in Customer Journey Analytics

There are roughly 20 default fields included in all WebSDK implementations. 

Before you can map these default columns, make sure that your Customer Journey Analytics environment meets the following prerequisites:

* It uses a WebSDK implementation.

* The appropriate field groups that contain the default WebSDK fields are added to your XDM schema.If the field is not added to your schema, it is included in the payload, but ultimately dropped.

* Each default field must be curated as a component in a Customer Journey Analytics data view.

* The component settings in the data view must be equivalent to how Analytics treats it (Visit persistence or hit-level persistence).

To map the default dimensions:

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that are included by default

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

### Step 2: Discover which additional data feed columns your consumers use

There are over 1,100 data feed columns available to be exported in Adobe Analytics. While not all Adobe Analytics customers export all of the available columns, many customers export more than they actually use. 

Before you begin mapping data feed columns, you should first:

1. Contact the teams or individuals who consume data feed content and determine which data feed columns they use.

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 


### Step 3 - Map each additional column

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that could be mapped if they are included in your schema and data views

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

Notes below here. Ignore:

Do we group these columns by if you're using the WebSDK, or if you're using specific field groups.

Here's what is in Analytics, and here's what it maps to in CJA. Customers want us to "give them the mappings."

Some of these fields there is probably something like it that you could get in WebSDK. There will be some fields that aren't. Or some that are in AEP that aren't in here (like call center data).

We have an XDM field mappings to Analytics variables. "Adobe analytics XDM Var - first hit on Google." If you set your XDM payload to the given field on the left, it will automatically be associated to the Analytics variable on the right. But we're looking for a reverse mapping of this. 









If you're using ADC, you'll have the AA column name in there. We also have an ADC mapping doc page. (Analytics field mappings doc page maps the fields)



Make a table (or a section) that talks about fields that are new to CJA, like cross-channel fields (call center, etc.) 

The number of AA columns that they can map is not going to be that big (maybe 100). The number of columns that don't map will be huge.

## Data feed column reference

### Adobe Analytics data feed columns that are included by default in Customer Journey Analytics WebSDK implementations

### Adobe Analytics data feed columns that can be included in Customer Journey Analytics data feed

### Adobe Analytics data feed columns that don't apply to Customer Journey Analytics


### Columns, descriptions, and data types

Use this section to learn what data is contained in each column. Most implementations don't use every column, so this section can be referenced when determining which columns to include in a data feed export.

-->
