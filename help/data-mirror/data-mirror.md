---
title: Panoramica di Data Mirror
description: Come sincronizzare i dati tra le soluzioni native di data warehouse e Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: 25d0647c6a764d8f4306a5c049a7a68e0426cef9
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 2%

---

# Panoramica di Experience Platform Data Mirror

{{release-limited-testing}}

Data Mirror è una funzionalità di Experience Platform che consente l’acquisizione delle modifiche a livello di riga dai database esterni nel data lake utilizzando schemi basati su modelli. Mantiene le relazioni tra i dati, applica l’univocità e supporta il controllo delle versioni senza richiedere processi ETL (Extract, Transform, and Load) a monte.

Utilizzare Experience Platform Data Mirror per sincronizzare inserimenti, aggiornamenti ed eliminazioni (dati mutabili) da soluzioni native data warehouse esterne ([!DNL Snowflake], [!DNL Azure Databricks] o [!DNL Google BigQuery]) direttamente con i dati in Experience Platform. Data Mirror consente di preservare la struttura del modello di database esistente e l’integrità dei dati durante l’inserimento dei dati in Experience Platform.

## Funzionalità e vantaggi

Data Mirror offre le seguenti funzionalità essenziali per la sincronizzazione del database:

* **Applicazione della chiave primaria.** Assicura l&#39;univocità all&#39;interno dei set di dati e impedisce la duplicazione dei record durante l&#39;acquisizione.
* **Acquisizione delle modifiche a livello di riga.** supporta modifiche granulari dei dati, inclusi upsert ed eliminazioni, con controllo di precisione.
* **Relazioni schema.** Abilita le relazioni chiave primaria e esterna tra i set di dati tramite descrittori.
* **Gestione degli eventi fuori servizio.** Elabora gli eventi di modifica utilizzando i descrittori di versione e timestamp, anche quando arrivano fuori sequenza.
* **Integrazione con warehouse diretto.** si connette con data warehouse cloud supportati per la sincronizzazione delle modifiche in tempo reale.

Utilizza Data Mirror per acquisire le modifiche direttamente dai sistemi di origine, applicare l’integrità dello schema e rendere i dati disponibili per le attività di analisi, orchestrazione del percorso e flussi di lavoro di conformità. Data Mirror elimina i complessi processi ETL a monte e accelera l&#39;implementazione consentendo il mirroring diretto dei modelli di database esistenti. Questa eliminazione può migliorare la governance dei dati attraverso un controllo preciso sulle eliminazioni e sulle operazioni di igiene dei dati.

Consulta anche la [documentazione di Experience Platform su Data Mirror](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}.

## Data Mirror per Customer Journey Analytics

>[!NOTE]
>
>La funzionalità Experience Platform Data Mirror per Customer Journey Analytics è disponibile in una **versione beta pubblica** fino al 25 marzo 2026. I clienti possono acquisire fino a 2 milioni di righe di modifica al giorno in Adobe Experience Platform Data Lake tramite i connettori di origine. Adobe si riserva il diritto di terminare l’accesso in versione beta alle funzionalità di Experience Platform Data Mirror nel caso in cui l’organizzazione superi tali limiti. <br/>Per richiedere l&#39;accesso a questa funzionalità, contatta il team del tuo account Adobe.
>

Experience Platform Data Mirror for Customer Journey Analytics è disponibile per le soluzioni native data warehouse selezionate ([!DNL Azure Databricks], [!DNL Google BigQuery] e [!DNL Snowflake]). La versione Customer Journey Analytics di Experience Platform Data Mirror richiede la corretta configurazione delle seguenti applicazioni o componenti:

* [Soluzioni native per data warehouse](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Guida rapida di Data Mirror: simulare e utilizzare dati basati su modelli](model-based.md)
>>[Data Mirror (documentazione Experience Platform)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>>[Schemi basati su modelli (documentazione di Experience Platform)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/model-based)
