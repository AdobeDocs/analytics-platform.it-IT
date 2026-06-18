---
title: Panoramica di Data Mirror
description: Come sincronizzare i dati tra le soluzioni native di data warehouse e Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
autotag-review: '2026-05-19T08:55:53.979Z'
TQID: 'https://experienceleague.adobe.com/10YCh2cnMTVriKKVOyYfzFfngvGQ2VVHOxzedE5NpWA'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: bfef374d-acfd-4c57-bf74-a2b36053c545id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 3%

---

# Panoramica di Experience Platform Data Mirror

Data Mirror è una funzionalità di Experience Platform che consente l’acquisizione delle modifiche a livello di riga dai database esterni nel data lake utilizzando schemi relazionali. Mantiene le relazioni tra i dati, applica l’univocità e supporta il controllo delle versioni senza richiedere processi ETL (Extract, Transform, and Load) a monte.

Utilizzare Experience Platform Data Mirror per sincronizzare inserimenti, aggiornamenti ed eliminazioni (dati mutabili) da soluzioni native data warehouse esterne ([!DNL Snowflake], [!DNL Azure Databricks] o [!DNL Google BigQuery]) direttamente con i dati in Experience Platform. Data Mirror consente di preservare la struttura del modello di database esistente e l’integrità dei dati durante l’inserimento dei dati in Experience Platform.

## Funzionalità e vantaggi

Data Mirror offre le seguenti funzionalità essenziali per la sincronizzazione del database:

* **Imposizione chiave primaria.** Assicura l’univocità all’interno dei set di dati e impedisce la duplicazione dei record durante l’acquisizione.
* **Acquisizione delle modifiche a livello di riga.** Supporta le modifiche granulari dei dati, incluse le operazioni di upsert ed eliminazione, con un controllo di precisione.
* **Relazioni schema.** Abilita le relazioni chiave esterna e primaria tra set di dati tramite descrittori.
* **Gestione eventi fuori servizio.** Elabora gli eventi di modifica utilizzando i descrittori di versione e marca temporale, anche quando arrivano fuori sequenza.
* **Integrazione warehouse diretta.** Consente la connessione con data warehouse cloud supportati per la sincronizzazione delle modifiche in tempo reale.

Utilizza Data Mirror per acquisire le modifiche direttamente dai sistemi di origine, applicare l’integrità dello schema e rendere i dati disponibili per le attività di analisi, orchestrazione del percorso e flussi di lavoro di conformità. Data Mirror elimina i complessi processi ETL a monte e accelera l&#39;implementazione consentendo il mirroring diretto dei modelli di database esistenti. Questa eliminazione può migliorare la governance dei dati attraverso un controllo preciso sulle eliminazioni e sulle operazioni di igiene dei dati.

Consulta anche la [documentazione di Experience Platform su Data Mirror](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}.

## Data Mirror per Customer Journey Analytics

>[!NOTE]
>
>Data Mirror è una funzione che supporta la sincronizzazione dei dati da data warehouse selezionati tramite l&#39;acquisizione dati di modifica (CDC) per l&#39;analisi in Customer Journey Analytics.<br/>Fare riferimento alla descrizione del prodotto applicabile per comprendere in che modo la funzione può influire sul consumo del limite di acquisizione annuale.
>

>[!IMPORTANT]
>
>I set di dati di acquisizione dei dati di modifica creati in Experience Platform ai fini di Data Mirror per Customer Journey Analytics non devono essere riutilizzati in altre soluzioni Experience Platform come Real-Time Customer Data Platform o Journey Optimizer. Se desideri utilizzare gli stessi dati per queste soluzioni, considera di creare set di dati alternativi con gli stessi dati.
>



Experience Platform Data Mirror for Customer Journey Analytics è disponibile per le soluzioni native data warehouse selezionate ([!DNL Azure Databricks], [!DNL Google BigQuery] e [!DNL Snowflake]). La versione Customer Journey Analytics di Experience Platform Data Mirror richiede la corretta configurazione delle seguenti applicazioni o componenti:

* [Soluzioni native per data warehouse](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Guida rapida di Data Mirror: mirroring e utilizzo dei dati relazionali](relational.md)
>[Data Mirror (documentazione Experience Platform)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[Schemi relazionali (documentazione Experience Platform)](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/schema/relational)
