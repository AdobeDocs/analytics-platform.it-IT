---
title: Panoramica di Data Mirror
description: Come sincronizzare i dati tra le soluzioni native di data warehouse e Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: a6cdade9790ef4bc222eb5979b7370f7403b5ad5
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 1%

---

# Panoramica di Experience Platform Data Mirror

{{release-limited-testing}}

Data Mirror è una funzionalità di Experience Platform che consente l’acquisizione delle modifiche a livello di riga dai database esterni nel data lake utilizzando schemi basati su modelli. Mantiene le relazioni tra i dati, applica l’univocità e supporta il controllo delle versioni senza richiedere processi ETL (Extract, Transform, Load) a monte.

Utilizza Data Mirror per sincronizzare inserimenti, aggiornamenti ed eliminazioni (dati mutabili) da soluzioni native per data warehouse esterne come [!DNL Snowflake], [!DNL Azure Databricks] o [!DNL Google BigQuery] direttamente in Experience Platform. Data Mirror consente di preservare la struttura del modello di database esistente e l’integrità dei dati durante l’inserimento dei dati in Experience Platform.


## Funzionalità e vantaggi

Data Mirror offre le seguenti funzionalità essenziali per la sincronizzazione del database:

* **Imposizione chiave primaria**. Assicura l’univocità all’interno dei set di dati e impedisce la duplicazione dei record durante l’acquisizione.
* **Acquisizione delle modifiche a livello di riga**. Supporta le modifiche granulari dei dati, incluse le operazioni di upsert ed eliminazione, con un controllo di precisione.
* **Relazioni schema**. Abilita le relazioni chiave esterna e primaria tra set di dati tramite descrittori.
* **Gestione eventi fuori servizio**. Elabora gli eventi di modifica utilizzando i descrittori di versione e marca temporale, anche quando arrivano fuori sequenza.
* **Integrazione warehouse diretta**. Consente la connessione con data warehouse cloud supportati per la sincronizzazione delle modifiche in tempo reale.

Utilizza Data Mirror per acquisire le modifiche direttamente dai sistemi di origine, applicare l’integrità dello schema e rendere i dati disponibili per le attività di analisi, orchestrazione del percorso e flussi di lavoro di conformità. Data Mirror elimina i complessi processi ETL a monte e accelera l&#39;implementazione consentendo il mirroring diretto dei modelli di database esistenti. Questa eliminazione può migliorare la governance dei dati attraverso un controllo preciso sulle eliminazioni e sulle operazioni di igiene dei dati.

<!-- Add link when AEP docs are ready... -->

Consulta anche la documentazione di Experience Platform su Data Mirror.


## Data Mirror per Customer Journey Analytics

>[!NOTE]
>
>La funzionalità Experience Platform Data Mirror per Customer Journey Analytics è disponibile in una **versione beta pubblica** fino al 25 marzo 2026. Durante il periodo beta, gli aggiornamenti CDC (Change Data Capture) sono limitati a 10 milioni di righe di modifica giornaliere spettanti per Customer Journey Analytics. Adobe si riserva il diritto di terminare l’accesso in versione beta alla funzionalità Experience Platform Data Mirror nel caso in cui l’organizzazione superi questo limite. Per ulteriori informazioni su questa funzione, comprese le implicazioni di fatturazione, consulta questa sezione della documentazione di Experience League.
>

La funzionalità Experience Platform Data Mirror per Customer Journey Analytics è disponibile per le soluzioni native data warehouse selezionate ([!DNL Azure Databricks], [!DNL Google BigQuery] e [!DNL Snowflake]). La versione Customer Journey Analytics della funzionalità Data Mirror richiede una configurazione e un’installazione corrette di diversi componenti:

* [Soluzione nativa per data warehouse](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)


>[!MORELIKETHIS]
>
>[Guida rapida di Data Mirror: simulare e utilizzare dati basati su modelli](model-based.md)
>
